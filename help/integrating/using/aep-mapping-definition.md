---
title: 對應定義
description: 瞭解如何使用Experience Data Model (XDM)欄位對應Campaign Standard欄位。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# 對應定義 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前為測試版，可能會經常更新，恕不另行通知。 客戶需在Azure上代管（目前僅限北美地區使用Beta版）才能存取這些功能。 如果您想要存取許可權，請聯絡Adobe客戶服務。

在本節中，您將瞭解如何使用Experience Data Model (XDM)欄位對應Campaign Standard欄位。

若要執行此工作，先決條件為：

* 透過介面或使用與XDM相關聯的REST API來定義XDM結構描述
* 根據XDM結構描述定義建立資料集

1. 前往「**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]**」並選擇&#x200B;**[!UICONTROL Data mappings]**&#x200B;專案。

1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;以開始新的XDM對應。

   ![](assets/aep_createmapping.png)

1. 填寫必填欄位並選取：

   * **目標維度**：這是要對應的Campaign Standard結構描述
   * **資料集**：這是與Adobe Experience Platform中的XDM結構描述相關聯的資料包。

>[!NOTE]
>
>若要將批次擷取至即時客戶設定檔或身分識別服務，資料集必須針對即時客戶設定檔[&#128279;](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html?lang=zh-Hant)啟用。
>
>如果您選取的資料集已用於現有資料對應，會出現警告以通知您資料可能會在Adobe Experience Platform上覆寫。 使用相同資料集的資料匹配中有一些常見的收件者時，可能會發生這種情況。

下列畫面會顯示&#x200B;**[!UICONTROL Field mappings]**&#x200B;區段，您可在其中為Campaign Standard結構描述中的每個欄位建立新的對應。

![](assets/aep_fieldmappings.png)

**[!UICONTROL Create new field mapping]**&#x200B;按鈕可讓您選取XDM結構描述中的Campaign Standard欄位和對應的欄位路徑運算式。

如果您找不到Adobe Campaign Standard欄位，則可以使用搜尋欄位來搜尋該欄位。 目前，搜尋僅適用於階層中開啟的欄位。

![](assets/aep_mapfield.png)

Campaign Standard中定義的擴充資源會對映所有原生欄位按讚。 它們定義在XDM中的_customer/預設擴充功能中。

![](assets/aep_fieldscusmapping.png)

您可以透過API自訂XDM擴充功能，並定義您自己的擴充功能，讓您更能掌控對應。

如需XDM API的詳細資訊，請參閱[結構描述登入API教學課程](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=zh-Hant)。

若要對應分項清單欄位，必須使用運算式編輯器定義與XDM值對應的每個分項清單值。 例如，postaladdressfield需要定義為：

![](assets/aep_enummapping.png)

如果XDM值定義為XDM結構描述中的分項清單，您可以使用會自動取代&#x200B;**lif**&#x200B;語法的原生EXDM函式。

![](assets/aep_enummappingexdm.png)

若要編輯XDM對應，請開啟對應、修改所需資訊並儲存。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>目前，如果您在&#x200B;**[!UICONTROL Field mappings]**&#x200B;區段中編輯值，然後按一下欄位外部，則在您按一下&#x200B;**[!UICONTROL Save]**&#x200B;按鈕之前，您的變更不會顯示在介面中。 當&#x200B;**[!UICONTROL Field Mappings]**&#x200B;上的編輯是頁面上的第一次編輯時，此行為只會發生一次。
