---
title: 關於範本
seo-title: 關於範本
description: 關於範本
seo-description: 「Adobe Campaign範本可讓您根據需求預先設定參數：範本可能包含行銷活動的完整或部分設定，以簡化非技術使用者的Adobe Campaign使用」。
page-status-flag: 從未啓動
uuid: 018534b6-61a3-433e-bb60-49883c8 b9386
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: 管理範本
discoiquuid: 95218eBE-5430-42a2-b900-1dadbhone92 d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fb303447e40f044bd221616cc320499c3cff0c3e

---


# 關於範本{#about-templates}

## 行銷活動範本 {#marketing-activity-templates}

當您建立新的行銷活動時，精靈中的第一個畫面會要求您選取類型或範本。範本可讓您根據需求預先設定某些參數。範本可能包含行銷活動的完整或部分設定。範本管理由功能管理員執行。

使用者擁有簡化的介面。建立新行銷活動時，您只需要選取想要使用的範本。無需擔心任何技術設定。這已經由範本中的功能管理員預先設定。

例如，若是電子郵件範本，您可以預先填入HTML內容、對象及傳送的任何其他參數：排程、測試描述檔、傳遞的一般屬性、進階參數等。這可讓您在建立新活動時節省時間。

![](assets/template_1.png)

針對每種行銷活動類型，一或多個現成可用的範本可用於最低組態。無法修改或刪除這些立即可用的範本。

範本可用於下列行銷活動：

* 程式
* 促銷活動
* 電子郵件傳送
* SMS傳送
* 推播通知
* 著陸頁面
* 工作流程
* Services
* 匯入
* 交易訊息

這些範本是從 **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** 畫面管理。

>[!NOTE]
>
>您可以在電子郵件或登陸頁面範本中預先設定品牌配置。如需詳細資訊，請參閱 [品牌](../../administration/using/branding.md) 區段。

## 內容範本 {#content-templates}

可從「進階」功能表的 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** 畫面存取HTML內容 [範本](../../start/using/interface-description.md#advanced-menu)。您可以從這裡管理著陸頁面內容範本、電子郵件內容範本和片段。

![](assets/content_templates_list.png)

現成可用的內容範本為唯讀。若要編輯其中一個，您必須先複製它。

您可以建立新範本或片段，並定義自己的內容。如需詳細資訊，請參閱 [「建立內容範本](../../start/using/about-templates.md#creating-a-content-template) 」和 [「建立內容片段](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment)」。

使用電子郵件設計工具編輯內容時，您也可以將內容儲存為片段或範本，建立內容範本。如需詳細資訊，請參閱 [「將內容儲存為範本](../../start/using/about-templates.md#saving-content-as-template) 」，並 [將內容儲存為片段](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment)。

### 立即可用的電子郵件內容範本 {#email-content-templates}

您可以管理 **[!UICONTROL Templates]**[電子郵件設計人員](../../designing/using/about-email-content-design.md#about-the-email-designer) 首頁標籤中提供的HTML內容。

現成可用的電子郵件內容範本包括18種行動最佳化版面配置，以及由Behance藝術家設計的種同級最佳回應範本。他們對應至最新的使用者，例如客戶歡迎訊息、電子報和重新吸引電子郵件等。您可以輕鬆地使用您的品牌內容自訂它們，輕鬆地從頭開始設計電子郵件。

![](assets/content_templates.png)

**相關主題：**

* 瞭解如何在此影片中個人化內容範本 [](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html)。
* 如需編輯內容的詳細資訊，請參閱 [關於電子郵件內容設計](../../designing/using/about-email-content-design.md)。

### 建立內容範本 {#creating-a-content-template}

您可以建立自己的內容範本，視需要多次使用它們。

下列範例說明如何建立電子郵件內容範本。

1. 前往 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** 並按一下 **[!UICONTROL Create]**。
1. 按一下電子郵件標籤以存取電子郵件設計工具 **[!UICONTROL Properties]** 的標籤。
1. 指定可識別的標籤並選取下列參數，以便在電子郵件中使用此範本：

   * 選擇 **[!UICONTROL Shared]** 或 **[!UICONTROL Delivery]** 從 **[!UICONTROL Content type]** 下拉式清單中。
   * **[!UICONTROL Template]** 從 **[!UICONTROL HTML type]** 下拉式清單中選取。
   ![](assets/email_designer_create-template.png)

1. 如有需要，您可以設定將做為範本縮圖的影像。從範本屬性 **[!UICONTROL Thumbnail]** 的標籤中選取它。

   ![](assets/email_designer_create-template_thumbnail.png)

   此縮圖會顯示 **[!UICONTROL Templates]**[在「電子郵件設計師」](../../designing/using/about-email-content-design.md#about-the-email-designer) 首頁的索引標籤中。

1. 關閉 **[!UICONTROL Properties]** 標籤以返回主工作區。
1. 新增您可視需要自訂的元件元件和內容元件。
   >[!NOTE]
   >
   > 您無法在內容範本內插入個人化欄位或條件式內容。
1. 編輯後，儲存範本。

此範本現在可用於電子郵件設計人員建立的任何電子郵件中。從 **[!UICONTROL Templates]**[「電子郵件設計師」](../../designing/using/about-email-content-design.md#about-the-email-designer) 首頁的標籤中選取。

![](assets/content_template_new.png)

### 將內容儲存為範本 {#saving-content-as-template}

使用電子郵件設計工具編輯電子郵件時，您可以直接將該電子郵件的內容儲存為範本。

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. **[!UICONTROL Save as template]** 從「電子郵件設計人員」主工具列中選取。

   ![](assets/email_designer_save-as-template.png)

1. 視需要新增標籤和說明，然後按一下 **[!UICONTROL Save]**。

   ![](assets/email_designer_save-as-template_creation.png)

1. 若要尋找剛建立的範本，請前往 **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**。

1. 若要使用新範本，請從 **[!UICONTROL Templates]**[「電子郵件設計師」](../../designing/using/about-email-content-design.md#about-the-email-designer) 首頁的標籤中選取它。

   ![](assets/content_template_new.png)

