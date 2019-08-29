---
title: 「Workflow Use-case：建立每周傳送」
seo-title: 「Workflow Use-case：建立每周傳送」
description: 「Workflow Use-case：建立每周傳送」
seo-description: 「Workflow Use-case：建立每周傳送」
page-status-flag: 從未啓動
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: '執行活動 '
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: 工作流程，使用案例，查詢，傳送，排程器
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# Worflow使用案例：每星期二建立電子郵件傳送{#creating-email-every-tuesday}

您可以每星期二傳送電子郵件給所有的客戶以索取特別優惠。

1. In **[!UICONTROL Marketing Activities]**，click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. 選擇 **[!UICONTROL New Workflow]** 工作流程類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立排程器活動{#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**，drag and drop a **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png).
1. 按兩下活動。
1. 設定傳送的執行。
1. In **[!UICONTROL Execution frequency]**，select **[!UICONTROL Weekly]**.
1. 為您的傳送選擇 **[!UICONTROL Time]** 和a **[!UICONTROL Repetition frequency]** 。
1. In **[!UICONTROL Days of the week]**，select **[!UICONTROL Tuesday]**.
1. 指定工作流程的參數 **[!UICONTROL Start]** 和 **[!UICONTROL Expiration]** 參數。

![](assets/scheduler_properties.png)

>[!NOTE]
>
>若要在特定 **[!UICONTROL Time Zone]**&#x200B;位置開始工作流程，請在&#x200B;**[!UICONTROL Execution options]**「時區」欄位中設定排程器的時區時區。

1. 確認您的活動並儲存您的工作流程。

## 建立查詢活動{#creating-a-query-activity}

1. 在 **[!UICONTROL Activities]** &gt;中 **[!UICONTROL Targeting]**，選取收件者，拖放 **[!UICONTROL query]** 活動並按兩下該活動。
1. 在 **[!UICONTROL Shortcuts]** &gt;中 **[!UICONTROL Profile]**&#x200B;拖放 **[!UICONTROL Email]**。
1. 選擇 **[!UICONTROL is not empty]** 作為運算元。
1. 在 **[!UICONTROL Shortcuts]** &gt;中 **[!UICONTROL General]**，新增描述檔並 **[!UICONTROL no longer contact by email]** 以值選取 **[!UICONTROL No]**。
1. Click **[!UICONTROL Confirm]**.

## 建立電子郵件傳送{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**，drag and drop an **[!UICONTROL Email delivery]**.
1. 按一下活動，然後選擇 ![](assets/edit_darkgrey-24px.png) 編輯。
1. 選擇 **[!UICONTROL Recurring email]** 並按 **[!UICONTROL Next]**&#x200B;一下。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面配置，請按 **[!UICONTROL Use Email Designer]**&#x200B;一下。
1. 插入元素或選取現有範本。
1. 使用欄位和連結個人化您的電子郵件。
1. Click **[!UICONTROL Save]**.

如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。

**相關主題：**

* [查詢活動](../..//automating/using/query.md)
* [排程器活動](../..//automating/using/scheduler.md)
* [電子郵件傳送](../..//automating/using/email-delivery.md)
* [電子郵件頻道](../..//channels/using/creating-an-email.md)
