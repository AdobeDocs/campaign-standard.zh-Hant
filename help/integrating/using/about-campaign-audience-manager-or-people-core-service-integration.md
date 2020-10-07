---
title: 關於 Campaign-Audience Manager 或 People 核心服務整合
description: 透過Audience Manager / People核心服務整合，您可以在不同的Adobe Experience Cloud解決方案中共用受眾或細分。
page-status-flag: never-activated
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 關於 Campaign-Audience Manager 或 People 核心服務整合{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>根據交換的資料，匯入Adobe Campaign中的觀眾可能會受到法律限制。

Adobe Campaign可讓您使用不同的Adobe Experience Cloud應用程式來交換和分享受眾／細分。 將 **Adobe Campaign** 與People核心服務 **(又稱為** Profiles &amp; Audiences核心服務 ****)或Adobe Audience Manager整合，可讓您：

* 從不同的Adobe Experience Cloud解決方案將受眾／細分匯入Adobe Campaign。 您可從Adobe Campaign的功能表 **[!UICONTROL Audiences]** 匯入觀眾。
* 將觀眾匯出為共用的觀眾／區段。 這些受眾可用於您所使用的不同Adobe Experience Cloud解決方案。 使用活動定位工作流程中的活動後，即可匯出對象 **[!UICONTROL Save audience]** 。

整合支援兩種Adobe Experience Cloud ID:

* **訪客ID**:這種ID類型可讓您協調Adobe Experience Cloud訪客與Adobe Campaign設定檔。 一旦透過Adobe IMS啟用連線，Marketing Cloud訪客ID服務就會啟動，取代Adobe Campaign使用的永久Cookie。 這可讓您識別訪客，然後將其連結至描述檔。
   <br>當訪客ID按一下透過Adobe Campaign傳送的電子郵件中的描述檔時，就會立即連結至描述檔：
   * 如果描述檔已有訪客ID，則描述檔的瀏覽器資料可讓Adobe Campaign復原並自動將描述檔連結至訪客ID。
   * 如果找不到訪客ID，則會建立新ID。 此訪客ID儲存在描述檔追蹤記錄檔中。

   然後，具有相同CNAME的其他Adobe Marketing Cloud應用程式將會識別該ID。

* **宣告的ID**:此類型的ID可讓您將任何類型的資料與Adobe Campaign資料庫的元素協調。 在Adobe Campaign中，它會以預先定義的協調金鑰呈現。 在交換資料時，會雜湊Adobe Campaign資料庫識別碼。 然後，這些雜湊ID會與匯入或匯出中涉及之Adobe Marketing Cloud觀眾的雜湊ID進行比較。
   <br>此整合支援一般宣告的ID、雜湊的宣告ID和加密的宣告ID。

   >[!CAUTION]
   >
   >宣告的ID僅能與Adobe Audience Manager搭配使用。 沒有宣告的ID將無法運作。

   加密可讓您透過指定加密演算法，使用宣告的ID在資料來源（例如PII）中共用加密資料。

   例如，您可以解密加密的電子郵件地址或SMS號碼，即使Adobe Campaign資料庫中不存在觸發訊息，也可以傳送給使用者。

下圖詳細說明此整合的運作方式。AAM代表Adobe Audience Manager和ACS for Adobe Campaign Standard。

![](assets/aam_diagram.png)