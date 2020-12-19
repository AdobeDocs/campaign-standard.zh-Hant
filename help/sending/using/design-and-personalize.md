---
solution: Campaign Standard
product: campaign
title: 建置個人化內容
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 7%

---


# 建置個人化內容 {#build-personalized-content}

在設計訊息內容時，請盡量避免可能導致您無法執行傳送的常見問題。 大多數情況下，可能的錯誤與[個人化](../../designing/using/personalization.md)、使用現有內容](../../designing/using/using-existing-content.md) —— 和[轉換HTML內容](../../designing/using/using-existing-content.md#converting-an-html-content) —— 和[影像](../../designing/using/images.md)時的格式相關。[

## 最佳化個人化{#optimize-personalization}

為避免常見問題，避免您無法執行傳送作業，並改善收件者的體驗，Adobe Campaign可讓您個人化您的訊息。

您可以使用儲存在Adobe Campaign資料庫中或透過追蹤、登陸頁面、訂閱等方式收集的收件者資料。
個人化基本資訊會顯示在[本節](../../designing/using/personalization.md)中。

請確定您的訊息內容已正確設計，以避免任何通常與個人化相關的錯誤。

您可以手動新增動態內容，根據運算式編輯器中定義的條件，向收件者顯示不同的內容。 新增動態內容時，您必須永遠為不符合選取條件的收件者保留預設變數。
有關動態內容的更多資訊，請參閱[本節](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

**提示** -使用不同的測試設定檔預覽您的電子郵件，以確定您的動態內容已正確設定。

## 建立最佳化內容{#optimize-content}

在建立電子郵件時，請牢記以下一般最佳實務。

* 讓設計更簡單

* 讓行動使用者注意

* 避免完全以影像為基礎的電子郵件

* 使用電子郵件安全字型

* 編碼特殊字元

### 主旨行

在[主旨行](../../designing/using/subject-line.md)上工作，以改善開放率：

* 避免主題過長。 最多使用50個字元

* 避免重複使用「免費」或「選件」等可視為垃圾訊息的字詞

* 避免使用大寫字母和特殊字元，例如&quot;!&quot;、&quot;£&quot;、&quot;€&quot;、&quot;$&quot;

### 鏡像頁

一律包含鏡像頁面連結。 首選位置是電子郵件的頂端。 [進一步瞭解](../../designing/using/personalization.md#adding-a-content-block)

### 取消訂閱連結

取消訂閱連結是必備的。 它必須可見且有效，而且表單必須正常運作。 瞭解本節](../../designing/using/personalization.md#about-targeting-dimension)中的取消訂閱連結方針[。

依預設，在分析訊息時，控制項[排版規則](../../sending/using/control-rules.md)會檢查是否已包含選擇退出連結，並在遺失時產生警告。

**提示**:由於人為錯誤總是可能發生，因此每次傳送前請先檢查退出連結是否正常運作。例如，傳送證明時，請確定連結有效、表單是線上的，以及「不再與此收件者聯絡」欄位已變更為「是」。

瞭解如何在本節](../../designing/using/personalization.md#adding-a-content-block)中插入退出連結[。

### 電子郵件大小

為避免效能或傳遞性問題，建議的電子郵件大小上限為&#x200B;**35KB**。

若要限制您的電子郵件，請考慮下列事項：

* 移除多餘或未使用的樣式

* 將部分電子郵件內容移至登陸頁面

* 精簡您的程式碼

請務必在最終傳送前測試任何變更

### SMS長度

根據預設，SMS 中的字元數量符合 GSM（行動通訊全球系統）標準。使用 GSM 編碼的 SMS 訊息最多只能有 160 個字元，若是以多個部分傳送的訊息，則每個 SMS 的 SMS 訊息最多只能有 153 個字元。

音譯包括當 GSM 標準未考慮到 SMS 的一個字元時，用另一個字元取代該字元。請注意，將個人化欄位插入SMS訊息的內容可能會引入GSM編碼未考慮的字元。 您可以通過選中相應&#x200B;**[!UICONTROL External account]**的SMPP通道設定頁籤中的相應框來授權字元音譯。
瞭解本節](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)的更多資訊。[

**提示**:

* 若要保留SMS訊息中所有字元的原樣，請勿變更正確的名稱，例如，請勿啟用音譯。

* 不過，如果您的SMS訊息包含許多未經GSM標準考量的字元，則可讓音譯功能限制傳送訊息的成本。

瞭解本節](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)的更多資訊。[

### 互動式電子郵件設計

互動式設計可確保電子郵件能夠針對開啟裝置以最佳方式呈現。

* 使用互動式電子郵件HTML，而非網頁HTML

* 使用預覽模式並傳送校樣，以盡可能多的裝置來測試演算。 瞭解如何在傳送前預覽訊息](../../sending/using/previewing-messages.md)。[

* Campaign電子郵件設計工具隨附適用於行動裝置的互動式設計格式範本。 在本頁瞭解更多[的資訊。](../../designing/using/using-reusable-content.md#content-templates)

## 管理影像{#manage-images}

使用影像時，請遵循以下准則。

### 防止影像封鎖

有些電子郵件用戶端依預設會封鎖影像，而有些使用者會變更其設定來封鎖影像，以儲存資料使用情況。 因此，如果不下載影像，則會丟失整個消息。 若要避免此情況：

* 在內容與影像和文字之間取得平衡。 避免完全以影像為基礎的電子郵件。

* 如果文字必須包含在影像中，請使用alt和title文字，以確保訊息傳達完畢。 設定替代／標題文字的樣式以改善其外觀。

* 避免使用背景影像，因為有些電子郵件客戶不支援這些影像。

### 讓影像互動

嘗試讓影像回應速度快且可調整大小。 請注意，由於建置時間較長，這可能會造成成本影響。

### 使用絕對影像參照

若要從外部存取，連結至促銷活動的電子郵件和公共資源中使用的影像必須存在於外部存取的伺服器上。

## 預覽您的訊息{#preview-msg}

Adobe建議預覽您的訊息，以檢查其個人化，以及收件者如何看到您的傳送。

在「電子郵件設計器」中，**[!UICONTROL Preview]**&#x200B;按鈕可讓您檢視收件者的每個內容的轉換。 個性化欄位和內容的條件元素被所選配置檔案的相應資訊替換。 [進一步瞭解](../../sending/using/previewing-messages.md)
