---
solution: Campaign Standard
product: campaign
title: 傳送前先檢查
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「在您的郵件準備就緒後，了解如何在發送前執行所有檢查」
feature: 達成能力
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 16%

---

# 在發送前執行所有檢查 {#perform-all-checks}

在您的訊息準備就緒後，請確定其內容在所有裝置上皆正確顯示，且不會包含任何錯誤，例如錯誤的個人化或中斷的連結。

傳送訊息前，也請確定參數和設定與傳送一致。

## 驗證為何是關鍵 {#validation-is-key}

在傳送傳遞前，您必須確保收件者會收到您確實想要傳送的訊息。 若要這麼做，您需要驗證訊息內容和傳送參數。

此步驟可讓您在傳送至主要目標之前，偵測可能的錯誤並加以修正。

在本小節](../../sending/using/get-started-sending-messages.md#prepare-test-send)中顯示了驗證傳送的步驟[。

## 電子郵件轉譯 {#email-rendering}

在按下 **[!UICONTROL Send]** 按鈕之前，請確定您的郵件會以最佳方式顯示在各種 Web 用戶端、網頁郵件與裝置上。

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

**提示**:

* 您可以在可接收郵件的不同內容中檢視已傳送的郵件：網站郵件、訊息服務、行動等。

* 電子郵件呈現功能對於識別您的電子郵件促銷活動是否成功超過主要ISP（網際網路服務提供者）和網路郵件服務的篩選至關重要。 這類工具會將電子郵件的飛行前副本傳送至測試收件匣網路，讓您了解訊息在這些服務中的顯示或呈現方式。 它們也可能包含報表和程式碼修正選項，可協助您快速識別並進行修正，以改善傳遞能力。

了解更多[，請參閱本節](../../sending/using/email-rendering.md)。

## 校樣訊息 {#proof-messages}

傳送校樣可讓您檢查選擇退出連結、鏡像頁面和任何其他連結、驗證訊息、確認影像已顯示、偵測可能的錯誤等。 您也可能想要檢查您的設計和在不同裝置上呈現。

了解更多[，請參閱本節](../../sending/using/sending-proofs.md)。

## 設定A/B測試傳送 {#a-b-testing-deliveries}

如果您有數個電子郵件傳送內容，您可以使用A/B測試來找出哪個版本對目標母體影響最大。

**提示**:

* 將不同的版本傳送給您的部分收件者

* 選取成功率最高的，並將其傳送至目標的其餘部分

了解更多[，請參閱本節](../../channels/using/designing-an-a-b-test-email.md)。
