---
title: 關於Adobe Campaign Standard的可交付性
description: 瞭解與交付能力相關的概念和最佳做法以及Adobe Campaign Standard為優化交付而提供的工具。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 7%

---

# 什麼是傳遞性{#about-deliverability}

可遞送性允許測量您的活動在到達收件人收件箱時是否成功，而不會彈跳或標籤為垃圾郵件。 [瞭解為什麼交付性很重要](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters)。

更準確地說，電子郵件傳送能力是指一組特徵，這些特徵決定了郵件在短時間內通過個人電子郵件地址到達其目的地的能力，並且在內容和格式方面具有預期的質量。 <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

要深入瞭解什麼是可交付性，並瞭解關鍵可交付性術語、概念和方法的更多資訊，請參閱 [Adobe交付能力最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant)。

## 如何提高可交付性 {#deliverability-key-points}

傳遞性問題通常與網際網路服務提供商和郵件伺服器管理員實施的針對垃圾郵件的保護措施有關。

* 有關如何設計成功的電子郵件營銷活動的一般建議，請參閱 [可交付性策略和定義](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html)。

* 有關如何優化Adobe Campaign電子郵件的可傳送性的更具體建議，我們建議使用本節中列出的最佳做法。

>[!NOTE]
>
>由於ISP必須不斷開發新的複雜過濾技術來保護其客戶免受垃圾郵件發送者的侵害，因此電子郵件發送能力的特點是標準和規則不斷變化。 確保您引用 [Adobe交付能力最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant) 定期更新。

### 交付率

Deliverability rate是與已傳送的郵件數相比，命中收件人收件箱的郵件數。 為了提高交付能力，您可以努力提高此速率。

在Adobe Campaign，供應率取決於諸多因素，特別是：

* 正確配置實例：請與Adobe代表聯繫以獲得幫助。
* 合法網路配置：見 [此部分](../../sending/using/optimize-delivery.md#network-config) 和 [域設定和策略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy)。
* 您的IP地址信譽：見 [IP策略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy)。
* 目標地址的質量：見 [隔離管理](../../sending/using/optimize-delivery.md#quarantine-management)。
* 低 [投訴](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) 和 [硬彈](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces) 利率。
* 您的消息內容：見 [控制電子郵件內容](../../sending/using/control-email-content.md)。
* 消息驗證(SPF、DKIM、DMARC):見 [此部分](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication)。
* 發件人信譽：要瞭解主要ISP如何評估發件人信譽，請參閱 [此部分](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html)。

## 市場活動交付工具 {#deliverability-tools}

Adobe Campaign提供了多種工具來跟蹤和改進您的平台的可交付性效能。 此頁還重點介紹了在使用市場活動時優化交付能力時應牢記的主要原則。

### 小心構建您的消息

在配置、設計和測試消息時，請確保遵循下面各節中提到的最佳做法。 利用Adobe Campaign提供的所有功能，可幫助您提高交付能力。

* [關於傳遞的最佳實務](../../sending/using/delivery-best-practices.md)
* [控制電子郵件內容](../../sending/using/control-email-content.md)
* [預覽訊息](../../sending/using/previewing-messages.md)
* [傳送校樣](../../sending/using/sending-proofs.md)

### 通過雙重選擇加入驗證同意 {#double-opt-in}

為避免向無效地址發送消息、限制不當通信並改善發送者信譽，Adobe建議實施雙重選擇加入機制。 這使您能夠確保您的收件人有意地訂閱。

有關此的詳細資訊，請參閱 [關於選擇加入和選擇退出活動](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

有關從客戶收集資料時的最佳做法的詳細資訊，請參閱 [Adobe交付能力最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene)。

### 利用隔離管理

Adobe Campaign管理一個收集垃圾郵件投訴、硬回報和軟回報的清單，這些內容始終如一地發生。

為了保護您的交貨能力，預設情況下，其地址位於該清單中的收件人將排除在所有將來的交貨之外，因為發送到這些聯繫人可能會損害您的發送信譽。

如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。因此，隔離允許您避免被這些提供程式添加到denylist中。

有關詳細資訊，請參閱以下各節：

* [瞭解傳遞故障](../../sending/using/understanding-delivery-failures.md)
* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [隔離與密文清單](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### 使用監控和報告工具

使用Adobe Campaign提供的功能監控您的交付能力。

Adobe Campaign允許您通過一組內置即時指示器來檢查交貨情況。 <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->您還可以構建完全可定製的即時報告，以便更好地瞭解您的交貨情況。

有關詳細資訊，請參閱以下各節：

* [監視傳遞能力](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [發生故障時接收警示](../../sending/using/receiving-alerts-when-failures-happen.md)
* [動態報告](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
