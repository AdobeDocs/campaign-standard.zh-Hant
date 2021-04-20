---
solution: Campaign Standard
product: campaign
title: 論Adobe Campaign Standard的傳遞能力
description: 瞭解有關遞送能力的概念和最佳實務，以及Adobe Campaign Standard提供的工具，以最佳化傳送遞送。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 6%

---


# 什麼是傳遞能力{#about-deliverability}

傳遞能力可讓您測量促銷活動在到達收件者收件匣時是否成功，而不會反彈或標示為垃圾訊息。 [瞭解傳遞能力為何重要](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters)。

更準確地說，電子郵件傳遞能力是指一組特性，這些特性決定了郵件通過個人電子郵件地址在短時間內到達其目的地的能力，並且在內容和格式方面具有預期的質量。<!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

如需深入瞭解何謂可交付性，並進一步瞭解關鍵可交付性術語、概念和方法，請參閱[Adobe可交付性最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html)。

## 如何提高傳遞能力{#deliverability-key-points}

傳遞能力問題通常與網際網路服務提供商和郵件伺服器管理員實施的針對垃圾郵件的保護措施有關。

* 有關如何設計成功電子郵件行銷活動的一般建議，請參閱[傳遞性策略和定義](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html)。

* 有關如何最佳化您Adobe Campaign電子郵件傳遞能力的更多特定建議，我們建議使用本節所列的最佳實務。

>[!NOTE]
>
>由於ISP必須不斷開發新的精密過濾技術，以保護客戶免受垃圾郵件發送者的侵擾，因此電子郵件傳遞的特點是標準和規則不斷變化。 請務必參考定期更新的[Adobe交付能力最佳實踐指南。](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html)

### 可交付性率

傳遞能力比率是點擊收件者收件箱的訊息數，與傳送的訊息數相比。 為了改善傳遞能力，您可能會努力提高此比率。

在Adobe Campaign，可交付率取決於眾多因素，特別是：

* 正確配置實例：請洽詢您的Adobe代表以取得協助。
* 合法的網路配置：請參閱[本節](../../sending/using/optimize-delivery.md#network-config)和[域設定和策略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy)。
* 您的IP位址信譽：請參閱[IP策略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy)。
* 目標地址的質量：請參閱[隔離管理](../../sending/using/optimize-delivery.md#quarantine-management)。
* 低[投訴](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html)和[硬反彈](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)率。
* 您的訊息內容：請參閱[控制電子郵件內容](../../sending/using/control-email-content.md)。
* 消息驗證(SPF、DKIM、DMARC):請參閱[本節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication)。
* 發件人信譽：要瞭解主要ISP如何評估發件人信譽，請參閱[本節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html)。

## 促銷活動傳遞性工具{#deliverability-tools}

Adobe Campaign提供多種工具來追蹤並改善您平台的傳遞效能。 本頁也強調您在使用Campaign時應牢記的最佳化傳遞能力的主要原則。

### 仔細建構您的訊息

在設定、設計和測試訊息時，請務必遵循下列章節中提及的最佳實務。 運用Adobe Campaign提供的所有功能，將可協助您改善傳遞能力。

* [傳遞最佳實務](../../sending/using/delivery-best-practices.md)
* [控管電子郵件內容](../../sending/using/control-email-content.md)
* [預覽訊息](../../sending/using/previewing-messages.md)
* [傳送校樣](../../sending/using/sending-proofs.md)

### 透過雙重選擇加入{#double-opt-in}來驗證同意

為避免將消息發送到無效地址、限制不當通信並改善發件人信譽，Adobe建議實施雙重選擇加入機制。 這可讓您確保收件者有意訂閱。

如需詳細資訊，請參閱[關於促銷活動中的選擇加入和選擇退出。](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

有關從客戶收集資料時的最佳實踐的詳細資訊，請參閱[Adobe交付能力最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene)。

### 利用隔離管理

Adobe Campaign管理的清單會收集垃圾郵件投訴、硬性回報和軟性回報，而這些回報會一貫發生。

為了保護您的傳送能力，該清單上地址的收件者預設會從所有未來傳送中排除，因為傳送給這些連絡人可能會損害您的傳送信譽。

如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。因此，隔離可讓您避免被這些提供者添加到拒絕清單。

如需詳細資訊，請參閱下列章節：

* [瞭解傳送故障](../../sending/using/understanding-delivery-failures.md)
* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [隔離與拒絕清單](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### 使用監控和報告工具

使用Adobe Campaign提供的功能監控您的傳遞能力。

Adobe Campaign可讓您透過一組內建的即時指標，來檢查傳送的成效。 <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->您也可以建立可完全自訂的即時報表，以改善對傳送的洞察力。

如需詳細資訊，請參閱下列章節：

* [監視傳遞能力](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [發生故障時收到警報](../../sending/using/receiving-alerts-when-failures-happen.md)
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
