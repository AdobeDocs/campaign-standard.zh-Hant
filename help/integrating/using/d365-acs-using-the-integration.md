---
title: 使用 Microsoft Dynamics 365 整合
description: 瞭解如何將MicrosoftDynamics 365與Campaign Standard整合一起使用
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

# 使用MicrosoftDynamics 365整合

Adobe Campaign Standard與MicrosoftDynamics 365整合可執行若干資料流。 這些流在 [此頁](../../integrating/using/d365-acs-self-service-app-workflows.md)。

有關資料流的更多詳細資訊，請參閱 [資料流](#data-flows)  的子菜單。

## Adobe Campaign Standard用戶體驗

在MicrosoftDynamics 365中建立、修改或刪除聯繫人（如果已啟用刪除）時，該聯繫人將被發送到Campaign Standard。 這些聯繫人將在市場活動的「概要檔案」螢幕中可見，並可以在市場營銷活動中定向。 請參閱下面的「配置式」螢幕。

![](assets/MSdynamicsACS-usage1.png)

在「市場活動」中修改opt-out屬性時，如果選擇了 **單向(MicrosoftDynamics 365營銷活動)** 或 **雙向** opt-out配置，如果正確映射了該特定屬性。

## MicrosoftDynamics 365用戶體驗

對於出口，以下電子郵件營銷事件將從「市場活動」發送到Dynamics 365，並作為自定義活動顯示在「MicrosoftDynamics 365時間軸」視圖中：

* Adobe Campaign電子郵件發送

* Adobe Campaign電子郵件開啟

* Adobe Campaign電子郵件URL按一下

* Adobe Campaign電子郵件彈出

要查看聯繫人的時間軸，請通過按一下Dynamics 365下拉菜單中的「銷售中心」導航到聯繫人清單。 然後按一下左側菜單欄上的「聯繫人」，然後選擇一個聯繫人。

>[!NOTE]
>
>的 **Adobe CampaignMicrosoft動力365** AppSource中的app需要安裝在您的MicrosoftDynamics 365實例中才能查看這些事件。 [了解更多](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app)。

在下面，您可以看到「Dynamics User」的「Contact」螢幕的快照。 在「時間軸」視圖中，您會注意到Dynamics用戶已發送與市場活動名稱「2019LoyaltyCamp」和交付名稱「DM190」關聯的電子郵件。 Dynamics用戶開啟了電子郵件並按一下了電子郵件中的URL;這兩個操作都建立了同樣顯示在下面的事件。 如果你看右角，你會看到「關係助理」(RA)卡；當前，它包含要跟蹤按一下的URL的任務。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

有關Dynamics用戶的時間軸視圖的特寫，請參閱下面。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

下面是Relationship Assistant(RA)卡的特寫。 AppSource應用包含一個工作流，它監視Adobe電子郵件URL按一下事件。 發生此事件時，它會建立任務並設定到期日期。 這允許任務顯示在RA卡中，使其更加可見。 Adobe「電子郵件退出」事件有類似的工作流，添加一個任務以協調無效的電子郵件地址。 可以在解決方案中關閉這些工作流。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

如果按一下發送事件的主題，您將看到與下面類似的表單。 開放式和彈跳事件的表格類似。

![](assets/do-not-localize/mirror_page_url_send.png)

電子郵件URL按一下事件的表單為按一下的URL添加了附加屬性：

![](assets/do-not-localize/mirror_page_url_click.png)

以下是屬性清單和說明：

* **主題**:活動主題；由電子郵件傳遞的市場活動ID和傳遞ID組成

* **所有者**:在預配後步驟中建立的應用程式用戶

* **關於**:聯繫人的姓名

* **市場活動名稱**:市場活動ID在Campaign Standard

* **交貨名稱**:傳遞ID在Campaign Standard

* **發送/開啟/按一下/跳轉日期**:建立事件的日期/時間

* **跟蹤URL**:已按一下的URL

* **鏡像頁URL**:發送/開啟/按一下/彈回的電子郵件的鏡像頁面的URL。 可以在相應市場活動電子郵件渠道活動的配置螢幕中修改電子郵件鏡像頁面的到期期間。 [了解更多](../../administration/using/configuring-email-channel.md#validity-period-parameters)。

>[!NOTE]
>
>對於「退出」，當在MicrosoftDynamics 365中修改「退出」屬性時，如果您選擇了 **單向(MicrosoftDynamics 365營銷活動)** 或 **雙向** opt-out配置，如果正確映射了該特定屬性。

## 資料流 {#data-flows}

### 聯繫人和自定義實體入口

新建、更新和刪除的記錄(注：必須啟用刪除)從MicrosoftDynamics 365聯繫表發送到「活動」配置檔案表。

可以在整合應用程式UI中配置表映射，以將MicrosoftDynamics 365表屬性映射到市場活動表屬性。 可以根據需要修改表映射以添加/刪除屬性。

資料流的初始運行旨在傳輸所有映射的記錄，包括那些標籤為「非活動」的記錄；隨後，整合將只處理增量更新。 這種情況的例外是，如果重播資料或配置了過濾器；可以配置基本、基於屬性的篩選規則，以確定要同步到市場活動的記錄。

基本替換規則可在整合應用程式UI中配置，以用不同的值替換屬性值(例如，&quot;#00FF00&quot;的&quot;green&quot;,1的&quot;F&quot;等)。

根據記錄的數量，您的市場活動SFTP儲存可能需要用於初始資料傳輸。 [了解更多](#initial-data-transfer)。

必須用Dynamics 365聯繫人屬性contactId填充「活動概要檔案」表屬性externalId，以便聯繫人進入工作。 市場活動自定義實體還必須填充Dynamics 365唯一ID屬性；但是，此屬性可以儲存在任何市場活動自定義實體屬性中（即，不必是externalId）。

>[!NOTE]
>
>對於自定義實體入口，必須在Dynamics 365中為同步的自定義實體啟用更改跟蹤。

#### 自定義實體

的 [Microsoft動力365-Adobe Campaign Standard一體化](../../integrating/using/d365-acs-get-started.md) 支援自定義實體，使Dynamics 365中的自定義實體能夠與市場活動中的相應自定義資源同步。

定制資源中的新資料可用於多種用途，包括分段和個性化。

整合支援連結表和非連結表。 連結最多支援三個級別（即級別1->級別2->級別3）。

>[!IMPORTANT]
>
>如果任何市場活動自定義資源記錄包含個人資訊，則應用特定建議。 瞭解更多資訊 [此部分](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data)。

配置自定義實體資料流時，必須注意以下事項：

* 建立和修改市場活動自定義資源是敏感操作，必須僅由專家用戶執行。
* 對於自定義實體資料流，必須在Dynamics 365中為同步的自定義實體啟用更改跟蹤。
* 如果在Dynamics 365中幾乎同時建立父記錄和連結的子記錄，則由於整合的並行處理，新子記錄在其父記錄之前被寫入市場活動的可能性很小。

* 如果父項和子項在「市場活動」端使用 **1個基數簡單連結** 選項，在父記錄到達「市場活動」之前，子記錄將保持隱藏且不可訪問（通過UI或API）。

* (假設 **1個基數簡單連結** 在市場活動中)如果在Dynamics 365中更新或刪除了子記錄，並且在市場活動中顯示父記錄之前將該更改寫入市場活動（不可能，但是可能是遠程），則該更新或刪除將不會在市場活動中處理，並且將引發錯誤。 在更新的情況下，需要在Dynamics 365中再次更新有關的記錄，以便同步更新的記錄。 在刪除的情況下，需要在市場活動方面單獨處理有關的記錄，因為Dynamics 365中不再有要刪除或更新的記錄。

* 如果遇到您認為有隱藏的子記錄並且無法訪問這些記錄的情況，則可以將基數連結類型臨時更改為 **0或1基數簡單連結** 來訪問那些記錄。

可以找到市場活動定制資源的更全面概覽 [此部分](../../developing/using/key-steps-to-add-a-resource.md)。

### 電子郵件營銷事件流{#email-marketing-event-flow}

電子郵件營銷活動將從「市場活動」發送到MicrosoftDynamics 365，以顯示在時間軸視圖中。

支援的市場營銷事件類型：
* 發送 — 發送給收件人的電子郵件
* 開啟 — 收件人開啟的電子郵件
* 按一下 — 收件人按一下的電子郵件中的URL
* 彈出 — 電子郵件到收件人時遇到硬反彈

Dynamics 365中顯示以下事件屬性：
* 市場營銷活動名稱
* 電子郵件傳遞名稱
* 時間戳記
* 電子郵件鏡像頁URL
* 已按一下URL（僅按一下事件）

可以按類型啟用/禁用電子郵件營銷事件（發送、開啟、按一下、彈出），以便只將您選擇的事件類型傳遞到Dynamics 365。

### 選擇退出流 {#opt-out-flow}

Opt-out（如denyList）值在系統之間同步；您可以選擇以下選項，以在登機時進行選擇：

* **單向(MicrosoftDynamics 365到市場活動)**:Dynamics 365是退出選擇的真相來源。 Opt-out屬性將在從Dynamics 365到Campaign Standard的一個方向上同步&quot;
* **單向(MicrosoftDynamics 365營銷活動)**:Campaign Standard是退出選擇的真相來源。 從Campaign Standard到Dynamics 365將在一個方向上同步退出屬性
* **雙向**:Dynamics 365 ANDCampaign Standard是真理的源泉。 Opt-out屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有單獨的過程來管理系統之間的選擇退出同步，則可以禁用整合的選擇退出資料流。

>[!NOTE]
>
>在整合應用程式UI中， **單向(MicrosoftDynamics 365到市場活動)** 和 **雙向** opt-out使用案例在單獨的opt-out工作流中配置。 [了解更多](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。
>
>的 **單向(MicrosoftDynamics 365營銷活動)** 選擇退出使用案例是例外；它是在入口（聯繫到配置檔案）工作流中配置的。

選擇退出流映射由客戶指定，因為公司之間的業務要求可能不同。 在「市場活動」側，只有OOTB opt-out屬性可用於opt-out映射：

* 拒絕清單
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPush通知
* ccpaOptOut

在Dynamics 365中，大多數選擇退出欄位都有「donot」前置詞；但是，如果資料類型相容，您也可以利用其他屬性來選擇退出。

### 初始資料傳輸 {#initial-data-transfer}

初始資料傳輸可能需要一段時間，具體取決於您從MicrosoftDynamics 365中攝取的記錄數。 在初始資料傳輸後，整合將採集增量更新。
