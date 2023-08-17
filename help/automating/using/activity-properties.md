---
title: 管理活動的屬性
description: 瞭解如何管理工作流程活動的屬性。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# 管理活動的屬性 {#activity-properties}

## 活動的全域屬性 {#global-properties-of-an-activity}

每個活動都有 **[!UICONTROL General]** 標籤，可讓您修改活動專屬的一般引數。

![](assets/activity-properties.png)

此 **[!UICONTROL Properties]** 標籤可讓您修改活動的全域引數，尤其是標籤和ID。 您可以選擇是否設定此標籤。

![](assets/activity-properties2.png)

## 管理活動的出站轉變 {#managing-an-activity-s-outbound-transitions}

依預設，某些活動沒有出站轉變。 您可以從以下位置新增一個： **[!UICONTROL Transitions]** 標籤或從活動的 **[!UICONTROL Properties]** 標籤，將其他程式套用至相同工作流程中的母體。

視活動而定，您可以新增數種型別的出站轉變：

* **標準轉變**：由活動運算的母體
* **無母體轉換**：此型別的出站轉變可以新增以繼續工作流程，不包含任何母體以消耗系統上任何不必要的空間。
* **拒絕**：母體已拒絕。 例如，如果活動的傳入資料因不正確或不完整而無法處理。
* **補充**：執行活動後剩餘的母體。 例如，如果分段活動設定為僅儲存入站母體的百分比。

如果適用，請指定 **[!UICONTROL Segment code]** 適用於活動的出站轉變。 此區段代碼可讓您識別目標母體的子集來自何處，以及稍後可能用於訊息個人化目的。

## 活動執行選項 {#activity-execution-options}

在活動的屬性畫面中，有一個 **[!UICONTROL Advanced options]** 索引標籤可讓您定義活動的執行模式和發生錯誤時的行為。

若要存取這些選項，請在工作流程中選取活動，然後使用 ![](assets/edit_darkgrey-24px.png) 按鈕。

![](assets/wkf_advanced_parameters.png)

此 **[!UICONTROL Execution]** 欄位可讓您定義任務啟動時要執行的動作。 此專案有三個選項：

* **一般**：活動會正常執行。
* **啟用但不執行**：活動已暫停，因此後續的任何未來程式都會暫停。 如果您想在任務啟動時出席，這會很有用。
* **不要啟用**：活動不會執行，因此後面的所有活動也不會執行（在相同分支中）。

此 **[!UICONTROL In case of error]** 欄位可讓您指定活動發生錯誤時要執行的動作。 對此有兩個可用選項：

* **暫停處理序**：工作流程會自動暫停。 然後，工作流程狀態為 **錯誤** 而關聯的顏色會變成紅色。 問題解決後，請重新啟動工作流程。
* **忽略**：活動不會執行，因此後面沒有任何活動（在相同分支中）。 事實證明，這對週期性任務很有用。 如果分支有放置在上游的排程器，這應在下一個執行日期觸發。

此 **[!UICONTROL Behavior]** 欄位可讓您定義在使用非同步工作時要遵循的程式。 對此有兩個可用選項：

* **已授權多個任務**：即使第一個任務未完成，可以同時執行多個任務。
* **目前任務有優先權**：任務進行中時，此為優先順序。 只要一個任務仍在進行中，就不會執行其他任務。

此 **[!UICONTROL Max. execution duration]** 欄位可讓您指定持續時間，例如&quot;30s&quot;或&quot;1h&quot;。 如果活動在指定的持續時間過後仍未完成，則會觸發警報。 這對工作流程的運作方式沒有影響。

此 **[!UICONTROL Affinity]** 欄位可讓您強制在特定電腦上執行工作流程或工作流程活動。 若要這麼做，您必須為相關工作流程或活動指定一或多個相關性。

此 **[!UICONTROL Time zone]** 欄位可讓您選取活動的時區。 Adobe Campaign可讓您在同一例項上管理多個國家/地區之間的時間差異。 套用的設定會在建立執行個體時進行設定。

>[!NOTE]
>
>依預設，如果未選取時區，活動將使用工作流程屬性中定義的時區。

此 **註解** 欄位是可讓您新增附註的自由欄位。
