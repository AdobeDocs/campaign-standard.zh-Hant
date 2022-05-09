---
title: 在 Experience Cloud 中設定觸發程式
description: '瞭解如何配置Adobe Experience Cloud Triggers整合，以便根據客戶以前的行為開始向客戶發送個性化送貨。 '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 6%

---

# 在 Experience Cloud 中設定觸發程式{#configuring-triggers-in-experience-cloud}

## 激活功能 {#activating-the-functionality}

必須在Adobe Campaign通過Adobe激活該功能。 請與您的Adobe客戶主管或專業服務合作夥伴聯繫。

Adobe團隊需要以下資訊才能激活觸發器：

* Marketing Cloud公司名稱
* 組織ID
* 分析登錄公司(可與Marketing Cloud公司名稱相同)

## 配置解決方案和服務 {#configuring-solutions-and-services}

要使用此功能，您需要訪問以下解決方案/核心服務：

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
>子域配置是可傳遞性關鍵元素。 確保Adobe Campaign電子郵件與網站使用的電子郵件來自同一域。

您需要配置 [Experience CloudDTM核心服務](#configuring-experience-cloud-dtm-core-service)。 [Experience Cloud人核心服務](#configuring-experience-cloud-people-core-service) 和 [活動](#configuring-triggers-and-aliases-in-campaign) 運行這些使用案例。

### 配置Experience CloudDTM核心服務 {#configuring-experience-cloud-dtm-core-service}

1. 在Experience CloudDTM核心服務(動態Tag Management)中，激活網站頁面的Experience CloudID和Adobe Analytics。

   ![](assets/trigger_uc_conf_1.png)

1. 網站、Adobe Analytics和Adobe Campaign之間的ID協調需要使用混疊。 建立別名，例如「visitorid」。

   ![](assets/trigger_uc_conf_2.png)

### 配置Experience Cloud人核心服務 {#configuring-experience-cloud-people-core-service}

以前在DTM中引用的別名需要通過「客戶屬性」在「Experience Cloud人員核心服務」中建立。 確保建立新別名並引用整合代碼中的相同DTM別名（例如&quot;visitorid&quot;）。

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>我們將在Adobe Campaign的資料源中使用此客戶屬性（下一步）。

### 在市場活動中配置觸發器和別名 {#configuring-triggers-and-aliases-in-campaign}

1. 確保你 **[!UICONTROL Experience Cloud triggers]** 在你的Adobe Campaign Standard案上可見。 否則，請與Adobe Campaign管理員聯繫。

   ![](assets/remarketing_1.png)

1. 別名使分析中的聯繫人能夠與市場活動中的配置檔案進行協調。 您需要將Experience CloudID服務中定義的別名與市場活動中的共用資料源匹配。 您需要通過資料源在Adobe Campaign配置別名解析( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** )。 確保在 **[!UICONTROL Data Source/Alias]** 下拉菜單，該菜單與在上一步中建立的同一「客戶屬性」資料源進行映射。

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >您可以協調匿名用戶和登錄用戶的觸發器。 對於匿名用戶，配置檔案應存在於Adobe Campaign，並且以前已向用戶發送過電子郵件。 因此，訪問者ID配置就足夠了。 但是，如果要協調已登錄用戶的觸發器，則需要設定聲明的ID資料源。 有關此內容的詳細資訊，請參閱 [資料源配置](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)。

## 在Experience Cloud介面中建立觸發器 {#creating-a-trigger-in-the-experience-cloud-interface}

需要建立一個Adobe Experience Cloud觸發器，以便您可以在市場活動中使用它。

在Experience Cloud中建立新觸發器，並確保選擇網站上使用的報告套件。 確保選擇正確的維，以便觸發器。

請參閱 [Adobe Experience Cloud文檔](https://experienceleague.adobe.com/docs/core-services/interface/activation/triggers.html) 看這個 [視頻](https://helpx.adobe.com/tw/marketing-cloud/how-to/email-marketing.html#step-two)。

## 觸發最佳做法和限制 {#triggers-best-practices-and-limitations}

下面列出了使用「市場活動 — 觸發器」整合的最佳做法和限制：

* 如果您有多個Campaign Standard實例，則只要觸發器位於同一組織中，所有實例都可以接收觸發器。 分析還需要位於同一組織。
* 不能在觸發器核心服務中使用來自兩個不同報告套件的事件建立觸發器。
* 觸發器基於事務消息。 只要您必須非常快速地發送消息，就會使用事務性消息。 您不能對事務性消息排隊，然後以批處理方式循環這些消息。
* 觸發器在本質上不是確定性的。 當觸發器生成時，它會發送與cookie關聯的所有別名，因此，如果共用瀏覽器(如在零售亭、庫、網吧或家中的共用設備（夫妻從同一設備登錄）)，則無法映射到正確的ID。 使用瀏覽器登錄的所有ID都發送到市場活動，市場活動根據第一次協調發出消息。 如果有多個「電子郵件ID」符合協調條件，則市場活動不會發送電子郵件。 除非Analytics捕獲併發送正確的電子郵件ID，否則市場活動無法知道該ID是什麼。
* 不能在市場活動中儲存有效負載的內容。 觸發器不能用於更新配置檔案的資料。
* 觸發器中不支援客戶屬性（這意味著，只能使用報表套件資料來定義觸發器業務規則）。
* 市場活動不支援收集。

>[!CAUTION]
>
>您的網站必須與Adobe Campaign伺服器在同一域中運行。 否則，無法使用訪問者ID協調並聯繫匿名訪問該網站的用戶。
