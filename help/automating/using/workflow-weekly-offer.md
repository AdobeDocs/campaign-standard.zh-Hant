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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 建立每週二傳送的電子郵件{#creating-email-every-tuesday}

您可以每星期二寄電子郵件給所有客戶，以獲得特別優惠。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立排程器活動{#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Scheduler](../../automating/using/scheduler.md) activity.
1. 連按兩下此活動。
1. 設定傳送的執行。
1. 在 **[!UICONTROL Execution frequency]** 中選取 **[!UICONTROL Weekly]**。
1. 為您的傳送選取 **[!UICONTROL Time]** 及 **[!UICONTROL Repetition frequency]**。
1. 在 **[!UICONTROL Days of the week]** 中選取 **[!UICONTROL Tuesday]**。
1. 指定工作流程的 **[!UICONTROL Start]** 及 **[!UICONTROL Expiration]**　參數。
1. 確認您的活動並儲存您的工作流程。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>若要在特定 **[!UICONTROL Time Zone]** 中開始進行工作流程，請在「**[!UICONTROL Execution options]**」標籤的「時區」欄位中為排程器設定時區。依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

## 建立「查詢」活動{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, to select recipients, drag and drop a [Query](../../automating/using/query.md) activity and double-click it.
1. 在 **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]** 中拖放 **[!UICONTROL Email]**。
1. 選取 **[!UICONTROL is not empty]** 作為運算子。
1. 在 **[!UICONTROL Shortcuts]** > **[!UICONTROL General]** 中，新增設定檔並使用值　**[!UICONTROL No]**　選取　**[!UICONTROL no longer contact by email]**。
1. 按一下 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，拖放電子郵件 [傳送活動](../../automating/using/email-delivery.md) 。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Recurring email]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Use Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用欄位和連結個人化您的電子郵件。
1. 按一下 **[!UICONTROL Save]**。

如需詳細資訊，請參閱[設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

**相關主題：**

* [電子郵件通道](../../channels/using/creating-an-email.md)
