---
title: 在 Adobe Campaign 中設計內容
description: 從頭開始建立電子郵件內容、匯入HTML或運用現有範本。
page-status-flag: never-activated
uuid: 8f73407f-ab90-46bc-aeb6-bd87fcb0404c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: about-content-design
discoiquuid: 20800cde-50ad-4d2b-a2f9-812258bec665
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1208'
ht-degree: 90%

---


# Campaign 電子郵件設計工具{#designing-content-in-adobe-campaign}

在 Adobe Campaign 中建立電子郵件後，您必須定義其內容。

電子郵件設計工具可讓您透過拖放介面，建立吸引人、個別自訂的電子郵件。 不論您是從空白顯示窗開始，或是運用現有的內容片段或範本，針對每封電子郵件（不論是促銷或異動）設計和調整所有內容。

電子郵件設計工具是專為提供最佳化的 HTML 以進行回應式式計而建置，可讓您透過使用者介面，輕鬆定義並套用可見性條件和動態內容至電子郵件、範本或片段。只要按一下按鈕，您就可以順暢地在拖放介面和 HTML 代碼之間切換。

電子郵件設計工具可以讓您建立電子郵件內容和電子郵件內容範本。它可與簡單電子郵件、異動電子郵件、A/B 測試電子郵件、多語言電子郵件和循環電子郵件相容。

