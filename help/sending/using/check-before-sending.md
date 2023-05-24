---
title: 傳送前先檢查
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: "一旦您的郵件準備好，請瞭解如何在發送前執行所有檢查"
feature: Deliverability
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 15%

---

# 發送前執行所有檢查 {#perform-all-checks}

一旦您的消息準備就緒，請確保其內容在所有設備上都正確顯示，並且不包含任何錯誤，如錯誤的個性化設定或中斷的連結。

在發送郵件之前，還要確保參數和配置與傳遞一致。

## 為什麼驗證是關鍵 {#validation-is-key}

在發送傳遞之前，您需要確保您的收件人將收到您確實要發送的郵件。 為此，您需要驗證消息內容和傳遞參數。

通過此步驟，您可以檢測可能的錯誤並在將錯誤傳送到主目標之前對其進行修復。

顯示驗證交貨的步驟 [此部分](../../sending/using/get-started-sending-messages.md#prepare-test-send)。

## 電子郵件轉譯 {#email-rendering}

在按下 **[!UICONTROL Send]** 按鈕之前，請確定您的郵件會以最佳方式顯示在各種 Web 用戶端、網頁郵件與裝置上。

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

**提示**:

* 您可以在接收消息的不同上下文中查看已發送的消息：Web郵件、消息服務、移動等。

* 電子郵件呈現功能對於確定您的電子郵件活動是否成功地使其超過主要ISP（Internet服務提供商）和Web郵件服務的過濾器至關重要。 此類工具會將電子郵件的印前拷貝發送到test收件箱網路，這樣您就可以看到這些服務中消息的顯示或呈現方式。 它們還可能包括報告和代碼更正選項，這些選項可幫助您快速識別並做出可改善交付性的修復。

瞭解更多資訊 [此部分](../../sending/using/email-rendering.md)。

## 校樣消息 {#proof-messages}

通過發送校樣，您可以檢查選擇退出連結、鏡像頁和任何其他連結、驗證消息、驗證影像是否顯示、檢測可能的錯誤等。 您可能還希望檢查不同設備上的設計和呈現。

瞭解更多資訊 [此部分](../../sending/using/sending-proofs.md)。

## 設定A/B測試交貨 {#a-b-testing-deliveries}

如果您有幾個用於電子郵件傳遞的內容，則可以使用A/B測試來確定哪個版本將對目標群體產生最大影響。

**提示**:

* 將不同版本發送給您的某些收件人

* 選擇成功率最高的，並將其發送到目標的其他部分

瞭解更多資訊 [此部分](../../channels/using/designing-an-a-b-test-email.md)。
