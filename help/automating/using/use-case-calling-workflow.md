---
title: 使用外部參數呼叫工作流程
description: 本節詳細說明如何使用外部參數呼叫工作流程。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 1%

---

# 使用案例 {#use-case}

以下使用案例說明如何使用工作流程中的參數呼叫工作流程。

目標是從含有外部參數的API呼叫觸發工作流程。 此工作流程會從檔案將資料載入至您的資料庫，並建立相關的對象。 建立對象後，將觸發第二個工作流程，以傳送與API呼叫中定義的外部參數個人化的訊息。

若要執行此使用案例，您必須執行下列動作：

1. **進行API呼叫** 以使用外部參數觸發工作流程1。 請參閱 [步驟1:設定API呼叫](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **建置工作流程1**:工作流程會傳輸檔案並將其載入資料庫。 接著會測試資料是否空白，並最終將設定檔儲存至對象。 最後，它會觸發工作流程2。 請參閱 [步驟2:配置工作流1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **建置工作流程2**:工作流程將讀取在工作流程1中建立的對象，然後傳送個人化訊息至設定檔，並使用參數自訂的區段代碼。 請參閱 [步驟3:配置工作流2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## 先決條件 {#prerequisites}

在設定工作流程之前，您需要使用 **[!UICONTROL External signal]** 活動。 如此一來，您就可以在呼叫工作流程時鎖定這些訊號活動。

## 步驟1:設定API呼叫 {#step-1--configuring-the-api-call}

進行API呼叫以使用參數觸發工作流程1。 如需API呼叫語法的詳細資訊，請參閱 [Campaign StandardREST API檔案](../../api/using/triggering-a-signal-activity.md).

在我們的案例中，我們想使用下列參數呼叫工作流程：

* **fileToTarget**:要導入資料庫的檔案的名稱。
* **discountDesc**:要顯示在折扣傳送中的說明。

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

## 步驟2:配置工作流1 {#step-2--configuring-workflow-1}

工作流程1的建置如下：

* **[!UICONTROL External signal]** 活動：其中，必須聲明外部參數才能在工作流程中使用。
* **[!UICONTROL Transfer file]** 活動：會以參數中定義的名稱匯入檔案。
* **[!UICONTROL Load file]** 活動：將資料從導入的檔案載入到資料庫。
* **[!UICONTROL Update data]** 活動：插入或更新資料庫，使用從導入的檔案中獲取的資料。
* **[!UICONTROL Test]** 活動：檢查是否有匯入的資料。
* **[!UICONTROL Save audience]** 活動：如果檔案包含資料，會將設定檔儲存至對象。
* **[!UICONTROL End activity]** 活動：使用您要在其中使用的參數呼叫工作流程2。

![](assets/extsignal_uc_wkf1.png)

請依照下列步驟來設定工作流程：

1. 宣告API呼叫中已定義的參數。 若要這麼做，請開啟 **[!UICONTROL External signal]** 活動，然後新增參數的名稱和類型。

   ![](assets/extsignal_uc1.png)

1. 新增 **[!UICONTROL Transfer file]** 將資料導入資料庫的活動。要執行此操作，請拖放活動，開啟它，然後選擇 **[!UICONTROL Protocol]** 標籤。
1. 選取 **[!UICONTROL Use a dynamic file path]** 選項，然後使用 **fileToTarget** 參數作為要傳輸的檔案：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. 將資料從檔案載入資料庫。

   若要這麼做，請拖放 **[!UICONTROL Load file]** 活動並放入工作流程中，然後根據您的需求進行設定。

1. 插入資料庫，並使用匯入檔案中的資料更新資料庫。

   若要這麼做，請拖放 **[!UICONTROL Update data]** 活動，然後選取 **[!UICONTROL Identification]** 索引標籤來新增調解條件(在本例中為 **電子郵件** 欄位)。

   ![](assets/extsignal_uc3.png)

1. 選取 **[!UICONTROL Fields to update]** ，然後指定要在資料庫中更新的欄位(在本例中， **名字** 和 **電子郵件** 欄位)。

   ![](assets/extsignal_uc4.png)

1. 檢查是否從檔案中擷取資料。 若要這麼做，請拖放 **[!UICONTROL Test]** 活動並進入工作流程，然後按一下 **[!UICONTROL Add an element]** 按鈕來新增條件。
1. 命名並定義條件。 在本例中，我們要測試出站轉變是否包含具有下列語法的資料：

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. 如果擷取資料，則將其儲存至對象中。 若要這麼做，請新增 **[!UICONTROL Save audience]** 活動 **目標不為空** 轉變，然後開啟它。
1. 選取 **[!UICONTROL Use a dynamic label]** 選項，然後使用 **fileToTarget** 參數做為對象的標籤：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. 拖放 **[!UICONTROL End]** 使用參數呼叫工作流程2，然後開啟的活動。
1. 選取 **[!UICONTROL External signal]** ，然後指定要觸發的工作流程及其相關訊號活動。
1. 定義您要在工作流程2中使用的參數及其關聯值。

   在本例中，我們想要傳遞原本在API呼叫中定義的參數(**fileToTarget** 和 **discountDesc**)，以及 **segmentCode** 值（「20%折扣」）。

   ![](assets/extsignal_uc7.png)

工作流程1已設定，您現在可以建置工作流程2。 如需詳細資訊，請參閱[本章節](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)。

## 步驟3:配置工作流2 {#step-3--configuring-workflow-2}

工作流程2的建置方式如下：

* **[!UICONTROL External signal]** 活動：其中，必須聲明參數，才能在工作流程中使用。
* **[!UICONTROL Read audience]** 活動：讀取儲存在工作流程1中的對象。
* **[!UICONTROL Email delivery]** 活動：傳送循環訊息給目標對象，並使用參數個人化。

![](assets/extsignal_uc_wkf2.png)

請依照下列步驟來設定工作流程：

1. 聲明已在工作流1中定義的參數。

   若要這麼做，請開啟 **[!UICONTROL External signal]** 活動，然後新增中定義之每個參數的名稱和類型 **[!UICONTROL End]** 工作流1的活動。

   ![](assets/extsignal_uc8.png)

1. 使用已儲存在工作流程1中的對象。 若要這麼做，請拖放 **[!UICONTROL Read audience]** 活動並開啟至工作流程。
1. 選取 **[!UICONTROL Use a dynamic audience]** 選項，然後使用 **fileToTarget** 參數作為要讀取的對象名稱：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. 根據 **segmentCode** 參數。

   若要這麼做，請選取 **[!UICONTROL Transition]** ，然後 **[!UICONTROL Use a dynamic segment code]** 選項。

1. 使用 **segmentCode** 參數作為出站轉變的名稱：

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. 拖放 **[!UICONTROL Email delivery]** 傳送訊息給對象的活動。
1. 識別訊息中要使用的參數，以使用將 **discountDesc** 參數。 若要這麼做，請開啟活動的進階選項，然後新增參數名稱和值。

   ![](assets/extsignal_uc10b.png)

1. 您現在可以設定訊息。 開啟活動，然後選取 **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. 選取要使用的範本，然後根據您的需求定義電子郵件屬性。
1. 使用 **discountDesc** 參數做為個人化欄位。 若要這麼做，請從個人化欄位清單中選取它。

   ![](assets/extsignal_uc13.png)

1. 您現在可以完成訊息的設定，然後照常傳送。

   ![](assets/extsignal_uc14.png)

## 執行工作流程 {#executing-the-workflows}

建置工作流程後，您就可以執行這些工作流程。 執行API呼叫之前，請確定兩個工作流程已啟動。
