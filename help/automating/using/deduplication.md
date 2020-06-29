---
title: 重複資料刪除
description: 重複資料消除活動允許您刪除入站活動結果中的重複項。
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
ht-degree: 0%

---


# 重複資料刪除{#deduplication}

## 說明 {#description}

![](assets/deduplication.png)

活 **[!UICONTROL Deduplication]** 動允許您刪除入站活動結果中的重複項。

## 使用內容 {#context-of-use}

活動 **[!UICONTROL Deduplication]** 通常用於定位活動後或匯入檔案後，以及允許使用定位資料之活動前。

在重複資料消除期間，入站轉換會單獨處理。 例如，如果配置檔案&#39;A&#39;出現在查詢1的結果中，也出現在查詢2的結果中，則不會對其進行重複資料消除。

因此，建議重複資料消除只有一個入站過渡。 若要這麼做，您可以使用符合您定位需求的活動（例如聯合活動、交叉點活動等）來結合不同的查詢。 例如：

![](assets/dedup_bonnepratique.png)

**相關主題**

* [使用案例： 在傳送前識別重複項目](../../automating/using/identifying-duplicated-before-delivery.md)
* [使用案例： 從導入的檔案中消除重複資料](../../automating/using/deduplicating-data-imported-file.md)

## 配置 {#configuration}

要配置重複資料消除活動，必須輸入標籤、方法和重複資料消除標準，以及與結果相關的選項。

1. 將活動拖放 **[!UICONTROL Deduplication]** 到工作流程中。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。

   ![](assets/deduplication_1.png)

1. 選擇必 **[!UICONTROL Resource type]** 須執行重複資料消除的位置：

   * **[!UICONTROL Database resource]** 如果對資料庫中已存在的資料執行重複資料消除。 根據 **[!UICONTROL Filtering dimension]** 要 **[!UICONTROL Targeting dimension]**&#x200B;消除重複的資料，選擇和。 預設情況下，對配置檔案執行重複數 **據消除**。
   * **[!UICONTROL Temporary resource]** 如果對工作流的臨時資料執行重複資料消除： 選擇包 **[!UICONTROL Targeted set]** 含要消除重複的資料。 在匯入檔案或資料庫中的資料已豐富（例如使用區段代碼）後，就會遇到此使用案例。

1. 選擇 **[!UICONTROL Number of unique records to keep]**。 此欄位的預設值為1。 值0允許您保留所有重複項。

   例如，如果記錄A和B被視為記錄Y的重複項，而記錄C被視為記錄Z的重複項：

   * 如果欄位的值為1: 只保存Y和Z記錄。
   * 如果欄位的值為0: 所有記錄都保存了。
   * 如果欄位的值為2: 記錄C和Z被保存，並且A、B和Y中的兩條記錄被保存，這是偶然的，或取決於之後選擇的重複資料消除方法。

1. 在提供的 **[!UICONTROL Duplicate identification]** 清單中新增條件，以定義標準。 指定允許標識重複值的欄位和／或表達式： 電子郵件地址、名字、姓氏等。 條件的順序允許您指定要首先處理的條件。
1. 在下拉式清單中，選取要 **[!UICONTROL Deduplication method]** 使用的：

   * **[!UICONTROL Choose for me]**: 隨機選擇要從重複項中保留的記錄。
   * **[!UICONTROL Following a list of values]**: 可讓您定義一或多個欄位的值優先順序。 要定義值，請選擇一個欄位或建立表達式，然後將值添加到相應的表中。 若要定義新欄位，請按一 **[!UICONTROL Add]** 下值清單上方的按鈕。

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: 這可讓您保留所選運算式值不為空的記錄作為優先順序。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: 這可讓您保留輸入的運算式值最小或最大的記錄。

      ![](assets/deduplication_4.png)

1. 如有需要，請管理活動的 [轉場](../../automating/using/activity-properties.md) ，以存取出站人口的進階選項。
1. 確認活動的設定並儲存工作流程。
