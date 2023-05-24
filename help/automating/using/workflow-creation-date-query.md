---
title: 在配置檔案的建立日期建立交貨
description: 此用例說明如何在配置檔案的建立日期建立交貨。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f611e023-f74c-476e-83b9-aff451f68c81
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---

# 在設定檔建立日期中建立傳遞 {#creation-date-query}

您可以在客戶建立配置檔案的週年時通過電子郵件發送優惠。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立排程器活動 {#creating-a-scheduler-activity}

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Execution]**，拖放 [調度程式](../../automating/using/scheduler.md) 的子菜單。
1. 連按兩下此活動。
1. 設定傳送的執行。
1. 在 **[!UICONTROL Execution frequency]** 中選取 **[!UICONTROL Daily]**。
1. 選擇 **[!UICONTROL Time]** 和 **[!UICONTROL Repetition frequency]** 執行。
1. 選擇 **[!UICONTROL Start]** 日期和 **[!UICONTROL Expiration]** 的子菜單。
1. 確認您的活動並儲存您的工作流程。

>[!NOTE]
>
>要在特定時區啟動工作流，請在 **[!UICONTROL Execution options]** 頁籤，在 **[!UICONTROL Time zone]** 的子菜單。 依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

![](assets/time_zone.png)

## 建立「查詢」活動 {#creating-a-query-activity}

1. 要選擇收件人，請拖放 [查詢](../../automating/using/query.md) 並按兩下它。
1. 添加 **[!UICONTROL Profiles]** 選擇 **[!UICONTROL no longer contact by email]** 值 **[!UICONTROL no]**。

### 正在檢索在執行日期同一天建立的配置檔案 {#retrieving-profiles-created-on-the-same-day}

1. 在 **[!UICONTROL Profile]**，拖放 **[!UICONTROL Created]** 的子菜單。 按一下 **[!UICONTROL Advanced Mode]**。
   ![](assets/advanced_mode.png)
1. 在 **[!UICONTROL list of functions]**，按兩下 **[!UICONTROL Day]** 從 **[!UICONTROL Date]** 的下界。
1. 然後，插入該欄位 **[!UICONTROL Created]** 作為論據。
1. 選擇 **[!UICONTROL equals to (=)]** 作為運算子。
1. 對於值，選擇 **[!UICONTROL Day]** 從 **[!UICONTROL Date]** 中的 **[!UICONTROL List of functions]**。
1. 插入 **[!UICONTROL GetDate()]** 函式作為參數。

您檢索了建立日等於當前日的配置檔案。

您最後應該有：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

按一下&#x200B;**[!UICONTROL Confirm]**。

### 正在檢索在執行月份的同一月份建立的配置檔案{#retrieving-profiles-created-on-the-same-month}

1. 在 **[!UICONTROL Query]** 編輯器，選擇第一個查詢並複製它。
1. 開啟副本。
1. 替換 **[!UICONTROL Day]** 按 **[!UICONTROL Month]** 的子菜單。
1. 按一下&#x200B;**[!UICONTROL Confirm]**。

![](assets/month_rule.png)

你最後應該這樣做：

``` Month(@created) = Month(GetDate()) ```

最終查詢顯示：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 拖放 [電子郵件傳遞](../../automating/using/email-delivery.md) 的子菜單。
1. 按一下活動並選取 ![](assets/edit_darkgrey-24px.png) 以編輯。
1. 選取 **[!UICONTROL Recurring email]** 並按一下 **[!UICONTROL Next]**。
1. 選取電子郵件範本，然後按一下 **[!UICONTROL Next]**。
1. 輸入電子郵件屬性，然後按一下 **[!UICONTROL Next]**。
1. 若要建立電子郵件的版面，請按一下 **[!UICONTROL Email Designer]**。
1. 插入元素或選取現有範本。
1. 使用欄位和連結個人化您的電子郵件。如需詳細資訊，請參閱[設計電子郵件](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)。
1. 按一下 **[!UICONTROL Preview]** 以檢查版面。
1. 按一下 **[!UICONTROL Save]**。

**相關主題：**

* [電子郵件通道](../../channels/using/creating-an-email.md)
