---
title: 關於Campaign-Audience Manager或人員核心服務整合
seo-title: 關於Campaign-Audience Manager或人員核心服務整合
description: 關於Campaign-Audience Manager或人員核心服務整合
seo-description: 透過Audience Manager/People核心服務整合，您可以在不同的Adobe Experience Cloud解決方案中共用受眾或細分。
page-status-flag: 從未啓動
uuid: 39e3c78e-ccd-4823-afe9-abc7 f8 aef034
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: working-with-campaign-and-udience-manager-or-ople-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525 a dee46 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About Campaign-Audience Manager or People core service integration{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign可讓您與不同的Adobe Experience Cloud應用程式交換及共用受眾/區段。Integrating **Adobe Campaign** with **People core service** (also known as **Profiles &amp; Audiences core service**) or Adobe Audience Manager allows you to:

* 將不同的Adobe Experience Cloud解決方案的受眾/區段匯入Adobe Campaign。Audiences can be imported from the **[!UICONTROL Audiences]** menu in Adobe Campaign.
* 將觀眾匯出為共用觀眾/區段。這些觀眾可用於您使用的不同Adobe Experience Cloud解決方案中。Audiences can be exported after targeting activities in a workflow, using the **[!UICONTROL Save audience]** activity.

整合支援兩種Adobe Experience Cloud ID：

* **訪客ID**：此類型的ID可讓您透過Adobe Campaign設定檔協調Adobe Experience Cloud訪客。
* **宣告ID**：此類型的ID可讓您將任何類型的資料與Adobe Campaign資料庫中的描述檔協調。此項整合支援一般宣告的ID、雜湊宣告的ID和加密的宣告ID。

   加密可讓您透過指定加密演算法，在資料來源(例如PII)中共用加密資料。

   例如，若有解密加密電子郵件地址或SMS編號的能力，您也可以傳送觸發訊息給使用者，即使他們的描述檔不存在於Adobe Campaign資料庫中也一樣。

>[!CAUTION]
>
>根據交換的資料，在Adobe Campaign中匯入觀眾可能受法律限制

