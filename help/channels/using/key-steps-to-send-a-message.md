---
title: 傳送訊息的關鍵步驟
description: 請依照下列步驟，使用 Adobe Campaign 建立和傳送訊息。
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Overview
role: User
level: Beginner
exl-id: a903d7e2-7654-46b3-bc61-4653a065faad
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 14%

---

# 傳送訊息的重要步驟{#key-steps-to-send-a-message}

在本節中，您將學習如何使用Adobe Campaign Standard建立個人化訊息，並傳送給目標對象。

有關如何建立和配置每個通信通道的特定資訊，請參閱以下部分：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [建立簡訊](../../channels/using/creating-an-sms-message.md)
* [建立直接郵件傳遞](../../channels/using/creating-the-direct-mail.md)
* [建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)。
* [準備和傳送應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md)

若要了解傳遞最佳實務，請參閱[傳遞最佳實務](../../sending/using/delivery-best-practices.md)區段。

## 建立您的訊息

運用Campaign Standard[行銷活動](../../start/using/marketing-activities.md)來建立電子郵件、簡訊、直接郵件、推播通知或應用程式內訊息。

![](assets/marketing-activities.png)

可從行銷活動清單或使用[專用活動](../../automating/using/about-channel-activities.md)的工作流程建立訊息。

![](assets/steps-channel.png)

## 定義對象

定義訊息的收件者。 若要這麼做，請使用左窗格的[查詢編輯器](../../automating/using/editing-queries.md)來篩選資料庫中包含的資料，並建立規則來鎖定您的對象。

可用的對象類型有數種：

* **[!UICONTROL Target]** 是您電子郵件的主要目標，
* **[!UICONTROL Test profiles]** 是用來測試及驗證電子郵件的設定檔(請參閱 [管理測試設定檔](../../audiences/using/managing-test-profiles.md))。

![](assets/steps-audience.png)

## 設計並個人化內容

在&#x200B;**[!UICONTROL Content]**&#x200B;區塊中，使用資料庫的欄位來設計和個人化訊息內容。 如需如何設計特定頻道內容的詳細資訊，請參閱本頁面頂端所列的區段。

![](assets/steps-content.png)

## 準備和測試

[](../../sending/using/preparing-the-send.md) 準備訊息。此程式會計算目標母體並準備個人化訊息。

![](assets/steps-prepare.png)

**使用Campaign Standard功能** 傳送訊息之前，請先檢查並測試訊息：預覽、電子郵件呈現、校對等。如需詳細資訊，請參閱[本章節](../../sending/using/previewing-messages.md)。

使用&#x200B;**[!UICONTROL Schedule]**&#x200B;區塊來定義訊息的傳送時間（請參閱[排程訊息](../../sending/using/about-scheduling-messages.md)）。

![](assets/steps-schedule.png)

## 傳送及追蹤

訊息準備就緒後，您可以確認傳送。 **[!UICONTROL Deployment]**&#x200B;區塊會顯示傳送進度和結果。

![](assets/steps-send.png)

有數個記錄檔可協助您監控訊息的傳送（請參閱[監控傳送](../../sending/using/monitoring-a-delivery.md)）。 您也可以透過Campaign Standard的[追蹤功能](../../sending/using/tracking-messages.md)來追蹤傳送收件者的行為。

![](../../sending/using/assets/tracking_logs.png)

透過各種指標和圖表測量訊息的效益以及傳送和促銷活動的演變（請參閱[存取報表](../../reporting/using/about-dynamic-reports.md)）。

![](assets/steps-reports.png)
