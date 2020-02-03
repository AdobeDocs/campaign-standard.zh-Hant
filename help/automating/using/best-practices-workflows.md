---
title: 工作流程最佳範例
description: 瞭解如何將最佳實務套用至您的工作流程。
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# 工作流程最佳實務{#workflow-best-practices}

有了Adobe Campaign，您可以設定所有類型的工作流程，以執行大範圍的工作。 不過，在設計和執行工作流程時，您必須非常小心，因為不當的實施可能會導致效能不佳、錯誤和平台問題。 您可以在下方找到最佳實務和疑難排解秘訣。

>[!NOTE]
>
>工作流程設計和執行必須由Adobe Campaign進階使用者執行。

## 命名{#naming}

為方便工作流程疑難排解，Adobe建議您明確命名工作流程並加上標籤。 填寫工作流程的說明欄位，匯總要執行的程式，讓營運商可輕鬆瞭解。
如果工作流是涉及多個工作流的流程的一部分，您可以在輸入標籤時使用數字來清楚地對它們進行排序。

例如：

* 001 —— 導入——導入收件人
* 002 —— 導入——導入銷售
* 003 —— 導入——導入銷售詳細資訊
* 010 —— 匯出——匯出傳送記錄檔
* 011 —— 匯出——匯出追蹤記錄檔

## 複製工作流程{#duplicating-workflows}

您可以複製工作流程。 在中， **[!UICONTROL Marketing Activities]**將滑鼠指標暫留在工作流程上，然後按一下**[!UICONTROL Duplicate element]**。 複製後，工作流的修改不會轉存到工作流的副本中。 可以編輯工作流的副本。

![](assets/duplicating_workflow.png)

## 執行{#execution}

### 工作流程數量

依預設，我們建議不要同時執行超過20個作用中的工作流程。 在達到此限制後，工作流程將排入佇列，以免影響效能。 同樣地，Adobe建議您將工作流程執行分散到不同的時間。
在特定情況下，您可能需要執行超過20個工作流程。 它不適用於等待排程執行的工作流程。  如果是，您需要向Campaign專家檢查使用案例，並聯絡Adobe客戶服務以提高限制。

### 頻率

工作流程無法每隔10分鐘自動執行一次。
活動的重複頻率不得少於10分鐘。 如果重複頻率設為0（也是預設值），則不會考慮此選項，並會根據執行頻率執行工作流程。

### 暫停的工作流程

已暫停或失敗狀態超過7天的工作流程會停止，以減少磁碟空間。 清除任務顯示在工作流日誌中。

### 轉場效果

仍可執行包含未終止轉場的工作流程：它將產生警告訊息，工作流程在轉場時會暫停，但不會產生錯誤。 您也可以在沒有完成設計的情況下開始工作流程，並隨時完成工作流程。

