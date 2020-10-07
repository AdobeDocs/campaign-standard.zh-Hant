---
title: 關於Adobe Campaign Standard中的傳遞能力
description: 瞭解與傳遞能力相關的概念和最佳實務，以及Adobe Campaign Standard提供的工具，以最佳化傳送您的傳遞。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 關於傳遞能力{#about-deliverability}

傳遞能力可讓您測量促銷活動在到達收件者收件匣時是否成功，而不會反彈或標示為垃圾訊息。

可交付率取決於眾多因素，特別是：

* 正確配置實例
* 您的IP位址信譽
* 目標地址的質量
* 低投訴與高反彈率
* 您的訊息內容
* 消息驗證(SPF、DKIM、DMARC)
* 發件人信譽

## 需要檢查的關鍵點 {#deliverability-key-points}

若要最佳化Adobe Campaign電子郵件的傳遞能力，我們建議使用下列最佳實務。 傳遞能力問題通常與網際網路服務提供商和郵件伺服器管理員實施的針對垃圾郵件的保護措施有關。

電子郵件傳遞能力是指一組特性，這些特性決定了郵件在短時間內通過個人電子郵件地址到達其目的地的能力，並且在內容和格式方面具有預期的質量。 這些特徵可分為四大類：資料品質、訊息和內容、傳送基礎架構和聲譽。 它們共同構成了成功的電子郵件傳遞能力計畫的基礎。

傳遞率是已傳送成功傳送給收件人的電子郵件數。
以下列出要檢查的要點，以確保良好的交付能力。

## 傳遞性工具 {#deliverability-tools}

首先，請先參閱Campaign Standard隨附之傳遞性工具相關檔案：
* [提供最佳實務](../../sending/using/delivery-best-practices.md)
* [個人化傳送者名稱](../../designing/using/personalization.md#personalizing-the-sender)
* [測試電子郵件的主旨行](../../sending/using/testing-subject-line-email.md)
* [最佳化傳送時間](../../sending/using/optimizing-the-sending-time.md)
* [預覽訊息](../../sending/using/previewing-messages.md)
* [電子郵件呈現](../../sending/using/email-rendering.md)
* [監控傳送](../../sending/using/monitoring-a-delivery.md)
* [發生故障時收到警報](../../sending/using/receiving-alerts-when-failures-happen.md)
* [瞭解傳送故障](../../sending/using/understanding-delivery-failures.md)
* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [隔離與拒絕清單](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)
* [動態報表](../../reporting/using/about-dynamic-reports.md)

## 檢查網路配置 {#network-configuration}

垃圾郵件發送者試圖隱藏其真實身份，結果導致其伺服器難以識別。 不嘗試隱藏伺服器身份的合法網路配置對於大量發送電子郵件至關重要。

## 傳送至有效位址 {#valid-addresses}

垃圾郵件發送者通常使用基於頻繁名稱和名字清單的地址生成器；此外，他們很少處理郵件伺服器傳回的技術通知。 無效地址的高率通常被解釋為垃圾郵件的標誌。 雙重加入機制和有效處理技術反彈訊息，可避免此情況。

## 降低投訴率 {#reduce-complaint-rate}

ISP通常會以明顯的方式將收到的訊息報告為垃圾訊息。 這使得識別不可靠源成為可能。 透過快速執行退出要求、定期使用特定清單、透過雙重加入系統驗證同意，並實作回饋回覆，您可以降低投訴率。

## 傳送至蜜罐地址 {#honeypot-addresses}

ISP和其他組織(請參閱https://www.projecthoneypot.org/)會利用不對應於實際人員，但僅是為了欺騙垃圾郵件發送者而建立的郵箱。 這些所謂的「蜜罐」地址會發佈在網路上，以便由垃圾郵件機器人收集，從而捕獲非法發送者。 使用雙重選擇加入機制，將此類地址排除在清單中。 使用協力廠商清單時，您必須確定其維護人員採用的方法。

## 改編訊息內容 {#adapt-message-content}

在較小程度上，某些郵件的內容會導致某些篩選器將其檢測為垃圾郵件。 使用某些單字、在主旨行和訊息內使用驚嘆號，會視為垃圾郵件的告示符號。 此外，垃圾郵件發送者已知會用影像取代文字，以防止反垃圾郵件過濾器自動分析違規文字。 因此，含有高比例影像或影像作為附件的訊息（HTML格式）最終可能會遭到封鎖。

## 定期傳送 {#regular-deliveries}

寄送垃圾郵件的人會進行程式化傳送，以維持其久遠的聲譽。 他們有時需要調整行銷計畫，以符合ISP強加的最佳實務，因此，在聲譽達到高峰（上升）後，他們會設定定期的遞送。
