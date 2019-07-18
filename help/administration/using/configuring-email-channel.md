---
title: 設定電子郵件頻道
seo-title: 設定電子郵件頻道
description: 設定電子郵件頻道
seo-description: 瞭解如何設定電子郵件渠道。
page-status-flag: 從未啓動
uuid: 9fddb655-b445-41f3-9b02-5d356 fc88 aa1
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 設定頻道
discoiquuid: 3752d41f-8c59-4fad-b30 f-e98 e09 cd74 a8
context-tags: extAccountMail，概觀；EmailConfig，main；規則集，概觀；傳送，屬性，開啓
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring email channel{#configuring-email-channel}

## Email channel parameters {#email-channel-parameters}

電子郵件設定畫面可讓您定義電子郵件渠道的參數。

![](assets/channels_1.png)

* **傳送電子郵件的頁首參數**

   In this section, you can specify the **[!UICONTROL masks]** authorized for the sender address and the error address. 如有必要，這些遮色片可使用逗號分隔。此設定為選用。輸入這些欄位時，在訊息準備階段期間，Adobe Campaign會檢查輸入的位址是否有效。此作業模式可確保不會使用任何可能觸發遞送功能的位址。傳送地址必須在傳送伺服器上設定。

* **可讀性**

   此ID由支援提供。傳送能力報告必須正確運作。

* **傳送參數**

   Adobe Campaign會在開始日期時傳送訊息。**[!UICONTROL Message delivery duration]** 欄位可讓您指定訊息可傳送的時間長度。

   **[!UICONTROL Online resources validity duration]** 欄位用於上傳的資源，主要用於鏡像頁面和影像。此頁面上的資源在限定時間內有效(儲存磁碟空間)。

* **重試**

   暫時未傳送的訊息會受到自動重試。This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**).

   依預設，會排程五次重試，最低間隔為一小時，在24小時內分散。One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **電子郵件隔離參數**

   **[!UICONTROL Time between two significant errors]** 在欄位中輸入值，以定義應用程式在發生失敗時遞增錯誤計數器的時間。Defaut value: **"1d"**, for 1 day.

   When the **[!UICONTROL Maximum number of errors before quarantine]** value is reached, the email address is then quarantined. Default value: **"5"**: the address will be quarantined on the sixth error. 這表示連絡人將會自動排除後續傳送的內容。

**相關主題**：

[瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)

## Email routing accounts {#email-routing-accounts}

**[!UICONTROL Integrated email routing]** 預設提供外部帳戶。其中包含允許應用程式傳送電子郵件的技術參數。

![](assets/channels_2.png)

The account type must always be set to **[!UICONTROL Routing]**, the channel to **[!UICONTROL Email]** and the delivery mode set to **[!UICONTROL Bulk delivery]**.

**相關主題**：

[外部帳戶](../../administration/using/external-accounts.md)

## Email processing rules {#email-processing-rules}

These rules contain the list of character strings which can be returned by remote servers and which let you qualify the error (**Hard**, **Soft** or **Ignored**).

預設規則如下：

**彈回數**

當電子郵件失敗時，遠端訊息伺服器會傳回反彈錯誤訊息至應用程式設定中指定的位址。Adobe Campaign會將每個反彈郵件的內容與規則清單中的字串進行比較，然後指派這個錯誤類型之一。

使用者可以建立自己的規則。

>[!CAUTION]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.

**管理電子郵件網域**

網域管理規則可用來控管特定網域的傳出電子郵件流程。他們會取樣反彈訊息，並在適當時機封鎖傳送。Adobe Campaign訊息伺服器會套用適用於網域的規則，然後套用規則清單中星號代表的一般大小寫規則。Adobe Campaign預設提供Hotmail和MSN網域的規則。

若要設定網域管理規則，只需設定臨界值並選取某些SFTP參數。**臨界值** 是計算的限制，超出所有對特定網域的訊息都會被封鎖。

