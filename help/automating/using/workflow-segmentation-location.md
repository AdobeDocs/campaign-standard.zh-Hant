---
title: 區段位置」
description: 此使用案例說明如何對位置執行分段。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 83%

---


# 區段位置 {#segmentation-on-location}

您可以傳送目標定位電子郵件給客戶，並在其當地商店提供優惠。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 透過電子郵件選取可聯絡的收件者{#selecting-recipients-contactable-via-email}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放查詢 [活動](../../automating/using/query.md)![](assets/query.png)。
1. 連按兩下此活動。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放 **[!UICONTROL Profiles]** 並選取包含運算子 **[!UICONTROL is not empty]** 的欄位 **[!UICONTROL email]**。
1. 在 **[!UICONTROL Shortcuts]**&#x200B;中，拖放 **[!UICONTROL Profiles]** 並選取包含值 **[!UICONTROL no]** 的欄位 **[!UICONTROL no longer contact by email]**。
1. 按兩下 **[!UICONTROL Confirm]**。

![](assets/wf-complement-query.png)

## 建立細分活動{#creating-a-segmentation-activity}

1. Drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. 按一下區段，然後開啟轉變，以定位第一個城市中的人。這裡是波士頓。
1. 拖放 **[!UICONTROL Location]** 並選取包含運算子 **[!UICONTROL equals to]** 及值 **[!UICONTROL Boston]** 的 **[!UICONTROL City]**。
注意：若要聯絡所有進入波士頓的人，請忽略大小寫選項中區分大小寫的選項。
1. 按一下 **[!UICONTROL Confirm]**。
1. 在 **[!UICONTROL List of outbound segments]**&#x200B;中，依序按一下 **[!UICONTROL Add an element]** 和 ![](assets/edit_darkgrey-24px.png)，建立以第二個城市人群為目標定位的區段。這裡是芝加哥。
1. 拖放 **[!UICONTROL Location]** 並選取包含運算子 **[!UICONTROL equals to]** 的 **[!UICONTROL City]**，然後在值中輸入 **[!UICONTROL Chicago]**。
1. 若要聯絡所有進入芝加哥的人，請忽略大小寫選項中區分大小寫的選項。
1. 按一下 **[!UICONTROL Confirm]**。

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，在每個區段後拖 [放「電子郵件](../../automating/using/email-delivery.md) 」傳送活動。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Simple email]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 利用每個位置專屬的優惠，個人化您的電子郵件。

   如需詳細資訊，請參閱[設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

![](assets/wf-segmentation-location.png)

