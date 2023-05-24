---
title: 對應定義
description: 瞭解如何使用「體驗資料模型」(XDM)欄位映射Campaign Standard欄位。
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
>Adobe Experience Platform資料連接器目前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

在本節中，您將瞭解如何使用「體驗資料模型」(XDM)欄位映射Campaign Standard欄位。

要執行此任務，必備條件包括：

* 通過介面或使用與XDM關聯的REST API定義XDM架構
* 基於XDM模式定義的資料集建立

1. 轉到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** 選擇 **[!UICONTROL Data mappings]** 的子菜單。

1. 按一下 **[!UICONTROL Create]** 啟動新XDM映射。

   ![](assets/aep_createmapping.png)

1. 填寫必需欄位並選擇：

   * a **目標維**:這是要映射的Campaign Standard架構
   * a **資料集**:這是與Adobe Experience Platform的XDM架構關聯的資料包。

>[!NOTE]
>
>若要將批次接收到即時客戶配置檔案或身份服務，必須將資料集 [為即時客戶配置檔案啟用](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html)。
>
>如果您選擇的資料集已在現有資料映射中使用，則會出現一則警告，通知您您的資料可能會在Adobe Experience Platform被覆蓋。 當使用同一資料集的資料綁架中存在一些常見收件人時，可能會發生這種情況。

以下螢幕顯示 **[!UICONTROL Field mappings]** 部分，您可以在其中為Campaign Standard架構中的每個欄位建立新映射。

![](assets/aep_fieldmappings.png)

的 **[!UICONTROL Create new field mapping]** 按鈕，您可以在XDM架構中選擇Campaign Standard欄位和相應的欄位路徑表達式。

如果找不到Adobe Campaign Standard欄位，則可以使用搜索欄位搜索該欄位。 當前，搜索僅適用於在層次結構中開啟的欄位。

![](assets/aep_mapfield.png)

Campaign Standard中定義的擴展資源被映射為所有本機欄位。 它們定義到XDM的_customer/default擴展中。

![](assets/aep_fieldscusmapping.png)

您可以通過API自定義XDM擴展，並定義自己的擴展，以便更好地控制映射。

請參閱 [架構註冊表API教程](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) 的子菜單。

要映射枚舉欄位，需要使用表達式編輯器定義與XDM值對應的每個枚舉值。 例如，後處理地址場需要定義為：

![](assets/aep_enummapping.png)

如果XDM值在XDM架構中定義為枚舉，則可以使用將自動替換 **生命** 語法。

![](assets/aep_enummappingexdm.png)

要編輯XDM映射，請開啟它，修改所需資訊，然後保存它。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>現在，如果在 **[!UICONTROL Field mappings]** 在域外按一下，直到按一下 **[!UICONTROL Save]** 按鈕 此行為僅發生一次，在 **[!UICONTROL Field Mappings]** 是頁面上的第一個編輯。
