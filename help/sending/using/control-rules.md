---
solution: Campaign Standard
product: campaign
title: 控制規則
description: 了解如何使用控制規則來強化訊息的品質檢查。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: 態樣規則
role: Business Practitioner
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
source-git-commit: c41d51538b8a8376a034c7d2db77b66b21256fd8
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 4%

---

# 控制規則 {#control-rules}

控制規則可讓您在傳送訊息之前檢查訊息的有效性和品質，例如字元顯示、SMS訊息大小、位址格式等。

>[!NOTE]
>
>出於安全原因，控制規則為只讀，無法修改。

## 預設控制規則 {#default-control-rules}

一組預設規則可確保標準控制項。 下表提供這些規則的相關資訊，以及它們的相關通道和[執行階段](#control-rules-execution-phases)。

| 標籤 | 通道 | 執行階段 | 說明 |
|---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | 電子郵件 | 個人化開始時 | 透過A/B測試擷取傳送的測試母體。 |
| **[!UICONTROL Check delivery size]** | 全部 | 定位後 | 檢查訊息的大小。 |
| **[!UICONTROL Check email content is not empty]** | 電子郵件 | 定位後 | 如果訊息的內容為空，則產生錯誤。 |
| **[!UICONTROL Check In-App content for broadcast template]** | 應用程式內 | 開始個人化時 | 檢查廣播範本的應用程式內內容/觸發器是否非空白。 |
| **[!UICONTROL Check In-App content for profile template]** | 應用程式內 | 個人化開始時 | 檢查設定檔範本的應用程式內內容/觸發器是否非空白。 |
| **[!UICONTROL Check In-App content for subscriber template]** | 應用程式內 | 個人化開始時 | 檢查訂閱者範本的應用程式內內容/觸發器是否非空白。 |
| **[!UICONTROL Check proof size]** | 全部 | 定位後 | 如果校樣目標母體超過100個收件者，則產生錯誤訊息。 |
| **[!UICONTROL Check social network sharing link]** | 電子郵件 | 個人化開始時 | 在內容中加入社交網路共用連結(ViralLinks)時，會檢查鏡像頁面的連結是否存在。 |
| **[!UICONTROL Check subject]** | 電子郵件 | 個人化開始時 | 檢查主題和發件人地址是否不包含可能導致某些郵件傳輸代理出現問題的特殊字元，並檢查郵件主題是否已完成。 |
| **[!UICONTROL Check unsubscription link]** | 電子郵件 | 個人化開始時 | 檢查每個內容（HTML和文字）中是否至少有一個取消訂閱（選擇退出）URL。 |
| **[!UICONTROL Check URL labels]** | 電子郵件 | 個人化開始時 | 檢查每個追蹤URL是否都有標籤。 |
| **[!UICONTROL Check URLs]** | 電子郵件 | 個人化開始時 | 檢查追蹤URL（是否有&quot;&amp;&quot;字元）。 |

## 控制規則執行階段 {#control-rules-execution-phases}

控制規則可在傳送生命週期的不同階段套用：

* **定位開始時**:可在此階段套用控制規則，這樣在發生錯誤時就不會執行個人化步驟。

* **鎖定目標後**:在目標定位後執行可讓您知道目標的卷，以便套用控制規則。

   例如，**檢查校樣大小**&#x200B;控制規則會套用在目標定位階段之後：如果有太多校樣收件者，此規則會防止準備訊息個人化。

* **個人化開始時**:當檢查與訊息個人化核准相關時套用。在分析階段期間會執行訊息個人化。

* **分析結束時**:當檢查需要完成訊息個人化時。
