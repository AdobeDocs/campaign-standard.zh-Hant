---
title: 控制規則
description: 瞭解如何使用控制規則加強訊息的品質檢查。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 14%

---

# 控制規則 {#control-rules}

控制規則可讓您在傳送訊息之前檢查訊息的有效性和品質，例如字元顯示、SMS訊息大小、位址格式等。

>[!NOTE]
>
>基於安全理由，控制規則是唯讀的，無法修改。

## 預設控制規則 {#default-control-rules}

一組預設規則可確保標準控制項。 下表提供這些規則的相關資訊，以及其相關的管道和 [執行階段](#control-rules-execution-phases).

| 標籤 | 管道 | 執行階段 | 說明 |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | 電子郵件 | 在個人化開始時 | 使用A/B測試為傳遞擷取測試母體。 |
| **[!UICONTROL Check delivery size]** | 全部 | 鎖定之後 | 檢查訊息的大小。 |
| **[!UICONTROL Check email content is not empty]** | 電子郵件 | 鎖定之後 | 如果訊息的內容為空白，則產生錯誤。 |
| **[!UICONTROL Check In-App content for broadcast template]** | 應用程式內 | 開始時，個人化 | 檢查廣播範本的應用程式內內容/觸發程式是否非空白。 |
| **[!UICONTROL Check In-App content for profile template]** | 應用程式內 | 在個人化開始時 | 檢查設定檔範本的應用程式內內容/觸發器是否非空白。 |
| **[!UICONTROL Check In-App content for subscriber template]** | 應用程式內 | 在個人化開始時 | 檢查訂閱者範本的應用程式內內容/觸發器是否非空白。 |
| **[!UICONTROL Check proof size]** | 全部 | 鎖定之後 | 如果校訂目標母體超過100個收件者，則產生錯誤訊息。 |
| **[!UICONTROL Check social network sharing link]** | 電子郵件 | 在個人化開始時 | 在內容中包含社交網路共用連結（病毒連結）時，檢查是否存在映象頁面的連結。 |
| **[!UICONTROL Check subject]** | 電子郵件 | 在個人化開始時 | 檢查主旨和寄件者地址是否不包含特殊字元，這些字元可能會對某些郵件傳輸代理程式造成問題，並檢查郵件主旨是否已完成。 |
| **[!UICONTROL Check unsubscription link]** | 電子郵件 | 在個人化開始時 | 檢查每個內容(HTML和文字)中是否存在至少一個取消訂閱（選擇退出） URL。 |
| **[!UICONTROL Check URL labels]** | 電子郵件 | 在個人化開始時 | 檢查每個追蹤URL是否都有標籤。 |
| **[!UICONTROL Check URLs]** | 電子郵件 | 在個人化開始時 | 檢查追蹤URL （「&amp;」字元是否存在）。 |

## 控制規則執行階段 {#control-rules-execution-phases}

控制規則可在傳遞生命週期的不同階段套用：

* **在鎖定開始時**：控制規則可在此階段套用，以便在發生錯誤時不會執行個人化步驟。

* **目標定位後**：在鎖定目標後執行可讓您知道目標的磁碟區，以套用控制規則。

  例如， **檢查校訂大小** 控制規則會在目標定位階段後套用：如果校樣收件者過多，此規則會防止準備訊息個人化。

* **在個人化開始時**：當檢查與訊息個人化核准相關時套用。 訊息個人化會在分析階段中執行。

* **在分析結束時**：檢查需要完成訊息個人化時。
