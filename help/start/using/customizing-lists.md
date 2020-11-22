---
solution: Campaign Standard
product: campaign
title: 自訂清單
description: 「瞭解如何自訂Adobe Campaign Standard中的顯示畫面並對清單畫面採取行動：排序、篩選、刪除或複製元素。 清單畫面會顯示一或多個特定資源的元素。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 1%

---


# 自訂清單{#customizing-lists}

**清單** (List)畫面可讓您顯示一或多個特定資源的元素。

Adobe Campaign有兩種清單類型：

* 同 **構清單** ，即包含單一資源類型時。 例如，描述檔清單只包含描述檔。
* 異 **構清單** ，即包含多種資源類型時。 例如，行銷活動清單包含著陸頁面、工作流程、電子郵件、簡訊等。

清單以列顯示。 每個欄可依遞增或遞減順序一次排序。

清單中的元素有一個複選框，允許您選擇這些元素。 只要選取一或多個元素，您就可執行數個動作，例如編輯、複製和刪除這些元素。

將滑鼠指標暫留在清單中的元素上時，可執行 **快速動作**。 這些動作可讓使用者對暫留的元素執行各種動作，例如編輯、選取、刪除或顯示詳細資訊。

![](assets/overview_list_quickactions.png)

您也可以設定是否顯示清單中的欄。 要添加或刪除列：

1. 請確定畫面處於「清 **單** 」模式。

   ![](assets/export_list_mode_switch.png)

1. 選擇操作欄中的按鈕，轉到 ![](assets/columnsettings.png) 清單配置窗口。

   ![](assets/list_configuration1.png)

1. 新增您要納入清單的欄。 若要這麼做，請從視窗左側選取欄，然後使用動作列 ![](assets/arrowright.png) 的按鈕來新增欄。

   可選列對應於清單資源。

   對於每個新增的欄，指定是否依預設套用排序：

   * **[!UICONTROL NO]**:欄上沒有排序
   * **[!UICONTROL ASC]**:對列應用升序（上升）排序
   * **[!UICONTROL DESC]**:對列應用降序（拒絕）排序。

1. 通過選中與要刪除的列對應的框來刪除不想顯示的列。 然後，使用動 ![](assets/delete.png) 作列中的按鈕確認刪除。
1. 一旦您的清單包含正確的欄，您就可以勾選您要移動的欄，以變更這些欄在清單中的顯示順序。 然後，使用 ![](assets/arrowdown.png) 和 ![](assets/arrowup.png) 箭頭。
1. 選擇以確認您的清單配置 **[!UICONTROL OK]**。

您的清單現在會顯示為您已設定的清單。
