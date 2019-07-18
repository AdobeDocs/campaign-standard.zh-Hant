---
title: 「範例：電子郵件個人化」
seo-title: 「範例：電子郵件個人化」
description: 「範例：電子郵件個人化」
seo-description: 檢視以動態內容和文字根據個人檔案年齡個人化電子郵件的完整範例。
page-status-flag: 從未啓動
uuid: 3d30213c-474f-4e5f-8688-9260ea2e2583
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: 個人化內容
discoiquuid: d1b618ac-a842-41e8-9ba6-7a50 f7315 b02
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Example: Email personalization{#example-email-personalization}

在此範例中，行銷服務團隊的成員已建立電子郵件，通知他的部分客戶特別優惠。團隊成員決定根據客戶的年齡個人化電子郵件。年齡介於18歲到27歲的客戶會收到包含不同影像和口號的電子郵件，其中包含27歲以上的客戶。

電子郵件的建立方式如下：

* 動態內容會套用至影像，而這些動態內容會根據年齡範圍設定。

   ![](assets/delivery_content_43.png)

   Adding and configuring dynamic content is detailed in the [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md) section.

* 個人化欄位和動態內容會套用至文字。根據描述檔的年齡範圍，電子郵件會以描述檔的名字或描述檔的標題和姓氏開始。

   ![](assets/delivery_content_44.png)

   Adding and configuring the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

## Configuring images {#configuring-images}

在此範例中，套用至影像的動態內容設定如下：

**若要定位18-27歲：**

1. Select the dynamic content in the **[!UICONTROL Properties]** palette and click the **[!UICONTROL Edit]** button.

   ![](assets/delivery_content_48.png)

1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.

   ![](assets/delivery_content_49.png)

1. Select the **Greater than or equal to** operator then enter **18** to create the **older than 18** expression.

   ![](assets/delivery_content_50.png)

1. Add a new **[!UICONTROL Age]** condition.

   Select the **Less than or equal to** operator followed by 27 in the value field to create the **younger than 27** expression.

   ![](assets/delivery_content_51.png)

1. 確認您的變更。

**若要定位27歲以上的個人檔案：**

1. 從浮動視窗中選取動態內容並加以編輯。
1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.
1. Add the **Greater than** operator followed by 27 in the value field to create the **older than 27** expression.

   ![](assets/delivery_content_52.png)

1. 確認您的變更。

您的動態內容已正確設定。

## Configuring text {#configuring-text}

在此範例中，套用至文字的動態內容設定如下：

**若要定位18-27之間的設定檔：**

1. 選取您想要的結構元件，並新增動態內容。
1. 編輯動態內容並設定定位運算式。Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. In the list that appears, select the **[!UICONTROL First name]** field and confirm.

   ![](assets/delivery_content_54.png)

1. 然後您的個人化欄位就會完美插入選取的動態內容中。

**若要定位27歲以上的個人檔案：**

1. 選取您想要的結構元件，並新增動態內容。
1. 編輯動態內容並設定定位運算式。Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.
1. **[!UICONTROL Title]** 從下拉式清單中選取。
1. Proceed similarly to add the **[!UICONTROL Last name]** field.

   ![](assets/delivery_content_56.png)

您的個人化欄位現在應完美插入選擇的動態內容中。

## Previewing emails {#previewing-emails}

Previewing allows you to check that the personalization fields and the dynamic contents are configured correctly before sending the **[!UICONTROL Proofs]**. 在預覽期間，您可以選取對應於電子郵件目標的不同測試設定檔。

沒有測試設定檔，預設出現的電子郵件為：

![](assets/delivery_content_45.png)

電子郵件在口號中沒有個人化欄位，且使用預設影像。

第一個測試設定檔對應至介於18到27之間的用戶端。選取此設定檔後，會顯示下列電子郵件：

![](assets/delivery_content_46.png)

對應至18-27歲運算式的個人化欄位(尤其是描述檔的名字)已正確設定，且影像也會根據描述檔變更。

第二個描述檔對應至超過27歲的用戶端，並產生下列電子郵件：

![](assets/delivery_content_47.png)

隨著動態內容的出現，影像已改變，而出現的口號則是針對此目標的較正式口號。

**相關主題：**

* [建立觀眾](../../audiences/using/creating-audiences.md)
* [準備傳送](../../sending/using/preparing-the-send.md)

