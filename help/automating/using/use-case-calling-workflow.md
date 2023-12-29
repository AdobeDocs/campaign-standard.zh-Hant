---
title: 呼叫工作流程的使用案例
description: 本節詳細說明如何使用外部引數呼叫工作流程。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# 使用實例 {#use-case}

以下使用案例顯示如何使用工作流程中的引數呼叫工作流程。

目標是使用外部引數從API呼叫觸發工作流程。 此工作流程會將資料從檔案載入您的資料庫，並建立關聯的對象。 建立對象後，系統會觸發第二個工作流程，使用API呼叫中定義的外部引數傳送個人化訊息。

若要執行此使用案例，您必須執行下列動作：

1. **進行API呼叫** 以使用外部引數觸發工作流程1。 另請參閱 [步驟1：設定API呼叫](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **建置工作流程1**：工作流程會傳輸檔案並將其載入資料庫。 然後它會測試資料是否空白，最終將設定檔儲存至受眾。 最後，它會觸發工作流程2。 另請參閱 [步驟2：設定工作流程1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **建置工作流程2**：工作流程將讀取在工作流程1中建立的對象，然後傳送個人化訊息給設定檔，並使用引數自訂區段代碼。 另請參閱 [步驟3：設定工作流程2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## 先決條件 {#prerequisites}

設定工作流程之前，您需要使用建立工作流程1和2 **[!UICONTROL External signal]** 活動。 如此一來，您就可以在呼叫工作流程時鎖定這些訊號活動。

## 步驟1：設定API呼叫 {#step-1--configuring-the-api-call}

進行API呼叫以使用引數觸發工作流程1。 如需API呼叫語法的詳細資訊，請參閱 [Campaign StandardREST API檔案](../../api/using/triggering-a-signal-activity.md).

在本例中，我們想使用下列引數呼叫工作流程：

* **fileToTarget**：我們要匯入資料庫的檔案名稱。
* **discountdesc**：我們要在傳遞中顯示用來取得折扣的說明。

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

## 步驟2：設定工作流程1 {#step-2--configuring-workflow-1}

工作流程1將建置如下：

* **[!UICONTROL External signal]** 活動：外部引數必須宣告才能在工作流程中使用。
* **[!UICONTROL Transfer file]** 活動：以引數中定義的名稱匯入檔案。
* **[!UICONTROL Load file]** 活動：將資料從匯入的檔案載入資料庫。
* **[!UICONTROL Update data]** 活動：使用匯入檔案的資料插入或更新資料庫。
* **[!UICONTROL Test]** 活動：檢查是否有匯入的資料。
* **[!UICONTROL Save audience]** 活動：如果檔案包含資料，會將設定檔儲存至對象。
* **[!UICONTROL End activity]** 活動：使用您想要在其中使用的引數呼叫工作流程2。

![](assets/extsignal_uc_wkf1.png)

請依照下列步驟設定工作流程：

1. 宣告API呼叫中已定義的引數。 若要這麼做，請開啟 **[!UICONTROL External signal]** 活動，然後新增引數的名稱和型別。

   ![](assets/extsignal_uc1.png)

1. 新增 **[!UICONTROL Transfer file]** 將資料匯入資料庫的活動。若要執行此動作，請拖放活動，開啟活動，然後選取 **[!UICONTROL Protocol]** 標籤。
1. 選取 **[!UICONTROL Use a dynamic file path]** 選項，然後使用 **fileToTarget** 要傳輸的檔案引數：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. 將資料從檔案載入資料庫。

   若要這麼做，請拖放 **[!UICONTROL Load file]** 活動進入工作流程，然後視需要進行設定。

1. 使用匯入檔案的資料插入並更新資料庫。

   若要這麼做，請拖放 **[!UICONTROL Update data]** 活動，然後選取 **[!UICONTROL Identification]** 索引標籤以新增調解條件(在此案例中， **電子郵件** 欄位)。

   ![](assets/extsignal_uc3.png)

1. 選取 **[!UICONTROL Fields to update]** 標籤，然後指定要在資料庫中更新的欄位(在我們的案例中， **firstname** 和 **電子郵件** 欄位)。

   ![](assets/extsignal_uc4.png)

1. 檢查是否從檔案擷取資料。 若要這麼做，請拖放 **[!UICONTROL Test]** 活動進入工作流程，然後按一下 **[!UICONTROL Add an element]** 按鈕以新增條件。
1. 命名並定義條件。 在本例中，我們要測試出站轉變是否包含使用下列語法的資料：

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. 如果擷取資料，則將其儲存到對象中。 若要這麼做，請新增 **[!UICONTROL Save audience]** 活動至 **目標不是空的** 轉變，然後開啟它。
1. 選取 **[!UICONTROL Use a dynamic label]** 選項，然後使用 **fileToTarget** 做為對象標籤的引數：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. 拖放 **[!UICONTROL End]** 使用引數呼叫工作流程2的活動，然後開啟它。
1. 選取 **[!UICONTROL External signal]** 標籤，然後指定要觸發的工作流程及其關聯的訊號活動。
1. 定義您要在「工作流程2」中使用的引數及其相關值。

   在本例中，我們想要傳遞原本在API呼叫(**fileToTarget** 和 **discountdesc**)，以及其他 **segmentCode** 具有常數值的引數（「20%折扣」）。

   ![](assets/extsignal_uc7.png)

工作流程1已設定，您現在可以建置工作流程2。 如需詳細資訊，請參閱[本章節](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)。

## 步驟3：設定工作流程2 {#step-3--configuring-workflow-2}

工作流程2將建置如下：

* **[!UICONTROL External signal]** 活動：必須宣告引數才能在工作流程中使用。
* **[!UICONTROL Read audience]** 活動：讀取儲存在工作流程1中的對象。
* **[!UICONTROL Email delivery]** 活動：傳送週期性訊息給目標對象，使用引數個人化。

![](assets/extsignal_uc_wkf2.png)

請依照下列步驟設定工作流程：

1. 宣告已在工作流程1中定義的引數。

   若要這麼做，請開啟 **[!UICONTROL External signal]** 活動，然後新增中定義之每個引數的名稱和型別 **[!UICONTROL End]** 工作流程1的活動。

   ![](assets/extsignal_uc8.png)

1. 使用工作流程1中儲存的對象。 若要這麼做，請拖放 **[!UICONTROL Read audience]** 活動進入工作流程，然後開啟它。
1. 選取 **[!UICONTROL Use a dynamic audience]** 選項，然後使用 **fileToTarget** 引數當作要讀取的對象名稱：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. 根據為出站轉變命名 **segmentCode** 引數。

   若要這麼做，請選取 **[!UICONTROL Transition]** 標籤，然後 **[!UICONTROL Use a dynamic segment code]** 選項。

1. 使用 **segmentCode** 引數作為出站轉變的名稱：

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. 拖放 **[!UICONTROL Email delivery]** 活動以傳送訊息給對象。
1. 識別訊息中要使用的引數，以透過對其進行個人化 **discountdesc** 引數。 若要這麼做，請開啟活動的進階選項，然後新增引數名稱和值。

   ![](assets/extsignal_uc10b.png)

1. 您現在可以設定訊息。 開啟活動，然後選取「 」 **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. 選取要使用的範本，然後視需要定義電子郵件屬性。
1. 使用 **discountdesc** 引數作為個人化欄位。 若要這麼做，請從個人化欄位清單中選取它。

   ![](assets/extsignal_uc13.png)

1. 您現在可以完成訊息設定，然後照常傳送。

   ![](assets/extsignal_uc14.png)

## 執行工作流程 {#executing-the-workflows}

一旦建立工作流程後，您就可以執行它們。 執行API呼叫之前，請確定兩個工作流程已開始。
