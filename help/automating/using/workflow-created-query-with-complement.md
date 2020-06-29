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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 5%

---


# 使用補救來建立傳送 {#deliveries-with-complement}

您可以傳送電子郵件給客戶： 一個是為不到一年前建立的客戶建立的，一個是為一年多以前建立的客戶建立的。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;按一下並 **[!UICONTROL Create]** 選擇 **[!UICONTROL Workflow]**。
1. 選擇 **[!UICONTROL New Workflow]** 為工作流類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流的屬性並按一下 **[!UICONTROL Create]**。

## 建立查詢活動 {#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放 [](../../automating/using/query.md) Query活動。
1. 連按兩下活動。
1. 在中 **[!UICONTROL Shortcuts]**，使用運算 **[!UICONTROL Profiles]** 符拖放 **[!UICONTROL email]** 並選擇 **[!UICONTROL is not empty]**。
1. 在中 **[!UICONTROL Shortcuts]**，拖放並 **[!UICONTROL Profiles]** 使用 **[!UICONTROL no longer contact by email]** 值進行選擇 **[!UICONTROL no]**。
1. 按一下「**[!UICONTROL Confirm]**」。

![](assets/wf-complement-query.png)

## 建立區段活動 {#create-a-segmentation-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放區段 [活動](../../automating/using/segmentation.md) ，然後按兩下它。
1. 將滑鼠指標暫留在區段上，然後按一 ![](assets/edit_darkgrey-24px.png) 下，以定位今年在資料庫中新增的客戶。
1. 拖放並選 **[!UICONTROL Profiles]** 取具 **[!UICONTROL Created]** 有篩選類型的項目 **[!UICONTROL Relative]**。
1. 將更改 **[!UICONTROL Level of precision]** 為並 **[!UICONTROL Year]** 選擇 **[!UICONTROL This year]**。
1. 按兩 **[!UICONTROL Confirm]** 下。
1. 在中 **[!UICONTROL Advanced Options]**，選 **[!UICONTROL Generate complement]** 取以建立以其餘收件者為目標的區段。
1. 按一下「**[!UICONTROL Confirm]**」。
1. 按一下「**[!UICONTROL Save]**」。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>若要觀察規則的結構，請按一下 **[!UICONTROL Advanced Mode]**。

## 建立電子郵件傳送 {#create-an-email-delivery}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，在每個區段後拖 [放「電子郵件](../../automating/using/email-delivery.md) 」傳送活動。
1. 按一下活動並選 ![](assets/edit_darkgrey-24px.png) 擇以編輯。
1. 選擇 **[!UICONTROL Single send email]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 透過每次傳送的特定優惠，個人化您的電子郵件。
1. 按一 **[!UICONTROL Preview]** 下以檢查版面。
1. 按一下「**[!UICONTROL Save]**」。

如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

![](assets/wf-deliveries-with-a-complement.png)