例如，在一般情況下，至少有300個訊息，如果錯誤率高達90%，傳送電子郵件會被封鎖三小時。

**SMTP參數** 會作為套用至封鎖規則的篩選器。

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **SMTP繼電器**：可讓您設定特定網域的IP位址和中繼伺服器連接埠。

**MX管理**

每個規則都會定義MX的地址遮色片。因此，名稱符合此遮色片的任何MX都符合資格。遮色片可以包含「*」和「？」一般字元。

例如，下列地址：

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

與下列遮色片相容：

* *.yahoo.com
* ？mx.yahoo.com

這些規則依順序套用：第一個規則，其MX遮色片與目標MX相容。

每個規則可使用下列參數：

* **[!UICONTROL Range of IDs]**：此選項可讓您指出套用規則的識別碼(publicId)範圍。您可以指定：

   * 數字：規則只會套用至此PublicId。
   * 數字範圍(數字1)：規則將適用於這兩個編號之間的所有Publicities。
   如果欄位空白，規則會套用至所有ID。

* **[!UICONTROL Shared]**：此選項指出每小時和連線最高的訊息數，適用於所有連結至此規則的MXS。
* **[!UICONTROL Maximum number of connections]**：從指定位址同時連線到MX的次數上限。
* **最大訊息數量**：可由一個連線傳送的最大訊息數量。在此金額後，連線便會關閉，新的連線也會重新開啓。
* **[!UICONTROL Messages per hour]**：可透過指定位址在一小時內傳送的訊息數上限。

>[!CAUTION]
>
>* 如果參數已變更，則必須重新啓動傳送伺服器(MTA)。
>* 修改或建立管理規則僅適用於專家使用者。
>



## List of email properties {#list-of-email-properties}

This section details the list of parameters available in the properties screen of an email or [email template](../../start/using/about-templates.md).

>[!NOTE]
>
>有些參數僅適用於範本。Parameters you can access [depend on your permissions](../../administration/using/types-of-users.md).

To edit the properties of an email or an email template, use the **[!UICONTROL Edit properties]** button.

![](assets/delivery_options_1.png)

### General parameters {#general-parameters}

On the top of the email parameter screen, identify the email using the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields. 這些資訊會出現在介面中，但訊息收件者看不到。

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>ID必須是唯一的。

**[!UICONTROL Brand]** 欄位可讓您選取連結至遞送的品牌。For more information on using and configuring brands, refer to the [Branding](../../administration/using/branding.md) section.

**[!UICONTROL Campaign]** 欄位可讓您輸入連結至電子郵件的促銷活動。

You can also add a **[!UICONTROL Description]** in the corresponding field and edit the image displayed on the email thumbnail in the lists.

### Sending parameters {#sending-parameters}

**[!UICONTROL Send]** 此區段僅適用於電子郵件範本。其中包含下列參數：

#### Retries parameters {#retries-parameters}

暫時未傳送的訊息會受到自動重試。This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

依預設，會排程五次重試，最低間隔為一小時，在24小時內分散。One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters) section.

可以全域變更重試次數(聯絡您的Adobe技術管理員)或每個傳送或傳送範本

**[!UICONTROL Test SMTP delivery]** 此選項可讓您測試透過SMTP傳送訊息。這些訊息會經過處理，直到與SMTP伺服器連線，但不會傳送。For more information on configuring SMTP, refer to the [List of email SMTP parameters](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters) section.

#### Email format parameters {#email-format-parameters}

您可以設定要傳送的電子郵件格式。有三個可用選項：

* **使用收件者偏好設定** (預設模式)：訊息格式是根據收件者描述檔中儲存的資料來定義，並依預設在 **電子郵件格式** 欄位(@ EmailFormat)中儲存。如果收件者想要接收特定格式的訊息，則會傳送格式。如果欄位尚未完成，則會傳送多部分替代訊息(請參閱下面)。
* **讓收件者郵件用戶端選擇最適合的格式(多部分替代)**：訊息包含兩種格式：文字和HTML。接收時顯示的格式取決於收件者的郵件軟體設定(多部分替代)。

   >[!CAUTION]
   >
   >此選項包括這兩個版本的訊息。因此，這會影響傳送總處理能力，因為訊息大小較大。

