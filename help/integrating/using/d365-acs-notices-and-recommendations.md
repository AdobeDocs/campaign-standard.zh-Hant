---
title: Campaign和Microsoft Dynamics 365資料管理
description: 了解Campaign Standard和Microsoft Dynamics 365如何管理常見資料
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2507'
ht-degree: 1%

---

# 最佳實務和限制 {#acs-msdyn-best-practices}

## 管理資料 {#acs-msdyn-manage-data}

對於聯繫人和自定義實體同步，此整合將&#x200B;**Microsoft Dynamics 365視為真值**&#x200B;的源。  對同步屬性的任何變更應在Dynamics 365中完成，而不應在Adobe Campaign Standard中完成)。  如果在Campaign中進行變更，則在同步期間最終可能會在Campaign中覆寫，因為同步是單向的。

您可以選擇將整合設定為在Dynamics 365中刪除連絡人時，向Campaign發出設定檔刪除呼叫，以協助維護資料完整性。 不過，設定檔刪除與隱私權刪除不同。 Campaign中的隱私權刪除將移除Campaign設定檔記錄和相關的記錄項目；但是，一般設定檔刪除只會刪除Campaign設定檔記錄，在Campaign記錄中留下殘餘。 如果整合中啟用了設定檔刪除功能，則需執行其他步驟，才能正確處理資料主體隱私權請求。 請參閱[隱私權區段下方的步驟。](#manage-privacy-requests)

## 隱私權{#acs-msdyn-manage-privacy}

此整合旨在在Microsoft Dynamics 365和Adobe Campaign Standard之間傳輸一般使用者資料。 如果您的一般使用者資料中包含此資料，則該資料包含個人資訊。  身為資料控管單位，貴公司有責任遵守適用於您收集和使用個人資料的任何隱私權法律與法規。

此整合旨在在Microsoft Dynamics 365和Adobe Campaign Standard之間傳輸一般使用者資料(包括但不限於個人資訊（如果其包含在您的一般使用者資料中）。 身為資料控管單位，貴公司有責任遵守適用於您收集和使用個人資料的任何隱私權法律與法規。

整合不會發出任何資料主體隱私權（例如GDPR），以刪除或處理任何其他隱私權請求（選擇退出除外）。 處理隱私權要求時，您應在Microsoft Dynamics 365和Campaign(透過Adobe Experience Platform Privacy Service)中獨立執行。

如果您已將整合設定為在Dynamics 365中刪除連絡人時，向Campaign發出定期的設定檔刪除呼叫，則應遵循下列步驟。 確保在此過程中未對相關記錄進行任何更新。

1. 向[Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)發出隱私權刪除請求

1. 監視請求，直到成功完成

1. 確認記錄不再在您的Campaign執行個體中

1. （不久之後）在Dynamics 365中發佈隱私權刪除

1. 驗證是否已從兩個系統中刪除記錄

以下連結可協助您在每個系統中實作存取和/或刪除與隱私權相關的請求：

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>如果任何促銷活動自訂資源記錄包含適用於客戶使用促銷活動的個人資訊，則此類記錄應連結至對應的促銷活動設定檔記錄（直接或透過其他自訂資源），這樣設定檔記錄上與隱私權相關的刪除也可以刪除包含個人資訊的連結自訂資源記錄；必須配置實體之間的連結和刪除選項，以啟用這種類級聯的連結記錄刪除。 個人資訊不應輸入未連結至設定檔的自訂資源中。

## 選擇退出 {#opt-out}

由於Microsoft Dynamics 365和Campaign之間的選擇退出屬性有所差異，以及每個客戶的業務需求有所差異，因此選擇退出對應已保留為供客戶完成的練習。  請務必確保在系統之間正確對應選擇退出，以便保持最終用戶選擇退出首選項，並且他們不會通過選擇退出的通道接收通信。

請注意，只有下列項目可用於選擇退出對應：

* 首碼為「不再透過」的促銷活動屬性（例如，不再透過電子郵件聯絡），或

* CCPA的特定屬性

有關「設定檔」實體欄位的更多資訊，請參閱[此處](../../developing/using/datamodel-profile.md)。

在Dynamics 365中，大部分的退出欄位都有「donot」首碼，不過，如果資料類型相容，您也可以將其他屬性用於退出用途。

布建整合時，您將有機會指定您的業務所需的選擇退出設定：

* **單向（Microsoft Dynamics 365到Campaign）**:Dynamics 365是退出的真相來源。退出屬性將從Dynamics 365同步至Campaign Standard
* **單向（Campaign至Microsoft Dynamics 365）**:Campaign Standard是退出的真相來源。退出屬性將從Campaign Standard同步到Dynamics 365
* **雙向**:Dynamics 365和Campaign Standard都是真理的源泉。退出屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有獨立的程式來管理系統之間的選擇退出同步，則可停用整合的選擇退出資料流程。

雙向選擇退出配置使用邏輯確定要寫入兩個系統的值。 此邏輯會比較兩個系統之間的時間戳記（Dynamics 365中的記錄層級變更、Campaign中的屬性層級變更），以判斷哪個系統佔優。 如果促銷活動包含最近的時間戳記，則使用促銷活動值。 如果Dynamics 365包含較新的時間戳記，或者等於，則選擇退出=TRUE將會成功（假設其中一個值為TRUE）。

了解如何在[此區段](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)中選取選擇加入/退出選項。

>[!NOTE]
>
>請先檢閱並視情況更新Adobe Campaign中的預設和特定類型規則，再在此進行變更，以確保這些變更正確套用至所有傳出的通訊。 例如，請確定任何對應至選擇退出偏好設定都能準確反映收件者的意圖/通訊選擇，且不會不慎中止關係或交易式訊息的傳送，例如客戶訂單確認。

如果您選取&#x200B;**Bidirential**&#x200B;或&#x200B;**單向（促銷活動至Microsoft Dynamics 365）**&#x200B;選擇退出設定，則促銷活動選擇退出資料將透過工作流程定期匯出至您的促銷活動SFTP儲存區（請參閱下方的「促銷活動SFTP使用情形」）。 如果您的Campaign選擇退出工作流程停止執行，您需要盡快手動重新啟動，以減少遺漏選擇退出同步的可能性。

>[!IMPORTANT]
>
>如果您需要&#x200B;**Bidirential**&#x200B;或&#x200B;**單向(Campaign to Microsoft Dynamics 365)**&#x200B;選擇退出設定，則需要向Adobe技術聯絡人提出要求，以便在您的Campaign執行個體上設定選擇退出工作流程

## 促銷活動SFTP使用情況

您的Campaign SFTP儲存空間需要供以下使用案例的整合使用。  您需要確保SFTP帳戶有足夠的儲存容量來容納這些使用案例。 超過授權的SFTP儲存容量，可能會嚴重影響Campaign、整合和/或SFTP帳戶的功能使用。

| 使用案例 | 說明 |
|---|---|
| 雙向和單向（向Microsoft Dynamics 365進行的促銷活動） | 雙向和單向(Campaign to Microsoft Dynamics 365)選擇退出資料流將利用Campaign SFTP儲存空間。 促銷活動工作流程將增量變更匯出至SFTP資料夾。 整合會從該處擷取記錄和程式。 |
| 退出記錄檔 | 疑難排解整合時，從連接器輸出記錄檔將有所幫助。 可開啟/關閉輸出日誌。 |


>[!IMPORTANT]
>
>您需負責從SFTP資料夾存取和下載的資訊。 如果資訊包含個人資料，您需負責遵守任何適用的隱私權法律和法規。 [深入瞭解](#acs-msdyn-manage-privacy)。

## 資料管理

### 現有促銷活動資料

此整合會將連絡人和自訂實體從Microsoft Dynamics 365同步至Campaign。 在整合之外建立的促銷活動記錄（亦即，不是由同步工作建立）將不會由整合修改，包括整合設定時現有的促銷活動記錄。

由於此整合使用Campaign中的&#x200B;**[!UICONTROL externalId]**&#x200B;欄位來同步Campaign設定檔記錄與Dynamics 365聯絡記錄，因此對於您要從Microsoft Dynamics 365同步的記錄，此Campaign欄位(**[!UICONTROL externalId]**)必須填入Microsoft Dynamics 365 **[!UICONTROL contactId]**。  自訂實體也會使用Microsoft Dynamics 365唯一ID來同步。 Campaign自訂實體將需要將此ID屬性包含為表格欄。 externalId欄可用來儲存此屬性值，但Campaign自訂實體不需要它。

請記住，Microsoft Dynamics 365仍是真相的來源，而且當整合偵測到Dynamics 365端的更新時，可以覆寫Campaign設定檔資料。  視您現有的部署而定，啟用整合可能還需要其他步驟；因此，建議您與Adobe技術聯絡人密切合作。

>[!NOTE]
>
>由於現有Adobe部署的複雜性，建議您在規劃和設定整合時與客戶技術聯絡人合作。

### 資料同步頻率

此整合採用的架構可偵測更新，並在Microsoft Dynamics 365中發生更新後（即串流，而非批次處理），立即將其新增至處理「佇列」。 因此，不需要指定資料流運行頻率或調度。

Dynamics 365選擇退出資料流程的雙向和Campaign是此作法的例外。 對於這些選擇退出設定，更新的Campaign記錄會透過Campaign工作流程每天匯出一次，之後整合工具會讀取檔案並處理記錄。

### 資料使用協定

如果您位在EMEA或APAC地區，部分資料將會在美國處理，作為這項整合的一部分。 如需詳細資訊，請參閱[本區段](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 護欄和限制

>[!IMPORTANT]
>
>您所執行的某些動作（例如，初始擷取記錄、重播記錄資料等） 可能會導致從Microsoft Dynamics 365擷取大量記錄至您的Adobe Campaign執行個體。 為降低效能問題的風險，建議您停止所有促銷活動程式（例如，無行銷活動、無工作流程執行等） 直到將大量記錄擷取到Campaign中為止。

### 自訂實體

[Microsoft Dynamics 365-Adobe Campaign Standard整合](../../integrating/using/d365-acs-get-started.md)支援自訂實體，讓Dynamics 365中的自訂實體同步至Campaign中的對應自訂資源。

整合支援連結和非連結的表格。

設定自訂實體資料流程時，請務必注意下列事項：

* 建立和修改Campaign自訂資源是敏感操作，只能由專家使用者執行。
* 對於自訂實體資料流，必須在Dynamics 365中為同步的自訂實體啟用變更追蹤。
* 如果在Dynamics 365中建立父記錄和連結的子記錄時間接近同一時間，由於並行處理整合，則在其父記錄之前，將新子記錄寫入Campaign的機會很小。

* 如果使用&#x200B;**1基數簡單連結**&#x200B;選項在促銷活動端連結父記錄和子記錄，則子記錄在父記錄到達Campaign前將保持隱藏且無法存取（透過UI或API）。

* （假設促銷活動中&#x200B;**1基數簡單連結**）如果子記錄在Dynamics 365中更新或刪除，且該變更在父記錄在促銷活動中顯示之前（不可能，但是是遠端可能）已寫入促銷活動，則該更新或刪除不會在促銷活動中處理，且會擲回錯誤。 如果是更新，則需要在Dynamics 365中再次更新相關記錄，以便同步更新的記錄。 如果是刪除，則需要在促銷活動端個別處理相關記錄，因為Dynamics 365中已沒有記錄可刪除或更新。

* 如果您遇到您認為隱藏了子記錄且無法訪問這些記錄的情況，可以暫時將基數連結類型更改為&#x200B;**0或1個基數簡單連結**&#x200B;以訪問這些記錄。

您可在此區段](../../developing/using/key-steps-to-add-a-resource.md)找到更全面的Campaign自訂資源概觀。[

### 整合護欄

規劃使用此整合時，應考量下列護欄。 如果您認為超過這些護欄，請咨詢您的Adobe技術代表。

* 您需要授權適當的Campaign套件，以支援整合產生的引擎呼叫量。 超過授權引擎呼叫量可能會導致促銷活動效能降低。

   請使用下列項目來協助估計整合中的引擎呼叫量：

   * 記錄插入（即，新記錄）:1個引擎呼叫
   * 記錄刪除：1個引擎呼叫
   * 記錄更新：2個引擎呼叫（只有在目標籤錄與來源記錄相同時才呼叫1個 — 即，如果促銷活動記錄未變更）

   估計整體Campaign引擎呼叫量時，請務必將其他引擎呼叫來源納入考量，包括登陸頁面、WebApps、JSSP、API、行動應用程式註冊等。

   請在此處檢視Adobe Campaign Standard套件資訊：[https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)

* 整合最多可支援1,500萬筆記錄，用於初始同步至Campaign中的資源。 增量同步受Adobe Campaign Standard套件限制。

* 標準整合產品包含最多20個自訂實體的支援，每個實體的大小最多為50欄。

* 在實作整合之前，您需要建立並發佈自訂資源。

* 連結表時的表深度上限為2（即表1->表2->表3）

* 整合支援每個自訂資源最多5個連結欄。 在自訂資源之間連結多個欄可能會對效能產生重大影響。 **0或1個基數簡單連** 結比1個基 **數簡單連結更好**。

* 整合支援基元Microsoft Dynamics 365資料類型（布林值、整數、小數、雙倍、字串、DateTime、Date）和Adobe Campaign Standard資料類型（整數、布林值、浮點、雙倍、日期、日期、字串）之間的轉換。 更多進階資料類型會解譯為字串，並依原樣同步。

* Adobe和客戶之間可能需要建立上線維護窗口。

* 請注意，整合使用量的顯著增加或「尖峰」（例如，新記錄或更新記錄的大幅增加）可能會導致資料同步速度緩慢。

* 作為整合的一部分，您應完成Microsoft Azure和Dynamics 365中的預整合設定步驟。 請參閱本頁的配置步驟[](../../integrating/using/d365-acs-configure-d365.md)

* 預期您會將Dynamics 365和Campaign資料模型帶入整合，並加以維護。

### 整合界限

此整合旨在解決Microsoft Dynamics 365和Campaign之間常見資料移動的一般使用案例，但並非旨在解決每個客戶特有的所有使用案例：

* 整合不會發出任何隱私權（例如GDPR）刪除。 履行使用者隱私權要求的責任在於客戶；這類要求應在Campaign(透過Adobe Experience Platform Privacy Service)和Dynamics 365中獨立提出。 如有需要，整合可發出定期刪除以協助進行資料同步。   如需詳細資訊，請檢閱[隱私權區段](#manage-privacy-requests)。

* 除了選擇退出資訊（如果由客戶設定）外，不會從Campaign將任何設定檔或自訂實體資料同步至Dynamics 365。

* 本機不支援促銷活動訂閱管理（亦即訂閱/取消訂閱）。

* 不支援從Dynamics 365內撰寫及觸發Campaign電子郵件促銷活動。

* 整合&#x200B;**not**&#x200B;支援在Dynamics 365和Campaign Standard資料模型之間重構資料。 預計整合會將一個Dynamics 365表格同步至一個Campaign表格。
