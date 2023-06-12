---
title: 關於Adobe Campaign Standard中的傳遞能力
description: 瞭解與傳遞能力相關的概念和最佳實務，以及Adobe Campaign Standard提供的用於最佳化傳送傳送內容的工具。
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

可遞送性可讓您測量行銷活動在到達收件者收件匣時不會退回或標示為垃圾訊息的成功程度。 [瞭解傳遞能力重要的原因](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters).

更準確地說，電子郵件傳遞能力指一組特性，這些特性決定訊息在短時間內透過個人電子郵件地址到達其目的地的能力，以及內容和格式的預期品質。 <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

如需深入瞭解什麼是傳遞能力，並深入瞭解傳遞能力的重要術語、概念和方法，請參閱 [Adobe傳遞性最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant).

## 如何改善傳遞能力 {#deliverability-key-points}

傳遞能力問題通常與網際網路服務提供者和郵件伺服器管理員所實施的防止垃圾郵件的措施有關。

* 如需如何設計成功電子郵件行銷活動的一般建議，請參閱 [傳遞能力策略和定義](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html).

* 如需如何最佳化Adobe Campaign電子郵件傳遞能力的更具體建議，建議您使用本節所列的最佳實務。

>[!NOTE]
>
>由於ISP必須持續開發新的複雜篩選技術，以保護客戶免受垃圾郵件傳送者的傷害，因此電子郵件傳遞能力的特點是標準和規則不斷變化。 請務必參閱 [Adobe傳遞性最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant) 並定期更新。

### 傳遞率

傳遞率是相較於已傳遞的訊息數，點選收件者收件匣的訊息數。 若要改善傳遞能力，您可以致力於提高此比率。

使用Adobe Campaign時，傳遞率取決於許多因素，特別是：

* 正確設定您的執行個體：請聯絡您的Adobe代表以尋求協助。
* 合法的網路設定：請參閱 [本節](../../sending/using/optimize-delivery.md#network-config) 和 [網域設定和策略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy).
* 您的IP位址信譽：請參閱 [IP策略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy).
* 目標地址的品質：請參閱 [隔離管理](../../sending/using/optimize-delivery.md#quarantine-management).
* 低 [申訴](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) 和 [硬跳出](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces) 費率。
* 您的訊息內容：請參閱 [控制電子郵件內容](../../sending/using/control-email-content.md).
* 訊息驗證(SPF、DKIM、DMARC)：請參閱 [本節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).
* 寄件者信譽：若要瞭解主要ISP如何評估寄件者信譽，請參閱 [本節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html).

## Campaign傳遞工具 {#deliverability-tools}

Adobe Campaign提供許多工具，用於追蹤及改善平台的可遞送性效能。 本頁也強調使用Campaign時，最佳化傳遞能力時應牢記的主要原則。

### 謹慎建立您的訊息

設定、設計和測試訊息時，請務必遵循下列區段中提到的最佳實務。 運用Adobe Campaign提供的所有功能，協助您改善傳遞能力。

* [關於傳遞的最佳實務](../../sending/using/delivery-best-practices.md)
* [控制電子郵件內容](../../sending/using/control-email-content.md)
* [預覽訊息](../../sending/using/previewing-messages.md)
* [傳送校樣](../../sending/using/sending-proofs.md)

### 透過雙重選擇加入驗證同意 {#double-opt-in}

為避免將訊息傳送至無效地址、限制不當通訊並改善寄件者信譽，Adobe建議實作雙重選擇加入機制。 這可讓您確保收件者有意訂閱。

如需詳細資訊，請參閱 [關於Campaign中的加入和退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

如需從客戶收集資料時最佳實務的詳細資訊，請參閱 [Adobe傳遞性最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene).

### 運用隔離管理

Adobe Campaign管理會收集垃圾郵件投訴、硬跳出和一致發生的軟跳出的清單。

為了保護您的傳遞能力，該清單中地址在未來的所有傳遞中預設都會排除收件者，因為傳送給這些連絡人可能會損害您的傳送信譽。

如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。因此，隔離可讓您避免被這些提供者新增至封鎖清單。

如需詳細資訊，請參閱下列章節：

* [瞭解傳遞故障](../../sending/using/understanding-delivery-failures.md)
* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [隔離與封鎖清單](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### 使用監控與報告工具

使用Adobe Campaign提供的功能來監控您的傳送能力。

Adobe Campaign可讓您透過一組內建即時指標檢查傳遞的執行方式。 <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->您也可以建立完全可自訂的即時報表，以提升對傳送內容的深入分析。

如需詳細資訊，請參閱下列章節：

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
