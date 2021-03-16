---
solution: Campaign Standard
product: campaign
title: 傳送訊息的關鍵步驟
description: 請依照下列步驟，使用 Adobe Campaign 建立和傳送訊息。
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: 概觀
role: 業務從業人員
level: 初學者
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 12%

---


# 傳送訊息的關鍵步驟{#key-steps-to-send-a-message}

在本節中，您將學習如何使用Adobe Campaign Standard來建立個人化訊息並傳送給目標對象。

有關如何建立和配置每個通信通道的具體資訊，請參閱以下各節：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [建立簡訊](../../channels/using/creating-an-sms-message.md)
* [建立直接郵件傳遞](../../channels/using/creating-the-direct-mail.md)
* [建立推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)。
* [準備和傳送應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md)

要瞭解交付最佳實踐，請參閱[交付最佳實踐](../../sending/using/delivery-best-practices.md)一節。

## 建立您的訊息

運用Campaign Standard[行銷活動](../../start/using/marketing-activities.md)來建立電子郵件、簡訊、直效郵件、推播通知或應用程式內訊息。

![](assets/marketing-activities.png)

您可從行銷活動清單或使用[專用活動](../../automating/using/about-channel-activities.md)的工作流程來建立訊息。

![](assets/steps-channel.png)

## 定義觀眾

定義訊息的收件者。 若要這麼做，請使用左窗格的[查詢編輯器](../../automating/using/editing-queries.md)來篩選資料庫中包含的資料，並建立規則來定位您的對象。

可用的觀眾類型有幾種：

* **[!UICONTROL Target]** 是您電子郵件的主要目標，
* **[!UICONTROL Test profiles]** 是用於測試和驗證您電子郵件的設定檔(請參閱 [管理測試設定檔](../../audiences/using/managing-test-profiles.md))。

![](assets/steps-audience.png)

## 設計和個人化內容

在&#x200B;**[!UICONTROL Content]**&#x200B;塊中，使用資料庫中的欄位來設計和個性化消息內容。 如需如何設計特定頻道內容的詳細資訊，請參閱本頁最上方的章節。

![](assets/steps-content.png)

## 準備和測試

[準](../../sending/using/preparing-the-send.md) 備訊息。此程式會計算目標人口並準備個人化訊息。

![](assets/steps-prepare.png)

**使用Campaign Standard功能傳** 送訊息前，請先檢查並測試訊息：預覽、電子郵件轉譯、校對等。如需詳細資訊，請參閱[本章節](../../sending/using/previewing-messages.md)。

使用&#x200B;**[!UICONTROL Schedule]**&#x200B;塊定義何時發送消息（請參閱[計畫消息](../../sending/using/about-scheduling-messages.md)）。

![](assets/steps-schedule.png)

## 傳送及追蹤

訊息準備就緒後，您就可以確認傳送。 **[!UICONTROL Deployment]**&#x200B;區塊會顯示傳送進度和結果。

![](assets/steps-send.png)

有幾個日誌可幫助您監視消息的傳送（請參閱[監視傳送](../../sending/using/monitoring-a-delivery.md)）。 您也可以透過Campaign Standard的[追蹤功能](../../sending/using/tracking-messages.md)來追蹤遞送收件者的行為。

![](../../sending/using/assets/tracking_logs.png)

透過各種指標和圖表衡量訊息的成效以及傳送和促銷活動的演變（請參閱[存取報表](../../reporting/using/about-dynamic-reports.md)）。

![](assets/steps-reports.png)
