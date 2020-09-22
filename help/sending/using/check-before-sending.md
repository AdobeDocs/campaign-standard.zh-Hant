---
title: 傳送前先檢查
seo-title: 傳送前先檢查
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d5d9d50474142306457a8c76a24388c3c574791d
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 15%

---


# 傳送前先執行所有檢查 {#perform-all-checks}

當訊息準備就緒後，請確定其內容在所有裝置上都正確顯示，且不包含任何錯誤，例如錯誤的個人化或損壞的連結。

在傳送訊息之前，請確定參數和設定與傳送一致。

## 驗證為何是關鍵 {#validation-is-key}

在傳送傳送內容之前，您必須確保收件者會收到您真正想要傳送的訊息。 為此，您需要驗證訊息內容和傳送參數。

此步驟可讓您偵測可能的錯誤並加以修正，然後再傳送至主要目標。

本節將介紹驗證傳送 [的步驟](../../sending/using/get-started-sending-messages.md#prepare-test-send)。

## 電子郵件呈現 {#email-rendering}

在按下 **[!UICONTROL Send]** 按鈕之前，請確定您的郵件會以最佳方式顯示在各種 Web 用戶端、網頁郵件與裝置上。

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

**提示**:

* 您可以在接收郵件的不同上下文中查看發送的郵件：webmail、訊息服務、行動等。

* 電子郵件轉換功能對於識別您的電子郵件宣傳是否成功超越主要ISP（網際網路服務供應商）和網路郵件服務的篩選至關重要。 此類工具會將電子郵件的預檢副本傳送至測試收件匣網路，讓您瞭解訊息在這些服務間的顯示或呈現方式。 它們也可能包含報表和程式碼修正選項，可協助您快速識別並進行修正，以改善傳遞性。

在本節 [中進一步瞭解](../../sending/using/email-rendering.md)。

## 校對訊息 {#proof-messages}

傳送校樣可讓您檢查選擇退出連結、鏡像頁面和任何其他連結、驗證訊息、確認影像已顯示、偵測可能的錯誤等。 您也可能想要檢查不同裝置上的設計和演算。

詳細資訊[[在本節中](../../sending/using/sending-proofs.md)。

## 設定A/B測試傳送 {#a-b-testing-deliveries}

如果您有數個內容要傳送電子郵件，您可以使用A/B測試來找出哪個版本對目標群體的影響最大。

**提示**:

* 將不同的版本傳送給您的部分收件者

* 選取成功率最高的成功率，並將它傳送至目標的其他部分

在本節 [中進一步瞭解](../../channels/using/designing-an-a-b-test-email.md)。

