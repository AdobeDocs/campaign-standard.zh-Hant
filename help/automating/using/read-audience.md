---
title: 讀取閱聽眾
description: 「讀取對象」活動可讓您擷取現有對象，並套用其他篩選條件以加以調整。
page-status-flag: 從未激活
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 定位活動
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 讀取閱聽眾{#read-audience}

## 說明 {#description}

![](assets/prefill.png)

此活 **[!UICONTROL Read audience]** 動可讓您擷取現有的觀眾，並套用其他篩選條件來調整觀眾。

## 使用內容 {#context-of-use}

此活 **[!UICONTROL Read audience]** 動是活動的簡單版本，專 **[!UICONTROL Query]** 為您只需要選取現有對象的情況而設計。

## 配置 {#configuration}

1. 將活動 **[!UICONTROL Read audience]** 拖放至工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 選取您要從標籤擷取的對 **[!UICONTROL Properties]** 像。

   您可以擷取下列類型的觀眾： **[!UICONTROL List]**、 **[!UICONTROL Query]****[!UICONTROL File]** 和 **[!UICONTROL Experience Cloud]**。 如需觀眾類型的詳細資訊，請參閱「觀眾 [」檔案](../../audiences/using/about-audiences.md) 。

   選 **[!UICONTROL Use a dynamic audience]** 項可讓您根據工作流程的事件變數定義要定位的對象名稱。 如需詳細資訊，請參閱「使用事件變 [數自訂活動](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 」一節。

   ![](assets/readaudience_activity1.png)

1. 如果您想要將其他篩選套用至選取的對象，請透過活動的標 **[!UICONTROL Source filtering]** 簽新增條件。

   有關建立篩選條件的詳細資訊，請參閱「創 [建查詢](../../automating/using/editing-queries.md#creating-queries) 」文檔。

1. 確認活動的設定並儲存工作流程。

## 範例：協調檔案對象與資料庫 {#example--reconcile-a-file-audience-with-the-database}

此範例說明如何使用活 **[!UICONTROL Read audience]** 動協調直接從檔案匯入建立的對象。

執行檔案匯入時，您可以直接將其內容儲存在觀眾中。 此對象是檔案對象，其資料未連結至任何資料庫資源。

匯入工作流程的設計如下：

![](assets/readaudience_activity_example3.png)

* 「載 [入檔案](../../automating/using/load-file.md) 」活動會上傳包含從外部工具擷取之描述檔資料的檔案。

   例如：

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* 「儲 [存觀眾](../../automating/using/save-audience.md) 」活動會將傳入的資料儲存為觀眾。 由於資料尚未協調，因此對象是檔案對象，其資料尚未被識別為描述檔資料。

協調工作流程的設計如下：

![](assets/readaudience_activity_example2.png)

* 活動 **[!UICONTROL Read audience]** 會上傳在匯入工作流程中建立的檔案對象。 觀眾資料尚未與Adobe Campaign資料庫協調。
* 「協 [調](../../automating/using/reconciliation.md) 」活動通過其頁籤將傳入資料標識為配 **[!UICONTROL Identification]** 置檔案。 例如，使用電子郵件 **欄位** 作為協調標準。
* 「更 [新資料](../../automating/using/update-data.md) 」活動將插入和更新帶有傳入資料的資料庫的配置檔案資源。 由於資料已標識為配置檔案，您可以選 **[!UICONTROL Directly using the targeting dimension]** 擇選項並 **[!UICONTROL Profiles]** 在活動 **[!UICONTROL Identification]** 的頁籤中選擇。 然後，您只需要在標籤中新增需要更新的欄位清單。

## 範例：結合兩個精美受眾 {#example--union-on-two-refined-audiences}

此示例中定義的工作流顯示了兩個活動的 **[!UICONTROL Read audience]** 合併。 此工作流程的目標是傳送電子郵件給年齡在18到30歲之間的金級或銀級會員。

系統中已建立特定對象，以追蹤金級和銀級會員。

工作流設計如下：

![](assets/readaudience_activity_example1.png)

* 第一個 **[!UICONTROL Read audience]** 活動，可擷取金級會員對象，並只選取18到30歲的設定檔來調整它。
* 第二個 **[!UICONTROL Read audience]** 活動會擷取銀色會員觀眾，並只選取18到30歲的設定檔，以調整觀眾。
* 一種 **[!UICONTROL Union]** 將兩種活動的人口統一 **[!UICONTROL Read audiences]** 為最終人口的活動。
* 將電 **[!UICONTROL Email delivery]** 子郵件傳送給來自活動之人口的活 **[!UICONTROL Union]** 動。

