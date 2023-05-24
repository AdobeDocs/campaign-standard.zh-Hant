---
title: 自訂清單
description: 「瞭解如何自定義顯示和在Adobe Campaign Standard的清單螢幕上操作：排序、過濾、刪除或複製元素。 列出螢幕顯示一個或多個給定資源的元素。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Campaigns
role: User
level: Intermediate
exl-id: 651a53b4-e02f-4963-99e6-2e2c324b1c8c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 2%

---

# 自訂清單{#customizing-lists}

**清單** 螢幕允許您顯示一個或多個給定資源的元素。

Adobe Campaign有兩類清單：

* A **均勻** 清單，即包含單種資源類型時。 例如，配置檔案清單僅包含配置檔案。
* A **異構** 清單，即包含多種資源類型時。 例如，市場營銷活動清單包含登錄頁、工作流、電子郵件、簡訊等。

清單顯示在欄中。每列可以按升序或降序一次排序。

清單中的元素有一個複選框，允許您選中這些元素。 通過選取一個或多個元素，可以執行多個操作，如編輯、複製和刪除這些元素。

當懸停在清單中的元素上時， **快速操作**。 這些操作允許用戶對懸停的元素執行各種操作，如編輯、選擇、刪除或顯示詳細資訊。

![](assets/overview_list_quickactions.png)

還可以配置是否顯示清單中的列。 添加或刪除列：

1. 確保螢幕在 **清單** 的子菜單。

   ![](assets/export_list_mode_switch.png)

1. 通過選擇 ![](assets/columnsettings.png) 按鈕。

   ![](assets/list_configuration1.png)

1. 添加要包括在清單中的列。 為此，請從窗口的左側選擇一個列，然後使用 ![](assets/arrowright.png) 按鈕。

   可選列對應於清單資源。

   對於添加的每列，指定是否預設應用排序：

   * **[!UICONTROL NO]**:列上沒有排序
   * **[!UICONTROL ASC]**:對列應用升序（上升）排序
   * **[!UICONTROL DESC]**:對列應用降序（下降）排序。

1. 通過選中與要刪除的列對應的框來刪除不想顯示的列。 然後，使用 ![](assets/delete.png) 按鈕，來確認刪除。
1. 清單包含正確的列後，您可以通過檢查要移動的列來更改它們在清單中顯示的順序。 然後，使用 ![](assets/arrowdown.png) 和 ![](assets/arrowup.png) 按鈕。
1. 通過選擇 **[!UICONTROL OK]**。

此時，您的清單將顯示為已配置的清單。
