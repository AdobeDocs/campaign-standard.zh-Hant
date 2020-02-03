---
title: 「工作流程使用案例：在描述檔的建立日期建立傳送」
description: 「工作流程使用案例：在描述檔的建立日期建立傳送」
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# 工作流程使用案例：在描述檔建立日期建立傳送 {#creation-date-query}

您可以在客戶個人檔案建立週年時透過電子郵件傳送選件。

1. 在中， **[!UICONTROL Marketing Activities]**按一下並**[!UICONTROL Create]** 選擇 **[!UICONTROL Workflow]**。
1. 選擇 **[!UICONTROL New Workflow]**為工作流類型，然後按一下**[!UICONTROL Next]**。
1. 輸入工作流的屬性並按一下 **[!UICONTROL Create]**。

## 建立調度程式活動 {#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]**>**[!UICONTROL Execution]**&#x200B;中拖放 **[!UICONTROL Scheduler activity]**。
1. 連按兩下活動。
1. 設定傳送的執行。
1. 在中 **[!UICONTROL Execution frequency]**，選擇**[!UICONTROL Daily]**。
1. 選擇工 **[!UICONTROL Time]**作流**[!UICONTROL Repetition frequency]** 的執行和執行。
1. 為您的工 **[!UICONTROL Start]**作流程選**[!UICONTROL Expiration]** 擇日期和日期。
1. 確認您的活動並儲存您的工作流程。

>[!NOTE]
>
>要在特定時區啟動工作流，請在該頁籤&#x200B;**[!UICONTROL Execution options]**的欄位中為調度程式設定時**[!UICONTROL Time zone]**&#x200B;區。 依預設，選取的時區是工作流屬性中定義的時區(請參 [閱建立工作流](../../automating/using/building-a-workflow.md))。

![](assets/time_zone.png)

## 建立查詢活動 {#creating-a-query-activity}

1. 若要選取收件者，請拖放並 **[!UICONTROL Query activity]**按兩下收件者。
1. 使用 **[!UICONTROL Profiles]**值新**[!UICONTROL no longer contact by email]** 增並選取 **[!UICONTROL no]**。

### 檢索在執行日建立的配置檔案 {#retriving-profiles-created-on-the-same-day}

1. 在 **[!UICONTROL Profile]**中，拖放字**[!UICONTROL Created]** 段。 並按一下 **[!UICONTROL Advanced Mode]**。   ![](assets/advanced_mode.png)
1. 在中， **[!UICONTROL list of functions]**按兩下節**[!UICONTROL Day]** 點中的&#x200B;**[!UICONTROL Date]**按鈕。
1. 然後，將欄位插 **[!UICONTROL Created]**入為參數。
1. 選擇 **[!UICONTROL equals to (=)]**作為運算子。
1. 對於「值」,**[!UICONTROL Day]**請從中**[!UICONTROL Date]** 的節點中選擇 **[!UICONTROL List of functions]**。
1. 將函式&#x200B;**[!UICONTROL GetDate()]**插入為參數。

您檢索了建立日等於當天的配置檔案。

您最終應該有：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

按一下 **[!UICONTROL Confirm]**.

### 檢索在執行月的同一月建立的配置檔案{#retriving-profiles-created-on-the-same-month}

1. 在編輯 **[!UICONTROL Query]**器上，選擇第一個查詢並複製它。
1. 開啟復本。
1. 在查 **[!UICONTROL Day]**詢**[!UICONTROL Month]** 中替換為。
1. 按一下 **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

您最後應該會有這樣的結果：

``` Month(@created) = Month(GetDate()) ```

最終查詢將顯示：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 拖放電子郵件傳送。
1. 按一下活動並選 ![](assets/edit_darkgrey-24px.png) 擇以編輯。
1. 選擇 **[!UICONTROL Recurring email]**並按一下**[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用欄位和連結個人化您的電子郵件。
如需詳細資訊，請參閱 [設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 按一 **[!UICONTROL Preview]**下以檢查版面。
1. 按一下 **[!UICONTROL Save]**.

**相關主題：**

* [查詢](../../automating/using/query.md)
* [排程器](../../automating/using/scheduler.md)
* [電子郵件傳送](../../automating/using/email-delivery.md)
* [電子郵件通道](../../channels/using/creating-an-email.md)
