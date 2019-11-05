---
title: 關於 Campaign-Audience Manager 或 People 核心服務整合
description: 透過Audience Manager / People核心服務整合，您可以在不同的Adobe Experience cloud解決方案中共用受眾或細分。
page-status-flag: 從未激活
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 整合
content-type: 參考
topic-tags: 使用促銷活動與觀眾管理員或人員核心服務
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 關於 Campaign-Audience Manager 或 People 核心服務整合{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign可讓您使用不同的Adobe Experience cloud應用程式來交換和分享受眾／細分。 將 **Adobe Campaign** 與People核心服務 **(又稱為** Profiles &amp; Audiences核心服務 ****)或Adobe Audience manager整合，可讓您：

* 從不同的Adobe Experience cloud解決方案將受眾／細分匯入Adobe Campaign。 您可從Adobe Campaign的功能表 **[!UICONTROL Audiences]** 匯入觀眾。
* 將觀眾匯出為共用的觀眾／區段。 這些受眾可用於您所使用的不同Adobe Experience cloud解決方案。 使用活動定位工作流程中的活動後，即可匯出對象 **[!UICONTROL Save audience]** 。

整合支援兩種Adobe Experience Cloud ID:

* **訪客ID**:這種ID類型可讓您協調Adobe Experience cloud訪客與Adobe Campaign設定檔。
* **宣告的ID**:此類型的ID可讓您協調任何類型的資料與Adobe Campaign資料庫中的設定檔。 此整合支援一般宣告的ID、雜湊的宣告ID和加密的宣告ID。 若要進一步了 **[!UICONTROL Declared ID]** 解有效性，請參 [閱本頁](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md)。

   加密可讓您透過指定加密演算法，使用宣告的ID在資料來源（例如PII）中共用加密資料。

   例如，您可以解密加密的電子郵件地址或SMS號碼，即使Adobe Campaign資料庫中不存在觸發訊息，也可以傳送給使用者。

>[!CAUTION]
>
>根據交換的資料，匯入Adobe Campaign中的觀眾可能會受到法律限制

