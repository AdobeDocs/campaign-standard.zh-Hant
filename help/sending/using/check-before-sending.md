---
title: 傳送前先檢查
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「訊息準備就緒後，請瞭解如何在傳送前執行所有檢查」
feature: Deliverability
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 15%

---

# 傳送前執行所有檢查 {#perform-all-checks}

訊息就緒後，請確定內容在所有裝置上皆正確顯示，且未包含任何錯誤，例如錯誤的個人化或中斷的連結。

在傳送訊息之前，也請確定引數和設定與傳送一致。

## 為何驗證是關鍵 {#validation-is-key}

傳送傳遞前，您必須確保收件者會收到您真正想要傳送的訊息。 為此，您需要驗證訊息內容和傳遞引數。

此步驟可讓您在傳送到主要目標之前，偵測並修正可能的錯誤。

以下說明驗證傳送的步驟 [在本節中](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## 電子郵件轉譯 {#email-rendering}

在按下 **[!UICONTROL Send]** 按鈕之前，請確定您的郵件會以最佳方式顯示在各種 Web 用戶端、網頁郵件與裝置上。

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

**提示**：

* 您可以在不同的接收內容中檢視已傳送的訊息：網頁郵件、訊息服務、行動裝置等。

* 電子郵件呈現功能對於識別您的電子郵件行銷活動是否成功通過主要ISP （網際網路服務提供者）的篩選器和網頁郵件服務至關重要。 這類工具會將電子郵件的預檢復本傳送至測試收件匣的網路，以便您檢視這些服務中訊息的顯示或呈現方式。 它們也可能包括報表和程式碼更正選項，協助您快速識別並進行修正，以改善傳遞能力。

瞭解更多 [在本節中](../../sending/using/email-rendering.md).

## 校樣訊息 {#proof-messages}

傳送校樣可讓您檢查選擇退出連結、映象頁面和任何其他連結、驗證訊息、驗證影像是否已顯示、偵測可能的錯誤等。 您可能也會想要檢查您在不同裝置上的設計和演算。

瞭解更多 [在本節中](../../sending/using/sending-proofs.md).

## 設定A/B測試傳送 {#a-b-testing-deliveries}

如果您有數個電子郵件傳送內容，可使用A/B測試來找出哪個版本對目標母體有最大影響。

**提示**：

* 傳送不同版本給部分收件者

* 選取成功率最高的專案，並將其傳送至目標的其餘部分

瞭解更多 [在本節中](../../channels/using/designing-an-a-b-test-email.md).
