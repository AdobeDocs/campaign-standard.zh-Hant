---
solution: Campaign Standard
product: campaign
title: 隱私權要求
description: 瞭解如何在 Adobe Campaign Standard 中管理隱私權要求
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '1711'
ht-degree: 100%

---


# 管理隱私權要求 {#privacy-requests}

如需隱私權管理的一般簡報，請參閱[本節](../../start/using/privacy-management.md)。

此資訊適用於 GDPR、CCPA、PDPA 及 LGPD。如需這些法規的詳細資訊，請參閱[本節](../../start/using/privacy-management.md#privacy-management-regulations)。

[本節](#sale-of-personal-information-ccpa)會詳細說明專屬於 CCPA 的選擇退出個人資訊銷售。

>[!IMPORTANT]
>
>自 19.4 版本以來，不建議使用 Campaign API 和介面來存取和刪除要求。對於任何 GDPR、CPA、PDPA 或 LGPD 存取和刪除要求，您都需要使用[隱私權核心服務](#create-privacy-request)整合方法。

## 關於隱私權要求 {#about-privacy-requests}

為協助您加速隱私權準備，Adobe Campaign 可讓您處理存取和刪除要求。[本節](../../start/using/privacy-management.md#right-access-forgotten)說明&#x200B;**存取權限**&#x200B;及&#x200B;**被遺忘的權利**（刪除要求）。

若要執行那些要求，您必須使用&#x200B;**隱私權核心服務**&#x200B;整合。從「隱私權核心服務」推送至所有 Experience Cloud 解決方案的隱私權要求，會由 Campaign 透過專用的工作流程自動處理。

### 必要條件 {#prerequesites}

Adobe Campaign 提供資料控制方工具，可針對儲存在 Adobe Campaign 中的資料而建立和處理隱私權要求。然而，資料控制方有責任處理與資料主體（電子郵件、客戶服務或 Web 入口網站）的關係。

因此，身為資料控制方的您，應負責確認提出要求之資料主體的身份，並確認傳回給要求者的資料與資料主體有關。

>[!NOTE]
>
>如需關於個人資料及管理資料之不同實體（資料控制方、資料處理方和資料主體）的詳細資訊，請參閱[個人資料和人員](../../start/using/privacy.md#personal-data)。

### 命名空間 {#namesspaces}

在建立隱私權要求之前，您必須先定義要使用的命名空間。命名空間是將用於識別 Adobe Campaign 資料庫中資料主體的金鑰。現成可用的兩個命名空間：電子郵件和行動電話。如果您需要不同的命名空間（如設定檔自訂欄位），請依照下列步驟進行。

也請參閱本[教學課程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/namespaces-for-privacy-requests.html?lang=zh-Hant#privacy)，以瞭解如何建立命名空間。

>[!NOTE]
>
>如果您使用數個命名空間，您將需要為每個命名空間建立一個隱私權要求。

1. 按一下左上方的 Adobe Campaign 標誌，然後選取 **[!UICONTROL Administration]** > **[!UICONTROL Namespaces]**。

   ![](assets/privacy-namespaces.png)

1. 在命名空間清單中，按一下 **[!UICONTROL Create]**。

   ![](assets/privacy-namespace-create.png)

1. 輸入 **[!UICONTROL Label]**。

   ![](assets/privacy-namespace-label.png)

1. 如果您想使用現有的身份識別服務命名空間，請選擇 **[!UICONTROL Map from Identity Namespace Service]** 並從 **[!UICONTROL Identity Service Namespaces]** 清單選取命名空間。

   ![](assets/privacy-map-from-namespace.png)

   如果您想在 Campaign 中建立新的命名空間 **[!UICONTROL Identity Service]** 並加以對應，請選取 **[!UICONTROL Create new]** 並在 **[!UICONTROL Identity namespace name]** 欄位中輸入一個名稱。

   ![](assets/privacy-create-new-namespace.png)

   若要深入瞭解身份識別命名空間，請參閱 [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=zh-Hant) 文件。

1. 一個身份識別服務命名空間會對應至 Campaign 中的一個命名空間。您需要指定在 Campaign 中協調命名空間的方式。

   選擇目標對應（**[!UICONTROL Recipients]**、**[!UICONTROL Real-time event]** 或 **[!UICONTROL Subscriptions to an application]**）。如果您想使用數個目標對應，則需要為每個目標對應建立一個命名空間。

   ![](assets/privacy-namespace-target-mapping.png)

1. 選擇 **[!UICONTROL Reconciliation key]**。這是將用於識 別Adobe Campaign 資料庫中資料主體的欄位。

   ![](assets/privacy-namespace-reconciliation-key.png)

1. 按一下 **[!UICONTROL Create]**。您現在可以根據新的命名空間來建立隱私權要求。如果您使用數個命名空間，您將需要為每個命名空間建立一個隱私權要求。

### 建立隱私權要求 {#create-privacy-request}

>[!IMPORTANT]
>
>**隱私權核心服務**&#x200B;整合是您應用於處理所有存取和刪除要求的方法。
>
>自 19.4 版本以來，不建議使用 Campaign API 和介面來存取和刪除要求。將核心隱私權服務用於任何 GDPR、CCPA、PDPA 或 LGPD 存取及刪除要求。

「隱私權核心服務整合」可讓您透過單一 JSON API 呼叫，在多解決方案內容中自動處理您的隱私權要求。從「隱私權核心服務」推送至所有 Experience Cloud 解決方案的隱私權要求，會由 Campaign 透過專用的工作流程自動處理。

請參閱 [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hant) 文件，以瞭解如何從隱私權核心服務建立隱私權要求。

依據正在使用的命名空間數量，每個隱私權核心服務都會分割為 Campaign 中的多個隱私權要求，而一個要求都會與一個命名空間相對應。此外，一個作業可在多個執行個體上執行。因此，會針對一個作業建立多個檔案。例如，如果要求有兩個命名空間，且在三個執行個體上執行，則總共會傳送六個檔案。每個命名空間和執行個體會有一個檔案。

檔案名稱的模式是：`<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**：Campaign 執行個體名稱
* **NamespaceId**：所使用命名空間的身份識別服務命名空間 ID
* **調解金鑰**：編碼調解金鑰

### 資源清單 {#list-of-resources}

執行刪除或存取隱私權要求時，Adobe Campaign 會根據所有包含設定檔資源連結（自有類型）之資源中的&#x200B;**調解**&#x200B;值，以搜尋所有資料主體的資料。

執行隱私權要求時，以下是可列入考量的現成可用資源清單：

* 設定檔（收件者）
* 設定檔傳送記錄 (broadLogRcp)
* 設定檔追蹤記錄 (trackingLogRcp)
* 傳送記錄（應用程式的訂閱）(broadLogAppSubRcp)
* 追蹤記錄（應用程式的訂閱）(trackingLogAppSubRcp)
* 應用程式的訂閱 (appSubscriptionRcp)
* 設定檔的訂閱歷史記錄 (subHistoRcp)
* 設定檔訂閱 (subscriptionRcp)
* 訪客（訪客）

如果您建立的自訂資源具有設定檔資源（自有類型）的連結，也會將這些資源列入考量。例如，如果您有連結至設定檔資源的交易資源和連結至交易資源的交易詳細資料資源，則會同時將這些資源列入考量。

另請參閱[本教學課程](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/custom-resources-for-privacy-requests.html?lang=zh-Hant#privacy)，以瞭解如何修改自訂資源。

為了讓此功能發揮作用，您需要在自訂資源中選取 **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** 選項：

1. 按一下左上方的 Adobe Campaign 標誌，然後選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**。

1. 選擇具有設定檔資源（自有類型）之連結的自訂資源。

1. 按一下 **[!UICONTROL Links]** 區段。

1. 對於每個連結，按一下鉛筆圖示 (**[!UICONTROL Edit properties]**)。

1. 在 **[!UICONTROL Behavior if deleted/duplicated]** 區段中，選取 **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** 選項。

   ![](assets/privacy-cus-resource-option.png)

### 隱私權要求狀態 {#privacy-request-statuses}

隱私權要求的不同狀態如下：

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**：進行中，工作流程尚未處理要求。
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**：工作流程正在處理要求。
* **[!UICONTROL Delete pending]**：工作流程已識別所有要刪除的收件者資料。
* **[!UICONTROL Delete in progress]**：工作流程正在處理刪除。
   <!--**[!UICONTROL Delete Confirmation Pending]** (Delete request in 2-steps process mode): the workflow has processed the Access request. Manual confirmation is requested to perform the deletion. The button is available for 15 days.-->
* **[!UICONTROL Complete]**：要求處理已完成，並未發生錯誤。
* **[!UICONTROL Error]**：工作流程發生錯誤。原因會顯示在 **[!UICONTROL Request status]** 欄的「隱私權要求」清單中。例如，**[!UICONTROL Error data not found]** 表示在資料庫中找不到與資料主體 **[!UICONTROL Reconciliation value]** 相符的收件者資料。

### 停用兩步驟程序 {#disabling-two-step-process}

核心隱私權服務不支援兩步驟程序。

>[!IMPORTANT]
>
>在使用「核心隱私權服務」整合以管理您的隱私權要求之前，您必須先從 Campaign Standard 介面停用刪除要求的兩步驟程序。

如果尚未停用此選項，則使用「隱私權核心服務」管理的所有刪除要求都將保持擱置中狀態，且將無法完成。

依預設，會啟動兩步驟程序。

若要變更此模式，請按一下 **[!UICONTROL Privacy Requests]** 畫面右上方的 **[!UICONTROL Edit properties]**，然後取消勾選 **[!UICONTROL Activate the 2-step process]** 選項。

![](assets/privacy-disable-2-step-process.png)

## 選擇退出個人資訊銷售 (CCPA) {#sale-of-personal-information-ccpa}

**加州消費者隱私保護法 (CCPA)** 為加州居民提供新的個資權利，並對在加州經營業務的特定實體賦予資料保護責任。

GDPR 和 CCPA 都很常使用存取及刪除要求的設定與使用情況。本節說明專屬於 CCPA 的選擇退出個人資訊銷售。

除了 Adobe Campaign 提供的[同意管理](../../start/using/privacy-management.md#consent-management)工具以外，您還可以追蹤消費者是否選擇退出個人資訊銷售。

消費者透過您的系統決定其不允許將個人資訊銷售給第三方。在 Adobe Campaign 中，您將能儲存及追蹤此資訊。

>[!NOTE]
>
>您可以透過 Campaign 介面及 API，善用選擇退出個人資訊銷售。您無法透過「隱私權核心服務」使用此功能。

>[!IMPORTANT]
>
>您身為資料控制方，有責任接收資料主體的要求並追蹤 CCPA 的要求日期。身為技術提供者，我們只提供選擇退出的方式。有關您擔任資料控制方的詳細資訊，請參閱[個人資料和角色](../../start/using/privacy.md#personal-data)。

### 自訂表格的先決條件 {#ccpa-prerequisite}

從 19.4 版本以來，Campaign 介面及 API 中可立即使用 **[!UICONTROL CCPA Opt-Out]** 欄位。依預設，此欄位適用於標準 **[!UICONTROL Profile]** 資源。

如果您使用自訂設定檔資源，則需要擴充資源並新增欄位。我們建議您使用與現成可用欄位不同的名稱，例如：**[!UICONTROL Opt-Out for CCPA]** (optouccpa)。建立新欄位時，Campaign API 會自動支援該欄位。

如需如何擴充設定檔資源的詳細資訊，請參閱[本節](../../developing/using/extending-the-profile-resource-with-a-new-field.md)。

>[!NOTE]
>
>修改資源是敏感性作業，此作業僅能由專家使用者執行。

1. 前往 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**。按一下自訂設定檔資源。如需擴充資源的詳細資訊，請參閱[本節](../../developing/using/creating-or-extending-the-resource.md)。

   ![](assets/privacy-ccpa-extend-cus.png)

1. 按一下 **[!UICONTROL Add field]** 或 **[!UICONTROL Create Element]**、新增標籤、ID 並選擇 **[!UICONTROL Boolean]** 類型。對於名稱，請使用 **Opt-Out for CCPA**。對於 ID，請使用：**optOutCcpa**。

   ![](assets/privacy-ccpa-extend-field.png)

1. 在 **[!UICONTROL Screen definition]** 索引標籤的 **[!UICONTROL Detail screen configuration]** 下方，新增欄位並選取 **[!UICONTROL Input field]**。如此即可在設定檔清單及詳細資料中使用該欄位。如需設定螢幕定義的詳細資訊，請參閱[本節](../../developing/using/configuring-the-screen-definition.md)。

   ![](assets/privacy-ccpa-extend-screen.png)

1. 前往 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**，準備出版物並發佈修改。如需發佈資源的詳細資訊，請參閱[本節](../../developing/using/updating-the-database-structure.md)。

   ![](assets/privacy-ccpa-extend-pub.png)

1. 確認該欄位是否可用於設定檔的詳細資料。如需詳細資訊，請參閱[本節](#usage)。

### 使用情況 {#usage}

資料控制方應負責填入欄位的值，並遵循關於資料銷售的 CCPA 準則和規則。

若要填入值，可使用數種方法：

* 編輯收件者的詳細資料，以使用 Campaign 的介面（請參閱以下內容）
* 使用 Campaign 隱私權 API（請參閱 [API 文件](../../api/using/managing-ccpa-opt-out.md)）
* 透過資料匯入工作流程

之後，您應該確保您絕對不會向已選擇退出之任何第三方銷售設定檔的個人資訊。

1. 在 Campaign 介面中，編輯設定檔以變更選擇退出狀態。

   ![](assets/privacy-ccpa-profile-opt-out.png)

1. 如果欄位值為 **[!UICONTROL True]**，資訊會顯示在設定檔的詳細資料上。

   ![](assets/privacy-ccpa-profile-opt-out-true.png)

1. 您可以將設定檔清單設定為顯示選擇退出欄。若要瞭解如何設定清單，請參閱[本節](../../start/using/customizing-lists.md)。

   ![](assets/privacy-ccpa-profile-configure-list.png)

1. 您可以按一下該欄，以依據選擇退出資訊來排序收件者。

   ![](assets/privacy-ccpa-profile-sorting.png)
