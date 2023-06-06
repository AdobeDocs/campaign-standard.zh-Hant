---
title: Campaign與Microsoft Dynamics 365資料管理
description: 瞭解Campaign Standard和Microsoft Dynamics 365如何管理常見資料
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: 17522f4df86c7fb46593472316d57b4ba4acee2b
workflow-type: tm+mt
source-wordcount: '2471'
ht-degree: 1%

---

# 最佳實務和限制 {#acs-msdyn-best-practices}

## 管理資料 {#acs-msdyn-manage-data}

對於連絡人和自訂實體同步處理，此整合會將 **Microsoft Dynamics 365作為真相來源**.  同步屬性的任何變更應在Dynamics 365中完成，而不是在Adobe Campaign Standard中完成)。  如果在Campaign中進行了變更，則最終可能會在同步期間在Campaign中覆寫這些變更，因為同步是在一個方向進行的。

您可以選擇將整合設定為在Dynamics 365中刪除連絡人時向Campaign發出設定檔刪除呼叫，以協助維護資料完整性。 不過，設定檔刪除與隱私權刪除不同。 Campaign中的隱私權刪除會移除Campaign設定檔記錄和相關聯的記錄專案；而定期的設定檔刪除只會刪除Campaign設定檔記錄，留下在Campaign記錄中的其餘專案。 如果整合中啟用了設定檔刪除功能，則需要執行其他步驟才能正確處理資料主體隱私權請求。 請參閱 [隱私權區段如下](#manage-privacy-requests).

## 隱私權{#acs-msdyn-manage-privacy}

此整合旨在於Microsoft Dynamics 365與Adobe Campaign Standard之間傳輸一般使用者資料。 此資料包含個人資訊（若包含在您的一般使用者資料中）。  作為資料控管單位，貴公司有責任遵守適用於您收集和使用個人資料的任何隱私權法規。

此整合旨在在Microsoft Dynamics 365和Adobe Campaign Standard之間傳輸一般使用者資料（包括但不限於個人資訊，若包含在一般使用者資料中）。 作為資料控管單位，貴公司有責任遵守適用於您收集和使用個人資料的任何隱私權法規。

整合不會發佈任何資料主體隱私權（例如GDPR）刪除或處理任何其他隱私權請求（選擇退出除外）。 處理隱私權請求時，您應在Microsoft Dynamics 365和Campaign (透過Adobe Experience Platform Privacy Service)中個別執行。

如果您已設定整合，在Dynamics 365中刪除連絡人時，會對Campaign發出一般設定檔刪除呼叫，請遵循下列步驟。 確保在此過程中沒有對相關記錄進行更新。

1. 將隱私權刪除請求傳送至 [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. 監視請求，直到成功完成為止

1. 驗證記錄是否不再位於您的Campaign執行個體中

1. （不久之後） Dynamics 365中的問題隱私權刪除

1. 確認記錄已從兩個系統中移除


>[!IMPORTANT]
>
>如果任何Campaign自訂資源記錄包含個人資訊，且適用於客戶的Campaign使用，則此類記錄應連結至對應的Campaign設定檔記錄（直接或透過其他自訂資源），以便設定檔記錄上的隱私權相關刪除也可以刪除包含個人資訊的連結自訂資源記錄；實體之間的連結和刪除選項必須設定為啟用這種階層式移除連結記錄。 個人資訊不應輸入到未連結至設定檔的自訂資源中。

## 選擇退出 {#opt-out}

由於Microsoft Dynamics 365和Campaign之間在選擇退出屬性上的差異，以及每個客戶的業務需求差異，選擇退出對應留作客戶完成的一項練習。  請務必確保系統之間正確對應選擇退出，以維護一般使用者選擇退出的偏好設定，且他們不會透過選擇退出的管道收到通訊。

請注意，只有下列專案才能用於選擇退出對應：

* 具有「不再透過聯絡」首碼的行銷活動屬性（例如，不再透過電子郵件聯絡），或

* CCPA的特定屬性

有關設定檔實體欄位的更多資訊可以找到 [此處](../../developing/using/datamodel-profile.md).

在Dynamics 365中，大部分的選擇退出欄位都有「不要」首碼，不過，如果資料型別相容，您也可以利用其他屬性來達到選擇退出的目的。

布建整合時，您將有機會指定業務所需的選擇退出設定：

* **單向(Microsoft Dynamics 365至Campaign)**：Dynamics 365是選擇退出的信任來源。 選擇退出屬性會從Dynamics 365同步至Campaign Standard的一個方向
* **單向(Campaign至Microsoft Dynamics 365)**：Campaign Standard是選擇退出的真實來源。 選擇退出屬性將會在從Campaign Standard到Dynamics 365的一個方向上同步
* **雙向**：Dynamics 365和Campaign Standard都是信任來源。 選擇退出屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有個別程式來管理系統之間的選擇退出同步，則可以停用整合的選擇退出資料流程。

雙向選擇退出設定會使用邏輯來決定要寫入兩個系統的值。 邏輯會比較兩個系統之間的時間戳記（Dynamics 365中的記錄層級變更、Campaign中的屬性層級變更），以判斷哪個系統優先。 如果Campaign包含較新的時間戳記，則Campaign值優先。 如果Dynamics 365包含較新的時間戳記或兩者相等，則opt-out=TRUE會獲勝（假設其中一個值為TRUE）。

瞭解如何在中選取選擇加入/退出選項 [本節](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>請檢閱並在適當時更新Adobe Campaign中的預設和特定型別規則，然後再在此進行變更，以確保此等變更正確套用至所有傳出通訊。 例如，請確定任何選擇退出偏好設定的對應都會準確反映收件者的意圖/通訊選擇，而不會無意間中斷關係或交易式訊息（例如客戶訂單確認）的傳送。

如果您已選取 **雙向** 或 **單向(Campaign至Microsoft Dynamics 365)** 選擇退出設定，Campaign選擇退出資料將透過工作流程定期匯出至您的Campaign SFTP儲存區域（請參閱以下的「Campaign SFTP使用量」）。 如果Campaign選擇退出工作流程停止執行，您需要儘快手動重新啟動，以減少遺漏選擇退出同步的可能性。

>[!IMPORTANT]
>
>如果您需要 **雙向** 或 **單向(Campaign至Microsoft Dynamics 365)** 選擇退出設定，您必須向Adobe技術連絡人提出要求，才能在您的Campaign執行個體上設定選擇退出工作流程

## Campaign SFTP使用情況

在以下使用案例中，整合需要使用您的Campaign SFTP儲存空間。  您需要確保您的SFTP帳戶有足夠的儲存容量來因應這些使用案例。 超過授權的SFTP儲存容量可能會嚴重損害Campaign、整合和/或SFTP帳戶的功能使用。

| 使用案例 | 說明 |
|---|---|
| 雙向與單向(Campaign至Microsoft Dynamics 365) | 雙向和單向(Campaign至Microsoft Dynamics 365)選擇退出資料流程將利用Campaign SFTP儲存空間。 Campaign工作流程會將增量變更匯出至SFTP資料夾。 整合功能會從此擷取記錄並處理。 |
| 選擇退出記錄 | 疑難排解整合時，聯結器的輸出記錄會很有幫助。 輸出記錄可以開啟/關閉。 |


>[!IMPORTANT]
>
>您需負責存取和下載SFTP資料夾中的資訊。 如果資訊包含個人資料，您有責任遵守任何適用的隱私權法規。 [了解更多](#acs-msdyn-manage-privacy)。

## 資料管理

### 現有的Campaign資料

此整合會將聯絡人和自訂實體從Microsoft Dynamics 365同步至Campaign。 在整合之外建立的行銷活動記錄（即不是由同步工作建立的）不會被整合修改，包括整合設定時存在的Campaign記錄。

因為這項整合使用 **[!UICONTROL externalId]** 用來同步Campaign設定檔記錄與Dynamics 365連絡人記錄的Campaign欄位，此Campaign欄位(**[!UICONTROL externalId]** )必須填入Microsoft Dynamics 365 **[!UICONTROL contactId]** 用於您要從Microsoft Dynamics 365同步的記錄。  自訂實體也使用Microsoft Dynamics 365唯一ID進行同步。 Campaign自訂實體將需要包含此ID屬性作為表格欄。 externalId欄可用於儲存此屬性值，但Campaign自訂實體不需要它。

請記住，Microsoft Dynamics 365仍然是真相的來源，而且當整合偵測Dynamics 365端的更新時，可以覆寫Campaign設定檔資料。  啟用整合可能也需要其他步驟，視您現有的部署而定；因此，建議您與您的Adobe技術聯絡人密切合作。

>[!NOTE]
>
>由於現有客戶部署的複雜性，建議您在計畫和設定整合時與Adobe技術聯絡人合作。

### 資料同步頻率

整合採用的架構可偵測更新，並在Microsoft Dynamics 365中發生更新後不久將其新增至處理「佇列」（亦即串流，而非批次處理）。 因此，不需要指定資料流程執行頻率或排程。

例外情況為雙向和Campaign to Dynamics 365選擇退出資料流程。 對於這些選擇退出設定，更新的Campaign記錄會透過Campaign工作流程每天匯出至SFTP一次，之後整合工具會讀取檔案並處理記錄。

### 資料使用協定

如果您位於EMEA或APAC地區，部分資料將在美國處理，作為此整合的一部分。 如需詳細資訊，請參閱[本區段](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 護欄和限制

>[!IMPORTANT]
>
>您的某些動作（例如，記錄的初始擷取、記錄資料的重播等） 可能會導致大量記錄從Microsoft Dynamics 365擷取至您的Adobe Campaign執行個體。 為了降低效能問題的風險，建議您停止所有Campaign程式（例如，沒有行銷活動、沒有執行工作流程等） 直到將大量記錄擷取到Campaign之後。

### 自訂實體

此 [Microsoft Dynamics 365-Adobe Campaign Standard整合](../../integrating/using/d365-acs-get-started.md) 支援自訂實體，可讓Dynamics 365中的自訂實體與Campaign中對應的自訂資源同步。

整合約時支援連結和非連結表格。

設定自訂實體資料流程時，請務必注意下列事項：

* 建立和修改Campaign自訂資源是敏感性作業，只能由專家使用者執行。
* 對於自訂實體資料流程，必須在Dynamics 365中為同步的自訂實體啟用變更追蹤。
* 如果在Dynamics 365中幾乎相同時間建立父記錄和連結的子記錄，則由於平行處理整合，將新子記錄寫入父記錄之前的Campaign的機會很低。

* 如果使用連結至促銷活動側面的父項和子項 **1個基數簡單連結** 選項，在父記錄到達Campaign之前，子記錄將保持隱藏和無法存取（透過UI或API）。

* (假設 **1個基數簡單連結** （在Campaign中）如果子記錄在Dynamics 365中更新或刪除，且該變更會先寫入Campaign，然後父記錄才會出現在Campaign中（不太可能，但極有可能出現），則不會在Campaign中處理該更新或刪除，且會擲回錯誤。 更新時，需要在Dynamics 365中再次更新有問題的記錄，才能同步更新的記錄。 刪除時，相關記錄需要在Campaign端個別處理，因為Dynamics 365中不再有要刪除或更新之記錄。

* 如果您遇到您認為有隱藏的子記錄且無法存取這些記錄的情況，您可以暫時將基數連結型別變更為 **0或1個基數簡單連結** 以存取這些記錄。

如需更全面的Campaign自訂資源概觀，請參閱 [在本節中](../../developing/using/key-steps-to-add-a-resource.md).

### 整合護欄

規劃使用此整合時，應將下列護欄列入考量。 如果您認為超過這些護欄，請洽詢您的Adobe技術代表。

* 您需要授權正確的Campaign套件，以支援整合產生的引擎呼叫量。 超過授權的引擎呼叫量可能會導致Campaign效能降低。

   使用下列專案來協助評估整合的引擎呼叫量：

   * 記錄插入（即新記錄）：1個引擎呼叫
   * 記錄刪除： 1個引擎呼叫
   * 記錄更新： 2個引擎呼叫（如果目的地記錄與來源記錄相同，即如果促銷活動記錄沒有變更，則只有1個呼叫）

   在估計整體Campaign引擎呼叫量時，務必要將引擎呼叫的其他來源（包括登陸頁面、WebApps、JSSP、API、行動應用程式註冊等）納入考量。

   在這裡檢視Adobe Campaign Standard套件資訊： [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)

* 整合最多可支援1500萬筆記錄，以便初次同步至Campaign中的資源。 增量同步受到Adobe Campaign Standard套件的限制。

* 標準整合產品最多可支援20個自訂實體，每個實體的大小上限為50欄。

* 實施整合前，您需要建立並發佈自訂資源。

* 連結表格時的最大表格深度為兩個（即table1->table2->table3）

* 整合可支援每個自訂資源最多5個連結欄。 在自訂資源之間連結多個欄可能會對效能造成重大影響。 **0或1個基數簡單連結** 比更適合 **1個基數簡單連結**.

* 整合支援基本Microsoft Dynamics 365資料型別（布林值、整數、小數、雙精度浮點數、字串、日期時間、日期）與Adobe Campaign Standard資料型別（整數、布林值、浮點數、雙精度浮點數、日期、日期時間、字串）之間的轉換。 更進階的資料型別會解譯為字串，並照原樣同步。

* 可能需要在Adobe和客戶之間建立入門維護視窗。

* 請注意，整合使用量大幅增加或「激增」（例如，新記錄或更新記錄大幅增加）可能會造成資料同步速度變慢。

* 在整合過程中，您需要完成Microsoft Azure和Dynamics 365中的整合前設定步驟。 請參閱設定步驟 [在此頁面上](../../integrating/using/d365-acs-configure-d365.md)

* 預計您會將Dynamics 365和Campaign資料模型整合併加以維護。

### 整合邊界

此整合旨在解決Microsoft Dynamics 365與Campaign之間常見資料移動的一般使用案例，但並非旨在解決每個客戶特有的每個使用案例：

* 整合不會發佈任何隱私權（例如GDPR）刪除通知。 客戶有責任履行使用者的隱私權要求；這類要求應在Campaign (透過Adobe Experience Platform Privacy Service)和Dynamics 365中獨立提出。 如有需要，整合可發佈定期刪除，以協助進行資料同步。   檢閱 [隱私權區段](#manage-privacy-requests) 以取得詳細資訊。

* 除了選擇退出資訊（若由客戶設定）之外，沒有任何設定檔或自訂實體資料會從Campaign同步至Dynamics 365。

* 不原生支援行銷活動訂閱管理（即訂閱/取消訂閱）。

* 不支援在Dynamics 365內撰寫和觸發Campaign電子郵件行銷活動。

* 整合可以 **not** 支援在Dynamics 365和Campaign Standard資料模型之間重新建立資料。 預期整合會將一個Dynamics 365表格同步至一個Campaign表格。
