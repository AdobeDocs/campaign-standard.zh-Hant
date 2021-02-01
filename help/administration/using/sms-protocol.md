---
solution: Campaign Standard
product: campaign
title: SMS 連接器通訊協定及設定
description: 進一步瞭解SMS連接器以及如何設定它。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 4b87ebc2585b87f918bbd688c5858394d8d4a742
workflow-type: tm+mt
source-wordcount: '8666'
ht-degree: 0%

---


# SMS 連接器通訊協定及設定 {#sms-connector-protocol}

>[!NOTE]
>
>此[頁面](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.htmln#sending-messages)中提供Adobe Campaign Classic的&#x200B;**SMS連接器通訊協定和設定**。
>
>通過本文檔，所有有關協定、欄位名和值的詳細資訊的引用都引用[SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

## 概觀 {#overview}

SMS可能僅限於傳送沒有格式的簡短文字訊息，但其簡單性使它成為有價值的通訊管道。

傳送SMS的主要方式有兩種：

* 手動從電話傳送，這是人們直接進行溝通的通常方式。

* 從網際網路傳送，就像Adobe Campaign傳送訊息的方式。 為此，您需要一個將網際網路連接到移動網路的SMS服務提供商。
Adobe Campaign使用SMPP通訊協定將SMS傳送給服務供應商。

本檔案將引導您完成Adobe Campaign與SMPP供應商之間的連線設定。

SMPP供應商有時可能會偏離官方規格，但Adobe Campaign中的SMS連接器提供許多選項來調整其行為，使其與大部分供應商相容。

>[!IMPORTANT]
>
>設定與新提供程式的連接可能需要一些技術知識、TCP知識、二進位、十六進位表示和文本編碼。 此外，還需要與供應商積極合作。

### SMS類型{#sms-types}

當透過SMS提供者傳送大量SMS時，您會遇到三種不同的SMS:

* **SMS MT（行動終止）**:Adobe Campaign透過SMPP供應商向行動電話發出的SMS。

* **SMS MO（源自行動裝置）**:行動裝置透過SMPP供應商傳送至Adobe Campaign的SMS。

* **SMS SR（狀態報告）、DR或DLR（傳送收據）**:行動裝置透過SMPP提供者傳送回執給Adobe Campaign，指出SMS已成功接收。Adobe Campaign也可能會收到SR，指出無法傳送訊息，通常會附上錯誤的說明。

您需要區分鳴謝（RESP PDU, SMPP協定的一部分）和SR :SR是一種通過網路端到端發送的SMS，而確認只是確認一次傳輸成功。

確認聲明和SR都可觸發錯誤，區分這兩種錯誤將有助於進行故障排除。

### SMS {#information-sms}攜帶的資訊

簡訊攜帶的資訊比文字更多。 以下是您在SMS中可尋找的項目清單：

* 文字（限制為140位元組），這表示70到160個字元之間（視編碼而定）。 如需詳細資訊和限制，請參閱下方的[SMS文字編碼](../../administration/using/sms-protocol.md#sms-text-encoding)。

* 收件者地址，有時稱為`ADC`或`MSISDN`。 這就是接收SMS的行動裝置的數目。

* 發件人地址，可以稱為`oADC`或有時稱為`sender id`。 這可以是日常使用的電話號碼、透過供應商傳送的簡短代碼或名稱。 名稱是選用功能，在此情況下，您無法回覆SMS。

* 用於指示消息是否為快閃消息的標誌。 快閃記憶體消息是不儲存在記憶體中的彈出消息。

* 指示是否需要SR的標誌。

* 有效日期，之後不允許網路設備重試。

* `data_coding`欄位，指出文字的編碼。

## SMPP協定{#smpp-protocol}

Adobe Campaign Standard支援SMPP通訊協定3.4版。這是一種廣泛的協定，允許向提供者(SMSC)發送SMS，並接收SMS和接收。 有關詳細資訊，請參閱[SMPP文檔](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

SMS服務提供商端的網路設備通常稱為SMSC。

### SMPP連接{#smpp-connections}

Adobe Campaign透過TCP連線至SMS服務供應商的網路設備。 SMPP通訊協定會設定從Adobe Campaign到提供者的永久TCP連線。 TCP連線一律由Adobe Campaign啟動，甚至是接收訊息。
SMPP會開啟1或2個TCP連接，具體取決於其模式。 所有連線一律由Adobe Campaign啟動。

SMPP協定可以在兩種模式下工作：

* **發射機+接收機（或TX+RX）**:兩個獨立的TCP連接用於發送和接收消息。
* **收發器(Abor TRX)**:單個TCP連接用於發送和接收消息。

>[!NOTE]
>
>TRX是Adobe Campaign Standard的偏好選擇，因為它可減少連線數量，並簡化連線在發生故障時的復原。

### SMPP PDU {#smpp-pdu}

SMPP傳輸單元（「資料包」）稱為PDU。 **PDU**&#x200B;包含命令、狀態、序列號和資料。

每個PDU都必須由`SMPP RESP PDU`（同步響應）確認。 請求可以流水線化：發送方可以發送許多命令而無需等待`RESP`，隨時可流水線處理的請求數稱為窗口。 `RESP PDU` 可能以任何順序到達，與其相應的啟動器PDU的順序無關。

在分離的&#x200B;**Transmitter+receiver**&#x200B;模式中，所使用的連接取決於所發送的消息類型。 發射機連接用於MT，接收機連接用於MO和SR。 每種消息的請求和響應都通過相同的TCP連接發送。

例如，在發送MT時，使用發射器連接，並通過發射器通道發送確認MT的`RESP`。 當您收到MO（或SR）時，接收器連接用於接收MO併發送確認MO的`RESP`。

![](assets/do-not-localize/sms_protocol_1.png)

在Adobe Campaign Standard中，MT和SR協調是MTA的原生功能，因此沒有專用的SMS程式。

成功的`SUBMIT_SM_RESP PDU`在成功的`DELIVER_SM (SR) PDU`觸發「已接收」消息狀態時，會在發送日誌中觸發「已發送」消息狀態。

### 安全方面{#security-aspects}

協定本身不加密。 大部分的提供者會實作允許清單上的IP變數，因此必須向提供者宣告Adobe Campaign伺服器IP位址。

Adobe Campaign支援在系結階段傳遞登入和密碼。 它還支援SMPP而非TLS。 應當指出，為了獲得適當的安全性，需要證書。 雖然SMPP連接器允許略過證書檢查，但它只應用於測試，因為沒有證書的TLS提供了明顯較低的安全級別。

連接器使用系統`openssl`庫提供的預設證書。 通常由Debian上的`/etc/ssl/certs`目錄提供。 預設情況下，此目錄由&quot;ca-certificates&quot;包提供，但可自定義。

### 每種PDU中的資訊{#information-pdu}

每種PDU都有不同的欄位，這些欄位包含不同的資訊。 [SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)中對這些PDU的詳細說明。

以下各節介紹PDU及其同步響應(`*_RESP PDU`)。 所有PDU都必須由相應的`RESP`進行確認，這是規範的必備部分。

PDU可以有可選欄位。 此處僅介紹最常見的欄位。 有關詳細資訊，請參閱[SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

#### BIND_TRANSMITTER / BIND_RECEIVER / BIND_TURNSEIVER {#bind-transmitter}

此PDU用於啟動到SMSC的連接。 **發射機**、 **** 接收機 **** 和收發機模式只更改允許通過此連接傳輸的SMS類型，具體來說：

| 模式 | 允許的SMS類型 |
|:-:|:-:|
| 發射器 | MT |
| 接收器 | MO + SR |
| 收發器 | MT + MO + SR |

`BIND_* PDU`中值得注意的欄位：

* **system_id**:用於驗證的登錄。在外部帳戶中設定。

* **密碼**:用於驗證的密碼。在外部帳戶中設定。

* **system_type**:需要為某些提供者設定特定值。在外部帳戶中設定，所有版本都提供。 通常可區分不同類型的合約、管道、國家等。

* **addr_** tonand  **addr_npi**:某些提供者要求。由外部帳戶中的`Bind TON`和`Bind NPI`設定來設定。

* **address_range**:某些提供者要求。大多數情況下，此為此連接上允許的快捷方式代碼清單。 在外部帳戶中設定。

`BIND_*_RESP` 沒有特定欄位，則會確認連線是否成功。

#### 解除綁定{#unbind}

此PDU必須由系統發送，才能斷開連接。 必須等待匹配`UNBIND_RESP PDU`才能關閉連接。

符合SMSC的TCP連線不得關閉，而TCP連線由Adobe Campaign連接器控制。

#### SUBMIT_SM {#submit-sm}

此PDU向SMSC發送MT。 其響應PDU提供MT的ID。

`SUBMIT_SM PDU`中值得注意的欄位：

* **service_type**:需要。在傳送屬性中設定。

* **source_addr_** tonand  **source_addr_npi**:指示傳輸的源地址類型。這些欄位的含義是標準化的，但由於有些提供者使用不同的欄位，因此您應要求提供者提供正確的值。 在外部帳戶中設定。

* **source_addr**:MT的源地址/oADC。它會顯示在行動電話上。 在外部帳戶和傳送中設定，傳送中的值優先於外部帳戶的值。

* **dest_addr_** ton和 **dest_addr_npi**:指示傳輸的目的地址類型（例如本地或國際格式）。這些欄位的含義是標準化的，但由於有些提供者使用不同的欄位，因此您應要求提供者提供正確的值。 在外部帳戶中設定。

* **destination_addr**:收件者位址、電話號碼或MSISDN。

* **esm_class**:用來判斷文字欄位中是否使用UDH。如果未使用`message_payload`模式，則連接器會自動啟用拆分SMS。

* **priority_flag**:此消息的優先順序高於其他消息。這與交付本身的優先順序有關。

* **validity_period**:時間戳記，之後不應嘗試重試。設定在傳送本身。

* **registered_delivery**:說明是否請求SR。Adobe Campaign一律會設定此標幟，但自動回覆除外。 對於多部件消息，僅為第一部件設定標誌。 所有版本都有相同的行為。

* **data_coding**:表示文字欄位中使用的編碼。如需詳細資訊，請參閱[SMS文字編碼](../../administration/using/sms-protocol.md#sms-text-encoding)一節。

* **short_message**:訊息的文字。如果使用UDH，這也包含UHD標題。

Adobe Campaign支援下列選用欄位：

* **dest_addr_subut**:用於指定SMS的目標：flash、行動或SIM卡。在傳送屬性中設定。

* **message_payload**:在外部帳戶中啟用後，將在單個PDU中發送長消息，並在此欄位中發送文 `short_message` 本。

#### SUBMIT_SM_RESP {#submit-sm-resp}

此PDU將包含MT的ID。 這對於與傳入的SR匹配非常有用。

>[!IMPORTANT]
>
>許多提供者會以十六進位方式傳送MT ID。 請務必在外部帳戶中正確設定MT確認&#x200B;**中的** ID格式。

某些提供者在發送SR後發送`SUBMIT_SM_RESP`。 為了說明該行為，Adobe Campaign會等待30秒後，將&#x200B;**無效訊息ID**&#x200B;回覆給SR，其ID未知。

#### DELIVER_SM {#delivery-sm}

此PDU由SMSC傳送至Adobe Campaign。 它包含MO或SR。

大部分欄位的含義與其`SUBMIT_SM`對應項目相同。 以下是實用欄位清單：

* **source_addr**:MO/SR的源地址。通常這是電話號碼。

* **destination_addr**:接收MO或SR的簡碼。

* **esm_class**:用來判斷PDU是MO還是SR。

* **short_message**:文字。對於SR ，它包含SMPP協定規範附錄B中介紹的資料。 有關詳細資訊，請參見[SR錯誤管理](../../administration/using/sms-protocol.md#sr-error-management)。

Adobe Campaign可在`receipted_message_id`選用欄位中讀取訊息ID，並進行一些設定調整。

#### DELIVER_SM_RESP {#deliver-sm-resp}

此PDU由Adobe Campaign傳送，以確認SR和MO。

Adobe Campaign Standard只會在所有處理步驟均成功後傳送`DELIVER_SM_RESP`。 這可保證不會確認SR或MO，同時仍有處理錯誤的風險。

#### INQUIRE_LINK {#enquire-links}

此PDU僅用於檢查連接是否為活動連接。 頻率應根據供應商的需求來設定。

預設60秒應符合外部帳戶中設定的大部分設定。

#### INQUIRE_LINK_RESP {#enquire-links-resp}

此PDU確認連接是活的。

### 多部分SMS（長SMS）{#multipart}

多部分簡訊(SMS)或長篇簡訊(SMS)是以多個部分傳送的簡訊。 由於行動網路通訊協定的技術限制，SMS不能大於140位元組，否則需要分割。 請參閱[SMS文字編碼](../../administration/using/sms-protocol.md#sms-text-encoding)一節，進一步瞭解SMS中可容納的字元數。

長訊息的每個部分都是個別的SMS。 這些部件獨立地在網路上運行，並由接收行動電話組裝。 為處理重試和連線問題，Adobe Campaign會以反向順序傳送這些部分，並僅在訊息的第一部分（最後一次傳送）上要求SR。 由於行動電話只會在收到其第一部分時顯示訊息，因此在行動電話上，其他部分的重試不會產生重複。

使用&#x200B;**傳送範本**&#x200B;中的&#x200B;**每則訊息的最大SMS數設定，可設定每則訊息的最大SMS數。**&#x200B;在發送時，如果訊息超過此限制，會因為SMS故障過長而失敗。

有2種方式可傳送長篇簡訊：

* **UDH**:預設和建議的傳送長訊息方式。在此模式下，連接器將消息拆分為多個`SUBMIT_SM PDU`s，其中包含UDH資訊。 此通訊協定是行動電話本身使用的通訊協定。 這表示Adobe Campaign對訊息產生的控制力最強，因此能夠精確計算已傳送的部件數及分割方式。

* **message_payload**:以單一方式傳送長資訊 `SUBMIT_SM PDU`。提供者必須分割它，這表示Adobe Campaign無法確切知道已傳送的零件數。 有些提供者需要此模式，但我們建議您只在不支援UDH時才使用。

有關協定和格式的詳細資訊，請參閱[SUBMIT_SM PDU](../../administration/using/sms-protocol.md#information-pdu)的`esm_class`、`short_message`和`message_payload`欄位的說明。

### 吞吐量上限設定和窗口{#throughput-capping}

大多數提供商要求每個SMPP連接的吞吐量限制。 這可透過在外部帳戶中設定數個簡訊來達成。 請注意，吞吐量調節是按每個連接進行的，總有效吞吐量是每個連接的限制乘以連接總數。 這在[同時連接](../../administration/using/sms-protocol.md#connection-settings)部分中有詳細說明。

要達到最大吞吐量，您需要微調最大發送窗口。 發送窗口是可以在不等待`SUBMIT_SM_RESP`的情況下發送的`SUBMIT_SM PDU`數。 有關詳細資訊，請參閱[發送窗口設定](../../administration/using/sms-protocol.md#throughput-timeouts)部分。

### SR和錯誤管理（「附錄B」）{#sr-error-management}

SMPP協定定義了`RESP PDU`s中的標準同步錯誤，但並未定義SR的錯誤代碼。 每個提供者都使用各自的錯誤碼來表達其含義。

建議在[SMPP協定規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第167頁）的附錄B部分中提出，但不列出實際錯誤代碼及其含義。

為了適應錯誤管理，Adobe Campaign的廣播訊息系統已運用於正確布建錯誤及其嚴重性（硬式、軟式等）。

如上所述，存在兩種不同的錯誤：

* 在`SUBMIT_SM_RESP`中發生的同步回覆，會在訊息傳送至SMSC後立即發生
* 回執，這些回執可能會在行動裝置收到訊息或訊息逾時時時產生。 在這種情況下，錯誤在SR中發現。

收到SR時，其`short_message`欄位（例如附錄B符合要求的實施）中可找到狀態和錯誤。 PDU的`short_message`欄位通常稱為&#x200B;**文本欄位**，因為它包含MT中的文本。 如果是SR，則它包含技術資訊加上名為&#x200B;**Text**&#x200B;的子欄位。 這2個欄位不同，`short_message`實際上包含&#x200B;**Text**&#x200B;欄位和其他資訊。

#### SR文本欄位格式{#sr-text-field-format}

規格建議在SR文本欄位中使用此格式。 它是子欄位的清單，以分隔空格的冒號分隔欄位名稱及其值。 欄位名稱不區分大小寫。

與附錄B建議匹配的SR文本欄位示例：

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

id欄位是`SUBMIT_SM_RESP PDU`中收到的ID，即MT的確認。

`sub` 而且 `dlvrd` 應計算已傳送的部件和已傳送訊息的數量，但Adobe Campaign並未使用此功能，因為Broadlog系統提供更好、更整合的資訊。

`submit date` 欄位 `done date` 是指MT的傳送時間和行動裝置傳送SR的時間戳記。預期會出現時區問題，甚至是日期設定不正確之手機所指定的時間戳記錯誤。

stat欄位很重要，因為它會告訴消息的狀態。 唯一重要的狀態是`DELIVRD`、`UNDELIV`和`REJECTD`。 `DELIVRD`狀態表示成功，其他兩個表示錯誤。 其他值是可能的，但通常是中間通知，例如MT到達行動電信業者，但不是行動電話。 Adobe Campaign會忽略這些中介通知。

err欄位包含特定於提供程式的錯誤代碼。 提供者必須提供可能的錯誤代碼及其含義的表，才能解釋此值。

最後，文本欄位通常包含MT文本的開頭。 Adobe Campaign會忽略這一點，而有些供應商不會傳輸它，以避免PII洩漏和網路頻寬耗用。 在故障排除期間，可通過閱讀此欄位，更輕鬆地發現與測試MT匹配的SR。

### Adobe Campaign Standard Extended中的SR處理範例一般SMPP {#sr-processing}

此範例顯示附錄B建議後的實作案例、外部帳戶的預設值，以及成功的SMS MT。

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

首先，應用`id extraction`規則運算式來擷取ID，並與對應的MT協調。

然後，會套用`status extraction` regex和`error code extraction` regex來擷取這些欄位，並附加至字串。

Broadlog消息由此資訊構成，並附加原始未更改的字串以供參考：

```
SR ExampleProvider DELIVRD 000|MESSAGE=id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

然後對消息進行標準化，刪除MESSAGE部分，以便能夠使多個消息與相同的stat和err代碼匹配。

```
SR ExampleProvider DELIVRD 000|#MESSAGE#
```

如果廣播消息表中尚未設定消息，則將使用作為&#x200B;**firstText**&#x200B;的整個消息以及標準化消息建立新條目。 接著，連接器使用success和`error` regex來判斷它是成功還是失敗：

* 如果符合`success` regex，則會視為成功。

* 如果符合`error` regex，則訊息會限定為錯誤。

* 如果這兩個規則集不匹配，則會忽略SR。 可能是中間通知，Adobe Campaign不會處理。

預設情況下，所有錯誤都被設定為軟錯誤。 這表示必須手動布建硬性錯誤。

### SMS文字編碼{#sms-text-encoding}

如果發生編碼問題，請務必&#x200B;**聯絡SMSC提供者。**&#x200B;只有SMSC提供者具備其支援的編碼精確知識，並具備可能因技術平台限制而適用的特殊規則。

SMS訊息使用特殊的7位元編碼，通常稱為GSM7編碼。

在SMPP通訊協定中，GSM7文字將擴充為每個字元8位元，以方便疑難排解。 SMSC會在傳送至行動裝置之前，先將它封裝為每個字元7位元。 這表示SMS的`short_message`欄位在SMPP影格中最長可能有160位元組，而在行動網路上傳送時則限制為140位元組。

若發生編碼問題，請檢查下列重要事項：

* 請確定您知道哪些字元屬於哪個編碼。 GSM7不完全支援變音符號（重音）。 尤其在法語中，é和è是GSM7的一部分，但ê、â或ï不是。 西班牙語也是如此。

* C with cedilla(ç)僅在GSM7字母表的上方顯示，但有些手機會以下方顯示或以「智慧型」顯示。 一般建議是完全避免它，並移除嘶音或切換至UCS-2。

* **除非SMSC提供者明確** 要求，否則請勿在SMS中使用ASCII。此編碼會浪費空間，因為它具有8位元字元，而且比GSM7的覆蓋率更低。 在北美地區使用的CDMA網路可能需要此編碼。

* Latin-1並非一律受支援。 嘗試使用Latin-1之前，請先檢查與SMSC提供商的相容性。

* Adobe Campaign連接器不支援國家語言班次表。 您必須改用UCS-2或其他`data_coding`。

* UCS-2和UTF-16通常由手機混合。 使用UCS-2中未顯示的emoji和其他字元時，這個問題。

* 大部份的手機都沒有UCS-2字元的字型字元。 智慧手機往往能夠很容易地顯示稀有字元，但功能手機通常對它們所購買國家的母語有用的功能的支援有限。 如果您想要使用emoji或ASCII-art，請在傳送前在多種手機上進行測試。 Adobe Campaign預覽不會模擬遺失的字元，並會顯示網頁瀏覽器上可用的符號。

`data_coding`欄位會告訴您使用的編碼。 一個主要問題是，值0表示規範中的預設SMSC編碼，通常指GSM7。 請洽詢SMSC合作夥伴，Adobe Campaign僅支援與`data_coding` = 0關聯的編碼。 其他`data_coding`值通常遵循規範，但確保唯一方法是向SMSC提供程式檢查。

消息的最大大小取決於其編碼。 下表總結了所有相關資訊：

| 編碼 | 通常的data_coding | 訊息大小（字元） | 多部分SMS的部分大小 | 可用字元 |
|:-:|:-:|:-:|:-:|:-:|
| GSM7 | 0 | 160 | 152 | GSM7基本字元集+擴充功能（擴充字元需2個字元） |
| 拉丁文-1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 <br>UTF-16 | 8 | 70 | 67 | Unicode（視電話而定） |

## SMPP外部帳戶參數{#SMPP-parameters-external}

SMPP協定的每個實現都有許多變化。 為了提高相容性和適應性，可使用許多設定來更改SMPP連接器的行為。 本節介紹每個參數及其對連接器的影響。

### 常規參數和路由{#general-parameters-routing}

**限制此帳戶的MTA例項**

可以設定允許連接到SMPP提供程式的MTA實例數的限制。 勾選後，您最多可以指定使用多少個MTA。

此選項允許更精細地控制連接數，請參見[同時連接](../../administration/using/sms-protocol.md#connection-settings)。

如果您設定的值高於執行中的MTA數，則所有MTA都會正常執行：此選項僅限於限制，無法衍生其他MTA。

如果您需要精確控制連線數量（例如提供者需求），建議您永遠設定此選項，即使目前部署的MTA數目正確。 如果之後新增其他MTA，則仍會遵守連線限制。

### 連接設定{#connection-settings}

#### SMPP連接模式{#smpp-connection-mode}

在&#x200B;**收發器**&#x200B;模式或在分離的&#x200B;**發射器+接收器**&#x200B;模式中設定連接。 當切換到分離的&#x200B;**發射機+接收機**&#x200B;模式時，**SMPP連接模式**&#x200B;部分中的設定適用於發射機，而&#x200B;**接收機連接設定**&#x200B;部分中的設定僅適用於接收機連接，只有選中了&#x200B;**使用接收機**&#x200B;複選框。

#### SMSC實施名稱{#smsc-implementation-name}

設定SMSC實施的名稱。 應將其設定為提供程式的名稱。 請聯絡管理員或傳送能力團隊，瞭解要在此欄位中新增的項目。 在[SR錯誤管理](../../administration/using/sms-protocol.md#sr-error-management)部分中介紹了此欄位的角色。

#### 伺服器{#server}

要連接的伺服器的DNS名稱或IP地址。

#### 埠{#port}

要連接的TCP埠。

#### 帳戶{#account}

連接的登錄。 在BIND PDU的`system_id`欄位中傳遞。

#### 密碼{#password}

SMPP連接的口令。 在BIND PDU的口令欄位中傳遞。

#### 系統類型{#system-type}

在BIND PDU的`system_id`欄位中傳遞的值。 有些提供者需要特定值。

#### 同時連接{#simultaneous-connections}

在Adobe Campaign Standard中，它定義每個SMS執行緒和每個MTA程式的連線數。
MTA流程的數量由部署決定：通常有2個MTA和1個線程。 使用smppConnectorThreads設定，可在config-instance.xml檔案中變更執行緒數。 通常每個容器有1個MTA流程，每個MTA流程有1個線程。

Adobe Campaign Standard的連線總數公式：

* **總連接數=同時連接數*線程數* MTA數**

在外部帳戶中設定同時連線，在config-instance.xml檔案(smppConnectorThreads)中設定線程數，而在外部帳戶中可限制MTA數。

在分離的&#x200B;**發射器／接收器**&#x200B;模式中，上述連接數表示&#x200B;**發射器／接收器**&#x200B;對的數量，這意味著總連接數將是兩倍。

#### 在SMPP上啟用TLS {#enable-TLS}

使用TLS連線至提供者。 連接將加密。 TLS連線由OpenSSL程式庫管理，任何適用於OpenSSL的項目，在此連線中都成立。

#### 在日誌檔案{#enable-verbose-log-file}中啟用詳細的SMPP跟蹤

此設定會轉儲記錄檔中的所有SMPP流量。 在初始設定期間，通常需要調整參數。 在排除連接器故障時必須啟用此功能，並與提供者所看到的流量進行比較。

### 接收器連接設定{#receiver-connection}

此部分僅在分離的&#x200B;**transmitter+receiver**&#x200B;模式中可見。

#### 對接收器{#receiver-parameters}使用不同的參數

如果取消選中該框，則發射器和接收器的設定相同。

選中該框後，**連接設定**&#x200B;部分中的設定將應用於發射器，而&#x200B;**接收器連接**&#x200B;設定中的設定將應用於接收器。

**接收伺服器、埠、帳戶、密碼、系統類型**

這些設定在&#x200B;**transmitter+receiver**&#x200B;模式下適用於接收機。 它們的運作方式與發射器部分類似，請參閱上面以取得更多詳細資訊。

### SMPP通道設定{#smpp-channel-settings}

#### 允許字母音譯{#allow-character-transliteration}

音譯是尋找等效字元與遺失字元的過程。 例如，GSM編碼中遺失法文&quot;ê&quot;（含抑揚符號的e）字元，但可以用&quot;e&quot;取代，而不會影響可讀性。

如果取消勾選此方塊，如果文字編碼無法依現狀對字串進行編碼，就會失敗。

勾選此方塊時，文字編碼會嘗試將字串轉換為近似版本，而非失敗。 如果某些字元在目標編碼中沒有相同的字元，文字編碼將會失敗。

如需編碼程式的更一般說明，請參閱[定義編碼設定的特定對應。](../../administration/using/sms-protocol.md#SMSC-specifics)

#### 在資料庫{#incoming-mo-storing}中儲存傳入的MO

啟用後，傳入的MO將儲存在資料庫的inSMS表中。 您可以使用任何工作流程的查詢活動來查詢此表格。

#### 在SR處理{#real-time-kpi}期間啟用即時KPI更新

啟用後，當收到錯誤SR時，KPI將在主交付頁上即時更新。

缺點是效能低，因為它會產生資料庫爭用。 如果禁用，則&#x200B;**syncfromexec**&#x200B;工作流將更新統計資訊，每20分鐘運行一次。

#### 源編號{#source-number}

定義消息的預設源地址。 此設定僅適用於傳送中的來源編號空白時。

依預設，不會傳遞來源編號欄位，因此提供者會用它取代簡短代碼。

這會啟用傳送者位址/oADC覆寫功能。

#### 簡碼{#short-code}

指出帳戶的主要簡碼。 如果此帳戶使用多個簡短代碼，或者簡短代碼未知，請將此欄位留空。

指定簡短程式碼對下列兩個功能有幫助：

* 如果未提供原始碼，預覽會顯示簡碼。 它將反映手機上的真實行為。

* 自動回復功能的塊清單設定僅發送給隔離用戶特定短代碼。

#### 來源噸/NPI，目的地噸/NPI {#ton-npi}

[SMPP 3.4規格](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第117頁）第5.2.5節中介紹了TON（編號類型）和NPI（編號計畫指標）。 這些值應設定為提供程式的需要。

它們在`SUBMIT_SM PDU`的`source_addr_ton`、`source_addr_npi`、`dest_addr_ton`和`dest_addr_npi`欄位中按原樣傳輸。

#### 服務類型{#service-type}

在`SUBMIT_SM PDU`的`service_type`欄位中，此欄位會依現狀傳送。 根據提供者的需求進行設定。

### 吞吐量和超時{#throughput-timeouts}

這些設定控制SMPP通道的所有定時方面。 有些提供者需要非常精確地控制訊息速率、視窗和重試計時。 這些設定應設定為與供應商的能力及其合同中指明的條件相匹配的值。

#### 發送窗口{#sending-window}

該窗口是可以在不等待匹配`SUBMIT_SM_RESP`的情況下發送的`SUBMIT_SM PDU`數。

最大窗口為4的傳輸示例：

![](assets/do-not-localize/sms_protocol_2.png)

當網路連結有高延遲時，此視窗有助於提高總處理能力。  窗口的值必須至少是SMS/s乘以鏈路的延遲（以秒為單位），這樣連接器在發送下一條消息之前就不會等待`SUBMIT_SM_RESP`。
如果窗口太大，在發生連接問題時，可能會發送更多重複消息。 此外，大部分供應商對視窗有非常嚴格的限制，並拒絕超出限制的訊息。

如何計算最佳發送窗口公式：

* 測量`SUBMIT_SM`和`SUBMIT_SM_RESP`之間的最大延遲。

* 以秒為單位將此值乘以最大MT吞吐量。 這會提供最佳傳送視窗值。

範例：如果您在最大MT吞吐量中設定了300個SMS/s，並且平均在`SUBMIT_SM`和`SUBMIT_SM_RESP`之間有100毫秒的延遲，則最佳值為`300×0.1 = 30`。

#### 最大MT吞吐量{#max-mt-throughput}

每秒和每個連接的最大MT數。 此設定會嚴格執行，MTA絕不會以超過此限制的速度推送訊息。 對於需要精確調節的提供者而言，這非常有用。

要瞭解總吞吐量限制，請將此數乘以上述公式中詳述的連接總數。

0表示無限制，MTA會盡快傳送MT。

一般建議將此設定保持在1000以下，因為除非對最終架構進行適當基準測試，否則無法保證高於此數目的精確吞吐量。 如果您需要超過1000的吞吐量，請與您的供應商聯繫。 將連接數增加到1000 MT/s以上可能更好。

#### 重新連接{#time-reconnection}之前的時間

當TCP連接丟失時，連接器將等待此秒數，然後再嘗試建立連接。

#### MT {#expiration-period}的過期期

`SUBMIT_SM`與其匹配`SUBMIT_SM_RESP`之間的超時。 如果未按時收到`RESP`，則消息將被視為失敗，並且將應用MTA的全局重試策略。

#### 綁定超時{#bind-timeout}

TCP連接嘗試與`BIND_*_RESP`回覆之間的逾時。 逾時時，連線會由Adobe Campaign連接器關閉，而且會等候「時間」再重新連線，然後再次嘗試。

#### inquire_link句點{#enquire-link-period}

`enquire_link` 是一種特殊的PDU，用於保持連接正常。此時段以秒為單位。 促銷活動連接器僅在連線閒置時傳送`enquire_link`，以節省頻寬。 如果在此時段後兩次未收到RESP，則連接將被視為死機，並觸發重新連接過程。

### SMSC 細節 {#SMSC-specifics}

這些設定是進階設定，可讓Adobe Campaign連接器與大部分SMPP實作特性相適應。

#### 定義編碼{#encoding-specific-mapping}的特定映射

有關文本編碼的詳細資訊，請參閱[SMS文本編碼](../../administration/using/sms-protocol.md#sms-text-encoding)部分。

此設定可讓您定義自訂編碼對應，與規格不同。 您可以宣告編碼清單及其`data_coding`值。

MTA會嘗試使用清單中的第一個編碼進行編碼。 如果失敗，則會嘗試使用清單上的下一個編碼，等等。 如果不能使用任何編碼來編碼訊息，將會發生錯誤。 找到編碼後，MTA將建立`SUBMIT_SM PDU`，其中包含編碼文本，並設定`data_coding`欄位，其值在表中指定。

表中項的順序很重要：編碼會從上到下嘗試。 您應將最便宜或建議最多的編碼放在清單的頂端，接著是越來越昂貴的編碼。

請注意，UCS-2不會失敗，因為它可以編碼Adobe Campaign支援的所有字元，而UCS-2 SMS的最大長度則小得多：僅70個字元。

您也可以使用此設定，強制一律使用特定編碼，方法是在對應表格中僅聲明1行。

未勾選核取核取方塊時使用的預設對應等同於下表：

| data_coding | 編碼 |
|---|---|
| 0 | GSM |
| 9 | UCS-2 |

這表示MTA將嘗試在GSM中編碼訊息。 如果成功，它將以`data_coding`設為0的方式傳送。

如果消息無法在GSM中編碼，則將在UCS-2中編碼，並將`data_coding`設定為8。

#### 啟用message_payload {#enable-message-payload}

若未勾選，長SMS將被MTA分割，並透過UDH傳送多個`SUBMIT_SM PDU`。 該消息將由手機按照UDH資料重新合成。

勾選後，長SMS會傳送到一個SUBMIT_SM PDU中，並將文字放入message_payload選填欄位。 有關詳細資訊，請參見[SMPP規範](../../administration/using/sms-protocol.md#ACS-SMPP-connector)。

如果啟用此功能，Adobe Campaign將無法個別計算SMS部件：所有訊息都會計為一個部分傳送。

#### 傳送完整電話號碼{#send-full-phone-number}

如果未選中此複選框，則只向提供商發送電話號碼的數字（`SUBMIT_SM`欄位的`destination_addr`欄位）。 這是預設行為，因為國際數字指示符（通常為+前置詞）在SMPP中由TON和NPI欄位替換。

勾選核取方塊時，電話號碼會依原樣傳送，不需預處理和潛在空格、+首碼或井號／雜湊／星號。

此功能也會影響自動回覆登入清單功能的行為：如果未選中此複選框，則在插入隔離表的電話號碼中添加一個+前置詞，以補償SMPP協定本身從電話號碼中刪除的+前置詞。

#### 略過TLS證書檢查{#skip-tls}

啟用TLS時，請跳過所有證書檢查。

勾選後，連線不再安全，在生產中不應啟用。

它可用於除錯或測試用途。

#### 綁定TON/NPI {#bind-ton-npi}

[SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第117頁）第5.2.5節中所述的TON（編號類型）和NPI（編號計畫指示符）。 這些值應設定為提供程式需要的任何值。

它們在BIND PDU的`addr_ton`和`addr_npi`欄位中按原樣傳輸。

#### 地址範圍{#address-range}

在BIND PDU的address_range欄位中按原樣發送。 此值應設定為提供方需要的任何值。

#### 無效的ID確認計數{#invalid-id}

限制可針對單個SR發送的&#x200B;**消息ID無效** `DELIVER_SM_RESP`的數量。

**這應僅用於作為工作區的疑難排** 解目的，並在正常情況下設為0。

Fox範例，設定為2時：

* 提供者發送ID為&quot;1234&quot;的SR(`DELIVER_SM`)。

* 在資料庫中找不到ID &quot;1234&quot;。

* 連接器對該ID計數1 **無效ID**&#x200B;錯誤，因此會以「訊息ID無效」錯誤碼（一般行為）傳送`DELIVER_SM_RESP`。

* 提供程式將重試ID為&quot;1234&quot;的相同SR。

* 資料庫中仍然找不到ID &quot;1234&quot;。

* 連接器會計算該ID的2個&#x200B;**無效ID**&#x200B;錯誤，因此會傳送`DELIVER_SM_RESP` &quot;OK&quot;，即使未正確處理亦然。

* 當無效的SR塊合法且無法處理消息時，此功能旨在刷新提供方的SR緩衝區。

將此欄位設定為0會禁用始終返回&#x200B;**消息ID invalid**&#x200B;的機制，這是正常行為。

將此欄位設定為1會使連接器始終響應「OK」，即使ID無效。 這應設為1（僅限在監管下），以排除故障並在最短的時間內（例如從供應商端問題中恢復）。

#### SR {#regex-extraction}中ID的抽取規則

SR格式不嚴格由SMPP協定規範執行。 它只是說明書[附錄B](../../administration/using/sms-protocol.md#sr-error-management)（第167頁）中所述的建議。 有些SMPP實作者對此欄位的格式不同，因此Adobe Campaign需要一種擷取正確欄位的方法。

依預設，在`id:`之後最多可擷取10個英數字元。

regex必須只有一個捕獲組，並且包含括在括弧內的部件。 括弧必須包圍ID部分。 regex格式為PCRE。

在調整此設定時，請務必包含盡可能多的內容，以避免錯誤觸發。 如果有特定的前置詞，例如標準中的`id:`，請將它們包括在regex中。 此外，請盡量使用字詞分隔字元(\b)，以避免擷取字詞中間的文字。

regex中未包含足夠的上下文，可能會造成小的安全性缺陷：消息的實際內容可以包括在SR中。 如果只匹配沒有上下文的特定ID格式（例如UUID），則它可能是在解析實際文本內容，例如嵌入在文本欄位中的UUID，而不是ID。

#### 已應用Regex以確定成功／錯誤狀態{#regex-applied}

遇到具有未知stat/err欄位組合的消息時，這些regex將應用於stat欄位，以確定SR是成功還是錯誤。 SR的stat值與任何這些regex不匹配，將被忽略。

預設情況下，以`DELIV`開頭的stat值，如[附錄B](../../administration/using/sms-protocol.md#sr-error-management)中的`DELIVRD`將被視為成功傳遞，以及所有符合錯誤的stat值，例如。`REJECTED`、`UNDELIV`被視為錯誤。

#### MT確認{#id-format-mt}中的ID格式

這表示在`SUBMIT_SM_RESP PDU`的`message_id`欄位中傳回的ID格式。

* **不要修改**:ID會以ASCII編碼文字的形式儲存在資料庫中。不會進行預處理或篩選。

* **小數數**:ID應為ASCII格式的十進位數字。使用此設定時，前導和尾隨空格以及前導零會被移除。

* **十六進位數**:ID應為ASCII格式的十六進位數字，沒有前導0x或尾隨h。然後，ID會轉換為小數，然後再儲存在資料庫中。

* **十六進位字串**:ID應為ASCII編碼的文字，其本身是以十六進位編碼的位元組串。例如，在PDU中，您將找到`0x34 0x31 0x34 0x32 0x34 0x33` ，它轉換為ASCII &quot;414243&quot;。 然後，此字串會解碼為十六進位位元組字串，因此您會取得&quot;ABC&quot;:您將ID &quot;ABC&quot;儲存在資料庫中。

#### SR {#id-format-sr}中的ID格式

這表示SR中ID的`Extraction` regex所捕獲的ID的格式。 值與上述MT中的格式具有相同含義和行為。

**可選欄位中的SR ID或錯誤代碼**

如果勾選，則選用欄位的內容會附加至上述規則處理的文字。 文本的格式為`0xTAG:VALUE`,`0xTAG` ，是標籤的4位十六進位值，大寫如下：`0x002E`。

例如，您可能想在`receipted_message_id`欄位中擷取ID。 為此，請啟用此複選框，以下文本將添加到狀態：

```
0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739
```

在此範例中，0x001E是可選欄位的標籤，而UUID是欄位的值。

為了捕獲此值，您現在可以在SR欄位的ID的Extraction regex中設定以下regex:

```
\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b
```

>[!IMPORTANT]
>
>您只能擷取具有文字(ASCII/UTF-8)值的選用欄位。 具體而言，二進位欄位無法以目前的regex系統可靠地擷取。

**文字欄位中的SR ID或錯誤碼**

如果選中，則在處理SR的狀態文本期間將保留&#x200B;**Text**&#x200B;欄位。

如果提供者將此欄位中的重要資料（例如ID或狀態）放入此欄位，這就很有用。 通常，此欄位可安全地捨棄，因為它可能包含具有非ASCII編碼的文字，並中斷regex處理。

如果SR欄位中ID的`Extraction`regex不夠具體，則啟用此選項可能會引入非常小的安全漏洞。 **Text**&#x200B;欄位的內容可被解析為ID，攻擊者可使用該欄位插入偽造的ID，這可能導致部分拒絕服務情況。

**服務ID標籤**

允許添加自定義TLV。 此欄位會設定標籤部分。 在&#x200B;**服務或程式ID**&#x200B;值中，可根據傳送的進階參數自訂值。

此設定僅允許每條消息添加一個TLV選項。

>[!NOTE]
>
>從21.1版開始，現在可以新增多個選用參數。 如需詳細資訊，請參閱本[區段](../../administration/using/sms-protocol.md#automatic-reply-tlv)。

### 自動回覆傳送至 MO {#automatic-reply}

此功能可讓您快速回覆文字至MO，並處理傳送至區塊清單的簡短程式碼。

**關鍵字**&#x200B;和&#x200B;**簡碼**&#x200B;欄定義條件以觸發自動回覆。 如果兩個欄位都相符，則會傳送MO並觸發其他動作。 若要指定萬用字元，您應將欄位留空。 關鍵字會比對MO文字中第一個英數字詞，忽略標點符號和前導空格。 這表示&#x200B;**Keyword**&#x200B;欄位不能包含空格，且必須是單一字詞。

**Keyword**&#x200B;設定為首碼。 例如，如果您指定「AD」，則會比對「AD」、「ADAPT」和「ADOBE」。 如果您有多個具有通用首碼的關鍵字，則需要注意順序，因為關鍵字會從上到下處理。

**Reply**&#x200B;欄是要回覆的文字。 此欄位不提供個人化。 如果您將此欄位留空，將不會回覆任何訊息，但仍會觸發其他動作。

當&#x200B;**Additional action**&#x200B;欄同時符合&#x200B;**Keyword**&#x200B;和&#x200B;**Short code**&#x200B;時，空白的short code會符合所有的short code時，提供額外的動作。 您可以發送到隔離或從隔離中移除，對文本無任何回覆進行值。 如果您指定&#x200B;**Additional action**，但將&#x200B;**Reply**&#x200B;欄位保留為空白，則會執行動作，但不會傳送任何回覆。 隔離僅適用於指定的簡碼，或所有的簡碼（如果欄位為空）。

>[!IMPORTANT]
>
>發送完整電話號碼設定對自動回復隔離機制的行為有影響：如果未勾選發送完整電話號碼，則將加號(&quot;+&quot;)加上輸入隔離的電話號碼，使其與國際電話號碼格式相容。

表格中的所有項目都會以指定順序處理，直到有一個規則符合為止。 如果多個規則符合MO，則只會套用最上方的規則。

### 自動回覆可選參數(TLV){#automatic-reply-tlv}

從21.1版開始，您可以新增選用參數以自動回覆MT。 它們作為可選的TLV參數添加到回復的`SUBMIT_SM PDU`中，如[SMPP規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第131頁）第5.3節所述。

有關可選參數的詳細資訊，請參閱此[部分](../../administration/using/sms-protocol.md#smpp-optional-parameters)。

## SMS傳送範本參數{#sms-delivery-template-parameters}

某些參數可依傳送範本設定。

### 從欄位{#from-field}

此欄位為選擇性。 它允許覆蓋發送器地址(oADC)。 此欄位的內容放在`SUBMIT_SM PDU`的`source_addr`欄位中。

SMPP規範將欄位限制為21個字元，但有些提供者允許的值較長。 另請注意，某些國家／地區可能會套用非常嚴格的限制，例如長度、內容、允許的字元。

### 傳送參數 {#delivery-parameters}

#### 每條消息的SMS最大數量{#maximum-sms}

此設定僅在&#x200B;**消息裝載**&#x200B;設定被禁用時才起作用。 有關此問題的詳細資訊，請參閱此[頁](../../administration/using/configuring-sms-channel.md)。 如果訊息需要的SMS比此值還多，則會觸發錯誤。

SMS協定將SMS限制在255個部分，但有些手機無法將長消息與10個部分以上的部分組合在一起，這個限制取決於確切的型號。 我們建議您不要在每則訊息中超過5個部分。

由於個人化訊息在Adobe Campaign中的運作方式，訊息的大小可能會有所不同。 長資訊量大可能會增加發送成本。

#### 傳輸模式{#transmission-mode}

此欄位表示要傳輸的SMS類型：一般或快閃訊息，儲存在行動裝置或SIM卡上。

此設定會在`SUBMIT_SM PDU`的`dest_addr_subunit`選填欄位中傳送。

* **未** 指定的PDU中不發送可選欄位。

* **** Flash將值設為1。它會傳送快閃訊息，該訊息會在行動裝置上彈出，而不會儲存在記憶體中。

* **標** 準化將值設為0。它會傳送正常訊息。

* **儲存至** 行動裝置，將值設為2。它會要求手機將簡訊儲存在記憶體中。

* **儲存到** terminal將值設為3。它讓手機把簡訊儲存在SIM卡里。

#### 有效期{#validity-period}

有效期間在`SUBMIT_SM PDU`的`validity_period`欄位中傳送。 日期一律以絕對UTC時間格式（日期欄位將以&quot;00+&quot;結尾）。

#### SMPP可選參數(TLV){#smpp-optional-parameters}

從21.1版開始，您可以在每個傳送給此傳送的MT中新增多個可選參數。 這些可選參數被添加到回復的`SUBMIT_SM PDU`中，如[SMPP規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第131頁）的5.3節所述。

表格中的每一行都代表一個可選參數：

* **參數**:參數說明。未傳送給提供者。
* **標籤Id**:可選參數的標籤。必須是有效的十六進位，格式為0x1234。 無效的值會導致傳送準備錯誤。
* **值**:選填欄位的值。當傳送至提供者時，編碼為UTF-8。 編碼格式無法變更，無法傳送二進位值或使用不同的編碼，例如UTF-16或GSM7。

如果任何可選參數的&#x200B;**標籤Id**&#x200B;與外部帳戶中定義的&#x200B;**服務標籤Id**&#x200B;相同，則此表中定義的值將佔上風。

## SMPP連接器{#ACS-SMPP-connector}

![](assets/do-not-localize/sms_protocol_3.png)

箭頭代表資料流。

這裡要注意的最重要一點是，有多個SMPP連接器線程。 這些線程都是相同的，並且共用相同的配置。 這就是為什麼連接數總是乘以線程數。

客戶無法更改線程數，因為它需要更改配置檔案。

### SMPP連接器{#behavior-smpp-connector}的行為說明

#### 匹配MT 、 SR和broadlog條目{#matching-mt-sr}

在Adobe Campaign中，訊息是廣播項目。 在Adobe Campaign Standard中，外部連接器只需要知道工作中的廣告表格：`nmsBroadLogExec`。 工作流負責將廣播條目複製回其特定目標維(nmsBroadLogXXX)。

很遺憾，SMPP不允許傳送ID及訊息：提供者會為每個MT提供MT ID，然後提供一或多個具有相同ID的SR。

提供者提供的ID儲存在`nmsBroadLogExec`表的`sProviderId`欄中。 SR總是在成功發送和確認MT後到達，但有時候會出現故障，在Adobe Campaign中稱為傑出SR。 處理線程將這些SR臨時儲存在RAM中，直到完整資訊到達。

當確認MT(`SUBMIT_SM_RESP`)時，`sProviderId`會立即在資料庫中更新。

每個SR由SMPP處理線程單獨處理。 此過程是偽同步的：它被視為與外部同步，但是會與事件導向的實作內部實作。 只有在成功更新broadlog時才確認SR，如果遇到錯誤，則拒絕SR。

以下是應用於每個SR的過程：

* SR的ID是使用regex提取的。
* 在`nmsBroadLogExec:sProviderId`中搜索ID。
* 使用regex從SR中提取狀態+錯誤代碼。
* Broadlog消息機制用於限定錯誤並查找broadlog消息ID。
* Broadlog會以上述所有資訊更新。
* 確認SR。

檢查上述步驟需要&#x200B;**啟用詳細SMPP跟蹤**&#x200B;以手動檢查所有步驟是否正確應用。 每次連線至新的SMPP供應商時，都需要這個選項。

## 在上線前{#checklist}

此檢查清單提供您上線前應檢查的項目清單。 不完整的設定可能會導致許多問題。

### 檢查外部帳戶衝突{#external-account-conflict}

檢查您沒有舊的SMS外部帳戶。 如果您停用測試帳戶，您就會面臨在生產系統上重新啟用測試帳戶並產生潛在衝突的風險。

檢查沒有其他實例連接到此帳戶。 尤其是，請確定舞台環境未連線至帳戶。 有些提供者支援此項功能，但需要在Adobe Campaign端和提供者平台上進行非常特定的設定。

如果您需要在連線至相同提供者的相同Adobe Campaign例項上擁有多個帳戶，請連絡提供者，以確定他們實際區分這些帳戶的連線。 若有多個帳戶具有相同的登入，則需要額外的設定。

### 在檢查{#enable-verbose}期間啟用詳細SMPP跟蹤

您應始終在檢查期間啟用詳細的SMPP跟蹤。
即使您無法自行檢查記錄檔，「支援」也能更輕鬆地協助您。

### 測試您的SMS {#test}

* **使用各種字元傳送**
簡訊如果您需要傳送使用非GSM或非ASCII字元的簡訊，請盡量傳送包含多種字元的訊息。如果您設定自訂字元對應表格，請至少傳送一個SMS以供所有可能 
`data_coding` values.

* **檢查SR是否正**
確處理SMS應在傳送記錄中標示為已接收。傳送記錄應成功，如下所示：

檢查您是否已變更傳送提供者名稱。 傳送記錄不應包含    `SR yourProvider stat=DELIVRD err=000|#MESSAGE`
檢查您是否已變更傳送提供者名稱。在生產環境中，交付日誌不應包含**SR Generic**。

* **檢查MO是否**
已處理如果您需要處理MO（自動回覆、將MO儲存在資料庫等）試著做些測試。 針對所有自動回覆關鍵字傳送幾則簡訊，並檢查回覆是否足夠快，不超過幾秒。
登入記錄，Adobe Campaign會成功回覆 
`DELIVER_SM_RESP` (command_status=0)。

### 檢查PDU {#check-pdus}

即使消息看起來很成功，檢查PDU的格式是否正確也很重要。

連線至之前未連線至Adobe Campaign的提供者時，此步驟是必要的。

#### BIND {#bind}

檢查`BIND_* PDUs`是否正確傳送。 最需要檢查的是，提供程式始終返回成功的`BIND_*_RESP PDUs`(command_status = 0)。

檢查`BIND_* PDU`s的數量是否不太多。如果其中的連接太多，則可能表示連接不穩定。 有關詳細資訊，請參閱[不穩定連接問題](../../administration/using/sms-protocol.md#issues-unstable-connection)一節。

#### INQUIRE_LINK {#enquire-link-pdus}

檢查連接空閒時是否定期交換`ENQUIRE_LINK PDU`。

#### SUBMIT_SM / DELIVER_SM {#submit-sm-deliver-sm}

傳送訊息，然後在記錄檔中搜尋其對應的`SUBMIT_SM`、`SUBMIT_SM_RESP`、`DELIVER_SM`和`DELIVER_SM_RESP PDU`。

使用`SUBMIT_SM PDU`:

* 檢查`data_coding`是否正確，預設為0。
* 檢查`short_message`是否已正確編碼。 請嘗試使用支援多種編碼的十六進位轉換器來解碼。

使用`SUBMIT_SM_RESP PDU`:

* 檢查它是否成功，command_status = 0。
* 檢查其內文是否包含格式正確的ID，後面接著&#39;0&#39;位元組。

使用`DELIVER_SM PDU`:

* 解碼十六進位`short_message`欄位。
* 使用regex檢查工具檢查在SR中ID的`Extraction` regex中定義的regex是否只返回一個捕獲組，並且它捕獲消息中的整個ID。
* 檢查提取的ID是否與`SUBMIT_SM_RESP`中的ID匹配。
* 檢查在`Extraction` regex中定義的SR狀態regex是否返回stat欄位的內容。
* 檢查在`Extraction` regex中定義的SR錯誤規則表是否返回err欄位的內容。

使用`DELIVER_SM_RESP PDU`:

* 檢查收到`DELIVER_SM PDU`後是否快速傳送，通常不到1秒。
* 檢查它是否成功，command_status = 0。

### 詢問提供者是否一切正常{#provider}

即使您的SMS成功，請連絡提供者以檢視一切順序。

### 禁用詳細SMPP跟蹤{#disable-verbose}

完成所有檢查後，最後一件事是&#x200B;**禁用詳細SMPP跟蹤**&#x200B;以不生成太多日誌。 即使在生產系統上，您也可以重新啟用它們以排除故障。
