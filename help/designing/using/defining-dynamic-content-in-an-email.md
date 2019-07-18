---
title: 在電子郵件中定義動態內容
seo-title: 在電子郵件中定義動態內容
description: 在電子郵件中定義動態內容
seo-description: 依照下列步驟，根據透過Adobe Campaign運算式編輯器定義的條件，動態顯示電子郵件中的不同內容。
page-status-flag: 從未啓動
uuid: b1c5013f-3201-4239-8202-511a6902d604
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: d0d009a5-6022-433e-acdf-2b51 a233 a5 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining dynamic content in an email{#defining-dynamic-content-in-an-email}

在電子郵件中，您可以定義不同的內容，根據透過運算式編輯器定義的條件動態顯示給收件者。例如，從相同的電子郵件，您可以確保每個描述檔根據年齡範圍接收不同的訊息。

Defining dynamic content is different from [defining visibility conditions](../../designing/using/defining-a-visibility-condition.md).

1. 選取片段、元件或元素。在此範例中，選取影像。
1. Click the **[!UICONTROL Dynamic content]** icon from the contextual toolbar.

   ![](assets/dynamic_content_2.png)

   **[!UICONTROL Dynamic content]** 區段會顯示在左側的浮動視窗中。

   ![](assets/dynamic_content_3.png)

   依預設，本節包含兩個元素：預設變體和新變體。

   >[!NOTE]
   >
   >內容必須一律具有預設變體。您無法刪除它。

1. Click the **[!UICONTROL Edit]** button to define the display conditions for the first alternative variant.

   ![](assets/dynamic_content_4.png)

1. 指定標籤並選取您要設定為條件的欄位。For example, from the **[!UICONTROL General]** node, select the **[!UICONTROL Age]** field

   ![](assets/dynamic_content_5.png)

1. 設定篩選條件。例如，您想要向年齡介於18到25歲的人顯示不同的內容。

   ![](assets/dynamic_content_6.png)

1. 設定所有條件後，定義將套用條件的優先順序順序，並儲存您的變更。

   ![](assets/dynamic_content_7.png)

   內容會依優先順序顯示在浮動視窗中，由上到下排列。For more on priorities, refer to [this section](../../designing/using/defining-dynamic-content-in-an-email.md#order-of-priority).

1. 上傳剛定義的變體的影像。

   ![](assets/dynamic_content_8.png)

   年齡介於18到25歲的收件者會看到新影像。

   ![](assets/dynamic_content_10.png)

1. Click **[!UICONTROL Add a condition]** to add a new content and its linked rule.

   ![](assets/dynamic_content_9.png)

   例如，您可以新增不同影像給年齡介於26到35歲的人。

1. 對於您想要動態顯示的電子郵件中任何其他元素，繼續執行相同的動作。可以是文字、按鈕、分割等。儲存變更。

>[!CAUTION]
>
>準備好訊息後再傳送，請使用校樣進行測試。如果您未執行此動作，可能無法偵測到某些錯誤，而電子郵件可能無法傳送。

**相關主題：**

* [傳送校樣](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)
* [進階運算式編輯](../../automating/using/editing-queries.md#about-query-editor)

## Order of priority {#order-of-priority}

在運算式編輯器中，定義動態內容時，優先順序順序如下。

1. You define two different dynamic contents with **two different conditions**, for example:

   **條件1：** 描述檔的性別是馬術、

   **條件2：** 描述檔在20到30歲之間。

   ![](assets/delivery_content_61.png)

   資料庫中的某些描述檔對應至兩個條件，但只能傳送一個具有動態內容的電子郵件。

1. 因此，您必須定義動態內容的優先順序。A condition with an order of priority of **1** (and therefore the corresponding dynamic content) will be sent to a profile even if another condition whose priority order is **2** or **3** is also met by this profile.

   ![](assets/delivery_content_62.png)

每個動態內容只能定義一個優先順序。
