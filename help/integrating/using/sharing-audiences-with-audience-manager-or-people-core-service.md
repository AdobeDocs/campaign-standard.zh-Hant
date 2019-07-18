---
title: 與Audience Manager或People核心服務共用觀眾
seo-title: 與Audience Manager或People核心服務共用觀眾
description: 與Audience Manager或People核心服務共用觀眾
seo-description: 瞭解如何在不同的Adobe Experience Cloud解決方案中匯入或匯出觀眾。
page-status-flag: 從未啓動
uuid: a3701e72-5846-4241-afee-d713 b499 a27 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: working-with-campaign-and-udience-manager-or-ople-core-service
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Sharing audiences with Audience Manager or People core service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importing an audience {#importing-an-audience}

人員核心服務整合可讓您透過技術工作流程直接將觀眾匯入Adobe Campaign，豐富您的資料庫。For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

Importing audiences/segments from People core service in Adobe Campaign can be carried out from the **[!UICONTROL Audiences]** menu only by users connected via IMS (authentication via Adobe ID).

1. Go to the **[!UICONTROL Audiences]** menu.
1. In the action bar, select **[!UICONTROL Create]** to be taken to the screen to create an audience.
1. 指定新觀眾的標籤。
1. Set the audience **[!UICONTROL Type]** to **[!UICONTROL Experience Cloud]** to indicate that the audience being created is an audience that was imported from People core service.
1. From the **[!UICONTROL Name of the shared audience]** field, select the audience to import. 只能匯入區段。不支援精細資料，包括索引鍵值配對、特徵和規則。

   ![](assets/aam_import_audience.png)

1. Select the corresponding **[!UICONTROL Shared Data Source]**.

   If the selected data source is configured to use an encryption algorithm, an additional option offers you the possibility to **[!UICONTROL Force reconciliation with a profile]**. Check this option if the **[!UICONTROL Channel]** field of the data source is set to Email or Mobile (SMS) and if you want to leverage profile data.

   If you do not select the **[!UICONTROL Force reconciliation with a profile]** and if **[!UICONTROL Channel]** is set in AMC Data source to Email or Mobile (SMS) then all the encrypted declared IDs are decrypted. An audience of type **File** with a list of all the email addresses/mobile phone numbers is created/updated. 如此，即使該描述檔不存在於Campaign中，但透過此整合匯入共用觀眾，也不會遺失電子郵件地址/行動電話號碼。請注意，這種對象類型無法直接使用，因為您必須使用工作流程手動進行協調。

1. 確認以建立觀眾。

   然後，觀眾便會透過技術工作流程匯入。它由ID('訪客ID'或「宣告ID」)能夠與描述檔維度協調的記錄組成。並非由Adobe Campaign識別的人員核心服務區段中的ID未匯入。

您的觀眾現在會匯入您的Adobe Campaign資料庫中。從人員核心服務或Audience Manager直接匯入區段時，匯入程序需要24-36小時。在這段期間後，您將能夠在Adobe Campaign中找到並使用您的新觀眾。

>[!NOTE]
>
>如果您要從Adobe Analytics將觀眾匯入Adobe Campaign，這些對象必須先在People Core Service或Audience Manager中共用。此程序需要12-24小時，必須新增至促銷活動的24-36小時。在這種情況下，觀眾共用時間範圍最多可達60小時。For more information on Adobe Analytics audience sharing in People Core service and Audience manager, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exporting an audience {#exporting-an-audience}

An audience can be exported from Adobe Campaign to Audience Manager or People core service using a workflow and the **[!UICONTROL Save audience]** activity.

它可以在新工作流程中進行，而且只能由透過IMS連接的使用者(透過Adobe ID驗證)進行。

1. 從程式、促銷活動或行銷活動清單建立新的工作流程。
1. 使用可用的不同活動，定位一組描述檔。
1. After the targeting, drag and drop a **[!UICONTROL Save audience]** activity into the workflow, then open it.
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Specify the audience using the **[!UICONTROL Shared audience]** field. 在開啓的視窗中，您可以選擇選擇現有對象或建立新對象：

   * 如果您選取現有對象，則只會新增新記錄給對象。
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.
   ![](assets/aam_save_audience_segment_picker.png)

   為了協調並交換，記錄必須具有Adobe Experience Cloud ID('訪客ID'或「宣告ID」)。匯入和匯出對象時，不會忽略未協調的記錄。

1. 若要完成，請按一下畫面右上角的勾號。
1. Select the corresponding **[!UICONTROL Shared Data Source]**.
1. If you like, check the **[!UICONTROL Generate an outbound transition]** box to use the profiles that were exported. 只有可協調的描述檔才會匯出。
1. 確認活動的組態並儲存您的工作流程。
1. 開始您的工作流程，以匯出觀眾。Adobe Campaign和People核心服務之間的同步需要數小時

Adobe Campaign和People核心服務之間的同步需要24-36小時。在這段期間內，您將能夠在People核心服務中找到新受眾，並在其他Adobe Experience Cloud解決方案中重復使用它。For more information on using an Adobe Campaign shared audience in Adobe People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**相關主題：**

* [工作流程](../../automating/using/workflow-data-and-processes.md)
* [觀眾](../../audiences/using/about-audiences.md)

