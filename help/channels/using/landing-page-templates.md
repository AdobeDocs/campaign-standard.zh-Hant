---
title: 登錄頁面範本
description: 進一步瞭解登錄頁面範本。
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 94%

---


# 關於登錄頁面範本 {#landing-page-templates}

Campaign 隨附一組內建的登錄頁面範本：

* **[!UICONTROL Acquisition]**：這是登錄頁面的預設範本，可讓您擷取和更新 Campaign 資料庫中的資料。
* **[!UICONTROL Subscription]**：此範本應用於提供服務的訂閱。
* **[!UICONTROL Unsubscription]**：此範本可從寄送給訂閱者的電子郵件連結至服務，讓他們得以取消訂閱此服務。
* **[!UICONTROL Denylist]**：此範本應在設定檔不想再由 Campaign 聯絡時使用。For more about denylist management, refer to [About opt-in and opt-out in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

這些範本在建立新登錄頁面時，預設會建議使用。

![](assets/lp_creation_1.png)

若要存取登錄頁面範本，請按一下左上角的 Adobe Campaign 標誌，然後選取 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**。

>[!NOTE]
>
>Adobe 建議複製內建範本，以建立您自己的範本。有些參數只能在登錄頁面範本中設定，而無法直接在登錄頁面中修改。

建立範本時，建議將 **&#39;type&#39;** 屬性新增至標籤。編輯器將處理此資訊，並幫助使用者在設定 Web 應用程式時將資料庫欄位連結到表單欄位。

範本中的 HTML 程式碼範例：

```
<input id="email" type="email" name="email"/>
```

「類型」屬性的正式清單可在下列位址取得：[https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)