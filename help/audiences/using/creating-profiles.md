---
title: 建立設定檔
description: 瞭解如何使用API、匯入功能、線上贏取、自動或手動更新，建立個人檔案並收集您的連絡人資料。
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7bf000a9191a73664b88f78cadff57d97a820af

---


# 建立設定檔{#creating-profiles}

在Adobe Campaign中，預設會使用描述檔來定義訊息的主要目標。

若要在Campaign中建立或更新描述檔，您可以：

* 透過工作流程從檔案匯入描述檔清 [單](../../automating/using/importing-data.md#example--import-workflow-template)
* 透過登陸頁麵線上收 [集資料](../../channels/using/getting-started-with-landing-pages.md)
* 透過 [REST API大量建立](../../api/using/about-campaign-standard-apis.md)
* 從 [Microsoft Dynamics同步描述檔](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* 使用圖形介面畫面輸入資料，如下所述

例如，若要直接在使用者介面中建立新的描述檔，請遵循下列步驟：

1. 從Adobe Campaign首頁，按一下「客戶 **描述檔** 」卡或「 **Profiles** 」標籤以存取描述檔清單。

   ![](assets/profile_creation_1.png)

1. 然後按一 **[!UICONTROL Create]**下。

   ![](assets/profile_creation.png)

1. 輸入描述檔資料。

   ![](assets/profile_creation1.png)

   * 聯絡資訊，例如名字、姓氏、性別、出生日期、像片、慣用語言(適用於多語系電子郵 [件](../../channels/using/creating-a-multilingual-email.md))，有助於更個人化傳遞。
   * 描述檔的 **[!UICONTROL Time zone]**用來在描述檔的時區傳送傳送。 For more on this, refer to this[section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * 此類 **[!UICONTROL Channels]**別包含電子郵件地址、行動電話號碼、選擇退出資訊，讓您知道可以透過哪個頻道存取描述檔。
   * 一 **[!UICONTROL No longer contact]**旦設定檔取消訂閱頻道，類別就會更新。
   * 類 **[!UICONTROL Address]**別包含需要填寫的郵遞區號，以及傳送**[!UICONTROL Address specified]** 直效郵 [件至此設定檔](../../channels/using/about-direct-mail.md) 。 如果未選 **[!UICONTROL Address specified]**中該選項，則此配置檔案將從每個直接郵件發送中排除。
   * 類別 **[!UICONTROL Access authorization]**會指出描述檔的組織單位(以管[理權限](../../administration/using/about-access-management.md))。 另請參見[Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles)。
   * 類別 **[!UICONTROL Traceability]**會自動更新，內含建立或修改描述檔之使用者的相關資訊。

1. 按一 **[!UICONTROL Create]**下以儲存描述檔。

描述檔現在會出現在清單中。

>[!NOTE]
>
>您也可以使用Adobe Campaign Standard API建立設定檔。 如需詳細資訊，請參閱專用 [檔案](../../api/using/creating-profiles.md)。

配置檔案也可以根據其組織單位進行分區。 要將組織欄位添加到配置檔案中，請參閱「分 [區配置檔案](../../administration/using/organizational-units.md#partitioning-profiles) 」部分。

>[!NOTE]
>
>首選語言欄位用於在發送多語言消息時選擇語言。 有關多語言消息的詳細信 [息，請參閱本頁](../../channels/using/creating-a-multilingual-email.md)。

**相關主題：**

* [關於著陸頁面](../../channels/using/getting-started-with-landing-pages.md) -逐步指南
* [匯入描述檔](https://video.tv.adobe.com/v/24993?captions=chi_hant) ：視訊
