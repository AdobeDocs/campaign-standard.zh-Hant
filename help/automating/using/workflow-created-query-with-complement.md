---
title: 「Workflow Use-case：建立具有輔助功能的傳送內容」
seo-title: 「Workflow Use-case：建立具有輔助功能的傳送內容」
description: 「Workflow Use-case：建立具有輔助功能的傳送內容」
seo-description: 「Workflow Use-case：建立具有輔助功能的傳送內容」
page-status-flag: 從未啓動
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 執行活動
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: 工作流程、使用案例、分段
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# 工作流程使用案例：建立具有輔助功能的傳送 {#deliveries-with-complement}

您可以傳送電子郵件給客戶：一個面向不到一年前建立的客戶，為客戶一年前建立的客戶一次建立。

1. In **[!UICONTROL Marketing Activities]**，click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. 選擇 **[!UICONTROL New Workflow]** 工作流程類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立查詢活動 {#create-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**，drag and drop a **[!UICONTROL Query activity]**![](assets/query.png).
1. 按兩下活動。
1. In **[!UICONTROL Shortcuts]**、drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**、drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no]**.
1. Click **[!UICONTROL Confirm]**.

## 建立分段活動 {#create-a-segmentation-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Targeting]**&#x200B;拖放 **[!UICONTROL Segmentation]** 活動，然後按兩下它。
1. 將滑鼠指標暫留在區段上，然後按一下定位 ![](assets/edit_darkgrey-24px.png) 客戶今年新增的資料庫。
1. 拖放並 **[!UICONTROL Profiles]****[!UICONTROL Created]** 以篩選類型進行選取 **[!UICONTROL Relative]**。
1. 變更 **[!UICONTROL Level of precision]** 並 **[!UICONTROL Year]** 選取 **[!UICONTROL This year]**。

>[!NOTE]
>
>若要觀察規則的結構，請按一 **[!UICONTROL Advanced Mode]**&#x200B;下。

1. 按 **[!UICONTROL Confirm]** 兩下。
1. In **[!UICONTROL Advanced Options]**，check **[!UICONTROL Generate complement]** to create a segment target thele剩下collector.
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

## 建立電子郵件傳送 {#create-an-email-delivery}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Channels]**，拖放每個區段後的電子郵件傳送。
1. 按一下活動，然後選擇 ![](assets/edit_darkgrey-24px.png) 編輯。
1. 選擇 **[!UICONTROL Single send email]** 並按 **[!UICONTROL Next]**&#x200B;一下。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面配置，請按 **[!UICONTROL Email Designer]**&#x200B;一下。
1. 插入元素或選取現有範本。
1. 透過每次傳遞專屬的優惠，個人化您的電子郵件。

如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。

1. 按一下 **[!UICONTROL Preview]** 以檢查您的版面。
1. Click **[!UICONTROL Save]**.

**相關主題：**

* [Query](../../automating/using/query.md)
* [區段活動](../../automating/using/segmentation.md)
* [電子郵件傳送](../../automating/using/email-delivery.md)
