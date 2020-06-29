---
title: 建立每週傳送
description: 此使用案例說明如何建立每週傳送。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 3%

---


# 建立每週二傳送的電子郵件{#creating-email-every-tuesday}

您可以每星期二寄電子郵件給所有客戶以索取特別優惠。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;按一下並 **[!UICONTROL Create]** 選擇 **[!UICONTROL Workflow]**。
1. 選擇 **[!UICONTROL New Workflow]** 為工作流類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流的屬性並按一下 **[!UICONTROL Create]**。

## 建立調度程式活動{#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放排程 [器活動](../../automating/using/scheduler.md) 。
1. 連按兩下活動。
1. 設定傳送的執行。
1. 在中 **[!UICONTROL Execution frequency]**，選擇 **[!UICONTROL Weekly]**。
1. 為您的 **[!UICONTROL Time]** 交貨選 **[!UICONTROL Repetition frequency]** 擇和。
1. 在中 **[!UICONTROL Days of the week]**，選擇 **[!UICONTROL Tuesday]**。
1. 指定工 **[!UICONTROL Start]** 作流程 **[!UICONTROL Expiration]** 的和參數。
1. 確認您的活動並儲存您的工作流程。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>要在特定位置啟動工作流，請 **[!UICONTROL Time Zone]**&#x200B;在頁籤&#x200B;**[!UICONTROL Execution options]**&#x200B;的「時區」欄位中為調度程式設定時區。 依預設，選取的時區是工作流屬性中定義的時區(請參 [閱建立工作流](../../automating/using/building-a-workflow.md))。

## 建立查詢活動{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，若要選取收件者，請拖放 [Query](../../automating/using/query.md) 活動，然後按兩下它。
1. 在 **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]**&#x200B;中拖放 **[!UICONTROL Email]**。
1. 選擇 **[!UICONTROL is not empty]** 作為運算子。
1. 在 **[!UICONTROL Shortcuts]** > **[!UICONTROL General]**&#x200B;中，新增描述檔並 **[!UICONTROL no longer contact by email]** 使用值選取 **[!UICONTROL No]**。
1. 按一下「**[!UICONTROL Confirm]**」。

![](assets/wf-complement-query.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，拖放電子郵件 [傳送活動](../../automating/using/email-delivery.md) 。
1. 按一下活動並選 ![](assets/edit_darkgrey-24px.png) 擇以編輯。
1. 選擇 **[!UICONTROL Recurring email]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Use Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用欄位和連結個人化您的電子郵件。
1. 按一下「**[!UICONTROL Save]**」。

如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

**相關主題：**

* [電子郵件通道](../../channels/using/creating-an-email.md)
