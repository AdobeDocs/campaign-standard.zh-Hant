---
title: 調用工作流的用例
description: 本節詳細說明如何使用外部參數調用工作流。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 1%

---

# 使用案例 {#use-case}

下面的使用案例說明了如何使用工作流中的參數調用工作流。

目標是從具有外部參數的API調用觸發工作流。 此工作流將從檔案將資料載入到資料庫中並建立關聯的訪問群體。 一旦建立了受眾，將觸發第二個工作流以發送使用API調用中定義的外部參數個性化的消息。

要執行此使用情形，您需要執行以下操作：

1. **進行API調用** 以使用外部參數觸發工作流1。 請參閱 [步驟1:配置API調用](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call)。
1. **生成工作流1**:工作流將傳輸檔案並將其載入到資料庫中。 然後，如果資料為空或不空，它將test，並最終將配置檔案保存到受眾中。 最後，觸發工作流2。 請參閱 [步驟2:配置工作流1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1)。
1. **生成工作流2**:工作流將讀取在工作流1中建立的受眾，然後向配置檔案發送個性化消息，並使用參數自定義段代碼。 請參閱 [第3步：配置工作流2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)。

![](assets/extsignal_uc_process.png)

## 必要條件 {#prerequisites}

在配置工作流之前，您需要使用 **[!UICONTROL External signal]** 每個活動。 這樣，在調用工作流時，您就可以瞄準這些信號活動。

## 步驟1:配置API調用 {#step-1--configuring-the-api-call}

進行API調用，以使用參數觸發工作流1。 有關API調用語法的詳細資訊，請參閱 [Campaign StandardREST API文檔](../../api/using/triggering-a-signal-activity.md)。

在本例中，我們要使用以下參數調用工作流：

* **檔案目標**:要導入到資料庫的檔案的名稱。
* **折扣設計**:要在交貨中顯示折扣的說明。

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

工作流1的構建方式如下：

* **[!UICONTROL External signal]** 活動：其中必須聲明外部參數才能在工作流中使用。
* **[!UICONTROL Transfer file]** 活動：使用參數中定義的名稱導入檔案。
* **[!UICONTROL Load file]** 活動：將資料從導入的檔案載入到資料庫中。
* **[!UICONTROL Update data]** 活動：使用導入檔案中的資料插入或更新資料庫。
* **[!UICONTROL Test]** 活動：檢查是否導入了資料。
* **[!UICONTROL Save audience]** 活動：如果檔案包含資料，則將配置檔案保存到受眾中。
* **[!UICONTROL End activity]** 活動：使用要在其中使用的參數調用工作流2。

![](assets/extsignal_uc_wkf1.png)

按照以下步驟配置工作流：

1. 聲明已在API調用中定義的參數。 為此，請開啟 **[!UICONTROL External signal]** 活動，然後添加參數的名稱和類型。

   ![](assets/extsignal_uc1.png)

1. 添加 **[!UICONTROL Transfer file]** 將資料導入資料庫的活動。為此，請拖放活動，開啟活動，然後選擇 **[!UICONTROL Protocol]** 頁籤。
1. 選擇 **[!UICONTROL Use a dynamic file path]** ，則使用 **檔案目標** 參數作為要傳輸的檔案：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. 將資料從檔案載入到資料庫。

   要執行此操作，請拖放 **[!UICONTROL Load file]** 將活動放入工作流中，然後根據需要配置。

1. 使用導入檔案中的資料插入和更新資料庫。

   要執行此操作，請拖放 **[!UICONTROL Update data]** 活動，然後選擇 **[!UICONTROL Identification]** 頁籤，以添加協調條件（在我們的情況下） **電子郵件** )。

   ![](assets/extsignal_uc3.png)

1. 選擇 **[!UICONTROL Fields to update]** 頁籤，然後指定要在資料庫中更新的欄位(在我們的情況下， **名字** 和 **電子郵件** )。

   ![](assets/extsignal_uc4.png)

1. 檢查是否從檔案檢索到資料。 要執行此操作，請拖放 **[!UICONTROL Test]** 活動，然後按一下 **[!UICONTROL Add an element]** 按鈕
1. 命名並定義條件。 在本例中，我們希望test出站轉換是否包含以下語法的資料：

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. 如果檢索到資料，則將其保存到受眾中。 為此，請添加 **[!UICONTROL Save audience]** 活動 **目標不為空** 過渡，然後開啟它。
1. 選擇 **[!UICONTROL Use a dynamic label]** ，則使用 **檔案目標** 參數（作為受眾的標籤）:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. 拖放 **[!UICONTROL End]** 將使用參數調用工作流2的活動，然後將其開啟。
1. 選擇 **[!UICONTROL External signal]** 頁籤，然後指定要觸發的工作流及其關聯的信號活動。
1. 定義要在工作流2中使用的參數及其關聯值。

   在本例中，我們要傳遞API調用中最初定義的參數(**檔案目標** 和 **折扣設計**)和 **段代碼** 值（「20%折扣」）。

   ![](assets/extsignal_uc7.png)

已配置工作流1，您現在可以生成工作流2。 如需詳細資訊，請參閱[本章節](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2)。

## 第3步：配置工作流2 {#step-3--configuring-workflow-2}

工作流2將按如下方式構建：

* **[!UICONTROL External signal]** 活動：其中必須聲明參數才能在工作流中使用。
* **[!UICONTROL Read audience]** 活動：讀取保存在工作流1中的受眾。
* **[!UICONTROL Email delivery]** 活動：向目標受眾發送定期消息，並使用參數進行個性化。

![](assets/extsignal_uc_wkf2.png)

按照以下步驟配置工作流：

1. 聲明已在工作流1中定義的參數。

   為此，請開啟 **[!UICONTROL External signal]** ，然後添加在 **[!UICONTROL End]** 工作流1的活動。

   ![](assets/extsignal_uc8.png)

1. 使用已保存在工作流1中的訪問群體。 要執行此操作，請拖放 **[!UICONTROL Read audience]** 活動，然後將其開啟。
1. 選擇 **[!UICONTROL Use a dynamic audience]** ，則使用 **檔案目標** 參數，作為要讀取的受眾的名稱：

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. 根據 **段代碼** 的下界。

   要執行此操作，請選擇 **[!UICONTROL Transition]** ，則 **[!UICONTROL Use a dynamic segment code]** 的雙曲餘切值。

1. 使用 **段代碼** 參數作為出站轉換的名稱：

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. 拖放 **[!UICONTROL Email delivery]** 的子菜單。
1. 確定消息中要使用的參數，以使用 **折扣設計** 的下界。 為此，請開啟活動的高級選項，然後添加參數名稱和值。

   ![](assets/extsignal_uc10b.png)

1. 您現在可以配置消息。 開啟活動，然後選擇 **[!UICONTROL Recurring email]**。

   ![](assets/extsignal_uc11.png)

1. 選擇要使用的模板，然後根據需要定義電子郵件屬性。
1. 使用 **折扣設計** 參數。 為此，請從個性化欄位清單中選擇它。

   ![](assets/extsignal_uc13.png)

1. 您現在可以完成配置消息，然後照常發送。

   ![](assets/extsignal_uc14.png)

## 執行工作流 {#executing-the-workflows}

構建工作流後，您可以執行它們。 在執行API調用之前，確保啟動兩個工作流。
