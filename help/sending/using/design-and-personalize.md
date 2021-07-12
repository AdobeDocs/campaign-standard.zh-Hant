---
solution: Campaign Standard
product: campaign
title: 建置個人化內容
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 了解如何設計訊息內容，並嘗試避免可能妨礙您執行傳送的常見問題。 
feature: 達成能力
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 7%

---

# 建置個人化內容 {#build-personalized-content}

在設計訊息內容時，請嘗試避免可能妨礙您執行傳送的常見問題。 大多數情況下，可能的錯誤與[個人化](../../designing/using/personalization.md)、使用現有內容](../../designing/using/using-existing-content.md) — 和[轉換HTML內容](../../designing/using/using-existing-content.md#converting-an-html-content) — 和[影像](../../designing/using/images.md)時的格式設定有關。[

## 最佳化個人化 {#optimize-personalization}

為避免執行傳遞作業無法解決的常見問題，並改善收件者的使用體驗，Adobe Campaign可讓您個人化訊息。

您可以使用儲存在Adobe Campaign資料庫中的收件者資料，或透過追蹤、登錄頁面、訂閱等方式收集。
個人化基本介紹在[此區段](../../designing/using/personalization.md)中。

請確定您的訊息內容已正確設計，以避免任何與個人化一般相關的錯誤。

您可以手動新增動態內容，以根據運算式編輯器中定義的條件，向收件者顯示不同內容。 新增動態內容時，您必須一律為不符合選取條件的收件者保留預設變體。
有關動態內容的詳細資訊，請參閱[此區段](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

**提示**  — 使用不同的測試設定檔預覽您的電子郵件，以確定您的動態內容已正確設定。

## 建立最佳化內容 {#optimize-content}

建置電子郵件時，請牢記下列一般最佳實務。

* 保持設計簡單

* 請牢記行動使用者

* 避免完全以影像為基礎的電子郵件

* 使用電子郵件安全字型

* 為特殊字元編碼

### 主旨行

在[主旨行](../../designing/using/subject-line.md)上工作以改善開放率：

* 避開過長的科目。 最多使用50個字元

* 請避免重複使用「free」或「offer」等可視為垃圾訊息的單字

* 避免大寫字母和特殊字元，如「！」、「£」、「€」、「$」

### 鏡像頁面

一律包含鏡像頁面連結。 偏好位置是電子郵件的頂端。 [深入瞭解](../../designing/using/personalization.md#adding-a-content-block)

### 取消訂閱連結

取消訂閱連結至關重要。 表單必須可見且有效，且必須可運作。 在本小節](../../designing/using/personalization.md#about-targeting-dimension)中了解取消訂閱連結指南[。

依預設，分析訊息時，控制項[類型規則](../../sending/using/control-rules.md)會檢查是否已包含選擇退出連結，並在遺失時產生警告。

**提示**:因為一律可能發生人為錯誤，請在每次傳送前檢查選擇退出連結是否正常運作。例如，傳送校樣時，請確定連結有效、表單已上線，且「不再與此收件者聯絡」欄位已變更為「是」。

了解如何在此小節](../../designing/using/personalization.md#adding-a-content-block)插入選擇退出連結[。

### 電子郵件大小 {#email-size}

為避免效能或傳遞能力問題，建議的電子郵件大小上限為&#x200B;**35KB**。

若要限制電子郵件，請考慮下列事項：

* 移除冗餘或未使用的樣式

* 將部分電子郵件內容移至[登錄頁面](../../channels/using/getting-started-with-landing-pages.md)

* 縮小程式碼

請務必在最終傳送前測試任何變更。

在Adobe Campaign中，電子郵件的預設最大大小設定為&#x200B;**100MB**。 <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

如果達到限制，超過限制的訊息將會失敗，且傳送記錄檔中會顯示錯誤訊息。 相同傳送的其他訊息將不會受到影響。 在此情況下，您必須調整電子郵件範本的動態部分或傳送使用的內容片段。<!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobe建議保留最大郵件大小預設值。 不過，此值只能由[功能管理員](../../administration/using/users-management.md#functional-administrators)透過&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;功能表在&#x200B;**[!UICONTROL Maximum message size]**&#x200B;選項中變更。

>[!IMPORTANT]
>
>如果將此值設為零，則不會套用任何限制。

### SMS長度

根據預設，SMS 中的字元數量符合 GSM（行動通訊全球系統）標準。使用 GSM 編碼的 SMS 訊息最多只能有 160 個字元，若是以多個部分傳送的訊息，則每個 SMS 的 SMS 訊息最多只能有 153 個字元。

音譯包括當 GSM 標準未考慮到 SMS 的一個字元時，用另一個字元取代該字元。請注意，將個人化欄位插入SMS訊息的內容，可能會引入GSM編碼未考慮的字元。 您可以核取對應&#x200B;**[!UICONTROL External account]**之SMPP通道設定標籤中的對應方塊，以授權字母音譯。
了解更多[，請參閱本節](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。

**提示**:

* 若要保留SMS訊息中的所有字元原樣，請勿變更正確名稱（例如），請勿啟用音譯。

* 不過，如果您的SMS訊息包含許多GSM標準未考慮的字元，請啟用音譯以限制傳送訊息的成本。

了解更多[，請參閱本節](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。

### 回應式電子郵件設計

回應式設計可確保電子郵件在其開啟的裝置上以最佳方式呈現。

* 使用回應式電子郵件HTML而非網頁HTML

* 使用預覽模式並傳送校樣，以盡可能在裝置上測試轉譯。 了解如何在傳送前預覽訊息](../../sending/using/previewing-messages.md)。[

* Campaign電子郵件設計工具隨附適用於行動裝置的回應式設計格式範本。 在[本頁](../../designing/using/using-reusable-content.md#content-templates)中深入瞭解。

## 管理影像 {#manage-images}

使用影像時，請遵循下列准則。

### 防止影像阻塞

有些電子郵件用戶端預設會封鎖影像，有些使用者會變更其設定以封鎖影像，以便儲存資料使用情況。 因此，如果未下載影像，則會丟失整個消息。 若要避免此情況：

* 平衡內容與影像和文字。 避免完全以影像為基礎的電子郵件。

* 如果影像中必須包含文字，請使用alt和title文字，確保訊息傳達完畢。 設定替代/標題文字的樣式以改善其外觀。

* 避免使用某些電子郵件用戶端不支援的背景影像。

### 讓影像回應式

嘗試讓影像具有回應性和可調整大小。 請注意，這可能會造成成本影響，因為建置所需時間較長。

### 使用絕對影像參照

若要從外部存取，連結至促銷活動的電子郵件和公共資源中使用的影像必須存在於可外部存取的伺服器上。

## 預覽訊息 {#preview-msg}

Adobe建議預覽您的訊息，以檢查其個人化以及收件者如何看到您的傳遞。

在電子郵件設計工具中，**[!UICONTROL Preview]**&#x200B;按鈕可讓您檢視收件者的每個內容呈現。 個人化欄位和內容的條件元素會取代為所選設定檔的對應資訊。 [深入瞭解](../../sending/using/previewing-messages.md)
