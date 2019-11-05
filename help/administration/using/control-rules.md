---
title: 控制規則
description: 瞭解如何使用控制規則來強化訊息的品質檢查。
page-status-flag: 從未激活
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 參考
topic-tags: 使用類型學規則
discoiquuid: 305cade-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 控制規則{#control-rules}

控制規則允許用戶在發送消息之前檢查消息的有效性和質量，如字元顯示、SMS消息大小、地址格式等。

Adobe Campaign中提供的一組預設規則可確保標準控制項：

* **[!UICONTROL Check subject]** （電子郵件）:檢查主題和發件人地址是否不包含某些郵件傳輸代理上可能出現問題的特殊字元，並檢查郵件主題是否已完成。
* **[!UICONTROL Check URL labels]** （電子郵件）:檢查每個追蹤URL是否有標籤。
* **[!UICONTROL Check URLs]** （電子郵件）:檢查追蹤URL（存在"&amp;"字元）。
* **[!UICONTROL Check proof size]** （所有頻道）:如果校對目標人口超過100個收件者，則會產生錯誤訊息。
* **勾選取消訂閱連結** （電子郵件）:檢查每個內容（HTML和文字）中是否至少有一個未訂閱（選擇退出）URL。
* **[!UICONTROL Check delivery size]** （所有頻道）:檢查消息的大小。
* **[!UICONTROL Check social network sharing link]** （電子郵件）:在內容中包含社交網路共用連結(ViralLinks)時，會檢查鏡像頁面的連結是否存在。
* **[!UICONTROL A/B Test]**:透過A/B測試擷取要傳送的測試人口族群。

您可以從交貨生命週期的其中一個階段中選擇應用規則的時間。 從排版規則欄位中，選取要套用在下拉式清 **[!UICONTROL Phase]** 單中的值。

![](assets/typology_phase.png)

可能的值包括：

* **定位開始時**

   該控制規則可在此階段應用，以便在發生錯誤時不執行個人化步驟。

* **定位後**

   如果您需要知道目標的卷才能應用控制規則，請選擇此階段。

   例如，「檢查 **校樣大小** 」控制規則適用於定位階段後：如果有太多的證明收件者，此規則會防止準備訊息個人化。

* **個人化開始時**

   如果檢查涉及批准消息個性化，則必須選擇此階段。 在分析階段中執行消息個性化。

* **分析結束時**

   當檢查要求消息個性化完成時，請選擇此階段。

>[!NOTE]
>
>出於安全原因，無法修改控制規則的內容。 該 **[!UICONTROL Code]** 欄位為只讀。
