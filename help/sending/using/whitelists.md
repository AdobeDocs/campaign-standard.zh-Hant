---
title: Adobe Campaign standard中的白名單
description: 瞭解如何使用Adobe Campaign Standard最佳化白名單。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# 白名單{#whitelists}

主要的網際網路服務供應商(ISP)和Web郵件供應商管理識別的電子郵件傳送者的白名單。 Adobe Campaign可協助您取得最佳白名單認證的程式。

電子郵件白名單是電子郵件地址或域名的清單，電子郵件攔截程式將允許接收郵件。

白名單有兩種類型：
* 非商業性白名單
* 商業白名單

## 非商業性白名單 {#non-commercial-whitelists}

要獲得這些白名單的接受，發件人必須通過一系列基於基礎架構或其活動（傳送頻率、數量、投訴數）的技術驗證（其電子郵件伺服器不能是開放中繼，但應具有靜態IP）的測試。

如果發件人未遵守其中一項規則，則可能會從白名單中刪除該規則。 Adobe Campaign在其 **Adobe Campaign電子郵件傳遞功能套件中** ，針對非商業性白名單的認證程式提供隨附的專家諮詢服務。

## 商業白名單 {#commercial-whitelists}

商業白名單是以允許傳送者完全略過反垃圾郵件篩選器，或在進入系統時被指派遞增點數的系統為基礎。 這些付費白名單（CPT或按年繳費）由諸如「回訪路徑傳送者分數」之類的系統提供。

ISP可免費使用這些服務，而ISP的數量可能因白名單而異。 因此，發送者在通過提供傳送保證來發送其消息時可以更加自信。 某些白名單也提供開啟影像和啟用連結的功能。

出現在白名單中是任何電子郵件促銷活動不可否認的資產。 Adobe Campaign在其 **Adobe Campaign Email Deliverability套件中** ，提供商業白名單認證服務，例如CSA和回訪路徑寄件者分數。