* **以文字格式傳送所有訊息**：訊息會以文字格式傳送。HTML格式不會傳送，但只有當收件者按一下訊息中的連結時，才會使用該格式。

### Validity period parameters {#validity-period-parameters}

**[!UICONTROL Validity]** 區段包含下列參數：

* **[!UICONTROL Explicitly set validity dates]**：勾選此方塊時，您必須在 **[!UICONTROL Delivery duration]** 和 **[!UICONTROL Resource validity limit]** 欄位中輸入持續時間。如果您想要定義特定時間和日期，請勾選此方塊。
* **[!UICONTROL Delivery duration]**：Adobe Campaign會在開始日期時傳送訊息。此欄位可讓您指定訊息可傳送的時間長度。
* **[!UICONTROL Resource validity duration]**：此欄位用於上傳的資源，主要用於鏡像頁面和影像。此頁面上的資源在限定時間內有效(儲存磁碟空間)。
* **[!UICONTROL Mirror page management]**：鏡像頁面是可透過網頁瀏覽器在線上存取的HTML頁面。其內容與電子郵件內容相同。根據預設，如果連結插入郵件內容，會產生鏡像頁面。此欄位可讓您修改產生此頁面的方式：

   >[!CAUTION]
   >
   >必須為電子郵件定義HTML內容，以便建立鏡像頁面。

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (預設模式)：如果連結插入郵件內容，就會產生鏡像頁面。
   * **強制產生鏡像頁面**：即使未插入鏡像頁面的連結，也會建立鏡像頁面。
   * **請勿產生鏡像頁面**：不會產生鏡像頁面，即使該連結位於訊息中亦然。
   * **只使用訊息ID產生可存取的鏡像頁面**：此選項可讓您在傳送記錄視窗中存取鏡像頁面的內容，以及個人化資訊。

>[!NOTE]
>
>The **[!UICONTROL Explicitly set validity dates]** and **[!UICONTROL Delivery duration]** parameters do not apply to transactional messages. For more on transactional messaging, see [this section](../../channels/using/about-transactional-messaging.md).

### Tracking parameters {#tracking-parameters}

**[!UICONTROL Tracking]** 區段包含下列參數：

* **[!UICONTROL Activate tracking]**：可讓您啓用/停用訊息URL追蹤。To manage tracking for each message URL, use the **[!UICONTROL Links]** icon in the Email Designer action bar. See [About tracked URLs](../../designing/using/about-tracked-urls.md).
* **[!UICONTROL Tracking validity limit]**：可讓您定義追蹤將在URL上啓動的時間長度。
* **[!UICONTROL Substitution URL for expired URLs]**：您可以輸入網頁的URL，在追蹤過期後顯示該URL。

### Advanced parameters {#advanced-parameters}

**[!UICONTROL Advanced parameters]** 區段包含多個參數。

前兩個欄位可讓您輸入複雜電子郵件標題(回覆地址和回覆地址文字)所需的資訊。這項資訊可以個人化。若要這麼做，按一下要變更之欄位右側的按鈕，然後新增個人化欄位。Inserting and using the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

#### Target context {#target-context}

定位內容可讓您定義一組表格，用於電子郵件鎖定(在對象定義畫面中)和個人化(在HTML內容編輯器中定義個人化欄位)。

#### Routing {#routing}

此欄位表示使用的路由模式。它會參照外部帳戶。例如，如果您想要使用包含特定品牌設定的外部帳戶，則可使用此選項。

>[!NOTE]
>
>External accounts are accessible via the **Administration** &gt; **Application settings** &gt; **External accounts** menu.

#### Preparation {#preparation}

Preparing messages is detailed in the [Approving messages](../../sending/using/preparing-the-send.md) section.

