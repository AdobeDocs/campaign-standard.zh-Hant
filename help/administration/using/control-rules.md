---
title: 控制規則
seo-title: 控制規則
description: 控制規則
seo-description: 瞭解如何使用控制規則加強訊息的品質檢查。
page-status-flag: 從未啓動
uuid: 33a1c90c-534e-4Fe1-982c-f4 e1858 d4 d2 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 使用typology規則
discoiquuid: 305adde-6424-4c6f-b11 b-1b-1e8 bdnow6 ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e5532c0769fe33016eaee994bdaae9c70a7eaa5

---


# Control rules{#control-rules}

控制規則可讓使用者在傳送訊息之前檢查其有效性和品質，例如字元顯示、SMS訊息大小、地址格式等。

Adobe Campaign提供的一組預設規則可確保標準控制項：

* **[!UICONTROL Check subject]** (電子郵件)：檢查主旨和傳送者地址不包含特殊字元，這些字元可能會導致某些郵件傳輸代理程式發生問題，並檢查訊息主體是否已完成。
* **[!UICONTROL Check URL labels]** (電子郵件)：檢查每個追蹤URL是否有標籤。
* **[!UICONTROL Check URLs]** (電子郵件)：檢查追蹤URL(「&amp;」字元的存在)。
* **[!UICONTROL Check proof size]** (所有通道)：產生錯誤訊息，如果校對目標人口超過100位收件者。
* **檢查取消訂閱連結** (電子郵件)：檢查每個內容中至少有一個取消訂閱(選擇退出) URL(HTML和文字)。
* **[!UICONTROL Check delivery size]** (所有通道)：檢查訊息大小。
* **[!UICONTROL Check social network sharing link]** (電子郵件)：檢查在內容中加入社交網路分享連結(VirallLinks)時，鏡像頁面的連結是否存在。
* **[!UICONTROL A/B Test]**：透過A/B測試擷取測試人口的測試人口。

您可以選擇規則將從傳送生命週期的某個階段套用的時機。Select the value to apply in the drop-down list from the **[!UICONTROL Phase]** field of the typology rule.

![](assets/typology_phase.png)

可能的值為：

* **在目標鎖定之時**

   控制規則可套用至此階段，因此不會在發生錯誤時執行個人化步驟。

* **定位後**

   如果您需要知道目標的音量以套用控制規則，請選取此階段。

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **在個人化之時**

   如果檢查核准訊息個人化，必須選取此階段。訊息個人化是在分析階段進行。

* **分析結束時**

   當檢查要求訊息個人化完成時，請選取這個階段。

>[!NOTE]
>
>基於安全理由，無法修改控制規則的內容。**[!UICONTROL Code]** 欄位為唯讀。
