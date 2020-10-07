---
title: 重新鎖定非開啟者
description: 此使用案例說明如何重新定位非開啟者。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---


# Retargeting workflow sending a new delivery to non-openers{#retargeting-delivery-to-non-openers}

您可以先傳送電子郵件給客戶，然後再傳送簡訊給未開啟郵件的客戶。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## Creating a query activity{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查詢](../../automating/using/query.md)活動。
1. 連按兩下此活動。
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no ]**.
1. 按一下 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 在每個區段之後拖 [放電子郵件](../../automating/using/email-delivery.md) 傳送。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple email]** 並按一下 **[!UICONTROL Next]**。
1. 選取 **[!UICONTROL Add an outbound transition without the population]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用每個位置專屬的優惠來個人化您的電子郵件。如需詳細資訊，請參 [閱設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

## 定位查詢活動中的非開啟者{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Wait](../../automating/using/wait.md) activity.
1. 在中 **[!UICONTROL Duration]**，按一下並 ![](assets/duration-icon.png) 選擇一天。
1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中拖放 **[!UICONTROL Query activity]**。
1. 連按兩下此活動。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放 **[!UICONTROL Tracking Logs]** 和運算子 **[!UICONTROL exists]**。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，使用運算子 **[!UICONTROL delivery]** 拖放，並 **[!UICONTROL is equal to]** 選取傳送為值。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，拖放並 **[!UICONTROL type]** 檢查 **[!UICONTROL Open]** 為值。
1. 在規則之間選取運算子 **[!UICONTROL except]**。
1. 按一下 **[!UICONTROL Confirm]**。

## 建立簡訊傳送{#creating-a-sms-delivery}

1. 在每個區段之後拖放簡訊傳送。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple sms]** 並按一下 **[!UICONTROL Next]**。
1. Select an sms template and click **[!UICONTROL Next]**.
1. Enter the sms properties and click **[!UICONTROL Next]**.
1. To create the layout of your sms, click on **[!UICONTROL Email Designer]**.
1. 插入元素或選取現有範本。
1. 使用各個位置專屬的優惠，個人化您的簡訊。
如需詳細資訊，請參閱「設 [計sms」一節](../../channels/using/creating-an-sms-message.md) 。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

![](assets/wf-retargeting-non-openers.png)

**相關主題：**

* [電子郵件通道](../../channels/using/creating-an-email.md)
