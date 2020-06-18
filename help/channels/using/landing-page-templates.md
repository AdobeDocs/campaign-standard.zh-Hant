---
title: 著陸頁面範本
description: 進一步瞭解登陸頁面範本。
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
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# 關於登錄頁面範本 {#landing-page-templates}

Campaign隨附一組內建的登陸頁面範本：

* **[!UICONTROL Acquisition]**: 這是著陸頁面的預設範本，可讓您擷取和更新促銷活動資料庫中的資料。
* **[!UICONTROL Subscription]**: 此範本應用於提供服務的訂閱。
* **[!UICONTROL Unsubscription]**: 此範本可從寄送給訂閱者的電子郵件連結至服務，以允許他們取消訂閱此服務。
* **[!UICONTROL Block list]**: 此範本應在描述檔不想再由促銷活動聯絡時使用。 如需區塊清單管理的詳細資訊，請 [參閱關於促銷活動中的選擇加入和選擇退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

這些範本在建立新登陸頁面時，預設會建議使用。

![](assets/lp_creation_1.png)

若要存取著陸頁面範本，請按一下左上角的Adobe Campaign標誌，然後選取 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**。

>[!NOTE]
>
>Adobe建議複製內建範本，以建立您自己的範本。 有些參數只能在著陸頁面範本中設定，而無法直接在著陸頁面中修改。

建立範本時，建議將&#39;type&#39; **attribute新增至** tags。 編輯器將處理此資訊，並幫助用戶在配置Web應用程式時將資料庫欄位連結到表單欄位。

範本中的HTML程式碼範例：

```
<input id="email" type="email" name="email"/>
```

「類型」屬性的正式清單可在下列位址取得： [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)