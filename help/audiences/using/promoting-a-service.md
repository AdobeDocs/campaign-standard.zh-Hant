---
title: 推廣服務
description: 使用Adobe Campaign通過專用登錄頁、電子郵件或直接在您的網站上推廣服務並吸引客戶。
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: Audiences
role: User
level: Intermediate
exl-id: c1f8770a-8b25-41db-aa52-828e181a563d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# 推廣服務{#promoting-a-service}

您可以通過多種方式為服務提供訂閱，並讓訪問者能夠管理其訂閱。

您可以使用「市場活動」通過以下方式促銷服務：

* [將服務訂閱或取消訂閱連結插入電子郵件](../../designing/using/links.md#inserting-a-link)。

* [在電子郵件中插入指向訂閱或取消訂閱登錄頁的連結](../../designing/using/links.md)。 在這種情況下，必須在相關登錄頁的屬性中直接引用該服務(請參見 [將登錄頁連結到服務](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service))。

   >[!NOTE]
   >
   >同時，還要給用戶取消訂閱的可能性。 為此，請插入服務 <b>取消訂閱連結</b> 在自動發送給新訂戶的確認電子郵件（在服務屬性中定義）中，以及將來的新聞稿電子郵件中。

* 在網站上提供訂閱或取消訂閱登錄頁。 允許您訪問登錄頁的URL必須指定相關服務等參數以及訪問它的配置檔案ID。 可以在登錄頁參數中定義此ID(請參見 [配置登錄頁](../../channels/using/configuring-landing-page.md))。
