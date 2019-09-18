---
title: 關於著陸頁面內容設計
seo-title: 關於著陸頁面內容設計
description: 關於著陸頁面內容設計
seo-description: 瞭解著陸頁面內容編輯器的特定性。
page-status-flag: 從未激活
uuid: 8b230690-8a63-44da-b4ed-8e9d8fd84262
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 參考
topic-tags: 編輯——著陸——頁面——內容
discoiquuid: 212720d2-5d57-4e7a-bb72-10512050e78c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---

# 關於著陸頁面內容設計{#about-landing-page-content-design}

使用標準內容編輯器，在Adobe Campaign中建立並修改著陸頁面的內容。

本節說明著陸頁面內容編輯器的特定性：

* [著陸頁面內容編輯器介面](../../channels/using/landing-page-content-editor-interface.md)
* [管理著陸頁面結構和樣式](../../channels/using/managing-landing-page-structure-and-style.md)
* [變更著陸頁面表單資料屬性](../../channels/using/changing-a-landing-page-form-data-properties.md)

若要進一步瞭解一個或多個行銷活動常見的動作，請參閱下列章節：

* 如需個人化著陸頁面內容的詳細資訊，請 [參閱插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)[和新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)。
* 如需在著陸頁面中定義動態內容的詳細資訊，請參閱 [在著陸頁面中定義動態內容](../../channels/using/defining-dynamic-content-in-a-landing-page.md)。
* 如需在著陸頁面中插入連結的詳細資訊，請參 [閱插入連結](../../designing/using/links.md#inserting-a-link)。
* 如需在著陸頁面中插入影像的詳細資訊，請參 [閱插入影像](../../designing/using/images.md)。

另請檢查內 [容設計的一般最佳實務](../../designing/using/overview.md#content-design-best-practices)。

>[!NOTE]
>
>如果您的例項是在Adobe Campaign Standard 19.0發行之前安裝，您仍可存取舊版電子郵件內容編輯器。 著陸頁面的介面、使用原則和設定大致與下文所述相同。 但是，舊版電子郵件內容編輯器中可能無法使用或維護所有功能，此編輯器自19.0版起即不再提供。 若要透過具有擴充功能的拖放介面快速編輯您的電子郵件內容，請使用電子郵 [件設計器](../../designing/using/overview.md)。

## 著陸頁面設計最佳範例 {#landing-pages-best-practices-design}

* 編輯著陸 **頁面內容時**:

   * 在Adobe Campaign中匯入HTML頁面範本之前，請確定範本已開啟並正確顯示在各種瀏覽器中。
   * 如果HTML頁面包含JavaScript指令碼，則必須在編輯器外執行這些指令碼，而不會出現錯誤。 一般而言，請避免在訊息內容中使用指令碼，以確保電子郵件用戶端正確處理。
   * 建立範本時，建議將'type' **attribute新增至** tags。 編輯器將處理此資訊，並幫助用戶在配置Web應用程式時將資料庫欄位連結到表單欄位。
   範本中的HTML程式碼範例：

   ```
   <input id="email" type="email" name="email"/>
   ```

   「類型」屬性的正式清單可在下列位址取得： [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)