---
title: 使用 Microsoft Dynamics 365 整合
description: 了解如何使用Microsoft Dynamics 365與Campaign Standard整合
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---

# 使用Microsoft Dynamics 365整合

Adobe Campaign Standard與Microsoft Dynamics 365整合可執行數個資料流程。 此等流量於 [本頁](../../integrating/using/d365-acs-self-service-app-workflows.md).

有關資料流的更多詳細資訊，請參閱 [資料流](#data-flows)  區段。

## Adobe Campaign Standard使用者體驗

在Microsoft Dynamics 365中建立、修改或刪除連絡人（如果已啟用）時，系統會將其傳送至Campaign Standard。 這些連絡人將顯示在Campaign的「設定檔」畫面中，並可在行銷活動中定位。 請參閱下方的設定檔畫面。

![](assets/MSdynamicsACS-usage1.png)

在Campaign中修改選擇退出屬性時，如果您已選取 **單向(促銷活動至Microsoft Dynamics 365)** 或 **雙向** 選擇退出設定，以及正確對應特定屬性的選項。

## Microsoft Dynamics 365使用者體驗

如需輸出，下列電子郵件行銷事件會從Campaign傳送至Dynamics 365，並以自訂活動形式顯示在Microsoft Dynamics 365時間軸檢視中：

* Adobe Campaign電子郵件傳送

* Adobe Campaign電子郵件開啟

* Adobe Campaign電子郵件URL點按

* Adobe Campaign電子郵件跳出

要查看聯繫人的時間表，請按一下Dynamics 365下拉菜單中的Sales Hub以導航到您的聯繫人清單。 然後按一下左側菜單欄上的「聯繫人」並選擇聯繫人。

>[!NOTE]
>
>此 **Adobe Campaign for Microsoft Dynamics 365** 您必須在Microsoft Dynamics 365執行個體中安裝AppSource中的應用程式，才能檢視這些事件。 [深入瞭解](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app)。

下面是「Dynamics User」的「聯繫人」螢幕的快照。 在「時間軸」檢視中，您會發現Dynamics使用者已傳送與促銷活動名稱「2019LoyatyCamp」和傳送名稱「DM190」相關聯的電子郵件。 Dynamics使用者開啟電子郵件，也按一下電子郵件中的URL;這兩個動作都會建立事件，其也顯示於下方。 如果你往右看，你會看到「關係助理(RA)」卡；目前，它包含要追蹤已點按URL的工作。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

有關Dynamics用戶的時間軸視圖的特寫，請參見下面。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下是「關係助理(RA)」卡的特寫。 AppSource應用程式包含監視Adobe電子郵件URL點按事件的工作流程。 發生此事件時，會建立任務並設定到期日。 這可讓任務顯示在RA卡中，讓其更具可見性。 「Adobe電子郵件退信」事件的工作流程類似，會新增一項任務來調解無效的電子郵件地址。 解決方案中可關閉這些工作流程。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

如果您按一下傳送事件的主題，您會看到類似下方的表單。 開啟和彈回事件的表單類似。

![](assets/do-not-localize/mirror_page_url_send.png)

電子郵件url點按事件的表單會為已點按的URL新增一個額外屬性：

![](assets/do-not-localize/mirror_page_url_click.png)

以下是屬性清單和說明：

* **主旨**:活動主體；由電子郵件傳送的促銷活動ID和傳送ID組成

* **擁有者**:在布建後步驟中建立的應用程式用戶

* **關於**:聯繫人的姓名

* **促銷活動名稱**:促銷活動ID(Campaign Standard)

* **傳送名稱**:傳遞IDCampaign Standard

* **傳送/開啟/點按/跳出日期**:建立事件的日期/時間

* **追蹤URL**:已點按的URL

* **鏡像頁面URL**:已傳送/開啟/點按/退信之電子郵件的鏡像頁面的URL。 您可以在對應Campaign電子郵件通道活動的設定畫面中修改電子郵件鏡像頁面的到期期間。 [深入瞭解](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

>[!NOTE]
>
>若為退出，當在Microsoft Dynamics 365中修改了退出屬性時，如果您選取 **單向(促銷活動至Microsoft Dynamics 365)** 或 **雙向** 選擇退出設定，以及正確對應特定屬性的選項。

## 資料流 {#data-flows}

### 聯繫人和自定義實體入口

新記錄、更新記錄和刪除記錄(注意：必須啟用刪除)，會從Microsoft Dynamics 365聯絡資料表格傳送至Campaign設定檔表格。

可在整合應用程式UI中設定表格對應，以將Microsoft Dynamics 365表格屬性對應至Campaign表格屬性。 可視需要修改表格對應以新增/移除屬性。

資料流的初始運行旨在傳輸所有映射記錄，包括標籤為「非活動」的記錄；隨後，整合將僅處理增量更新。 例外情況是重播資料或設定篩選器時；可以設定基本、基於屬性的篩選規則，以決定要同步至Campaign的記錄。

基本取代規則可在整合應用程式UI中設定，以用不同的值取代屬性值(例如，&quot;#00FF00&quot;為&quot;green&quot;,1為&quot;F&quot;等)。

視記錄數量而定，您的Campaign SFTP儲存空間可能需要用於初始資料傳輸。 [深入瞭解](#initial-data-transfer)。

Campaign設定檔表格屬性externalId必須填入Dynamics 365聯絡人屬性contactId，才能讓聯絡人進入運作。 促銷活動自訂實體也必須填入Dynamics 365唯一ID屬性；不過，此屬性可儲存在任何Campaign自訂實體屬性中（亦即不必是externalId）。

>[!NOTE]
>
>對於自訂實體入口，必須在Dynamics 365中為同步的自訂實體啟用變更追蹤。

#### 自訂實體

此 [Microsoft Dynamics 365-Adobe Campaign Standard整合](../../integrating/using/d365-acs-get-started.md) 支援自訂實體，讓Dynamics 365中的自訂實體同步至Campaign中對應的自訂資源。

自訂資源中的新資料可用於數個用途，包括細分和個人化。

整合支援連結和非連結的表格。 最多支援三個層級（即level1->level2->level3）的連結。

>[!IMPORTANT]
>
>如果任何Campaign自訂資源記錄包含個人資訊，則會套用特定建議。 深入了解 [在本節](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).

設定自訂實體資料流程時，請務必注意下列事項：

* 建立和修改Campaign自訂資源是敏感操作，只能由專家使用者執行。
* 對於自訂實體資料流，必須在Dynamics 365中為同步的自訂實體啟用變更追蹤。
* 如果在Dynamics 365中建立父記錄和連結的子記錄時間接近同一時間，由於並行處理整合，則在其父記錄之前，將新子記錄寫入Campaign的機會很小。

* 如果父項和子項在促銷活動端連結，則使用 **1個基數簡單連結** 選項，則子記錄在父記錄到達Campaign之前，將會保持隱藏且無法存取（透過UI或API）。

* (假設 **1個基數簡單連結** （在促銷活動中）如果子記錄在Dynamics 365中更新或刪除，且該變更在父記錄在促銷活動中顯示之前（不可能，但是可能是遠端）已寫入促銷活動，則該更新或刪除不會在促銷活動中處理，且會擲回錯誤。 如果是更新，則需要在Dynamics 365中再次更新相關記錄，以便同步更新的記錄。 如果是刪除，則需要在促銷活動端個別處理相關記錄，因為Dynamics 365中已沒有記錄可刪除或更新。

* 如果您遇到您認為隱藏了子記錄且無法存取這些記錄的情況，您可以暫時將基數連結類型變更為 **0或1個基數簡單連結** 來存取那些記錄。

您可以找到Campaign自訂資源的更完整概觀 [在本節](../../developing/using/key-steps-to-add-a-resource.md).

### 電子郵件行銷事件流程{#email-marketing-event-flow}

電子郵件行銷事件會從Campaign傳送至Microsoft Dynamics 365，以顯示在時間軸檢視中。

支援的行銷事件類型：
* 傳送 — 傳送電子郵件給收件者
* 開啟 — 收件者開啟的電子郵件
* 按一下 — 收件者點按之電子郵件內的URL
* 彈回數 — 傳送給收件者的電子郵件出現硬跳出

Dynamics 365中會顯示下列事件屬性：
* 行銷活動名稱
* 電子郵件傳送名稱
* 時間戳記
* 電子郵件鏡像頁面URL
* 已點按URL（僅限點按事件）

電子郵件行銷事件可以依類型來啟用/停用（傳送、開啟、按一下、退信），這樣只有您選取的事件類型才會傳遞至Dynamics 365。

### 退出流程 {#opt-out-flow}

退出（例如denyList）值會在系統之間同步；上線時，您可以選擇下列選項：

* **單向(Microsoft Dynamics 365至Campaign)**:Dynamics 365是退出的真相來源。 退出屬性將從Dynamics 365同步到Campaign Standard。」
* **單向(促銷活動至Microsoft Dynamics 365)**:Campaign Standard是退出的真相來源。 退出屬性將從Campaign Standard同步到Dynamics 365
* **雙向**:Dynamics 365和Campaign Standard都是真理的源泉。 退出屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有獨立的程式來管理系統之間的選擇退出同步，則可停用整合的選擇退出資料流程。

>[!NOTE]
>
>在整合應用程式UI中， **單向(Microsoft Dynamics 365至Campaign)** 和 **雙向** 退出使用案例會在個別的退出工作流程中設定。 [深入瞭解](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。
>
>此 **單向(促銷活動至Microsoft Dynamics 365)** 選擇退出使用案例是例外；它是在入口（聯絡至設定檔）工作流程中設定。

由於公司之間的業務需求可能不同，因此客戶需指定選擇退出流程對應。 在Campaign端，只能使用OOTB選擇退出屬性來進行選擇退出對應：

* denyList
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

在Dynamics 365中，大部分的退出欄位都有「donot」首碼；不過，如果資料類型相容，您也可以利用其他屬性來選擇退出。

### 初始資料傳輸 {#initial-data-transfer}

初始資料傳輸可能需要一段時間，具體取決於您從Microsoft Dynamics 365擷取的記錄數。 初始資料傳輸後，整合會擷取增量更新。
