---
title: 建立輪廓
description: 瞭解如何使用 API、匯入功能、線上贏取、自動或手動更新，建立輪廓並收集您的聯絡人資料。
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Beginner
exl-id: 827df9f6-070c-466a-890c-e363de6b129b
TQID: https://experienceleague.adobe.com/STHpDRtsdjT7OMDg3aOtVHdzqLokzOxvM2PI0ho9WLA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 395
ht-degree: 84%

---

# 建立輪廓{#creating-profiles}

在 Adobe Campaign 中，預設會使用輪廓來定義訊息的主要目標。

>[!NOTE]
>
>現在也可以使用 Adobe Campaign Standard API　建立輪廓。 如需詳細資訊，請參閱[專屬文件](../../api/using/creating-profiles-api.md)。

![](assets/do-not-localize/how-to-video.png) [探索如何使用視訊中的工作流程匯入設定檔](#video)

若要在 Campaign 中建立或更新輪廓，您可以：

* 透過[工作流程](../../automating/using/creating-import-workflow-templates.md)從檔案匯入輪廓清單
* 透過[登錄頁面](../../channels/using/getting-started-with-landing-pages.md)線上收集資料
* 透過 [REST API](../../api/using/get-started-apis.md) 大量建立
* 從 [Microsoft Dynamics](../../integrating/using/d365-acs-get-started.md) 同步輪廓
* 使用使用者介面輸入資料，如下所述

例如，若要直接在使用者介面中建立新的輪廓，請遵循下列步驟：

1. 從 Adobe Campaign 首頁，按一下 **Customer Profiles** 資訊卡或 **Profiles** 索引標籤以存取設定檔清單。

   ![](assets/profile_creation_1.png)

1. 按一下 **[!UICONTROL Create]**。

   ![](assets/profile_creation.png)

1. 輸入輪廓資料。

   ![](assets/profile_creation1.png)

   * 聯絡資訊，例如名字、姓氏、性別、出生日期、相片、首選語言（適用於[多語言電子郵件](../../channels/using/creating-a-multilingual-email.md)），有助於更妥善地進行個人化傳送。
   * 輪廓的 **[!UICONTROL Time zone]** 會用於在輪廓的時區進行傳送。 如需詳細資訊，請參閱[本區段](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)。
   * **[!UICONTROL Channels]** 類別包含電子郵件地址、行動電話號碼、選取退出資訊，讓您知道可透過哪個通道存取輪廓。

     >[!NOTE]
     > 在設定檔表格中，行動電話號碼必須一律為國際格式(`+<country><number>`)格式。

   * 輪廓取消訂閱通道之後，就會更新　**[!UICONTROL No longer contact]**　類別。
   * **[!UICONTROL Address]** 類別包含需要填寫的郵遞區號，以及需要將[直接郵件](../../channels/using/about-direct-mail.md)傳送給此輪廓的　**[!UICONTROL Address specified]**　選項。 如果未核取 **[!UICONTROL Address specified]** 選項，則會將此輪廓從每個直接郵件發送中排除。
   * **[!UICONTROL Access authorization]**&#x200B;類別指出設定檔的組織單位，以[管理許可權](../../administration/using/about-access-management.md)。 若要將組織欄位新增至您的輪廓，請參閱[分割輪廓](../../administration/using/organizational-units.md#partitioning-profiles)區段。
   * **[!UICONTROL Traceability]** 類別會使用關於建立或修改輪廓的使用者來自動更新。

1. 按一下 **[!UICONTROL Create]** 以儲存輪廓。

輪廓現在會顯示在清單中。

>[!NOTE]
>首選語言欄位的作用是在傳送多語言訊息時選取語言。 如需關於多語言訊息的詳細資訊，[請參閱本頁](../../channels/using/creating-a-multilingual-email.md)。

## 教學課程影片 {#video}

本影片說明如何使用工作流程匯入設定檔。

>[!VIDEO](https://video.tv.adobe.com/v/24993?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)提供其他Campaign Standard操作說明影片。
