---
title: 控制規則
description: 瞭解如何使用控制規則加強郵件的質量檢查。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 14%

---

# 控制規則 {#control-rules}

控制規則允許您在發送消息之前檢查消息的有效性和質量，如字元顯示、SMS消息大小、地址格式等。

>[!NOTE]
>
>出於安全原因，控制規則為只讀，無法修改。

## 預設控制規則 {#default-control-rules}

一組預設規則可確保標準控制項。 下表提供了有關這些規則及其相關渠道和 [執行階段](#control-rules-execution-phases)。

| 標籤 | 通道 | 執行階段 | 說明 |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | 電子郵件 | 在個人化開始時 | 提取test群體，以使用A/Btest進行遞送。 |
| **[!UICONTROL Check delivery size]** | 全部 | 鎖定之後 | 檢查消息的大小。 |
| **[!UICONTROL Check email content is not empty]** | 電子郵件 | 鎖定之後 | 如果消息的內容為空，則生成錯誤。 |
| **[!UICONTROL Check In-App content for broadcast template]** | 應用程式內 | 開始個性化 | 檢查In-App內容/觸發器是否為廣播模板的空。 |
| **[!UICONTROL Check In-App content for profile template]** | 應用程式內 | 在個人化開始時 | 檢查配置檔案模板的In-App內容/觸發器是否不為空。 |
| **[!UICONTROL Check In-App content for subscriber template]** | 應用程式內 | 在個人化開始時 | 檢查訂閱者模板的In-App內容/觸發器是否不為空。 |
| **[!UICONTROL Check proof size]** | 全部 | 鎖定之後 | 如果證明目標總數超過100個收件人，則生成錯誤消息。 |
| **[!UICONTROL Check social network sharing link]** | 電子郵件 | 在個人化開始時 | 在內容中包括社交網路共用連結(ViralLinks)時，檢查指向鏡像頁面的連結是否存在。 |
| **[!UICONTROL Check subject]** | 電子郵件 | 在個人化開始時 | 檢查主題和發件人地址是否不包含可能導致某些郵件轉移代理出現問題的特殊字元，並檢查郵件主題是否已完成。 |
| **[!UICONTROL Check unsubscription link]** | 電子郵件 | 在個人化開始時 | 檢查每個內容(HTML和文本)中是否存在至少一個未訂閱（選擇退出）URL。 |
| **[!UICONTROL Check URL labels]** | 電子郵件 | 在個人化開始時 | 檢查每個跟蹤URL是否都有標籤。 |
| **[!UICONTROL Check URLs]** | 電子郵件 | 在個人化開始時 | 檢查跟蹤URL（「&amp;」字元的存在）。 |

## 控制規則執行階段 {#control-rules-execution-phases}

控制規則可在交貨生命週期的不同階段應用：

* **在瞄準**:該控制規則可在該階段應用，使得在發生錯誤時不執行個性化步驟。

* **目標後**:目標後執行允許您瞭解目標的卷以應用控制規則。

   例如， **校驗尺寸** 控制規則在目標階段後應用：如果證明收件人過多，則此規則將阻止準備郵件個性化。

* **個性化開始時**:當支票與郵件個性化審批相關時應用。 在分析階段執行消息個性化。

* **在分析結束時**:當檢查要求完成消息個性化時。
