---
title: 建立及使用可重複使用的內容
description: 開始使用電子郵件Designer建置可重複使用的電子郵件內容。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 64c3d3dd-0c41-4dbc-abcd-9ddea23759f4
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1812'
ht-degree: 2%

---

# 建立及使用可重複使用的內容 {#using-reusable-content}

瞭解如何掌握電子郵件內容版本。 透過電子郵件Designer，您可以使用您自己的預先定義內容來建立範本和片段，並在後續傳送中重複使用。

## 使用範本設計電子郵件 {#designing-templates}

>[!NOTE]
>
> 在Adobe Campaign Standard中，您可以建立可從&#x200B;**資源** > **範本**&#x200B;功能表存取的不同範本型別。 電子郵件Designer中使用的範本為內容範本。 如需詳細資訊，請參閱[關於範本](../../start/using/marketing-activity-templates.md)。

![](assets/do-not-localize/how-to-video.png) [探索如何在影片中建立範本](#video)

### 關於內容範本 {#content-templates}

您可以管理[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)首頁的&#x200B;**[!UICONTROL Templates]**&#x200B;索引標籤中提供的HTML內容。

現成的電子郵件內容範本包含18個行動裝置最佳化的版面，以及Behance藝人設計的四個同級最佳回應範本。 它們對應於最新使用情況，例如客戶歡迎訊息、電子報和重新參與電子郵件等。 您可以輕鬆根據品牌內容進行自訂，以簡化從草稿開始設計電子郵件的程式。

![](assets/template_content.png)

可從[進階功能表](../../start/using/interface-description.md#advanced-menu)的&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]**&#x200B;畫面存取HTML內容範本。 從那裡，您可以管理登入頁面內容範本、電子郵件內容範本以及片段。

![](assets/content_templates_list.png)

現成可用的內容範本是唯讀的。 若要編輯其中一個範本，您必須先複製所需的範本。

您可以建立新範本或片段，並定義您自己的內容。 如需詳細資訊，請參閱[建立內容範本](#creating-a-content-template)和[建立內容片段](#creating-a-content-fragment)。

使用電子郵件Designer編輯內容時，您也可以將內容儲存為片段或範本以建立內容範本。 如需詳細資訊，請參閱[將內容儲存為範本](#saving-content-as-template)和[將內容儲存為片段](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)。

**相關主題：**

* 如需編輯內容的詳細資訊，請參閱[關於電子郵件內容設計](../../designing/using/designing-content-in-adobe-campaign.md)。

### 建立內容範本 {#creating-a-content-template}

您可以建立自己的內容範本，以視需要多次使用。

下列範例顯示如何建立電子郵件內容範本。

1. 前往&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]**&#x200B;並按一下&#x200B;**[!UICONTROL Create]**。
1. 按一下電子郵件標籤以存取電子郵件Designer的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤。
1. 指定可識別的標籤並選取下列引數，以便在電子郵件中使用此範本：

   * 從&#x200B;**[!UICONTROL Content type]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Shared]**&#x200B;或&#x200B;**[!UICONTROL Delivery]**。
   * 從&#x200B;**[!UICONTROL HTML type]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Template]**。

   ![](assets/email_designer_create-template.png)

1. 如有需要，您可以設定要作為範本縮圖的影像。 從範本屬性的&#x200B;**[!UICONTROL Thumbnail]**&#x200B;索引標籤中選取它。

   ![](assets/email_designer_create-template_thumbnail.png)

   此縮圖會顯示在[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)首頁的&#x200B;**[!UICONTROL Templates]**&#x200B;標籤中。

1. 關閉&#x200B;**[!UICONTROL Properties]**&#x200B;標籤以返回主工作區。
1. 新增您可視需求自訂的結構元件和內容元件。
   >[!NOTE]
   >
   > 您無法在內容範本中插入個人化欄位或條件式內容。
1. 編輯後，儲存您的範本。

此範本現在可用於透過電子郵件Designer建置的任何電子郵件。 從[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)首頁的&#x200B;**[!UICONTROL Templates]**&#x200B;索引標籤中選取它。

![](assets/content_template_new.png)

### 將內容另存為範本 {#saving-content-as-template}

使用電子郵件Designer編輯電子郵件時，您可以直接將該電子郵件的內容另存為範本。

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. 從電子郵件Designer主工具列選取&#x200B;**[!UICONTROL Save as template]**。

   ![](assets/email_designer_save-as-template.png)

1. 視需要新增標籤和說明，然後按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-template_creation.png)

1. 若要尋找您剛建立的範本，請移至&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]**。

1. 若要使用您的新範本，請從[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)首頁的&#x200B;**[!UICONTROL Templates]**&#x200B;索引標籤中選取它。

   ![](assets/content_template_new.png)

### 使用片段和元件建立範本 {#template-fragments-components}

您現在可以使用電子郵件Designer建立電子郵件範本。 使用內容元件來反映電子郵件的不同區段，並調整設定以使其儘可能接近您的原始電子報。 最後，插入您剛才建立的片段。

1. 使用電子郵件Designer建立範本。 如需詳細資訊，請參閱[內容範本](#content-templates)。
1. 將數個結構元件插入範本中 — 對應至電子郵件的頁首、頁尾和內文。 如需新增結構元件的詳細資訊，請參閱[使用電子郵件Designer編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。
1. 視需要插入任意數量的內容元件，以建立Newsletter內文。 這將是您每月更新的電子郵件的可編輯內容。

   ![](assets/des_loading_compatible_fragment_5.png)

   如果您熟悉HTML程式碼，Adobe建議您運用&#x200B;**[!UICONTROL Html]**&#x200B;元件，以便複製並貼上原始電子郵件中較複雜的元素。 其餘內容使用其他元件，例如&#x200B;**[!UICONTROL Button]**、**[!UICONTROL Image]**&#x200B;或&#x200B;**[!UICONTROL Text]**。 如需詳細資訊，請參閱[關於內容元件](../../designing/using/designing-from-scratch.md#about-content-components)。

   >[!NOTE]
   >
   >使用&#x200B;**[!UICONTROL Html]**&#x200B;元件會導致建立可用有限選項編輯的元件。 在選取此元件之前，請確定您知道如何處理HTML程式碼。

1. 儘可能調整內容元件以符合原始電子郵件。

   ![](assets/des_loading_compatible_fragment_6.png)

   如需管理樣式設定和內嵌屬性的詳細資訊，請參閱[編輯電子郵件樣式](../../designing/using/styles.md)。

1. 將您先前建立的兩個片段（頁首和頁尾）插入所需的結構元件中。

   ![](assets/des_loading_compatible_fragment_10.png)

1. 儲存您的範本。

您現在可以在電子郵件Designer中完全管理此範本，以建立和更新您每月傳送給收件者的電子報。

若要使用，請建立電子郵件並選取您剛建立的內容範本。

**相關主題**：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [電子郵件Designer的簡介影片](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [從草稿開始設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

### 教學課程影片 {#video}

本影片說明如何建立您自己的範本。

>[!VIDEO](https://video.tv.adobe.com/v/23106?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)提供其他Campaign Standard操作說明影片。

## 關於片段 {#about-fragments}

>[!CONTEXTUALHELP]
>id="ac_fragments"
>title="關於片段"
>abstract="片段指可重複使用的內容區塊，可在一封或多封電子郵件中參照。"

片段是可重複使用的元件，可在一封或多封電子郵件中參考。
它們可以在&#x200B;**資源** > **內容片段和範本**&#x200B;下的介面中找到。

若要在電子郵件Designer中善用片段：

* 建立您自己的片段。 請參閱[建立內容片段](#creating-a-content-fragment)和[將內容另存為片段](#saving-content-as-a-fragment)。
* 視需要在電子郵件中多次使用。 請參閱[將元素插入電子郵件](#inserting-elements-into-an-email)。
* 當您編輯片段時，會同步變更：會自動傳播至包含該片段的所有電子郵件（假設尚未準備或傳送）。

新增至電子郵件時，預設會鎖定片段。 如果您想要修改特定電子郵件的片段，可以在使用原始片段的電子郵件中將其解除鎖定，以中斷與原始片段的同步。 變更將不再同步。

若要解除鎖定電子郵件內的片段，請選取該片段，然後按一下內容工具列中的鎖定圖示。

![](assets/des_unlocking_fragment.png)

該片段會成為不再連結至原始片段的獨立元件。 然後可以像任何其他內容元件一樣對其進行編輯。 請參閱[關於內容元件](../../designing/using/designing-from-scratch.md#about-content-components)。

### 在電子郵件中插入片段 {#inserting-elements-into-an-email}

若要定義電子郵件的內容，您可以在預先放置的結構元件中新增內容元素。 請參閱[編輯電子郵件結構](../../designing/using/designing-from-scratch.md#defining-the-email-structure)。

1. 選取左側的&#x200B;**+**&#x200B;圖示以存取內容元素。 選取[片段](#about-fragments)或[內容元件](../../designing/using/designing-from-scratch.md#about-content-components)。
1. 如果您已經知道要新增的片段標籤的標籤或部分，您可以搜尋它。

   ![](assets/email_designer_fragmentsearch.png)

1. 從浮動視窗將片段或內容元件拖放至電子郵件的結構元件。

   ![](assets/email_designer_addfragment.png)

   將元素新增至電子郵件後，即可將其移至結構元件內部或電子郵件中的另一個結構元件。

   ![](assets/email_designer_movefragment.png)

1. 編輯元素以符合此電子郵件的確切需求。 您可以新增文字、連結、影像等。

   >[!NOTE]
   >
   >將片段新增至電子郵件時，預設會鎖定片段。 如果您想要修改特定電子郵件的片段，或直接在片段中進行變更，可以中斷與原始片段的同步。 請參閱[關於片段](#about-fragments)。

1. 針對您需要新增至電子郵件的所有元素重複此程式。
1. 儲存您的電子郵件。

現在您的電子郵件結構已填入，您可以編輯每個內容元素的樣式。 請參閱[編輯元素](../../designing/using/styles.md)。

>[!NOTE]
>
>如果修改片段，變更會自動傳播到使用它的電子郵件中。 如需詳細資訊，請參閱[關於片段](#about-fragments)。

### 建立內容片段 {#creating-a-content-fragment}

您可以建立自己的內容片段，以視需要在一封或多封電子郵件中使用這些片段。

1. 前往&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]**&#x200B;並按一下&#x200B;**[!UICONTROL Create]**。
1. 按一下電子郵件標籤以存取電子郵件Designer的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤。
1. 指定可識別的標籤，並選取下列引數，以在編輯電子郵件內容時尋找片段：

   * 因為片段只與電子郵件相容，請從&#x200B;**[!UICONTROL Content type]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Delivery]**。
   * 從&#x200B;**[!UICONTROL HTML type]**&#x200B;下拉式清單中選取&#x200B;**[!UICONTROL Fragment]**，以便將此內容當做片段使用。

   ![](assets/email_designer_createfragment.png)

1. 如有需要，您可以設定要做為片段縮圖的影像。 從範本屬性的&#x200B;**[!UICONTROL Thumbnail]**&#x200B;索引標籤中選取它。

   ![](assets/email_designer_createfragment_thumbnail.png)

   編輯電子郵件時，此縮圖將顯示在片段標籤旁邊。

1. 關閉&#x200B;**[!UICONTROL Properties]**&#x200B;標籤以返回主工作區。
1. 新增您可視需求自訂的結構元件和內容元件。

   >[!CAUTION]
   >
   >片段不得包含個人化欄位、動態內容或其他片段。
   >
   >避免儲存為具有空白結構元件的片段內容。 插入>片段後，就無法編輯。
   >
   >[行動檢視](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)在片段中無法使用。

1. 編輯後，儲存您的片段。

此片段現在可用於使用電子郵件Designer建置的任何電子郵件。 它會顯示在浮動視窗的&#x200B;**[!UICONTROL Fragments]**&#x200B;區段下方。

>[!NOTE]
>
>除非在電子郵件中使用並解除鎖定，否則無法在片段中插入個人化欄位。 請參閱[關於片段](#about-fragments)。

### 將內容另存為片段 {#saving-content-as-a-fragment}

使用電子郵件Designer編輯電子郵件時，您可以直接將該電子郵件的一部分另存為片段。

* 您無法儲存包含個人化欄位、動態內容或其他片段的結構做為片段。
* 您只能選取彼此相鄰的結構。
  <!-- - You cannot select an empty structure.-->

1. 在電子郵件Designer中編輯電子郵件時，從主工具列選取&#x200B;**[!UICONTROL Save as fragment]**。

   ![](assets/email_designer_save-as-fragment.png)

1. 從工作區中，選取將構成片段的結構。

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >請務必選取彼此相鄰且不包含個人化欄位、動態內容或其他片段的結構。
   <!--You cannot select an empty structure.-->

1. 按一下&#x200B;**[!UICONTROL Create]**。

1. 視需要新增標籤和說明，然後按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-fragment_popup.png)

1. 若要尋找您剛才建立的片段，請前往&#x200B;**[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]**。

   ![](assets/email_designer_save-as-fragment_list.png)

1. 若要使用新片段，請開啟任何電子郵件內容，然後從片段清單中選取。

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>[行動檢視](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)在片段中無法使用。 如果您想要編輯電子郵件行動檢視，請在將內容儲存為片段之前進行編輯。

<!--You need to copy-paste the HTML corresponding to the section that you want to save into a new fragment.

>[!NOTE]
>
>To do this, you need to be familiar with HTML code.

To save as a fragment some email content that you created, follow the steps below.

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of that email.
1. Select and copy the HTML corresponding to the part that you want to save.
1. Go to **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. Paste the HTML that you copied where appropriate.
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.-->

## 使用片段建立可重複使用的頁首和頁尾 {#header-footer-fragments}

使用電子郵件Designer，為每個可重複使用的區段建立片段。 在此範例中，您將建立兩個片段：一個用於頁首，另一個用於頁尾。 接著，您就可以將現有內容中的相關部分複製到這些片段中。

要執行此操作，請遵循下列步驟：

1. 在Adobe Campaign中，前往「**[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]**」並為標題建立片段。 如需詳細資訊，請參閱[建立內容片段](#creating-a-content-fragment)。
1. 視需要儘量新增結構元件至片段。

   ![](assets/des_loading_compatible_fragment_1.png)

1. 將影像和文字元件插入您的結構中。

   ![](assets/des_loading_compatible_fragment_2.png)

1. 上傳對應的影像、輸入文字並調整設定。

   ![](assets/des_loading_compatible_fragment_3.png)

1. 儲存您的片段。
1. 以類似方式繼續建立並儲存您的頁尾。

   ![](assets/des_loading_compatible_fragment_4.png)

您的片段現在已準備好用於範本中。
