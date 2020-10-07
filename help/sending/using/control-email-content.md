---
title: 在Adobe Campaign Standard中控制電子郵件內容
description: 瞭解如何在編輯您的電子郵件內容時，改善Adobe Campaign Standard的傳遞能力。
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


# 控管電子郵件內容{#control-email-content}

為了提高電子郵件的傳遞率，並確保您的電子郵件送達您的收件人，電子郵件必須遵守一定數量的規則。

* **發件人姓名和地址**:地址必須明確識別發件人。 網域必須由傳送者擁有並註冊。 域註冊不得私有化。
* **主旨**:避免過度大寫和標點符號，以及垃圾郵件發送者常用的字詞（「Win」、「免費」等）。
* **個人化您的電子郵件**:個人化電子郵件會增加開啟訊息的機率。
* **影像和文字**:尊重適當的文字／影像比例（例如60%的文字和40%的影像）。
* **取消訂閱連結和登陸頁面**:取消訂閱連結是必備的。 它必須可見且有效，而且表單必須正常運作。
* **使用** Adobe Campaign提供的工具來最佳化您的電子郵件內容（傳送分析、反垃圾訊息分析）。

有關編輯電子郵件內容的其他資訊，請參 [閱「電子郵件設計人員概述](../../designing/using/designing-content-in-adobe-campaign.md) 」和 [「郵件」設計最佳實踐方案](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## 發件人姓名和地址 {#sender-name}

某些ISP在接受消息之前檢查發件人地址(From)的有效性。 錯誤形成的地址可能導致接收伺服器拒絕。 您必須確保在實例級別或最常使用的情況下提供正確的地址。 聯絡您的管理員。

![](assets/delivery_content_edition16.png)

有關詳細資訊，請參 [閱個性化發件人名稱](../../designing/using/personalization.md#personalizing-the-sender)。

## 主旨行 {#subject-line}

在編輯電子郵件時，您可以嘗試不同的主旨行，並在傳送電子郵件前先估計其開放率。 如需詳細資訊，請參 [閱測試電子郵件的主旨行](../../sending/using/testing-subject-line-email.md)。

![](assets/predictive_subject_line_example.png)

如需定義電子郵件主旨行的詳細資訊，請參 [閱本節](../../designing/using/subject-line.md)。

## Send time optimization {#send-time-optimization}

若要提高訊息的成功率，您可以手動定義每個收件者的傳送時間。 每個設定檔都會在指定的日期和時間收到訊息。

如需詳細資訊，請參 [閱最佳化傳送時間](../../sending/using/optimizing-the-sending-time.md)。

## 退出連結和表單 {#opt-out}

依預設，在分析訊息時，排版規則會檢查是否已包含選擇退出連結，並在遺失時產生警告。

您必須在每次傳送前檢查退出連結是否正常運作。 例如，傳送校樣時，請確定連結有效、表單是線上，且驗證此變更會勾選「不再連絡人」方塊的值。 您應該系統性地進行此檢查，因為在進入連結或更改表單時，總是可能出現人為錯誤。

如果在傳送開始後偵測到有關取消訂閱的問題，則仍可以手動（例如使用大量更新功能）對點按選擇退出連結的收件者執行取消訂閱，即使他們無法確認其選擇。

一般而言，請勿嘗試透過要求收件者填寫電子郵件地址或姓名等欄位，來妨礙想要退出的收件者。 取消訂閱的登陸頁面應僅包含一個驗證按鈕。 要求額外確認是不可靠的：使用者可能有兩個電子郵件地址被重新導向至相同方塊(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果描述檔僅能記住第一個位址，並希望透過傳送至另一個位址的訊息取消訂閱，表單將拒絕此項訂閱，因為加密的識別碼與輸入的電子郵件地址不符。

## 反垃圾郵件分析 {#anti-spam-analysis}

Adobe Campaign的訊息編輯器整合了 **Anti-spam分析** ，可讓您對電子郵件進行分數，以判斷訊息是否有可能被收到時使用的防垃圾郵件工具視為垃圾郵件的風險。 For more on this, see [Previewing messages](../../sending/using/previewing-messages.md).

在消息內容編輯器中，按一下 **[!UICONTROL Preview]**。 如果反垃圾郵件檢查檢測到此郵件存在高風險，則會發出消息警告。 按一 **[!UICONTROL Anti-spam analysis]** 下以檢視詳細資訊。

![](assets/sending_anti-spam_analysis.png)

## 檢查訊息回應性 {#message-responsiveness}

在傳送訊息之前，您可以檢查訊息在不同裝置上的外觀。 這是為了確保它以最佳方式顯示在各種Web用戶端、Web郵件和裝置上。

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

如需詳細資訊，請參閱「[電子郵件轉譯](../../sending/using/email-rendering.md)」。

![](assets/inbox_rendering_report_3.png)
