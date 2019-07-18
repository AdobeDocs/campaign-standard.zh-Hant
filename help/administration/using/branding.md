---
title: 品牌推廣
seo-title: 品牌推廣
description: 品牌推廣
seo-description: 探索所有可用來管理品牌身分的工具。
page-status-flag: 從未啓動
uuid: d66ac5a2-2ae1-4870-b48 e-7f276744 fdd
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 應用程式設定
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32fb8
context-tags: 品牌，概觀；品牌，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Branding{#branding}

## About brand identity {#about-brand-identity}

每家公司都有品牌形象和技術方針。透過Adobe Campaign，您可以定義一組規格，為客戶提供一致的品牌，從標誌到技術層面，例如電子郵件傳送者、URL或網域。

技術管理員可以定義一或數個品牌，以集中輸入影響品牌身分的參數。其中包括品牌標誌、登陸頁面存取URL的網域或訊息追蹤設定。借助Adobe Campaign，您可以建立這些品牌，並將它們連結至訊息或登陸頁面。此配置是以範本管理。

## Configuring and using brands {#configuring-and-using-brands}

設定和使用品牌的主要原則是：

1. 建立並設定品牌-此作業需要特定權限，由Adobe Campaign技術管理員執行。
1. 為此品牌建立一或數個傳送和著陸頁面範本。Refer to the [Creating a template](../../start/using/about-templates.md) section.
1. 根據此範本建立訊息和登陸頁面。Refer to the [Creating an email](../../channels/using/creating-an-email.md) and [Creating a landing page](../../channels/using/designing-a-landing-page.md) sections.

>[!CAUTION]
>
>品牌無法由使用者建立或修改：這些作業必須由Adobe Campaign技術管理員執行。如需任何要求，請聯絡Adobe客戶服務。多品牌推廣無法用於交易訊息的內容中。For more on this, see [Transactional messages and branding](../../channels/using/about-transactional-messaging.md#permissions-and-branding).

Brands can be found in the **[!UICONTROL Administration > Instance settings > Brand configuration]** menu.

根據預設，新建立的品牌只會顯示給指派給管理員之對應權限的使用者。

**品牌** 定義由下列特性定義：

* **定義**&#x200B;並個人化您品牌的身分識別。本節包含下列欄位：

   ![](assets/branding_01.png)

   * **介面** 中可見標籤
   * **品牌名稱**
   * **品牌的網站URL** 和 **網站標籤**
   * **品牌標誌**

* **[!UICONTROL Header parameters of sent emails]** 個人化促銷活動收件者所看到的內容。本節包含下列欄位：

   ![](assets/branding_04_header.png)

   * **傳送者(電子郵件地址)** 與品牌的電子郵件地址。
   * **傳送者(名稱)** 加上品牌名稱。
   * **回覆(電子郵件地址)** 與客戶可回覆的電子郵件地址。
   * **以品牌名稱回覆(名稱)** 。
   * **錯誤(電子郵件地址)** ，以用於發生錯誤的電子郵件地址。
   >[!CAUTION]
   >
   >更新電子郵件的標頭參數後，如果傳送者的名稱和電子郵件地址未在範本建立的電子郵件中變更，則會檢查範本的進階設定。

* **在網際網路上公開的伺服器** 定義用於追蹤的伺服器，以及著陸頁面存取。本節包含下列欄位：

   ![](assets/configure_branding_04.png)

   * **應用程式伺服器** 的外部URL，用於代管和存取您所建立的不同登陸頁面。
   * **追蹤伺服器** 的外部URL，作為傳送期間的追蹤URL。
   * **鏡像頁面伺服器** 的外部URL，作為傳送的預設鏡像頁面。

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**&#x200B;它定義了您品牌的URL追蹤設定。

   此處定義了允許在外部系統上追蹤連結的其他參數，例如Adobe Analytics或Google Analytics之類的Web Analytics工具。

   ![](assets/branding_05.png)

## Assigning a brand to an email {#assigning-a-brand-to-an-email}

### Linking a brand to a template {#linking-a-brand-to-a-template}

若要使用為品牌定義的參數，必須連結至傳送範本或著陸頁面範本。若要這麼做，您必須建立或編輯範本。

>[!NOTE]
>
>For more information about creating a template, refer to the [Creating a template](../../start/using/about-templates.md) section.

建立範本後，您可以將它連結至品牌。若要這麼做：

1. Click the **[!UICONTROL Edit properties]** button to access the template properties.

   ![](assets/branding_04.png)

1. 使用下拉式清單選擇您要連結至範本的品牌。

   >[!NOTE]
   >
   >By default, the **[!UICONTROL Default brand (branding)]** is selected.

   ![](assets/branding_05.png)

   To view how the brand selected is configured, click the **[!UICONTROL Navigate to the detail of the element selected]** icon.

   ![](assets/branding_06.png)

1. 確認您的選擇並儲存範本。

您的範本會連結至品牌。In the email editor, the elements such as the **Email address of default sender**, the **Default sender name**, or the **Logo** will use the configured brand data.

### Branding use case {#branding-use-case}

在此範例中，我們將建立新的旅遊相關品牌，並將它用於電子郵件中。

#### Configure a new brand {#configure-a-new-brand}

>[!CAUTION]
>
>品牌配置僅由Adobe管理，因為它需要特定權限和技術設定。

1. The Adobe Campaign administrator creates the brand in **[!UICONTROL Administration > Instance settings > Brand configuration]**. He adds the **Vacations in the Tropics** element from the advanced menu and configures the **[!UICONTROL ID]** and the **[!UICONTROL Header parameters of sent emails]** of the brand.

   ![](assets/branding_07.png)

1. The administrator then configures the URL of the **Server(s) exposed on the Internet** so that landing pages can be used, then the tracking URLs.

   In this example, the **Web Analytics** tool used is **Google Analytics**. 管理員會設定追蹤URL，如下所示：

   ![](assets/branding_12.png)

品牌已正確建立並設定。行銷團隊現在可以使用它。

#### Implement a new brand {#implement-a-new-brand}

身為發送經理，您負責建立傳送範本以使用新品牌。若要達成此目標，請遵循下列步驟：

1. In the advanced menu **[!UICONTROL Resources > Templates > Delivery templates]**, duplicate a built-in template to configure a new delivery template.

   ![](assets/branding_08.png)

1. To link this template to the **Vacations in the Tropics** brand, edit the template properties and select the brand from the drop-down list.

   ![](assets/branding_09.png)

1. 設定此電子郵件範本以反映品牌識別。
1. 範本完成後，您可以儲存它。

   ![](assets/branding_10.png)

   現在，傳送範本可以用來建立傳送給觀眾的電子郵件。

#### Use the new brand in a delivery {#use-the-new-brand-in-a-delivery}

若要建立連結至品牌的電子郵件，請遵循下列步驟：

1. Click the **[!UICONTROL Create]** button from the **[!UICONTROL Marketing activities]** menu.

   ![](assets/branding_14.png)

1. Select the **[!UICONTROL Email]** activity, then choose the template linked to the new brand.

   ![](assets/branding_15.png)

1. 您的電子郵件已設定。您可以先檢查資訊，再使用測試描述檔進行測試，然後傳送給觀眾。

   ![](assets/branding_16.png)

