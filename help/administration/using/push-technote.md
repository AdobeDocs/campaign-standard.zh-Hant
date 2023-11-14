---
title: 推播通知頻道近期變更
description: 推播通知頻道近期變更
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: f9a0d01196ac4c31e57ae14cdfa448a9ffd6106f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 1%

---

# 推播通知頻道近期變更 {#push-upgrade}

您可以使用Campaign在Android和iOS裝置上傳送推播通知。 為此，Campaign需仰賴特定的訂閱服務。 Android Firebase Cloud Messaging (FCM)服務的一些重要變更將於2024年發行，並將影響您的Adobe Campaign實施。 此外，對於iOS應用程式，Adobe正在變更允許管理員設定憑證的方式。

## 哪些部分有所變更？ {#push-changes}

### Android {#push-android}

為Google持續改善其服務，我們將於以下日期終止使用舊版FCM API： **2024年6月20日**. 在中進一步瞭解Firebase雲端通訊HTTP通訊協定 [Google Firebase檔案](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

目前Adobe Campaign Standard正在使用HTTP舊版API來傳送Android推播通知訊息，並將在未來幾個月進行變更，以升級至HTTP v1 API。

### iOS {#push-ios}

Adobe也將升級適用於iOS推播通知通道的Adobe Campaign Standard ，並變更允許管理員為其iOS應用程式設定憑證的方式。 管理員現在需要透過iOS的使用者介面上傳Adobe Campaign Standard憑證。

## 您有受到影響嗎？ {#push-impact}

作為Campaign Standard使用者，如果您傳送推播通知訊息給對象，則會受到影響。

## 如何移轉？ {#push-migration}

這些更新需要Campaign Standard組建升級，因為它們會影響行動裝置頻道設定和許可權管理。

我們很快就會提供詳細指示，以利順暢的轉換過程。

我們的客戶支援團隊將全程協助您進行轉換。 我們可能也會舉辦網路研討會及賦權研討會，以涵蓋轉換的技術層面及最佳實務。

同時，建議花點時間檢閱您目前在Adobe Campaign Standard中的設定和自訂，以便您準備在必要時進行任何必要的變更。

如果您有任何急迫的疑慮或問題，請隨時與我們的支援團隊聯絡。
