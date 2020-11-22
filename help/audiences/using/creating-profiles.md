---
solution: Campaign Standard
product: campaign
title: 建立設定檔
description: 瞭解如何使用 API、匯入功能、線上贏取、自動或手動更新，建立個人檔案並收集您的聯絡人資料。
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 97%

---


# 建立設定檔{#creating-profiles}

在 Adobe Campaign 中，預設會使用設定檔來定義訊息的主要目標。

>[!NOTE]
>
>現在也可以使用 Adobe Campaign Standard API　建立設定檔。如需詳細資訊，請參閱[專屬文件](../../api/using/creating-profiles.md)。

若要在 Campaign 中建立或更新設定檔，您可以：

* 透過[工作流程](../../automating/using/creating-import-workflow-templates.md)從檔案匯入設定檔清單
* 透過[登錄頁面](../../channels/using/getting-started-with-landing-pages.md)線上收集資料
* 透過 [REST API](../../api/using/get-started-apis.md) 大量建立
* 從 [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) 同步設定檔
* 使用圖形化介面畫面輸入資料，如下所述

例如，若要直接在使用者介面中建立新的設定檔，請遵循下列步驟：

1. 從 Adobe Campaign 首頁，按一下 **Customer Profiles** 資訊卡或 **Profiles** 索引標籤以存取設定檔清單。

   ![](assets/profile_creation_1.png)

1. 按一下 **[!UICONTROL Create]**。

   ![](assets/profile_creation.png)

1. 輸入設定檔資料。

   ![](assets/profile_creation1.png)

   * 聯絡資訊，例如名字、姓氏、性別、出生日期、相片、首選語言（適用於[多語言電子郵件](../../channels/using/creating-a-multilingual-email.md)），有助於更妥善地進行個人化傳送。
   * 設定檔的 **[!UICONTROL Time zone]** 會用於在設定檔的時區進行傳送。如需詳細資訊，請參閱[本區段](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)。
   * **[!UICONTROL Channels]** 類別包含電子郵件地址、行動電話號碼、選取退出資訊，讓您知道可透過哪個通道存取設定檔。
   * 設定檔取消訂閱通道之後，就會更新　**[!UICONTROL No longer contact]**　類別。
   * **[!UICONTROL Address]** 類別包含需要填寫的郵遞區號，以及需要將[直接郵件](../../channels/using/about-direct-mail.md)傳送給此設定檔的　**[!UICONTROL Address specified]**　選項。如果未核取 **[!UICONTROL Address specified]** 選項，則會將此設定檔從每個直接郵件發送中排除。
   * The **[!UICONTROL Access authorization]** category indicates the profile&#39;s organizational units to [manage permissions](../../administration/using/about-access-management.md). 若要將組織欄位新增至您的設定檔，請參閱[分割設定檔](../../administration/using/organizational-units.md#partitioning-profiles)區段。
   * **[!UICONTROL Traceability]** 類別會使用關於建立或修改設定檔的使用者來自動更新。

1. 按一下 **[!UICONTROL Create]** 以儲存設定檔。

設定檔現在會顯示在清單中。

>[!NOTE]
>首選語言欄位的作用是在傳送多語言訊息時選取語言。如需關於多語言訊息的詳細資訊，[請參閱本頁](../../channels/using/creating-a-multilingual-email.md)。

**相關主題：**

* [關於登錄頁面](../../channels/using/getting-started-with-landing-pages.md)
* [匯入設定檔](https://video.tv.adobe.com/v/24993?captions=chi_hant)影片
