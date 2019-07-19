---
title: 著陸頁面限制
seo-title: 著陸頁面限制
description: 著陸頁面限制
seo-description: 探索促銷活動登陸頁面及其生命週期。
page-status-flag: 從未啓動
uuid: b316fb47-7d98-46fa-ab4 f-67ff50 de8095
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 登陸頁面
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152 e14286
context-tags: landingPage，精靈；landingPage，概觀；LandingPage，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 578993ccdf8f31c527c62a9d7fc84daa1c61e94a

---


# Landing page limitations{#landing-page-limitations}

**寫入和更新資料**

* Landing pages are limited to **[!UICONTROL Profile]** and **[!UICONTROL Subscription]** resources only. Record can be saved and updated from **[!UICONTROL Profile]** and a subscription/unsubscription to a **[!UICONTROL Service]**.
To learn more on resources configuration, see [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!CAUTION]
>
> A landing page cannot display or update data from any other resource than **[!UICONTROL Profile]** and **[!UICONTROL Subscription]**.

**預先載入**

* 著陸頁面無法自動顯示記錄清單，它無法列出已訂閱的設定檔服務。For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* 具有預先填入表單的著陸頁面(資料已預先載入頁面)只能從Adobe Campaign電子郵件存取。無法從網站頁面存取此表單。

**調解**

* 協調行為如下：找到相符項目後，調解程序就會停止。這表示協調只能在一個描述檔記錄上完成，而不能在有重復的情況下進行多次記錄。

例如，您想要將下列贏取著陸頁面傳送至個人檔案，以便使用個人檔案的行動電話號碼更新促銷活動資料庫。

![](assets/landing_page_limitation_1.png)

如果您的其中一個設定檔填入了包含新資訊的登陸頁面，但已有重復的描述檔，則會更新具有最早建立日期的相符描述檔，因為設定檔只會依其建立日期排列優先順序。

這裡只有第一個描述檔已更新，因為它是最舊的項目。

![](assets/landing_page_limitation_2.png)

**測試登陸頁面**

* 著陸頁面僅適用於描述檔，而非測試設定檔，也就是說，著陸頁面無法作為電子郵件校樣的一部分進行測試。
