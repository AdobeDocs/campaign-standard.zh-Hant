---
title: 建置個人化內容
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 瞭解如何設計訊息內容，並嘗試避免可能會阻止您執行傳送的常見問題。 
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

在設計訊息內容時，請儘量避免可能會妨礙您執行傳送的常見問題。 大多數情況下，可能的錯誤與 [個人化](../../designing/using/personalization.md)，格式設定時機 [使用現有內容](../../designing/using/using-existing-content.md)  — 和 [轉換HTML內容](../../designing/using/using-existing-content.md#converting-an-html-content)  — 和 [影像](../../designing/using/images.md).

## 最佳化個人化 {#optimize-personalization}

為避免阻止您執行傳送的常見問題並改善收件者體驗，Adobe Campaign可讓您個人化訊息。

您可以使用儲存在Adobe Campaign資料庫中的收件者資料，或是透過追蹤、登陸頁面、訂閱等收集的資料。
個人化基本資訊顯示於 [本節](../../designing/using/personalization.md).

請確定您的訊息內容經過適當設計，以避免發生任何錯誤，這些錯誤通常與個人化有關。

您可以手動新增動態內容，以根據運算式編輯器中定義的條件向收件者顯示不同的內容。 新增動態內容時，您必須一律為不符合所選條件的收件者保留預設變體。
如需動態內容的詳細資訊，請參閱 [本節](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**提示**  — 使用不同的測試設定檔預覽您的電子郵件，以確保您的動態內容已正確設定。

## 建置最佳化內容 {#optimize-content}

建立電子郵件時，請記住以下一般最佳實務。

* 讓設計保持簡單

* 將行動使用者放在心上

* 避免完全以影像為基礎的電子郵件

* 使用電子郵件安全字型

* 編碼特殊字元

### 主旨列

處理 [主旨列](../../designing/using/subject-line.md) 若要改善開啟率：

* 避免主題太長。 最多使用50個字元

* 避免使用可視為垃圾訊息的重複字詞，例如「free」或「offer」

* 避免使用大寫字母和特殊字元，如「！」、「£」、「€」、「$」

### 鏡像頁面

一律包含映象頁面連結。 偏好位置是電子郵件的頂端。 [了解更多](../../designing/using/personalization.md#adding-a-content-block)

### 取消訂閱連結

取消訂閱連結是必要的。 它必須是可見且有效的，而且表單必須是功能性的。 瞭解取消訂閱連結准則 [在本節中](../../designing/using/personalization.md#about-targeting-dimension).

依預設，分析訊息時，控制項 [型別規則](../../sending/using/control-rules.md) 檢查是否包含選擇退出連結，如果缺少則產生警告。

**秘訣**：由於人為錯誤永遠是可能的，在您每次傳送前，請先檢查選擇退出連結是否正確運作。 例如，傳送校樣時，請確認連結有效、表單線上上，且「不再連絡此收件者」欄位已變更為「是」。

瞭解如何插入選擇退出連結 [在本節中](../../designing/using/personalization.md#adding-a-content-block).

### 電子郵件大小 {#email-size}

為避免效能或傳遞能力問題，建議的最大電子郵件大小約為 **35KB**.

若要將您的電子郵件保持在限制之下，請考慮下列事項：

* 移除多餘或未使用的樣式

* 將部分電子郵件內容移至 [登陸頁面](../../channels/using/getting-started-with-landing-pages.md)

* 精簡您的程式碼

請務必在最終傳送前測試任何變更。

在Adobe Campaign中，電子郵件的預設大小上限設為 **100MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

如果達到限制，超過限制的訊息將會失敗，並在傳送記錄中顯示錯誤訊息。 相同傳遞的其他訊息將不會受到影響。 在這種情況下，您必須調整電子郵件範本的動態部分或傳遞使用的內容片段。 <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobe建議保留訊息大小上限預設值。 不過，此值可在 **[!UICONTROL Maximum message size]** 選項，透過 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 功能表，依據 [功能管理員](../../administration/using/users-management.md#functional-administrators) 僅限。

>[!IMPORTANT]
>
>如果您將此值設為零，則不會套用任何限制。

### 簡訊長度

根據預設，SMS 中的字元數量符合 GSM（行動通訊全球系統）標準。使用 GSM 編碼的 SMS 訊息最多只能有 160 個字元，若是以多個部分傳送的訊息，則每個 SMS 的 SMS 訊息最多只能有 153 個字元。

音譯包括當 GSM 標準未考慮到 SMS 的一個字元時，用另一個字元取代該字元。請注意，將個人化欄位插入您的SMS訊息內容，可能會引入GSM編碼未考慮的字元。 您可以核取對應方塊的SMPP管道設定索引標籤中的對應方塊，以授權字母音譯 **[!UICONTROL External account]**.
瞭解更多 [在本節中](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**提示**：

* 若要保留SMS訊息中的所有字元不變，例如不要變更正確名稱，請勿啟用音譯。

* 不過，如果您的SMS訊息包含許多GSM標準未考慮的字元，請啟用音譯以限制傳送訊息的成本。

瞭解更多 [在本節中](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### 回應式電子郵件設計

回應式設計可確保電子郵件以最佳方式呈現給開啟它的裝置。

* 使用回應式電子郵件HTML而非網頁HTML

* 使用預覽模式並傳送校樣，以儘可能在多數裝置上測試轉譯。 瞭解如何 [預覽訊息](../../sending/using/previewing-messages.md) 傳送之前。

* Campaign電子郵件設計工具隨附行動裝置的回應式設計格式化範本。 在[本頁](../../designing/using/using-reusable-content.md#content-templates)中深入瞭解。

## 管理影像 {#manage-images}

使用影像時，請遵循下列准則。

### 避免影像封鎖

有些電子郵件使用者端預設會封鎖影像，有些使用者則變更其設定以封鎖影像，以便在資料使用時進行儲存。 因此，如果未下載影像，可能會遺失整個訊息。 若要避免此情況：

* 平衡您的內容與影像和文字。 避免使用完全以影像為基礎的電子郵件。

* 如果文字必須包含在影像中，請使用替代文字和標題文字來確認訊息是否傳達。 設定替代/標題文字的樣式，以改善其外觀。

* 避免使用背景影像，因為某些電子郵件使用者端不支援這些影像。

### 讓影像回應

嘗試讓影像回應速度快且可調整大小。 請注意，這可能會對成本造成影響，因為建置時間較長。

### 使用絕對影像參照

若要從外部存取，連結至行銷活動的電子郵件和公共資源中使用的影像，必須存在於外部可存取的伺服器上。

## 預覽您的訊息 {#preview-msg}

Adobe建議預覽您的訊息，以檢查其個人化，以及收件者看到您傳遞內容的方式。

在電子郵件設計工具中， **[!UICONTROL Preview]** 按鈕可讓您檢視收件者的每個內容轉譯。 個人化欄位和內容的條件元素會取代為所選設定檔的對應資訊。 [了解更多](../../sending/using/previewing-messages.md)
