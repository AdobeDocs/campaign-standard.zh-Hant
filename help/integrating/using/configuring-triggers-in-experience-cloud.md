---
title: 在 Experience Cloud 中設定觸發程式
description: 瞭解如何設定Adobe Experience Cloud觸發器整合，以根據客戶先前的行為開始向客戶傳送個人化傳遞。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 6%

---

# 在 Experience Cloud 中設定觸發程式{#configuring-triggers-in-experience-cloud}

## 啟動功能 {#activating-the-functionality}

必須在Adobe Campaign中由Adobe啟用此功能。 請聯絡您的Adobe客戶主管或專業服務合作夥伴。

Adobe團隊需要下列資訊才能啟用觸發程式：

* Marketing Cloud公司名稱
* 組織 ID
* Analytics登入公司(可與Marketing Cloud公司名稱相同)

## 設定解決方案和服務 {#configuring-solutions-and-services}

若要使用此功能，您必須具備下列解決方案/核心服務的存取權：

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
>子網域設定是傳遞能力關鍵元素。 請確定Adobe Campaign電子郵件是從網站使用的相同網域傳送的。

您必須設定[Experience Cloud DTM核心服務](#configuring-experience-cloud-dtm-core-service)、[Experience Cloud People核心服務](#configuring-experience-cloud-people-core-service)和[Campaign](#configuring-triggers-and-aliases-in-campaign)，才能執行這些使用案例。

### 設定Experience Cloud DTM核心服務 {#configuring-experience-cloud-dtm-core-service}

1. 在Experience Cloud DTM核心服務(動態Tag Management)中，針對您的網站頁面啟動Experience Cloud ID和Adobe Analytics。

   ![](assets/trigger_uc_conf_1.png)

1. 網站、Adobe Analytics和Adobe Campaign之間的ID調解需要使用別名。 建立別名，例如&quot;visitorid&quot;。

   ![](assets/trigger_uc_conf_2.png)

### 設定Experience Cloud People核心服務 {#configuring-experience-cloud-people-core-service}

先前在DTM中參考的別名，需透過客戶屬性在Experience Cloud People核心服務中建立。 請務必建立新別名，並在整合代碼中參照相同的DTM別名（例如「visitorid」）。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>我們打算在Adobe Campaign的資料來源中使用此客戶屬性（下一步）。

### 在Campaign中設定觸發器和別名 {#configuring-triggers-and-aliases-in-campaign}

1. 確定您的Adobe Campaign Standard執行個體上有顯示&#x200B;**[!UICONTROL Experience Cloud triggers]**。 否則，請聯絡Adobe Campaign管理員。

   ![](assets/remarketing_1.png)

1. 別名可讓Analytics中的聯絡人與Campaign中的設定檔進行調解。 您需要將Experience Cloud ID服務中定義的別名與Campaign中的共用資料Source比對。 您必須透過資料來源( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** )在Adobe Campaign中設定別名解析。 請務必在「**[!UICONTROL Data Source/Alias]**」下拉式選單中選擇正確的資料來源，此資料來源已對應至上一步驟中建立的相同客戶屬性資料來源。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >您可以為匿名和登入使用者調解您的觸發程式。 對於匿名使用者，設定檔應存在於Adobe Campaign中，並且之前已傳送電子郵件給使用者。 對此，訪客ID設定就足夠了。 不過，如果您想要調解登入使用者的觸發程式，則需要設定宣告ID資料Source。 如需詳細資訊，請參閱[資料Source設定](../../integrating/using/integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)。

## 在Experience Cloud介面中建立觸發因子 {#creating-a-trigger-in-the-experience-cloud-interface}

需要建立Adobe Experience Cloud觸發程式，才能在Campaign中使用。

在Experience Cloud中建立新的觸發程式，並請務必選取您網站上使用的報表套裝。 請務必選擇正確的維度，以便觸發程式。

請參閱[Adobe Experience Cloud檔案](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=zh-Hant)。

## 觸發器最佳作法和限制 {#triggers-best-practices-and-limitations}

以下是使用Campaign — 觸發器整合的最佳實務和限制清單：

* 如果您有多個Campaign Standard執行個體，則所有執行個體都能接收觸發器，只要這些觸發器位在同一個組織中即可。 Analytics也需要位於相同的組織。
* 您無法使用兩個不同報表套裝的事件，在「觸發程式核心服務」中建立觸發程式。
* 觸發器以異動訊息為基礎。 無論何時必須快速傳送訊息，都會使用交易式訊息。 您無法將交易式訊息排入佇列，然後在批次中重複執行。
* 觸發器的本質不是決定性的。 觸發器產生時，會傳送與Cookie相關聯的所有別名，所以在零售資訊站、資料庫、網路咖啡館或家中共用裝置（夫妻從同一部裝置登入）等共用瀏覽器的情況下，無法對應至正確的ID。 所有使用瀏覽器登入的ID都會傳送至Campaign，後者會根據第一次調解傳送訊息。 如果有多個「電子郵件ID」符合調解資格，則Campaign不會傳送電子郵件。 除非Analytics擷取並傳送電子郵件ID，否則Campaign無法得知正確的電子郵件ID。
* 您無法將裝載的內容儲存在Campaign中。 觸發器無法用於更新設定檔的資料。
* Triggers不支援客戶屬性（這表示，只有報表套裝資料才能用於定義Triggers business rules）。
* Campaign不支援集合功能。

>[!CAUTION]
>
>您的網站必須執行於與Adobe Campaign伺服器相同的網域上。 如果沒有，您將無法使用訪客ID來調解並和匿名造訪網站的使用者聯絡。
