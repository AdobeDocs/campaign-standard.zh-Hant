---
title: 在Adobe Campaign Standard中控制電子郵件內容
description: 瞭解在編輯您的電子郵件內容時，如何改善Adobe Campaign Standard中的傳遞能力。
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
source-wordcount: '787'
ht-degree: 6%

---

# 控制電子郵件內容{#control-email-content}

<!--TO KEEP because specific to Campaign-->

為確保您的電子郵件能送達收件者並提高電子郵件傳遞率，他們必須遵守許多規則。 否則，某些訊息的內容可能會偵測為垃圾訊息。 Adobe Campaign提供數種工具，可讓您的內容符合這些規則。

設計訊息內容時，請遵循下列原則：

* [寄件者名稱和地址](#sender-name)：地址必須明確識別寄件者。 網域必須由寄件者擁有並註冊給寄件者。 網域登入不可為私用。
  <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [Personalization和傳送時間最佳化](#perso-send-time-optimization)：個人化內容並定義每位收件者的傳送時間會增加您開啟郵件的機會。
* 影像和文字：遵循像面文字/影像比例（例如60%文字和40%影像）。
* [取消訂閱連結](#opt-out)和登陸頁面：取消訂閱連結是必要的。 它必須可見且有效，而且表單必須有效。
* 預覽：使用Adobe Campaign提供的工具來檢查並最佳化您的電子郵件內容（[反垃圾郵件分析](#anti-spam-analysis)，[電子郵件呈現](#message-responsiveness)）。

如需在設計內容時最佳化傳遞能力的其他秘訣，請參閱[Adobe傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html)。

>[!NOTE]
>
>如需編輯電子郵件內容的詳細資訊，請參閱[電子郵件Designer概觀](../../designing/using/designing-content-in-adobe-campaign.md)和[訊息設計最佳實務](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## 寄件者名稱和地址 {#sender-name}

某些ISP在接受訊息之前會檢查寄件者地址(**[!UICONTROL From]**)的有效性。 格式錯誤的位址可能會導致接收伺服器拒絕該位址。

![](assets/delivery_content_edition16.png)

您必須確保在例項層級或最常使用的案例中提供正確的位址。 若要這麼做，請聯絡管理員。

如需詳細資訊，請參閱[定義電子郵件的電子郵件寄件者](../../designing/using/subject-line.md#email-sender)。

## Personalization和傳送時間最佳化 {#perso-send-time-optimization}

為了改善收件者的體驗並讓他們開啟您的電子郵件，Adobe Campaign可讓您個人化您的訊息。 如需詳細資訊，請參閱[本節](../../designing/using/personalization.md)。

若要提高訊息的開啟率，您也可以手動定義每個收件者的傳送時間。 每個設定檔都會在指定的日期和時間收到訊息。 如需詳細資訊，請參閱[最佳化傳送時間](../../sending/using/optimizing-the-sending-time.md)。

## 選擇退出連結和表單 {#opt-out}

依預設，分析訊息時，型別規則會檢查是否包含退出連結，如果缺少該連結，則會產生警告。 如需管理連結的詳細資訊，請參閱[本節](../../designing/using/links.md)。

每次傳送前，您必須先檢查選擇退出連結是否正常運作。 例如，當[傳送校樣](../../sending/using/sending-proofs.md)時，請確定連結有效、表單線上上，且驗證此功能時會檢查&#x200B;**[!UICONTROL No longer contact]**&#x200B;方塊。 您應該系統地進行此檢查，因為輸入連結或變更表單時總是可能發生人為錯誤。 如需管理加入和退出的詳細資訊，請參閱[本節](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)。

![](assets/optin_landingpage_3.png)

如果在開始傳遞後偵測到有關取消訂閱的問題，則仍可以為按一下選擇退出連結的收件者手動執行取消訂閱（例如使用大量更新函式），即使他們無法確認自己的選擇。

一般而言，您不應透過要求收件者填寫電子郵件地址或名稱等欄位，來妨礙想要選擇退出的收件者。 取消訂閱登入頁面應只有一個驗證按鈕。

要求額外確認並不可靠：使用者可能有兩個電子郵件地址會重新導向至同一個方塊(例如：firstname.lastname@club.com和firstname.lastname@internet-club.com)。 如果設定檔只能記住第一個地址，並希望透過傳送給另一個的訊息取消訂閱，則表單將拒絕此操作，因為加密的識別碼和輸入的電子郵件地址不匹配。

## 反垃圾郵件分析 {#anti-spam-analysis}

Adobe Campaign的郵件編輯器整合了&#x200B;**反垃圾郵件分析**，可讓您對電子郵件評分，以判斷郵件是否會在收到郵件時被反垃圾郵件工具視為垃圾郵件。 如需詳細資訊，請參閱[預覽訊息](../../sending/using/previewing-messages.md)。

在訊息內容編輯器中，按一下&#x200B;**[!UICONTROL Preview]**。 如果反垃圾郵件檢查偵測到此郵件有高風險，郵件會警告您。 按一下&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;以檢視詳細資料。

![](assets/sending_anti-spam_analysis.png)

## 電子郵件轉譯 {#message-responsiveness}

在傳送訊息之前，您可以檢查訊息在不同裝置上的外觀，以測試訊息回應能力。 這是為了確保以最佳方式顯示在各種Web使用者端、網頁郵件與裝置上。

![](assets/inbox_rendering_report_3.png)

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

如需詳細資訊，請參閱「[電子郵件轉譯](../../sending/using/email-rendering.md)」。
