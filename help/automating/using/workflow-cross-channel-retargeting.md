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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 2%

---


# 重新定位傳送新傳送給非開啟者的工作流程{#retargeting-delivery-to-non-openers}

您可以先傳送電子郵件給客戶，然後再傳送簡訊給未開啟郵件的客戶。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;按一下並 **[!UICONTROL Create]** 選擇 **[!UICONTROL Workflow]**。
1. 選擇 **[!UICONTROL New Workflow]** 為工作流類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流的屬性並按一下 **[!UICONTROL Create]**。

## 建立查詢活動{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放 [](../../automating/using/query.md) Query活動。
1. 連按兩下活動。
1. 在中 **[!UICONTROL Shortcuts]**，使用運算 **[!UICONTROL Profiles]** 符拖放 **[!UICONTROL email]** 並選擇 **[!UICONTROL is not empty]**。
1. 在中 **[!UICONTROL Shortcuts]**，拖放並 **[!UICONTROL Profiles]** 使用 **[!UICONTROL no longer contact by email]** 值進行選擇 **[!UICONTROL no ]**。
1. 按一下「**[!UICONTROL Confirm]**」。

![](assets/wf-complement-query.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 在每個區段之後拖 [放電子郵件](../../automating/using/email-delivery.md) 傳送。
1. 按一下活動並選 ![](assets/edit_darkgrey-24px.png) 擇以編輯。
1. 選擇 **[!UICONTROL Simple email]** 並按一下 **[!UICONTROL Next]**。
1. 選擇 **[!UICONTROL Add an outbound transition without the population]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Using the Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用每個位置專屬的優惠來個人化您的電子郵件。如需詳細資訊，請參 [閱設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 按一 **[!UICONTROL Preview]** 下以檢查版面。
1. 按一下「**[!UICONTROL Save]**」。

## 定位查詢活動中的非開啟者{#targeting-non-openers-in-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放「等 [待](../../automating/using/wait.md) 」活動。
1. 在中 **[!UICONTROL Duration]**，按一下並 ![](assets/duration-icon.png) 選擇一天。
1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中拖放 **[!UICONTROL Query activity]**。
1. 連按兩下活動。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放 **[!UICONTROL Tracking Logs]** 和運算子 **[!UICONTROL exists]**。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，使用運算子 **[!UICONTROL delivery]** 拖放，並 **[!UICONTROL is equal to]** 選取傳送為值。
1. 在 **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**&#x200B;中，拖放並 **[!UICONTROL type]** 檢查 **[!UICONTROL Open]** 為值。
1. 在規則之間選取運算子 **[!UICONTROL except]**。
1. 按一下「**[!UICONTROL Confirm]**」。

## 建立簡訊傳送{#creating-a-sms-delivery}

1. 在每個區段之後拖放簡訊傳送。
1. 按一下活動並選 ![](assets/edit_darkgrey-24px.png) 擇以編輯。
1. 選擇 **[!UICONTROL Simple sms]** 並按一下 **[!UICONTROL Next]**。
1. 選取簡訊範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入sms屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立簡訊的版面，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用各個位置專屬的優惠，個人化您的簡訊。
如需詳細資訊，請參閱「設 [計sms」一節](../../channels/using/creating-an-sms-message.md) 。
1. 按一 **[!UICONTROL Preview]** 下以檢查版面。
1. 按一下「**[!UICONTROL Save]**」。

![](assets/wf-retargeting-non-openers.png)

**相關主題：**

* [電子郵件通道](../../channels/using/creating-an-email.md)
