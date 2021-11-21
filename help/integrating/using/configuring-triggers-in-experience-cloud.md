---
title: 在 Experience Cloud 中設定觸發程式
description: '了解如何設定Adobe Experience Cloud Triggers整合，以開始根據客戶先前的行為將個人化傳遞傳送至客戶。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 7%

---

# 在 Experience Cloud 中設定觸發程式{#configuring-triggers-in-experience-cloud}

## 啟用功能 {#activating-the-functionality}

必須透過Adobe在Adobe Campaign中啟動功能。 請連絡您的Adobe客戶經理或專業服務合作夥伴。

Adobe團隊需要下列資訊才能啟動觸發器：

* Marketing Cloud公司名稱
* IMS 組織 ID
* Analytics登入公司(可以與Marketing Cloud公司名稱相同)

## 配置解決方案和服務 {#configuring-solutions-and-services}

若要使用此功能，您需要存取下列解決方案/核心服務：

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、行動應用程式、Select 或 Standard。
* Experience Cloud 觸發程式核心服務

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM 核心服務

   ![](assets/trigger_uc_prereq_2.png)

* Experience Cloud 訪客 ID 及 Experience Cloud People Core Service

   ![](assets/trigger_uc_prereq_3.png)

此外，您還需要有正常運作的網站。

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>子網域配置是傳遞能力關鍵元素。 請確定Adobe Campaign電子郵件的傳送網域與網站使用的網域相同。

您需要設定 [Experience CloudDTM核心服務](#configuring-experience-cloud-dtm-core-service), [Experience Cloud人員核心服務](#configuring-experience-cloud-people-core-service) 和 [行銷活動](#configuring-triggers-and-aliases-in-campaign) 來執行這些使用案例。

### 設定Experience CloudDTM核心服務 {#configuring-experience-cloud-dtm-core-service}

1. 在Experience CloudDTM核心服務（動態標籤管理）中，為您的網站頁面啟用Experience CloudID和Adobe Analytics。

   ![](assets/trigger_uc_conf_1.png)

1. 網站、Adobe Analytics和Adobe Campaign之間的ID調解需要使用鋸齒。 建立別名，例如「visitorid」。

   ![](assets/trigger_uc_conf_2.png)

### 設定Experience Cloud人員核心服務 {#configuring-experience-cloud-people-core-service}

先前在DTM中參考的別名需透過Experience Cloud屬性在客戶人員核心服務中建立。 請務必建立新別名，並在整合程式碼中參照相同的DTM別名（例如「visitorid」）。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>我們將在Adobe Campaign的資料來源中使用此客戶屬性（下一步）。

### 在Campaign中設定觸發程式和別名 {#configuring-triggers-and-aliases-in-campaign}

1. 請確定您 **[!UICONTROL Experience Cloud triggers]** 顯示在您的Adobe Campaign Standard執行個體上。 如果您沒有，請聯絡Adobe Campaign管理員。

   ![](assets/remarketing_1.png)

1. 別名可讓Analytics中的連絡人與Campaign中的設定檔調解。 您需要比對Experience CloudID服務中定義的別名與促銷活動中的共用資料來源。 您需要透過資料來源在Adobe Campaign中設定別名解析( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** )。 請務必在 **[!UICONTROL Data Source/Alias]** 下拉式功能表，此功能表會與先前步驟中建立的相同客戶屬性資料來源對應。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >您可以協調匿名和登入使用者的觸發器。 若為匿名使用者，設定檔應存在於Adobe Campaign中，且之前已傳送電子郵件給使用者。 對此，訪客ID設定就足夠了。 不過，如果您想要調解登入使用者的觸發器，則需要設定「宣告ID資料來源」。 有關詳細資訊，請參閱 [資料來源設定](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## 在Experience Cloud介面中建立觸發程式 {#creating-a-trigger-in-the-experience-cloud-interface}

需要建立Adobe Experience Cloud觸發程式，才能在Campaign中使用。

在「Experience Cloud」中建立新觸發器，並確定您選取網站上使用的報表套裝。 請確定您選取正確的維度，以便觸發器。

請參閱 [Adobe Experience Cloud檔案](https://experienceleague.adobe.com/docs/core-services/interface/activation/triggers.html) 看這個 [影片](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html#step-two).

## 觸發最佳實務和限制 {#triggers-best-practices-and-limitations}

以下是使用Campaign — 觸發器整合的最佳實務和限制清單：

* 如果您有多個Campaign Standard例項，則只要觸發器位於相同的IMS組織ID，所有例項都能接收觸發器。 Analytics也必須位於相同的IMS組織ID上。
* 您無法使用來自兩個不同報表套裝的事件，在觸發核心服務中建立觸發器。
* 觸發器是根據交易式訊息。 每當您必須快速傳送訊息時，就會使用交易式訊息。 您無法將交易式訊息排入佇列，然後以批次方式重複播放。
* 觸發器本質上並非決定性因素。 產生觸發器時，會傳送與Cookie相關聯的所有別名，因此若是共用瀏覽器(例如零售資訊站、資料庫、網吧或家中的共用裝置（從同一部裝置登入的丈夫和妻子），則無法對應至正確的ID。 使用瀏覽器登入的所有ID都會傳送至Campaign，而Campaign會根據第一次調解傳送訊息。 如果有多個「電子郵件ID」符合調解的資格，則Campaign不會傳送電子郵件。 除非由Analytics擷取並傳送，否則Campaign無法知道正確的電子郵件ID。
* 您無法在Campaign中儲存裝載的內容。 觸發器無法用於更新設定檔的資料。
* 觸發器不支援客戶屬性（亦即，只有報表套裝資料可用來定義觸發器業務規則）。
* Campaign不支援集合的集合。

>[!CAUTION]
>
>您的網站必須執行與Adobe Campaign伺服器相同的網域。 否則，您無法使用訪客id來調解並聯絡匿名造訪網站的使用者。
