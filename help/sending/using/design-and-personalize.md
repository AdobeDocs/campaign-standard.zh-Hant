---
title: 建置個人化內容
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 瞭解如何設計郵件內容並嘗試避免可能阻止您執行傳遞的常見問題。 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 7%

---

# 建置個人化內容 {#build-personalized-content}

設計郵件內容時，請盡量避免可能阻止您執行傳遞的常見問題。 大多數時候，可能的錯誤都與 [個性化](../../designing/using/personalization.md)，在 [使用現有內容](../../designing/using/using-existing-content.md)  — 和 [轉換HTML內容](../../designing/using/using-existing-content.md#converting-an-html-content)  — 和 [影像](../../designing/using/images.md)。

## 優化個性化 {#optimize-personalization}

為避免可能阻止您執行傳遞並改善收件人體驗的常見問題，Adobe Campaign允許您個性化您的郵件。

您可以使用儲存在Adobe Campaign資料庫中的收件人資料，或通過跟蹤、登錄頁、訂閱等方式收集。
在中介紹個性化基礎 [此部分](../../designing/using/personalization.md)。

確保您的郵件內容設計正確，以避免任何與個性化設定通常相關的錯誤。

可以根據表達式編輯器中定義的條件手動添加動態內容以向收件人顯示不同的內容。 添加動態內容時，必須始終為不滿足選定條件的收件人保留預設變數。
有關動態內容的詳細資訊，請參閱 [此部分](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

**提示**  — 使用不同的test配置檔案預覽電子郵件，以確保正確配置了動態內容。

## 構建優化內容 {#optimize-content}

在生成電子郵件時，請牢記以下一般最佳做法。

* 保持設計簡單

* 記住移動用戶

* 避免完全基於影像的電子郵件

* 使用電子郵件安全字型

* 編碼特殊字元

### 主旨列

工作 [主題行](../../designing/using/subject-line.md) 要提高開放率：

* 避免過長的主題。 最多使用50個字元

* 避免重複使用諸如「免費」或「優惠」等可視為垃圾郵件的詞

* 避免大寫字母和特殊字元，如&quot;!&quot;、&quot;£&quot;、&quot;€&quot;、&quot;$&quot;

### 鏡像頁面

始終包括鏡像頁面連結。 首選位置是電子郵件的頂部。 [了解更多](../../designing/using/personalization.md#adding-a-content-block)

### 取消訂閱連結

取消訂閱連結至關重要。 它必須可見且有效，並且表單必須有效。 瞭解取消訂閱連結准則 [此部分](../../designing/using/personalization.md#about-targeting-dimension)。

預設情況下，分析消息時， [類型規則](../../sending/using/control-rules.md) 檢查是否包括了opt-out連結，如果缺少，則生成警告。

**提示**:由於人為錯誤總是可能發生，因此在每次發送之前，請檢查「opt-out（選擇退出）」連結是否工作正常。 例如，在發送證明時，請確保連結有效，表單聯機，並且「不再聯繫此收件人」欄位更改為「是」。

瞭解如何插入選擇退出連結 [此部分](../../designing/using/personalization.md#adding-a-content-block)。

### 電子郵件大小 {#email-size}

為避免效能或可交付性問題，建議的電子郵件最大大小約為 **35KB**。

要限制電子郵件，請考慮以下事項：

* 刪除冗餘或未使用的樣式

* 將一些電子郵件內容移動到 [登錄頁](../../channels/using/getting-started-with-landing-pages.md)

* 精簡代碼

確保在最終發送之前test任何更改。

在Adobe Campaign，電子郵件的預設最大大小設定為 **100MB**。 <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

如果達到該限制，超過該限制的消息將失敗，並且在傳遞日誌中顯示錯誤消息。 相同傳遞的其他消息將不受影響。 在這種情況下，您必須調整電子郵件模板的動態部分或傳遞所使用的內容片段。 <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobe建議保留最大消息大小預設值。 但是，可以在 **[!UICONTROL Maximum message size]** 選項，通過 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 菜單，按 [功能管理員](../../administration/using/users-management.md#functional-administrators) 只是。

>[!IMPORTANT]
>
>如果將此值設定為零，則不應用任何限制。

### SMS長度

根據預設，SMS 中的字元數量符合 GSM（行動通訊全球系統）標準。使用 GSM 編碼的 SMS 訊息最多只能有 160 個字元，若是以多個部分傳送的訊息，則每個 SMS 的 SMS 訊息最多只能有 153 個字元。

音譯包括當 GSM 標準未考慮到 SMS 的一個字元時，用另一個字元取代該字元。請注意，將個性化欄位插入SMS消息的內容可能會引入GSM編碼未考慮的字元。 您可以通過選中相應的SMPP通道設定頁籤中的相應框來授權字元音譯 **[!UICONTROL External account]**。
瞭解更多資訊 [此部分](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。

**提示**:

* 要保留SMS消息中的所有字元，例如，要不更改正確的名稱，請不要啟用音譯。

* 但是，如果您的SMS消息包含許多GSM標準未考慮的字元，則啟用音譯功能可限制發送消息的成本。

瞭解更多資訊 [此部分](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。

### 響應性電子郵件設計

響應性設計確保電子郵件對開啟該電子郵件的設備進行最佳呈現。

* 使用響應性電子郵件HTML，而不是WebHTML

* 使用預覽模式併發送校樣以在盡可能多的設備上test渲染。 瞭解如何 [預覽消息](../../sending/using/previewing-messages.md) 在發送之前。

* 市場活動電子郵件設計器為移動設備提供了響應性設計格式模板。 在[本頁](../../designing/using/using-reusable-content.md#content-templates)中深入瞭解。

## 管理映像 {#manage-images}

使用影像時，請遵循以下指導原則。

### 防止影像阻塞

預設情況下，某些電子郵件客戶端會阻止影像，而一些用戶會更改其設定以阻止影像以保存資料使用情況。 因此，如果不下載影像，則整個消息可能丟失。 為避免這種情況：

* 將內容與影像和文本平衡。 避免完全基於影像的電子郵件。

* 如果文本必須包含在影像中，請使用Alt和標題文本來確保您的消息傳遞。 設定替換/標題文本的樣式以改進其外觀。

* 避免使用背景影像，因為某些電子郵件客戶端不支援這些影像。

### 使影像響應

嘗試使影像響應並可調整大小。 請注意，這可能會帶來成本影響，因為需要較長的構建時間。

### 使用絕對影像參照

要從外部訪問，與市場活動連結的電子郵件和公共資源中使用的影像必須存在於外部可訪問的伺服器上。

## 預覽您的郵件 {#preview-msg}

Adobe建議預覽您的郵件以檢查其個性化以及您的收件人將如何查看您的遞送。

在電子郵件設計器中， **[!UICONTROL Preview]** 按鈕，查看收件人的每個內容的呈現。 將個性化欄位和內容的條件元素替換為所選簡檔的相應資訊。 [了解更多](../../sending/using/previewing-messages.md)
