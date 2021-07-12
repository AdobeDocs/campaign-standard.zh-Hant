---
solution: Campaign Standard
product: campaign
title: 在Adobe Campaign Standard中控制電子郵件內容
description: 了解如何在編輯電子郵件內容時改善Adobe Campaign Standard中的傳遞能力。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 達成能力
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 8%

---

# 控制電子郵件內容{#control-email-content}

<!--TO KEEP because specific to Campaign-->

為了確保您的電子郵件可送達您的收件者，並改善您的電子郵件傳遞率，他們必須遵守許多規則。 否則，某些消息的內容可能被檢測為垃圾郵件。 Adobe Campaign提供數種工具，讓您的內容符合這些規則。

設計訊息內容時，請遵循下列原則：

* [寄件者名稱和地址](#sender-name):地址必須明確標識發件人。網域必須屬於寄件者，並註冊給寄件者。 域註冊表不得私有化。

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [個人化和傳送時間最佳化](#perso-send-time-optimization):個人化內容並定義每位收件者的傳送時間，可增加開啟訊息的機率。
* 影像和文字：請遵循適當的文字/影像比例（例如60%的文字和40%的影像）。
* [取消訂](#opt-out) 閱連結和登錄頁面：取消訂閱連結至關重要。表單必須可見且有效，且必須可運作。
* 預覽：使用Adobe Campaign提供的工具來檢查並最佳化您的電子郵件內容（[Anti-spam analysis](#anti-spam-analysis)、[電子郵件呈現](#message-responsiveness)）。

如需在設計內容時最佳化傳遞能力的其他秘訣，請參閱[Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html)。

>[!NOTE]
>
>如需編輯電子郵件內容的詳細資訊，請參閱[電子郵件設計工具概述](../../designing/using/designing-content-in-adobe-campaign.md)和[訊息設計最佳實務](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## 寄件者名稱和地址 {#sender-name}

某些ISP在接受郵件之前檢查發件人地址(**[!UICONTROL From]**)的有效性。 錯誤形成的地址可能導致接收伺服器拒絕該地址。

![](assets/delivery_content_edition16.png)

您必須確保在執行個體層級或最常使用的案例中提供正確的地址。 若要這麼做，請聯絡您的管理員。

有關詳細資訊，請參閱[定義電子郵件](../../designing/using/subject-line.md#email-sender)的電子郵件發件人。

## 個人化和傳送時間最佳化 {#perso-send-time-optimization}

為了改善收件者的體驗，並讓他們開啟您的電子郵件，Adobe Campaign可讓您個人化您的訊息。 如需詳細資訊，請參閱[本節](../../designing/using/personalization.md)。

若要提高訊息的開啟率，您也可以手動定義每個收件者的傳送時間。 每個設定檔都會在指定的日期和時間收到訊息。如需詳細資訊，請參閱[最佳化傳送時間](../../sending/using/optimizing-the-sending-time.md)。

## 退出連結和表單 {#opt-out}

依預設，分析訊息時，類型規則會檢查是否已包含選擇退出連結，並在遺失時產生警告。 如需管理連結的詳細資訊，請參閱[此區段](../../designing/using/links.md)。

您必須在每次傳送前，檢查選擇退出連結是否正常運作。 例如，當[傳送校樣](../../sending/using/sending-proofs.md)時，請確定連結有效、表單已上線且驗證會核取&#x200B;**[!UICONTROL No longer contact]**&#x200B;方塊。 您應系統地進行此檢查，因為在進入連結或更改表單時，始終可能出現人為錯誤。 如需管理選擇加入和選擇退出的詳細資訊，請參閱[此區段](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)。

![](assets/optin_landingpage_3.png)

如果在傳送開始後偵測到有關取消訂閱的問題，則即使收件者無法確認其選擇，仍可手動執行取消訂閱（例如使用大量更新功能）。

一般而言，您不應嘗試讓想要退出的收件者填寫欄位（例如其電子郵件地址或名稱），以此方式來阻礙收件者。 取消訂閱登錄頁面應該只包含一個驗證按鈕。

請求附加確認是不可靠的：使用者可能有兩個電子郵件地址已重新導向至相同的方塊(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果設定檔只能記住第一個地址，而且想透過傳送給另一個地址的訊息取消訂閱，則表單會拒絕此項，因為加密的識別碼與輸入的電子郵件地址不符。

## 反垃圾郵件分析 {#anti-spam-analysis}

Adobe Campaign的訊息編輯器整合了&#x200B;**反垃圾訊息分析**，可讓您對電子郵件評分，以判斷訊息是否存在被收到時使用的反垃圾訊息工具視為垃圾郵件的風險。 有關詳細資訊，請參閱[預覽訊息](../../sending/using/previewing-messages.md)。

在訊息內容編輯器中，按一下&#x200B;**[!UICONTROL Preview]**。 如果反垃圾郵件檢查檢測到此郵件有高風險，則會發出消息警告。 按一下&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;以查看詳細資訊。

![](assets/sending_anti-spam_analysis.png)

## 電子郵件轉譯 {#message-responsiveness}

在傳送訊息之前，您可以檢查訊息在不同裝置上的外觀，以測試訊息的回應速度。 這是為了確保以最佳方式顯示在各種Web用戶端、網頁郵件和裝置上。

![](assets/inbox_rendering_report_3.png)

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

如需詳細資訊，請參閱「[電子郵件轉譯](../../sending/using/email-rendering.md)」。
