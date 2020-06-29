---
title: 使用其他資料個人化電子郵件
description: 此使用案例說明如何新增不同類型的其他資料至查詢，並將它當成電子郵件中的個人化欄位。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# 使用其他資料個人化電子郵件 {#example--personalizing-an-email-with-additional-data}

下列範例說明如何新增不同類型的其他資料至查詢，以及其作為電子郵件中個人化欄位的用途。 如需如何豐富活動所定位資料的詳細 **[!UICONTROL Query]** 資訊，請參閱 [本節](../../automating/using/query.md#enriching-data)。

在此範例中， [會使用自訂資](../../developing/using/data-model-concepts.md) 源：

* 擴充 **描述檔資源** ，以便新增欄位，以儲存每個描述檔的忠誠度點數。
* 已創 **建事務** 資源，並標識資料庫中配置檔案執行的所有採購。 系統會針對每筆交易儲存購買的日期、價格和產品。
* 已建 **立產品** 資源，並參考可供購買的產品。

目標是傳送電子郵件至至少已儲存一個交易的設定檔。 透過這封電子郵件，客戶將會收到上次交易的提醒，以及其所有交易的概述： 購買的產品數、總花費、提醒已累計的忠誠度點數總數。

工作流程如下：

![](assets/enrichment_example1.png)

1. 新增查 [詢活動](../../automating/using/query.md) ，可讓您定位已執行至少一項交易的設定檔。

   ![](assets/enrichment_example2.png)

   從查詢的標籤 **[!UICONTROL Additional data]** 中，定義要顯示在最終電子郵件中的不同資料：

   * 對應於忠誠點 **的** 「描述檔」維度的簡單欄位。 請參閱「 [Adding a simple field](../../automating/using/query.md#adding-a-simple-field) 」（添加簡單欄位）部分。
   * 根據事務處理收集進行兩個匯總： 購買的產品數量和花費的總金額。 您可以使用「計數」和「 **[!UICONTROL Data]** 總和」聚合，從聚合配置窗口的選 **項卡中添****** 加它們。 請參閱「添 [加聚合](../../automating/using/query.md#adding-an-aggregate) 」部分。
   * 傳回已生效之上次交易之花費金額、日期和產品的系列。

      若要這麼做，您必須從系列設定視窗的標籤中新增您要顯示的 **[!UICONTROL Data]** 不同欄位。

      要僅返回最近的事務處理，您必須為輸入&quot;1&quot;, **[!UICONTROL Number of lines to return]** 並在標籤中的系列的「日期」欄位上應用降序 ******[!UICONTROL Sort]** 排序。

      請參閱「新 [增系列](../../automating/using/query.md#adding-a-collection) 」 [和「排序其他資料](../../automating/using/query.md#sorting-additional-data) 」區段。
   ![](assets/enrichment_example4.png)

   如果要檢查活動的出站轉移是否正確傳輸資料，請首次啟動工作流（沒有活動）並開啟查詢的出站轉移。 **[!UICONTROL Email delivery]**

   ![](assets/enrichment_example5.png)

1. 新增電子 [郵件傳送](../../automating/using/email-delivery.md) 活動。 在電子郵件內容中，插入與查詢中計算的資料對應的個人化欄位。 您可以透過個人化欄位瀏 **[!UICONTROL Additional data (targetData)]** 覽器的連結找到它。

   ![](assets/enrichment_example3.png)

您的工作流程現在已可以執行。 查詢中定位的設定檔將會收到包含其交易所計算資料的個人化電子郵件。
