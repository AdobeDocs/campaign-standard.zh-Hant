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

1. 前往 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** 並選擇 **[!UICONTROL Data mappings]** 登入點。

1. 按一下 **[!UICONTROL Create]** 以開始新的XDM對應。

   ![](assets/aep_createmapping.png)

1. 填寫必填欄位並選取：

   * a **目標維度**：這是要對應的Campaign Standard結構描述
   * a **資料集**：這是與Adobe Experience Platform中XDM結構描述相關聯的資料套件。

>[!NOTE]
>
>若要將批次擷取至即時客戶設定檔或Identity Service，資料集必須是 [已啟用即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html).
>
>如果您選取的資料集已用於現有資料對應，會出現警告以通知您資料可能會在Adobe Experience Platform上覆寫。 使用相同資料集的資料匹配中有一些常見的收件者時，可能會發生這種情況。

下列畫面會顯示 **[!UICONTROL Field mappings]** 區段，您可在其中為Campaign Standard結構描述中的每個欄位建立新的對應。

![](assets/aep_fieldmappings.png)

此 **[!UICONTROL Create new field mapping]** 按鈕可讓您選取XDM結構描述中的Campaign Standard欄位和對應的欄位路徑運算式。

如果您找不到Adobe Campaign Standard欄位，則可以使用搜尋欄位來搜尋該欄位。 目前，搜尋僅適用於階層中開啟的欄位。

![](assets/aep_mapfield.png)

Campaign Standard中定義的擴充資源會對映所有原生欄位按讚。 它們定義在XDM中的_customer/預設擴充功能中。

![](assets/aep_fieldscusmapping.png)

您可以透過API自訂XDM擴充功能，並定義您自己的擴充功能，讓您更能掌控對應。

另請參閱 [結構描述登入API教學課程](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) 以取得有關XDM API的更多詳細資料。

若要對應分項清單欄位，必須使用運算式編輯器定義與XDM值對應的每個分項清單值。 例如，postaladdressfield需要定義為：

![](assets/aep_enummapping.png)

如果XDM值定義為XDM結構描述中的分項清單，則您可以使用會自動取代的原生EXDM函式 **lif** 語法。

![](assets/aep_enummappingexdm.png)

若要編輯XDM對應，請開啟對應、修改所需資訊並儲存。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>目前，如果您編輯 **[!UICONTROL Field mappings]** 區段，然後按一下欄位外部，則在您按一下 **[!UICONTROL Save]** 按鈕。 此行為只會發生一次，當編輯 **[!UICONTROL Field Mappings]** 是頁面上的第一次編輯。
