---
title: 對應定義
description: 了解如何使用Experience Data Model(XDM)欄位對應Campaign Standard欄位。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# 對應定義 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上托管（目前測試版僅供北美使用），才能存取這些功能。 如果您想要存取權限，請聯絡Adobe客戶服務。

在本節中，您將探索如何將Campaign Standard欄位與體驗資料模型(XDM)欄位對應。

要執行此任務，必要條件是：

* 透過介面或使用與XDM相關聯的REST API來定義XDM結構
* 根據XDM架構定義建立資料集

1. 前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]**&#x200B;並選擇&#x200B;**[!UICONTROL Data mappings]**&#x200B;項目。

1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;以啟動新的XDM對應。

   ![](assets/aep_createmapping.png)

1. 填寫必填欄位並選取：

   * a **目標維度**&#x200B;這是要映射的Campaign Standard結構
   * a **dataset**:這是與Adobe Experience Platform中XDM架構相關聯的資料套件。

>[!NOTE]
>
>若要將批次擷取至即時客戶設定檔或Identity Service，資料集必須為[啟用即時客戶設定檔](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html)。
>
>如果您選取的資料集已用於現有資料對應，系統會顯示警告，通知您的資料可能會在Adobe Experience Platform上覆寫。 使用相同資料集的資料綁架中有某些常見收件者時，即會發生此情況。

以下螢幕顯示&#x200B;**[!UICONTROL Field mappings]**&#x200B;區段，您可在此為Campaign Standard架構中的每個欄位建立新對應。

![](assets/aep_fieldmappings.png)

**[!UICONTROL Create new field mapping]**&#x200B;按鈕可讓您選取XDM架構中的Campaign Standard欄位及對應的欄位路徑運算式。

如果您找不到Adobe Campaign Standard欄位，可以使用搜尋欄位來搜尋欄位。 目前，搜尋只適用於階層中開啟的欄位。

![](assets/aep_mapfield.png)

Campaign Standard中定義的擴充資源會對應至所有原生欄位。 這些範本定義在XDM的_customer/default擴充功能中。

![](assets/aep_fieldscusmapping.png)

您可以透過API自訂XDM擴充功能，並定義自己的擴充功能，以更妥善地控制對應。

如需XDM API的詳細資訊，請參閱[結構註冊表API教學課程](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)。

若要對應分項清單欄位，您需要使用運算式編輯器來定義與XDM值對應的每個分項清單值。 例如，後置定址欄位需定義為：

![](assets/aep_enummapping.png)

如果XDM值在XDM架構中定義為分項清單，您可以使用原生EXDM函式，自動取代&#x200B;**lif**&#x200B;語法。

![](assets/aep_enummappingexdm.png)

若要編輯XDM對應，請開啟該對應，修改所需資訊，然後儲存。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>目前，如果您編輯&#x200B;**[!UICONTROL Field mappings]**&#x200B;區段中的值，然後按一下欄位外部，在您按一下&#x200B;**[!UICONTROL Save]**&#x200B;按鈕之前，介面中不會顯示您的變更。 當&#x200B;**[!UICONTROL Field Mappings]**&#x200B;上的編輯是頁面上的第一個編輯時，此行為僅發生一次。
