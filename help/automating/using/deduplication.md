---
title: 重複資料刪除
description: 重複資料刪除活動可讓您刪除入站活動結果中的重複項目。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 97%

---


# 重複資料刪除{#deduplication}

## 說明 {#description}

![](assets/deduplication.png)

**[!UICONTROL Deduplication]** 活動可讓您刪除入站活動結果中的重複項目。

## 使用內容 {#context-of-use}

**[!UICONTROL Deduplication]** 活動通常用於目標定位活動後或匯入檔案後，以及允許使用目標定位資料之活動前。

在重複資料刪除期間，會單獨處理入站轉變。例如，如果設定檔 &#39;A&#39; 出現在查詢 1 的結果，也出現在查詢 2 的結果中，將不會進行重複資料刪除。

因此，建議重複資料刪除僅具有一個入站轉變。要執行此操作，您可以透過使用與您目標定位需求（例如，聯合活動與交集活動等）相對應的活動以組合不同的查詢。例如：

![](assets/dedup_bonnepratique.png)

**相關主題**

* [使用案例： 在傳送前識別重複項目](../../automating/using/identifying-duplicated-before-delivery.md)
* [使用案例： 從導入的檔案中消除重複資料](../../automating/using/deduplicating-data-imported-file.md)

## 設定 {#configuration}

設定重複資料刪除的活動，必須輸入標籤、方法與重複資料刪除的條件，以及與結果相關的選項。

1. 將 **[!UICONTROL Deduplication]** 活動拖放至工作流程中。
1. 選取活動，然後使用所顯示快速操作中的 ![](assets/edit_darkgrey-24px.png) 按鈕將其開啟。

   ![](assets/deduplication_1.png)

1. 選取必須對其執行重複資料刪除的 **[!UICONTROL Resource type]**：

   * **[!UICONTROL Database resource]** 如果對資料庫中已存在的資料執行重複資料刪除。選取 **[!UICONTROL Filtering dimension]** 和 **[!UICONTROL Targeting dimension]**，根據您想執行重複資料刪除之資料。預設情況下，在&#x200B;**設定檔**&#x200B;執行重複資料刪除。
   * **[!UICONTROL Temporary resource]** 如果對工作流程的臨時資料執行重複資料刪除：選取包含要重複資料刪除之資料的 **[!UICONTROL Targeted set]**。在匯入檔案或資料庫中的資料已擴充（例如使用區段代碼）後，就會遇到此使用案例。

1. 選取 **[!UICONTROL Number of unique records to keep]**。此欄位的預設值為 1。如果值為 0 則可讓您保留所有重複項目。

   例如，如果記錄 A 和 B 被視為記錄 Y 的重複項目，而記錄 C 被視為記錄 Z 的重複項目：

   * 如果該欄位的值為 1：僅保留 Y 和 Z 記錄。
   * 如果該欄位的值為 0：會保留所有記錄。
   * 如果該欄位的值為 2：會保留記錄 C 和 Z，並且將保留 A、B 和 Y 中的兩條記錄，這是偶然的或取決於之後所選取的重複資料刪除方法。

1. 在提供的清單中新增條件，以定義 **[!UICONTROL Duplicate identification]** 條件。指定具有完全相同值的欄位和/或運算式，以便識別重複資料刪除：電子郵件地址、名字、姓氏等。條件的順序可讓您指定首要處理的條件。
1. 在下拉式清單中，選取要使用的 **[!UICONTROL Deduplication method]**：

   * **[!UICONTROL Choose for me]**：隨機選取要保留在重複項目外的記錄。
   * **[!UICONTROL Following a list of values]**：可讓您定義一或多個欄位的值優先順序。若要定義值，請選取欄位或建立運算式，然後將值新增至適當的資料表中。若要定義新欄位，請按一下值清單上方的 **[!UICONTROL Add]** 按鈕。

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**：您可以保留所選運算式的值不為空白的記錄作為優先順序。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**：這可讓您保留所入站運算式的值最小或最大的記錄。

      ![](assets/deduplication_4.png)

1. 如有需要，請管理活動的[轉變](../../automating/using/activity-properties.md)，以存取輸出母體的進階選項。
1. 確認活動的設定並儲存工作流程。
