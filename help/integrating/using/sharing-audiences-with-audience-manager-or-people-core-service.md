---
title: 與 Audience Manager 或 People 核心服務共用閱聽眾
description: 瞭解如何在不同的Adobe Experience Cloud解決方案中匯入或匯出您的觀眾。
page-status-flag: never-activated
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 2%

---


# 與 Audience Manager 或 People 核心服務共用閱聽眾{#sharing-audiences-with-audience-manager-or-people-core-service}

## 匯入對象 {#importing-an-audience}

人員核心服務整合可讓受眾透過技術工作流程直接匯入Adobe Campaign，以豐富您的資料庫。 如需「人員」核心服務中觀眾分享的詳細資訊，請參閱本 [檔案](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

從Adobe Campaign的「人物」核心服務匯入觀眾／區段，只能由透過IMS連線的 **[!UICONTROL Audiences]** 使用者（透過Adobe ID驗證）執行。

1. 前往功能 **[!UICONTROL Audiences]** 表。
1. 在動作列中，選 **[!UICONTROL Create]** 取要移至畫面以建立觀眾。
1. 指定新對象的標籤。
1. 將觀眾設 **[!UICONTROL Type]** 定為 **[!UICONTROL Experience Cloud]** 指出所建立的觀眾是從People核心服務匯入的觀眾。
1. 從欄位 **[!UICONTROL Name of the shared audience]** 中，選取要匯入的對象。 只能匯入區段。 不支援精細資料，包括索引鍵值配對、特徵和規則。

   ![](assets/aam_import_audience.png)

1. 選擇相應的 **[!UICONTROL Shared Data Source]**。

   如果選取的資料來源已設定為使用加密演算法，則另一個選項可讓您有可能 **[!UICONTROL Force reconciliation with a profile]**。 如果資料來源的欄 **[!UICONTROL Channel]** 位已設為「電子郵件」或「行動」(SMS)，而且您想要運用描述檔資料，請勾選此選項。

   如果您未選取， **[!UICONTROL Force reconciliation with a profile]** 且在AMC資 **[!UICONTROL Channel]** 料來源中設定為「電子郵件」或「行動」(SMS)，則所有加密的宣告ID都會解密。 會建立／更 **新包含** 所有電子郵件地址／行動電話號碼清單的「檔案」類型對象。 如此，透過此整合匯入共用對象時，不會遺失電子郵件地址／行動電話號碼，即使該描述檔不存在於Campaign中亦然。 請注意，此類型的觀眾無法直接使用，因為需要使用工作流程手動調節觀眾。

1. 確認建立觀眾。

   然後，觀眾會透過技術工作流程匯入。 它由記錄組成，其中ID（&#39;訪客ID&#39;或&#39;Declared ID&#39;）可與描述檔維度協調。 不會匯入Adobe Campaign未識別之「人員」核心服務區段的ID。

您的觀眾現在已匯入Adobe Campaign資料庫。 從People核心服務或Audience Manager直接匯入區段時，匯入程式需要24-36小時才能同步。 在這段期間後，您就可以在Adobe Campaign中尋找並使用您的新觀眾。

>[!NOTE]
>
>如果您要將觀眾從Adobe Analytics匯入Adobe Campaign，這些觀眾必須先在People Core Service或Audience Manager中共用。 此程式需要12-24小時，這必須新增至與Campaign同步的24-36小時。 在此特定情況下，觀眾分享的時間最長可達60小時。 如需People Core服務和Audience Manager中Adobe Analytics觀眾分享的詳細資訊，請參閱本文 [件](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

## 匯出觀眾 {#exporting-an-audience}

觀眾可以使用工作流程和活動從Adobe Campaign匯出至Audience Manager或People核心服 **[!UICONTROL Save audience]** 務。

它可在新的工作流程中執行，而且只能由透過IMS（透過Adobe ID驗證）連線的使用者執行。

1. 從方案、促銷活動或行銷活動清單建立新的工作流程。
1. 使用可用的不同活動，鎖定一組描述檔。
1. 定位後，將活動拖放至工 **[!UICONTROL Save audience]** 作流程中，然後開啟它。
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. 使用欄位指定對 **[!UICONTROL Shared audience]** 像。 在開啟的視窗中，您可以選擇選取現有對象或建立新對象：

   * 如果您選取現有對象，則只會將新記錄新增至對象。
   * 若要將個人檔案清單匯出至新對象，請填妥欄 **[!UICONTROL Segment name]** 位，然後按一 **[!UICONTROL Create]** 下，再選取新建立的對象。
   ![](assets/aam_save_audience_segment_picker.png)

   為了進行協調和交換，這些記錄必須有Adobe Experience Cloud ID（「訪客ID」或「宣告的ID」）。 匯入和匯出對象時，不協調的記錄會被忽略。

1. 若要完成，請按一下位於螢幕右上角的核取標籤。
1. 選擇相應的 **[!UICONTROL Shared Data Source]**。
1. 如果您喜歡，請勾選 **[!UICONTROL Generate an outbound transition]** 該框以使用導出的配置檔案。 僅導出可調節的配置檔案。
1. 確認活動的設定並儲存您的工作流程。
1. 啟動您的工作流程以匯出您的觀眾。 Adobe Campaign和People核心服務之間的同步化可能需要數小時

Adobe Campaign和People核心服務之間的同步化需要24-36小時。 在這段期間後，您將可在People核心服務中尋找新的受眾，並在其他Adobe Experience Cloud解決方案中重複使用。 如需在Adobe People核心服務中使用Adobe Campaign共用觀眾的詳細資訊，請參閱本文 [件](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-audience-create.html)。

**相關主題：**

* [工作流程](../../automating/using/get-started-workflows.md)
* [觀眾](../../audiences/using/about-audiences.md)

