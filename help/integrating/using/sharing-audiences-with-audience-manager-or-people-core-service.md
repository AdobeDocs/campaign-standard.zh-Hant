---
title: 與 Audience Manager 或 People 核心服務共用對象
description: 瞭解如何在不同的Adobe Experience Cloud解決方案中匯入或匯出您的對象。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%

---

# 與 Audience Manager 或 People 核心服務共用對象{#sharing-audiences-with-audience-manager-or-people-core-service}

## 匯入對象 {#importing-an-audience}

People核心服務整合可讓您透過技術工作流程，直接將受眾匯入Adobe Campaign，讓您的資料庫更為豐富。 如需People核心服務中對象共用的詳細資訊，請參閱本節 [檔案](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

從Adobe Campaign的People核心服務匯入受眾/區段可從以下網址執行： **[!UICONTROL Audiences]** 功能表僅由透過IMS連線的使用者使用(透過Adobe ID驗證)。

1. 前往 **[!UICONTROL Audiences]** 功能表。
1. 在動作列中，選取 **[!UICONTROL Create]** 將移至畫面以建立對象。
1. 指定新對象的標籤。
1. 設定對象 **[!UICONTROL Type]** 至 **[!UICONTROL Experience Cloud]** 以指出正在建立的對象是從People核心服務匯入的對象。
1. 從 **[!UICONTROL Name of the shared audience]** 欄位中，選取要匯入的對象。 只能匯入區段。 不支援包含鍵值組、特徵和規則的精細資料。

   ![](assets/aam_import_audience.png)

1. 選取對應的 **[!UICONTROL Shared Data Source]**.

   如果選取的資料來源設定為使用加密演演算法，則其他選項可讓您 **[!UICONTROL Force reconciliation with a profile]**. 如果 **[!UICONTROL Channel]** 資料來源的欄位設為「電子郵件」或「行動裝置」（簡訊），以及您是否要利用設定檔資料。

   如果您未選取 **[!UICONTROL Force reconciliation with a profile]** 和if **[!UICONTROL Channel]** 在AMC資料來源中設為電子郵件或行動裝置(SMS)，然後解密所有加密的宣告ID。 型別的對象 **檔案** 以所有電子郵件地址/行動電話號碼的清單建立/更新。 如此一來，透過此整合匯入共用對象時，即使該設定檔不存在於Campaign中，也不會遺失任何電子郵件地址/行動電話號碼。 請注意，此類對象無法直接使用，因為需使用工作流程手動進行調節。

1. 確認以建立對象。

   然後透過技術工作流程匯入對象。 它由能夠與設定檔維度協調的ID （「訪客ID」或「宣告ID」）記錄組成。 Adobe Campaign無法辨識的People核心服務區段之ID不會匯入。

您的對象現在已匯入Adobe Campaign資料庫。 直接從People核心服務或Audience Manager匯入區段時，匯入程式需要24到36小時才能同步。 在此期間後，您將能夠在Adobe Campaign中尋找並使用新對象。

>[!NOTE]
>
>如果您要將對象從Adobe Analytics匯入至Adobe Campaign，首先需要在People核心服務或Audience Manager中共用這些對象。 此程式需要12到24小時，必須將其新增到與Campaign的24到36小時同步中。 在該特定情況下，對象共用時間範圍最長可達60小時。 如需在People核心服務和Audience Manager中分享Adobe Analytics受眾的詳細資訊，請參閱本節 [檔案](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

## 匯出對象 {#exporting-an-audience}

Adobe Campaign Audience Manager您可以使用工作流程和 **[!UICONTROL Save audience]** 活動。

它可在新的工作流程中執行，且僅能由透過IMS (透過Adobe ID驗證)連線的使用者執行。

1. 從方案、行銷活動或行銷活動清單建立新的工作流程。
1. 使用可用的不同活動，將目標設定檔集合。
1. 目標定位後，拖放 **[!UICONTROL Save audience]** 活動進入工作流程，然後開啟它。
1. 選取 **[!UICONTROL Share in Adobe Experience Cloud]**。

   ![](assets/aam_save_audience_activity.png)

1. 使用「 」指定對象 **[!UICONTROL Shared audience]** 欄位。 在開啟的視窗中，您可以選擇選取現有對象或建立新對象：

   * 如果您選取現有對象，則只有新記錄會新增至對象。
   * 若要將設定檔清單匯出至新受眾，請完成 **[!UICONTROL Segment name]** 欄位，然後按一下 **[!UICONTROL Create]** 再選取新建立的對象。

   ![](assets/aam_save_audience_segment_picker.png)

   為了進行調解和交換，記錄必須具有Adobe Experience Cloud ID （「訪客ID」或「宣告ID」）。 匯入和匯出受眾時，會忽略未調解的記錄。

1. 若要完成，請按一下畫面右上方的核取記號。
1. 選取對應的 **[!UICONTROL Shared Data Source]**.
1. 您也可以勾選 **[!UICONTROL Generate an outbound transition]** 方塊以使用已匯出的輪廓。 只會匯出可調解的設定檔。
1. 確認活動的設定並儲存工作流程。
1. 開始工作流程以匯出您的對象。 Adobe Campaign與People核心服務之間的同步處理可能需要數小時的時間

Adobe Campaign與People核心服務之間的同步作業需要24到36小時的時間。 在此期間後，您就能在People核心服務中尋找新的受眾，並在其他Adobe Experience Cloud解決方案中重複使用。 如需在Adobe People核心服務中使用Adobe Campaign共用對象的詳細資訊，請參閱此 [檔案](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html).

**相關主題：**

* [工作流程](../../automating/using/get-started-workflows.md)
* [對象](../../audiences/using/about-audiences.md)
