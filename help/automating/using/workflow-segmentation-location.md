---
title: 「工作流程使用案例：區段位置」
description: 「工作流程使用案例：區段位置」
page-status-flag: 從未激活
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 執行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: '工作流程，使用案例，查詢，分段，傳送 '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 工作流程使用案例：區段位置 {#segmentation-on-location}

您可以傳送定位電子郵件給客戶，並在其當地商店提供優惠。

1. 在中， **[!UICONTROL Marketing Activities]**&#x200B;按一下並 **[!UICONTROL Create]** 選擇 **[!UICONTROL Workflow]**。
1. 選擇 **[!UICONTROL New Workflow]** 為工作流類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流的屬性並按一下 **[!UICONTROL Create]**。

## 透過電子郵件選擇可聯絡的收件者{#selecting-recipients-contactable-via-email}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**&#x200B;中拖放 **[!UICONTROL Query activity]**![](assets/query.png)。
1. 連按兩下活動。
1. 在中 **[!UICONTROL Shortcuts]**，拖放並選 **[!UICONTROL Profiles]** 擇包含運算子 **[!UICONTROL email]** 的欄位 **[!UICONTROL is not empty]**。
1. 在中 **[!UICONTROL Shortcuts]**，拖放並 **[!UICONTROL Profiles]** 選擇包含值 **[!UICONTROL no longer contact by email]** 的欄位 **[!UICONTROL no]**。
1. 按兩 **[!UICONTROL Confirm]** 下。

![](assets/wf-complement-query.png)

## 建立區段活動{#creating-a-segmentation-activity}

1. 拖放活動 **[!UICONTROL Segmentation]** 並按兩下它。
1. 按一下區段，然後開啟轉場，以定位第一個城市的人。 波士頓。
1. 拖放並選 **[!UICONTROL Location]** 取運算 **[!UICONTROL City]** 子和值 **[!UICONTROL equals to]** 的項目 **[!UICONTROL Boston]**。
注意：要聯繫所有進入波士頓的人，請取消選中區分大小寫選項。
1. Click **[!UICONTROL Confirm]**.
1. 在中 **[!UICONTROL List of outbound segments]**，按一 **[!UICONTROL Add an element]** 下並按一 ![](assets/edit_darkgrey-24px.png) 下，以建立以第二個城市的訪客為目標的區段。 芝加哥。
1. 拖放並 **[!UICONTROL Location]** 使用運 **[!UICONTROL City]** 算元選 **[!UICONTROL equals to]** 取，然後 **[!UICONTROL Chicago]** 輸入值。
1. 要聯繫所有進入芝加哥的人，請取消選中區分大小寫選項。
1. Click **[!UICONTROL Confirm]**.

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 在 **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**&#x200B;中，拖放每個區 **[!UICONTROL Email Delivery]** 段之後。
1. 按一下活動並選 ![](assets/edit_darkgrey-24px.png) 擇以編輯。
1. 選擇 **[!UICONTROL Simple email]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 利用每個位置專屬的優惠，個人化您的電子郵件。

如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。

1. 按一 **[!UICONTROL Preview]** 下以檢查版面。
1. Click **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**相關主題：**

* [查詢活動](../../automating/using/query.md)
* [區段活動](../../automating/using/segmentation.md)
* [電子郵件傳送](../../automating/using/email-delivery.md)
