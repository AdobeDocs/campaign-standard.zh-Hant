---
solution: Campaign Standard
product: campaign
title: 個人化電子郵件內容
description: 瞭解如何在電子郵件設計人員中個人化電子郵件。
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: fc755f3176622e1faf08ccfa4236e016110f9a68
workflow-type: tm+mt
source-wordcount: '2573'
ht-degree: 3%

---


# 個人化電子郵件內容 {#personalization}

Adobe Campaign傳遞的訊息內容和顯示方式可透過多種不同方式個人化。 這些方式可根據條件結合，視描述檔而定。 一般而言，Adobe Campaign 允許您：

* 插入動態的個人化欄位。請參閱[插入個人化欄位](#inserting-a-personalization-field)。
* 插入預先定義的個人化區塊。 請參閱[新增內容區塊](#adding-a-content-block)。
* 個人化電子郵件的寄件者。 請參閱[個人化發件人](#personalizing-the-sender)。
* 個人化電子郵件的主題。 請參閱[個人化電子郵件的主旨行](../../designing/using/subject-line.md#subject-line)。
* 建立有條件的內容。請參閱[定義電子郵件中的動態內容。](#defining-dynamic-content-in-an-email)

## 個人化發件人{#personalizing-the-sender}

要定義將出現在發送郵件標題中的發件人名稱，請轉至「電子郵件設計器」首頁的&#x200B;**[!UICONTROL Properties]**&#x200B;頁籤（可通過首頁表徵圖訪問）。 有關詳細資訊，請參閱[定義電子郵件的發件人](../../designing/using/subject-line.md#email-sender)。

通過按一下&#x200B;**發件人名稱**&#x200B;塊，可以更改發件人名稱。 然後，欄位會變成可編輯，您可以輸入要使用的名稱。

此欄位可以個人化。 若要這麼做，您可以按一下傳送者名稱下方的圖示，新增個人化欄位、內容區塊和動態內容。

>[!NOTE]
>
>標題參數不得為空。 發件人地址是允許發送電子郵件的強制性地址（RFC標準）。 Adobe Campaign會檢查輸入的電子郵件地址語法。

## 個人化URL{#personalizing-urls}

Adobe Campaign可讓您新增個人化欄位、內容區塊或動態內容，以個人化訊息中的一或多個URL。 操作步驟：

1. 插入外部URL並指定其參數。 請參閱[插入連結](../../designing/using/links.md#inserting-a-link)。
1. 如果未顯示，請按一下「設定」窗格中選取之URL旁的鉛筆，以存取個人化選項。
1. 新增您要使用的個人化欄位、內容區塊和動態內容。

   ![](assets/des_personalize_links.png)

1. 儲存您的變更。

>[!NOTE]
>
>個人化URL無法套用至網域名稱，也無法套用至URL副檔名。 如果個人化不正確，則會在訊息分析期間顯示錯誤訊息。 選擇內容塊時，不允許選擇元素，如&#x200B;**連結到鏡像頁**。 此類塊在連結內部被禁止。

## 插入個人化欄位{#inserting-a-personalization-field}

Adobe Campaign可讓您將資料庫中的欄位插入頁面，例如描述檔的名字。

>[!NOTE]
>
>下圖顯示如何使用[電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)來插入個人化欄位。

若要新增個人化欄位至內容：

1. 在文字區塊內按一下，按一下內容相關工具列中的&#x200B;**[!UICONTROL Personalize]**&#x200B;圖示，然後選取&#x200B;**[!UICONTROL Insert personalization field]**。 有關「電子郵件設計器」介面的詳細資訊，請參閱[本節](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_perso_field_1.png)

1. 選取您要插入頁面內容的欄位。

   ![](assets/email_perso_field_2.png)

1. 按一下 **[!UICONTROL Confirm]**。

欄位名稱會出現在編輯器中，並反白顯示。

![](assets/email_perso_field_3.png)

產生個人化後（例如預覽和準備電子郵件時），此欄位將由與目標描述檔對應的值取代。

>[!NOTE]
>
>如果電子郵件是從工作流程建立，在工作流程中計算的其他資料也會顯示在個人化欄位中。 有關從工作流添加其他資料的詳細資訊，請參閱[ Myching data](../../automating/using/about-targeting-activities.md#enriching-data)部分。

## 添加內容塊{#adding-a-content-block}

Adobe Campaign提供預先設定的內容區塊清單。 這些內容區塊是動態、個人化的，並具有特定的演算。 例如，您可以添加問候語或鏡像頁面的連結。

>[!NOTE]
>
>下圖顯示如何使用[電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)來插入電子郵件的內容區塊。

若要新增內容區塊：

1. 在文字區塊內按一下，按一下內容相關工具列中的&#x200B;**[!UICONTROL Personalize]**&#x200B;圖示，然後選取&#x200B;**[!UICONTROL Insert content block]**。 有關「電子郵件設計器」介面的詳細資訊，請參閱[本節](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_content_block_1.png)

1. 選取您要插入的內容區塊。 可用的區塊會視上下文（電子郵件或著陸頁面）而異。

   ![](assets/email_content_block_2.png)

1. 按一下 **[!UICONTROL Save]**。

內容區塊的名稱會顯示在編輯器中，並以黃色反白顯示。 當個人化產生時，它會自動調整至個人檔案。

![](assets/email_content_block_3.png)

現成可用的內容區塊包括：

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Link to mirror page (MirrorPage)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**:此內容區塊僅能用於著 **陸頁面**。
* **[!UICONTROL Default sender name (DefaultSenderName)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**:此內容區塊只能用於傳 **送**。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### 建立自訂內容區塊{#creating-custom-content-blocks}

您可以定義將插入訊息或登陸頁面的新內容區塊。

若要建立內容區塊，請依照下列步驟進行：

1. 從進階功能表按一下&#x200B;**[!UICONTROL Resources > Content blocks]**&#x200B;以存取內容區塊清單。
1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕或複製預先存在的內容區塊。

   ![](assets/content_bloc_01.png)

1. 輸入標籤。
1. 選擇塊的&#x200B;**[!UICONTROL Content type]**。 有三種可用選項：

   * **[!UICONTROL Shared]**:內容區塊可用於傳送或著陸頁面。
   * **[!UICONTROL Delivery]**:內容區塊只能用於傳送。
   * **[!UICONTROL Landing page]**:內容區塊只能用於著陸頁面。

   ![](assets/content_bloc_02.png)

1. 您可以選取&#x200B;**[!UICONTROL Targeting dimension]**。 如需詳細資訊，請參閱[關於定位維度](#about-targeting-dimension)。

   ![](assets/content_bloc_04.png)

1. 您可以選擇&#x200B;**[!UICONTROL Depends on format]**&#x200B;選項來定義兩個不同的塊：一個用於HTML電子郵件，一個用於文本格式的電子郵件。 然後，編輯器（HTML和Text）中會顯示兩個標籤，以定義對應的內容。

   ![](assets/content_bloc_03.png)

1. 輸入內容區塊的內容，然後按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。

您的內容區塊現在可用於訊息或登陸頁面的內容編輯器中。

>[!CAUTION]
>
>編輯塊的內容時，請確保&#x200B;*if*&#x200B;語句的開頭和結尾之間沒有額外的空格。 在HTML中，空白字元會顯示在螢幕上，因此會影響您的內容版面配置。

### 關於定位維{#about-targeting-dimension}

定位維度可讓您定義可以使用內容區塊的訊息類型。 這是為了防止在消息中使用不適當的塊，這可能會導致錯誤。

事實上，在編輯訊息時，您只能選擇具有與訊息定位維度相容之定位維度的內容區塊。

例如，**[!UICONTROL Unsubscription link]**&#x200B;區塊的定位維度是&#x200B;**[!UICONTROL Profiles]**，因為它包含特定於&#x200B;**[!UICONTROL Profiles]**&#x200B;資源的個人化欄位。 因此，您不能在[事件事務性消息](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)中使用&#x200B;**[!UICONTROL Unsubscription link]**&#x200B;塊，因為該類型消息的目標維度為&#x200B;**[!UICONTROL Real-time events]**。 但是，您可以在[描述檔事務性訊息](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)中使用&#x200B;**取消訂閱連結**&#x200B;區塊，因為該類型訊息的定位維度是&#x200B;**描述檔**。 最後，**[!UICONTROL Link to mirror page]**&#x200B;區塊沒有定位維度，因此您可以在任何訊息中使用它。

如果您將此欄位保留為空白，則無論定位維度為何，內容區塊都會與所有訊息相容。 如果您設定定位維度，該區塊將僅與具有相同定位維度的訊息相容。

如需詳細資訊，請參閱[目標維度和資源](../../automating/using/query.md#targeting-dimensions-and-resources)。

**相關主題：**

* [插入個人化欄位](#inserting-a-personalization-field)
* [新增內容區塊](#adding-a-content-block)
* [定義電子郵件中的動態內容](#defining-dynamic-content-in-an-email)

## 個人化影像來源{#personalizing-an-image-source}

Adobe Campaign可讓您根據特定標準或使用追蹤，個人化訊息中的一或多張影像。 這是透過將個人化欄位、內容區塊或動態內容插入影像來源來完成的。 操作步驟：

1. 將影像插入訊息內容，或選取已存在的影像。
1. 在影像屬性浮動視窗中，勾選&#x200B;**[!UICONTROL Enable personalization]**&#x200B;選項。

   ![](assets/des_personalize_images_1.png)

   顯示&#x200B;**[!UICONTROL Source]**&#x200B;欄位，並在編輯器中將所選影像顯示為&#x200B;**個性化**。

1. 按一下&#x200B;**[!UICONTROL Source]**&#x200B;欄位按鈕旁的鉛筆，存取個人化選項。
1. 新增影像來源後，請新增您喜歡的個人化欄位、內容區塊和動態內容。

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >網域名稱(http://mydomain.com)無法個人化，必須手動輸入。 其餘的URL可以個人化。 例如：http://mydomain.com/ `[Gender]` .jpg

1. 確認您的變更。

## 條件式內容 {#conditional-content}

### 定義可見性條件{#defining-a-visibility-condition}

您可以在任何元素上指定可見性條件。 只有在遵守條件時，才會顯示。

要添加可見性條件，請選擇一個塊並在其設定的&#x200B;**[!UICONTROL Visibility condition]**&#x200B;欄位中輸入要考慮的條件。

![](assets/delivery_content_5.png)

此選項僅適用於下列元素：地址、塊引號、中心、目錄、DIV、DL、FIELDSET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD。

運算式編輯器顯示在[進階運算式編輯](../../automating/using/editing-queries.md#about-query-editor)區段中。

這些條件採用XTK表達式語法(例如，**context.profile.email !=&quot;**&#x200B;或&#x200B;**context.profile.status=&#39;0&#39;**)。 依預設，所有欄位皆可顯示。

>[!NOTE]
>
>無法為已包含具有動態內容的子元素的區塊或已構成動態內容的區塊定義條件。 無法編輯非可見的動態區塊（如下拉式清單）。

### 定義電子郵件中的動態內容{#defining-dynamic-content-in-an-email}

>[!CONTEXTUALHELP]
>id="ac_dynamic_content"
>title="定義動態內容"
>abstract="定義將僅根據您將定義的條件顯示給某些配置檔案的不同內容。"

在電子郵件中，您可以定義不同的內容，這些內容會根據透過運算式編輯器定義的條件動態顯示給收件者。 例如，您可以從相同的電子郵件，確保每個描述檔會根據其年齡範圍收到不同的訊息。

定義動態內容與定義可見性條件[不同。](#defining-a-visibility-condition)

1. 選取片段、元件或元素。 在此範例中，選取影像。
1. 按一下內容相關工具列中的&#x200B;**[!UICONTROL Dynamic content]**&#x200B;圖示。

   ![](assets/dynamic_content_2.png)

   **[!UICONTROL Dynamic content]**&#x200B;區段會出現在左側的浮動視窗中。

   ![](assets/dynamic_content_3.png)

   依預設，本節包含兩個元素：預設變體和新變體。

   >[!NOTE]
   >
   >內容必須始終具有預設變型。 您無法刪除。

1. 按一下&#x200B;**[!UICONTROL Edit]**&#x200B;按鈕可定義第一個替代變數的顯示條件。

   ![](assets/dynamic_content_4.png)

1. 指定標籤，並選取您要設定為條件的欄位。 例如，從&#x200B;**[!UICONTROL General]**&#x200B;節點中，選擇&#x200B;**[!UICONTROL Age]**&#x200B;欄位

   ![](assets/dynamic_content_5.png)

1. 設定篩選條件。 例如，您想要向18到25歲的人顯示不同的內容。

   ![](assets/dynamic_content_6.png)

1. 設定好所有條件後，請定義要套用條件的優先順序，並儲存您所做的變更。

   ![](assets/dynamic_content_7.png)

   內容會依優先順序從上到下顯示在浮動視窗中。 有關優先順序的詳細資訊，請參閱[本節](#defining-dynamic-content-in-an-email)。

1. 上傳您剛定義的變型的新影像。

   ![](assets/dynamic_content_8.png)

   18至25歲的受贈者將看到新的形象。

   ![](assets/dynamic_content_10.png)

1. 按一下&#x200B;**[!UICONTROL Add a condition]**&#x200B;以新增內容及其連結規則。

   ![](assets/dynamic_content_9.png)

   例如，您可以新增不同的影像，以便顯示給26歲到35歲的人。

1. 對於您電子郵件中想要動態顯示的任何其他元素，請以類似方式繼續。 可以是文字、按鈕、片段等。 儲存您的變更。

>[!CAUTION]
>
>在準備好消息後，在發送消息之前，請使用證明對其進行測試。 如果不執行此操作，則可能未檢測到某些錯誤，並且可能未發送電子郵件。

**相關主題：**

* [傳送校樣](../../sending/using/sending-proofs.md)
* [進階運算式編輯](../../automating/using/editing-queries.md#about-query-editor)

### 優先順序順序{#order-of-priority}

在表達式編輯器中，定義動態內容時，優先順序順序如下。

1. 可以定義兩個不同的動態內容，其中&#x200B;**包含兩個不同的條件**，例如：

   **條件1:** 側寫的性別為男性，

   **條件2:** 檔案在20到30歲之間。

   ![](assets/delivery_content_61.png)

   資料庫中的某些配置檔案符合這兩種情況，但只能發送一封包含一個動態內容的電子郵件。

1. 因此，必須定義動態內容的優先順序。 優先順序順序為&#x200B;**1**&#x200B;的條件（以及相應的動態內容）將被發送到配置檔案，即使優先順序順序為&#x200B;**2**&#x200B;或&#x200B;**3**&#x200B;的另一條件也由此配置檔案滿足。

   ![](assets/delivery_content_62.png)

每個動態內容只能定義一個優先順序順序。

## 示例：電子郵件個性化{#example-email-personalization}

在此示例中，營銷服務團隊的一名成員建立了一封電子郵件，通知他的一些客戶只有他們才有特別優惠。 團隊成員決定根據客戶各自的年齡對電子郵件進行個性化設定。 年齡在18歲至27歲之間的客戶將收到一封電子郵件，其中包含不同的影像和口號，這些客戶將收到27歲以上的客戶。

電子郵件的建立方式如下：

* 將動態內容應用到影像，並且根據年齡範圍配置這些動態內容。

   ![](assets/delivery_content_43.png)

   在[定義電子郵件](#defining-dynamic-content-in-an-email)部分中詳細介紹了添加和配置動態內容。

* 個性化欄位和動態內容被應用到文本。 根據配置檔案的年齡範圍，電子郵件以配置檔案的名稱或配置檔案的標題和姓氏開頭。

   ![](assets/delivery_content_44.png)

   在[插入個性化欄位](#inserting-a-personalization-field)部分中詳細介紹了添加和配置個性化欄位。

### 配置映像{#configuring-images}

>[!CONTEXTUALHELP]
>id="ac_dynamic_image"
>title="管理動態映像"
>abstract="根據您將要定義的條件，使用動態影像個性化您的電子郵件。"

在本示例中，應用於影像的動態內容配置如下：

**針對18-27歲兒童：**

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;調色板中選擇動態內容，然後按一下&#x200B;**[!UICONTROL Edit]**&#x200B;按鈕。

   ![](assets/delivery_content_48.png)

1. 編輯標籤，然後從&#x200B;**[!UICONTROL Profile]**&#x200B;節點中選擇&#x200B;**[!UICONTROL Age]**&#x200B;欄位。

   ![](assets/delivery_content_49.png)

1. 選擇「大於或等於&#x200B;**」運算子，然後輸入** 18 **以建立早於18**&#x200B;的&#x200B;**表達式。**

   ![](assets/delivery_content_50.png)

1. 添加新的&#x200B;**[!UICONTROL Age]**&#x200B;條件。

   在值欄位中，選擇&#x200B;**小於或等於**&#x200B;運算子後跟27以建立小於27 **的**&#x200B;表達式。

   ![](assets/delivery_content_51.png)

1. 確認您的變更。

**要針對27歲及以上的配置檔案：**

1. 從調色板中選擇動態內容並對其進行編輯。
1. 編輯標籤，然後從&#x200B;**[!UICONTROL Profile]**&#x200B;節點中選擇&#x200B;**[!UICONTROL Age]**&#x200B;欄位。
1. 在值欄位中添加&#x200B;**大於**&#x200B;運算子後跟27，以建立早於27 **的**&#x200B;表達式。

   ![](assets/delivery_content_52.png)

1. 確認您的變更。

您的動態內容已正確配置。

### 配置文本{#configuring-text}

在本示例中，應用於文本的動態內容配置如下：

**要針對18-27之間的陳舊配置檔案：**

1. 選擇所需的結構元件並添加動態內容。
1. 編輯動態內容並配置目標表達式。 請參閱[配置映像](#configuring-images)。
1. 在結構元件中，在所需位置，按一下上下文工具欄中的&#x200B;**[!UICONTROL Personalize]**&#x200B;表徵圖並選擇&#x200B;**[!UICONTROL Insert personalization field]**。

   ![](assets/delivery_content_53.png)

1. 在顯示的清單中，選擇&#x200B;**[!UICONTROL First name]**&#x200B;欄位並確認。

   ![](assets/delivery_content_54.png)

1. 然後，您的個性化欄位將完全插入選定的動態內容中。

**要針對27歲及以上的配置檔案：**

1. 選擇所需的結構元件並添加動態內容。
1. 編輯動態內容並配置目標表達式。 請參閱[配置映像](#configuring-images)。
1. 在結構元件中，在所需位置，按一下上下文工具欄中的&#x200B;**[!UICONTROL Personalize]**&#x200B;表徵圖並選擇&#x200B;**[!UICONTROL Insert personalization field]**。
1. 從下拉清單中選擇&#x200B;**[!UICONTROL Title]**。
1. 類似地繼續添加&#x200B;**[!UICONTROL Last name]**&#x200B;欄位。

   ![](assets/delivery_content_56.png)

您的個性化欄位現在應完美地插入到所選的動態內容中。

### 預覽電子郵件{#previewing-emails}

預覽允許您在發送&#x200B;**[!UICONTROL Proofs]**&#x200B;之前檢查個性化欄位和動態內容是否配置正確。 在預覽期間，您可以選擇與電子郵件目標對應的不同測試配置檔案。

如果沒有測試配置檔案，預設顯示的電子郵件為：

![](assets/delivery_content_45.png)

該電子郵件在口號中沒有個性化欄位，並且使用預設影像。

第一測試簡檔對應於年齡在18到27歲之間的客戶。 通過選擇此配置檔案，將顯示以下電子郵件：

![](assets/delivery_content_46.png)

與18-27年前的表達式（特別是配置檔案的名稱）對應的個性化欄位被正確配置，並且影像也根據配置檔案而改變。

第二個配置檔案對應於年齡超過27歲的客戶端，並生成以下電子郵件：

![](assets/delivery_content_47.png)

影像因為動態內容而發生了改變，而出現的口號正是為這個目標公眾定義的更正式的口號。

**相關主題：**

* [建立閱聽眾](../../audiences/using/creating-audiences.md)
* [準備傳送](../../sending/using/preparing-the-send.md)

