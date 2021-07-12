---
solution: Campaign Standard
product: campaign
title: 推廣服務
description: 使用Adobe Campaign來推廣服務，並透過專屬登陸頁面、電子郵件或直接在您的網站上與客戶互動。
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: 對象
role: User
level: Intermediate
exl-id: c1f8770a-8b25-41db-aa52-828e181a563d
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 3%

---

# 推廣服務{#promoting-a-service}

您可以透過數種方式提供服務的訂閱，並讓您的訪客能夠管理其訂閱。

您可以使用Campaign透過下列方式促銷服務：

* [在電子郵件中插入服務訂閱或取消訂閱連結](../../designing/using/links.md#inserting-a-link)。

* [在電子郵件中插入訂閱或取消訂閱登錄頁面的連結](../../designing/using/links.md)。在此情況下，服務必須在相關登錄頁面的屬性中直接參照（請參閱[將登錄頁面連結至服務](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)）。

   >[!NOTE]
   >
   >也必須讓訂閱者有取消訂閱的可能性。 要執行此操作，請在自動傳送給新訂閱者的確認電子郵件（在服務屬性中定義）以及未來電子報電子郵件中插入服務<b>取消訂閱連結</b>。

* 讓網站上可以使用訂閱或取消訂閱登錄頁面。 授予您登錄頁面存取權的URL必須指定參數（例如相關服務），以及存取該參數的設定檔ID。 此ID可在登錄頁面參數中定義（請參閱[設定登錄頁面](../../channels/using/configuring-landing-page.md)）。
