---
title: 「Workflow Use-case：重新定向非opervers」
seo-title: 「Workflow Use-case：重新定向非opervers」
description: 「Workflow Use-case：重新定向非opervers」
seo-description: 「Workflow Use-case：重新定向非opervers」
page-status-flag: 從未啓動
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: '工作流程，使用案例，查詢，等待，傳送 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 035726bbd3112058b9a89525a861521bc3b9867e

---


# 工作流程使用案例：重新定位工作流程，將新傳送傳送至非opervers{#retargeting-delivery-to-non-openers}

您可以傳送電子郵件給客戶，然後傳送電子郵件給未開啓郵件的人。

1. In **[!UICONTROL Marketing Activities]**，click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. 選擇 **[!UICONTROL New Workflow]** 工作流程類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性，然後按一下 **[!UICONTROL Create]**。

## 建立查詢活動{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**，drag and drop a **[!UICONTROL Query activity]**![](assets/query.png).
1. 按兩下活動。
1. In **[!UICONTROL Shortcuts]**、drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**、drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no ]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 拖放每個區段後的****[!UICONTROL Email delivery]電子郵件傳送。
1. 按一下活動，然後選擇 ![](assets/edit_darkgrey-24px.png) 編輯。
1. 選擇 **[!UICONTROL Simple email]** 並按 **[!UICONTROL Next]**&#x200B;一下。
1. 選擇 **[!UICONTROL Add an outbound transition without the population]** 並按 **[!UICONTROL Next]**&#x200B;一下。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面配置，請按 **[!UICONTROL Using the Email Designer]**&#x200B;一下。
1. 插入元素或選取現有範本。
1. 透過每個位置專屬的選件個人化您的電子郵件。如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。
1. 按一下 **[!UICONTROL Preview]** 以檢查您的版面。
1. Click **[!UICONTROL Save]**.

## 在查詢活動中定位非Opener{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**，drag and drop a **[!UICONTROL Wait activity]**![](assets/wait.png).
1. In **[!UICONTROL Duration]**，click on ![](assets/duration-icon.png) and select one day.
1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**，drag and drop a **[!UICONTROL Query activity]**![](assets/query.png).
1. 按兩下活動。
1. In **[!UICONTROL Shortcuts]**、drag and drop **[!UICONTROL Tracking Logs]** and with the operator **[!UICONTROL exists]**.
1. 在 **[!UICONTROL Shortcuts]**&gt;中 **[!UICONTROL Delivery]****[!UICONTROL delivery]** ，使用運算元 **[!UICONTROL is equal to]** 拖放，然後將傳送選擇為值。
1. 在 **[!UICONTROL Shortcuts]**&gt;中 **[!UICONTROL Delivery]**&#x200B;拖放 **[!UICONTROL type]** 並檢查 **[!UICONTROL Open]** 值。
1. 在規則之間選取運算子 **[!UICONTROL except]**。
1. Click **[!UICONTROL Confirm]**.

## 建立SMS傳送{#creating-a-sms-delivery}

1. 在每個區段後拖放SMS傳送。
1. 按一下活動，然後選擇 ![](assets/edit_darkgrey-24px.png) 編輯。
1. 選擇 **[!UICONTROL Simple sms]** 並按 **[!UICONTROL Next]**&#x200B;一下。
1. 選取sms範本並按一下 **[!UICONTROL Next]**。
1. 輸入sms屬性並按一下 **[!UICONTROL Next]**。
1. 若要建立sms的版面配置，請按 **[!UICONTROL Email Designer]**&#x200B;一下。
1. 插入元素或選取現有範本。
1. 使用特定位置的優惠，個人化您的簡訊。
如需詳細資訊，請參閱 [設計SMS](../../channels/using/creating-an-sms-message.md)。
1. 按一下 **[!UICONTROL Preview]** 以檢查您的版面。
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**相關主題：**

* [Query](../../automating/using/query.md)
* [SMS傳送](../../automating/using/sms-delivery.md)
* [電子郵件傳送](../../automating/using/email-delivery.md)
* [電子郵件頻道](../../channels/using/creating-an-email.md)
