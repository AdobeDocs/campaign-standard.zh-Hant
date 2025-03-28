---
title: 個人化電子郵件內容
description: 瞭解如何在電子郵件Designer中個人化電子郵件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3ea58bcf-234e-4dac-b296-da3f57e18a7d
source-git-commit: 9291eb06c35b1d06c0a992fa64a460215477f57e
workflow-type: tm+mt
source-wordcount: '2611'
ht-degree: 4%

---

# 個人化電子郵件內容 {#personalization}

Adobe Campaign傳送的訊息內容和顯示方式可透過數種不同的方式實現個人化。 根據設定檔的條件，可以將這些方式結合使用。 一般而言，Adobe Campaign 允許您：

* 插入動態的個人化欄位。請參閱[插入個人化欄位](#inserting-a-personalization-field)。
* 插入預先定義的個人化區塊。 請參閱[新增內容區塊](#adding-a-content-block)。
* 個人化電子郵件的寄件者。 請參閱[個人化寄件者](#personalizing-the-sender)。
* 個人化電子郵件的主旨。 請參閱[個人化電子郵件的主旨列](../../designing/using/subject-line.md#subject-line)。
* 建立有條件的內容。請參閱[定義電子郵件中的動態內容](#defining-dynamic-content-in-an-email)。

## 個人化寄件者 {#personalizing-the-sender}

若要定義將顯示在已傳送訊息標題中的寄件者名稱，請移至電子郵件Designer首頁的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤（可透過首頁圖示存取）。 如需詳細資訊，請參閱[定義電子郵件的寄件者](../../designing/using/subject-line.md#email-sender)。

您可以按一下&#x200B;**寄件者名稱**&#x200B;區塊來變更寄件者名稱。 欄位隨後會變成可編輯，您可以輸入要使用的名稱。

此欄位可個人化。 若要這麼做，您可以按一下寄件者名稱下方的圖示，新增個人化欄位、內容區塊和動態內容。

>[!NOTE]
>
>標頭引數不得為空白。 必須提供寄件者的地址，才能傳送電子郵件（RFC標準）。 Adobe Campaign會檢查所輸入電子郵件地址的語法。

## 個人化URL {#personalizing-urls}

Adobe Campaign可讓您新增個人化欄位、內容區塊或動態內容，以個人化訊息中的一或多個URL。 操作步驟：

1. 插入外部URL並指定其引數。 請參閱[插入連結](../../designing/using/links.md#inserting-a-link)。
1. 如果未顯示，請按一下「設定」窗格中所選URL旁的鉛筆，以存取個人化選項。
1. 新增您要使用的個人化欄位、內容區塊和動態內容。

   ![](assets/des_personalize_links.png)

1. 儲存您的變更。

>[!NOTE]
>
>當追蹤連結的URL簽章機制停用時，個人化URL無法套用至網域名稱或URL副檔名。 如果個人化不正確，在訊息分析期間會顯示錯誤訊息。
>
>選取內容區塊時，不允許您選取元素，例如&#x200B;**映象頁面的連結**。 連結內禁止此類封鎖。

## 插入個人化欄位{#inserting-a-personalization-field}

Adobe Campaign可讓您將欄位從資料庫插入您的頁面，例如設定檔的名字。

>[!NOTE]
>
>以下影像顯示如何使用電子郵件的[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)插入個人化欄位。

若要將個人化欄位新增至內容：

1. 在文字區塊內按一下，從內容工具列按一下&#x200B;**[!UICONTROL Personalize]**&#x200B;圖示並選取&#x200B;**[!UICONTROL Insert personalization field]**。 如需電子郵件Designer介面的詳細資訊，請參閱[本節](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_perso_field_1.png)

1. 選取您要插入頁面內容的欄位。

   ![](assets/email_perso_field_2.png)

1. 按一下&#x200B;**[!UICONTROL Confirm]**。

欄位名稱會出現在編輯器中，並反白顯示。

![](assets/email_perso_field_3.png)

產生個人化後（例如預覽和準備電子郵件時），此欄位將由目標設定檔對應的值取代。

>[!NOTE]
>
>如果電子郵件是從工作流程建立，則工作流程中計算的其他資料也可在個人化欄位中使用。 如需從工作流程新增其他資料的詳細資訊，請參閱[擴充資料](../../automating/using/about-targeting-activities.md#enriching-data)區段。

## 新增內容區塊 {#adding-a-content-block}

Adobe Campaign提供預先設定的內容區塊清單。 這些內容區塊為動態、個人化的且具有特定轉譯。 例如，您可以新增問候語或映象頁面的連結。

>[!NOTE]
>
>以下影像顯示如何使用電子郵件的[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)插入內容區塊。

若要新增內容區塊：

1. 在文字區塊內按一下，從內容工具列按一下&#x200B;**[!UICONTROL Personalize]**&#x200B;圖示並選取&#x200B;**[!UICONTROL Insert content block]**。 如需電子郵件Designer介面的詳細資訊，請參閱[本節](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface)。

   ![](assets/email_content_block_1.png)

1. 選取您要插入的內容區塊。 可用的區塊會因內容（電子郵件或登入頁面）而異。

   ![](assets/email_content_block_2.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。

內容區塊的名稱會顯示在編輯器中，並以黃色反白顯示。 產生個人化時，會自動調整為適合設定檔。

![](assets/email_content_block_3.png)

現成可用的內容區塊包括：

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Link to mirror page (MirrorPage)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**：此內容區塊只能在&#x200B;**登陸頁面**&#x200B;中使用。
* **[!UICONTROL Default sender name (DefaultSenderName)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**：此內容區塊只能用於&#x200B;**傳遞**。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### 建立自訂內容區塊 {#creating-custom-content-blocks}

您可以定義要插入訊息或登入頁面的新內容區塊。

若要建立內容區塊，請執行下列步驟：

1. 按一下進階功能表中的&#x200B;**[!UICONTROL Resources > Content blocks]**&#x200B;以存取內容區塊清單。
1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕或複製預先存在的內容區塊。

   ![](assets/content_bloc_01.png)

1. 輸入標籤。
1. 選取區塊的&#x200B;**[!UICONTROL Content type]**。 有三種可用選項：

   * **[!UICONTROL Shared]**：內容區塊可用於傳遞或登入頁面。
   * **[!UICONTROL Delivery]**：內容區塊只能用於傳遞。
   * **[!UICONTROL Landing page]**：內容區塊只能用於登入頁面。

   ![](assets/content_bloc_02.png)

1. 您可以選取&#x200B;**[!UICONTROL Targeting dimension]**。 如需詳細資訊，請參閱[關於目標維度](#about-targeting-dimension)。

   ![](assets/content_bloc_04.png)

1. 您可以選取&#x200B;**[!UICONTROL Depends on format]**&#x200B;選項來定義兩個不同的區塊：一個用於HTML電子郵件，另一個用於文字格式的電子郵件。 編輯器接著會顯示兩個索引標籤(HTML和文字)，以定義對應的內容。

   ![](assets/content_bloc_03.png)

1. 輸入內容區塊的內容，然後按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。

您的內容區塊現在可用於訊息或登入頁面的內容編輯器。

>[!CAUTION]
>
>編輯區塊的內容時，請確定&#x200B;*if*&#x200B;陳述式的開頭和結尾之間沒有額外的空格。 在HTML中，熒幕上會顯示空格，因此會影響您的內容版面。

### 關於目標維度 {#about-targeting-dimension}

目標維度可讓您定義您可以使用內容區塊的訊息型別。 這是為了防止在訊息中使用不當區塊，因為這可能造成錯誤。

事實上，在編輯訊息時，您只能選取具有與訊息目標維度相容之目標維度的內容區塊。

例如，**[!UICONTROL Unsubscription link]**&#x200B;區塊的目標維度是&#x200B;**[!UICONTROL Profiles]**，因為它包含&#x200B;**[!UICONTROL Profiles]**&#x200B;資源專屬的個人化欄位。 因此，您無法在[事件交易式訊息](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)中使用&#x200B;**[!UICONTROL Unsubscription link]**&#x200B;區塊，因為該訊息型別的目標維度是&#x200B;**[!UICONTROL Real-time events]**。 不過，您可以在[設定檔交易式訊息](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types)中使用&#x200B;**取消訂閱連結**&#x200B;區塊，因為該訊息型別的目標維度是&#x200B;**設定檔**。 最後，**[!UICONTROL Link to mirror page]**&#x200B;區塊沒有目標維度，因此您可以在任何訊息中使用它。

如果您將此欄位留空，無論目標維度為何，內容區塊都將與所有訊息相容。 如果您設定目標維度，該區塊只會與具有相同目標維度的訊息相容。

如需詳細資訊，請參閱[目標維度和資源](../../automating/using/query.md#targeting-dimensions-and-resources)。

**相關主題：**

* [插入個人化欄位](#inserting-a-personalization-field)
* [新增內容區塊](#adding-a-content-block)
* [定義電子郵件中的動態內容](#defining-dynamic-content-in-an-email)

## 個人化影像來源{#personalizing-an-image-source}

Adobe Campaign可讓您根據特定條件或使用追蹤，將訊息中的一個或多個影像個人化。 將個人化欄位、內容區塊或動態內容插入影像來源即可完成此操作。 操作步驟：

1. 將影像插入訊息內容，或選取已存在的影像。
1. 在影像屬性調色盤中，核取&#x200B;**[!UICONTROL Enable personalization]**&#x200B;選項。

   ![](assets/des_personalize_images_1.png)

   顯示&#x200B;**[!UICONTROL Source]**&#x200B;欄位，且編輯器中選取的影像顯示為&#x200B;**個人化**。

1. 按一下&#x200B;**[!UICONTROL Source]**&#x200B;欄位按鈕旁的鉛筆以存取個人化選項。
1. 新增影像來源後，新增您喜歡的個人化欄位、內容區塊和動態內容。

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >無法個人化網域名稱(http://mydomain.com)，必須手動輸入。 URL的其餘部分都可以個人化。 例如： http://mydomain.com/ `[Gender]` .jpg

1. 確認您的變更。

## 條件式內容 {#conditional-content}

### 定義可見度條件{#defining-a-visibility-condition}

您可以指定任何元素的可見度條件。 只有在符合條件時才會顯示它。

若要新增可見度條件，請選取區塊並在其設定的&#x200B;**[!UICONTROL Visibility condition]**&#x200B;欄位中輸入要遵循的條件。

![](assets/delivery_content_5.png)

此選項僅適用於下列元素：ADDRESS、BLOCKQUOTE、CENTER、DIR、DIV、DL、FIELDSET、FORM、H1、H2、H3、H4、H5、H6、NOSCRIPT、OL、P、PRE、UL、TR、TD。

運算式編輯器出現在[進階運算式編輯](../../automating/using/editing-queries.md#about-query-editor)區段中。

這些條件採用XTK運算式語法(例如&#x200B;**context.profile.email！=&quot;**&#x200B;或&#x200B;**context.profile.status=&#39;0&#39;**)。 依預設，所有欄位都是可見的。

>[!NOTE]
>
>無法為已包含具有動態內容的子元素或已構成動態內容的區塊定義條件。 無法編輯無法看到的動態區塊（例如下拉式清單）。

### 定義電子郵件中的動態內容{#defining-dynamic-content-in-an-email}

>[!CONTEXTUALHELP]
>id="ac_dynamic_content"
>title="定義動態內容"
>abstract="根據您要定義的條件，定義將僅顯示給部分輪廓的不同內容。"

在電子郵件中，您可以定義不同的內容，這些內容將根據透過運算式編輯器定義的條件，以動態方式顯示給收件者。 例如，從相同的電子郵件，您可以確保每個設定檔都會根據其年齡範圍收到不同的訊息。

定義動態內容與[定義可見性條件](#defining-a-visibility-condition)不同。

1. 選取片段、元件或元素。 在此範例中，選取影像。
1. 按一下內容工具列中的&#x200B;**[!UICONTROL Dynamic content]**&#x200B;圖示。

   ![](assets/dynamic_content_2.png)

   **[!UICONTROL Dynamic content]**&#x200B;區段會出現在左側的浮動視窗中。

   ![](assets/dynamic_content_3.png)

   依預設，此區段包含兩個元素：預設變體和新變體。

   >[!NOTE]
   >
   >內容必須一律有預設變體。 您無法刪除它。

1. 按一下&#x200B;**[!UICONTROL Edit]**&#x200B;按鈕以定義第一個替代變體的顯示條件。

   ![](assets/dynamic_content_4.png)

1. 指定標籤並選取要設定為條件的欄位。 例如，從&#x200B;**[!UICONTROL General]**&#x200B;節點，選取&#x200B;**[!UICONTROL Age]**&#x200B;欄位

   ![](assets/dynamic_content_5.png)

1. 設定篩選條件。 例如，您希望向18至25歲之間的人顯示不同的內容。

   ![](assets/dynamic_content_6.png)

1. 設定所有條件後，定義將套用條件的優先順序並儲存變更。

   ![](assets/dynamic_content_7.png)

   內容會依優先順序（從上到下）顯示在浮動視窗中。 如需優先順序的詳細資訊，請參閱[本節](#defining-dynamic-content-in-an-email)。

1. 為您剛定義的變體上傳新影像。

   ![](assets/dynamic_content_8.png)

   年齡介於18至25歲的收件者將看到新影像。

   ![](assets/dynamic_content_10.png)

1. 按一下&#x200B;**[!UICONTROL Add a condition]**&#x200B;以新增內容及其連結的規則。

   ![](assets/dynamic_content_9.png)

   例如，您可以新增要顯示給26至35歲之間之人員的不同影像。

1. 對於您想要動態顯示的任何其他電子郵件元素，請以類似方式繼續執行。 可以是文字、按鈕、片段等。 儲存您的變更。

>[!CAUTION]
>
>當您準備好訊息之後並在傳送訊息之前，請使用校樣來測試訊息。 如果不這樣做，則可能無法偵測到某些錯誤，且可能無法傳送電子郵件。

**相關主題：**

* [傳送校樣](../../sending/using/sending-proofs.md)
* [進階運算式編輯](../../automating/using/editing-queries.md#about-query-editor)

### 優先順序 {#order-of-priority}

在運算式編輯器中，當您定義動態內容時，優先順序如下。

1. 您以&#x200B;**兩個不同的條件**&#x200B;定義兩個不同的動態內容，例如：

   **條件1：**&#x200B;設定檔的性別是男性的，

   **條件2：**&#x200B;設定檔的年齡介於20到30歲之間。

   ![](assets/delivery_content_61.png)

   資料庫中的部分設定檔對應至兩個條件，但只能傳送一封包含一個動態內容的電子郵件。

1. 因此，您必須定義動態內容的優先順序。 優先順序為&#x200B;**1** （因此也是對應的動態內容）的條件會傳送到設定檔，即使此設定檔也符合其優先順序為&#x200B;**2**&#x200B;或&#x200B;**3**&#x200B;的另一個條件。

   ![](assets/delivery_content_62.png)

您只能為每個動態內容定義一個優先順序順序。

## 範例：電子郵件個人化{#example-email-personalization}

在此範例中，行銷服務團隊的成員已建立電子郵件，通知部分客戶有專門為其提供的特別優惠。 團隊成員決定根據客戶各自的年齡來個人化電子郵件。 年齡介於18至27歲的客戶會收到一封電子郵件，內含27歲以上客戶將收到的不同影像和口號。

電子郵件的建立方式如下：

* 動態內容會套用至影像，且這些動態內容會根據年齡範圍進行設定。

  ![](assets/delivery_content_43.png)

  新增及設定動態內容的詳細資訊請參閱[定義電子郵件](#defining-dynamic-content-in-an-email)中的動態內容。

* 個人化欄位和動態內容會套用至文字。 根據設定檔的年齡範圍，電子郵件會從設定檔的名字或設定檔的標題和姓氏開始。

  ![](assets/delivery_content_44.png)

  新增及設定個人化欄位的詳細資訊請參閱[插入個人化欄位](#inserting-a-personalization-field)區段。

### 設定影像 {#configuring-images}

>[!CONTEXTUALHELP]
>id="ac_dynamic_image"
>title="管理動態影像"
>abstract="根據您要定義的條件，使用動態影像將您的電子郵件個人化。"

在此範例中，套用至影像的動態內容設定如下：

**至目標18-27歲：**

1. 在&#x200B;**[!UICONTROL Properties]**&#x200B;浮動視窗中選取動態內容，然後按一下&#x200B;**[!UICONTROL Edit]**&#x200B;按鈕。

   ![](assets/delivery_content_48.png)

1. 編輯標籤，然後從&#x200B;**[!UICONTROL Profile]**&#x200B;節點選取&#x200B;**[!UICONTROL Age]**&#x200B;欄位。

   ![](assets/delivery_content_49.png)

1. 選取&#x200B;**大於或等於**&#x200B;運運算元，然後輸入&#x200B;**18**&#x200B;以建立早於18 **運算式的**。

   ![](assets/delivery_content_50.png)

1. 新增新的&#x200B;**[!UICONTROL Age]**&#x200B;條件。

   在值欄位中選取&#x200B;**小於或等於**&#x200B;運運算元，然後選取27以建立小於27 **的**&#x200B;運算式。

   ![](assets/delivery_content_51.png)

1. 確認您的變更。

**若要鎖定年齡在27歲或以上的設定檔：**

1. 從浮動視窗中選取動態內容並加以編輯。
1. 編輯標籤，然後從&#x200B;**[!UICONTROL Profile]**&#x200B;節點選取&#x200B;**[!UICONTROL Age]**&#x200B;欄位。
1. 在值欄位中加入&#x200B;**大於**&#x200B;的運運算元，後面加27，以建立早於27 **的**&#x200B;運算式。

   ![](assets/delivery_content_52.png)

1. 確認您的變更。

您的動態內容已正確設定。

### 設定文字 {#configuring-text}

在此範例中，套用至文字的動態內容設定如下：

**若要鎖定年齡介於18至27歲之間的設定檔：**

1. 選取您要的結構元件並新增動態內容。
1. 編輯動態內容並設定目標定位運算式。 請參閱[設定影像](#configuring-images)。
1. 在結構元件中，在所需位置按一下內容工具列中的&#x200B;**[!UICONTROL Personalize]**&#x200B;圖示，然後選取&#x200B;**[!UICONTROL Insert personalization field]**。

   ![](assets/delivery_content_53.png)

1. 在出現的清單中，選取&#x200B;**[!UICONTROL First name]**&#x200B;欄位並確認。

   ![](assets/delivery_content_54.png)

1. 接著，您的個人化欄位就會完美地插入選取的動態內容中。

**若要鎖定年齡在27歲或以上的設定檔：**

1. 選取您要的結構元件並新增動態內容。
1. 編輯動態內容並設定目標定位運算式。 請參閱[設定影像](#configuring-images)。
1. 在結構元件中，在所需位置按一下內容工具列中的&#x200B;**[!UICONTROL Personalize]**&#x200B;圖示，然後選取&#x200B;**[!UICONTROL Insert personalization field]**。
1. 從下拉式清單中選取&#x200B;**[!UICONTROL Title]**。
1. 以類似方式繼續新增&#x200B;**[!UICONTROL Last name]**&#x200B;欄位。

   ![](assets/delivery_content_56.png)

您的個人化欄位現在應完美插入所選的動態內容。

### 預覽電子郵件 {#previewing-emails}

預覽可讓您在傳送&#x200B;**[!UICONTROL Proofs]**&#x200B;之前檢查個人化欄位和動態內容是否已正確設定。 在預覽期間，您可以選取與電子郵件目標對應的不同測試設定檔。

若沒有測試設定檔，預設顯示的電子郵件為：

![](assets/delivery_content_45.png)

電子郵件中的標語沒有個人化欄位，而是使用預設影像。

第一個測試設定檔對應至年齡介於18到27歲之間的使用者端。 選取此設定檔後，會顯示下列電子郵件：

![](assets/delivery_content_46.png)

對應至18-27歲運算式（特別是設定檔的名字）的個人化欄位已正確設定，且影像也已根據設定檔變更。

第二個設定檔對應至27歲以上的使用者端，並產生下列電子郵件：

![](assets/delivery_content_47.png)

由於動態內容，影像已變更，而出現的標語是為此目標群體定義的較正式標語。

**相關主題：**

* [建立客群](../../audiences/using/creating-audiences.md)
* [準備傳送](../../sending/using/preparing-the-send.md)
