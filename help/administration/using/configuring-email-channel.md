---
title: 在 Adobe Campaign Standard 中設定電子郵件通道
description: 瞭解如何在Adobe Campaign Standard配置電子郵件通道
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 76d70fd1-dd93-4a6d-b18c-96ebe5a27a7d
source-git-commit: a1b947acf70803a7350dd626e697318e0ed35f26
workflow-type: tm+mt
source-wordcount: '2681'
ht-degree: 62%

---

# 設定電子郵件頻道{#configuring-email-channel}

身為 Campaign [管理員](../../administration/using/users-management.md#functional-administrators)，您可以進行電子郵件通道設定。這些進階設定包含一般電子郵件通道參數、電子郵件路由帳戶、電子郵件處理規則和電子郵件屬性。在此頁上，瞭解如何編輯常規電子郵件和發送參數的預設值。

## 電子郵件通道參數 {#email-channel-parameters}

電子郵件設定畫面可用於定義電子郵件通道的參數。管理員可以存取「**[!UICONTROL Administration]> [!UICONTROL Channels] > [!UICONTROL Email] >[!UICONTROL Configuration]**」功能表中的這些設定。

![](assets/channels_1.png)

* **授權遮罩欄位**

   **[!UICONTROL Header parameters of sent emails]** 小節列出您可用於傳送電子郵件給收件者（寄件者地址），並讓他們傳回自動回覆的電子郵件地址，例如非同步退件、休假回覆等。（錯誤地址）。Adobe Campaign 會檢查所輸入的地址在訊息準備階段期間是否有效。此操作模式可確保不使用任何可能觸發傳送能力問題的地址。
   * 寄件者和錯誤位址皆由 Adobe 設定。那些欄位不可為空白。
   * 您無法編輯那些欄位。若要更新地址，請聯絡 Adobe 客戶服務團隊。
   * 要添加其他地址，可以使用 [市場活動控制面板](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html?lang=zh-Hant) 設定新子域，或與Adobe客戶服務團隊聯繫。 請注意，如果使用了多個蒙版，則用逗號分隔。
   * 使用星號（例如 *@yourdomain.com）來設定地址是很理想的作法：這可讓您使用以子網域名稱結尾的任何地址。

* **傳送能力**

   **[!UICONTROL Delivery reports ID]** 是由 Adobe 客戶服務團隊提供。其會使用技術傳送能力報告中使用的傳送能力 ID 來識別每個執行個體。
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **傳送參數**

   Adobe Campaign 會從開始日期開始傳送訊息。

   當傳遞中的郵件由於臨時錯誤或軟彈回而被拒絕時，市場活動將重試每天發送此郵件。 使用 **[!UICONTROL Message delivery duration]** 欄位以指定重試期間的時間範圍。

   >[!IMPORTANT]
   >
   >**現在，只有當設定為 3.5 天或更短時間時，才會在 Campaign 中使用此參數。** 如果您定義的值超過　3.5　天，則不會考慮該值。

   **[!UICONTROL Online resources validity duration]** 欄位是用於上傳的資源，主要用於鏡像頁面和影像。本頁上的資源在限定時間內有效（以節省磁碟空間）。

* **重試次數**

   暫時未傳送的郵件可能會自動重試。如需詳細資訊，請參閱[傳送暫時失敗後重試](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

   >[!IMPORTANT]
   >
   >要執行的最大重試次數和兩次重試之間的最小延遲現在取決於IP在給定域中的歷史和當前執行情況。 的 **[!UICONTROL Retry period]** 和 **[!UICONTROL Number of retries]** 將忽略「市場活動」中的設定。

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **電子郵件隔離參數**

   在欄位 **[!UICONTROL Time between two significant errors]** 中輸入值，以定義應用程式在發生軟退信失敗時增加錯誤計數器之前等待的時間。1 天的預設值是 **&quot;1d&quot;**。

   達到值 **[!UICONTROL Maximum number of errors before quarantine]** 時，則會隔離電子郵件地址。預設值為 **&quot;5&quot;**:地址在第五個錯誤時被隔離。 這表示該在後續傳送時將自動排除該聯絡人。
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   如需隔離的詳細資訊，請參閱[瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)。

## 電子郵件路由帳戶 {#email-routing-accounts}

預設會提供 **[!UICONTROL Integrated email routing]** 外部帳戶。其包含可讓應用程式傳送電子郵件的技術參數。

![](assets/channels_2.png)

帳戶類型必須一律設定為 **[!UICONTROL Routing]**、通道設定為 **[!UICONTROL Email]**，而且傳送模式設定為 **[!UICONTROL Bulk delivery]**。

**相關主題**：

[外部帳戶](../../administration/using/external-accounts.md)

## 電子郵件處理規則 {#email-processing-rules}

管理員 **[!UICONTROL Email processing rules]** 可透過功能表存取 **[!UICONTROL Administration > Channels > Email]**。

>[!IMPORTANT]
>
>電子郵件域和MX規則現在將自動管理<!--by the Adobe Campaign Enhanced MTA (Message Transfer Agent)--> 不能更改。

* **DKIM(DomainKeys Indifed Mail)** 對所有域的所有郵件都執行電子郵件身份驗證簽名。 它不用 **發件人ID**。 **域密鑰**&#x200B;或 **S/MIME**。
* MX規則根據您自己的歷史電子郵件信譽以及您發送電子郵件的域的即時反饋，按域自動定制吞吐量。

<!--Note that the email domains and the MX rules are now managed by the Adobe Campaign Enhanced MTA:
* **DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.
* The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

### 退回郵件 {#bounce-mails}

非同步退信仍由 Campaign inMail 程序透過 **[!UICONTROL Bounce mails]** 規則來限定。

這些規則包含可由遠端伺服器傳回的字元字串清單，可讓您限定錯誤（**Hard**、**Soft** 或 **Ignored**）。

>[!IMPORTANT]
>
>同步傳遞失敗錯誤消息現在由Adobe Campaign增強型MTA進行鑑定，它確定退貨類型和鑑定，並將該資訊發回市場活動。

有關退信限定的詳細資訊，請參閱[本節](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)。

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## 電子郵件屬性清單 {#list-of-email-properties}

本節詳細說明電子郵件或電子郵件範本之屬性畫面中可用的參數清單。

>[!NOTE]
>
>一些參數只適用於範本。您可以存取的參數[視於您的權限而定](../../administration/using/users-management.md)。

若要編輯電子郵件或電子郵件範本的屬性，請使用 **[!UICONTROL Edit properties]** 按鈕。

![](assets/delivery_options_1.png)

### 一般參數 {#general-parameters}

在電子郵件參數畫面頂端，使用 **[!UICONTROL Label]** 及 **[!UICONTROL ID]** 欄位來視別電子郵件。此資訊會顯示在介面中，但郵件收件者看不到。

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>ID 必須是唯一的。

使用 **[!UICONTROL Brand]** 欄位以選擇連結到交貨的品牌。 有關使用和設定品牌的詳細資訊，請參閱[「品牌](../../administration/using/branding.md)」一節。

在 **[!UICONTROL Campaign]** 欄位中，輸入與電子郵件關聯的市場活動。

您也可以在對應欄位中新增 **[!UICONTROL Description]**，並編輯清單中電子郵件縮圖上顯示的影像。

### 傳送參數 {#sending-parameters}

**[!UICONTROL Send]** 區段僅適用於電子郵件範本。其包含下列參數：

#### 重試參數 {#retries-parameters}

暫時未傳送的郵件可能會自動重試。如需詳細資訊，請參閱[傳送暫時失敗後重試](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

>[!IMPORTANT]
>
>重試之間的最小延遲和要執行的最大重試次數現在取決於IP在給定域中的歷史和當前執行情況。 的 **[!UICONTROL Retry period]** 和 **[!UICONTROL Max. number of retries]** 將忽略「市場活動」中的設定。

在 Campaign 中設定的&#x200B;**傳送持續期間設定**（在[有效期間參數](#validity-period-parameters)區段中定義）**仍將接受，但最多只能接受　3.5　天**。此時，重試佇列中的任何郵件都會從佇列中移除，並以退信的形式傳回。如需傳送失敗的詳細資訊，請參閱[本節](../../sending/using/understanding-delivery-failures.md#about-delivery-failures)。

#### 電子郵件格式參數 {#email-format-parameters}

您可以設定要傳送的電子郵件格式。有三種可用選項：

* **使用收件者偏好設定**（預設模式）：郵件格式的定義是根據儲存在收件人設定檔中的資料定義，並預設會儲存在 **Email format** 欄位　(@emailFormat)　中。如果收件者希望以特定格式接收郵件，則此格式為傳送的格式。如果欄位尚未完成，則會傳送替代的多重部分郵件（請參閱下文）。
* **讓收件者郵件用戶端選取最適合的格式（替代的多重部分）**：郵件包含兩種格式：文字和　HTML。接收時顯示的格式視收件人的郵件軟體（替代的多重部分）的設定而定。

   >[!IMPORTANT]
   >
   >此選項包含兩個版本的郵件。因此，它會影響傳送輸送量，因為郵件大小較大。

* **以文字格式傳送所有郵件**：郵件會以文字格式傳送。將不會傳送　HTML　格式，但只有當收件者按一下郵件中的連結時，才會用於鏡像頁面。

#### SMTP　測試模式 {#smtp-test-mode}

使用 **[!UICONTROL Enable SMTP test mode]** test通過SMTP連接發送電子郵件而不實際發送郵件。 處理傳遞直到連線到 SMTP 伺服器，但不傳送：對於傳遞的每個收件者，Campaign 會連線到 SMTP 提供者伺服器，執行 SMTP RCPT TO 命令，並在 SMTP DATA 命令之前關閉連線。

![](assets/smtp-test-mode.png)

此選項適用於電子郵件和電子郵件範本。

如果為電子郵件範本啟用　SMTP　測試模式選項，則根據此模板建立的所有電子郵件都將啟用此選項。

>[!IMPORTANT]
>
>如果為電子郵件啟用此選項，則在取消核取該選項之前，不會傳送任何郵件。
>電子郵件或電子郵件範本控制面板中會顯示警告。

有關設定　SMTP　的詳細資訊，請參閱[電子郵件　SMTP　參數清單](#list-of-email-smtp-parameters)小節。

### 有效期間參數 {#validity-period-parameters}

**[!UICONTROL Validity period]** 一節包含下列參數：

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**：取消核取此方塊時，您必須在 **[!UICONTROL Delivery duration]** 及 **[!UICONTROL Resource validity limit]** 欄位中輸入持續時間。

   如果您想要定義特定的時間和日期，請核取此方塊。

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**：Adobe Campaign　會從開始日期開始傳送訊息。使用此欄位可指定消息可發送的期間。

   >[!IMPORTANT]
   >
   >**您必須定義最多　3.5　天的值。** 如果設定的值大於3.5天，則不會將其考慮在內。
   >
   >**[!UICONTROL Delivery duration]** 參數不適用於異動訊息。如需異動訊息的詳細資訊，請參閱[本節](../../channels/using/getting-started-with-transactional-msg.md)。

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**：此欄位是用於上傳的資源，主要用於鏡像頁面和影像。本頁上的資源在限定時間內有效（以節省磁碟空間）。
* **[!UICONTROL Mirror page management]**：鏡像頁面是可透過網頁瀏覽器線上存取的　HTML　頁面。其內容與電子郵件內容相同。依預設，如果將連結插入郵件內容中，則會產生鏡像頁面。使用此欄位可修改此頁的生成方式：

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]**（預設模式）：如果將連結插入郵件內容中，則會產生鏡像頁面。
   * **強制產生鏡像頁面**：即使未將任何鏡像頁面的連結插入郵件中，也會建立鏡像頁面。
   * **不要產生鏡像頁面**：不會產生任何鏡像頁面，即使郵件中已經有連結亦然。
   * **產生僅可使用郵件　ID　存取的鏡像頁面**：此選項可讓您在傳送記錄視窗中存取包含個人化資訊的鏡像頁面內容。

   >[!IMPORTANT]
   >
   >僅當為電子郵件定義了HTML內容時，才會生成鏡像頁面。


### 追蹤參數 {#tracking-parameters}

**[!UICONTROL Tracking]** 一節包含下列參數：

* **[!UICONTROL Activate tracking]**:使用此選項可激活/停用消息URL跟蹤。 若要管理每個郵件 URL 的追蹤，請使用「電子郵件設計工具」動作列中的 **[!UICONTROL Links]** 圖示。請參閱[關於追蹤的 URL](../../designing/using/links.md#about-tracked-urls)。
* **[!UICONTROL Tracking validity limit]**:使用此選項可定義在URL上激活跟蹤的持續時間。
* **[!UICONTROL Substitution URL for expired URLs]**:使用此選項可輸入回退網頁的URL:跟蹤過期後，將顯示它。
* **[!UICONTROL Use tracking pixel at the top of email]**:使用此選項可移動電子郵件頂部而不是底部的跟蹤像素。 預設情況下，此像素位於電子郵件的底部。 如果您發送大郵件，請考慮將此像素移到電子郵件頂部而不是底部以改進開啟的跟蹤 — 否則，某些電子郵件提供商可能會剪切跟蹤像素。

### 高級參數 {#advanced-parameters}

**[!UICONTROL Advanced parameters]** 一節包含多個參數。

第一個欄位可讓您輸入必要資訊，以製作電子郵件標題。您可以在此處管理回覆位址和文字，以及寄件者地址（其中會填入「寄件者：」欄位）。可將此資訊加以個人化。

按一下將要變更之欄位右側的按鈕，然後新增個人化欄位、內容區塊或動態文字。

![](assets/advancedparameters.png)

[個人化電子郵件內容](../../designing/using/personalization.md)文件中會詳細說明插入及使用個人化內容。

#### 目標內容 {#target-context}

使用目標上下文定義一組表，這些表將用於電子郵件目標（在受眾定義螢幕中）和個性化設定(在HTML內容編輯器中定義個性化欄位)。

#### 路由 {#routing}

此欄位會指出所使用的路由模式。其會參考外部帳戶。例如，如果您想要使用包含特定品牌設定的外部帳戶，則可使用此帳戶。

>[!NOTE]
>
>可透過「**管理** > **應用程式設定** > **外部帳戶**」功能表存取外部帳戶。

#### 準備 {#preparation}

[核准郵件](../../sending/using/preparing-the-send.md)一節中會詳細說明準備郵件。

* **[!UICONTROL Typology]**：在任何傳送作業之前，必須準備郵件，才能驗證內容和設定。在&#x200B;**類型**&#x200B;中定義準備階段期間，會套用驗證規則。例如，對於電子郵件，準備涉及檢查主題、URL 和影像等。選取要在此欄位套用的類型。

   >[!NOTE]
   >
   >可透過「**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]**」功能表存取的類型，會顯示在[本節](../../sending/using/about-typology-rules.md)中。

* **[!UICONTROL Compute the label during delivery preparation]**:使用此選項可在消息準備階段使用個性化欄位、內容塊和動態文本計算電子郵件的標籤值。

   也可以使用已宣告至工作流程外部訊號活動的事件變數，以個人化傳送標籤。如需詳細資訊，請參閱[本區段](../../automating/using/calling-a-workflow-with-external-parameters.md)。

* **[!UICONTROL Save SQL queries in the log]**:在準備階段，使用此選項將SQL查詢日誌添加到日誌中。

#### 校樣設定 {#proof-settings}

在本節中，可以將預設前置詞配置為在證明消息的主題行中使用。 瞭解有關中的校樣的詳細資訊 [此部分](../../sending/using/sending-proofs.md)。

### 電子郵件 SMTP 參數清單 {#list-of-email-smtp-parameters}

**[!UICONTROL SMTP]** 一節包含下列參數：

* **[!UICONTROL Character encoding]**：如果您要強制對郵件編碼，請核取 **[!UICONTROL Force encoding]** 方塊，然後選取您要使用的編碼。
* **[!UICONTROL Bounce mails]**：依預設，會在平台的錯誤收件匣中接收退信郵件（在「**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]**」畫面中定義）。若要定義電子郵件的特定錯誤地址，請在　**[!UICONTROL Error address]**　欄位中輸入該地址。
* **[!UICONTROL Additional SMTP headers]**：此選項可將其他　SMTP　標頭新增至您的郵件中。在　**[!UICONTROL Headers]**　欄位中輸入的指令碼必須參照每行一個標題，其形式為 **name:value**。如有必要，會自動對值編碼。

   >[!IMPORTANT]
   >
   >會為進階使用者保留新增指令碼，以便插入其他 SMTP 標題。此指令碼的語法必須符合以下內容類型的要求：沒有未使用的空間，沒有空行等。

### 存取授權參數清單 {#list-of-access-authorization-parameters}

**[!UICONTROL Access authorization]** 一節包含下列參數：

* 的 **[!UICONTROL Organizational unit]** 欄位用於限制特定用戶對此電子郵件的訪問。 與指定單位或上層單位相關聯的使用者會擁有此電子郵件的讀寫存取權限。與下層單位相關聯的使用者將只具有對此電子郵件的讀取存取權限。

   >[!NOTE]
   >
   >您可以透過「**管理** > **使用者與安全性**」功能表設定組織單位。

* 會自動完成 **[!UICONTROL Created by]**、**[!UICONTROL Created]**、**[!UICONTROL Modified by]** 及 **[!UICONTROL Last modified]** 欄位。

## 舊設定 {#legacy-settings}

如果 **不** 運行最新版本的市場活動，下面描述的參數和UI部分仍然適用於您。

### 重試次數 {#legacy-retries}

的 **[!UICONTROL Retries]** 的 [配置菜單](#email-channel-parameters) 在 [發送參數](#retries-parameters) 電子郵件屬性的值指示在開始發送後一天應執行多少次重試(**[!UICONTROL Number of retries]** / **[!UICONTROL Max. number of retries]**)和重試間的最小延遲(**[!UICONTROL Retry period]**)。

可以全局更改重試次數(與Adobe技術管理員聯繫)或每個交付或交付模板。

預設情況下，為第一天安排五次重試，最小時間間隔為1小時，在一天的24小時內分佈。 每天一次重試的程式設定在此之後，直到交貨截止日期為止，該截止日期在 **[!UICONTROL Delivery parameters]** 的下界 **[!UICONTROL Configuration]** ，或 **[!UICONTROL Validity period]** 在交貨層(請參閱 [交貨期](#legacy-delivery-duration) )。

### 傳遞期間 {#legacy-delivery-duration}

使用 **[!UICONTROL Message delivery duration]** 參數 [配置菜單](#email-channel-parameters) 指定傳遞中遇到臨時錯誤或軟彈回的任何消息將重試的時間範圍。

使用 **[!UICONTROL Delivery duration]** 或 **[!UICONTROL Validity limit for sending messages]** 參數 [有效期參數](#validity-period-parameters) 的子菜單。

### 電子郵件處理規則 {#legacy-email-processing-rules}

的 **[!UICONTROL MX management]**。 **[!UICONTROL Bounce mails]** 和 **[!UICONTROL Domain management]** 管理員可通過 **[!UICONTROL Administration > Channels > Email > Email processing rules]** 的子菜單。 [了解更多](#email-processing-rules)。

### 退回郵件資格 {#legacy-bounce-mail-qualification}

要列出各種邊界及其關聯的錯誤類型和原因，請按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**。

退貨可以具有以下資格狀態：

* **[!UICONTROL To qualify]**:郵寄郵件需要經過鑑定。 必須由交付能力團隊進行鑑定，以確保平台交付能力正確運行。 只要不合格，就不會使用退信郵件來豐富電子郵件處理規則清單。
* **[!UICONTROL Keep]**:郵件是合格的，由 **更新可交付性** 將工作流與現有電子郵件處理規則進行比較並豐富清單。
* **[!UICONTROL Ignore]**:郵寄郵件已經合格，但不會被 **更新可交付性** 工作流。 因此它不會被發送到客戶端實例。

>[!NOTE]
>
>在ISP停機時，通過Campaign發送的電子郵件將被錯誤地標籤為退貨。 要更正此問題，您需要更新退貨資格。 [了解更多](../../administration/using/update-bounce-qualification.md)。

<!--Bounces are qualified through the **[!UICONTROL Bounce mails]** processing rule. For more on accessing this rule, refer to this [section](#legacy-bounce-mail-qualification).-->

### 已交付指標報告 {#legacy-delivered-status-report}

在 **[!UICONTROL Summary]** 查看每個消息， **[!UICONTROL Delivered]** 隨著軟和硬邊界返回報告，在整個交貨的有效期內，百分比逐漸增加。

軟彈跳消息顯示為 **[!UICONTROL Failed]** 在交貨後的第一天。 每天重試這些消息，直到傳遞的有效期結束。
