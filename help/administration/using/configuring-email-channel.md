---
title: 設定電子郵件通道
seo-title: 設定電子郵件通道
description: 設定電子郵件通道
seo-description: 瞭解如何設定電子郵件通道。
page-status-flag: 從未激活
uuid: 9fddb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 參考
topic-tags: 配置通道
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 設定電子郵件通道{#configuring-email-channel}

## 電子郵件通道參數 {#email-channel-parameters}

電子郵件設定畫面可讓您定義電子郵件頻道的參數。

![](assets/channels_1.png)

* **已傳送電子郵件的標題參數**

   在本節中，您可以指定 **[!UICONTROL masks]** 發件人地址和錯誤地址的授權。 如有必要，這些遮色片可以使用逗號來分隔。 此配置是可選的。 在輸入這些欄位時，在訊息準備階段期間，Adobe Campaign會檢查輸入的位址是否有效。 此操作模式可確保不使用任何可能觸發傳遞性問題的地址。 必須在傳送伺服器上設定傳送位址。

* **可傳遞性**

   此ID由支援提供。 傳送能力報表必須正確運作。

* **傳送參數**

   Adobe Campaign會從開始日期開始傳送訊息。 該 **[!UICONTROL Message delivery duration]** 欄位允許您指定消息的發送期間。

   此欄 **[!UICONTROL Online resources validity duration]** 位用於上傳的資源，主要用於鏡像頁面和影像。 本頁上的資源在限定時間內有效（以節省磁碟空間）。

* **重試次數**

   暫時未傳送的訊息可能會自動重試。 此部分指示在發送開始後一天應執行多少次重試(重試&#x200B;**次數**)和兩次重試之間的最小延遲(**重試週期**)。

   依預設，會為第一天排程5次重試，最低間隔為1小時，分佈在一天的24小時內。 在此之後，每天會設定一次重試，直到交貨截止日期（在章節中定義） **[!UICONTROL Delivery parameters]** 為止。

* **電子郵件隔離參數**

   在欄位 **[!UICONTROL Time between two significant errors]** 中輸入值，以定義應用程式在發生故障時，在增加錯誤計數器之前等待的時間。 預設值： **1d」**，為期1天。

   到達值 **[!UICONTROL Maximum number of errors before quarantine]** 後，會隔離電子郵件地址。 預設值： **"5"**:地址將在第六個錯誤時被隔離。 這表示該連絡人將自動排除在後續傳送之外。

**相關主題**:

[瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)

## 電子郵件傳送帳戶 {#email-routing-accounts}

預設 **[!UICONTROL Integrated email routing]** 會提供外部帳戶。 它包含允許應用程式傳送電子郵件的技術參數。

![](assets/channels_2.png)

帳戶類型必須一律設 **[!UICONTROL Routing]**&#x200B;定為、渠道 **[!UICONTROL Email]** 和傳送模式設定為 **[!UICONTROL Bulk delivery]**。

**相關主題**:

[外部帳戶](../../administration/using/external-accounts.md)

## 電子郵件處理規則 {#email-processing-rules}

這些規則包含可由遠端伺服器傳回的字元字串清單，可讓您限定錯誤(**Hard**、 **Soft** 或 **Ignored**)。

預設規則如下：

**彈回郵件**

當電子郵件失敗時，遠端訊息伺服器會將彈回錯誤訊息傳回至應用程式設定中指定的位址。 Adobe Campaign會將每個彈回郵件的內容與規則清單中的字串進行比較，然後指派其中一種錯誤類型。

使用者可建立自己的規則。

>[!CAUTION]
>
>當匯入套件時，以及透過「更新以進行傳遞性 **」工作流程更新資料時** ，會覆寫使用者建立的規則。

**管理電子郵件網域**

網域管理規則用於規範特定網域的傳出電子郵件流程。 他們會取樣彈回訊息，並在適當時封鎖傳送。 Adobe Campaign傳訊伺服器會套用網域的特定規則，然後套用規則清單中星號所代表之一般案例規則。 Hotmail和MSN網域的規則預設可在Adobe Campaign中使用。

要配置域管理規則，只需設定閾值並選擇某些SMTP參數。 閾 **值** (Threshold)是計算為錯誤百分比的限制，超過該百分比，將阻止指向特定域的所有消息。

例如，一般情況下，至少300則訊息，如果錯誤率達到90%，則會封鎖3小時的電子郵件傳送。

SMTP參 **數用作** （應用於阻止規則）的篩選器。

* 您可以選擇是否激活某些標準和加密密鑰來檢查域名，如 **Sender ID**、 **DomainKeys**、 **DKIM**&#x200B;和 **** S/MIME Juckint。
* **SMTP中繼**:用於為特定域配置中繼伺服器的IP地址和埠。

**MX管理**

每個規則都會定義MX的位址遮色片。 因此，任何名稱符合此遮色片名稱的MX都符合資格。 遮色片可包含"*"和"?" 一般字元。

例如，以下地址：

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

與下列遮色片相容：

* *.yahoo.com
* ?.mx.yahoo.com

這些規則依序套用：套用其MX遮色片與目標MX相容的第一個規則。

每個規則可使用下列參數：

* **[!UICONTROL Range of IDs]**:此選項可讓您指出套用規則的識別碼範圍(publicId)。 您可以指定：

   * 數字：該規則僅適用於此publicId。
   * 數字範圍（數字1-數字2）:該規則將適用於這兩個數字之間的所有publicId。
   如果欄位為空，則規則會套用至所有ID。

* **[!UICONTROL Shared]**:此選項表示每小時和連線的最多訊息數量適用於所有連結至此規則的MX。
* **[!UICONTROL Maximum number of connections]**:從指定位址同時連線至MX的最大數目。
* **最大消息數**:一個連接可發送的最大消息數。 在此數量後，將關閉連接並重新開啟新連接。
* **[!UICONTROL Messages per hour]**:MX可透過指定位址在一小時內傳送的訊息數上限。

>[!CAUTION]
>
>* 如果參數已變更，則必須重新啟動傳送伺服器(MTA)。
>* 管理規則的修改或建立僅限專業使用者。
>



## 電子郵件屬性清單 {#list-of-email-properties}

本節詳細說明電子郵件或電子郵件範本屬性畫面中可用的參 [數清單](../../start/using/about-templates.md)。

>[!NOTE]
>
>有些參數只適用於範本。 您可存取的參 [數取決於您的權限](../../administration/using/users-management.md)。

若要編輯電子郵件或電子郵件範本的屬性，請使用按 **[!UICONTROL Edit properties]** 鈕。

![](assets/delivery_options_1.png)

### 一般參數 {#general-parameters}

在電子郵件參數畫面頂端，使用和欄位識別 **[!UICONTROL Label]** 電子 **[!UICONTROL ID]** 郵件。 此資訊會顯示在介面中，但訊息收件者看不到。

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>ID必須是唯一的。

欄位 **[!UICONTROL Brand]** 可讓您選取連結至傳送的品牌。 有關使用和設定品牌的詳細資訊，請參閱「品 [牌](../../administration/using/branding.md) 」一節。

欄位 **[!UICONTROL Campaign]** 可讓您輸入連結至電子郵件的促銷活動。

您也可以在對應欄 **[!UICONTROL Description]** 位中新增影像，並編輯清單中電子郵件縮圖上顯示的影像。

### 傳送參數 {#sending-parameters}

此 **[!UICONTROL Send]** 區段僅適用於電子郵件範本。 它包含下列參數：

#### 重試參數 {#retries-parameters}

暫時未傳送的訊息可能會自動重試。 此部分指示在發送開始( **[!UICONTROL Max. number of retries]** )後應執行多少次重試，以及兩次重試之間的最小延遲( **[!UICONTROL Retry period]** )。

依預設，會為第一天排程5次重試，最低間隔為1小時，分佈在一天的24小時內。 在此之後，每天會設定一次重試，直到交貨期限為止(在有效期間參數部分中 [定義)](#validity-period-parameters) 。

可以全域變更重試次數（請連絡您的Adobe技術管理員），或針對每個傳送或傳送範本變更重試次數

#### 電子郵件格式參數 {#email-format-parameters}

您可以設定要傳送的電子郵件格式。 有三種可用選項：

* **使用收件者偏好設定** （預設模式）:消息格式根據儲存在收件人配置檔案中的資料定義，並預設儲存在 **Email format** 欄位(@emailFormat)中。 如果收件者希望以特定格式接收訊息，則此格式為傳送的格式。 如果欄位未完成，則會傳送多部分替代訊息（請參閱下面）。
* **讓收件者郵件用戶端選擇最適合的格式（多部分替代）**:消息包含兩種格式：文字和HTML。 接收時顯示的格式取決於收件人的郵件軟體（多部分替代）的配置。

   >[!CAUTION]
   >
   >此選項包含兩個版本的訊息。 因此，它會影響傳送吞吐量，因為消息大小較大。

* **以文字格式傳送所有訊息**:訊息會以文字格式傳送。 HTML格式不會傳送，但僅當收件者按一下訊息中的連結時，才會用於鏡像頁面。

#### SMTP測試模式 {#smtp-test-mode}

此選 **[!UICONTROL Enable SMTP test mode]** 項允許您測試通過SMTP連接發送的電子郵件，而不實際發送郵件。
這些消息將被處理，直到與SMTP伺服器建立連接為止，但不會發送這些消息。

![](assets/smtp-test-mode.png)

此選項適用於電子郵件和電子郵件範本。

如果為電子郵件模板啟用SMTP測試模式選項，則根據此模板建立的所有電子郵件都將啟用此選項。

>[!CAUTION]
>
>如果為電子郵件啟用此選項，則在取消勾選該選項之前，不會傳送任何訊息。
>電子郵件或電子郵件範本控制面板中會顯示警告。

有關配置SMTP的詳細資訊，請參閱「電子郵 [件SMTP參數清單」部分](#list-of-email-smtp-parameters) 。

### 有效期參數 {#validity-period-parameters}

該 **[!UICONTROL Validity]** 部分包含以下參數：

* **[!UICONTROL Explicitly set validity dates]**:取消選中此框後，您必須在和欄位中輸入 **[!UICONTROL Delivery duration]** 持續時間 **[!UICONTROL Resource validity limit]** 。 如果您想要定義特定的時間和日期，請勾選此方塊。
* **[!UICONTROL Delivery duration]**:Adobe Campaign會從開始日期開始傳送訊息。 此欄位允許您指定消息的發送期間。
* **[!UICONTROL Resource validity duration]**:此欄位用於上傳的資源，主要用於鏡像頁面和影像。 本頁上的資源在限定時間內有效（以節省磁碟空間）。
* **[!UICONTROL Mirror page management]**:鏡像頁是可通過Web瀏覽器線上上訪問的HTML頁。 其內容與電子郵件內容相同。 預設情況下，如果連結插入郵件內容中，將生成鏡像頁。 此欄位可讓您修改產生此頁面的方式：

   >[!CAUTION]
   >
   >必須為要建立鏡像頁面的電子郵件定義了HTML內容。

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** （預設模式）:如果連結插入郵件內容，則生成鏡像頁。
   * **強制生成鏡像頁**:即使消息中未插入到鏡像頁的連結，也會建立鏡像頁。
   * **不生成鏡像頁**:不會產生任何鏡像頁面，即使連結位於訊息中亦然。
   * **生成僅使用消息ID可訪問的鏡像頁**:此選項可讓您在傳送記錄視窗中存取包含個人化資訊的鏡像頁面內容。

>[!NOTE]
>
>和 **[!UICONTROL Explicitly set validity dates]** 參 **[!UICONTROL Delivery duration]** 數不適用於事務性消息。 有關交易式訊息的詳細資訊，請 [參閱本節](../../channels/using/about-transactional-messaging.md)。

### 追蹤參數 {#tracking-parameters}

該 **[!UICONTROL Tracking]** 部分包含以下參數：

* **[!UICONTROL Activate tracking]**:可讓您啟用／停用訊息URL追蹤。 若要管理每個訊息URL的追蹤，請使用「電子郵 **[!UICONTROL Links]** 件設計器」動作列中的圖示。 請參 [閱關於追蹤的URL](../../designing/using/links.md#about-tracked-urls)。
* **[!UICONTROL Tracking validity limit]**:可讓您定義在URL上啟動追蹤的持續時間。
* **[!UICONTROL Substitution URL for expired URLs]**:您可以輸入URL至追蹤過期後將顯示的網頁。

### 高級參數 {#advanced-parameters}

該節 **[!UICONTROL Advanced parameters]** 包含多個參數。

前兩個欄位可讓您輸入必要資訊，以製作電子郵件標題（回覆位址和回覆位址文字）。 這些資訊可以個人化。 若要這麼做，請按一下將要變更之欄位右側的按鈕，然後新增個人化欄位。 插入和使用個人化欄位在插入個人化欄 [位區段中有詳細說明](../../designing/using/personalization.md#inserting-a-personalization-field) 。

#### 目標內容 {#target-context}

定位內容可讓您定義一組表格，這些表格將用於電子郵件定位（在對象定義畫面中）和個人化（在HTML內容編輯器中定義個人化欄位）。

#### 路由 {#routing}

此欄位指明所使用的路由模式。 它參考外部帳戶。 例如，如果您想要使用包含特定品牌設定的外部帳戶，則可使用此帳戶。

>[!NOTE]
>
>外部帳戶可透過「管理 **&gt;應用程式** 設定 **&gt;外部帳** 戶」功能表存取 **** 。

#### 準備 {#preparation}

「批准消息」部分中將詳細 [介紹準備消息](../../sending/using/preparing-the-send.md) 。

* **[!UICONTROL Typology]**:在傳送之前，必須準備訊息，才能驗證內容和設定。 在準備階段期間應用的驗證規則以類型學 **定義**。 例如，對於電子郵件，準備包括檢查主題、URL和影像等。 選擇要在此欄位中應用的類型學。

   >[!NOTE]
   >
   >「類型」區段中顯示了可以通 **[!UICONTROL Administration]** 過&gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** 菜單訪問的 [類型](../../administration/using/about-typology-rules.md) 。

* **[!UICONTROL Compute the label during delivery preparation]**:可讓您使用個人化欄位、內容區塊和動態文字，在訊息準備階段計算電子郵件的標籤值。

   您也可以使用已宣告至工作流程外部訊號活動的事件變數來個人化傳送標籤。 如需詳細資訊，請參閱[本小節](../../automating/using/calling-a-workflow-with-external-parameters.md)。

* **[!UICONTROL Save SQL queries in the log]**:此選項允許您在準備階段期間在日誌中添加SQL查詢日誌。

### 電子郵件SMTP參數清單 {#list-of-email-smtp-parameters}

該 **[!UICONTROL SMTP]** 部分包含以下參數：

* **[!UICONTROL Character encoding]**:如果 **[!UICONTROL Force encoding]** 要強制進行消息編碼，請選中該框，然後選擇要使用的編碼。
* **[!UICONTROL Bounce mails]**:根據預設，彈回郵件會在平台的錯誤收件匣(定義於 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt;畫面)中收到 **[!UICONTROL Configuration]** 。 要定義電子郵件的特定錯誤地址，請在欄位中輸入該 **[!UICONTROL Error address]** 地址。
* **[!UICONTROL Additional SMTP headers]**:此選項允許在消息中添加其他SMTP標頭。 在欄位中輸入的 **[!UICONTROL Headers]** 指令碼必須參照每行一個標題，其形式 **為name:value**。 如有必要，值會自動編碼。

   >[!CAUTION]
   >
   >為高級用戶保留添加用於插入其他SMTP標頭的指令碼。 此指令碼的語法必須符合以下內容類型的要求：沒有未使用的空間，沒有空行等。

### 訪問授權參數清單 {#list-of-access-authorization-parameters}

該 **[!UICONTROL Access authorization]** 部分包含以下參數：

* 欄位 **[!UICONTROL Organizational unit]** 可讓您限制特定使用者存取此電子郵件。 與指定設備或父設備關聯的用戶將擁有此電子郵件的讀寫權限。 與子設備關聯的用戶將只具有對此電子郵件的讀取訪問權限。

   >[!NOTE]
   >
   >您可以透過「管理&gt;使用者與 **安全性** 」功 **能表來設定組織單位** 。

* 自 **[!UICONTROL Created by]**&#x200B;動完 **[!UICONTROL Created]**&#x200B;成、 **[!UICONTROL Modified by]** 和 **[!UICONTROL Last modified]** 欄位。

## 封存電子郵件 {#archiving-emails}

您可以設定Adobe Campaign，以保留從您的平台傳送的電子郵件副本。

但是，Adobe Campaign本身並不管理已封存的檔案。 它確實可讓您將您選擇的訊息傳送至專用位址，以便使用外部系統處理及封存。

在傳送範本中啟動時，此功能可讓您傳送對應已傳送訊息的精確副本至您必須指定的密件副本電子郵件地址（傳送收件者不可見）。

### 建議與限制 {#recommendations-and-limitations}

* 此功能為選擇性。 請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。
* 您只能使用一個密件副本電子郵件地址。
* 只會將成功傳送的電子郵件納入考量。 彈回數不是。
* 出於隱私原因，密件副本電子郵件必須由能夠安全地儲存個人識別資訊(PII)的歸檔系統處理。
* 建立新的傳送範本時，即使已購買選項，依預設不會啟用電子郵件密件副本。 您必須在每個要使用的傳送範本中手動啟用它。

### 啟動電子郵件封存 {#activating-email-archiving}

電子郵件密件副本會透過專 [屬選項](../../start/using/about-templates.md)，在電子郵件範本中啟動：

1. 前往「 **資源** &gt;范 **本** &gt; **傳送範本**」。
1. 複製現成可用的范 **[!UICONTROL Send via email]** 本。
1. 選擇複製的模板。
1. 按一下 **[!UICONTROL Edit properties]** 按鈕以編輯範本的屬性。
1. 展開該 **[!UICONTROL Send]** 部分。
1. 核取方 **[!UICONTROL Archive emails]** 塊，以根據此範本保留每個傳送之所有已傳送訊息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果開啟並點進傳送至密件副本位址的電子郵件，則會在傳送分析中考慮 **[!UICONTROL Total opens]** 這 **[!UICONTROL Clicks]** 一點，這可能會造成一些誤算。

