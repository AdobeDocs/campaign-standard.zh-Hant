---
title: 使用補數來建立傳遞
description: 此使用案例顯示如何建立具備輔助功能的傳送。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5cd71e07-f955-4c15-bdfb-14b0daccec1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---

# 使用補數來建立傳遞 {#deliveries-with-complement}

您可以傳送電子郵件給客戶：一個適用於不到一年前建立的客戶，另一個適用於超過一年前建立的客戶。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立「查詢」活動 {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查詢](../../automating/using/query.md)活動。
1. 連按兩下此活動。
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL email]** 使用運運算元 **[!UICONTROL is not empty]**.
1. 在 **[!UICONTROL Shortcuts]**，拖放 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL no longer contact by email]** 包含值 **[!UICONTROL no]**.
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立細分活動 {#create-a-segmentation-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**，拖放 [細分](../../automating/using/segmentation.md) 活動並連按兩下。
1. 將游標暫留在區段上，然後按一下 ![](assets/edit_darkgrey-24px.png) ，以定位今年在資料庫中新增的客戶。
1. 拖放 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL Created]** 使用篩選器型別 **[!UICONTROL Relative]**.
1. 變更 **[!UICONTROL Level of precision]** 至 **[!UICONTROL Year]** 並選取 **[!UICONTROL This year]**.
1. 按兩下 **[!UICONTROL Confirm]**。
1. 在 **[!UICONTROL Advanced Options]**，檢查 **[!UICONTROL Generate complement]** 建立以其他收件者為目標的區段。
1. 按一下&#x200B;**[!UICONTROL Confirm]**。
1. 按一下&#x200B;**[!UICONTROL Save]**。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>若要觀察規則的結構，請按一下 **[!UICONTROL Advanced Mode]**.

## 建立電子郵件傳送 {#create-an-email-delivery}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Channels]**，拖放 [電子郵件傳遞](../../automating/using/email-delivery.md) 活動於每個區段之後。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Single send email]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用每個傳遞專屬的優惠，個人化您的電子郵件。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

如需詳細資訊，請參閱[設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

![](assets/wf-deliveries-with-a-complement.png)
