---
solution: Campaign Standard
product: campaign
title: 控制Adobe Campaign Standard的電子郵件內容
description: 瞭解如何在編輯您的電子郵件內容時改善Adobe Campaign Standard的傳遞能力。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 傳送能力
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 8%

---


# 控管電子郵件內容{#control-email-content}

<!--TO KEEP because specific to Campaign-->

為了確保您的電子郵件送達您的收件人並改善電子郵件的傳遞率，他們必須遵守許多規則。 否則，某些消息的內容可能被檢測為垃圾郵件。 Adobe Campaign提供數種工具，讓您的內容符合這些規則。

在設計您的訊息內容時，請遵循下列原則：

* [發件人姓名和地址](#sender-name):地址必須明確識別發件人。網域必須由傳送者擁有並註冊。 域註冊不得私有化。

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [個人化和傳送時間最佳化](#perso-send-time-optimization):個人化內容並定義每位收件者的傳送時間，會增加您的訊息開啟的機率。
* 影像和文字：尊重適當的文字／影像比例（例如60%的文字和40%的影像）。
* [取消訂](#opt-out) 閱連結和登陸頁面：取消訂閱連結是必備的。它必須可見且有效，而且表單必須正常運作。
* 預覽：使用Adobe Campaign提供的工具檢查並最佳化您的電子郵件內容（[反垃圾訊息分析](#anti-spam-analysis)、[電子郵件轉譯](#message-responsiveness)）。

如需在設計內容時最佳化傳送能力的其他秘訣，請參閱[Adobe傳送能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html)。

>[!NOTE]
>
>有關編輯電子郵件內容的詳細資訊，請參閱[電子郵件設計器概述](../../designing/using/designing-content-in-adobe-campaign.md)和[郵件設計最佳實踐](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## 發件人姓名和地址{#sender-name}

某些ISP在接受消息之前檢查發件人地址(**[!UICONTROL From]**)的有效性。 錯誤形成的地址可能導致接收伺服器拒絕。

![](assets/delivery_content_edition16.png)

您必須確保在實例級別或最常使用的情況下提供正確的地址。 若要這麼做，請連絡您的管理員。

有關詳細資訊，請參閱[定義電子郵件的電子郵件發件人](../../designing/using/subject-line.md#email-sender)。

## 個人化和傳送時間最佳化{#perso-send-time-optimization}

為了改善收件者的體驗，並讓他們開啟您的電子郵件，Adobe Campaign讓您個人化您的訊息。 如需詳細資訊，請參閱[本節](../../designing/using/personalization.md)。

若要提高訊息的開啟率，您也可以手動定義每位收件者的傳送時間。 每個設定檔都會在指定的日期和時間收到訊息。有關詳細資訊，請參閱[優化發送時間](../../sending/using/optimizing-the-sending-time.md)。

## 退出連結並表單{#opt-out}

依預設，在分析訊息時，排版規則會檢查是否已包含選擇退出連結，並在遺失時產生警告。 有關管理連結的詳細資訊，請參閱[本節](../../designing/using/links.md)。

您必須在每次傳送前檢查退出連結是否正常運作。 例如，當[傳送proof](../../sending/using/sending-proofs.md)時，請確定連結有效、表單是線上且驗證會檢查&#x200B;**[!UICONTROL No longer contact]**&#x200B;方塊。 您應該系統性地進行此檢查，因為在進入連結或更改表單時，總是可能出現人為錯誤。 如需管理選擇加入和選擇退出的詳細資訊，請參閱[本節](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)。

![](assets/optin_landingpage_3.png)

如果在傳送開始後偵測到有關取消訂閱的問題，則仍可以手動（例如使用大量更新功能）對點按選擇退出連結的收件者執行取消訂閱，即使他們無法確認其選擇。

一般而言，您不應嘗試透過要求收件者填寫欄位（例如其電子郵件地址或姓名）來妨礙想要退出的收件者。 取消訂閱的登陸頁面應僅包含一個驗證按鈕。

要求額外確認是不可靠的：使用者可能有兩個電子郵件地址被重新導向至相同方塊(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果描述檔僅能記住第一個位址，並希望透過傳送至另一個位址的訊息取消訂閱，表單將拒絕此項訂閱，因為加密的識別碼與輸入的電子郵件地址不符。

## 反垃圾郵件分析{#anti-spam-analysis}

Adobe Campaign的郵件編輯器整合了&#x200B;**反垃圾郵件分析**，該分析允許您對電子郵件進行分數，以確定郵件是否存在被接收時使用的反垃圾郵件工具視為垃圾郵件的風險。 有關詳細資訊，請參閱[預覽消息](../../sending/using/previewing-messages.md)。

在消息內容編輯器中，按一下&#x200B;**[!UICONTROL Preview]**。 如果反垃圾郵件檢查檢測到此郵件存在高風險，則會發出消息警告。 按一下&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;以檢視詳細資訊。

![](assets/sending_anti-spam_analysis.png)

## 電子郵件呈現 {#message-responsiveness}

在傳送訊息之前，您可以檢查訊息在不同裝置上的外觀，以測試訊息回應速度。 這是為了確保它以最佳方式顯示在各種Web用戶端、Web郵件和裝置上。

![](assets/inbox_rendering_report_3.png)

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

如需詳細資訊，請參閱「[電子郵件轉譯](../../sending/using/email-rendering.md)」。