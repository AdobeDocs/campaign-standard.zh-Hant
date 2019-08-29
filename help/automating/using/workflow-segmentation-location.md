---
title: 「Workflow Use-case：區段上的區段」
seo-title: 「Workflow Use-case：區段上的區段」
description: 「Workflow Use-case：區段上的區段」
seo-description: 「Workflow Use-case：區段上的區段」
page-status-flag: 從未啓動
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: '工作流程，使用案例，查詢，分段，傳送 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e77c8a65834009f2f7157d9535ae8e12e59244ff

---


# 工作流程使用案例：位置區段 {#segmentation-on-location}

您可以將定位電子郵件傳送給客戶在當地商店提供的優惠。

1. In **[!UICONTROL Marketing Activities]**，click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. 選擇 **[!UICONTROL New Workflow]** 工作流程類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性，然後按一下 **[!UICONTROL Create]**。

## 透過電子郵件選擇收件者{#selecting-recipients-contactable-via-email}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**，drag and drop a **[!UICONTROL Query activity]**![](assets/query.png).
1. 按兩下活動。
1. In **[!UICONTROL Shortcuts]**、drag and drop **[!UICONTROL Profiles]** and select the field **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**、drag and drop **[!UICONTROL Profiles]** and select the field **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no]**.
1. 按 **[!UICONTROL Confirm]** 兩下。

## 建立分段活動{#creating-a-segmentation-activity}

1. 拖放 **[!UICONTROL Segmentation]** 活動，然後按兩下該活動。
1. 按一下區段，然後開啓轉場以定位第一個城市的目標人群。波士頓。
1. 拖放並 **[!UICONTROL Location]****[!UICONTROL City]** 使用運算元 **[!UICONTROL equals to]** 和值加以選取 **[!UICONTROL Boston]**。
注意：若要觸及所有進入波士頓的人員，不考慮大小寫會解除區分大小寫選項。
1. Click **[!UICONTROL Confirm]**.
1. In **[!UICONTROL List of outbound segments]**，click **[!UICONTROL Add an element]** and click on ![](assets/edit_darkgrey-24px.png) to create a segment target in the cond city.芝加哥。
1. 拖放並 **[!UICONTROL Location]****[!UICONTROL City]** 使用運算元 **[!UICONTROL equals to]** 進行選取，然後輸入 **[!UICONTROL Chicago]** 值。
1. 若要覆蓋所有進入芝加哥的人員，不考慮個案會取消區分區分大小寫選項。
1. Click **[!UICONTROL Confirm]**.

## 建立電子郵件傳送{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**，drag and drop an **[!UICONTROL Email Delivery]** after each segment.
1. 按一下活動，然後選擇 ![](assets/edit_darkgrey-24px.png) 編輯。
1. 選擇 **[!UICONTROL Simple email]** 並按 **[!UICONTROL Next]**&#x200B;一下。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面配置，請按 **[!UICONTROL Email Designer]**&#x200B;一下。
1. 插入元素或選取現有範本。
1. 透過每個位置專屬的優惠，個人化您的電子郵件。

如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。

1. 按一下 **[!UICONTROL Preview]** 以檢查您的版面。
1. Click **[!UICONTROL Save]**.

**相關主題：**

* [查詢活動](../../automating/using/query.md)
* [區段活動](../../automating/using/segmentation.md)
* [電子郵件傳送](../../automating/using/email-delivery.md)
