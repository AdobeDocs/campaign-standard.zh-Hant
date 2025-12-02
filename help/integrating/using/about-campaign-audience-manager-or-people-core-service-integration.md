---
title: 關於 Campaign-Audience Manager 或 People 核心服務整合
description: 透過Audience Manager/People核心服務整合，您可以在不同的Adobe Experience Cloud解決方案中共用受眾或區段。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 18%

---

# 關於 Campaign-Audience Manager 或 People 核心服務整合{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>根據交換的資料，在Adobe Campaign中匯入對象可能會受到法律限制。

Adobe Campaign可讓您與不同的Adobe Experience Cloud應用程式交換和共用對象/區段。 將&#x200B;**Adobe Campaign**&#x200B;與&#x200B;**People核心服務** （也稱為&#x200B;**設定檔與對象核心服務**）或Adobe Audience Manager整合可讓您：

* 從不同的Adobe Experience Cloud解決方案匯入對象/區段至Adobe Campaign。 您可以從Adobe Campaign的&#x200B;**[!UICONTROL Audiences]**&#x200B;功能表匯入對象。
* 將對象匯出為共用對象/區段。 這些客群可用於您所使用的不同 Adobe Experience Cloud 解決方案。 在工作流程中目標定位活動後，可使用&#x200B;**[!UICONTROL Save audience]**&#x200B;活動匯出對象。

整合支援兩種型別的Adobe Experience Cloud ID：

* **訪客ID**：此型別的ID可讓您調解Adobe Experience Cloud訪客與Adobe Campaign設定檔。 透過Adobe IMS啟用連線後，Marketing Cloud訪客ID服務就會立即啟動，取代Adobe Campaign使用的永久Cookie。 這可讓您識別訪客，然後將其連結至設定檔。
  <br>訪客ID只要在透過Adobe Campaign傳送的電子郵件中按一下，就會連結至設定檔：
   * 如果設定檔已有訪客ID，設定檔的瀏覽器資料可讓Adobe Campaign復原，並自動將設定檔連結至訪客ID。
   * 若找不到訪客ID，則會建立新的ID。 此訪客ID會儲存在設定檔追蹤記錄中。

  之後，具有相同CNAME的其他Adobe Marketing Cloud應用程式將會識別該ID。

* **宣告ID**：此型別的ID可讓您調解任何型別的資料與Adobe Campaign資料庫中的元素。 在Adobe Campaign中以預先定義的調解金鑰呈現。 交換資料時，會雜湊處理Adobe Campaign資料庫識別碼。 這些雜湊ID接著會與匯入或匯出所涉及的Adobe Marketing Cloud對象雜湊ID比較。
  <br>這項整合支援一般宣告ID、雜湊宣告ID和加密宣告ID。

  >[!NOTE]
  >
  >已宣告的 ID 資料來源現在也可搭配 People 核心服務整合使用。
  >
  >如果您使用 People 核心服務整合，且想要新增 Audience Manager 整合，則需要 Adobe Audience Manager 顧問的協助，以避免在 Adobe Audience Manager 內容中轉換為使用此宣告 ID 資料來源時，所收集的 ID 同步全部遺失。


  加密可讓您指定加密演演算法，使用宣告ID在資料來源（例如PII）中共用加密的資料。

  例如，透過解密加密的電子郵件地址或簡訊號碼的功能，您也可以傳送觸發式訊息給使用者，即使其設定檔不存在於Adobe Campaign資料庫中亦然。

下圖詳細說明此整合的運作方式。 在此，AAM代表Adobe Audience Manager，ACS代表Adobe Campaign Standard。

![](assets/aam_diagram.png)
