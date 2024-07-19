---
title: 使用 Microsoft Dynamics 365 整合
description: 瞭解如何使用Microsoft Dynamics 365進行Campaign Standard整合
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 0%

---

# 使用Microsoft Dynamics 365整合

Adobe Campaign Standard與Microsoft Dynamics 365整合可執行數個資料流程。 這些流程在[此頁面](../../integrating/using/d365-acs-self-service-app-workflows.md)中有詳細說明。

有關資料流程的更多詳細資訊，請參閱此檔案[資料流程](#data-flows)區段中的更下層。

## Adobe Campaign Standard使用者體驗

在Microsoft Dynamics 365中建立、修改或刪除（如果已啟用刪除）連絡人時，就會將其傳送至Campaign Standard。 這些連絡人將顯示在Campaign的「設定檔」畫面中，並可在行銷活動中定位。 請參閱下方的「設定檔」畫面。

![](assets/MSdynamicsACS-usage1.png)

在Campaign中修改選擇退出屬性時，如果您已選取&#x200B;**單向(Campaign至Microsoft Dynamics 365)**&#x200B;或&#x200B;**雙向**&#x200B;選擇退出設定，而且您已正確對應該特定屬性，則會反映在Dynamics 365中。

## Microsoft Dynamics 365使用者體驗

對於輸出，下列電子郵件行銷事件會從Campaign傳送至Dynamics 365，並在Microsoft Dynamics 365時間軸檢視中顯示為自訂活動：

* Adobe Campaign電子郵件傳送

* Adobe Campaign電子郵件開啟

* Adobe Campaign電子郵件URL點按

* Adobe Campaign電子郵件跳出

若要檢視連絡人的時間表，請從Dynamics 365下拉式功能表中按一下「銷售中心」，以瀏覽至您的連絡人清單。 然後按一下左側功能表列上的[連絡人]並選取連絡人。

>[!NOTE]
>
>AppSource中的&#x200B;**Adobe Campaign for Microsoft Dynamics 365**&#x200B;應用程式必須安裝在您的Microsoft Dynamics 365執行個體中，才能檢視這些事件。 [了解更多](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app)。

您可以在下方看到「Dynamics使用者」的「連絡人」畫面快照。 在「時間軸」檢視中，您會注意到Dynamics使用者已收到與行銷活動名稱「2019LoyaltyCamp」和傳送名稱「DM190」相關聯的電子郵件。 Dynamics使用者已開啟電子郵件並按一下電子郵件中的URL；這兩個動作都會建立事件，也會顯示如下。 如果往右邊看，就會看到關係小幫手(RA)卡；目前包含要追蹤已點按URL的工作。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

如需Dynamics使用者的「時間軸」檢視的特寫，請參閱下文。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下是關係助理(RA)卡的特寫。 AppSource應用程式包含的工作流程會監視Adobe的電子郵件URL點按事件。 發生此事件時，會建立任務並設定到期日。 如此可讓工作顯示在RA卡中，讓工作具有額外的可見度。 Adobe電子郵件退回事件有類似的工作流程，新增工作以調解無效的電子郵件地址。 解決方案中可關閉這些工作流程。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

如果您按一下傳送事件的主旨，您會看到類似下列的表單。 開啟和跳出事件的表單類似。

![](assets/do-not-localize/mirror_page_url_send.png)

電子郵件URL點選事件的表單會為點選的URL新增另一個屬性：

![](assets/do-not-localize/mirror_page_url_click.png)

以下是屬性清單和說明：

* **主旨**：事件的主旨；由電子郵件傳遞的行銷活動ID和傳遞ID組成

* **所有者**：在布建後步驟中建立的應用程式使用者

* **關於**：連絡人的名稱

* **促銷活動名稱**：Campaign Standard中的促銷活動識別碼

* **傳遞名稱**：Campaign Standard的傳遞識別碼

* **傳送/開啟/點按/退出的日期**：事件建立的日期/時間

* **追蹤URL**：已點按的URL

* **映象頁面URL**：已傳送/開啟/按一下/退回之電子郵件的映象頁面URL。 您可以在對應的Campaign電子郵件通道活動的設定畫面中修改電子郵件映象頁面的到期日。 [了解更多](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

>[!NOTE]
>
>針對選擇退出，當您在Microsoft Dynamics 365中修改選擇退出屬性時，如果您選取&#x200B;**單向(Campaign至Microsoft Dynamics 365)**&#x200B;或&#x200B;**雙向**&#x200B;選擇退出設定，而且您已正確對應該特定屬性，則會反映在Campaign中。

## 資料流程 {#data-flows}

### 連絡人和自訂實體入口

新的、更新的和刪除的記錄（注意：必須啟用刪除功能）會從Microsoft Dynamics 365聯絡人表格傳送至Campaign設定檔表格。

您可在整合應用程式UI中設定表格對應，將Microsoft Dynamics 365表格屬性對應至Campaign表格屬性。 您可以視需要修改表格對應，以新增/移除屬性。

資料流程的初始執行旨在傳輸所有對應記錄，包括標籤為「非使用中」的記錄；隨後，整合只會處理增量更新。 但如果重播資料或設定了篩選器，則屬例外；您可以設定以屬性為基礎的基本篩選規則，以決定要將哪些記錄同步至Campaign。

您可以在整合應用程式UI中設定基本取代規則，以不同的值取代屬性值(例如「#00FF00」代表「綠色」，「1代表「F」等)。

視記錄數量而定，您可能需要使用Campaign SFTP儲存空間進行初始資料傳輸。 [了解更多](#initial-data-transfer)。

Campaign設定檔表格屬性externalId必須填入Dynamics 365連絡人屬性contactId，連絡人入口才能運作。 行銷活動自訂實體也必須填入Dynamics 365唯一ID屬性；不過，此屬性可儲存在任何Campaign自訂實體屬性中（亦即，不須為externalId）。

>[!NOTE]
>
>對於自訂實體輸入，必須在Dynamics 365中為同步的自訂實體啟用變更追蹤。

#### 自訂實體

[Microsoft Dynamics 365-Adobe Campaign Standard整合](../../integrating/using/d365-acs-get-started.md)支援自訂實體，可讓Dynamics 365中的自訂實體同步處理至Campaign中對應的自訂資源。

自訂資源中的新資料可用於多種用途，包括細分和個人化。

整合約時支援連結表格和非連結表格。 最多支援三個層級（即level1->level2->level3）的連結。

>[!IMPORTANT]
>
>如果任何Campaign自訂資源記錄包含個人資訊，則套用特定建議。 在本節](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data)瞭解更多[。
>

設定自訂實體資料流程時，請務必注意下列事項：

* 建立和修改Campaign自訂資源是敏感性作業，僅能由專家使用者執行。
* 對於自訂實體資料流程，必須在Dynamics 365中為同步的自訂實體啟用變更追蹤。
* 如果在Dynamics 365中幾乎同時建立父記錄和連結的子記錄，則由於平行處理整合，將新子記錄寫入其父記錄之前的可能性微乎其微。

* 如果使用&#x200B;**1基數簡單連結**&#x200B;選項在Campaign端連結父項和子項，在父項記錄到達Campaign之前，子項記錄將保持隱藏狀態且無法存取（透過UI或API）。

* （假設Campaign中有&#x200B;**1個基數簡單連結**）若子記錄在Dynamics 365中更新或刪除，且該變更在父記錄出現在Campaign之前寫入Campaign （不大可能，但可能有遠端可能），則不會在Campaign中處理該更新或刪除，且將會擲回錯誤。 如果更新，需要在Dynamics 365中再次更新有問題的記錄，才能同步處理更新的記錄。 刪除時，由於在Dynamics 365中不再有要刪除或更新之記錄，因此需要在Campaign端個別處理有問題的記錄。

* 如果您認為您有隱藏的子記錄，且無法存取這些記錄，您可以暫時將基數連結型別變更為&#x200B;**0或1個基數簡單連結**，以存取這些記錄。

如需更全面的Campaign自訂資源概觀，請參閱本節[](../../developing/using/key-steps-to-add-a-resource.md)。

### 電子郵件行銷事件流程{#email-marketing-event-flow}

電子郵件行銷事件會從Campaign傳送至Microsoft Dynamics 365，以顯示在時間表檢視中。

支援的行銷事件型別：
* 傳送 — 電子郵件已傳送給收件者
* 開啟 — 收件者開啟的電子郵件
* 點按 — 收件者點按的電子郵件內的URL
* 退回 — 傳送給收件者的電子郵件出現硬退回

下列事件屬性會顯示在Dynamics 365中：
* 行銷活動名稱
* 電子郵件傳遞名稱
* 時間戳記
* 電子郵件映象頁面URL
* URL點按（僅限點按事件）

您可依型別（傳送、開啟、按一下、退回）啟用/停用電子郵件行銷事件，以便只有您選取的事件型別會傳遞至Dynamics 365。

### 選擇退出流程 {#opt-out-flow}

選擇退出（例如denyList）值會在系統之間同步；上線時，您可以選擇下列選項：

* **單向(Microsoft Dynamics 365至Campaign)**： Dynamics 365是選擇退出的信任來源。 選擇退出屬性會從Dynamics 365同步至Campaign Standard」
* **單向(從Campaign到Microsoft Dynamics 365)**：Campaign Standard是選擇退出的真實來源。 選擇退出屬性將會在從Campaign Standard到Dynamics 365的一個方向上同步
* **雙向**： Dynamics 365和Campaign Standard都是真實來源。 選擇退出屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有個別程式可管理系統之間的選擇退出同步，則可停用整合的選擇退出資料流程。

>[!NOTE]
>
>在整合應用程式UI中，**單向(Microsoft Dynamics 365至Campaign)**&#x200B;和&#x200B;**雙向**&#x200B;選擇退出使用案例是在單獨的選擇退出工作流程中設定的。 [了解更多](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。
>
>**單向(Campaign to Microsoft Dynamics 365)**&#x200B;選擇退出使用案例是例外狀況；它是在入口（聯絡至設定檔）工作流程中設定。
>

選擇退出流程對應將由客戶指定，因為公司之間的業務需求可能不同。 在Campaign端，只有OOTB選擇退出屬性可用於選擇退出對應：

* denyList
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpapoptout

在Dynamics 365中，大部分的選擇退出欄位都有「donot」前置詞；不過，如果資料型別相容，您也可以使用其他屬性作為選擇退出的用途。

### 初始資料傳輸 {#initial-data-transfer}

視您從Microsoft Dynamics 365擷取的記錄數量而定，初始資料傳輸可能需要一段時間。 初始資料傳輸後，整合將會採用增量更新。
