---
title: 建立描述檔
seo-title: 建立描述檔
description: 建立描述檔
seo-description: 瞭解如何使用API、匯入功能、線上採購、自動或手動更新，建立個人檔案並收集資料。
page-status-flag: 從未啓動
uuid: a5f5a58a-e798-400f-8648-05dc843 d5557
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 受眾
content-type: reference
topic-tags: 管理描述檔
discoiquuid: 4ab8a984-f898-4fff-ad8 c-ed8 f95362 f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f883986392f6b739832093e0473591aa39dfcbfe

---


# Creating profiles{#creating-profiles}

在Adobe Campaign中，預設會使用描述檔來定義訊息的主要目標。

若要在Campaign中建立或更新描述檔，您可以：

* Import a profile list from a file, via a [workflow](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)
* Collect data online, via [landing pages](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_CreateLandingPage.html)
* [透過REST API大量建立](http://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)
* Synchronize profiles from [Microsoft Dynamics](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* 使用圖形介面畫面輸入資料，如下所述

例如，若要直接在使用者介面中建立新的設定檔，請遵循下列步驟：

1. From the Adobe Campaign home page, click the **Customer Profiles** card or the **Profiles** tab to access the list of profiles.

   ![](assets/profile_creation_1.png)

1. **[!UICONTROL Create]**&#x200B;然後按一下。

   ![](assets/profile_creation.png)

1. 輸入描述檔資料。

   ![](assets/profile_creation1.png)

   * The contact information, such as first name, last name, gender, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)) helps better personalize deliveries.
   * The profile's **[!UICONTROL Time zone]** is used to send deliveries at the profile's time zone. For more on this, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * **[!UICONTROL Channels]** 此類別包含電子郵件地址、行動電話號碼、選擇退出資訊，可讓您瞭解設定檔易如反掌的管道。
   * The **[!UICONTROL No longer contact]** category is updated as soon as the profile unsubscribe to a channel.
   * **[!UICONTROL Address]** 類別包含需要填寫的郵寄地址， **[!UICONTROL Address specified]** 以及傳送 [直接郵件](../../channels/using/about-direct-mail.md) 至此描述檔的選項。If the **[!UICONTROL Address specified]** option is not checked, this profile will be excluded from every direct mail delivery.
   * **[!UICONTROL Access authorization]** 類別會指出描述檔的組織單位( [以管理權限](../../administration/using/about-access-management.md))。See also [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles).
   * **[!UICONTROL Traceability]** 類別會自動更新，其中包含建立或修改描述檔的使用者相關資訊。

1. Click **[!UICONTROL Create]** to save the profile.

描述檔現在會出現在清單中。

>[!NOTE]
>
>您也可以使用Adobe Campaign Standard API建立描述檔建立。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#creating-profiles) .

個人檔案也可以依據組織單位進行劃分。To add the organizational fields to your profiles, refer to the [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles) section.

>[!NOTE]
>
>偏好語言欄位是用來在傳送多語言訊息時選取語言。For more information about the multilingual messages [refer to this page](../../channels/using/creating-a-multilingual-email.md).

**相關主題：**

* [建立著陸頁面](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_CreateLandingPage.html) 逐步指南
* [匯入描述檔](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

