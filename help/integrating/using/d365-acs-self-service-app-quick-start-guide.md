---
title: 開始使用整合工具
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
source-wordcount: '1079'
ht-degree: 1%

---

# 開始使用自助服務整合應用程式 {#gs-self-service-app}

Adobe Campaign Standard與Microsoft Dynamics 365自助服務整合應用程式的整合，可讓您設定資料流程、控制資料流程是否正在執行，以及在哪個環境中執行。 不過，您必須先完成一些必要條件，才能開始使用自助服務整合應用程式。

## 概念和限制 {#concepts-and-restrictions}

開始使用整合工具之前，您必須瞭解與整合相關的概念和護欄，並採取一些初始步驟以取得存取權。

請在以下章節瞭解更多資訊：

* [開始使用Microsoft Dynamics 365整合](../../integrating/using/d365-acs-get-started.md)
* [整合最佳實務和限制](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [瞭解實作此整合的關鍵步驟](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [使用 Microsoft Dynamics 365 整合](../../integrating/using/d365-acs-using-the-integration.md)

## 先決條件 {#self-service-app-prerequisites}

您必須設定Microsoft Dynamics 365和Adobe Campaign Standard，整合應用程式才能存取您的資料。 這需要一些時間在Dynamics 365、Adobe Campaign Standard和Adobe I/O中進行設定；不過，一旦完成設定，您就能夠透過自助服務整合應用程式的使用者介面控制整合。

請在以下章節瞭解更多資訊：

* [設定Microsoft Dynamics 365以進行Campaign整合](../../integrating/using/d365-acs-configure-d365.md)
* [設定Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [對應Campaign自訂資源和Microsoft Dynamics 365自訂實體](../../integrating/using/d365-acs-notices-and-recommendations.md)

## 設定自助服務整合應用程式的關鍵步驟 {#self-service-app-configuration-steps}

接著，您就可以開始使用整合工具。 請依照下列步驟操作：

1. [存取整合應用程式](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [設定整合應用程式以符合您的使用情形](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [實作資料同步](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [設定同步工作流程](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 連結至整合應用程式 {#self-service-app-link}

開啟瀏覽器並瀏覽至與您地區相關聯的聯結器：

* [亞太地區](https://d365-acs-ap.ea.adobe.com/)
* [歐洲、中東或非洲(EMEA)](https://d365-acs-em.ea.adobe.com/)
* [美洲](https://d365-acs-am.ea.adobe.com/)

## 隱私權請求確認 {#self-service-app-acknowledgement}

第一次瀏覽至自助服務UI時，您將會收到隱私權確認。 您必須確認自己瞭解在Campaign和Microsoft Dynamics 365中分別執行隱私權要求時的角色，才能繼續。
進一步瞭解您的隱私權責任，以及如何在中管理隱私權請求 [本節](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## 設定您的認證 {#self-service-app-credentials}

第一次瀏覽UI時，應該會看到標題如下的頁面：

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> 如果尚未設定應用程式設定，通常會收到指出其「無法連線」至Adobe Campaign Standard或Microsoft Dynamics 365的警報。

請確認「ORG」和「INSTANCE」選項為您計畫設定的專案。  如果沒有，則按一下下拉式清單，然後選取正確的組織和執行個體。

>[!IMPORTANT]
>
> 如果您是第一次設定聯結器及/或您是此程式的新手，則 **強烈** 敦促您選取「階段」或「開發」例項。 在生產環境中嘗試安裝之前，請務必確認您的設定運作正常。

如果您有正確的組織和例項，則按一下「漢堡」功能表以公開下拉式功能表。 然後按一下 **[!UICONTROL Settings...]** 在下拉式功能表中，存取您輸入Microsoft Dynamics 365和Campaign認證的頁面（請參閱下文）。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

在 **[!UICONTROL Settings]** 頁面，請填寫下列區段：

* Microsoft Dynamics 365認證
* Adobe認證

前往 [此處](../../integrating/using/d365-acs-self-service-app-settings.md) 以尋找關於何處尋找每個輸入之資訊的詳細資訊。 完成後，按一下 **[!UICONTROL Save]** 底部按鈕。

## 檢查初始設定 {#self-service-app-initial-config}

假設您已完成上述必要條件，且已正確新增所有認證，我們現在導覽至 **[!UICONTROL Workflows]** 頁面。 進一步瞭解中的整合應用程式工作流程 [此頁面](../../integrating/using/d365-acs-self-service-app-workflows.md).

在  **[!UICONTROL Workflows]** 頁面上，按一下與頁面關聯的鉛筆圖示 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流程以編輯其設定。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

在 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 頁面上，您可以存取已設定的表格對應清單。  這會將您預設為現成的連絡人/設定檔對應。 所有其他自訂實體則需要個別設定。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

在 **[!UICONTROL Edit Table Mapping]** 頁面，核取 **[!UICONTROL Mappings]** 區段，確保來自Microsoft Dynamics 365的欄位會對應至Campaign中的正確欄位。 如果您需要新增任何其他對應，請立即新增，以及任何取代或篩選器。 [了解更多](../../integrating/using/d365-acs-self-service-app-data-sync.md)。

如果要新增對應，請參閱 [本節](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) 以取得詳細資訊。

設定正確後，按一下 **[!UICONTROL Play]** 按鈕旁的 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流程中，以開始整合與資料流。

>[!IMPORTANT]
>
>三 **強烈** 建議您先在預備或開發環境中執行此專案，再於生產環境中執行。 請檢查在標題中是否選取stage/dev例項。
>

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

執行後，您應該能夠在Microsoft Dynamics 365中新增或修改專案，並在幾分鐘內在Adobe Campaign中觀察這些變更，以進行測試。 如果您在任何時候需要停止此程式，則只需按一下相同的按鈕即可停止。 [了解更多](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## 整合應用程式工作區 {#self-service-app-workspace}

### 應用程式標頭 {#app-header}

自助式應用程式中的標題可讓您定義目前檢視和/或設定的組織和執行個體。

選取 **組織** 和 **例項** 您想要檢視/編輯。 這些欄位看起來是唯讀的，但是，當您將滑鼠游標放在上面時，它們會變成可編輯的。

當您按一下包含三條水平線的按鈕時，下拉式功能表將會顯示 ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) 標題的右側。

下拉式功能表中的專案包括：

* **設定**：選取此選項會傳送您到一個畫面，讓您指定Microsoft Dynamics 365和Adobe Campaign的API認證，以及應用程式的其他一般設定。

* **檔案**：此選項是此整合專用Adobe Campaign檔案的連結

* **客戶服務**：此連結會連結至與開啟客戶服務票證相關的Experience Cloud檔案

* **登出**：這會將您登出應用程式，並允許您以其他使用者的身分重新登入。

* **關於**：這會顯示一個對話方塊，其中包含有關應用程式的資訊，包括版權資訊。

### 階層連結 {#app-breadcrumbs}

當您導覽應用程式時，階層連結會出現在某些畫面的頂端。

**範例：**

以下是來自 **[!UICONTROL Edit Table Mapping]** 顯示階層連結和頁面標題的畫面。 在此情況下，您可以按一下 **[!UICONTROL Workflows]** 或 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 文字移至上一個畫面。 **[!UICONTROL Edit Table Mapping]** 在此情況下，無法點按在階層連結中，因為這是目前的畫面。

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### 常用按鈕 {#app-buttons}

自助式應用程式的多個頁面會使用下列圖示。

![](assets/do-not-localize/d365-to-acs-icon-add.png)  — 新增專案至清單。

![](assets/do-not-localize/d365-to-acs-icon-edit.png)  — 編輯已存在的專案

![](assets/do-not-localize/d365-to-acs-icon-delete.png)  — 從專案清單中刪除專案
