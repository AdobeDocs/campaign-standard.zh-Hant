---
title: 新增面板
description: 動態報表可讓您新增面板，以根據所選的時段更好地篩選資料。
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

## 新增空白麵板 {#adding-a-blank-panel}

若要啟動報表，您可以新增一組面板至立即可用或自訂報表。 每個面板包含不同的資料集，且由自由表格和視覺效果組成。

此面板可讓您視需要建立報表。 您可以在報表中新增任意數量的面板，以便依不同的時段篩選資料。

1. 按一下&#x200B;**面板**&#x200B;圖示。 您也可以按一下&#x200B;**插入標籤**&#x200B;並選取&#x200B;**新增空白麵板**&#x200B;來新增面板。

   ![](assets/dynamic_report_panel_1.png)

1. 將&#x200B;**空白麵板**&#x200B;拖放至控制面板。

   ![](assets/dynamic_report_panel.png)

您現在可以新增自由表格至面板，以開始鎖定目標資料。

## 新增自由表格 {#adding-a-freeform-table}

自由表格可讓您建立表格，以使用&#x200B;**Component**&#x200B;表格中可用的不同量度和維度來分析資料。

每個表格和視覺效果都可調整大小，並可移動以更妥善地自訂報表。

1. 按一下&#x200B;**[!UICONTROL Panels]**&#x200B;圖示。

   ![](assets/dynamic_report_panel_1.png)

1. 將&#x200B;**[!UICONTROL Freeform]**&#x200B;項目拖放至控制面板。

   您也可以按一下&#x200B;**[!UICONTROL Insert]**&#x200B;標籤並選取&#x200B;**[!UICONTROL New Freeform]**，或按一下空白麵板中的&#x200B;**[!UICONTROL Add a freeform table]**&#x200B;來新增表格。

   ![](assets/dynamic_report_panel_2.png)

1. 在&#x200B;**[!UICONTROL Drop a segment here]**&#x200B;欄位中，從&#x200B;**[!UICONTROL Components]**&#x200B;標籤將&#x200B;**[!UICONTROL Segment]**&#x200B;新增至頂端列。

   ![](assets/dynamic_report_panel_3.png)

1. 將&#x200B;**[!UICONTROL Components]**&#x200B;索引標籤中的項目拖放至欄和列，以建立表格。

   ![](assets/dynamic_report_freeform_3.png)

1. 按一下&#x200B;**[!UICONTROL Settings]**&#x200B;圖示以變更資料在欄中的顯示方式。

   ![](assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]**&#x200B;由以下部分組成：

   * **[!UICONTROL Number]**:可讓您顯示或隱藏欄中的摘要數字。
   * **[!UICONTROL Percent]**:可讓您顯示或隱藏欄中的百分比。
   * **[!UICONTROL Interpret zero as no value]**:可讓您在值等於零時顯示或隱藏。
   * **[!UICONTROL Background]**:可讓您顯示或隱藏儲存格中的水準進度列。
   * **[!UICONTROL Include retries]**:可讓您在結果中包含重試次數。這僅適用於&#x200B;**[!UICONTROL Sent]**&#x200B;和&#x200B;**[!UICONTROL Bounces + Errors]**。

1. 選取一或多列，然後按一下&#x200B;**[!UICONTROL Visualize]**&#x200B;圖示。 系統會新增視覺效果，以反映您選取的列。

   ![](assets/dynamic_report_freeform_5.png)

您現在可以新增所需的元件，並新增視覺效果，以呈現資料的圖形表示。
