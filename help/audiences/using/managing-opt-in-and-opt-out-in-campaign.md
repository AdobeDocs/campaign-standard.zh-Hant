---
title: 管理促銷活動中的選擇加入和退出
seo-title: 管理促銷活動中的選擇加入和退出
description: 管理促銷活動中的選擇加入和退出
seo-description: 瞭解選擇加入和退出如何在Adobe Campaign中進行管理。
page-status-flag: 從未啓動
uuid: aa1801ec-562b-420e-8d79-c07-c07 d0 a1 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受眾
content-type: reference
topic-tags: 瞭解選擇退出與選擇退出
discoiquuid: 6b5680f2-bba9-453e-a0 d5-8ca69 dd02001
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Managing opt-in and opt-out in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Managing opt-in and opt-out from a profile {#managing-opt-in-and-opt-out-from-a-profile}

Users can be opted in or out by an operator directly from the profile **[!UICONTROL General]** tab.

In the **[!UICONTROL No longer contact (blacklist)]** section, the selected checkboxes correspond to the channels from which the user chose to opt out. 根據使用者需求選擇渠道。

![](assets/optin_landingpage_3.png)

## Setting up opt-in and opt-out landing pages {#setting-up-opt-in-and-opt-out-landing-pages}

To give users the ability to opt in or opt out, you have to create and publish a **[!UICONTROL Profile acquisition]** landing page. 然後，他們就可以根據他們的需求選擇頻道。若要執行此動作，請遵循下列步驟。

You can also set up a **[!UICONTROL BlackList]** landing page that will enable users to opt out from all deliveries. For more on this, refer to [Setting up a landing page to opt out from all deliveries](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>著陸頁面也可以用來啓用服務訂閱。For more on this, refer to [this page](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service).

1. Create a **[!UICONTROL Profile acquisition]** landing page (see [this section](../../channels/using/about-landing-pages.md)).
1. 在每個所需頻道的著陸頁面內容中新增核取方塊，然後將其連結至促銷活動資料庫的對應欄位。

   ![](assets/optin_landingpage_1.png)

1. 儲存登陸頁面並加以發佈。
1. In the landing page, the checkboxes are already selected according to the profile **[!UICONTROL General]** tab. 使用者可以根據他的需求選擇或取消選取頻道，並提交表單。

   ![](assets/optin_landingpage_2.png)

1. Once the form submitted, the profile **[!UICONTROL General]** tab is updated according to the user's selection.

   ![](assets/optin_landingpage_3.png)

### Setting up a landing page to opt out from all deliveries {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

To give users the ability to opt out from all deliveries, you have to create and publish a **[!UICONTROL BlackList]** landing page. For more on landing pages creation, refer to [this page](../../channels/using/about-landing-pages.md).

Once a user clicks on the landing page link, the **[!UICONTROL No longer contact (by any channel)]** option in the profile is automatically selected.

![](assets/blacklisting_allchannels.png)

