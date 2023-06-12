---
title: 新增面板
description: 動態報告可讓您新增面板，以根據所選時段更好地篩選資料。
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

若要啟動報表，您可以將一組面板新增至立即可用或自訂的報表中。 每個面板都包含不同的資料集，由自由表格和視覺效果組成。

此面板可讓您視需要建置報表。 您可以在報表中新增任意數量的面板，以使用不同的時段篩選資料。

1. 按一下 **面板** 圖示。 您也可以按一下 **插入索引標籤** 並選取 **新增空白面板**.

   ![](assets/dynamic_report_panel_1.png)

1. 拖放 **空白面板** 放入您的儀表板。

   ![](assets/dynamic_report_panel.png)

您現在可以將自由表格新增至面板，以開始鎖定目標資料。

## 新增自由表格 {#adding-a-freeform-table}

自由表格可讓您建立表格，以使用中提供的不同量度和維度來分析您的資料。 **元件** 表格。

每個表格和視覺效果皆可調整大小，並可移動以自訂報表。

1. 按一下 **[!UICONTROL Panels]** 圖示。

   ![](assets/dynamic_report_panel_1.png)

1. 拖放 **[!UICONTROL Freeform]** 個專案放入您的儀表板。

   您也可以按一下 **[!UICONTROL Insert]** 標籤並選取 **[!UICONTROL New Freeform]** 或按一下 **[!UICONTROL Add a freeform table]** 在空白面板中。

   ![](assets/dynamic_report_panel_2.png)

1. 在 **[!UICONTROL Drop a segment here]** 欄位，新增 **[!UICONTROL Segment]** 從 **[!UICONTROL Components]** 定位至頂端列。

   ![](assets/dynamic_report_panel_3.png)

1. 從拖放專案 **[!UICONTROL Components]** 定位至欄和列，以建置您的表格。

   ![](assets/dynamic_report_freeform_3.png)

1. 按一下 **[!UICONTROL Settings]** 圖示來變更資料在欄中的顯示方式。

   ![](assets/dynamic_report_freeform_4.png)

   此 **[!UICONTROL Column settings]** 由下列專案組成：

   * **[!UICONTROL Number]**：可讓您顯示或隱藏欄中的摘要數字。
   * **[!UICONTROL Percent]**：可讓您顯示或隱藏欄中的百分比。
   * **[!UICONTROL Interpret zero as no value]**：可讓您在值等於零時顯示或隱藏。
   * **[!UICONTROL Background]**：可讓您顯示或隱藏儲存格中的水準進度列。
   * **[!UICONTROL Include retries]**：可讓您在結果中包含重試。 此專案僅適用於 **[!UICONTROL Sent]** 和 **[!UICONTROL Bounces + Errors]**.

1. 選取一或多個列，然後按一下 **[!UICONTROL Visualize]** 圖示。 新增視覺效果以反映您選取的列。

   ![](assets/dynamic_report_freeform_5.png)

您現在可以視需要新增任意數量的元件，也可以新增視覺效果以提供資料的圖形表示。
