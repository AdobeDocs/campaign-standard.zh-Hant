---
solution: Campaign Standard
product: campaign
title: 使用 Microsoft Dynamics 365 整合
description: 瞭解如何搭配Campaign Standard整合使用Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 0%

---


# 使用 Microsoft Dynamics 365 整合

此整合會執行數個工作：

* **入口**:

   * 將Dynamics **** 365的連絡人匯入Campaign

   * **自訂實體**:將自訂表格從Dynamics 365匯入Campaign。 在本節 [中進一步瞭解](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md)。

* **出口**:將電子郵件行銷活動從ACS帶入D365（電子郵件傳送、開啟、按一下、彈回）

* **選擇退出**:雙向同步退出狀態（例如denyList）

有關資料流的詳細資訊，請參 [閱本節](#data-flows)。

## Adobe Campaign Standard使用者體驗

當在Dynamics 365中建立或修改（或刪除）連絡人時，該連絡人會傳送至「促銷活動」。  這些連絡人會顯示在促銷活動的「設定檔」畫面中，並可定位在行銷促銷活動中。  請參閱下方的「描述檔」畫面。

![](assets/MSdynamicsACS-usage1.png)

當促銷活動中修改選擇退出屬性時，如果您已選取「促銷活動轉換動態」365或雙向選擇退出設定，而且您已正確對應該特定屬性，則會反映在Dynamics 365中。

## Microsoft Dynamics 365使用者體驗

若為出口，下列電子郵件行銷事件會從Campaign傳送至Dynamics 365，並在Dynamics 365時間軸檢視中顯示為自訂活動：

* Adobe Campaign電子郵件傳送

* Adobe Campaign電子郵件開啟

* Adobe Campaign電子郵件URL點按

* Adobe Campaign電子郵件彈回數

若要檢視連絡人的時間軸，請按一下Dynamics 365下拉式選單中的Sales Hub，以導覽至您的連絡人清單。  然後，按一下左側菜單欄上的「聯繫人」並選擇聯繫人。

>[!NOTE]
>
>AppSource中的Adobe Campaign for Dynamics 365應用程式必須安裝在Dynamics 365例項中，才能檢視這些事件。

下面是「Dynamics User」的「Contact」（聯繫人）螢幕快照。  在「時間軸」檢視中，您會注意到Dynamics使用者已寄送電子郵件，與促銷活動名稱「2019LoyaltyCamp」和傳送名稱「DM190」相關。  Dynamics使用者開啟電子郵件，並點選了電子郵件中的URL;這兩個動作都會建立事件，如下所示。  如果您往右拐，就會看到「關係助理」(RA)卡；目前，它包含要追蹤所點按URL的工作。

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

請參閱以下，以取得動態使用者時間軸檢視的詳細資訊。

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

以下是關係助理(RA)卡的特寫。  AppSource應用程式包含會監視Adobe電子郵件URL點按事件的工作流程。  發生此事件時，它會建立工作並設定到期日。  這可讓工作顯示在RA卡中，讓它更加可見。  Adobe電子郵件彈回數事件的工作流程類似，新增了協調無效電子郵件地址的任務。  這些工作流程可在解決方案中關閉。

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

如果您按一下傳送事件的主題，您會看到類似下方的表格。  開啟和彈回事件的表格類似。

![](assets/do-not-localize/mirror_page_url_send.png)

電子郵件URL點按事件的表單會為被點按的URL新增其他屬性：

![](assets/do-not-localize/mirror_page_url_click.png)

以下是屬性清單和說明：

* 主旨：活動主體；由電子郵件傳送的促銷活動ID和傳送ID組成

* 擁有者：在布建後步驟中建立的應用程式用戶

* 關於：連絡人姓名

* 促銷活動名稱：Campaign Standard中的促銷活動ID

* 傳送名稱：Campaign Standard中的傳送ID

* 傳送／開啟／點按／退回日期：建立事件的日期／時間

* 追蹤URL:已點按的URL

* 鏡像頁URL:傳送／開啟／點按／彈回之電子郵件之鏡像頁面的URL

>[!NOTE]
>
>電子郵件鏡像頁面的到期期間可在對應的「促銷活動」電子郵件渠道活動的設定畫面中加以修改(請參 [閱「有效期間參數](../../administration/using/configuring-email-channel.md#validity-period-parameters)」)。

>[!NOTE]
>
>對於選擇退出，在Dynamics 365中修改選擇退出屬性時，如果您已選取Dynamics 365到促銷活動或雙向選擇退出設定，且您已正確對應該特定屬性，則該屬性會反映在促銷活動中。

## 資料流 {#data-flows}

### 連絡人與自訂實體入口

新記錄和更新記錄（若已啟用）會從Dynamics 365連絡人表格傳送至「促銷活動」描述檔表格。

表格映射可設定為將Dynamics 365表格屬性映射至促銷活動表格屬性。 可根據需要修改表映射以添加／刪除屬性。

資料流的初始運行旨在傳輸所有映射記錄，包括標籤為「非活動」的記錄；之後，整合將只處理增量更新。 這個例外是，如果已設定篩選器；基本、屬性型的篩選規則可加以設定，以決定要同步至促銷活動的記錄。

基本取代規則可設定為以不同值取代屬性值（例如，「#00FF00」為「綠色」、「F」為1等）。

視記錄量而定，您的促銷活動SFTP儲存空間可能需要用於初始資料傳輸。  請參閱「初始資料傳輸」一節。

Campaign描述檔表格屬性externalId必須填入Dynamics 365 Contact屬性contactId，才能讓連絡人進入工作。 促銷活動自訂實體也必須填入Dynamics 365唯一ID屬性；不過，此屬性可儲存在任何促銷活動自訂實體屬性中（亦即不必是externalId）。

>[!NOTE]
>
>對於自訂實體入口，必須在Dynamics 365中為同步化的自訂實體啟用變更追蹤。

### 電子郵件行銷活動流程

電子郵件行銷事件會從Campaign傳送至Dynamics 365，以顯示在時間軸檢視中。

支援的行銷事件類型：
* 傳送——電子郵件傳送給收件者
* 開啟——收件者開啟的電子郵件
* 按一下——收件者點按之電子郵件內的URL
* 彈回數——傳送給收件者的電子郵件出現硬反彈

D365中顯示以下事件屬性：
* 行銷宣傳名稱
* 電子郵件傳送名稱
* 時間戳記
* 電子郵件鏡像頁面URL
* 點按的URL（僅限點按事件）

電子郵件行銷事件可依類型啟用／停用（傳送、開啟、按一下、彈回），因此只有您選取的事件類型才會傳遞至Dynamics 365。

### 退出流程

退出（如denyList）值在系統之間同步；您有下列選項可在上線時選擇：
* Dynamics 365是退出的真相來源：退出屬性將會在從Dynamics 365到Campaign Standard的一個方向上同步
* 「促銷活動標準」是退出的真相來源：退出屬性將會在從促銷活動標準到動態365的一個方向上同步
* Dynamics 365 AND Campaign Standard是真相的來源：退出屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有個別的程式來管理系統之間的退出同步，則可停用整合的退出資料流。

選擇退出流程映射由客戶指定，因為不同公司的業務需求可能不同。  在促銷活動方面，只有OOTB選擇退出屬性可用於選擇退出對應：
* denyList
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPush通知
* ccpaOptOut

在Dynamics 365中，大多數選擇退出欄位都有「donot」字首；但是，如果資料類型相容，您也可以利用其他屬性來選擇退出。

### 初始資料傳輸

超過500k記錄的Dynamics 365表格必須匯出至您的促銷活動SFTP儲存，才能透過促銷活動工作流程匯入。

初始資料傳輸是基於檔案的一次性資料傳輸。 在資料傳輸後，整合會使用API進行增量更新。
