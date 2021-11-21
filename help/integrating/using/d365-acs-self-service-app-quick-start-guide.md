---
title: '開始使用整合工具 '
description: 開始使用整合工具
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: e73e2069-e86d-4be2-bf73-22e6dc164340
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---

# 開始使用自助服務整合應用程式 {#gs-self-service-app}

Adobe Campaign Standard與Microsoft Dynamics 365自助服務整合應用程式的整合可讓您設定資料流、控制資料流是否在執行，以及在哪個環境中執行。 不過，您必須先完成一些必要條件，才能開始使用自助服務整合應用程式。

## 概念與限制 {#concepts-and-restrictions}

開始使用整合工具之前，您必須了解與整合相關聯的概念和護欄，並採取一些初始步驟以取得存取權。

了解更多資訊：

* [開始使用 Microsoft Dynamics 365 整合](../../integrating/using/d365-acs-get-started.md)
* [整合最佳實務和限制](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [了解實作此整合的關鍵步驟](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [使用 Microsoft Dynamics 365 整合](../../integrating/using/d365-acs-using-the-integration.md)

## 先決條件 {#self-service-app-prerequisites}

您必須設定Microsoft Dynamics 365和Adobe Campaign Standard，讓整合應用程式才能存取您的資料。 在Dynamics 365、Adobe Campaign Standard和Adobe I/O中進行設定需要一些時間；不過，一旦完成設定，您就能透過自助服務整合應用程式的使用者介面控制整合。

了解更多資訊：

* [設定 Microsoft Dynamics 365 以進行 Campaign 整合](../../integrating/using/d365-acs-configure-d365.md)
* [設定 Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [對應Campaign自訂資源和Microsoft Dynamics 365自訂實體](../../integrating/using/d365-acs-notices-and-recommendations.md)

## 設定自助服務整合應用程式的關鍵步驟 {#self-service-app-configuration-steps}

接著，您就可以從整合工具開始。 請依照下列步驟操作：

1. [存取整合應用程式](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [設定整合應用程式以供您使用](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [實作資料同步](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [配置同步工作流](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 連結至整合應用程式 {#self-service-app-link}

開啟瀏覽器，然後瀏覽至與您所在地區相關聯的連接器：

* [亞太](https://d365-acs-ap.ea.adobe.com/)
* [歐洲、中東或非洲(EMEA)](https://d365-acs-em.ea.adobe.com/)
* [美洲](https://d365-acs-am.ea.adobe.com/)

## 隱私權要求確認 {#self-service-app-acknowledgement}

第一次瀏覽至自助服務UI時，會收到隱私權確認訊息。 您必須確認您了解在Campaign和Microsoft Dynamics 365中個別執行隱私權要求時所扮演的角色，才能繼續。
深入了解您的隱私權責任，以及如何在 [本節](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## 設定您的憑證 {#self-service-app-credentials}

第一次瀏覽至UI時，您應該會看到標題如下所示的頁面：

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> 如果應用程式設定尚未設定，通常會收到提及「無法連線」至Adobe Campaign Standard或Microsoft Dynamics 365的警報。

請驗證您計畫配置的「ORG」和「INSTANCE」選項。  如果沒有，請按一下下拉式清單，然後選取正確的組織和例項。

>[!IMPORTANT]
>
> 如果您是第一次設定連接器，且/或您是此程式的新手，則我們 **強烈** 敦促您選取「stage」或「dev」例項。 在嘗試在生產環境中進行設定之前，請務必確認您的設定運作良好。

如果您有正確的組織和例項，請按一下「漢堡包」功能表以顯示下拉式功能表。 然後按一下 **[!UICONTROL Settings...]** 在下拉式功能表中，瀏覽您在其中輸入Microsoft Dynamics 365和Campaign認證的頁面（請參閱下方）。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

在 **[!UICONTROL Settings]** 頁面中，填寫下列區段：

* Microsoft Dynamics 365憑證
* Adobe憑證

開始 [此處](../../integrating/using/d365-acs-self-service-app-settings.md) 以查找有關在何處查找每個輸入的資訊的詳細資訊。 完成後，按一下 **[!UICONTROL Save]** 按鈕。

## 檢查初始配置 {#self-service-app-initial-config}

假設您已完成上述先決條件，且已正確新增所有認證，現在請導覽至 **[!UICONTROL Workflows]** 頁面。 深入了解整合應用程式工作流程，位於 [本頁](../../integrating/using/d365-acs-self-service-app-workflows.md).

在  **[!UICONTROL Workflows]** 頁，按一下與 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 編輯其設定的工作流程。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

在 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 頁，您可以訪問已配置的表映射清單。  這會預設為立即可用的聯絡人/設定檔對應。 所有其他自訂實體都需個別設定。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

在 **[!UICONTROL Edit Table Mapping]** 頁面，檢查 **[!UICONTROL Mappings]** 區段，確保將Microsoft Dynamics 365中的欄位對應至Campaign中的正確欄位。 如果需要添加任何其他映射，請立即添加，以及任何替換項或篩選器。 [深入瞭解](../../integrating/using/d365-acs-self-service-app-data-sync.md)。

如果要添加新映射，請參閱 [本節](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) 以取得更多資訊。

正確設定後，按一下 **[!UICONTROL Play]** 按鈕 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流程，以啟動整合和資料流程。

>[!IMPORTANT]
>
>我們 **強烈** 建議您先在預備或開發環境中執行此作業，然後再在生產環境中執行。 請檢查標題中是否已選取stage/dev執行個體。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

執行後，您應該可以在Microsoft Dynamics 365中新增或修改項目，並在幾分鐘內觀察這些變更，以測試。 如果您隨時需要停止此程式，只需按相同的按鈕即可停止。 [了解更多](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## 整合應用程式工作區 {#self-service-app-workspace}

### 應用程式標題 {#app-header}

自助應用程式中的標題可讓您定義目前檢視和/或設定的組織和例項。

選取 **ORG** 和 **例項** 您要檢視/編輯。 這些欄位顯示為唯讀，但是當您將滑鼠游標置於其上時，這些欄位就會變成可編輯的。

按一下包含三行水準線的按鈕時，畫面會顯示下拉式功能表 ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) 在標題的右側。

下拉式功能表中的項目為：

* **設定**:選取此選項會將您傳送至畫面，讓您指定Microsoft Dynamics 365和Adobe Campaign的API憑證，以及應用程式的其他一般設定。

* **檔案**:此選項是此整合專屬的Adobe Campaign檔案連結

* **客戶服務**:這是與開立客戶服務票證相關的Experience Cloud檔案連結

* **登出**:這會將您登出應用程式，並允許您以其他使用者的身分登入。

* **關於**:這會顯示一個對話方塊，其中包含應用程式的相關資訊，包括版權資訊。

### 階層連結 {#app-breadcrumbs}

導覽應用程式時，階層連結會顯示在某些畫面的頂端。

**範例:**

以下是 **[!UICONTROL Edit Table Mapping]** 顯示階層連結和頁面標題的畫面。 在此情況下，您可以按一下 **[!UICONTROL Workflows]** 或 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 文字，以前往其中一個先前的畫面。 **[!UICONTROL Edit Table Mapping]** 在此情況下，無法點按階層連結，因為它是目前的畫面。

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### 常用按鈕 {#app-buttons}

下列圖示用於自助服務應用程式的多個頁面。

![](assets/do-not-localize/d365-to-acs-icon-add.png)  — 將新項添加到清單中。

![](assets/do-not-localize/d365-to-acs-icon-edit.png)  — 編輯已存在的內容

![](assets/do-not-localize/d365-to-acs-icon-delete.png)  — 從項目清單中刪除項目
