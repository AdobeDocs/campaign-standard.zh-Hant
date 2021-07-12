---
solution: Campaign Standard
product: campaign
title: 簡訊連接器通訊協定及設定
description: 進一步了解SMS連接器及如何設定。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: 執行個體設定
role: Admin
level: Experienced
exl-id: ea936128-1c51-483d-914c-6d06708456d6
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '8666'
ht-degree: 0%

---

# 簡訊連接器通訊協定及設定 {#sms-connector-protocol}

>[!NOTE]
>
>您可以在此[page](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html)中找到Adobe Campaign Classic的&#x200B;**SMS連接器通訊協定和設定**。
>
>通過本文檔，對協定、欄位名稱和值的詳細資訊的所有引用都引用了[SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

## 概覽 {#overview}

簡訊可能僅限於傳送沒有格式的簡訊，但其簡單性使其成為有價值的通訊通道。

傳送簡訊的主要方式有兩種：

* 用手機手動發送，這是人們之間直接交流的常用方式。

* 從網際網路傳送，就像Adobe Campaign傳送訊息的方式。 為此，您需要SMS服務提供者，將網際網路連線至行動網路。
Adobe Campaign使用SMPP通訊協定將SMS傳送給服務提供者。

本檔案會逐步引導您完成Adobe Campaign與SMPP提供者之間的連線設定。

SMPP提供商有時可能會偏離官方規範，但Adobe Campaign的SMS連接器提供許多選項來調整其行為，使其與大多數提供商相容。

>[!IMPORTANT]
>
>設定與新提供程式的連接可能需要一些技術技能、TCP知識、二進位、十六進位表示和文本編碼。 還需要與提供商積極合作。

### SMS類型 {#sms-types}

透過簡訊提供者傳送大量簡訊時，您會遇到三種不同的簡訊：

* **SMS MT（已終止行動）**:由Adobe Campaign透過SMPP提供者向行動電話發出的簡訊。

* **SMS MO（行動產生）**:行動裝置透過SMPP提供者傳送至Adobe Campaign的SMS。

* **SMS SR（狀態報表）、DR或DLR（傳送回執）**:行動裝置透過SMPP提供者傳送至Adobe Campaign的回執，指出SMS已成功接收。Adobe Campaign也可能會收到SR，指出無法傳送訊息，且通常包含錯誤的說明。

您需要區分確認（RESP PDU, SMPP協定的一部分）和SR:SR是一種通過網路端到端發送的簡訊，而確認只是一個傳輸成功的確認。

確認和SR都可觸發錯誤，區分這兩種錯誤將有助於進行故障排除。

### 簡訊所攜帶的資訊 {#information-sms}

簡訊攜帶的資訊多於文字。 以下是您在SMS中可找到的項目清單：

* 文字，限制為140個位元組，這表示根據編碼，70到160個字元之間。 如需詳細資訊和限制，請參閱下方的[SMS文字編碼](../../administration/using/sms-protocol.md#sms-text-encoding)。

* 收件者地址，有時稱為`ADC`或`MSISDN`。 這是接收簡訊的行動裝置數量。

* 寄件者地址，可稱為`oADC`或有時稱為`sender id`。 這可以是日常使用的電話號碼、透過提供者或名稱傳送的簡短代碼。 名稱是選用功能，在此情況下，您無法回覆SMS。

* 用於指示消息是否為快閃消息的標誌。 快閃記憶體消息是不儲存在記憶體中的彈出消息。

* 指示SR是否期望的標誌。

* 有效日期，之後不允許任何網路設備重試。

* `data_coding`欄位，指示文本的編碼。

## SMPP協定 {#smpp-protocol}

Adobe Campaign Standard支援SMPP協定3.4版。這是一種廣泛的協定，允許向提供者(SMSC)發送簡訊、接收簡訊以及接收。 有關詳細資訊，請參閱[SMPP文檔](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

SMS服務提供商端的網路設備通常稱為SMSC。

### SMPP連接 {#smpp-connections}

Adobe Campaign通過TCP連接到SMS服務提供商的網路設備。 SMPP協定將從Adobe Campaign到提供程式的永久TCP連接設定為。 TCP連接始終由Adobe Campaign啟動，甚至接收消息。
SMPP會根據其模式開啟1個或2個TCP連接。 所有連線一律由Adobe Campaign啟動。

SMPP協定可以兩種模式工作：

* **發射機+接收機（或TX+RX）**:兩個獨立的TCP連接用於發送和接收消息。
* **收發器（或TRX）**:單個TCP連接用於發送和接收消息。

>[!NOTE]
>
>Adobe Campaign Standard偏好使用TRX，因為TRX可減少連線數量，並在發生故障時簡化連線復原。

### SMPP PDU {#smpp-pdu}

SMPP傳輸單元（「資料包」）稱為PDU。 **PDU**&#x200B;包含命令、狀態、序列號和資料。

每個PDU必須通過`SMPP RESP PDU`（同步響應）進行確認。 請求可以流水線處理：發送方可以發送許多命令而不等待`RESP`，隨時可以流水處理的請求數稱為窗口。 `RESP PDU` 可能以與其相應啟動器PDU的順序無關的任何順序到達。

在分離的&#x200B;**Trimper+receiver**&#x200B;模式中，所使用的連接取決於所發送的消息的類型。 發射機連接用於MT，接收機連接用於MO和SR。 每種報文的請求和響應都通過相同的TCP連接發送。

例如，在發送MT時，使用發射器連接，並且確認MT的`RESP`也通過發射器通道發送。 當您收到MO（或SR）時，接收器連接用於接收MO併發送確認MO的`RESP`。

![](assets/do-not-localize/sms_protocol_1.png)

在Adobe Campaign Standard中，MT和SR調解是MTA的原生功能，因此沒有專屬的SMS程式。

成功的`SUBMIT_SM_RESP PDU`在發送日誌中觸發「已發送」消息狀態，而成功的`DELIVER_SM (SR) PDU`觸發「已接收」消息狀態。

### 安全方面 {#security-aspects}

協定本身未加密。 大部分的提供者都會在允許清單上實作IP的變體，因此Adobe Campaign伺服器IP位址必須向提供者宣告。

Adobe Campaign支援在系結階段期間傳遞登入和密碼。 也支援SMPP而非TLS。 應當指出，需要證書才能獲得適當的安全性。 雖然SMPP連接器允許略過憑證檢查，但它僅應用於測試，因為沒有憑證的TLS提供的安全性要低得多。

連接器使用系統`openssl`庫提供的預設證書。 通常由Debian上的`/etc/ssl/certs`目錄提供。 預設情況下，此目錄由「ca-certificates」包提供，但可自定義。

### 每種PDU中的資訊 {#information-pdu}

每種PDU都有不同的欄位，承載不同的資訊。 [SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)中詳細介紹了這些PDU。

以下各節將介紹PDU及其同步響應(`*_RESP PDU`)。 所有PDU都必須通過相應的`RESP`進行確認，這是規範的強制部分。

PDU可以有可選欄位。 此處僅說明最常見的欄位。 有關詳細資訊，請參閱[SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

#### BIND_TRANSMITTER/BIND_RECEIVER/BIND_TURNESSIVE {#bind-transmitter}

此PDU用於啟動與SMSC的連接。 **發送器**、接 **** 收器 **** 和收發模式只更改允許通過此連接傳輸的簡訊類型，具體是：

| 模式 | 允許的簡訊種類 |
|:-:|:-:|
| 傳送器 | MT |
| 接收器 | MO + SR |
| 收發器 | MT + MO + SR |

`BIND_* PDU`中的顯著欄位：

* **system_id**:用於驗證的登錄。在外部帳戶中設定。

* **密碼**:用於驗證的密碼。在外部帳戶中設定。

* **system_type**:需要為某些提供者以特定值設定。在外部帳戶中設定，可在所有版本中使用。 通常會區分不同類型的合約、管道、國家等。

* **addr_** tonand  **addr_npi**:某些提供者所需。由外部帳戶中的`Bind TON`和`Bind NPI`設定設定。

* **address_range**:某些提供者所需。大多數情況下，這是此連接上允許的快捷方式代碼清單。 在外部帳戶中設定。

`BIND_*_RESP` 沒有特定欄位，則會確認連線是否成功。

#### 取消綁定 {#unbind}

在斷開連接之前，必須由系統發送此PDU。 它必須等待匹配的`UNBIND_RESP PDU`才能關閉連接。

符合SMSC的TCP連接不能關閉，而是由Adobe Campaign連接器控制。

#### SUBMIT_SM {#submit-sm}

此PDU向SMSC發送MT。 其響應PDU提供MT的ID。

`SUBMIT_SM PDU`中的顯著欄位：

* **service_type**:需要。在傳送屬性中設定。

* **source_addr_** ton和 **source_addr_npi**:指示傳輸的源地址類型。這些欄位的意義是標準化的，但由於某些提供者使用方式不同，因此您應要求提供者提供其正確值。 在外部帳戶中設定。

* **source_addr**:MT的源地址/oADC。會顯示在行動電話上。 在外部帳戶和傳送中設定，傳送中的值優先於外部帳戶的值。

* **dest_addr_** ton和 **dest_addr_npi**:指示傳輸的目的地址類型（例如本地或國際格式）。這些欄位的意義是標準化的，但由於某些提供者使用方式不同，因此您應要求提供者提供其正確值。 在外部帳戶中設定。

* **destination_addr**:收件者地址、電話號碼或MSISDN。

* **esm_class**:用於判斷文字欄位中是否使用UDH。如果未使用`message_payload`模式，則連接器會自動啟用分割SMS。

* **priority_flag**:此消息的優先順序高於其他消息。這會與傳送本身的優先順序系結。

* **validity_period**:不應嘗試重試的時間戳記。在傳送本身中設定。

* **registered_delivery**:指示是否請求SR。Adobe Campaign一律會設定此標幟，但自動回覆除外。 對於多部分消息，只為第一部分設定標誌。 所有版本都有相同的行為。

* **data_coding**:指示文本欄位中使用的編碼。如需詳細資訊，請參閱[SMS文字編碼](../../administration/using/sms-protocol.md#sms-text-encoding)區段。

* **short_message**:訊息的文字。若已使用UDH，則也會包含UHD標頭。

Adobe Campaign支援下列選用欄位：

* **dest_addr_subut**:用於指定簡訊的目標：快閃記憶體、行動或SIM卡。在傳送屬性中設定。

* **message_payload**:當在外部帳戶中啟用時，長消息將在單個PDU中發送，而文本將在此欄位而不是欄位中 `short_message` 傳輸。

#### SUBMIT_SM_RESP {#submit-sm-resp}

此PDU將包含MT的ID。 這對於與傳入的SR匹配很有用。

>[!IMPORTANT]
>
>許多提供程式以十六進位傳輸MT ID。 請務必在MT確認&#x200B;**中正確設定外部帳戶中的** ID格式。

某些提供程式在發送SR後發送`SUBMIT_SM_RESP`。 為了解該行為，Adobe Campaign會等待30秒，然後回覆&#x200B;**無效訊息ID**&#x200B;至ID未知的SR。

#### DELIVER_SM {#delivery-sm}

此PDU由SMSC發送到Adobe Campaign。 它包含MO或SR。

大多數欄位的含義與其`SUBMIT_SM`對應項相同。 以下是實用欄位的清單：

* **source_addr**:MO/SR的源地址。這通常是電話號碼。

* **destination_addr**:接收MO或SR的簡碼。

* **esm_class**:用來判斷PDU是MO還是SR。

* **short_message**:訊息的文字。對於SR，這包含SMPP協定規範附錄B中描述的資料。 有關詳細資訊，請參見[SR錯誤管理](../../administration/using/sms-protocol.md#sr-error-management)。

Adobe Campaign可透過一些設定調整，讀取`receipted_message_id`選用欄位中的訊息ID。

#### DELIVER_SM_RESP {#deliver-sm-resp}

此PDU由Adobe Campaign發送，以確認SR和MO。

Adobe Campaign Standard只會在所有處理步驟均成功後傳送`DELIVER_SM_RESP`。 這保證在仍有處理錯誤的風險時，不會確認任何SR或MO。

#### INQUIRE_LINK {#enquire-links}

此PDU僅用於檢查連接是否處於運行狀態。 其頻率應根據提供商的需要設定。

預設的60秒應符合外部帳戶中設定的大部分設定。

#### INQUIRE_LINK_RESP {#enquire-links-resp}

此PDU確認連接處於活動狀態。

### 多部分簡訊（長簡訊） {#multipart}

多部分簡訊（或長簡訊）是以多個部分傳送的簡訊。 由於行動網路通訊協定的技術限制，SMS不能超過140個位元組，否則需要分割。 請參閱[SMS文字編碼](../../administration/using/sms-protocol.md#sms-text-encoding)區段，進一步了解SMS中可容納的字元數。

長訊息的每個部分都是個別的簡訊。 這些部件在網路上獨立運行，並由接收行動電話組裝。 為了處理重試次數和連線問題，Adobe Campaign會以反向順序傳送這些部分，並僅在訊息的第一部分（上次傳送的部分）上要求SR。 由於行動電話只會在收到其第一部分時顯示訊息，因此其他部分的重試不會在行動電話上產生重複項目。

使用&#x200B;**傳送範本**&#x200B;中的&#x200B;**每則訊息的最大SMS數**&#x200B;設定，可設定每則傳送的最大SMS數。 傳送時，超過此限制的訊息會失敗，因為SMS失敗原因太長。

有2種方式可傳送長SMS:

* **UDH**:傳送長訊息的預設和建議方式。在此模式中，連接器會將訊息分割成多個`SUBMIT_SM PDU`s，其中包含UDH資訊。 這個協定是手機自己使用的。 這表示Adobe Campaign對訊息產生的控制力最強，因此可精確計算已傳送的部件數及分割方式。

* **message_payload**:以單一方式傳送完整長訊息的方 `SUBMIT_SM PDU`式。提供者必須將其分割，這表示Adobe Campaign無法確切知道已傳送多少部件。 有些提供者需要此模式，但我們建議您僅在不支援UDH時才使用此模式。

有關協定和格式的詳細資訊，請參閱[SUBMIT_SM PDU](../../administration/using/sms-protocol.md#information-pdu)的`esm_class`、`short_message`和`message_payload`欄位的說明。

### 吞吐量上限和窗口 {#throughput-capping}

大多數提供程式要求每個SMPP連接的吞吐量限制。 這可透過在外部帳戶中設定數個簡訊來達成。 請注意，每個連接都會發生吞吐量限制，有效總吞吐量是每個連接的限制乘以連接總數。 這在[同時連線](../../administration/using/sms-protocol.md#connection-settings)一節中有詳細說明。

要達到最大的吞吐量，您需要微調最大發送窗口。 發送窗口是可以在不等待`SUBMIT_SM_RESP`的情況下發送的`SUBMIT_SM PDU`數。 如需詳細資訊，請參閱[傳送視窗設定](../../administration/using/sms-protocol.md#throughput-timeouts)區段。

### SR和錯誤管理（「附錄B」） {#sr-error-management}

SMPP協定定義`RESP PDU`s中的標準同步錯誤，但不定義SR的錯誤代碼。 每個提供者都使用各自的錯誤碼及其含義。

建議在[SMPP協定規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)的附錄B部分（第167頁）中提出，但不列出實際錯誤代碼及其含義。

為了適應錯誤管理，已利用Adobe Campaign的broadlog訊息系統來正確布建錯誤及其嚴重性（硬式、軟式等）。

如上所述，存在兩種不同的錯誤：

* 在`SUBMIT_SM_RESP`中發送消息後立即發生的同步回復
* 在行動裝置收到訊息或訊息逾時時，可能會很晚傳回的收據。 在這種情況下，在SR中找到錯誤。

收到SR時，其`short_message`欄位（附錄B符合實施範例）中可找到狀態和錯誤。 PDU的`short_message`欄位通常稱為&#x200B;**文本欄位**，因為它包含MT中的文本。 如果是SR，則它包含技術資訊以及名為&#x200B;**Text**&#x200B;的子欄位。 這2個欄位不同，`short_message`實際包含&#x200B;**Text**&#x200B;欄位和其他資訊。

#### SR文本欄位格式 {#sr-text-field-format}

規範建議在SR文本欄位中使用此格式。 它是子欄位的清單，以冒號分隔，以分隔欄位名稱及其值。 欄位名稱不區分大小寫。

符合附錄B建議的SR文字欄位範例：

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

id欄位是`SUBMIT_SM_RESP PDU`中收到的ID，即MT的確認。

`sub` 和 `dlvrd` 應該計算已傳送的部件和已傳送訊息的數量，但Adobe Campaign沒有使用，因為broadlog系統提供更好、更整合的資訊。

`submit date` 和 `done date` 欄位是MT傳送時間和行動裝置傳送SR的時間的指示性時間戳記。由於日期設定不正確，行動裝置所提供的時區甚至時間戳記可能錯誤，這可能會造成一些問題。

stat欄位很重要，因為它會告訴訊息的狀態。 唯一重要的狀態是`DELIVRD`、`UNDELIV`和`REJECTD`。 `DELIVRD`狀態表示成功，其他兩個表示錯誤。 其他值可能存在，但通常是中間通知，例如MT到達行動電信業者，但不到行動電話。 Adobe Campaign會忽略這些中繼通知。

錯誤欄位包含提供者專屬的錯誤碼。 提供者必須提供可能的錯誤碼表及其含義，才能解譯此值。

最後，文本欄位通常包含MT文本的開頭。 Adobe Campaign會忽略這一點，有些提供者不會傳送它，以避免PII洩漏和網路頻寬耗用。 在故障排除期間，可通過讀取此欄位，更輕鬆地發現與測試MT匹配的SR。

### Adobe Campaign Standard延伸通用SMPP中的SR處理範例 {#sr-processing}

此範例顯示遵循附錄B建議、外部帳戶的預設值和成功的SMS MT實作的案例。

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

首先，會套用`id extraction`規則運算式來擷取ID，並與對應的MT調解。

接著，會套用`status extraction` regex和`error code extraction` regex來擷取這些欄位，並附加至字串。

broadlog訊息是使用此資訊所建構，並附加原始未更改的字串以供參考：

```
SR ExampleProvider DELIVRD 000|MESSAGE=id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

然後對消息進行標準化，刪除MESSAGE部分，以便能夠匹配具有相同的狀態代碼和錯誤代碼的多個消息。

```
SR ExampleProvider DELIVRD 000|#MESSAGE#
```

如果廣播消息表中尚未布建消息，則將建立新條目，使用作為&#x200B;**firstText**&#x200B;的整條消息以及標準化消息。 接著，連接器會使用success和`error`規則運算式來判斷其是否成功：

* 如果符合`success`規則運算式，則會視為成功。

* 如果符合`error`規則運算式，則訊息會限定為錯誤。

* 如果這兩個規則運算式均不相符，則會忽略SR。 這可能是中繼通知，但Adobe Campaign未處理。

依預設，所有錯誤都會布建為軟錯誤。 這表示必須手動布建硬錯誤。

### SMS文字編碼 {#sms-text-encoding}

若發生編碼問題，您應&#x200B;**一律聯絡SMSC提供者**。 只有SMSC提供者才確切了解其支援的編碼，以及可能因其技術平台限制而適用的特殊規則。

SMS訊息使用特殊的7位元編碼，通常稱為GSM7編碼。

在SMPP通訊協定中，GSM7文字將擴充至每字元8位元，以便疑難排解。 SMSC會先將其封裝為每字元7位元，再傳送至行動裝置。 這表示SMS的`short_message`欄位在SMPP幀中長度最多可達160個位元組，而在移動網路上發送時限制為140個位元組。

若有編碼問題，請檢查下列重要事項：

* 請確定您知道哪些字元屬於哪個編碼。 GSM7不完全支援差分標籤（重音）。 特別是在法語中，在法語中，é和è是GSM7的一部分，但ê, — 或ï不是。 西班牙語也是如此。

* C帶有Cedilla(ç)的字元僅在GSM7字母的大寫中存在，但有些手機會以小寫或「智慧」大小寫呈現。 一般建議是完全避免，並移除嘶音號或切換至UCS-2。

* **除非SMSC提供者明確** 要求，否則請勿在SMS中使用ASCII。此編碼會浪費空間，因為其8位元字元且覆蓋率小於GSM7。 在北美使用的CDMA網路可能需要此編碼。

* Latin-1並不總是受支援。 嘗試使用Latin-1之前，請檢查與SMSC提供程式的相容性。

* Adobe Campaign連接器不支援國家語言班次表。 您必須改用UCS-2或其他`data_coding`。

* UCS-2和UTF-16通常由手機混合。 這是使用UCS-2中不存在的表情符號和其他字元時的問題。

* 大多數手機沒有所有UCS-2字元的字型字型。 智慧手機往往能夠顯示稀有字元，但功能手機通常對那些在他們購買的國家的母語中有用的功能的支援有限。 如果您想使用表情符號或ASCII-art，請先在各種手機上測試，再發送。 Adobe Campaign預覽不會模擬遺失的字元，且會顯示網頁瀏覽器上可用的符號。

`data_coding`欄位會告訴您使用的編碼。 一個主要問題是，值0表示規範中的預設SMSC編碼，通常指GSM7。 請洽詢與`data_coding` = 0相關聯且Adobe Campaign僅支援的SMSC合作夥伴。 其他`data_coding`值通常遵循規範，但唯一可靠的方式是向SMSC提供者確認。

訊息的最大大小取決於其編碼。 下表匯總了所有相關資訊：

| 編碼 | 常用data_coding | 訊息大小（字元） | 多部分SMS的部件大小 | 可用字元 |
|:-:|:-:|:-:|:-:|:-:|
| GSM7 | 0 | 160 | 152 | GSM7基本字元集+擴充功能（延伸字元需2個字元） |
| 拉丁文–1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 <br>UTF-16 | 8 | 70 | 67 | Unicode（因電話而異） |

## SMPP外部帳戶參數 {#SMPP-parameters-external}

SMPP協定的每個實現都有許多變化。 為了改善相容性和適應性，可使用許多設定來更改SMPP連接器的行為。 本節介紹每個參數及其對連接器的影響。

### 一般參數和路由 {#general-parameters-routing}

**限制此帳戶的MTA例項**

可以設定允許連接到SMPP提供程式的MTA實例數的限制。 若勾選此選項，您最多可以指定使用多少個MTA。

此選項允許更精細地控制連接數，請參閱[同時連接](../../administration/using/sms-protocol.md#connection-settings)。

如果您設定的值高於執行中的MTA數，則所有MTA都會正常執行：此選項僅為限制，無法產生其他MTA。

如果您需要精確控制連線數量（例如提供者需求），建議您一律設定此選項，即使目前部署的MTA數量正確，亦然。 如果之後新增其他MTA，則仍會接受連線限制。

### 連線設定 {#connection-settings}

#### SMPP連接模式 {#smpp-connection-mode}

在&#x200B;**收發器**&#x200B;模式或在分離的&#x200B;**發射器+接收器**&#x200B;模式中設定連接。 當切換到分離的&#x200B;**發射機+接收機**&#x200B;模式時，**SMPP連接模式**&#x200B;部分中的設定將應用於發射機，而&#x200B;**接收機連接設定**&#x200B;部分中的設定將應用於接收機連接，只有在您選中了&#x200B;**為接收機**&#x200B;使用不同的參數複選框時。

#### SMSC實作名稱 {#smsc-implementation-name}

設定SMSC實施的名稱。 應將其設為提供者的名稱。 請聯絡管理員或傳遞團隊，了解要在此欄位中新增哪些項目。 [SR錯誤管理](../../administration/using/sms-protocol.md#sr-error-management)部分中描述了此欄位的角色。

#### 伺服器 {#server}

要連接的伺服器的DNS名稱或IP地址。

#### 埠 {#port}

要連接的TCP埠。

#### 帳戶 {#account}

連線的登入。 在BIND PDU的`system_id`欄位中傳遞。

#### 密碼 {#password}

SMPP連接的密碼。 在BIND PDU的口令欄位中傳遞。

#### 系統類型 {#system-type}

在BIND PDU的`system_id`欄位中傳遞的值。 有些提供者需要此處的特定值。

#### 同時連接 {#simultaneous-connections}

在Adobe Campaign Standard中，它定義每個SMS執行緒和每個MTA程式的連線數。
MTA進程的數量由部署決定：通常有2個MTA和1個執行緒。 在config-instance.xml檔案中，可使用smppConnectorThreads設定更改線程數。 通常每個容器有1個MTA流程，每個MTA流程有1個線程。

Adobe Campaign Standard的連線總數公式：

* **連線總數=同時連線數*執行緒數* MTA數**

在外部帳戶中設定同時連線，在config-instance.xml檔案(smppConnectorThreads)中設定執行緒數，且可在外部帳戶中限制MTA數。

在分離的&#x200B;**發射機/接收機**&#x200B;模式中，以上連接數表示&#x200B;**發射機/接收機**&#x200B;對的數量，這表示總的連接數將是兩倍。

#### 透過SMPP啟用TLS {#enable-TLS}

使用TLS連線至提供者。 連線會加密。 TLS連線由OpenSSL程式庫管理，任何適用於OpenSSL的項目，此連線都會成立。

#### 在日誌檔案中啟用詳細SMPP跟蹤 {#enable-verbose-log-file}

此設定會將所有SMPP流量轉儲到日誌檔案中。 在初始設定期間，通常需要調整參數。 在疑難排解連接器時，必須啟用此功能，並與提供者所看到的流量進行比較。

### 接收器連接設定 {#receiver-connection}

此區段只會以分隔&#x200B;**傳送器+接收器**&#x200B;模式顯示。

#### 對接收器使用不同的參數 {#receiver-parameters}

取消核取方塊時，傳送器和接收器會使用相同的設定。

核取方塊後，**連線設定**&#x200B;區段中的設定將套用至傳送器，而&#x200B;**接收器連線**&#x200B;設定中的設定將套用至接收器。

**接收伺服器，埠，帳戶，密碼，系統類型**

在&#x200B;**trinsmitter+receiver**&#x200B;模式下，這些設定適用於接收器。 如需詳細資訊，請參閱上方的傳送器部分。

### SMPP通道設定 {#smpp-channel-settings}

#### 允許字母音譯 {#allow-character-transliteration}

音譯是尋找相等字元與遺失字元的程式。 例如，GSM編碼中缺少法文&quot;ê&quot;（e含抑揚符號）字元，但可以以&quot;e&quot;取代，不會影響可讀性。

取消勾選此方塊時，如果文字編碼無法如實編碼字串，則會失敗。

核取此方塊時，文字編碼會嘗試將字串轉換為近似版本，而非失敗。 如果某些字元在目標編碼中沒有相同的字元，則文字編碼將會失敗。

如需編碼程式的更一般說明，請參閱[定義編碼設定的特定對應](../../administration/using/sms-protocol.md#SMSC-specifics) 。

#### 將傳入的MO儲存在資料庫中 {#incoming-mo-storing}

啟用後，傳入的MO將儲存在資料庫的inSMS表中。 可以使用任何工作流的查詢活動查詢此表。

#### 在SR處理期間啟用即時KPI更新 {#real-time-kpi}

啟用後，當收到錯誤SR時，主要傳送頁面上的KPI將即時更新。

缺點可能是效能低，因為它會產生資料庫爭用。 如果禁用，則統計資訊將由&#x200B;**syncfromexec**&#x200B;工作流更新，每20分鐘運行一次。

#### 來源編號 {#source-number}

定義消息的預設源地址。 此設定僅適用於傳送中的來源號碼為空的情況。

預設情況下，不會傳遞原始碼欄位，因此提供者會用它取代簡短代碼。

這會啟用寄件者地址/oADC覆寫功能。

#### 簡碼 {#short-code}

指出帳戶的主要簡碼。 如果此帳戶使用了多個短代碼，或者短代碼未知，請將此欄位留空。

指定短程式碼有助於兩項功能：

* 如果未提供原始碼，預覽將顯示簡短代碼。 它將反映手機上的真實行為。

* 自動回覆功能的封鎖清單設定只會傳送來隔離使用者特定簡短代碼。

#### 源噸/NPI，目的地噸/NPI {#ton-npi}

[SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第117頁）的第5.2.5節中描述了TON（編號類型）和NPI（編號計畫指示器）。 這些值應設為提供者的需求。

它們在`SUBMIT_SM PDU`、`source_addr_npi`、`dest_addr_ton`和`dest_addr_npi`欄位中按原樣傳輸。`source_addr_ton`

#### 服務類型 {#service-type}

此欄位在`SUBMIT_SM PDU`的`service_type`欄位中按原樣傳輸。 將此設定為提供程式的需求。

### 吞吐量和逾時 {#throughput-timeouts}

這些設定可控制SMPP通道的所有計時方面。 某些提供程式需要非常精確地控制消息速率、窗口和重試計時。 這些設定應設定為符合提供者的容量及其合約中指出條件的值。

#### 傳送視窗 {#sending-window}

該窗口是可以在不等待匹配`SUBMIT_SM_RESP`的情況下發送的`SUBMIT_SM PDU`數。

最大窗口為4的傳輸示例：

![](assets/do-not-localize/sms_protocol_2.png)

當網路鏈路的延遲很高時，窗口有助於提高吞吐量。  窗口的值必須至少是SMS/s數乘以連結的延遲（以秒為單位），這樣連接器在發送下一條消息之前就不會等待`SUBMIT_SM_RESP`。
如果窗口太大，您可能會在出現連接問題時發送更多重複郵件。 此外，大多數提供者對窗口有非常嚴格的限制，拒絕超出限制的報文。

如何計算最佳傳送視窗公式：

* 測量`SUBMIT_SM`和`SUBMIT_SM_RESP`之間的最大延遲。

* 將此值（以秒為單位）乘以最大MT吞吐量。 這可提供最佳的傳送視窗值。

範例：如果您在最大MT吞吐量中設定了300個SMS/s，且平均在`SUBMIT_SM`和`SUBMIT_SM_RESP`之間有100毫秒的延遲，則最佳值為`300×0.1 = 30`。

#### 最大MT吞吐量 {#max-mt-throughput}

每秒和每個連接的最大MT數。 此設定會嚴格強制執行，MTA永遠不會以超過此限制的速度推送訊息。 它對於需要精確調節的提供商非常有用。

要了解總吞吐量限制，請將此數乘以上述公式中詳述的連接總數。

0表示沒有限制，MTA會盡快傳送MT。

一般建議將此設定保持在1000以下，因為除非在最終體系結構上進行適當基準，否則無法保證精確的吞吐量高於此數字。 如果您需要的吞吐量超過1000，請與您的提供商聯繫。 將連接數量增加到1000 MT/s以上可能更好。

#### 重新連接前的時間 {#time-reconnection}

當TCP連接丟失時，連接器將等待此秒數再嘗試建立連接。

#### MT的到期期 {#expiration-period}

`SUBMIT_SM`與其相符`SUBMIT_SM_RESP`之間的逾時。 如果未按時收到`RESP`，則消息將被視為失敗，並且將應用MTA的全局重試策略。

#### 系結逾時 {#bind-timeout}

TCP連接嘗試與`BIND_*_RESP`回復之間的超時。 逾時時，Adobe Campaign連接器會關閉連線，且會等待「時間」再重新連線，然後再次嘗試。

#### inquire_link期間 {#enquire-link-period}

`enquire_link` 是發送的一種特殊類型的PDU，用於保持連接正常。此時段以秒為單位。 當連線閒置時，促銷活動連接器只會傳送`enquire_link`以節省頻寬。 如果在此期間後兩次未接收到RESP，則連接將被視為死，並將觸發重新連接進程。

### SMSC 細節 {#SMSC-specifics}

這些設定是進階設定，可讓Adobe Campaign連接器符合大部分SMPP實作特性。

#### 定義編碼的特定對應 {#encoding-specific-mapping}

有關文本編碼的詳細資訊，請參閱[SMS文本編碼](../../administration/using/sms-protocol.md#sms-text-encoding)部分。

此設定可讓您定義自訂編碼對應，與規格不同。 您將能宣告編碼清單及其`data_coding`值。

MTA會嘗試使用清單中的第一個編碼進行編碼。 如果失敗，會嘗試使用清單上的下一個編碼，以此類推。 如果無法使用任何編碼來編碼訊息，則會發生錯誤。 找到編碼後，MTA將使用編碼文本和使用表中指定的值設定的`data_coding`欄位建立`SUBMIT_SM PDU`。

表格中的項目順序很重要：編碼會從上到下嘗試。 您應將最便宜或最建議的編碼放在清單的頂端，然後再加上越來越昂貴的編碼。

請注意，UCS-2不會失敗，因為它可以編碼Adobe Campaign中支援的所有字元，而UCS-2 SMS的最大長度要小得多：僅70個字元。

您也可以使用此設定，在對應表格中僅聲明1行，以強制一律使用特定編碼。

未勾選核取方塊時使用的預設對應等同於下表：

| data_coding | 編碼 |
|---|---|
| 0 | GSM |
| 9 | UCS-2 |

這表示MTA將嘗試在GSM中將訊息編碼。 如果成功，則會將`data_coding`設為0傳送。

如果訊息無法在GSM中編碼，則會在UCS-2中編碼，並將`data_coding`設為8。

#### 啟用message_payload {#enable-message-payload}

取消勾選後，長SMS將會被MTA分割，並透過UDH傳入多個`SUBMIT_SM PDU`s。 在UDH資料之後，手機將重新合成該消息。

選中後，將在一個SUBMIT_SM PDU中發送長簡訊，將文本放入message_payload可選欄位中。 有關詳細資訊，請參閱[SMPP規範](../../administration/using/sms-protocol.md#ACS-SMPP-connector)。

如果已啟用此功能，Adobe Campaign將無法個別計算SMS部件：所有訊息都會計為在一個部分中傳送。

#### 發送完整電話號碼 {#send-full-phone-number}

未選中此複選框時，只會將電話號碼的數字發送到提供程式（`SUBMIT_SM`欄位的`destination_addr`欄位）。 這是預設行為，因為國際數字指示器（通常為+前置詞）在SMPP中被TON和NPI欄位取代。

核取核取方塊時，電話號碼會照原樣傳送，不含前置處理和潛在空格、+前置詞或井字/雜湊/星號。

此功能也會影響自動回覆封鎖清單功能的行為：未勾選核取方塊時，將在插入隔離表的電話號碼中新增+前置詞，以補償SMPP通訊協定本身從電話號碼中移除的+前置詞。

#### 略過TLS證書檢查 {#skip-tls}

啟用TLS時，請略過所有憑證檢查。

若勾選此選項，連線將不再安全，生產環境將不再啟用。

它可用於偵錯或測試用途。

#### 綁定TON/NPI {#bind-ton-npi}

[SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)第5.2.5節中描述的TON（編號類型）和NPI（編號計畫指示器）（第117頁）。 這些值應設為提供者需要的任何值。

它們在BIND PDU的`addr_ton`和`addr_npi`欄位中按原樣傳輸。

#### 地址範圍 {#address-range}

在BIND PDU的address_range欄位中按原樣發送。 此值應設為提供者需要的任何值。

#### ID確認計數無效 {#invalid-id}

限制可針對單個SR發送的&#x200B;**消息ID invalid** `DELIVER_SM_RESP`的數量。

**這應僅用於疑難排解作為工** 作區的用途，並在正常情況下設為0。

Fox範例，若設為2:

* 提供程式發送ID為「1234」的SR(`DELIVER_SM`)。

* 在資料庫中找不到ID「1234」。

* 連接器會計為該ID的1 **無效ID**&#x200B;錯誤，因此會以「訊息ID無效」錯誤碼（正常行為）傳送`DELIVER_SM_RESP`。

* 提供程式會重試ID為「1234」的相同SR。

* 在資料庫中仍找不到ID「1234」。

* 連接器會計為該ID的2 **無效ID**&#x200B;錯誤，因此會傳送`DELIVER_SM_RESP` &quot;OK&quot;，即使未正確處理亦然。

* 當無效的SR塊合法且無法處理消息時，此功能的用意是刷新提供程式端的SR緩衝區。

將此欄位設定為0會禁用始終返回&#x200B;**消息ID無效**&#x200B;的機制，這是正常行為。

將此欄位設為1會讓連接器一律回應「OK」，即使ID無效亦然。 只有在監管、故障排除和最小時間（例如從提供方問題中恢復）的情況下，此值才應設定為1。

#### 擷取SR中ID的規則運算式 {#regex-extraction}

SMPP協定規範未嚴格強制執行SR格式。 這只是說明書[附錄B](../../administration/using/sms-protocol.md#sr-error-management)（第167頁）中描述的建議。 某些SMPP實作者為此欄位的格式不同，因此Adobe Campaign需要一種方式來擷取正確欄位。

依預設，它會在`id:`後擷取最多10個英數字元。

規則運算式必須只有一個擷取群組，且其中包含括在括弧內的部分。 括弧必須圍住ID部分。 規則運算式格式為PCRE。

調整此設定時，請務必納入盡可能多的內容，以避免觸發錯誤。 如果標準中有特定字首，例如`id:`，請在規則運算式中加入這些字首。 請盡量使用單詞分隔符(\b)，以避免捕獲單詞中間的文本。

規則運算式中未包含足夠的內容可能會造成小型安全性缺陷：SR中可包含該消息的實際內容。 如果您只比對沒有上下文的特定ID格式（例如UUID），則可能會剖析實際的文字內容，例如內嵌在文字欄位中的UUID，而非ID。

#### 套用Regex以判斷成功/錯誤狀態 {#regex-applied}

遇到具有未知stat/err欄位組合的消息時，這些規則運算式將應用於stat欄位，以確定SR是成功還是錯誤。 SR的統計值與任何這些規則不匹配，則會被忽略。

預設情況下，以`DELIV`開頭的統計值，例如[附錄B](../../administration/using/sms-protocol.md#sr-error-management)中的`DELIVRD`將被視為已成功傳送，且所有符合錯誤的統計值，例如`REJECTED`、`UNDELIV`被視為錯誤。

#### MT確認中的ID格式 {#id-format-mt}

這表示在`SUBMIT_SM_RESP PDU`的`message_id`欄位中傳回的ID格式。

* **請勿修改**:ID會以ASCII編碼文字的形式儲存在資料庫中。不會進行預處理或篩選。

* **小數位數**:ID應為ASCII格式的小數數。使用此設定時，前導和尾隨空格以及前導零將被移除。

* **十六進位數**:ID應為十六進位數，以ASCII形式表示，前導不為0x或尾端為h。然後，ID會轉換為十進位數字，再儲存在資料庫中。

* **十六進位字串**:ID應為ASCII編碼的文本，其本身是以十六進位編碼的位元組字串。例如，在PDU中，您會找到`0x34 0x31 0x34 0x32 0x34 0x33`，它將轉換為ASCII &quot;414243&quot;。 然後，將此字串解碼為十六進位位元組字串，您將獲得&quot;ABC&quot;，結果：您會將ID「ABC」儲存在資料庫中。

#### SR中的ID格式 {#id-format-sr}

這表示SR中ID的`Extraction`規則運算式所擷取的ID格式。 值具有與上述MT格式相同的含義和行為。

**可選欄位中的SR ID或錯誤代碼**

若勾選此選項，選用欄位的內容將附加至上述規則處理的文字。 文字的格式為`0xTAG:VALUE`, `0xTAG`為標籤的4位數十六進位值，大小寫如下。`0x002E`。

例如，您可能想在`receipted_message_id`欄位中擷取ID。 為此，請啟用此核取方塊，並將下列文字新增至狀態：

```
0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739
```

在此範例中，0x001E是選用欄位的標籤，UUID是欄位的值。

若要擷取此值，您現在可以在SR欄位中ID的Extraction regex中設定下列regex:

```
\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b
```

>[!IMPORTANT]
>
>您只能擷取具有文字(ASCII/UTF-8)值的選用欄位。 具體來說，目前的規則運算式系統無法可靠地擷取二進位欄位。

**文字欄位中的SR ID或錯誤代碼**

如果選中，則在處理SR的狀態文本期間將保留&#x200B;**Text**&#x200B;欄位。

如果提供者在此欄位中放入重要資料（例如ID或狀態），這個功能就很實用。 此欄位通常可安全地捨棄，因為其中可能包含具有非ASCII編碼的文字，並中斷規則運算式處理。

如果SR欄位中ID的`Extraction`規則運算式不夠具體，則啟用此選項可能會引入非常小的安全漏洞。 **Text**&#x200B;欄位的內容可被解析為ID，攻擊者可使用該ID插入偽造的ID，這可能導致部分拒絕服務情況。

**服務ID標籤**

允許新增自訂TLV。 此欄位會設定標籤部分。 值可在&#x200B;**服務中，或在傳送的進階參數中的程式ID**&#x200B;值中，針對傳送自訂。

此設定僅允許為每個訊息新增一個TLV選項。

>[!NOTE]
>
>自21.1版開始，現在可以新增多個選用參數。 如需詳細資訊，請參閱本[區段](../../administration/using/sms-protocol.md#automatic-reply-tlv)。

### 自動回覆傳送至 MO {#automatic-reply}

此功能可讓您快速回覆文字給MO，並處理傳送至封鎖清單的每短代碼。

**關鍵字**&#x200B;和&#x200B;**簡碼**&#x200B;欄定義了觸發自動回覆的條件。 如果兩個欄位都相符，則會傳送MO並觸發其他動作。 若要指定萬用字元，您應將欄位留空。 關鍵字比對MO文字中的第一個英數字元字詞，忽略標點符號和前導空格。 這表示&#x200B;**Keyword**&#x200B;欄位不能包含空格，且必須是單一字詞。

**Keyword**&#x200B;設定是前置詞。 例如，如果您指定&quot;AD&quot;，則會比對&quot;AD&quot;、&quot;ADAP&quot;和&quot;ADOBE&quot;。 如果您有多個具有共同首碼的關鍵字，則需要注意順序，因為關鍵字會從上到下處理。

**Reply**&#x200B;欄是要回覆的文字。 此欄位中沒有可用的個人化。 如果將此欄位留空，系統不會回覆任何訊息，但仍會觸發其他動作。

當&#x200B;**Additional action**&#x200B;列&#x200B;**Keyword**&#x200B;和&#x200B;**Short code**&#x200B;匹配時，Additional action列提供了額外的操作，空的short code匹配所有的short code。 您可以傳送至隔離區或從隔離區中移除，且值不會回覆文字。 如果您指定&#x200B;**其他動作**，但將&#x200B;**回覆**&#x200B;欄位留空，則會執行動作，但不會傳送回覆。 隔離區僅對指定的短代碼應用；如果欄位為空，則對所有短代碼應用。

>[!IMPORTANT]
>
>發送完整電話號碼設定會影響自動回復隔離機制的行為：如果未檢查發送完整電話號碼，則放入隔離區的電話號碼將加上加號(「+」)，以使其與國際電話號碼格式相容。

表格中的所有項目都會以指定的順序處理，直到有一個規則符合為止。 如果多個規則符合MO，則只會套用最頂端的規則。

### 自動回覆選用參數(TLV) {#automatic-reply-tlv}

自21.1版起，您可以新增選用參數以自動回覆MT。 如[SMPP規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第131頁）第5.3節所述，將它們作為可選TLV參數添加到答復的`SUBMIT_SM PDU`中。

有關可選參數的詳細資訊，請參閱此[節](../../administration/using/sms-protocol.md#smpp-optional-parameters)。

## SMS傳遞範本參數 {#sms-delivery-template-parameters}

某些參數可依傳送範本設定。

### 從欄位 {#from-field}

此欄位為選填欄位。 它允許覆寫寄件者地址(oADC)。 此欄位的內容放置在`SUBMIT_SM PDU`的`source_addr`欄位中。

根據SMPP規範，欄位限制為21個字元，但某些提供者可能允許較長的值。 另請注意，有些國家/地區可能會套用非常嚴格的限制，例如長度、內容、允許的字元。

### 傳送參數 {#delivery-parameters}

#### 每條訊息的最大簡訊數 {#maximum-sms}

此設定僅在&#x200B;**消息裝載**&#x200B;設定被禁用時有效。 有關詳細資訊，請參閱此[page](../../administration/using/configuring-sms-channel.md)。 如果訊息需要的SMS超過此值，則會觸發錯誤。

簡訊通訊協定將簡訊限制為255個部分，但有些行動電話無法將長訊息與10多個部分組合在一起，這個限制取決於確切的型號。 我們建議您不要在每封郵件中超過5個部分。

由於個人化訊息在Adobe Campaign中的運作方式，訊息的大小可能會有所不同。 擁有大量長報文可能會增加發送成本。

#### 傳輸模式 {#transmission-mode}

此欄位指出您要傳輸的簡訊類型：普通或快閃資訊，儲存在行動或SIM卡上。

此設定在`SUBMIT_SM PDU`的`dest_addr_subunit`選填欄位中傳送。

* **** 未指定不發送PDU中的可選欄位。

* **** Flash會將值設為1。它會傳送快閃記憶體訊息，該訊息會彈出行動裝置，且不會儲存於記憶體中。

* **** 標準化將值設為0。它會傳送正常訊息。

* **儲存** 行動裝置時，值會設為2。它告訴手機將簡訊儲存在內部記憶體中。

* **「終止時** 保存」將值設定為3。它告訴手機將簡訊儲存在SIM卡中。

#### 有效期 {#validity-period}

有效期在`SUBMIT_SM PDU`的`validity_period`欄位中傳送。 日期的格式一律為絕對UTC時間格式（日期欄位的結尾為「00+」）。

#### SMPP可選參數(TLV) {#smpp-optional-parameters}

自21.1版起，您可以為此傳送的每個MT新增多個選用參數。 這些可選參數被添加到回復的`SUBMIT_SM PDU`中，如[SMPP規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第131頁）的5.3節所述。

表格中的每一列代表選用參數：

* **參數**:參數的說明。未傳送給提供者。
* **標籤Id**:選用參數的標籤。必須是有效的十六進位，格式為0x1234。 無效的值將導致傳送準備錯誤。
* **值**:選填欄位的值。編碼為UTF-8，當它傳輸至提供者時。 編碼格式無法變更，無法傳送二進位值或使用不同的編碼，例如UTF-16或GSM7。

如果任何選用參數的&#x200B;**標籤ID**&#x200B;與外部帳戶中定義的&#x200B;**服務標籤ID**&#x200B;相同，則以此表中定義的值為準。

## SMPP連接器 {#ACS-SMPP-connector}

![](assets/do-not-localize/sms_protocol_3.png)

箭頭代表資料流。

此處需注意的最重要事項是有多個SMPP連接器線程。 這些線程都相同，並且共用相同的配置。 這就是為什麼連接數總是乘以線程數。

客戶無法更改線程數，因為它需要更改配置檔案。

### SMPP連接器的行為說明 {#behavior-smpp-connector}

#### 匹配MT、SR和broadlog條目 {#matching-mt-sr}

在Adobe Campaign中，訊息是broadlog項目。 在Adobe Campaign Standard中，外部連接器只需了解正常運作的broadlog表格：`nmsBroadLogExec`。 工作流程負責將broadlog項目複製回其特定目標維度(nmsBroadLogXXX)。

很可惜，SMPP不允許傳送ID及訊息：提供者會為每個MT提供MT ID，然後提供一或多個具有相同ID的SR。

提供程式提供的ID儲存在`nmsBroadLogExec`表的`sProviderId`列中。 SR總是在成功發送和確認MT後到達，但有時可能未按順序到達，在Adobe Campaign中稱為傑出SR。 處理線程將這些SR暫時儲存在RAM中，直到完整資訊到達。

確認MT時(`SUBMIT_SM_RESP`)，會立即在資料庫中更新`sProviderId`。

每個SR由SMPP處理線程分別處理。 此過程是偽同步的：它被視為從外部同步，但是會透過事件導向的實作在內部實作。 只有在成功更新broadlog時，才會確認SR，如果遇到錯誤，則SR被拒絕。

以下是套用至每個SR的程式：

* SR的ID是使用規則運算式擷取。
* 會在`nmsBroadLogExec:sProviderId`中搜尋ID。
* 使用規則從SR中提取狀態+錯誤代碼。
* broadlog訊息機制可用來限定錯誤並尋找broadlog訊息ID。
* broadlog會更新為上述所有資訊。
* 確認SR。

檢查上述步驟需要&#x200B;**啟用詳細SMPP跟蹤**&#x200B;以手動檢查所有步驟是否已正確應用。 每次Adobe Campaign連線至新的SMPP提供者時，都需要此項目。

## 上線前 {#checklist}

此檢查清單提供上線前應檢查的項目清單。 未完成的設定可能會導致許多問題。

### 檢查外部帳戶衝突 {#external-account-conflict}

檢查您沒有舊的SMS外部帳戶。 如果禁用測試帳戶，則會運行在生產系統上重新啟用測試帳戶的風險，並產生潛在衝突。

檢查沒有其他實例連接到此帳戶。 尤其是，請確定預備環境未連線至帳戶。 有些提供者會支援此功能，但無論是在Adobe Campaign端，還是在提供者的平台上，都需要非常特定的設定。

如果您需要在同一個Adobe Campaign執行個體上有多個帳戶連線至相同的提供者，請連絡提供者，以確定他們實際上區分這些帳戶之間的連線。 有多個帳戶具有相同登入資訊需要額外設定。

### 在檢查期間啟用詳細SMPP跟蹤 {#enable-verbose}

檢查期間，您應始終啟用詳細的SMPP跟蹤。
即使您無法自行檢查日誌，支援人員也會更輕鬆地幫助您。

### 測試您的SMS {#test}

* **使用各種字元傳送**
簡訊如果您需要使用非GSM或非ASCII字元傳送簡訊，請嘗試傳送一些字元盡可能多的訊息。如果您設定自訂字元對應表格，請至少傳送一則簡訊（所有可能） 
`data_coding` values.

* **檢查SR是否已正**
確處理SMS應在傳送記錄中標示為已接收。傳送記錄應成功，如下所示：

檢查您是否已變更傳送提供者名稱。 傳送記錄不應包含    `SR yourProvider stat=DELIVRD err=000|#MESSAGE`
檢查您是否已變更傳送提供者名稱。生產環境上的傳送記錄不應包含**SR Generic**。

* **檢查MO是否**
已處理如果您需要處理MO（自動回覆、將MO儲存在資料庫等）嘗試進行一些測試。 傳送幾則簡訊給所有自動回覆關鍵字，並檢查回覆是否足夠快，幾秒以內。
在記錄中檢查Adobe Campaign是否回覆成功 
`DELIVER_SM_RESP` (command_status=0)。

### 檢查PDU {#check-pdus}

即使消息看起來很成功，也必須檢查PDU的格式是否正確。

連線至之前未連線至Adobe Campaign的提供者時，必須執行此步驟。

#### 綁定 {#bind}

檢查`BIND_* PDUs`是否正確傳送。 要檢查的最重要事項是，提供程式始終返回成功的`BIND_*_RESP PDUs`(command_status = 0)。

檢查`BIND_* PDU`s是否不太多。如果其中有太多，可能表示連線不穩定。 如需詳細資訊，請參閱[連線不穩定的問題](../../administration/using/sms-protocol.md#issues-unstable-connection)一節。

#### INQUIRE_LINK {#enquire-link-pdus}

檢查連接空閒時是否定期交換`ENQUIRE_LINK PDU`s。

#### SUBMIT_SM / DELIVER_SM {#submit-sm-deliver-sm}

傳送訊息，然後在記錄中搜尋其對應的`SUBMIT_SM`、`SUBMIT_SM_RESP`、`DELIVER_SM`和`DELIVER_SM_RESP PDU`s。

使用`SUBMIT_SM PDU`:

* 檢查`data_coding`是否正確，預設為0。
* 檢查`short_message`是否已正確編碼。 請嘗試使用支援多種編碼的十六進位轉換器來解碼。

使用`SUBMIT_SM_RESP PDU`:

* 檢查它是否成功，command_status = 0。
* 檢查其內文是否包含格式正確的ID，後跟「0」位元組。

使用`DELIVER_SM PDU`:

* 將十六進位`short_message`欄位解碼。
* 使用規則運算式檢查工具，確認在SR中ID的`Extraction`規則運算式中定義的規則運算式只會傳回一個擷取群組，且會擷取訊息中的整個ID。
* 檢查擷取的ID是否與`SUBMIT_SM_RESP`中的ID相符。
* 檢查在`Extraction` SR中狀態的regex中定義的regex是否返回stat欄位的內容。
* 檢查在`Extraction` SR中錯誤的regex中定義的regex是否傳回err欄位的內容。

使用`DELIVER_SM_RESP PDU`:

* 檢查在收到`DELIVER_SM PDU`後是否快速傳送，通常少於1秒。
* 檢查它是否成功，command_status = 0。

### 詢問提供者是否一切正常 {#provider}

即使您的SMS成功，請連絡提供者以查看一切都順序。

### 禁用詳細SMPP跟蹤 {#disable-verbose}

完成所有檢查後，最後一件事是&#x200B;**禁用詳細SMPP跟蹤**，以不生成太多日誌。 即使在生產系統上，您也可以重新啟用它們以用於疑難排解。
