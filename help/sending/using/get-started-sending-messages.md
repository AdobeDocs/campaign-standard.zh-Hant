---
title: 開始測試和傳送
description: 準備、測試、排程、傳送及監控您的訊息。
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 14%

---

# 開始測試和傳送 {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">準備和測試</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">傳送、監視和追蹤</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">傳遞能力准則</a></p></td></tr>
</table>

定義目標並建立訊息內容後，您需要準備並測試傳送的內容、個人化、轉譯和設定。 這可讓您在將訊息傳送至主要目標之前，確定一切皆正確。 為此，提供了多種功能，例如預覽、校樣、電子郵件主題行測試或電子郵件呈現。

執行行銷活動並傳送不同訊息後，請使用記錄檔監控行銷活動，以檢查行銷活動是否成功，並擷取收件者的追蹤資訊。

最後，運用Campaign Standard提供的傳遞能力准則和工具，改善傳遞的訊息數量，並確保行銷活動取得成功。

![](assets/do-not-localize/how-to-video.png) [瞭解如何透過影片傳送測試電子郵件、準備及傳送電子郵件傳遞](#video)

## 準備和測試 {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **訊息準備** 分析訊息的目標、個人化及有效性。 在此步驟中偵測到的錯誤必須先加以更正，才能繼續進行。

**預覽和測試** 使用各種功能傳送訊息：傳送校樣以測試設定檔或目標設定檔、測試電子郵件的主旨行，以及檢查訊息的轉譯，以確保訊息以最佳方式顯示在各種Web使用者端、網頁郵件和裝置上。

運用Campaign排程功能來定義訊息的傳送時間。 例如，您可以調整在收件者的時區傳送、最佳化傳送時間或計算傳送日期。

使用 **型別** 在準備期間檢查您的訊息是否有效，並透過疲勞、控制和目標定位規則符合您的品質標準。 例如，檢查您的電子郵件是否一律包含主旨行，或從訊息收件者中排除未訂閱者。

閱讀全文:

* [準備傳送](../../sending/using/preparing-the-send.md)
* [預覽訊息](../../sending/using/previewing-messages.md)
* [傳送校樣](../../sending/using/sending-proofs.md)
* [電子郵件轉譯](../../sending/using/email-rendering.md)
* [排程訊息](../../sending/using/about-scheduling-messages.md)
* [關於類型與類型規則](../../sending/using/about-typology-rules.md)

## 傳送、監視和追蹤 {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

訊息準備就緒後，您可以確認傳送和存取記錄檔及報告至 **監視傳遞** 和評估行銷活動的成功。 Adobe Campaign也提供電子郵件警報系統，以追蹤傳送成功或失敗，以及隔離管理功能。

**追蹤行為** 使用工作階段和永久Cookie來擷取追蹤資訊（已點按的URL、映象頁面、已開啟的郵件……）。

最後，您可以將Adobe Campaign設定為 **保留電子郵件的副本** 透過電子郵件密件副本從您的平台傳送。 特別是，如果您的組織需要封存所有傳出電子郵件訊息以符合規定，您可以啟用此功能。

閱讀全文:

* [確認傳送](../../sending/using/confirming-the-send.md)
* [追蹤訊息](../../sending/using/tracking-messages.md)
* [使用電子郵件密件副本進行歸檔](../../sending/using/archiving.md)
* [監視傳遞](../../sending/using/monitoring-a-delivery.md)
* [瞭解傳遞故障](../../sending/using/understanding-delivery-failures.md)
* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)

## 傳遞能力准則 {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

可遞送性可讓您測量行銷活動在到達收件者收件匣時不會退回或標示為垃圾訊息的成功程度。

Campaign Standard提供數種 **傳遞工具** 協助您改善成功傳遞的訊息數量：傳遞輸送量報告、傳送時間最佳化、訊息預覽、電子郵件呈現、隔離管理等。

閱讀全文:

* [關於傳遞能力](../../sending/using/about-deliverability.md)
* [監視傳遞能力](../../sending/using/monitor-deliverability.md)
* [Adobe傳遞性最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant)
* [控制傳遞輸送量](../../reporting/using/delivery-throughput.md)

## 額外資源

* [設計A/B測試電子郵件](../../channels/using/designing-an-a-b-test-email.md)
* [開始使用訊息](../../channels/using/key-steps-to-send-a-message.md)
* [關於傳遞的最佳實務](../../sending/using/delivery-best-practices.md)
* [新增控制組](../../sending/using/control-group.md)

## 教學課程影片 {#video}

本影片說明如何以Campaign Standard傳送測試電子郵件、準備然後傳送電子郵件傳遞。

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

提供其他Campaign Standard操作影片 [此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant).
