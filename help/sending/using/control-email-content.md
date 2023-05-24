---
title: 控制Adobe Campaign Standard的電子郵件內容
description: 瞭解如何在編輯電子郵件內容時提高Adobe Campaign Standard的可交付性。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 8%

---

# 控制電子郵件內容{#control-email-content}

<!--TO KEEP because specific to Campaign-->

為了確保您的電子郵件到達您的收件人並提高您的電子郵件傳送率，他們必須遵守許多規則。 否則，某些消息的內容可以被檢測為垃圾郵件。 Adobe Campaign為您提供了多種工具，使您的內容符合這些規則。

在設計消息內容時，請遵循以下原則：

* [發件人名稱和地址](#sender-name):地址必須明確地標識發件人。 域必須由發件人擁有並註冊。 不能對域註冊進行私有化。
   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [個性化和發送時間優化](#perso-send-time-optimization):個性化內容並定義每個收件人的發送時間會增加您的郵件開啟的機會。
* 影像和文本：尊重適當的文本/影像比率（例如60%的文本和40%的影像）。
* [取消訂閱連結](#opt-out) 和登錄頁：取消訂閱連結是必要的。 它必須可見且有效，並且表單必須有效。
* 預覽：使用Adobe Campaign提供的工具檢查和優化您的電子郵件內容([反垃圾郵件分析](#anti-spam-analysis)。 [電子郵件呈現](#message-responsiveness))。

有關在設計內容時優化可交付性的其他提示，請參見 [Adobe交付能力最佳實踐指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html)。

>[!NOTE]
>
>有關編輯電子郵件內容的詳細資訊，請參閱 [電子郵件設計器概述](../../designing/using/designing-content-in-adobe-campaign.md) 和 [消息設計最佳做法](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## 發件人名稱和地址 {#sender-name}

某些ISP檢查發送者地址的有效性(**[!UICONTROL From]**)，然後接受消息。 格式錯誤的地址可能導致接收伺服器拒絕它。

![](assets/delivery_content_edition16.png)

您必須確保在實例級別或最常用的方案中提供正確地址。 要執行此操作，請與管理員聯繫。

有關此的詳細資訊，請參閱 [定義電子郵件的電子郵件發件人](../../designing/using/subject-line.md#email-sender)。

## 個性化和發送時間優化 {#perso-send-time-optimization}

為了改善收件人的體驗並讓他們開啟您的電子郵件，Adobe Campaign使您能夠個性化您的郵件。 如需詳細資訊，請參閱[本節](../../designing/using/personalization.md)。

要提高郵件的開啟率，您還可以手動定義每個收件人的發送時間。 每個設定檔都會在指定的日期和時間收到訊息。有關此的詳細資訊，請參閱 [優化發送時間](../../sending/using/optimizing-the-sending-time.md)。

## 選擇退出連結和窗體 {#opt-out}

預設情況下，當分析消息時，類型規則會檢查是否包含了opt-out連結，並在缺少該連結時生成警告。 有關管理連結的詳細資訊，請參見 [此部分](../../designing/using/links.md)。

每次發送前，必須檢查選擇退出連結是否正常工作。 例如， [發證](../../sending/using/sending-proofs.md)，確保連結有效，表單聯機，並且驗證此檢查 **[!UICONTROL No longer contact]** 框。 您應系統地進行此檢查，因為在輸入連結或更改表單時始終可能出現人為錯誤。 有關管理選擇加入和選擇退出的更多資訊，請參見 [此部分](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)。

![](assets/optin_landingpage_3.png)

如果在交貨啟動後檢測到與取消訂閱有關的問題，則仍然可以為那些按一下選擇退出連結的收件人手動執行取消訂閱（例如，使用成批更新功能），即使他們無法確認其選擇。

一般來說，您不應通過要求收件人填寫電子郵件地址或姓名等欄位來妨礙希望退出的收件人。 取消訂閱登錄頁應只有一個驗證按鈕。

請求其他確認不可靠：用戶可能有兩個重定向到同一框的電子郵件地址(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果配置檔案只能記住第一個地址，並希望通過發送到另一個地址的消息取消訂閱，則表單將拒絕此操作，因為加密的標識符與輸入的電子郵件地址不匹配。

## 反垃圾郵件分析 {#anti-spam-analysis}

Adobe Campaign消息編輯器整合了 **反垃圾郵件分析** 它允許您對電子郵件進行分級，以確定郵件是否存在被接收時使用的反垃圾郵件工具視為垃圾郵件的風險。 有關此的詳細資訊，請參閱 [預覽消息](../../sending/using/previewing-messages.md)。

在消息內容編輯器中，按一下 **[!UICONTROL Preview]**。 如果反垃圾郵件檢查檢測到此郵件存在高風險，則會發出警告。 按一下 **[!UICONTROL Anti-spam analysis]** 的子菜單。

![](assets/sending_anti-spam_analysis.png)

## 電子郵件轉譯 {#message-responsiveness}

在發送郵件之前，您可以通過檢查不同設備上的郵件外觀來test郵件響應。 這是為了確保它以最佳方式顯示在各種Web客戶端、 Web郵件和設備上。

![](assets/inbox_rendering_report_3.png)

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

如需詳細資訊，請參閱「[電子郵件轉譯](../../sending/using/email-rendering.md)」。
