---
title: 管理活動的屬性
description: 瞭解如何管理工作流活動的屬性。
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

## 活動的全局屬性 {#global-properties-of-an-activity}

每個活動都有 **[!UICONTROL General]** 頁籤，用於修改特定於活動的常規參數。

![](assets/activity-properties.png)

的 **[!UICONTROL Properties]** 頁籤允許您修改活動的全局參數，特別是標籤和ID。 配置此頁籤是可選的。

![](assets/activity-properties2.png)

## 管理活動的出站過渡 {#managing-an-activity-s-outbound-transitions}

預設情況下，某些活動沒有出站轉移。 可以從 **[!UICONTROL Transitions]** 或 **[!UICONTROL Properties]** 頁籤，將其他進程應用於同一工作流中的填充。

根據活動，您可以添加幾種類型的出站過渡：

* **標準過渡**:按活動計算的人口
* **無人口過渡**:可以添加此類型的出站轉移以繼續工作流，並且不包含任何填充以不佔用系統上任何不必要的空間。
* **拒絕**:人口被拒絕。 例如，如果由於活動的入站資料不正確或不完整而無法處理該活動的入站資料。
* **補碼**:執行活動後剩餘人口。 例如，如果將分段活動配置為僅保存入站總量的百分比。

如果適用，請指定 **[!UICONTROL Segment code]** 的出站轉換。 此段代碼將允許您確定目標集合中的子集來自何處，並且稍後可能會用於消息個性化。

## 活動執行選項 {#activity-execution-options}

在活動的屬性螢幕中， **[!UICONTROL Advanced options]** 頁籤，用於定義活動的執行模式和行為以防出錯。

要訪問這些選項，請在工作流中選擇一個活動，然後使用 ![](assets/edit_darkgrey-24px.png) 按鈕。

![](assets/wkf_advanced_parameters.png)

的 **[!UICONTROL Execution]** 欄位中，您可以定義任務啟動時要執行的操作。 這有三種選擇：

* **正常**:活動正常執行。
* **啟用但不執行**:活動被暫停，因此後續的任何進程也會暫停。 如果希望在任務啟動時出現，則此選項會非常有用。
* **不啟用**:未執行該活動，因此，後續的所有活動（在同一分支中）也未執行。

的 **[!UICONTROL In case of error]** 欄位允許您指定在活動遇到錯誤時要執行的操作。 有兩個選項可供選擇：

* **暫停進程**:工作流自動掛起。 然後，工作流狀態為 **錯誤** 關聯的顏色變成紅色。 問題解決後，重新啟動工作流。
* **忽略**:未執行該活動，因此也不執行其後的任何活動（在同一分支中）。 這可能對循環任務有用。 如果分支有調度程式置於上游，則應在下一執行日期觸發該調度程式。

的 **[!UICONTROL Behavior]** 欄位中，您可以定義在使用非同步任務時要遵循的過程。 有兩個選項可供選擇：

* **已授權多個任務**:即使第一個任務沒有完成，也可以同時執行多個任務。
* **當前任務具有優先順序**:一旦任務正在執行，則優先執行此操作。 只要一個任務仍在進行中，則不會執行其他任務。

的 **[!UICONTROL Max. execution duration]** 欄位允許您指定持續時間，如「30s」或「1h」。 如果活動在經過指定的持續時間後未完成，則會觸發警報。 這不會影響工作流的運行方式。

的 **[!UICONTROL Affinity]** 欄位允許您強制在特定電腦上執行工作流或工作流活動。 為此，必須為有關的工作流或活動指定一個或多個關聯。

的 **[!UICONTROL Time zone]** 欄位中，您可以選擇活動的時區。 Adobe Campaign允許您管理同一實例上多個國家/地區之間的時間差。 在建立實例時配置應用的設定。

>[!NOTE]
>
>預設情況下，如果未選擇時區，則活動將使用工作流屬性中定義的時區。

的 **注釋** 欄位是允許您添加註釋的自由欄位。
