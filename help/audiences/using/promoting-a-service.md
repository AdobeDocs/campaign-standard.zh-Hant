---
title: 推廣服務
description: 使用Adobe Campaign來推廣服務，並透過專用的登陸頁面、電子郵件或直接在您的網站上與您的客戶互動。
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

您可以透過數種方式提供服務的訂閱，並讓訪客能夠管理其訂閱。

您可以使用Campaign透過以下方式促銷服務：

* [將服務訂閱或取消訂閱連結插入電子郵件](../../designing/using/links.md#inserting-a-link)。

* [在電子郵件中插入訂閱或取消訂閱登入頁面的連結](../../designing/using/links.md)。 在此情況下，必須在相關登入頁面的屬性中直接參考服務（請參閱[將登入頁面連結至服務](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)）。

  >[!NOTE]
  >
  >讓訂閱者有機會取消訂閱也很重要。 若要這麼做，請將服務<b>取消訂閱連結</b>插入自動傳送給新訂閱者的確認電子郵件（定義在服務屬性中）中，以及未來的電子報電子郵件中。

* 讓訂閱或取消訂閱登入頁面可在網站上使用。 授予您登陸頁面存取權的URL必須指定引數（例如關聯的服務），以及存取該服務的設定檔ID。 此ID可以在登入頁面引數中定義（請參閱[設定登入頁面](../../channels/using/configuring-landing-page.md)）。
