---
title: 重新目標定位非開啟者
description: 此使用案例顯示如何重新鎖定非開啟者。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cba4e5c6-8acd-47a1-824e-14415e90d451
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---

# 重新定位傳送新傳送給非開啟者的工作流程{#retargeting-delivery-to-non-openers}

您可以傳送電子郵件給客戶，然後傳送簡訊給未開啟郵件的客戶。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立查詢活動{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查詢](../../automating/using/query.md)活動。
1. 連按兩下此活動。
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL email]** 使用運運算元 **[!UICONTROL is not empty]**.
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL no longer contact by email]** 包含值 **[!UICONTROL no]**.
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立電子郵件傳遞{#creating-an-email-delivery}

1. 拖放 [電子郵件傳遞](../../automating/using/email-delivery.md) 在每個區段之後。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple email]** 並按一下 **[!UICONTROL Next]**。
1. 選取 **[!UICONTROL Add an outbound transition without the population]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用每個位置專屬的優惠方案個人化您的電子郵件。如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

## 在查詢活動中鎖定非開啟者{#targeting-non-openers-in-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Execution]**，拖放 [等待](../../automating/using/wait.md) 活動。
1. 在 **[!UICONTROL Duration]**，按一下 ![](assets/duration-icon.png) 並選取一天。
1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中拖放 **[!UICONTROL Query activity]**。
1. 連按兩下此活動。
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Tracking Logs]** 並使用運運算元 **[!UICONTROL exists]**.
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**，拖放 **[!UICONTROL delivery]** 使用運運算元 **[!UICONTROL is equal to]** 並選取傳送作為值。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**，拖放 **[!UICONTROL type]** 並勾選 **[!UICONTROL Open]** 做為值。
1. 在規則之間選取運運算元作為 **[!UICONTROL except]**.
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

## 建立簡訊傳送{#creating-a-sms-delivery}

1. 在每個區段後拖放簡訊傳送。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple sms]** 並按一下 **[!UICONTROL Next]**。
1. 選取簡訊範本並按一下 **[!UICONTROL Next]**.
1. 輸入簡訊屬性並按一下 **[!UICONTROL Next]**.
1. 若要建立簡訊的版面，請按一下 **[!UICONTROL Email Designer]**.
1. 插入元素或選取現有範本。
1. 利用每個位置專屬的優惠，個人化您的SMS。
如需詳細資訊，請參閱 [設計簡訊](../../channels/using/creating-an-sms-message.md) 區段。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

![](assets/wf-retargeting-non-openers.png)

**相關主題：**

* [電子郵件管道](../../channels/using/creating-an-email.md)