若要開始使用電子郵件設計工具，請觀看[這組影片](https://docs.adobe.com/content/help/zh-Hant/campaign-standard-learn/tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted)，其中說明電子郵件設計工具的一般功能，以及如何從草稿開始或使用範本來設計電子郵件。

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* 若要瞭解如何建立電子郵件內容，請參 閱「[開始使用電子郵件設計工具](../../designing/using/quick-start.md)」。
* 有關電子郵件設計工具的概觀，請參閱「[使用電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)」。
* 有關建立內容的更多資訊：
   * 從草稿開始，請參閱「[從草稿開始設計電子郵件](../../designing/using/designing-from-scratch.md)」。
   * 使用現有內容，請參閱「[使用現有內容設計](../../designing/using/using-existing-content.md)」。
   * 使用 Creative Cloud 整合，請參閱「[多解決方案電子郵件設計](../../designing/using/using-integrations.md)」。
* 如需個人化的詳細資訊，請參閱「[個人化](../../designing/using/personalization.md)」。

建立電子郵件時，您可以選擇使用預先定義的範本，或從其他來源載入現有內容。請參閱「[選擇現有內容](../../designing/using/using-existing-content.md#selecting-an-existing-content)」。

若要提高行銷活動的效率，請個人化您的內容。請參閱「[插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)」和「[新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)」。

您也可以定義根據每個設定檔而異的動態內容。請參閱「[定義電子郵件中的動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)」，和「[定義登陸頁面中的動態內容](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page)」。

使用連結和影像增強您的訊息和登陸頁面。請參閱「[插入連結](../../designing/using/links.md#inserting-a-link)」和「[插入影像](../../designing/using/images.md#inserting-images)」。

## 電子郵件設計工具介面 {#email-designer-interface}

電子郵件設計工具提供許多選項，可讓您建立、編輯和自訂內容的每個方面。

該介面由幾個提供不同功能的領域組成：

![](assets/email_designer_overview.png)

從&#x200B;**浮動視窗** (1) 中可用的元素，將結構元件和內容片段拖放至主&#x200B;**工作區** (2)。在&#x200B;**工作區** (2) 中選取元件或元素，並從&#x200B;**設定**&#x200B;窗格 (3) 自訂其主樣式和顯示特性。

從主&#x200B;**工具列** (4) 存取較一般的選項和設定。

>[!NOTE]
>
>**設定**&#x200B;窗格可依螢幕解析度向左移動並顯示。

![](assets/email_designer_toolbar.png)

編輯器介面的&#x200B;**上下文工具列**&#x200B;根據所選區域提供各種功能。其包含可讓您變更文字樣式的動作按鈕和按鈕。所進行的修改始終適用於選取的區域。

### 電子郵件設計工具首頁 {#email-designer-home-page}

[建立電子郵件](../../channels/using/creating-an-email.md)時，**[!UICONTROL Email Designer]** 首頁會在選取電子郵件內容時自動顯示。

![](assets/email_designer_home_page.png)

此 **[!UICONTROL Properties]** 索引標籤可讓您編輯電子郵件的詳細資訊，例如，標籤、寄件者的地址和名稱，或電子郵件主旨。您也可以按一下螢幕上方的電子郵件標籤，以存取此索引標籤。

![](assets/email_designer_home_properties.png)

此 **[!UICONTROL Templates]** 索引標籤可讓您從現成可用的 HTML 內容或您已建立的範本中選擇，以快速開始設計電子郵件。請參閱「[內容範本](../../designing/using/using-reusable-content.md#content-templates)」。

![](assets/email_designer_home_templates.png)

此 **[!UICONTROL Learn & support]** 索引標籤可讓您輕鬆存取相關文件和教學課程。

![](assets/email_designer_home_support.png)

如果您未選擇範本，電子郵件設計工具首頁還可以讓您選擇開始設計內容的方式：

* 按一下 **[!UICONTROL Create]** 按鈕，從草稿開始新內容。請參閱「[從草稿設計電子郵件內容](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)」。
* 按一下此 **[!UICONTROL Upload]** 按鈕，從您的電腦上傳檔案。請參閱「[從檔案匯入內容](../../designing/using/using-existing-content.md#importing-content-from-a-file)」。
* 按一下此 **[!UICONTROL Import from URL]** 按 鈕，從 URL 擷取現有內容。請參閱「[從 URL 匯入內容](../../designing/using/using-existing-content.md#importing-content-from-a-url)」。

## 術語 {#terminology}

**範本**：範本是電子郵件的結構，您可以建置並重複使用數個傳送。

**片段**：片段是可重複使用的元件，可在一封或多封電子郵件中參考。

**結構元件**：定義電子郵件版面的結構元素。

**內容元件**：內容元件是原始的空白元件，放入電子郵件後，您就可以編輯這些元件。

## 內容設計最佳實務 {#content-design-best-practices}

若要正確使用電子郵件設計工具並盡可能輕鬆地建立最佳電子郵件，建議您套用下列原則：

* 在 HTML 的 &lt;head> 區段中使用內嵌樣式，而不是個別的 CSS 和 CSS。透過使用內嵌樣式，您就可以最佳化內容片段的儲存和重複使用。

   請參閱「[新增內嵌樣式屬性](../../designing/using/styles.md#adding-inline-styling-attributes)」。

* 如果您匯入包含 HTML 內容的 ZIP 檔案，請使用一般的 CSS。不支援 SCSS 樣式表。

* 透過建立和重複使用內容片段，讓行銷活動保持一致性，輕鬆解決您的品牌化。

   請參閱「[建立內容片段](../../designing/using/using-reusable-content.md#creating-a-content-fragment)」。

* 編輯&#x200B;**電子郵件內容**&#x200B;時：

   在傳送訊息之前先預覽訊息。Adobe Campaign 提供了使用 Litmus 測試電子郵件轉譯的方法。如需詳細資訊，請參閱「[電子郵件轉譯](../../sending/using/email-rendering.md)」。

以下部分介紹有關消息的更多設計和一般最佳做法： [提供最佳實務](../../sending/using/delivery-best-practices.md)。

### 更新片段 {#email-designer-updates}

電子郵件設計工具正在不斷改進。如果您從草稿開始、從現成可用的範本建立電子郵件內容，或者如果您建立了片段，在您下次開啟內容時可能會收到下列更新訊息：

![](assets/email_designer_fragment_patch_message.png)

Adobe 建議將您的內容更新至最新版本，以避免發生 CSS 衝突等問題。按一下 **[!UICONTROL Update now]**。

如果內容更新期間發生錯誤，請檢查 HTML 並修正它，然後再次執行此更新。

有關片段問題，請注意下列事項：

* 如果您想要將片段新增至新電子郵件或範本，而且如果您收到此訊息，則需要先更新此片段。

* 如果您有多個片段，則必須更新您想在電子郵件內容中使用的每個片段。

* 為避免對目前尚未準備的電子郵件訊息造成影響，您可以選擇不更新某些片段。

* 您仍可傳送其中已使用未更新片段的電子郵件，但該片段不可編輯。

* 更新已準備好的電子郵件中使用的片段，並不會對這些電子郵件造成影響。

## 電子郵件設計工具限制 {#email-designer-limitations}

* 您無法在片段中使用個人化欄位。如需片段的詳細資訊，請參閱[本區段](../../designing/using/using-reusable-content.md#about-fragments)。

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* 在編輯樣式時，僅大多數電子郵件用戶端正式支援的網頁字型才有提供。
* 樣式無法儲存為主題，以供日後重複使用。不過，CSS 樣式可以儲存在內容範本或電子郵件中。如需樣式的詳細資訊，請參閱[本區段](../../designing/using/styles.md)。
* 「電子郵件設計工具」不支援反向連結meta標籤。
* 替代對（未包含在Unicode字元集的「基本多語言平面」中的字元）無法儲存為2個位元組（16位元），且需要編碼為2個UTF-16字元。 這些字元包括一些CJK表意文字、大多數表情符號和一些語言。<br>這些字元可能會在動態文字中造成一些不相容的問題。 傳送訊息前，您必須先執行強式測試。

**相關主題**

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [設計登錄頁面](../../channels/using/designing-a-landing-page.md)
* [建立 SMS 訊息](../../channels/using/creating-an-sms-message.md)
* [準備和傳送推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
