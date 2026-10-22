---
title: 登錄頁面範本
description: 進一步瞭解登錄頁面範本。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 29d1badf-9ce3-470c-9bdc-169586d2e943
TQID: 'https://experienceleague.adobe.com/vJyIRO33IjK6o3--ekx-Iw9K-GcIZMViLz9wEr-kxY0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 93%
---
# 關於登陸頁面範本 {#landing-page-templates}

Campaign 隨附一組內建的登錄頁面範本：

* **[!UICONTROL Acquisition]**：這是登錄頁面的預設範本，可讓您擷取和更新 Campaign 資料庫中的資料。
* **[!UICONTROL Subscription]**：此範本應用於提供服務的訂閱。
* **[!UICONTROL Unsubscription]**：此範本可從寄送給訂閱者的電子郵件連結至服務，讓他們得以取消訂閱此服務。
* **[!UICONTROL Denylist]**：此範本應在輪廓不想再由 Campaign 聯絡時使用。 如需封鎖清單管理的詳細資訊，請參閱[關於Campaign中的加入和退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

這些範本在建立新登錄頁面時，預設會建議使用。

![](assets/lp_creation_1.png)

若要存取登錄頁面範本，請按一下左上角的 Adobe Campaign 標誌，然後選取 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**。

>[!NOTE]
>
>Adobe 建議複製內建範本，以建立您自己的範本。 有些參數只能在登錄頁面範本中設定，而無法直接在登錄頁面中修改。

建立範本時，建議將 **&#39;type&#39;** 屬性新增至標籤。 編輯器將處理此資訊，並幫助使用者在設定 Web 應用程式時將資料庫欄位連結到表單欄位。

範本中的 HTML 程式碼範例：

```
<input id="email" type="email" name="email"/>
```

「類型」屬性的正式清單可在下列位址取得：[https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)
