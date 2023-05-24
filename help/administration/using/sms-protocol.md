---
title: 簡訊連接器通訊協定及設定
description: 瞭解有關SMS連接器及如何配置的詳細資訊
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: ea936128-1c51-483d-914c-6d06708456d6
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '8664'
ht-degree: 1%

---

# 簡訊連接器通訊協定及設定 {#sms-connector-protocol}

>[!NOTE]
>
>的 **SMS連接器協定和設定** Adobe Campaign Classic在這裡 [頁](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html)。
>
>通過本文檔，所有對協定、欄位名和值的詳細資訊的引用都引用 [SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

## 概覽 {#overview}

簡訊可能僅限於發送沒有格式的短文本消息，但其簡單性使其成為一種有價值的通信通道。

發送SMS的主要方式有兩種：

* 用手機手動發送，這是人與人直接交流的常用方式。

* 從網際網路上發送，Adobe Campaign發送資訊的方式。 為此，您需要一個將網際網路連接到移動網路的SMS服務提供商。
Adobe Campaign使用SMPP協定將SMS發送給服務提供商。

本文檔將指導您完成Adobe Campaign與SMPP提供商之間的連接設定。

SMPP提供商有時可能會偏離官方規範，但Adobe Campaign的SMS連接器提供了許多選擇來調整其行為，使其與大多數提供商相容。

>[!IMPORTANT]
>
>設定與新提供程式的連接可能需要一些技術技能、TCP知識、二進位、十六進位表示和文本編碼。 它還需要與提供商積極合作。

### 簡訊類型 {#sms-types}

通過簡訊提供商發送大量簡訊時，會遇到三種不同的簡訊：

* **SMS MT（已移動終止）**:Adobe Campaign通過SMPP提供商向行動電話發送的簡訊。

* **SMS MO（移動發源）**:由移動端通過SMPP提供商發送給Adobe Campaign的SMS。

* **SMS SR（狀態報告）、 DR或DLR（交貨回執）**:移動設備通過SMPP提供商發送給Adobe Campaign的回執，表示SMS已成功接收。 Adobe Campaign可能還會收到SR，指出無法傳遞消息，通常會提供錯誤描述。

您需要區分確認（RESP PDU, SMPP協定的一部分）和SR :SR是一種通過網路端到端發送的SMS，而確認只是確認一次傳輸成功。

確認和SR都可能觸發錯誤，區分兩者將有助於排除故障。

### SMS攜帶的資訊 {#information-sms}

簡訊攜帶的資訊比文本要多。 下面是您希望在SMS中找到的內容清單：

* 文本，限制為140位元組，表示70到160個字元之間，具體取決於編碼。 請參閱 [SMS文本編碼](../../administration/using/sms-protocol.md#sms-text-encoding) 詳細資訊和限制。

* 收件人地址，有時被調用 `ADC` 或 `MSISDN`。 這是接收簡訊的手機號碼。

* 可以調用的發件人地址 `oADC` 有時 `sender id`。 這可以是日常使用中的電話號碼、通過提供商發送的簡短代碼或名稱。 名稱是可選功能，在這種情況下您無法回復SMS。

* 指示消息是否為快閃消息的標誌。 快閃記憶體消息是未儲存在記憶體中的彈出窗口。

* 指示是否需要SR的標誌。

* 有效日期，在此日期後，不允許任何網路設備重試。

* A `data_coding` 欄位，它指示文本的編碼。

## SMPP協定 {#smpp-protocol}

Adobe Campaign Standard支援SMPP協定3.4版。這是一種廣泛的協定，它允許向提供商(SMSC)發送SMS，並接收SMS和接收。 有關詳細資訊，請參閱 [SMPP文檔](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

SMS服務提供方側的網路設備通常稱為SMSC。

### SMPP連接 {#smpp-connections}

Adobe Campaign通過TCP與SMS服務提供商的網路設備連接。 SMPP協定設定從Adobe Campaign到提供程式的永久TCP連接。 TCP連接始終由Adobe Campaign啟動，甚至是接收消息。
SMPP會開啟1個或2個TCP連接，具體取決於其模式。 所有連接始終由Adobe Campaign發起。

SMPP協定可以在兩種模式下工作：

* **發射機+接收機（或TX+RX）**:兩個獨立的TCP連接用於發送和接收消息。
* **收發器(Abor TRX)**:單個TCP連接用於發送和接收消息。

>[!NOTE]
>
>TRX是Adobe Campaign Standard的首選，因為它減少了連接數，並簡化了在出現故障時的連接恢復。

### SMPP PDU {#smpp-pdu}

SMPP傳輸單元（「資料包」）稱為PDU。 A **PDU** 包含命令、狀態、序列號和資料。

每個PDU必須由 `SMPP RESP PDU` （同步響應）。 請求可以流水線處理：發送方可以發送許多命令而無需等待 `RESP`，可以隨時進行流水線處理的請求數稱為窗口。 `RESP PDU` 可以按任何順序到達，與其相應的啟動器PDU的順序無關。

在分隔 **發射機+接收機** 模式，所使用的連接取決於所傳輸的消息類型。 發射機連接用於MT，接收機連接用於MO和SR。 每種消息的請求和響應都通過同一TCP連接發送。

例如，在發送MT時，使用發送器連接， `RESP` 確認MT也通過發送器通道發送。 當您接收MO（或SR）時，接收器連接用於接收MO併發送 `RESP` 來承認國防部。

![](assets/do-not-localize/sms_protocol_1.png)

在Adobe Campaign Standard,MT和SR協調是MTA的固有屬性，因此沒有專用的SMS過程。

成功 `SUBMIT_SM_RESP PDU` 成功時觸發發送日誌中的「已發送」消息狀態 `DELIVER_SM (SR) PDU` 觸發「已接收」消息狀態。

### 安全方面 {#security-aspects}

協定本身未加密。 大多數提供程式在允許清單上實現IP的變型，因此Adobe Campaign伺服器IP地址必須聲明給提供程式。

Adobe Campaign支援在綁定階段傳遞登錄和密碼。 它還支援TLS上的SMPP。 應當指出，需要證書才能獲得適當的安全。 儘管SMPP連接器允許繞過證書檢查，但它只應用於測試，因為沒有證書的TLS提供的安全級別要低得多。

連接器使用系統提供的預設證書 `openssl` 的下界。 通常由 `/etc/ssl/certs` 的下界。 預設情況下，此目錄由「ca-certificates」包提供，但可以自定義。

### 每種PDU中的資訊 {#information-pdu}

每種PDU都有不同的欄位，這些欄位承載不同的資訊。 這些PDU在 [SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)。

下面的每個部分都介紹PDU及其同步響應(`*_RESP PDU`)。 所有PDU都必須由相應的PDU確認 `RESP`，這是規範的必備部分。

PDU可以有可選欄位。 此處僅介紹最常見的欄位。 請參閱 [SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) 的子菜單。

#### BIND_TRANSMITTER/BIND_RECEIVER/BIND_TURNSEIVER {#bind-transmitter}

此PDU用於啟動到SMSC的連接。 **發射器**。 **接收機** 和 **收發器** 模式只更改允許通過此連接傳輸的SMS的類型，具體是：

| 模式 | 允許的簡訊種類 |
|:-:|:-:|
| 發射器 | 手動 |
| 接收機 | MO + SR |
| 收發器 | MT + MO + SR |

中的顯著欄位 `BIND_* PDU`:

* **系統ID**:用於驗證的登錄。 在外部帳戶中設定。

* **密碼**:用於驗證的密碼。 在外部帳戶中設定。

* **系統類型**:需要為某些提供程式設定特定值。 在外部帳戶中設定，所有版本都可用。 通常區分不同類型的合同、渠道、國家等。

* **地址噸** 和 **addr_npi**:某些提供程式需要。 由 `Bind TON` 和 `Bind NPI` 的子菜單。

* **地址範圍**:某些提供程式需要。 大多數情況下，這是此連接上允許的快捷方式清單。 在外部帳戶中設定。

`BIND_*_RESP` 沒有特定欄位，它確認連接是否成功。

#### 解除綁定 {#unbind}

此PDU必須由系統發送，然後才能斷開連接。 它必須等待匹配 `UNBIND_RESP PDU` 關閉連接之前。

符合要求的SMSC不能關閉連接，TCP連接由Adobe Campaign連接器控制。

#### 提交_SM {#submit-sm}

此PDU將MT發送到SMSC。 其響應PDU提供MT的ID。

中的顯著欄位 `SUBMIT_SM PDU`:

* **服務類型**:某些提供程式所需的。 在交貨屬性中設定。

* **源_addr_ton** 和 **源_addr_npi**:指示傳輸的源地址類型。 這些欄位的含義是標準化的，但是，由於某些提供方使用它的方式不同，因此您應詢問提供方其正確值。 在外部帳戶中設定。

* **源地址**:MT的源地址/oADC。 它將顯示在手機上。 在外部帳戶和交貨中設定，交貨中的值優先於外部帳戶的值。

* **dest_addr_ton** 和 **dest_addr_npi**:指示傳輸的目標地址類型（例如本地或國際格式）。 這些欄位的含義是標準化的，但是，由於某些提供方使用它的方式不同，因此您應詢問提供方其正確值。 在外部帳戶中設定。

* **目標地址**:收件人地址、電話號碼或MSISDN。

* **esm_class**:用於判斷文本欄位中是否使用了UDH。 如果 `message_payload` 未使用模式。

* **優先順序標誌**:此消息的優先順序高於其他消息。 這與交付本身的優先順序有關。

* **有效期**:不應嘗試重試的時間戳。 在交貨本身中設定。

* **已註冊的交付**:指示是否請求SR。 Adobe Campaign始終設定此標誌，但自動答復除外。 對於多部件消息，僅為第一部分設定標誌。 所有版本都具有相同的行為。

* **資料編碼**:指示在文本欄位中使用的編碼。 查看 [SMS文本編碼](../../administration/using/sms-protocol.md#sms-text-encoding) 的子菜單。

* **短消息**:消息的文本。 如果使用UDH，則還包含UHD頭。

Adobe Campaign支援以下可選欄位：

* **dest_addr_subunit**:用於指定SMS的目標：快閃記憶體、移動或SIM卡。 在交貨屬性中設定。

* **消息負載**:在外部帳戶中啟用後，長消息將在單個PDU中發送，文本將在此欄位中發送，而不是 `short_message` 的子菜單。

#### 提交_SM_RESP {#submit-sm-resp}

此PDU將包含MT的ID。 這對於與傳入的SR匹配非常有用。

>[!IMPORTANT]
>
>許多提供程式以十六進位形式傳輸MT ID。 確保設定 **MT確認中的ID格式** 正確設定外部帳戶。

某些提供程式發送 `SUBMIT_SM_RESP` 發送SR後。 為瞭解釋這種行為，Adobe Campaign在回復之前等30秒 **消息ID無效** ID未知的SR。

#### 交付_SM {#delivery-sm}

此PDU由SMSC發送到Adobe Campaign。 它包含MO或SR。

大多數欄位的含義與 `SUBMIT_SM` 對。 下面是有用欄位的清單：

* **源地址**:MO/SR的源地址。 這通常是電話號碼。

* **目標地址**:接收MO或SR的短代碼。

* **esm_class**:用於判斷PDU是MO還是SR。

* **短消息**:的子菜單。 對於SR，此包含SMPP協定規範的附錄B中描述的資料。 請參閱 [SR錯誤管理](../../administration/using/sms-protocol.md#sr-error-management) 的子菜單。

Adobe Campaign能夠讀取 `receipted_message_id` 帶有某些配置調整的可選欄位。

#### 交付_SM_RESP {#deliver-sm-resp}

此PDU由Adobe Campaign發送以確認SR和MO。

Adobe Campaign Standard `DELIVER_SM_RESP` 所有處理步驟都成功後， 這保證在仍存在處理錯誤的風險時不確認SR或MO。

#### INQUIRE_LINK {#enquire-links}

此PDU僅用於檢查連接是否處於活動狀態。 其頻率應根據提供商的需要來設定。

預設60秒應與外部帳戶中設定的大多數配置相匹配。

#### INQUIRE_LINK_RESP {#enquire-links-resp}

此PDU確認連接處於活動狀態。

### 多部分SMS（長SMS） {#multipart}

多部分SMS或長SMS是多部分發送的SMS。 由於移動網路協定中的技術限制，SMS不能大於140位元組，或者需要拆分。 查看 [SMS文本編碼](../../administration/using/sms-protocol.md#sms-text-encoding) 的子菜單。

長消息的每個部分都是單個SMS。 這些部件在網路上獨立運行，並由接收行動電話組裝。 為處理重試和連接問題，Adobe Campaign以反向順序發送這些部件，並僅在消息的第一部分請求SR，最後一部分是發送的。 由於行動電話只在收到其第一部分時顯示消息，因此對附加部分的重試不會在行動電話上產生重複。

使用 **每條消息的最大SMS數** 的 **交貨模板**。 超過此限制的消息在發送時將失敗，因為SMS失敗的原因太長。

發送長簡訊有兩種方式：

* **UDH**:預設和推薦的長消息發送方式。 在此模式下，連接器將消息拆分為多個 `SUBMIT_SM PDU`都有UDH資訊。 此協定是手機本身使用的協定。 這意味著Adobe Campaign對消息生成擁有最大的控制權，因此它能夠準確計算發送了多少個部件以及這些部件是如何分割的。

* **消息負載**:用單一方式發送整個長資訊 `SUBMIT_SM PDU`。 供應商將不得不分割它，這意味著Adobe Campaign不可能確切知道已發送了多少部件。 某些提供商需要此模式，但我們建議您僅在他們不支援UDH時才使用它。

請參閱 `esm_class`。 `short_message` 和 `message_payload` 的 [提交_SM PDU](../../administration/using/sms-protocol.md#information-pdu) 的子菜單。

### 吞吐量上限和窗口 {#throughput-capping}

大多數提供程式要求每個SMPP連接的吞吐量限制。 這可以通過在外部帳戶中設定多個SMS來實現。 請注意，每個連接都會發生吞吐量限制，總有效吞吐量是每個連接的限制乘以總連接數。 在 [同時連接](../../administration/using/sms-protocol.md#connection-settings) 的子菜單。

要達到最大可能的吞吐量，您需要微調最大發送窗口。 發送窗口是 `SUBMIT_SM PDU`可以不等待就發送 `SUBMIT_SM_RESP`。 查看 [發送窗口設定](../../administration/using/sms-protocol.md#throughput-timeouts) 的子菜單。

### SR和錯誤管理（「附錄B」） {#sr-error-management}

SMPP協定定義中的標準同步錯誤 `RESP PDU`s，但它不定義SR的錯誤代碼。 每個提供程式都使用各自的錯誤代碼及其含義。

建議見《公約》附錄B [SMPP協定規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) （第167頁），但未列出實際錯誤代碼及其含義。

為適應錯誤管理，Adobe Campaign的廣播消息系統已被用於正確設定錯誤及其嚴重性（硬、軟等）。

如上所述，存在兩種不同的誤差：

* 同步回復 `SUBMIT_SM_RESP` 在消息發送到SMSC後立即發生
* 當移動設備收到消息或消息超時時，可能會很晚收到的回執。 在這種情況下，在SR中發現錯誤。

收到SR後，在其中可找到狀態和錯誤 `short_message` 欄位（附錄B符合實施的示例）。 的 `short_message` PDU的欄位通常稱為 **文本欄位** 因為它包含MT中的文本。 對於SR，它包含技術資訊加上一個名為 **文本**。 這2個欄位不同， `short_message` 實際上包含 **文本** 欄位和其他資訊。

#### SR文本欄位格式 {#sr-text-field-format}

規範建議在SR文本欄位中使用此格式。 它是子欄位的清單，用冒號分隔，以分隔欄位名稱及其值。 欄位名稱不區分大小寫。

與附錄B建議匹配的SR文本欄位示例：

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

id欄位是在 `SUBMIT_SM_RESP PDU`,MT的確認

`sub` 和 `dlvrd` 本應計算已傳送部件和已傳送消息的數量，但Adobe Campaign沒有使用這種方法，因為廣播系統提供了更好、更完整的資訊。

`submit date` 和 `done date` 欄位是MT何時發送以及SR何時由移動器發送的指示時間戳。 預計在設定錯誤日期的手機上給出的時區，甚至時間戳錯誤時會出現一些問題。

stat欄位很重要，因為它會告訴消息的狀態。 唯一重要的狀態是 `DELIVRD`。 `UNDELIV` 和 `REJECTD`。 的 `DELIVRD` 狀態表示成功，另外兩個表示錯誤。 其它值是可能的，但通常是中間通知，例如MT到達了移動運營商，而不是行動電話。 這些中間通知被Adobe Campaign忽略。

錯誤欄位包含特定於提供程式的錯誤代碼。 提供程式必須提供可能的錯誤代碼及其含義的表，才能解釋此值。

最後，文本欄位通常包含MT文本的開頭。 這被Adobe Campaign忽略，一些提供商不會傳輸它以避免PII洩漏和網路頻寬消耗。 在故障排除期間，可通過讀取此欄位來更輕鬆地發現與testMT匹配的SR。

### Adobe Campaign Standard擴展通用SMPP中SR處理示例 {#sr-processing}

此示例顯示在附錄B建議案後實施的案例、外部帳戶中的預設值和成功的SMS MT。

```
id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

首先， `id extraction` regex被應用於提取ID並與相應的MT協調。

然後， `status extraction` 規則運算式 `error code extraction` regex將應用於提取這些欄位並附加到字串中。

廣播消息由此資訊構成，原始的未更改字串被附加以供參考：

```
SR ExampleProvider DELIVRD 000|MESSAGE=id:1234567890 sub:001 dlvrd:001 submit date:1608011415 done date:1608011417 stat:DELIVRD err:000 Text:Hello Adobe world
```

然後對消息進行標準化，刪除MESSAGE部分以能夠匹配具有相同統計碼和錯誤碼的多個消息。

```
SR ExampleProvider DELIVRD 000|#MESSAGE#
```

如果廣播消息表中尚未設定該消息，則將使用整個消息作為 **第一個文本** 和正常化的資訊。 然後，連接器使用成功和 `error` regex以確定是成功還是失敗：

* 如果它與 `success` regex，它會被視為成功。

* 如果它與 `error` regex，消息被限定為錯誤。

* 如果這兩個regex不匹配，則忽略SR。 它可能是中間通知，Adobe Campaign不處理。

預設情況下，所有錯誤都設定為軟錯誤。 這意味著必須手動設定硬錯誤。

### SMS文本編碼 {#sms-text-encoding}

你應該 **在編碼出現問題時，請始終與SMSC提供商聯繫**。 只有SMSC提供商對其支援的編碼有精確的瞭解，並且由於技術平台的限制可能適用特殊規則。

SMS消息使用特殊的7位編碼，通常稱為GSM7編碼。

在SMPP協定中，GSM7文本將擴展到每個字元8位，以便更輕鬆地進行故障排除。 SMSC將在將其發送到移動設備之前將其打包為7位/字元。 這意味著 `short_message` 在SMPP幀中，SMS的欄位長度可能高達160位元組，而在移動網路上發送時，該欄位長度限制為140位元組。

在編碼問題中，需要檢查以下重要事項：

* 確保知道哪些字元屬於哪個編碼。 GSM7不完全支援音調符號（重音）。 特別是在法語中，é和è是GSM7的一部分，但ê和ï不是。 西班牙語也是如此。

* C帶下加(C)字元只出現在GSM7字母表的上框中，但一些手機將其顯示在下框或「智慧」字元中。 一般建議是完全避免它，並刪除下拉或切換到UCS-2。

* **在SMS中不使用ASCII** 除非SMSC提供程式明確請求。 該編碼浪費了空間，因為它具有8位字元，並且比GSM7的覆蓋範圍小。 這種編碼可用於北美使用的CDMA網路。

* Latin-1並不總是受支援。 嘗試使用拉丁語–1之前，請檢查與SMSC提供程式的相容性。

* Adobe Campaign連接器不支援國家語言班次表。 必須使用UCS-2或其他 `data_coding` 的雙曲餘切值。

* UCS-2和UTF-16通常由手機混合使用。 使用UCS-2中不存在的emoji和其他字元時，會出現此問題。

* 大多數電話沒有所有UCS-2字元的字型字形。 智慧手機往往能夠顯示罕見的字元，但功能手機通常對購買國母語的有用功能的支援有限。 如果您想使用emoji或ASCII-art，請在發送前在多種電話上test它。 Adobe Campaign預覽不模擬丟失的字形，並將顯示Web瀏覽器上可用的符號。

的 `data_coding` 欄位將告訴您使用的編碼。 一個主要問題是，值0表示規範中的預設SMSC編碼，通常指GSM7。 與與編碼關聯的SMSC夥伴聯繫 `data_coding` = 0,Adobe Campaign只支援。 其他 `data_coding` 值往往遵循規範，但唯一可確保的方法是與SMSC提供程式進行檢查。

消息的最大大小取決於其編碼。 下表匯總了所有相關資訊：

| 編碼 | 常用資料編碼 | 消息大小（字元） | 多部件SMS的部件大小 | 可用字元 |
|:-:|:-:|:-:|:-:|:-:|
| GSM 7 | 0 | 160 | 152 | GSM7基本字元集+擴展（擴展字元為2個字元） |
| 拉丁語–1 | 3 | 140 | 134 | ISO-8859-1 |
| UCS-2 <br>UTF-16 | 8 | 70 | 67 | Unicode（因電話而異） |

## SMPP外部帳戶參數 {#SMPP-parameters-external}

SMPP協定的每個實現都有許多不同。 為了提高相容性和適應性，可以使用許多設定來更改SMPP連接器的行為。 本節介紹每個參數及其對連接器的影響。

### 常規參數和路由 {#general-parameters-routing}

**限制此帳戶的MTA實例**

可以設定允許連接到SMPP提供程式的MTA實例數的限制。 選中後，您最多可以指定使用多少個MTA。

此選項允許對連接數進行更精確的控制，請參見 [同時連接](../../administration/using/sms-protocol.md#connection-settings)。

如果設定的值高於正在運行的MTA的數量，則所有MTA都將正常運行：此選項僅為限制，無法生成其他MTA。

如果需要精確控制連接數，例如提供程式要求，建議始終設定此選項，即使當前部署運行的MTA數量正確。 如果以後添加了額外的MTA，則仍然會遵守連接限制。

### 連線設定 {#connection-settings}

#### SMPP連接模式 {#smpp-connection-mode}

在中設定連接 **收發器** 模式或分隔 **發射機+接收機** 的子菜單。 當您切換到分隔 **發射機+接收機** 模式，設定 **SMPP連接模式** 部分適用於 **接收器連接設定** 節應用於接收器連接，僅當您檢查了 **為接收器使用不同的參數** 複選框。

#### SMSC 實作名稱 {#smsc-implementation-name}

設定SMSC實現的名稱。 應將其設定為提供程式的名稱。 請與管理員或交付性團隊聯繫，以瞭解在此欄位中添加的內容。 此欄位的角色在 [SR錯誤管理](../../administration/using/sms-protocol.md#sr-error-management) 的子菜單。

#### 伺服器 {#server}

要連接的伺服器的DNS名稱或IP地址。

#### 連接埠 {#port}

要連接的TCP埠。

#### 帳戶 {#account}

連接的登錄。 傳入 `system_id` BIND PDU的欄位。

#### 密碼 {#password}

SMPP連接的密碼。 在BIND PDU的口令欄位中傳遞。

#### 系統類型 {#system-type}

傳入的值 `system_id` BIND PDU的欄位。 有些提供商需要在此處提供特定值。

#### 同時連接 {#simultaneous-connections}

在Adobe Campaign Standard，它定義每個SMS線程和每個MTA進程的連接數。
MTA進程數由部署決定：通常有2個MTA和1個線程。 可以使用smppConnectorThreads設定在config-instance.xml檔案中更改線程數。 通常每個容器有1個MTA進程，每個MTA進程有1個線程。

Adobe Campaign Standard總連接公式：

* **總連接數=同時連接數*線程數* MTA數**

在外部帳戶中設定同時連接，在config-instance.xml檔案(smppConnectorThreads)中設定線程數，並且可以在外部帳戶中限制MTA數。

分隔 **發射/接收** 模式，上面的連接數表示 **發射/接收** 對表示連接總數將是總數的兩倍。

#### 透過 SMPP 啟用 TLS {#enable-TLS}

使用TLS連接到提供程式。 連接將被加密。 TLS連接由OpenSSL庫管理，任何適用於OpenSSL的連接都將為True。

#### 在記錄檔中啟用詳細的 SMPP 追蹤 {#enable-verbose-log-file}

此設定將轉儲日誌檔案中的所有SMPP通信。 在初始設定期間，通常需要調整參數。 在排除連接器故障時必須啟用此功能，並將其與提供程式看到的通信進行比較。

### 接收器連接設定 {#receiver-connection}

此節僅在分隔的 **發射機+接收機** 的子菜單。

#### 為接收方使用不同的參數 {#receiver-parameters}

如果未選中該框，則發送器和接收器的設定相同。

選中該框後， **連接設定** 部分將應用於 **接收器連接** 設定將應用於接收器。

**接收伺服器、埠、帳戶、密碼、系統類型**

在中時，這些設定將應用於接收器 **發射機+接收機** 的子菜單。 它們與發射器部分一樣工作，有關詳細資訊，請參閱上文。

### SMPP頻道設定 {#smpp-channel-settings}

#### 允許字元音譯 {#allow-character-transliteration}

音譯是查找與缺失字元等效的過程。 例如，GSM編碼中缺少法文「ê」（帶揚抑符）字元，但可以用「e」替換，而不會影響可讀性。

如果未選中此框，則文本編碼將失敗，如果它無法按原樣對字串進行完全編碼。

選中此框後，文本編碼將嘗試將字串轉換為近似版本，而不是失敗。 如果某些字元在目標編碼中沒有等效字元，則文本編碼將失敗。

查看 [定義編碼設定的特定映射](../../administration/using/sms-protocol.md#SMSC-specifics) 的子菜單。

#### 將傳入的MO儲存在資料庫中 {#incoming-mo-storing}

啟用後，傳入的MO將儲存在資料庫的inSMS表中。 可以使用任何工作流的查詢活動查詢此表。

#### 在SR處理期間啟用即時KPI更新 {#real-time-kpi}

啟用後，在接收錯誤SR時，將在主交貨頁上即時更新KPI。

缺點是效能低，因為它會生成資料庫爭用。 如果禁用，統計資訊將由 **同構** 工作流，每20分鐘運行一次。

#### 來源編號 {#source-number}

定義消息的預設源地址。 僅當交貨中的源編號為空時，此設定才適用。

預設情況下，不會傳遞源編號欄位，因此提供程式將用它代替短代碼。

這啟用發送器地址/oADC覆蓋功能。

#### 簡短代碼 {#short-code}

指示帳戶的主短代碼。 如果此帳戶使用了多個短代碼，或者短代碼未知，請將此欄位留空。

指定短代碼對以下兩個功能有幫助：

* 如果未提供原始碼，則預覽將顯示短代碼。 它將反映手機上的真實行為。

* 自動回復功能的denylist設定僅發送給隔離特定短代碼的用戶。

#### 來源噸/NPI，目的噸/NPI {#ton-npi}

TON（編號類型）和NPI（編號計畫指標）在第5.2.5節中介紹 [SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) （第117頁）。 應將這些值設定為提供程式的需要。

按原樣傳輸 `source_addr_ton`。 `source_addr_npi`。 `dest_addr_ton` 和 `dest_addr_npi` 的 `SUBMIT_SM PDU`。

#### 服務類型 {#service-type}

此欄位按原樣在 `service_type` 的 `SUBMIT_SM PDU`。 將此設定為提供程式的需要。

### 吞吐量和超時 {#throughput-timeouts}

這些設定控制SMPP通道的所有計時方面。 某些提供程式要求對消息速率、窗口和重試計時進行非常精確的控制。 應將這些設定設定為與提供商的能力及其合同中指明的條件相匹配的值。

#### 傳送窗口 {#sending-window}

窗口是 `SUBMIT_SM PDU`可以在不等待匹配的情況下發送 `SUBMIT_SM_RESP`。

最大窗口為4的傳輸示例：

![](assets/do-not-localize/sms_protocol_2.png)

當網路鏈路具有高延遲時，該窗口有助於提高吞吐量。  窗口的值必須至少是SMS/s的數量乘以連結的延遲（以秒為單位），這樣連接器就永遠不會等待 `SUBMIT_SM_RESP` 發送下一條消息之前。
如果窗口太大，則在出現連接問題時可能會發送更多重複消息。 此外，大多數提供商對窗口有非常嚴格的限制，拒絕超過限制的消息。

如何計算最優發送窗口公式：

* 測量之間的最大延遲 `SUBMIT_SM` 和 `SUBMIT_SM_RESP`。

* 將此值（以秒為單位）乘以最大MT吞吐量。 這將給出最佳發送窗口值。

示例：如果在最大MT吞吐量中設定了300條SMS/s，並且介於 `SUBMIT_SM` 和 `SUBMIT_SM_RESP` 平均而言，最優值 `300×0.1 = 30`。

#### 最大 MT 輸送量 {#max-mt-throughput}

每秒和每個連接的最大MT數。 此設定將得到嚴格執行，MTA將永遠不會以超出此限制的速度推送消息。 對於需要精確限制的提供商來說，它非常有用。

要瞭解總吞吐量限制，請將此數乘以上述公式中詳述的連接總數。

0表示無限制，MTA將盡快發送MT。

通常建議將此設定保持在1000以下，因為除非對最終體系結構進行適當基準測試，否則無法保證超出此數字的準確吞吐量。 如果您需要超過1000的吞吐量，請與提供商聯繫。 將連接數增加到1000 MT/s以上可能更好。

#### 重新連線前的時間 {#time-reconnection}

當TCP連接丟失時，連接器將等待此秒數，然後嘗試建立連接。

#### MT 的有效期 {#expiration-period}

超時時間 `SUBMIT_SM` 與 `SUBMIT_SM_RESP`。 如果 `RESP` 未按時接收，消息將被視為失敗，並且將應用MTA的全局重試策略。

#### 繫結逾時 {#bind-timeout}

TCP連接嘗試和 `BIND_*_RESP` 回復。 超時後，連接將由Adobe Campaign連接器關閉，在重新連接之前，它將等待時間，然後再重試。

#### enquire_link 時段 {#enquire-link-period}

`enquire_link` 是一種特殊類型的PDU，用於保持連接正常。 此時段以秒為單位。 市場活動連接器僅發送 `enquire_link` 當連接空閒時，以節省頻寬。 如果在此時間段後兩次未收到RESP，則連接將被視為已死，並且將觸發重新連接進程。

### SMSC 細節 {#SMSC-specifics}

這些設定是高級設定，可使Adobe Campaign連接器適應大多數SMPP實現特性。

#### 定義編碼的特定映射 {#encoding-specific-mapping}

查看 [SMS文本編碼](../../administration/using/sms-protocol.md#sms-text-encoding) 的子菜單。

此設定允許您定義與規範不同的自定義編碼映射。 您將能夠聲明編碼清單及其編碼 `data_coding` 值。

MTA將嘗試使用清單中的第一個編碼進行編碼。 如果失敗，它將嘗試使用清單上的下一個編碼，等等。 如果不能使用編碼對消息進行編碼，則會發生錯誤。 一旦找到編碼，MTA將建立 `SUBMIT_SM PDU` 和 `data_coding` 欄位集中的值。

表中項的順序非常重要：編碼從上到下都嘗試。 您應該將最便宜或建議最多的編碼放在清單的頂端，然後是越來越昂貴的編碼。

請注意，UCS-2不會失敗，因為它可以對Adobe Campaign支援的所有字元進行編碼，並且UCS-2 SMS的最大長度要小得多：僅70個字元。

也可以使用此設定強制在映射表中僅聲明1行時始終使用特定編碼。

未選中複選框時使用的預設映射與下表相同：

| data_coding | 編碼 |
|---|---|
| 0 | GSM |
| 9 | UCS-2 |

這意味著MTA將嘗試在GSM中對消息進行編碼。 如果成功，它將發送 `data_coding` 設定為0。

如果消息無法以GSM編碼，則將以UCS-2編碼，並將 `data_coding` 到8。

#### 啟用message_payload {#enable-message-payload}

如果未選中，長SMS將被MTA拆分並以多個方式發送 `SUBMIT_SM PDU`與UDH合作。 該消息將由手機根據UDH資料重新合成。

選中後，將在一個SUBMIT_SM PDU中發送長SMS，將文本放在message_payload可選欄位中。 查看 [SMPP規範](../../administration/using/sms-protocol.md#ACS-SMPP-connector) 的下一頁。

如果啟用此功能，Adobe Campaign將無法單獨計算SMS部件：所有消息將被計算為在一個部分中發送。

#### 發送完整電話號碼 {#send-full-phone-number}

如果未選中此複選框，則只向提供商發送電話號碼的數字(`destination_addr` 的 `SUBMIT_SM` )。 這是預設行為，因為國際數字指示符（通常為+前置詞）被SMPP中的TON和NPI欄位替換。

選中該複選框後，電話號碼將按原樣發送，且沒有預處理和潛在空格，+前置詞或井號/散列/星號。

此功能還對自動回復denylist功能的行為產生影響：如果未選中該複選框，則會在插入隔離表中的電話號碼中添加+前置詞，以補償SMPP協定本身從電話號碼中刪除的+前置詞。

#### 跳過TLS證書檢查 {#skip-tls}

啟用TLS後，跳過所有證書檢查。

選中後，連接不再安全，不應在生產中啟用。

它可用於調試或test。

#### 綁定TON/NPI {#bind-ton-npi}

TON（編號類型）和NPI（編號計畫指標），詳情見5.2.5節 [SMPP 3.4規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf) （第117頁）。 這些值應設定為提供程式需要的任何值。

按原樣傳輸 `addr_ton` 和 `addr_npi` BIND PDU的欄位。

#### 地址範圍 {#address-range}

在BIND PDU的address_range欄位中按原樣發送。 此值應設定為提供程式需要的任何值。

#### 無效 ID 確認計數 {#invalid-id}

限制 **消息ID無效** `DELIVER_SM_RESP` 可以發送給單個SR。

**這應僅用於故障排除，作為解決方法** 在正常情況下設定為0。

Fox示例，當設定為2時：

* 提供程式發送SR(`DELIVER_SM`),ID為「1234」。

* 在資料庫中找不到ID「1234」。

* 連接器計數1 **無效ID** 該ID出錯，因此發送 `DELIVER_SM_RESP` 錯誤代碼為「消息ID無效」（正常行為）。

* 提供程式重試ID為「1234」的同一SR。

* 在資料庫中仍未找到ID「1234」。

* 連接器計數2 **無效ID** 該ID出錯，因此發送 `DELIVER_SM_RESP` 「OK」，即使處理不正確。

* 此功能用於在無效的SR塊合法且無法處理消息時刷新提供程式端的SR緩衝區。

將此欄位設定為0將禁用 **消息ID無效** 始終返回，這是正常行為。

將此欄位設定為1使連接器始終響應「OK」，即使ID無效。 這應設定為僅在監管下為1，以便進行故障排除，並且時間最短，例如從提供方問題中恢復。

#### SR 中 ID 的擷取規則運算式 {#regex-extraction}

SR格式未受SMPP協定規範的嚴格強制。 它僅是中描述的建議 [附錄B](../../administration/using/sms-protocol.md#sr-error-management) （第167頁）。 一些SMPP實現程式以不同格式設定此欄位，因此Adobe Campaign需要一種方法來提取正確的欄位。

預設情況下，它最多捕獲10個字母數字字元 `id:`。

regex必須只有一個捕獲組，其中的部件包含在括弧中。 ID部分必須用括弧括起來。 regex格式為PCRE。

調整此設定時，請確保盡可能多地包含上下文以避免出現假觸發器。 如果有特定前置詞，如 `id:` 在標準中，將它們包括在規則運算式中。 還盡可能使用單詞分隔符(\b)，以避免捕獲單詞中間的文本。

regex中未包含足夠的上下文可能會引入一個小安全漏洞：消息的實際內容可以包括在SR中。 如果僅與沒有上下文的特定ID格式（例如UUID）匹配，則它可能正在分析實際文本內容，例如嵌入在文本欄位中的UUID，而不是ID。

#### 應用規則運算式確定成功/錯誤狀態 {#regex-applied}

遇到具有未知stat/err欄位組合的消息時，這些regex將應用於stat欄位以確定SR是成功還是錯誤。 忽略stat值與任何這些區域不匹配的SR。

預設情況下，以開頭的stat值 `DELIV`，例如 `DELIVRD` 的 [附錄B](../../administration/using/sms-protocol.md#sr-error-management)，將被視為已成功傳遞和所有與錯誤匹配的stat值，例如 `REJECTED`。 `UNDELIV`，被視為錯誤。

#### MT確認中的ID格式 {#id-format-mt}

這表示在中返回的ID的格式 `message_id` 的 `SUBMIT_SM_RESP PDU`。

* **不修改**:ID按原樣儲存在資料庫中，如ASCII編碼文本。 不進行預處理或過濾。

* **小數**:ID應為ASCII格式的十進位數。 使用此設定時，前導和尾隨空格以及前導零將被刪除。

* **十六進位數**:ID應為ASCII格式的十六進位數，不帶前導0x或尾隨h。然後，ID將轉換為十進位數，然後儲存到資料庫中。

* **十六進位字串**:ID應為ASCII編碼的文本，它本身是一串以十六進位編碼的位元組。 例如，在PDU中，您會發現 `0x34 0x31 0x34 0x32 0x34 0x33`，轉換為ASCII &quot;414243&quot;。 然後，此字串被解碼為十六進位位元組字串，因此您會獲得「ABC」：將ID &quot;ABC&quot;儲存在資料庫中。

#### SR中的ID格式 {#id-format-sr}

這表示由 `Extraction` SR中ID的regex。 值與上面MT中的格式具有相同的含義和相同的行為。

**選擇性欄位中的 SR ID 或錯誤代碼**

如果選中，則可選欄位的內容將附加到上面由區域處理的文本中。 文本將具有格式 `0xTAG:VALUE`。 `0xTAG` 是標籤的4位十六進位值，例如 `0x002E`。

例如，您可能希望捕獲 `receipted_message_id` 的子菜單。 為此，啟用此複選框，將將以下文本添加到狀態：

```
0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739
```

在本示例中，0x001E是可選欄位的標籤，UUID是欄位的值。

為了捕獲此值，現在可以在SR欄位的ID的「提取」規則運算式中設定以下規則運算式：

```
\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b
```

>[!IMPORTANT]
>
>您只能捕獲具有文本(ASCII/UTF-8)值的可選欄位。 具體來說，二進位欄位不能用當前規則運算式系統可靠地捕獲。

**文字欄位中的 SR ID 或錯誤代碼**

如果選中， **文本** 欄位將在處理SR的狀態文本時保留。

如果提供程式在此欄位中放置重要資料（如ID或狀態），則此選項非常有用。 通常，此欄位可以安全地丟棄，因為它可能包含具有非ASCII編碼的文本，並會中斷規則運算式處理。

啟用此選項可能會在 `Extraction` SR欄位中ID的regex不夠具體。 內容 **文本** 欄位可以被分析為ID，攻擊者可能使用它注入偽造的ID，這可能導致部分拒絕服務情況。

**服務ID標籤**

允許添加自定義TLV。 此欄位設定標籤部分。 值可以按中的交貨進行自定義 **服務或程式ID** 交貨的高級參數中的值。

此設定僅允許每條消息添加一個TLV選項。

>[!NOTE]
>
>從21.1版開始，現在可以添加多個可選參數。 如需詳細資訊，請參閱本[區段](../../administration/using/sms-protocol.md#automatic-reply-tlv)。

### 自動回覆傳送至 MO {#automatic-reply}

此功能允許快速將文本回復到MO，並處理髮送到denylist的每短代碼。

的 **關鍵字** 和 **短碼** 列定義觸發自動答復的條件。 如果兩個欄位都匹配，則發送MO並觸發附加操作。 要指定通配符，應將欄位留空。 關鍵字與MO文本中的第一個字母數字字元匹配，忽略標點和前導空格。 這意味著 **關鍵字** 欄位不能包含空格，並且必須是單個單詞。

的 **關鍵字** 設定是前置詞。 例如，如果指定「AD」，它將匹配「AD」、「ADAPT」和「ADOBE」。 如果有多個具有公用前置詞的關鍵字，則需要注意順序，因為關鍵字是從上到下處理的。

的 **答復** column是要回復的文本。 此欄位中沒有可用的個性化設定。 如果將此欄位留空，則不會回復任何消息，但仍會觸發附加操作。

的 **其他操作** 列在兩者都 **關鍵字** 和 **短碼** 匹配，空短碼匹配所有短碼。 您可以發送到隔離區或從隔離區中刪除，值為「無」對文本的答復。 如果指定 **其他操作** 但離開 **答復** 欄位為空，將執行操作，但不會發送任何答復。 隔離僅對指定的短代碼應用，如果欄位為空，則應用所有短代碼。

>[!IMPORTANT]
>
>發送完整電話號碼設定會影響自動答復隔離機制的行為：如果未選中「發送完整電話號碼」，則輸入隔離的電話號碼將用加號(&quot;+&quot;)前置詞，使其與國際電話號碼格式相容。

表中的所有條目都按指定順序處理，直到一個規則匹配。 如果多個規則與MO匹配，則只應用最頂層的規則。

### 自動回復可選參數(TLV) {#automatic-reply-tlv}

從21.1版開始，您可以添加可選參數以自動答復MT。 它們作為可選TLV參數添加到 `SUBMIT_SM PDU` 第5.3節所述 [SMPP規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第131頁）。

有關可選參數的詳細資訊，請參閱 [節](../../administration/using/sms-protocol.md#smpp-optional-parameters)。

## SMS傳遞模板參數 {#sms-delivery-template-parameters}

某些參數可以按傳遞模板設定。

### 從欄位 {#from-field}

此欄位為可選欄位。 它允許覆蓋發送器地址(oADC)。 此欄位的內容位於 `source_addr` 的 `SUBMIT_SM PDU`。

SMPP規範將欄位限制為21個字元，但某些提供程式可能允許更長的值。 另請注意，在某些國家/地區可能會應用非常嚴格的限制，例如長度、內容、允許的字元。

### 傳送參數 {#delivery-parameters}

#### 每條消息的最大SMS數 {#maximum-sms}

僅當 **消息負載** 設定已禁用。 有關此的詳細資訊，請參閱此 [頁](../../administration/using/configuring-sms-channel.md)。 如果消息需要的SMS超過此值，將觸發錯誤。

SMS協定將SMS限制在255個部分，但一些手機很難將長消息與10個部分或10個以上的部分組合起來，這個限制取決於確切的型號。 我們建議您不要對每條消息進行5次以上的更新。

由於個性化消息在Adobe Campaign的工作方式，消息的大小可能有所不同。 擁有大量長消息可能會增加發送成本。

#### 傳輸模式 {#transmission-mode}

此欄位指示要傳輸的SMS類型：普通或快閃消息，儲存在移動或SIM卡上。

此設定在 `dest_addr_subunit` 可選欄位 `SUBMIT_SM PDU`。

* **未指定** 在PDU中不發送可選欄位。

* **Flash** 將值設定為1。 它發送一個快閃記憶體消息，該消息彈出在移動設備上，不儲存在記憶體中。

* **正常** 將值設定為0。 它發出一條正常資訊。

* **在移動設備上保存** 將值設定為2。 它告訴手機將簡訊儲存在記憶體中。

* **在終端上保存** 將值設定為3。 它告訴手機把簡訊存在SIM卡里。

#### 有效期限 {#validity-period}

有效期在 `validity_period` 的 `SUBMIT_SM PDU`。 日期始終以絕對UTC時間格式設定格式（日期欄位將以&quot;00+&quot;結束）。

#### SMPP可選參數(TLV) {#smpp-optional-parameters}

自21.1版起，您可以為此遞送發送的每個MT添加多個可選參數。 這些可選參數將添加到 `SUBMIT_SM PDU` 第5.3節所述 [SMPP規範](https://smpp.org/SMPP_v3_4_Issue1_2.pdf)（第131頁）。

表中的每一行都表示一個可選參數：

* **參數**:參數的說明。 未傳輸給提供程式。
* **標籤ID**:可選參數的標籤。 必須是有效的十六進位，格式為0x1234。 無效值將導致傳遞準備錯誤。
* **值**:可選欄位的值。 將UTF-8傳輸到提供程式時編碼為UTF-8。 無法更改編碼格式，無法發送二進位值或使用不同的編碼，如UTF-16或GSM7。

如果任何可選參數具有相同 **標籤ID** 的 **服務標籤ID** 在外部帳戶中定義，此表中定義的值將佔上風。

## SMPP連接器 {#ACS-SMPP-connector}

![](assets/do-not-localize/sms_protocol_3.png)

箭頭表示資料流。

這裡需要注意的最重要的一點是，有多個SMPP連接器線程。 這些線程都是相同的，並且共用相同的配置。 這就是為什麼連接數總是乘以線程數。

客戶無法更改線程數，因為它需要更改配置檔案。

### SMPP連接器的行為描述 {#behavior-smpp-connector}

#### 匹配MT、SR和broadlog條目 {#matching-mt-sr}

在Adobe Campaign，一條消息是一條廣播條目。 在Adobe Campaign Standard，外部連接器只需知道工作廣播表： `nmsBroadLogExec`。 工作流負責將廣播條目複製回其特定目標維(nmsBroadLogXXX)。

很遺憾，SMPP不允許發送ID和消息：提供程式向每個MT提供MT ID ，然後提供一個或多個具有相同ID的SR。

提供程式提供的ID儲存在 `sProviderId` 列 `nmsBroadLogExec` 的子菜單。 SR總是在成功發送和確認MT後到達，但有時可能出現故障，在Adobe Campaign被稱為傑出SR。 處理線程將這些SR臨時儲存在RAM中，直到完整資訊到達。

確認MT時(`SUBMIT_SM_RESP`) `sProviderId` 立即在資料庫中更新。

每個SR由SMPP處理線程單獨處理。 此過程是偽同步的：它被視為與外部同步，但是與事件驅動實現一起在內部實施。 僅當廣播已成功更新時，如果遇到錯誤，則SR被拒絕。

以下是應用於每個SR的流程：

* SR的ID使用regex提取。
* 在中搜索ID `nmsBroadLogExec:sProviderId`。
* 使用regex從SR中提取狀態+錯誤代碼。
* 廣播消息機制用於限定錯誤並查找廣播消息ID。
* 廣播將用上述所有資訊更新。
* 確認SR。

檢查上述步驟需要 **啟用詳細SMPP跟蹤** 以手動檢查是否正確應用了所有步驟。 每次Adobe Campaign連接到新的SMPP提供商時，都需要這一要求。

## 在生前 {#checklist}

此核對表列出了在開始使用前應檢查的內容。 設定不完善會導致許多問題。

### 檢查外部帳戶衝突 {#external-account-conflict}

檢查您沒有舊的SMS外部帳戶。 如果禁用test帳戶，則在生產系統上將其重新啟用並生成潛在衝突的風險。

檢查沒有其他實例連接到此帳戶。 特別是，確保階段環境未連接到帳戶。 一些提供商支援這一點，但它要求在Adobe Campaign端和提供商平台上進行非常具體的配置。

如果您需要在同一個Adobe Campaign實例上具有多個連接到同一提供程式的帳戶，請與該提供程式聯繫，以確保這些帳戶實際上能夠區分這些帳戶之間的連接。 擁有多個具有相同登錄名的帳戶需要額外配置。

### 在檢查期間啟用詳細SMPP跟蹤 {#enable-verbose}

檢查期間應始終啟用詳細的SMPP跟蹤。
即使您無法親自檢查日誌，「支援」也會更容易幫助您。

### Test您的SMS {#test}

* **發送包含各種字元的簡訊**
如果需要發送包含非GSM或非ASCII字元的SMS，請嘗試發送包含盡可能多不同字元的消息。 如果設定了自定義字元映射表，請至少發送一條SMS，以便所有可能 
`data_coding` values.

* **檢查SR是否已正確處理**
SMS應在傳遞日誌中標籤為已接收。 傳遞日誌應成功，如下所示：檢查是否更改了傳遞提供程式名稱。 傳遞日誌不應包含    `SR yourProvider stat=DELIVRD err=000|#MESSAGE`
檢查是否更改了傳遞提供程式名稱。 傳遞日誌不應包含 **SR通用** 在生產環境中。

* **檢查是否已處理MO**
如果您需要處理MO（自動答復、將MO儲存在資料庫中等） 試著做些test。 發送幾條簡訊，查看所有自動回復關鍵字，並檢查回復是否足夠快，不超過幾秒。
簽入Adobe Campaign用成功答復的日誌 
`DELIVER_SM_RESP` (command_status=0)。

### 檢查PDU {#check-pdus}

即使消息看起來很成功，檢查PDU的格式是否正確也很重要。

在連接到以前未連接到Adobe Campaign的提供程式時，此步驟是必要的。

#### 綁定 {#bind}

檢查 `BIND_* PDUs` 已正確發送。 要檢查的最重要的是，提供程式始終返回成功 `BIND_*_RESP PDUs` (command_status = 0)。

檢查是否太多 `BIND_* PDU`s如果其中有太多，則可能表示連接不穩定。 查看 [連接不穩定的問題](../../administration/using/sms-protocol.md#issues-unstable-connection) 的子菜單。

#### INQUIRE_LINK {#enquire-link-pdus}

檢查 `ENQUIRE_LINK PDU`當連接空閒時，定期交換。

#### SUBMIT_SM / DELIVER_SM {#submit-sm-deliver-sm}

發送消息，然後在日誌中搜索其相應消息 `SUBMIT_SM`。 `SUBMIT_SM_RESP`。 `DELIVER_SM` 和 `DELIVER_SM_RESP PDU`s

使用 `SUBMIT_SM PDU`:

* 檢查 `data_coding` 正確，預設為0。
* 檢查 `short_message` 正確編碼。 嘗試使用支援多個編碼的十六進位轉換器對其進行解碼。

使用 `SUBMIT_SM_RESP PDU`:

* 檢查是否成功，command_status = 0。
* 檢查其正文是否包含格式正確的ID，後跟「0」位元組。

使用 `DELIVER_SM PDU`:

* 解碼十六進位 `short_message` 的子菜單。
* 使用規則運算式檢查工具檢查在中定義的規則運算式 `Extraction` SR中ID的regex只返回一個捕獲組，並捕獲消息中的整個ID。
* 檢查提取的ID是否與 `SUBMIT_SM_RESP`。
* 檢查中定義的規則運算式 `Extraction` SR中狀態的regex返回stat欄位的內容。
* 檢查中定義的規則運算式 `Extraction` SR中錯誤的regex返回err欄位的內容。

使用 `DELIVER_SM_RESP PDU`:

* 檢查在收到 `DELIVER_SM PDU`，通常小於1秒。
* 檢查是否成功，command_status = 0。

### 詢問提供商是否一切正常 {#provider}

即使您的SMS成功，請與提供商聯繫，查看所有內容是否都正確。

### 禁用詳細SMPP跟蹤 {#disable-verbose}

一旦所有檢查完成，最後一件事就是 **禁用詳細SMPP跟蹤** 不生成太多日誌。 即使在生產系統上，您也可以重新啟用它們以進行故障排除。
