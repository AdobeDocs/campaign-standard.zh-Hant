---
title: 「Workflow Use-case：建立描述檔建立日期上的傳送」
seo-title: 「Workflow Use-case：建立描述檔建立日期上的傳送」
description: 「Workflow Use-case：建立描述檔建立日期上的傳送」
seo-description: 「Workflow Use-case：建立描述檔建立日期上的傳送」
page-status-flag: 從未啓動
uuid: 396a3de1-6ffa-4385-ac9 f-15fdeae5 a366
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: '執行活動 '
discoiquuid: 377821e6-69f8-41cc-a1 ad-8a2 f5 ed4 d409
context-tags: 工作流程，使用案例，查詢
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# 工作流程使用案例：建立描述檔「建立日期」上的傳送 {#creation-date-query}

您可以在客戶設定檔建立週年時透過電子郵件傳送優惠。

1. In **[!UICONTROL Marketing Activities]**，click **[!UICONTROL Create]** and select **[!UICONTROL Workflow]**.
1. 選擇 **[!UICONTROL New Workflow]** 工作流程類型，然後按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性，然後按一下 **[!UICONTROL Create]**。

## 建立排程器活動 {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**，drag and drop a **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png).
1. 按兩下活動。
1. 設定傳送的執行。
1. In **[!UICONTROL Execution frequency]**，select **[!UICONTROL Daily]**.
1. 為工作流程選擇執行 **[!UICONTROL Time]** 和執行 **[!UICONTROL Repetition frequency]** 。
1. 選取 **[!UICONTROL Start]** 日期和 **[!UICONTROL Expiration]** 工作流程。

>[!NOTE]
>
>若要在特定時區開始工作流程，請在&#x200B;**[!UICONTROL Execution options]**&#x200B;標籤中設定排程器 **[!UICONTROL Time zone]**&#x200B;的時區。

![](assets/time_zone.png)

1. 確認您的活動並儲存您的工作流程。

## 建立查詢活動 {#creating-a-query-activity}

1. 若要選取收件者，請拖放並 **[!UICONTROL Query activity]** 按兩下它。
1. 新增 **[!UICONTROL Profiles]** 並選取 **[!UICONTROL no longer contact by email]** 值 **[!UICONTROL no]**。

### 擷取在同一天內建立的設定檔，作為執行日 {#retriving-profiles-created-on-the-same-day}

1. In **[!UICONTROL Profile]**、drag and drop the **[!UICONTROL Created]** field.然後按 **[!UICONTROL Advanced Mode]**一下。
   ![](assets/advanced_mode.png)
1. 在此 **[!UICONTROL list of functions]**&#x200B;中，按兩下&#x200B;**[!UICONTROL Day]****[!UICONTROL Date]**&#x200B;節點。
1. 然後，將欄位 **[!UICONTROL Created]** 插入引數。
1. 選擇 **[!UICONTROL equals to (=)]** 作為運算元。
1. 對於值，請從&#x200B;**[!UICONTROL Day]** 中的 **[!UICONTROL Date]** 節點選取 **[!UICONTROL List of functions]**。
1. 將&#x200B;**[!UICONTROL GetDate()]**&#x200B;函數插入為引數。

您擷取了設定日期等於當天的描述檔。

您應終止：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### 擷取在同月份內建立的設定檔，作為執行月份{#retriving-profiles-created-on-the-same-month}

1. 在 **[!UICONTROL Query]** 編輯器上，選取第一個查詢並複製它。
1. 開啓復本。
1. 依 **[!UICONTROL Day]** 查詢 **[!UICONTROL Month]** 取代。
您應該會這樣：

``` Month(@created) = Month(GetDate()) ```

1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

最終查詢會顯示：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 拖放電子郵件傳送。
1. 按一下活動，然後選擇 ![](assets/edit_darkgrey-24px.png) 編輯。
1. 選擇 **[!UICONTROL Recurring email]** 並按 **[!UICONTROL Next]**&#x200B;一下。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面配置，請按 **[!UICONTROL Email Designer]**&#x200B;一下。
1. 插入元素或選取現有範本。
1. 使用欄位和連結個人化您的電子郵件。
如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)。
1. 按一下 **[!UICONTROL Preview]** 以檢查您的版面。
1. Click **[!UICONTROL Save]**.

**相關主題：**

* [Query](../../automating/using/query.md)
* [排程器](../../automating/using/scheduler.md)
* [電子郵件傳送](../../automating/using/email-delivery.md)
* [電子郵件頻道](../../channels/using/creating-an-email.md)
