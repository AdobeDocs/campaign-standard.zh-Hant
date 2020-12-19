---
solution: Campaign Standard
product: campaign
title: 控制規則
description: 瞭解如何使用控制規則來強化訊息的品質檢查。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 3%

---


# 控制規則 {#control-rules}

控制規則可讓您在傳送訊息之前檢查訊息的有效性和品質，例如字元顯示、SMS訊息大小、位址格式等。

>[!NOTE]
>
>出於安全原因，控制規則是唯讀的，無法修改。

## 預設控制規則{#default-control-rules}

一組預設規則可確保標準控制項。 下表提供這些規則的相關資訊，以及其相關頻道和[執行階段](#control-rules-execution-phases)。

| 標籤 | 通道 | 執行階段 | 說明 |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | 電子郵件 | 個人化開始時 | 擷取測試人口族群，以進行A/B測試傳送。 |
| **[!UICONTROL Check delivery size]** | 全部 | 定位後 | 檢查消息的大小。 |
| **[!UICONTROL Check email content is not empty]** | 電子郵件 | 定位後 | 如果消息的內容為空，則生成錯誤。 |
| **[!UICONTROL Check In-App content for broadcast template]** | 應用程式內 | 開始個人化時 | 檢查廣播範本的應用程式內容／觸發器是否不為空。 |
| **[!UICONTROL Check In-App content for profile template]** | 應用程式內 | 個人化開始時 | 檢查描述檔範本的應用程式內容／觸發器是否不為空。 |
| **[!UICONTROL Check In-App content for subscriber template]** | 應用程式內 | 個人化開始時 | 檢查訂閱者範本的應用程式內容／觸發器是否不為空。 |
| **[!UICONTROL Check proof size]** | 全部 | 定位後 | 如果校對目標人口超過100個收件者，則產生錯誤訊息。 |
| **[!UICONTROL Check social network sharing link]** | 電子郵件 | 個人化開始時 | 在內容中包含社交網路共用連結(ViralLinks)時，會檢查鏡像頁面的連結是否存在。 |
| **[!UICONTROL Check subject]** | 電子郵件 | 個人化開始時 | 檢查主題和發件人地址是否不包含某些郵件傳輸代理上可能出現問題的特殊字元，並檢查郵件主題是否已完成。 |
| **[!UICONTROL Check unsubscription link]** | 電子郵件 | 個人化開始時 | 檢查每個內容（HTML和文字）中是否至少有一個未訂閱（選擇退出）URL。 |
| **[!UICONTROL Check URL labels]** | 電子郵件 | 個人化開始時 | 檢查每個追蹤URL是否有標籤。 |
| **[!UICONTROL Check URLs]** | 電子郵件 | 個人化開始時 | 檢查追蹤URL（存在&quot;&amp;&quot;字元）。 |

## 控制規則執行階段{#control-rules-execution-phases}

控制規則可套用至交貨生命週期的不同階段：

* **在定位開始時**:該控制規則可在此階段應用，以便在發生錯誤時不執行個人化步驟。

* **定位後**:定位後執行可讓您瞭解定位的卷，以套用控制規則。

   例如，**檢查校樣大小**&#x200B;控制規則會套用在定位階段之後：如果有太多的證明收件者，此規則會防止準備訊息個人化。

* **個人化開始時**:當核取與訊息個人化核准相關時套用。在分析階段中執行消息個性化。

* **在分析結束時**:當檢查需要完成訊息個人化時。
