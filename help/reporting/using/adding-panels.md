---
title: 新增面板
description: 動態報告允許您添加面板以根據所選時間段更好地篩選資料。
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

## 添加空白麵板 {#adding-a-blank-panel}

要啟動報告，可將一組面板添加到現成或自定義報告中。 每個面板包含不同的資料集，由自由形式表和可視化組成。

此面板允許您根據需要生成報告。 您可以在報告中添加任意數量的面板，以便按不同的時段篩選資料。

1. 按一下 **面板** 表徵圖 也可以通過按一下 **插入頁籤** 選擇 **新建空白麵板**。

   ![](assets/dynamic_report_panel_1.png)

1. 拖放 **空白麵板** 你的儀錶盤。

   ![](assets/dynamic_report_panel.png)

現在，您可以向面板中添加自由格式表以開始目標資料。

## 添加自由形式表 {#adding-a-freeform-table}

自由形式表允許您建立表，以使用中提供的不同度量和維來分析資料 **元件** 的子菜單。

每個表和可視化都可調整大小，可以移動以更好地定制報告。

1. 按一下 **[!UICONTROL Panels]** 表徵圖

   ![](assets/dynamic_report_panel_1.png)

1. 拖放 **[!UICONTROL Freeform]** 項目。

   也可以通過按一下 **[!UICONTROL Insert]** 頁籤 **[!UICONTROL New Freeform]** 或 **[!UICONTROL Add a freeform table]** 的子菜單。

   ![](assets/dynamic_report_panel_2.png)

1. 在 **[!UICONTROL Drop a segment here]** 欄位，添加 **[!UICONTROL Segment]** 從 **[!UICONTROL Components]** 按鈕。

   ![](assets/dynamic_report_panel_3.png)

1. 從 **[!UICONTROL Components]** 頁籤。

   ![](assets/dynamic_report_freeform_3.png)

1. 按一下 **[!UICONTROL Settings]** 表徵圖以更改資料在列中的顯示方式。

   ![](assets/dynamic_report_freeform_4.png)

   的 **[!UICONTROL Column settings]** 由下列組成：

   * **[!UICONTROL Number]**:用於顯示或隱藏列中的摘要數字。
   * **[!UICONTROL Percent]**:允許您在列中顯示或隱藏百分比。
   * **[!UICONTROL Interpret zero as no value]**:允許在值等於零時顯示或隱藏。
   * **[!UICONTROL Background]**:用於顯示或隱藏單元格中的水準進度條。
   * **[!UICONTROL Include retries]**:允許您在結果中包括重試。 僅適用於 **[!UICONTROL Sent]** 和 **[!UICONTROL Bounces + Errors]**。

1. 選擇一行或多行，然後按一下 **[!UICONTROL Visualize]** 表徵圖 將添加一個可視化，以反映您選擇的行。

   ![](assets/dynamic_report_freeform_5.png)

現在，您可以根據需要添加盡可能多的元件，還可以添加可視化效果，以提供資料的圖形表示。
