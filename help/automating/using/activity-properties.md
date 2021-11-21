---
title: 管理活動的屬性
description: 了解如何管理工作流程活動的屬性。
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

每個活動都有 **[!UICONTROL General]** 索引標籤，可讓您修改活動專屬的一般參數。

![](assets/activity-properties.png)

此 **[!UICONTROL Properties]** 索引標籤可讓您修改活動的全域參數，尤其是標籤和ID。 設定此標籤為選用。

![](assets/activity-properties2.png)

## 管理活動的出站轉變 {#managing-an-activity-s-outbound-transitions}

依預設，某些活動沒有出站轉變。 您可以從 **[!UICONTROL Transitions]** 索引標籤或從活動的 **[!UICONTROL Properties]** 標籤，在相同工作流程中將其他程式套用至母體。

您可以根據活動新增數種類型的出站轉變：

* **標準轉變**:活動計算的母體
* **無母體轉換**:可以添加此類型的出站轉變以繼續工作流，並且不包含任何母體，以不佔用系統上任何不必要的空間。
* **拒絕**:已拒絕母體。 例如，如果由於活動不正確或不完整而無法處理活動的入站資料。
* **補充**:執行活動後剩餘的母體。 例如，如果分段活動設定為只儲存入站母體的百分比。

若適用，請指定 **[!UICONTROL Segment code]** 用於活動的出站轉變。 此區段代碼可讓您識別目標母體的子集來自何處，且稍後可能會用於訊息個人化目的。

## 活動執行選項 {#activity-execution-options}

在活動的屬性畫面中， **[!UICONTROL Advanced options]** 索引標籤，可讓您定義活動的執行模式和行為，以防發生錯誤。

若要存取這些選項，請在工作流程中選取活動，然後使用 ![](assets/edit_darkgrey-24px.png) 按鈕。

![](assets/wkf_advanced_parameters.png)

此 **[!UICONTROL Execution]** 欄位可讓您定義要在任務啟動時執行的動作。 這有三個選項：

* **正常**:活動會正常執行。
* **啟用但不執行**:活動會暫停，因此後續的任何未來程式也會暫停。 如果您想在任務啟動時出現，則此功能會很實用。
* **不啟用**:活動不會執行，因此也不會是所有追隨的活動（在相同分支中）。

此 **[!UICONTROL In case of error]** 欄位可讓您指定當活動發生錯誤時要執行的動作。 有兩個選項可供使用：

* **暫停進程**:工作流程會自動暫停。 然後，工作流狀態為 **錯誤** 而相關的顏色則變成紅色。 問題解決後，重新啟動工作流程。
* **忽略**:活動不會執行，因此後續的任何活動（在相同分支中）也不會執行。 這可能對循環任務很有用。 如果分支有排程器放在上游，則應在下一個執行日期觸發。

此 **[!UICONTROL Behavior]** 欄位可讓您定義在使用非同步任務時要遵循的程式。 有兩個選項可供使用：

* **授權多項任務**:即使第一個任務未完成，也可以同時執行多個任務。
* **當前任務具有優先順序**:一旦任務正在進行中，就會優先執行。 只要一個任務仍在進行中，則不會執行其他任務。

此 **[!UICONTROL Max. execution duration]** 欄位可讓您指定持續時間，例如「30s」或「1h」。 如果在指定的持續時間過後未完成活動，則會觸發警報。 這對工作流程的運作方式沒有影響。

此 **[!UICONTROL Affinity]** 欄位可讓您強制在特定電腦上執行工作流程或工作流程活動。 若要這麼做，您必須為工作流程或相關活動指定一或多個相關性。

此 **[!UICONTROL Time zone]** 欄位可讓您選取活動的時區。 Adobe Campaign可讓您管理同一執行個體上多個國家/地區之間的時間差異。 建立執行個體時，會設定套用的設定。

>[!NOTE]
>
>依預設，如果未選取時區，活動將使用工作流程屬性中定義的時區。

此 **註解** 欄位是可讓您新增附註的自由欄位。
