---
title: 關於 Campaign-Audience Manager 或 People 核心服務整合
description: 透過Audience Manager/人員核心服務整合，您可以在不同的Adobe Experience Cloud解決方案中共用受眾或區段。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 7%

---

# 關於 Campaign-Audience Manager 或 People 核心服務整合{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>視交換的資料而定，匯入Adobe Campaign中的對象可能會受到法律限制。

Adobe Campaign可讓您與不同的Adobe Experience Cloud應用程式交換和共用受眾/區段。 將&#x200B;**Adobe Campaign**&#x200B;與&#x200B;**People核心服務**（也稱為&#x200B;**Profiles &amp; Audiences核心服務**）或Adobe Audience Manager整合，可讓您：

* 將不同Adobe Experience Cloud解決方案的受眾/區段匯入Adobe Campaign。 您可以從Adobe Campaign的&#x200B;**[!UICONTROL Audiences]**&#x200B;功能表匯入對象。
* 將受眾匯出為共用受眾/區段。 這些對象可用於您所使用的不同Adobe Experience Cloud解決方案。 使用&#x200B;**[!UICONTROL Save audience]**&#x200B;活動，在工作流程中鎖定目標活動後，即可匯出對象。

整合支援兩種類型的Adobe Experience Cloud ID:

* **訪客ID**:此類型的ID可讓您調解Adobe Experience Cloud訪客與Adobe Campaign設定檔。透過Adobe IMS啟用連線後，Marketing Cloud訪客ID服務就會啟動，取代Adobe Campaign使用的永久Cookie。 這可讓您識別訪客，然後將其連結至設定檔。
   <br>當訪客ID點按透過Adobe Campaign傳送的電子郵件中的設定檔時，即會將訪客ID連結至設定檔：
   * 如果描述檔已有訪客ID，則描述檔的瀏覽器資料可讓Adobe Campaign復原，並自動將描述檔連結至訪客ID。
   * 如果找不到訪客ID，則會建立新ID。 此訪客ID會儲存在設定檔追蹤記錄中。

   接著，具有相同CNAME的其他Adobe Marketing Cloud應用程式將可辨識該ID。

* **宣告ID**:此類型的ID可讓您使用Adobe Campaign資料庫中的元素調解任何類型的資料。在Adobe Campaign中以預先定義的調解金鑰呈現。 交換資料時，會雜湊Adobe Campaign資料庫識別碼。 然後會將這些雜湊ID與匯入或匯出所涉之Adobe Marketing Cloud對象的雜湊ID進行比較。
   <br>此整合支援一般宣告ID、雜湊宣告ID和加密宣告ID。

   >[!NOTE]
   >
   >已宣告的 ID 資料來源現在也可搭配 People 核心服務整合使用。
   >
   >如果您使用People核心服務整合，且想要新增Audience Manager整合，則需要Adobe Audience Manager顧問的協助，以避免在Adobe Audience Manager內容中轉換為使用此宣告ID資料來源時，所收集的所有ID同步都遺失。


   加密可讓您透過指定加密演算法，使用宣告的ID在資料來源（例如PII）中共用加密的資料。

   例如，您可以解密加密的電子郵件地址或SMS號碼，即使使用者的設定檔不存在於Adobe Campaign資料庫中，您也可以傳送觸發訊息給使用者。

下圖詳細說明此整合的運作方式。在此，AAM代表Adobe Audience Manager,ACS代表Adobe Campaign Standard。

![](assets/aam_diagram.png)