如需詳細資訊，請參閱「執行 [工作流程」](../../automating/using//executing-a-workflow.md)。

### 時區

工作流屬性允許您定義在其所有活動中預設使用的特定時區。 依預設，工作流程的時區是為目前的促銷活動運算子定義的時區。


## 活動{#activity}

### 工作流程設計

為確保工作流程正常結束，請使用 **[!UICONTROL End activity]**。 請避免將工作流程的最後一個轉場作業單獨進行。

要訪問轉場的詳細視圖，請選中工 **[!UICONTROL Keep interim results]**作流屬性的「執行」部分中的選項。

>[!CAUTION]
>
>此選項佔用了大量磁碟空間，旨在幫助您構建工作流並確保正確的配置和行為。 在生產例項中保留未選中狀態。

![](assets/keep_interim_best_practices.png)


### 標籤活動{#activity-labeling}

在開發工作流程時，會針對每個活動產生名稱，就像所有Adobe Campaign物件一樣。 雖然工具會產生活動名稱，且無法編輯，但建議在設定活動名稱時，以明確的名稱加上標籤。

### 複製活動{#activity-duplicating}

若要複製現有活動，您可以使用複製貼上。 如此，您就可保留原本定義的設定。 如需詳細資訊，請參閱「復 [制工作流程」活動](../../automating/using/workflow-interface.md)。

### 排程器活動{#acheduler-activity}

在建立工作流程時，每個分支僅使 **[!UICONTROL Scheduler activity]**用一個。 如果工作流的同一分支有多個調度程式（相互連結），則要執行的任務數將呈指數倍增，這將大大超出資料庫。

您可以按一下，預覽工作流程的下十個執行 **[!UICONTROL Preview next executions]**。

![](assets/preview_scheduler.png)

有關詳細資訊，請參 [閱Scheduler活動](../../automating/using/scheduler.md)。

## 使用參數呼叫工作流程{#workflow-with-parameters}

請確定參數的名稱和數目與呼叫工作流時所定義的相同(請參閱呼 [叫工作流時定義參數](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow))。 參數的類型也必須與預期值一致。

請確定所有參數都已在中聲明 **[!UICONTROL External signal activity]**。 否則，當執行活動時將發生錯誤。

如需詳細資訊，請參 [閱使用外部參數呼叫工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md)。

## 導出包{#exporting-packages}

要導出包，導出的資源不能包含預設ID。 因此，必須使用與Adobe Campaign Standard標準範本不同的名稱來變更可匯出資源的ID。
如需詳細資訊，請參 [閱管理套件](../../automating/using/managing-packages.md)。

## 匯出清單{#exporting-lists}

導出清單選項允許預設情況下導出最多100,000行，並且由 **Nms_ExportListLimit選項定義**。 此選項可由功能管理員管理，位於 **[!UICONTROL Administration]**>**[!UICONTROL Application settings]** >下 **[!UICONTROL Options]**。
如需詳細資訊，請參閱匯[出清單](../../automating/using/exporting-lists.md)。

## 疑難排解{#workflow-troubleshooting}

Adobe Campaign提供多種記錄檔，讓您更清楚地瞭解工作流程問題。

### 使用工作流程記錄檔{#using-workflow-logs}

您可以存取工作流程記錄檔，以監控活動的執行。 它按時間順序對執行的操作和執行錯誤進行索引。 「日誌」頁籤包含所有或某些選定活動的執行歷史記錄。
「任務」頁籤詳細說明了活動的執行順序。 若要取得活動的詳細資訊，請按一下工作。
有關詳細資訊，請參閱「監 [視工作流執行」](../../automating/using/executing-a-workflow.md#monitoring)。

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

可以在[日誌]頁籤中分析SQL查詢。

1. 在工作流程工作區中，按一下 **[!UICONTROL Edit properties]**。
1. 在 **[!UICONTROL General]**>**[!UICONTROL Execution]**&#x200B;中，勾選 **[!UICONTROL Save SQL queries in the log]**和選**[!UICONTROL Execute in the engine]** 項並按一下 **[!UICONTROL Confirm]**。

**要在日誌中查看SQL查詢，請執行以下操作：**
1. 按一下 **[!UICONTROL Log and Tasks]**.
1. 在標籤 **[!UICONTROL Logs]**中，開啟面**[!UICONTROL Search]** 板。
1. 查 **[!UICONTROL Display SQL logs only]**。

查詢顯示在日 **[!UICONTROL Message]**志的列中。

### 使用傳送記錄檔{#using-delivery-logs}

傳送記錄可監控傳送的成功。 排除記錄在準備傳送期間傳回已排除的訊息。 傳送記錄檔可提供每個描述檔的傳送狀態。
如需詳細資訊，請參閱「了 [解傳送失敗](../../sending/using/understanding-delivery-failures.md)」。

### 使用傳送警報{#delivery-alerting}

「傳送警報」功能是警報管理系統，可讓一組使用者自動接收包含其傳送執行資訊的通知。
如需詳細資訊，請參閱「 [傳送警報」](../../sending/using/receiving-alerts-when-failures-happen.md)。

**相關主題：**

* [錯誤管理](../../automating/using/executing-a-workflow.md#error-management)