* **[!UICONTROL Typology]**：在傳送時，必須準備好訊息才能驗證內容和設定。The verification rules applied during the preparation phase are defined in a **typology**. 例如，對於電子郵件，準備需要檢查主旨、URL和影像等。選取要套用至此欄位的字元。

   >[!NOTE]
   >
   >Typologies, which can be accessed via the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu, are presented in the [Typologies](../../administration/using/about-typology-rules.md) section.

* **[!UICONTROL Compute the label during delivery analysis]**：可讓您在訊息準備階段期間計算電子郵件的標籤值。
* **[!UICONTROL Save SQL queries in the log]**：此選項可讓您在準備階段中新增SQL查詢記錄檔。

### List of email SMTP parameters {#list-of-email-smtp-parameters}

**[!UICONTROL SMTP]** 區段包含下列參數：

* **[!UICONTROL Character encoding]**：如果您想要強制訊息編碼，然後選取您要使用的編碼，請勾選 **[!UICONTROL Force encoding]** 此方塊。
* **[!UICONTROL Bounce mails]**：依預設，會在平台的錯誤收件匣中收到反彈郵件(定義於 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Configuration]** 畫面)。To define a specific error address for an email, enter the address in the **[!UICONTROL Error address]** field.
* **[!UICONTROL Additional SMTP headers]**：此選項可讓其他的SMTP標題新增至您的訊息。The script entered in the **[!UICONTROL Headers]** field must reference one header per line, in the form of **name:value**. 值會視需要自動編碼。

   >[!CAUTION]
   >
   >新增插入額外SFTP標題的指令碼，適用於進階使用者。此指令碼語法必須符合此內容類型的需求：沒有未使用的空間，沒有空的線條等。

### List of access authorization parameters {#list-of-access-authorization-parameters}

**[!UICONTROL Access authorization]** 區段包含下列參數：

* **[!UICONTROL Organizational unit]** 欄位可讓您限制對特定使用者的此電子郵件存取權限。與指定單位或父單位相關聯的使用者可讀取並寫入此電子郵件。與子單位關聯的使用者只能閱讀此電子郵件的存取權。

   >[!NOTE]
   >
   >You can configure organizational units via the **Administration** &gt; **Users &amp; Security** menu.

* The **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** and **[!UICONTROL Last modified]** fields are automatically completed.

## Archiving emails {#archiving-emails}

您可以設定Adobe Campaign，保存從您的平台傳送的電子郵件副本。

不過，Adobe Campaign本身不會管理封存檔案。它可讓您將所選擇的訊息傳送至專屬地址，並使用外部系統來處理和封存。

在傳送範本中啓動時，此功能可讓您傳送完全副本的對應訊息給您必須指定的BCC電子郵件地址(不可見傳送收件者)。

### Recommendations and limitations {#recommendations-and-limitations}

* 此功能為選擇性功能。請檢查您的授權合約，並聯絡您的帳戶管理員以啓用它。
* 您只能使用一個BCC電子郵件地址。
* 系統只會考量成功傳送電子郵件。彈回數不是。
* 基於隱私權理由，BCC電子郵件必須由封存系統處理，可儲存安全的個人識別資訊(PII)。
* 建立新的傳送範本時，即使已購買選項，電子郵件密件副本仍未啓用。您必須在每個傳送範本中手動啓用它。

### Activating email archiving {#activating-email-archiving}

Email BCC is activated in the [email template](../../start/using/about-templates.md), through a dedicated option:

1. Go to **Resources** &gt; **Templates** &gt; **Delivery templates**.
1. Duplicate the out-of-the-box **[!UICONTROL Send via email]** template.
1. 選取複製的範本。
1. Click the **[!UICONTROL Edit properties]** button to edit the template's properties.
1. Expand the **[!UICONTROL Send]** section.
1. Check the **[!UICONTROL Archive emails]** box to keep a copy of all sent messages for each delivery based on this template.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.

