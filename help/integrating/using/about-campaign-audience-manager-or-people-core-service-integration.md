---
solution: Campaign Standard
product: campaign
title: 關於 Campaign-Audience Manager 或 People 核心服務整合
description: 透過Audience Manager/人員核心服務整合，您可以在不同的Adobe Experience Cloud解決方案中分享受眾或細分。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: 觸發器
role: 資料架構師
level: 中級
translation-type: tm+mt
source-git-commit: a6272db76fbfca7b9ebcc3734368f7c032b234af
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 4%

---


# 關於 Campaign-Audience Manager 或 People 核心服務整合{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>根據交換的資料，匯入Adobe Campaign的受眾可能會受到法律限制。

Adobe Campaign可讓您與不同的Adobe Experience Cloud應用程式交換和分享受眾／細分。 將&#x200B;**Adobe Campaign**&#x200B;與&#x200B;**人員核心服務**（又稱為&#x200B;**設定檔與觀眾核心服務**）或Adobe Audience Manager整合，可讓您：

* 將不同Adobe Experience Cloud解決方案的受眾／細分匯入Adobe Campaign。 您可從Adobe Campaign的&#x200B;**[!UICONTROL Audiences]**&#x200B;功能表匯入觀眾。
* 將觀眾匯出為共用的觀眾／區段。 這些受眾可用於您使用的不同Adobe Experience Cloud解決方案。 使用&#x200B;**[!UICONTROL Save audience]**&#x200B;活動，在工作流程中定位活動後，可匯出觀眾。

整合支援兩種Adobe Experience CloudID:

* **訪客ID**:此類ID可讓您協調Adobe Experience Cloud訪客與Adobe Campaign描述檔。一旦透過AdobeIMS啟用連線，Marketing Cloud訪客ID服務就會啟動，取代Adobe Campaign使用的永久Cookie。 這可讓您識別訪客，然後將其連結至描述檔。
   <br>當訪客ID在透過Adobe Campaign傳送的電子郵件中按一下描述檔時，就會連結至描述檔：
   * 如果描述檔已有訪客ID，則描述檔的瀏覽器資料可讓Adobe Campaign復原並自動將描述檔連結至訪客ID。
   * 如果找不到訪客ID，則會建立新ID。 此訪客ID儲存在描述檔追蹤記錄檔中。

   ID將會由其他具有相同CNAME的Adobe Marketing Cloud應用程式識別。

* **宣告的ID**:此類型的ID可讓您將任何類型的資料與Adobe Campaign資料庫的元素協調。它在Adobe Campaign被表示為預先定義的和解密鑰。 在交換資料時，對Adobe Campaign資料庫標識符進行散列處理。 然後，這些雜湊ID會與匯入或匯出所涉及之Adobe Marketing Cloud觀眾的雜湊ID進行比較。
   <br>此整合支援一般宣告的ID、雜湊的宣告ID和加密的宣告ID。

   >[!NOTE]
   >
   >宣告的ID資料來源現在也可與People核心服務整合搭配使用。
   >
   >如果您使用「人員」核心服務整合併想要新增Audience Manager整合，您將需要Adobe Audience Manager顧問的協助，以避免在轉換至Adobe Audience Manager上下文中使用此Declared ID資料來源時遺失所有收集到的ID同步。


   加密可讓您透過指定加密演算法，使用宣告的ID在資料來源（例如PII）中共用加密資料。

   例如，您可以解密加密的電子郵件地址或SMS號碼，因此也可以傳送觸發訊息給您的使用者，即使其設定檔在Adobe Campaign資料庫中不存在亦然。

下圖詳細說明此整合的運作方式。這裡是AAMAdobe Audience Manager和Adobe Campaign Standard的ACS。

![](assets/aam_diagram.png)