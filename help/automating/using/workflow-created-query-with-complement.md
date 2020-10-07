---
title: 使用補救來建立傳送
description: 此使用案例說明如何建立輔助傳送。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---


# 使用補救來建立傳送 {#deliveries-with-complement}

您可以傳送電子郵件給客戶：一個是為不到一年前建立的客戶建立的，一個是為一年多以前建立的客戶建立的。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## Create a Query activity {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查詢](../../automating/using/query.md)活動。
1. 連按兩下此活動。
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no]**.
1. 按一下 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## Create a Segmentation activity {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. 將滑鼠指標暫留在區段上，然後按一 ![](assets/edit_darkgrey-24px.png) 下，以定位今年在資料庫中新增的客戶。
1. Drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL Created]** with the filter type **[!UICONTROL Relative]**.
1. Change the **[!UICONTROL Level of precision]** to **[!UICONTROL Year]** and select **[!UICONTROL This year]**.
1. 按兩下 **[!UICONTROL Confirm]**。
1. 在中 **[!UICONTROL Advanced Options]**，選 **[!UICONTROL Generate complement]** 取以建立以其餘收件者為目標的區段。
1. 按一下 **[!UICONTROL Confirm]**。
1. 按一下 **[!UICONTROL Save]**。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>若要觀察規則的結構，請按一下 **[!UICONTROL Advanced Mode]**。

## 建立電子郵件傳送 {#create-an-email-delivery}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，在每個區段後拖 [放「電子郵件](../../automating/using/email-delivery.md) 」傳送活動。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Single send email]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 透過每次傳送的特定優惠，個人化您的電子郵件。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

如需詳細資訊，請參閱[設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

![](assets/wf-deliveries-with-a-complement.png)
