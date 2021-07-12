---
solution: Campaign Standard
product: campaign
title: 自訂清單
description: 「了解如何自訂顯示以及在Adobe Campaign Standard中的清單畫面上操作：排序、篩選、刪除或複製元素。 列出螢幕，顯示一或多個指定資源的元素。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: 行銷活動
role: User
level: Intermediate
exl-id: 651a53b4-e02f-4963-99e6-2e2c324b1c8c
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 1%

---

# 自訂清單{#customizing-lists}

**** 清單畫面可讓您顯示一或多個指定資源的元素。

Adobe Campaign有兩種清單：

* **齊次**&#x200B;清單，即它包含單一類型的資源時。 例如，設定檔清單僅包含設定檔。
* **異構**&#x200B;清單，即它包含多種類型的資源時。 例如，行銷活動清單包含登錄頁面、工作流程、電子郵件、簡訊等。

清單會以欄顯示。 每欄可一次依遞增或遞減順序排序。

清單中的元素有一個可讓您選取的核取方塊。 選取一或多個元素，即可執行數個動作，例如編輯、複製和刪除這些元素。

將滑鼠游標暫留在清單中的元素上時，**快速動作**。 這些動作可讓使用者對暫留的元素執行各種動作，例如編輯、選取、刪除或顯示詳細資料。

![](assets/overview_list_quickactions.png)

您也可以設定是否顯示清單中的欄。 要添加或刪除列：

1. 請確定畫面處於&#x200B;**List**&#x200B;模式。

   ![](assets/export_list_mode_switch.png)

1. 通過選擇操作欄中的![](assets/columnsettings.png)按鈕，轉到清單配置窗口。

   ![](assets/list_configuration1.png)

1. 新增您要納入清單的欄。 要執行此操作，請從窗口的左側選擇一列，然後使用操作欄中的![](assets/arrowright.png)按鈕添加一列。

   可選列對應於清單資源。

   針對新增的每欄，指定是否依預設套用排序：

   * **[!UICONTROL NO]**:對列不排序
   * **[!UICONTROL ASC]**:對欄套用遞增（上升）排序
   * **[!UICONTROL DESC]**:對欄套用降序（遞減）排序。

1. 勾選與要刪除的欄相對應的方塊，以刪除您不想顯示的欄。 然後，使用動作列中的![](assets/delete.png)按鈕確認刪除。
1. 一旦清單包含正確的欄，您就可以檢查您要移動的欄，以變更清單中這些欄的顯示順序。 然後，使用![](assets/arrowdown.png)和![](assets/arrowup.png)箭頭。
1. 選擇&#x200B;**[!UICONTROL OK]**&#x200B;以確認清單配置。

您的清單現在會依您設定的方式顯示。
