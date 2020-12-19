---
solution: Campaign Standard
product: campaign
title: 使用補救來建立傳送
description: 此使用案例說明如何建立輔助傳送。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---


# 使用補救來建立傳送 {#deliveries-with-complement}

您可以傳送電子郵件給客戶：一個是為不到一年前建立的客戶建立的，一個是為一年多以前建立的客戶建立的。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立查詢活動{#create-a-query-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** 中，拖放[查詢](../../automating/using/query.md)活動。
1. 連按兩下此活動。
1. 在&#x200B;**[!UICONTROL Shortcuts]**&#x200B;中，拖放&#x200B;**[!UICONTROL Profiles]**&#x200B;並使用運算子&#x200B;**[!UICONTROL is not empty]**&#x200B;選擇&#x200B;**[!UICONTROL email]**。
1. 在&#x200B;**[!UICONTROL Shortcuts]**&#x200B;中，拖放&#x200B;**[!UICONTROL Profiles]**&#x200B;並選擇&#x200B;**[!UICONTROL no longer contact by email]**&#x200B;值&#x200B;**[!UICONTROL no]**。
1. 按一下 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立區段活動{#create-a-segmentation-activity}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放[ Segmentation](../../automating/using/segmentation.md)活動，然後按兩下它。
1. 將滑鼠指標暫留在區段上，然後按一下![](assets/edit_darkgrey-24px.png)，以定位今年在資料庫中新增的客戶。
1. 拖放&#x200B;**[!UICONTROL Profiles]**&#x200B;並選擇&#x200B;**[!UICONTROL Created]**&#x200B;和&#x200B;**[!UICONTROL Relative]**&#x200B;過濾器類型。
1. 將&#x200B;**[!UICONTROL Level of precision]**&#x200B;更改為&#x200B;**[!UICONTROL Year]**&#x200B;並選擇&#x200B;**[!UICONTROL This year]**。
1. 按兩下 **[!UICONTROL Confirm]**。
1. 在&#x200B;**[!UICONTROL Advanced Options]**&#x200B;中，勾選&#x200B;**[!UICONTROL Generate complement]**&#x200B;以建立以其餘收件者為目標的區段。
1. 按一下 **[!UICONTROL Confirm]**。
1. 按一下 **[!UICONTROL Save]**。

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>要觀察規則的結構，請按一下&#x200B;**[!UICONTROL Advanced Mode]**。

## 建立電子郵件傳送 {#create-an-email-delivery}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，將[電子郵件傳送](../../automating/using/email-delivery.md)活動拖放至每個區段之後。
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
