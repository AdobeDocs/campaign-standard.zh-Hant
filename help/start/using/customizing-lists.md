---
title: 自訂清單
description: 「瞭解如何在Adobe Campaign Standard中自訂顯示並在清單熒幕上操作：排序、篩選、刪除或複製元素。 列出畫面會顯示一或多個指定資源的元素。」
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

**清單**&#x200B;畫面可讓您顯示一或多個指定資源的元素。

Adobe Campaign有兩種清單：

* **同質的**&#x200B;清單，當它包含單一型別的資源時。 例如，設定檔清單僅包含設定檔。
* **異質性**&#x200B;清單，當它包含數種資源型別時。 例如，行銷活動清單包含登入頁面、工作流程、電子郵件、簡訊等。

清單顯示在欄中。每個欄可以一次一個地以升序或降序排序。

清單中的元素具有允許您選取它們的核取方塊。 選取一或多個元素後，您可以執行數個動作，例如編輯、複製和刪除這些元素。

將滑鼠懸停在清單中的專案上時，**快速動作**。 這些動作可讓使用者對暫留在其上的元素執行各種動作，例如編輯、選取、刪除或顯示詳細資訊。

![](assets/overview_list_quickactions.png)

您也可以設定是否要顯示清單中的欄。 若要新增或移除欄：

1. 確定熒幕處於&#x200B;**清單**&#x200B;模式。

   ![](assets/export_list_mode_switch.png)

1. 選取動作列中的![](assets/columnsettings.png)按鈕，移至清單設定視窗。

   ![](assets/list_configuration1.png)

1. 新增要包含在清單中的欄。 若要這麼做，請從視窗左側選取欄，然後使用動作列中的![](assets/arrowright.png)按鈕來新增欄。

   可選取的欄會對應至清單資源。

   針對新增的每個欄，指定您預設是否要套用排序：

   * **[!UICONTROL NO]**：資料行沒有排序
   * **[!UICONTROL ASC]**：對欄套用遞增（上升）排序
   * **[!UICONTROL DESC]**：對欄套用遞減（遞減）排序。

1. 勾選要刪除之欄的對應方塊，刪除您不想顯示的欄。 然後，使用動作列中的![](assets/delete.png)按鈕以確認刪除它們。
1. 一旦清單包含正確的欄之後，您就可以檢查要移動的欄，變更它們在清單中的顯示順序。 然後，使用![](assets/arrowdown.png)和![](assets/arrowup.png)箭頭。
1. 選取&#x200B;**[!UICONTROL OK]**&#x200B;以確認您的清單設定。

清單現在會依您的設定顯示。
