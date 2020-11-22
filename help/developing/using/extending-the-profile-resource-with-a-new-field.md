---
solution: Campaign Standard
product: campaign
title: 使用新欄位擴充設定檔資源
description: 瞭解如何擴充設定檔資源。
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 100%

---


# 使用新欄位擴充設定檔資源{#extending-the-profile-resource-with-a-new-field}

## 關於擴充設定檔 {#about-extending-profiles}

此使用案例詳細說明如何使用專用欄位擴充設定檔和測試設定檔。

在此處，我們想使用登錄頁面，以新欄位更新我們的設定檔，然後以符合其興趣的電子報來定位設定檔。

要執行此操作，請遵循下列步驟：

* [步驟 1：擴充設定檔資源](#step-1--extend-the-profile-resource)
* [步驟 2：擴充測試設定檔](#step-2--extend-the-test-profile)
* [步驟 3：發佈自訂資源](#step-3--publish-your-custom-resource)
* [步驟 4：使用工作流程更新和定位設定檔](#step-4--update-and-target-profiles-with-a-workflow)

之後會將下列欄位新增至我們的設定檔，並可在傳送中定位：

![](assets/schema_extension_uc20.png)

相關主題：

* [關於自訂資源](../../developing/using/data-model-concepts.md)
* [管理設定檔](../../audiences/using/about-profiles.md)
* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)

## 步驟 1：擴充設定檔資源 {#step-1--extend-the-profile-resource}

若要為設定檔建立新的&#x200B;**興趣**&#x200B;欄位，您必須先擴充現成的 **[!UICONTROL Profiles (profile)]** 資源。

1. 從進階功能表，透過 Adobe Campaign 標誌，依序選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** 及 **[!UICONTROL Custom resources]**。
1. 如果尚未擴充 **[!UICONTROL Profiles]** 資源，請按一下 **[!UICONTROL Create]**。
1. 選取 **[!UICONTROL Extend an existing resource]** 選項。
1. 選取 **[!UICONTROL Profile (profile)]** 資源。
1. 按一下 **[!UICONTROL Create]**。

   ![](assets/schema_extension_uc5.png)

1. 在 **[!UICONTROL Fields]** 索引標籤的 **[!UICONTROL Data structure]** 類別中，按一下 **[!UICONTROL Create element]**。

   >[!NOTE]
   >
   >請注意，如果您已將 **[!UICONTROL Profile]** 資源擴充至之前的用途，則可以按一下&#x200B;**[!UICONTROL Add field]** 開始進行此步驟。

   ![](assets/schema_extension_uc6.png)

1. 新增 **[!UICONTROL Label]** 及 **[!UICONTROL ID]**。選取 **[!UICONTROL Text]** 類型並按一下 **[!UICONTROL Add]**。

   ![](assets/schema_extension_uc9.png)

1. 若要設定欄位，請在 **[!UICONTROL Fields]** 下拉式清單的 **[!UICONTROL Data structure]** 索引標籤中，從先前建立的欄位依序按一下 ![](assets/schema_extension_uc8.png) 及 ![](assets/schema_extension_uc7.png)。
1. 在此範例中，我們要新增特定值，要執行此操作，請按一下 **[!UICONTROL Specify a list of authorized values]**。

   ![](assets/schema_extension_uc10.png)

1. 按一下 **[!UICONTROL Add an element]**，然後視需要新增值，方法是新增 **[!UICONTROL Label]** 及 **[!UICONTROL ID]** 並按一下 **[!UICONTROL Add]**。

   在此處，我們將建立 Books、Exhibitions、Movies 及 N/A 值，讓設定檔從這些選項進行選取。

   ![](assets/schema_extension_uc11.png)

1. 若要在 **[!UICONTROL Profile]** 畫面中新增此欄位，請按一下 **[!UICONTROL Screen definition]** 索引標籤。
1. 在 **[!UICONTROL Detail screen configuration]** 下拉式清單中，按一下 **[!UICONTROL Add a personalized fields section]** 並按 **[!UICONTROL Create element]**。

   ![](assets/schema_extension_uc12.png)

1. 選取 **[!UICONTROL Type]**。此處，我們要新增輸入欄位。之後，選取您先前建立的欄位並按一下 **[!UICONTROL Add]**。

   ![](assets/schema_extension_uc2.png)

1. 若要新增分隔符號，以便更妥善地組織您的設定檔視窗，請按一下 **[!UICONTROL Create an element]** 並從 **[!UICONTROL Type]** 下拉式清單中選取 **[!UICONTROL Separator]**。

   ![](assets/schema_extension_uc19.png)

您的欄位現已設定完畢。現在，我們需要將它擴充至測試設定檔。

>[!NOTE]
>
>如果您不需要擴充測試設定檔資源，可跳至「發佈」步驟。

## 步驟 2：擴充測試設定檔 {#step-2--extend-the-test-profile}

若要測試新建立的欄位是否已正確設定，您可以將傳遞傳送至測試設定檔，藉以測試欄位。首先，需要對測試設定檔執行新領域。

1. 從進階功能表，透過 Adobe Campaign 標誌，依序選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** 及 **[!UICONTROL Custom resources]**。
1. 如果尚未擴充 **[!UICONTROL Profiles]** 資源，請按一下 **[!UICONTROL Create]**。
1. 選取 **[!UICONTROL Extend an existing resource]** 選項。
1. 選取 **[!UICONTROL Test profile (seedMember)]** 資源。
1. 按一下 **[!UICONTROL Create]**。

   ![](assets/schema_extension_uc13.png)

1. 在 **[!UICONTROL Data structure]** 索引標籤中，按一下 **[!UICONTROL Create element]**。

   ![](assets/schema_extension_uc15.png)

1. 選取您先前建立的資源欄位並按一下 **[!UICONTROL Add]**。

   ![](assets/schema_extension_uc16.png)

1. 從步驟 11 到 13 執行與上述延伸設定檔步驟相同的步驟，將此欄位新增至 **[!UICONTROL Test profile]** 畫面中。
1. 按一下 **[!UICONTROL Save]**。

現在，設定檔和測試設定檔都可使用您的新欄位。若要正確設定，您必須發佈自訂資源。

## 步驟 3：發佈自訂資源 {#step-3--publish-your-custom-resource}

若要套用對資源執行的變更以及使用該變更，您必須執行資料庫更新。

1. 從進階功能表選取 **Administration** > **Development** 及 **Publishing**。
1. 依預設，會核取 **[!UICONTROL Determine modifications since the last publication]** 選項，這代表僅會套用自上次更新後所進行的變更。

   ![](assets/schema_extension_uc14.png)

1. 按一下 **[!UICONTROL Prepare publication]** 以啟動將更新資料庫的分析。
1. 發佈完成後，按一下 **Publish** 按鈕以套用新的設定。

   ![](assets/schema_extension_uc17.png)

1. 發佈後，每個資源的 **Summary** 窗格會指出狀態現在為 **Published** 並指定上次發佈的日期。

   ![](assets/schema_extension_uc18.png)

1. 選取 **[!UICONTROL Profiles]** 索引標籤並按一下 **[!UICONTROL New]**，檢視變更是否已正確實作。

   ![](assets/schema_extension_uc20.png)

例如，您的新資源欄位現在已準備好在傳送中使用和定位。

## 步驟 4：使用工作流程更新和定位設定檔 {#step-4--update-and-target-profiles-with-a-workflow}

若要使用新自訂欄位的資料更新設定檔，您可以使用 **[!UICONTROL Profile acquisition]** 範本建立登錄頁面。如需登錄頁面的詳細資訊，請參閱[本區段](../../channels/using/getting-started-with-landing-pages.md)。

在此處，我們想要定位未填入此欄位的工作流程設定檔。他們會收到電子郵件，要求他們更新設定檔，以接收個人化的電子報和優惠。然後，每個設定檔都會收到個人化電子報，內容視其選取的興趣而定。

首先，我們需要建立登錄頁面，以更新目標設定檔&#x200B;**興趣**&#x200B;欄位：

1. 從 **[!UICONTROL Marketing activities]** 按一下 **[!UICONTROL Create]**，然後選取 **[!UICONTROL Landing page]**。
1. 選取登錄頁面類型。因為我們要更新設定檔，請選取 **[!UICONTROL Profile acquisition]**。
1. 按一下 **[!UICONTROL Create]**。
1. 按一下 **[!UICONTROL Content]** 區塊以開始編輯登錄頁面的內容。

   ![](assets/schema_extension_uc21.png)

1. 視需要自訂您的登錄頁面。
1. 按一下針對您的設定檔所設定的欄位，以便在興趣之間做出選取。在左窗格中，選取您先前建立的&#x200B;**興趣**&#x200B;自訂資源。

   ![](assets/schema_extension_uc22.png)

1. 儲存登錄頁面並加以測試，以檢查欄位是否已正確設定。
1. 當您的登錄頁面準備就緒時，按一下 **[!UICONTROL Publish]**。

您的登錄頁面現已準備就緒。若要更新設定檔，您可以建立工作流程，然後根據所選的興趣傳送特殊優惠。

1. 在 **[!UICONTROL Marketing activities]** 索引標籤中，按一下 **[!UICONTROL Create]**，然後選取 **[!UICONTROL Workflow]**。
1. 拖放 **[!UICONTROL Query]** 活動，以定位您需要的設定檔或對象。
1. 拖放 **[!UICONTROL Email delivery]** 活動，以開始設定包含登錄頁面連結的電子郵件。選取 **[!UICONTROL Add an outbound transition with the population]**。

   ![](assets/schema_extension_uc3.png)

1. 視需要建立和設計您的電子郵件。如需電子郵件個人化的詳細資訊，請參閱[本區段](../../designing/using/quick-start.md)。
1. 新增按鈕至您的電子郵件，將設定檔重新導向至您的登錄頁面。
1. 選取新增的按鈕，然後按一下左窗格 **[!UICONTROL Link]** 區段中的 ![](assets/schema_extension_uc7.png)。

   ![](assets/schema_extension_uc23.png)

1. 在 **[!UICONTROL Insert link]** 視窗中，從 **[!UICONTROL Landing page]** 下拉式清單中選取 **[!UICONTROL Link type]**，然後選取先前建立的登錄頁面。

   ![](assets/schema_extension_uc24.png)

1. 按一下 **[!UICONTROL Save]**。您的電子郵件現已準備就緒，您可以返回工作流程。
1. 新增 **[!UICONTROL Wait]** 活動，讓您的設定檔有時間填入登錄頁面。
1. 新增 **[!UICONTROL Segmentation]** 活動以依據外站轉變的&#x200B;**興趣**&#x200B;進行分割。
1. 為每個&#x200B;**興趣**&#x200B;建立外站區段。

   ![](assets/schema_extension_uc4.png)

1. 在每次轉變後新增 **[!UICONTROL Email delivery]** 活動，並根據所選的&#x200B;**興趣**&#x200B;建立個人化電子郵件。
1. 完成設定之後，啟動工作流程。

   ![](assets/schema_extension_uc25.png)

設定檔現在會收到電子郵件，要求他們填寫此「興趣」欄位，之後會根據所選的值傳送個人化電子郵件。
