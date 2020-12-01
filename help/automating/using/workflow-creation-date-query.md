---
solution: Campaign Standard
product: campaign
title: 在配置檔案的建立日期建立交貨
description: 此使用案例說明如何在描述檔的建立日期建立傳送。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
translation-type: tm+mt
source-git-commit: 45c80b5e6bf2169c5acf6eea70da9e2f130982c8
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---


# 在設定檔建立日期中建立傳送 {#creation-date-query}

您可以在客戶個人檔案建立週年時透過電子郵件傳送選件。

1. 在 **[!UICONTROL Marketing Activities]** 中，按一下 **[!UICONTROL Create]** 並選取 **[!UICONTROL Workflow]**。
1. 選取 **[!UICONTROL New Workflow]** 作為工作流程類型，並按一下 **[!UICONTROL Next]**。
1. 輸入工作流程的屬性並按一下 **[!UICONTROL Create]**。

## 建立排程器活動 {#creating-a-scheduler-activity}

1. 在&#x200B;**[!UICONTROL Activities]** > **[!UICONTROL Execution]**&#x200B;中，拖放[調度程式](../../automating/using/scheduler.md)活動。
1. 連按兩下此活動。
1. 設定傳送的執行。
1. 在 **[!UICONTROL Execution frequency]** 中選取 **[!UICONTROL Daily]**。
1. 為工作流選擇&#x200B;**[!UICONTROL Time]**&#x200B;和&#x200B;**[!UICONTROL Repetition frequency]**&#x200B;執行。
1. 為工作流選擇&#x200B;**[!UICONTROL Start]**&#x200B;日期和&#x200B;**[!UICONTROL Expiration]**。
1. 確認您的活動並儲存您的工作流程。

>[!NOTE]
>
>要在特定時區啟動工作流，請在&#x200B;**[!UICONTROL Execution options]**&#x200B;頁籤的&#x200B;**[!UICONTROL Time zone]**&#x200B;欄位中為調度程式設定時區。 依預設，選取的時區是工作流程屬性中定義的時區（請參閱[建立工作流程](../../automating/using/building-a-workflow.md)）。

![](assets/time_zone.png)

## 建立「查詢」活動 {#creating-a-query-activity}

1. 若要選擇收件者，請拖放[Query](../../automating/using/query.md)活動，然後按兩下它。
1. 添加&#x200B;**[!UICONTROL Profiles]**&#x200B;並選擇&#x200B;**[!UICONTROL no longer contact by email]**，其值為&#x200B;**[!UICONTROL no]**。

### 正在檢索與執行日期{#retrieving-profiles-created-on-the-same-day}相同日期建立的配置檔案

1. 在&#x200B;**[!UICONTROL Profile]**&#x200B;中，拖放&#x200B;**[!UICONTROL Created]**&#x200B;欄位。 並按一下&#x200B;**[!UICONTROL Advanced Mode]**。
   ![](assets/advanced_mode.png)
1. 在&#x200B;**[!UICONTROL list of functions]**&#x200B;中，按兩下&#x200B;**[!UICONTROL Date]**&#x200B;節點中的&#x200B;**[!UICONTROL Day]**。
1. 然後，將欄位&#x200B;**[!UICONTROL Created]**&#x200B;插入為參數。
1. 選擇&#x200B;**[!UICONTROL equals to (=)]**&#x200B;作為運算子。
1. 對於「值」，從&#x200B;**[!UICONTROL List of functions]**&#x200B;的&#x200B;**[!UICONTROL Date]**&#x200B;節點中選擇&#x200B;**[!UICONTROL Day]**。
1. 將&#x200B;**[!UICONTROL GetDate()]**&#x200B;函式插入為參數。

您檢索了建立日等於當天的配置檔案。

您最終應該有：

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

按一下 **[!UICONTROL Confirm]**。

### 檢索在執行月建立的配置檔案{#retrieving-profiles-created-on-the-same-month}

1. 在&#x200B;**[!UICONTROL Query]**&#x200B;編輯器上，選擇第一個查詢並複製它。
1. 開啟復本。
1. 在查詢中將&#x200B;**[!UICONTROL Day]**&#x200B;替換為&#x200B;**[!UICONTROL Month]**。
1. 按一下 **[!UICONTROL Confirm]**。

![](assets/month_rule.png)

您最後應該會有這樣的結果：

``` Month(@created) = Month(GetDate()) ```

最終查詢將顯示：

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## 建立電子郵件傳送{#creating-an-email-delivery}

1. 拖放[電子郵件傳送](../../automating/using/email-delivery.md)活動。
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
