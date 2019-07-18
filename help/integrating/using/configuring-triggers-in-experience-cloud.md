---
title: 在Experience Cloud中設定觸發器
seo-title: 在Experience Cloud中設定觸發器
description: 在Experience Cloud中設定觸發器
seo-description: '瞭解如何設定Adobe Experience Cloud觸發器整合，開始根據客戶先前的行為傳送個人化傳遞給客戶。 '
page-status-flag: 從未啓動
uuid: 8fd7b804-9528-46a5-a060-bf16 b8 dc555 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與觸發器
discoiquuid: 4163dc0c-8103-4425-b8 bf-7aa45 c4 d06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activating the functionality {#activating-the-functionality}

Adobe Campaign必須在Adobe Campaign中啓用此功能。請聯絡您的Adobe銷售代表或專業服務合作夥伴。

Adobe團隊需要下列資訊才能啓動觸發器：

* Marketing Cloud公司名稱
* IMS OG ID
* Analytics登入公司(可與Marketing Cloud公司名稱相同)

## Configuring solutions and services {#configuring-solutions-and-services}

若要使用此功能，您必須存取下列解決方案/核心服務：

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、Select或Standard。
* Experience Cloud觸發器核心服務

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM核心服務

   ![](assets/trigger_uc_prereq_2.png)

* Experience Cloud訪客ID和Experience Cloud人員核心服務

   ![](assets/trigger_uc_prereq_3.png)

您也需要有工作網站。

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>子網域委派是一個傳遞能力關鍵元素。請確定Adobe Campaign電子郵件是從網站所使用的網域傳送的。

You need to configure [Experience Cloud DTM Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-people-core-service) and [Campaign](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-triggers-and-aliases-in-campaign) to run these use cases.

### Configuring Experience Cloud DTM Core Service {#configuring-experience-cloud-dtm-core-service}

1. 在Experience Cloud DTM核心服務(動態標籤管理)中，為您的網站頁面啓用Experience Cloud ID和Adobe Analytics。

   ![](assets/trigger_uc_conf_1.png)

1. 網站之間的ID協調，Adobe Analytics和Adobe Campaign需要使用別名。建立別名，「visitorid」。

   ![](assets/trigger_uc_conf_2.png)

### Configuring Experience Cloud People Core Service {#configuring-experience-cloud-people-core-service}

先前在DTM中參照的別名必須透過客戶屬性在Experience Cloud人員核心服務中建立。請確定您建立新的，並參照整合碼中相同的DTM別名(例如「visitorid」)。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>我們將在Adobe Campaign(下一步)的資料來源中使用此客戶屬性。

### Configuring triggers and aliases in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Make sure you have **[!UICONTROL Experience Cloud triggers]** visible on your Adobe Campaign Standard instance. 如果您沒有，請聯絡Adobe Campaign管理員。

   ![](assets/remarketing_1.png)

1. 別名可讓Analytics中的聯絡人與促銷活動中的描述檔協調。您必須符合Experience Cloud ID服務中與「促銷活動」中的「共用資料來源」定義的別名。You need to configure the aliases resolution in Adobe Campaign via a Data source ( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** ). Make sure you choose the correct data source in the **[!UICONTROL Data Source/Alias]** drop-down menu, which is mapped with the same Customer Attribute data source created in previous step.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >您可以協調匿名和登入使用者的觸發器。對於匿名使用者，該描述檔應該存在於Adobe Campaign中，且電子郵件之前已傳送給使用者。為此，訪客ID設定就足夠了。不過，如果您想要協調登入使用者的觸發器，則需要設定「宣告的ID資料來源」。For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creating a trigger in the Experience Cloud interface {#creating-a-trigger-in-the-experience-cloud-interface}

必須建立Adobe Experience Cloud觸發器，以便在Campaign中使用它。

在Experience Cloud中建立新觸發器，並確定您選取網站上使用的報表套裝。請確定您選擇正確的維度，以便觸發觸發。

Refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) and watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Triggers best practices and limitations {#triggers-best-practices-and-limitations}

以下列出使用促銷活動的最佳實務和限制-觸發器整合：

* 如果您有多個Campaign Standard例項，則只要這些實例位於相同的IMS組織ID中，就可接收所有例項。Analytics也必須位於相同的IMS組織ID上。
* 您無法在觸發核心服務中使用兩個不同報表套裝的事件建立觸發器。
* 觸發器是以交易訊息為基礎。每當您必須迅速傳送訊息時，就會使用交易式訊息。您無法佇列交易訊息，然後再循環回圈。
* 觸發器不是決定性的。產生觸發器時，會傳送與Cookie相關的所有別名，因此在共用瀏覽器中，例如零售資訊站、資料庫、網路咖啡廳或家中的裝置(丈夫和妻子從同一台裝置登入)，無法對應至正確的ID。所有用於登入瀏覽器的ID都會傳送至Campaign，以便在第一次協調時傳送訊息。如果有多個「電子郵件ID」符合協調資格，則「促銷活動」不會傳送電子郵件。促銷活動無法瞭解正確的電子郵件ID是甚麼，除非Analytics擷取並傳送。
* 您無法將裝載的內容儲存在Campaign中。觸發器無法用來更新描述檔的資料。
* 觸發器中不支援客戶屬性(亦即，只能使用報告套裝資料來定義觸發項目規則)。
* Campaign不支援系列集合。

>[!CAUTION]
>
>您的網站必須與Adobe Campaign伺服器上的相同網域執行。否則，您不能使用訪客ID進行協調，並以匿名方式接觸造訪網站的使用者。

