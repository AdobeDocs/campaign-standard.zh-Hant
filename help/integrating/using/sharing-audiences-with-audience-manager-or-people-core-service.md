---
solution: Campaign Standard
product: campaign
title: 與 Audience Manager 或 People 核心服務共用閱聽眾
description: 了解如何在不同的Adobe Experience Cloud解決方案中匯入或匯出您的對象。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: 人員核心服務整合
role: Data Architect
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 2%

---

# 與 Audience Manager 或 People 核心服務共用閱聽眾{#sharing-audiences-with-audience-manager-or-people-core-service}

## 匯入對象{#importing-an-audience}

People核心服務整合可讓對象透過技術工作流程直接匯入Adobe Campaign，以豐富您的資料庫。 如需「People」核心服務中受眾共用的詳細資訊，請參閱本[檔案](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

只有透過IMS連線的使用者(透過Adobe ID驗證)，才能從&#x200B;**[!UICONTROL Audiences]**&#x200B;功能表從Adobe Campaign的「People」核心服務匯入對象/區段。

1. 前往&#x200B;**[!UICONTROL Audiences]**&#x200B;功能表。
1. 在動作列中，選取要進入畫面以建立對象的&#x200B;**[!UICONTROL Create]**。
1. 指定新對象的標籤。
1. 將對象&#x200B;**[!UICONTROL Type]**&#x200B;設為&#x200B;**[!UICONTROL Experience Cloud]**，以指出所建立的對象是從People核心服務匯入的對象。
1. 從&#x200B;**[!UICONTROL Name of the shared audience]**&#x200B;欄位中，選取要匯入的對象。 只能匯入區段。 不支援包含機碼值組、特徵和規則的精細資料。

   ![](assets/aam_import_audience.png)

1. 選擇相應的&#x200B;**[!UICONTROL Shared Data Source]**。

   如果選定的資料源配置為使用加密算法，則附加的選項可提供&#x200B;**[!UICONTROL Force reconciliation with a profile]**。 如果資料來源的&#x200B;**[!UICONTROL Channel]**&#x200B;欄位設為「電子郵件」或「行動」(SMS)，且您想要運用設定檔資料，請核取此選項。

   如果您未選取&#x200B;**[!UICONTROL Force reconciliation with a profile]**，且在AMC資料來源中將&#x200B;**[!UICONTROL Channel]**&#x200B;設為電子郵件或行動(SMS)，則所有加密的宣告ID都會解密。 建立/更新&#x200B;**檔案**&#x200B;類型的受眾，其中包含所有電子郵件地址/行動電話號碼的清單。 如此一來，透過此整合匯入共用對象時，即使該設定檔不存在，也不會遺失電子郵件地址/行動電話號碼。 請注意，此類型的對象無法直接使用，因為需要使用工作流程手動協調。

1. 確認建立對象。

   然後會透過技術工作流程匯入對象。 它由可與設定檔維度調解ID（「訪客ID」或「宣告ID」）的記錄組成。 來自People核心服務區段且Adobe Campaign未辨識的ID不會匯入。

您的對象現在已匯入Adobe Campaign資料庫。 從People核心服務或Audience Manager直接匯入區段時，匯入程式需要24到36小時進行同步。 在此期間後，您將能在Adobe Campaign中尋找和使用您的新對象。

>[!NOTE]
>
>如果您要將對象從Adobe Analytics匯入Adobe Campaign，必須先在People核心服務或Audience Manager中共用這些對象。 此程式需要12到24小時，必須與Campaign同步，將其新增至24到36小時。 在該特定情況下，受眾共用時間範圍最多可為60小時。 如需People核心服務與Audience Manager中Adobe Analytics受眾共用的詳細資訊，請參閱本[檔案](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

## 匯出對象{#exporting-an-audience}

對象可使用工作流程和&#x200B;**[!UICONTROL Save audience]**&#x200B;活動，從Adobe Campaign匯出至Audience Manager或人員核心服務。

這只能由透過IMS連線的使用者(透過Adobe ID驗證)執行。

1. 從方案、行銷活動或行銷活動清單建立新的工作流程。
1. 使用可用的不同活動，鎖定一組設定檔。
1. 鎖定目標後，將&#x200B;**[!UICONTROL Save audience]**&#x200B;活動拖放至工作流程中，然後開啟。
1. 選取 **[!UICONTROL Share in Adobe Experience Cloud]**。

   ![](assets/aam_save_audience_activity.png)

1. 使用&#x200B;**[!UICONTROL Shared audience]**&#x200B;欄位指定對象。 在開啟的視窗中，您可以選擇選取現有對象或建立新對象：

   * 如果您選取現有對象，則只會將新記錄新增至對象。
   * 若要將您的設定檔清單匯出至新對象，請填入&#x200B;**[!UICONTROL Segment name]**&#x200B;欄位，然後在選取新建立的對象前按一下&#x200B;**[!UICONTROL Create]**。

   ![](assets/aam_save_audience_segment_picker.png)

   為了調解和交換，記錄必須有Adobe Experience Cloud ID（「Visitor ID」或「Delaced ID」）。 匯入和匯出對象時，會忽略未調解的記錄。

1. 要完成，請按一下螢幕右上方的複選標籤。
1. 選擇相應的&#x200B;**[!UICONTROL Shared Data Source]**。
1. 如果您喜歡，請核取&#x200B;**[!UICONTROL Generate an outbound transition]**&#x200B;方塊以使用已匯出的設定檔。 只會匯出可調解的設定檔。
1. 確認活動的設定並儲存工作流程。
1. 啟動工作流程以匯出對象。 Adobe Campaign與People核心服務的同步可能需要數小時

Adobe Campaign與People核心服務的同步需要24到36小時。 在此期間之後，您將能在People核心服務中尋找新的受眾，並在其他Adobe Experience Cloud解決方案中重複使用。 如需在「Adobe人員」核心服務中使用Adobe Campaign共用受眾的詳細資訊，請參閱本[檔案](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html)。

**相關主題：**

* [工作流程](../../automating/using/get-started-workflows.md)
* [對象](../../audiences/using/about-audiences.md)
