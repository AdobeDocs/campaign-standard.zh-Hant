---
solution: Campaign Standard
product: campaign
title: 重新鎖定非開啟者
description: 此使用案例說明如何重新定位非開啟者。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---


# 重新定位傳送新傳送給非開啟者的工作流程{#retargeting-delivery-to-non-openers}

您可以先傳送電子郵件給客戶，然後再傳送簡訊給未開啟郵件的客戶。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立查詢活動{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查詢](../../automating/using/query.md)活動。
1. 連按兩下此活動。
1. 在&#x200B;**[!UICONTROL Shortcuts]**&#x200B;中，拖放&#x200B;**[!UICONTROL Profiles]**&#x200B;並使用運算子&#x200B;**[!UICONTROL is not empty]**&#x200B;選擇&#x200B;**[!UICONTROL email]**。
1. 在&#x200B;**[!UICONTROL Shortcuts]**&#x200B;中，拖放&#x200B;**[!UICONTROL Profiles]**&#x200B;並選擇&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;值&#x200B;**[!UICONTROL no ]**。
1. 按一下 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 在每個區段後拖放[電子郵件傳送](../../automating/using/email-delivery.md)。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple email]** 並按一下 **[!UICONTROL Next]**。
1. 選取 **[!UICONTROL Add an outbound transition without the population]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用每個位置的特定選件個人化您的電子郵件。如需詳細資訊，請參閱[設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

## 定位查詢活動中的非開啟者{#targeting-non-openers-in-a-query-activity}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放[等待](../../automating/using/wait.md)活動。
1. 在&#x200B;**[!UICONTROL Duration]**&#x200B;中，按一下![](assets/duration-icon.png)並選擇一天。
1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中拖放 **[!UICONTROL Query activity]**。
1. 連按兩下此活動。
1. 在&#x200B;**[!UICONTROL Shortcuts]**&#x200B;中，拖放&#x200B;**[!UICONTROL Tracking Logs]**&#x200B;和運算子&#x200B;**[!UICONTROL exists]**。
1. 在&#x200B;**[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，使用運算子&#x200B;**[!UICONTROL is equal to]**&#x200B;拖放&#x200B;**[!UICONTROL delivery]**&#x200B;並選擇傳送為值。
1. 在&#x200B;**[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，拖放&#x200B;**[!UICONTROL type]**&#x200B;並將&#x200B;**[!UICONTROL Open]**&#x200B;檢查為值。
1. 選擇規則之間的運算子&#x200B;**[!UICONTROL except]**。
1. 按一下 **[!UICONTROL Confirm]**。

## 建立sms傳送{#creating-a-sms-delivery}

1. 在每個區段之後拖放簡訊傳送。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple sms]** 並按一下 **[!UICONTROL Next]**。
1. 選取sms範本，然後按一下&#x200B;**[!UICONTROL Next]**。
1. 輸入sms屬性，然後按一下&#x200B;**[!UICONTROL Next]**。
1. 若要建立sms的版面，請按一下&#x200B;**[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用各個位置專屬的優惠，個人化您的簡訊。
有關詳細資訊，請參閱[設計sms](../../channels/using/creating-an-sms-message.md)部分。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

![](assets/wf-retargeting-non-openers.png)

**相關主題：**

* [電子郵件通道](../../channels/using/creating-an-email.md)
