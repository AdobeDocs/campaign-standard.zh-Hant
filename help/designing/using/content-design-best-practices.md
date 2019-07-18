---
title: 內容設計最佳實務
seo-title: 內容設計最佳實務
description: 內容設計最佳實務
seo-description: 閱讀這些指引以確保編輯器的最佳運作。
page-status-flag: 從未啓動
uuid: ad74f49d-999f-4140-89b0-d1 ead8642 d89
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: 內容設計
discoiquuid: d33f5f14-a4 e3-4327-bd16-eb3135 a32076
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Content design best practices{#content-design-best-practices}

為確保編輯器的最佳運作，建議您遵守下列准則：

* 不支援SCSS樣式表。如果您匯入包含HTML內容的ZIP檔案，請使用一般CSS。
* When editing **email content**:

   請先預覽您的訊息，然後再傳送。Adobe Campaign提供使用Litmbus測試電子郵件演算的方式。For more on this, see [Email rendering](../../sending/using/email-rendering.md).

* When editing **landing page content**:

   * 在Adobe Campaign中匯入HTML頁面範本之前，請確定範本開啓並在各種瀏覽器中正確顯示。
   * 如果HTML頁面包含JavaScript指令碼，則需要執行，而不會出現在編輯器以外的錯誤。一般來說，避免使用訊息內容中的指令碼來確保電子郵件用戶端正確處理。
   * When building a template, we recommend adding a **'type'** attribute to  tags. 此資訊將由編輯器處理，並協助使用者在設定Web應用程式時，將資料庫欄位連結至表單欄位。

      範本中HTML程式碼範例：

      ```
      <input id="email" type="email" name="email"/>
      ```

      The official list of 'type' attributes is available at the following address: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)

More design and general best practices regarding messages are presented in the following Adobe Campaign step-by-step guide: [Delivery best practices with Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).
