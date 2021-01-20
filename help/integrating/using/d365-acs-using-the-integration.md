---
title: 使用 Microsoft Dynamics 365 整合
description: 瞭解如何搭配Campaign Standard整合使用Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---


# 使用Microsoft Dynamics 365整合

Adobe Campaign Standard與Microsoft Dynamics 365整合會執行數種資料流。 這些流在[本頁](../../integrating/using/d365-acs-self-service-app-workflows.md)中有詳細說明。

有關資料流的詳細資訊，請參閱本文檔的[資料流](#data-flows)部分。

## Adobe Campaign Standard使用者體驗

在Microsoft Dynamics 365中建立、修改或刪除連絡人（如果已啟用刪除）時，該連絡人會傳送至Campaign Standard。 這些連絡人會顯示在促銷活動的「設定檔」畫面中，並可定位在行銷促銷活動中。 請參閱下方的「描述檔」畫面。

![](assets/MSdynamicsACS-usage1.png)

當促銷活動中修改選擇退出屬性時，如果您已選取「單向(Campaign to Microsoft Dynamics 365)」「單向(Campaign to Microsoft Dynamics 365)」「a1/」或「**雙向」「選擇退出」設定，且您已正確映射該特定屬性，則此屬性會反映在Dynamics 365。******

## Microsoft Dynamics 365使用者體驗

如需出口，下列電子郵件行銷事件會從Campaign傳送至Dynamics 365，並在Microsoft Dynamics 365時間軸檢視中顯示為自訂活動：

* Adobe Campaign電子郵件傳送

* Adobe Campaign電子郵件開啟

* Adobe Campaign電子郵件URL點按

* Adobe Campaign電子郵件彈回數

若要檢視連絡人的時間軸，請按一下Dynamics 365下拉式選單中的Sales Hub，以導覽至您的連絡人清單。 然後，按一下左側菜單欄上的「聯繫人」並選擇聯繫人。

>[!NOTE]
>
>AppSource中的&#x200B;**Adobe Campaign for Microsoft Dynamics 365**&#x200B;應用程式必須安裝在您的Microsoft Dynamics 365例項中，才能檢視這些事件。 [進一步瞭解](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app)。

下面是「Dynamics User」的「Contact」（聯繫人）螢幕快照。 在「時間軸」檢視中，您會注意到Dynamics使用者已寄送電子郵件，與促銷活動名稱「2019LoyaltyCamp」和傳送名稱「DM190」相關。 Dynamics使用者開啟電子郵件，並點選了電子郵件中的URL;這兩個動作都會建立事件，如下所示。 如果您往右拐，就會看到「關係助理」(RA)卡；目前，它包含要追蹤所點按URL的工作。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

請參閱以下，以取得動態使用者時間軸檢視的詳細資訊。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下是關係助理(RA)卡的特寫。 AppSource應用程式包含會監視Adobe電子郵件URL點按事件的工作流程。 發生此事件時，它會建立工作並設定到期日。 這可讓工作顯示在RA卡中，讓它更加可見。 Adobe電子郵件彈回數事件的工作流程類似，新增了協調無效電子郵件地址的任務。 這些工作流程可在解決方案中關閉。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

如果您按一下傳送事件的主題，您會看到類似下方的表格。 開啟和彈回事件的表格類似。

![](assets/do-not-localize/mirror_page_url_send.png)

電子郵件URL點按事件的表單會為被點按的URL新增其他屬性：

![](assets/do-not-localize/mirror_page_url_click.png)

以下是屬性清單和說明：

* **主旨**:活動主體；由電子郵件傳送的促銷活動ID和傳送ID組成

* **擁有者**:在布建後步驟中建立的應用程式用戶

* **關於**:連絡人姓名

* **促銷活動名稱**:Campaign Standard中的促銷活動ID

* **傳送名稱**:Campaign Standard中的傳送ID

* **傳送／開啟／點按／退回日期**:建立事件的日期／時間

* **追蹤URL**:已點按的URL

* **鏡像頁面URL**:傳送／開啟／點按／彈回之電子郵件之鏡像頁面的URL。電子郵件鏡像頁面的到期期間可在對應的「促銷活動」電子郵件渠道活動的設定畫面中修改。 [進一步瞭解](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

>[!NOTE]
>
>對於選擇退出，當在Microsoft Dynamics 365中修改選擇退出屬性時，如果您選取了&#x200B;**單向(Campaign to Microsoft Dynamics 365)**&#x200B;或&#x200B;**雙向**&#x200B;選擇退出配置，並且您正確映射了該特定屬性，則該屬性會反映在促銷活動中。

## 資料流{#data-flows}

### 連絡人與自訂實體入口

新記錄、更新記錄和刪除記錄(注意：必須啟用)，從Microsoft Dynamics 365連絡人表格傳送至「促銷活動」描述檔表格。

可在整合應用程式UI中設定表格映射，以將Microsoft Dynamics 365表格屬性對應至促銷活動表格屬性。 可根據需要修改表映射以添加／刪除屬性。

資料流的初始運行旨在傳輸所有映射記錄，包括標籤為「非活動」的記錄；之後，整合將只處理增量更新。 例外情況是，如果重播資料或設定篩選器；基本、屬性型的篩選規則可加以設定，以決定要同步至促銷活動的記錄。

基本取代規則可在整合應用程式UI中設定，以不同的值取代屬性值（例如，「#00FF00」的「綠色」、「F」代表1等）。

視記錄量而定，您的促銷活動SFTP儲存空間可能需要用於初始資料傳輸。 [進一步瞭解](#initial-data-transfer)。

Campaign描述檔表格屬性externalId必須填入Dynamics 365 Contact屬性contactId，才能讓連絡人進入工作。 促銷活動自訂實體也必須填入Dynamics 365唯一ID屬性；不過，此屬性可儲存在任何促銷活動自訂實體屬性中（亦即不必是externalId）。

>[!NOTE]
>
>對於自訂實體入口，必須在Dynamics 365中為同步化的自訂實體啟用變更追蹤。

#### 自訂實體

[Microsoft Dynamics 365-Adobe Campaign Standard整合](../../integrating/using/d365-acs-get-started.md)支援自訂實體，讓Dynamics 365中的自訂實體與Campaign中的對應自訂資源同步。

自訂資源中的新資料可用於數種用途，包括分段和個人化。

整合支援連結和非連結的表格。 連結最多支援三個級別（即級別1->級別2->級別3）。

>[!IMPORTANT]
>
>如果任何促銷活動自訂資源記錄包含個人資訊，則會套用特定建議。 瞭解本節](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data)的更多資訊。[


設定自訂實體資料流時，請務必注意下列事項：

* 建立和修改促銷活動自訂資源是敏感作業，必須由專業使用者執行。
* 對於自訂實體資料流，必須在Dynamics 365中為同步化的自訂實體啟用變更追蹤。
* 如果在Dynamics 365中建立父記錄和連結的子記錄時，由於並行處理整合，因此在其父記錄之前，可能會將新的子記錄寫入Campaign。

* 如果父記錄和子記錄使用&#x200B;**1基數簡單連結**&#x200B;選項在促銷活動方面連結，子記錄將保持隱藏且無法存取（透過UI或API），直到父記錄到達Campaign。

* （假設促銷活動中&#x200B;**1基數簡單連結**）如果子記錄在Dynamics 365中更新或刪除，且該變更在父記錄顯示於促銷活動之前已寫入促銷活動（不可能，但是遠端可能），該更新或刪除不會在促銷活動中處理，且會擲回錯誤。 在更新時，相關記錄需要在Dynamics 365中再次更新，才能同步更新的記錄。 若是刪除，相關記錄需要在促銷活動端個別處理，因為Dynamics 365中不再有要刪除或更新的記錄。

* 如果您遇到您認為有隱藏的子記錄而無法訪問這些記錄的情況，可以暫時將基數連結類型更改為&#x200B;**0或1基數簡單連結**&#x200B;以訪問這些記錄。

有關促銷活動自訂資源的更完整概觀，請參閱本節[。](../../developing/using/key-steps-to-add-a-resource.md)

### 電子郵件行銷事件流程{#email-marketing-event-flow}

電子郵件行銷事件會從Campaign傳送至Microsoft Dynamics 365，以顯示在時間軸檢視中。

支援的行銷事件類型：
* 傳送——電子郵件傳送給收件者
* 開啟——收件者開啟的電子郵件
* 按一下——收件者點按之電子郵件內的URL
* 彈回數——傳送給收件者的電子郵件出現硬反彈

Dynamics 365中會顯示下列事件屬性：
* 行銷宣傳名稱
* 電子郵件傳送名稱
* 時間戳記
* 電子郵件鏡像頁面URL
* 點按的URL（僅限點按事件）

電子郵件行銷事件可依類型啟用／停用（傳送、開啟、按一下、彈回），因此只有您選取的事件類型才會傳遞至Dynamics 365。

### 退出流{#opt-out-flow}

退出（如denyList）值在系統之間同步；您有下列選項可在上線時選擇：

* **單向(Microsoft Dynamics 365 to Campaign)**:Dynamics 365是退出的真相。退出屬性將會在從Dynamics 365到Campaign Standard的單一方向上同步化」
* **單向（促銷活動至Microsoft Dynamics 365）**:「促銷活動標準」是退出的真相來源。退出屬性將會在從Campaign Standard到Dynamics 365的一個方向上同步
* **雙向**:Dynamics 365 AND Campaign Standard是真相的來源。退出屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有個別的程式來管理系統之間的退出同步，則可停用整合的退出資料流。

>[!NOTE]
>
>在整合應用程式UI中，在個別的退出工作流程中，設定&#x200B;**單向(Microsoft Dynamics 365 to Campaign)**&#x200B;和&#x200B;**雙向**&#x200B;選擇退出使用案例。 [進一步瞭解](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。
>
>**單向(Campaign to Microsoft Dynamics 365)**&#x200B;選擇退出使用案例是例外；它是在入口（連絡至描述檔）工作流程中設定。


選擇退出流程映射由客戶指定，因為不同公司的業務需求可能不同。 在促銷活動方面，只有OOTB選擇退出屬性可用於選擇退出對應：

* denyList
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPush通知
* ccpaOptOut

在Dynamics 365中，大多數選擇退出欄位都有「donot」字首；但是，如果資料類型相容，您也可以利用其他屬性來選擇退出。

### 初始資料傳輸{#initial-data-transfer}

初始資料傳輸可能需要一段時間，具體取決於您從Microsoft Dynamics 365中接收的記錄數。 在初始資料傳輸後，整合將會擷取增量更新。
