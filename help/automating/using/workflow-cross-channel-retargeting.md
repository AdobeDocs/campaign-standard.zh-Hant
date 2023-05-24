---
title: 重新目標定位非開啟者
description: 此用例說明如何重新定位非開啟者。
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

# 重新確定向非開啟者發送新交貨的工作流的目標{#retargeting-delivery-to-non-openers}

您可以向客戶發送電子郵件，然後向未開啟郵件的客戶發送簡訊。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立查詢活動{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查詢](../../automating/using/query.md)活動。
1. 連按兩下此活動。
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 選擇 **[!UICONTROL email]** 和運算子 **[!UICONTROL is not empty]**。
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 選擇 **[!UICONTROL no longer contact by email]** 值 **[!UICONTROL no ]**。
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立電子郵件傳遞{#creating-an-email-delivery}

1. 拖放 [電子郵件傳遞](../../automating/using/email-delivery.md) 段後。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple email]** 並按一下 **[!UICONTROL Next]**。
1. 選取 **[!UICONTROL Add an outbound transition without the population]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用特定於每個位置的服務個性化您的電子郵件。有關詳細資訊，請參閱 [設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

## 將查詢活動中的非開啟者作為目標{#targeting-non-openers-in-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Execution]**，拖放 [等待](../../automating/using/wait.md) 的子菜單。
1. 在 **[!UICONTROL Duration]**，按一下 ![](assets/duration-icon.png) 選擇一天。
1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中拖放 **[!UICONTROL Query activity]**。
1. 連按兩下此活動。
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Tracking Logs]** 和操作員 **[!UICONTROL exists]**。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**，拖放 **[!UICONTROL delivery]** 和運算子 **[!UICONTROL is equal to]** 並選擇交貨值。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**，拖放 **[!UICONTROL type]** 檢查 **[!UICONTROL Open]** 值。
1. 選擇規則之間的運算子為 **[!UICONTROL except]**。
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

## 建立簡訊傳遞{#creating-a-sms-delivery}

1. 在每段後拖放簡訊遞送。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple sms]** 並按一下 **[!UICONTROL Next]**。
1. 選擇簡訊模板，然後按一下 **[!UICONTROL Next]**。
1. 輸入sms屬性，然後按一下 **[!UICONTROL Next]**。
1. 要建立sms的佈局，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用特定於每個位置的服務個性化您的簡訊。
有關詳細資訊，請參閱 [設計簡訊](../../channels/using/creating-an-sms-message.md) 的子菜單。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

![](assets/wf-retargeting-non-openers.png)

**相關主題：**

* [電子郵件通道](../../channels/using/creating-an-email.md)
