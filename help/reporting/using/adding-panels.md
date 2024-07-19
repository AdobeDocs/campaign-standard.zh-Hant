---
title: 新增面板
description: 動態報告可讓您新增面板，以根據所選的時段更好地篩選資料。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# 新增面板{#adding-panels}

## 新增空白面板 {#adding-a-blank-panel}

若要啟動報表，您可以將一組面板新增至立即可用或自訂的報表中。 每個面板都包含不同的資料集，而且由自由表格和視覺效果組成。

此面板可讓您視需要建置報告。 您可以在報表中新增任意數量的面板，以篩選不同時段的資料。

1. 按一下&#x200B;**面板**&#x200B;圖示。 您也可以按一下&#x200B;**插入索引標籤**&#x200B;並選取&#x200B;**新增空白面板**，以新增面板。

   ![](assets/dynamic_report_panel_1.png)

1. 將&#x200B;**空白面板**&#x200B;拖放到您的儀表板中。

   ![](assets/dynamic_report_panel.png)

您現在可以將自由表格新增至面板，以開始鎖定資料目標。

## 新增自由表格 {#adding-a-freeform-table}

自由表格可讓您建立表格，以使用&#x200B;**元件**&#x200B;表格中可用的不同量度和維度來分析您的資料。

每個表格和視覺效果皆可調整大小，且可以移動以自訂報表。

1. 按一下&#x200B;**[!UICONTROL Panels]**&#x200B;圖示。

   ![](assets/dynamic_report_panel_1.png)

1. 將&#x200B;**[!UICONTROL Freeform]**&#x200B;專案拖放至您的儀表板。

   您也可以按一下「**[!UICONTROL Insert]**」索引標籤並選取「**[!UICONTROL New Freeform]**」，或在空白面板中按一下「**[!UICONTROL Add a freeform table]**」來新增表格。

   ![](assets/dynamic_report_panel_2.png)

1. 在&#x200B;**[!UICONTROL Drop a segment here]**&#x200B;欄位中，從&#x200B;**[!UICONTROL Components]**&#x200B;索引標籤新增&#x200B;**[!UICONTROL Segment]**&#x200B;至頂端列。

   ![](assets/dynamic_report_panel_3.png)

1. 從&#x200B;**[!UICONTROL Components]**&#x200B;索引標籤拖放專案至欄和列，以建置您的表格。

   ![](assets/dynamic_report_freeform_3.png)

1. 按一下&#x200B;**[!UICONTROL Settings]**&#x200B;圖示以變更資料在欄中的顯示方式。

   ![](assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]**&#x200B;由下列專案組成：

   * **[!UICONTROL Number]**：可讓您顯示或隱藏欄中的摘要數字。
   * **[!UICONTROL Percent]**：可讓您顯示或隱藏欄中的百分比。
   * **[!UICONTROL Interpret zero as no value]**：可讓您在值等於零時顯示或隱藏。
   * **[!UICONTROL Background]**：可讓您顯示或隱藏儲存格中的水準進度列。
   * **[!UICONTROL Include retries]**：可讓您在結果中包含重試。 這僅適用於&#x200B;**[!UICONTROL Sent]**&#x200B;和&#x200B;**[!UICONTROL Bounces + Errors]**。

1. 選取一或多個列，然後按一下&#x200B;**[!UICONTROL Visualize]**&#x200B;圖示。 視覺效果會新增，以反映您選取的列。

   ![](assets/dynamic_report_freeform_5.png)

您現在可以視需要新增任意數量的元件，也可以新增視覺效果以提供資料的圖形表示。
