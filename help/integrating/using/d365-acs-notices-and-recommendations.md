---
solution: Campaign Standard
product: campaign
title: Campaign和Microsoft Dynamics 365資料管理
description: 瞭解Campaign Standard和Microsoft Dynamics 365如何管理常見資料
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '2467'
ht-degree: 1%

---


# 最佳實務和限制 {#acs-msdyn-best-practices}

## 管理資料{#acs-msdyn-manage-data}

對於聯絡人和自訂實體同步，此整合將&#x200B;**Microsoft Dynamics 365視為真相來源**。  同步化屬性的任何變更應在Dynamics 365中進行，而不是在Adobe Campaign Standard中進行)。  如果在促銷活動中進行變更，則在同步期間，這些變更最終會在促銷活動中被覆寫，因為同步是單向的。

此整合可選擇性地設定為在Dynamics 365中刪除連絡人時，向促銷活動發出描述檔刪除呼叫，以協助維持資料的完整性。 不過，描述檔刪除與隱私權刪除不同。 促銷活動中的隱私權刪除會移除促銷活動描述檔記錄和相關記錄項目；但是，定期刪除描述檔只會刪除促銷活動描述檔記錄，而保留在促銷活動記錄中。 如果整合中啟用了描述檔刪除功能，則需要執行其他步驟，才能正確處理資料主體的隱私權要求。 請參閱[隱私權一節中的步驟](#manage-privacy-requests)。

## 隱私權{#acs-msdyn-manage-privacy}

此整合旨在在Microsoft Dynamics 365和Adobe Campaign Standard之間傳輸使用者資料。 如果您的使用者資料中包含此資料，則此資料會包含個人資訊。  身為資料掌控者，貴公司有責任遵守任何適用於您收集和使用個人資料的隱私權法律和法規。

此整合旨在在Microsoft Dynamics 365和Adobe Campaign Standard之間傳輸使用者資料(包括但不限於個人資訊（若您的使用者資料中包含）。 身為資料掌控者，貴公司有責任遵守任何適用於您收集和使用個人資料的隱私權法律和法規。

此整合不會發佈任何資料主體隱私權（例如GDPR），刪除或處理任何其他隱私權要求（選擇退出除外）。 在處理隱私權要求時，您應該在Microsoft Dynamics 365和Campaign（透過Adobe Experience Platform隱私權服務）中單獨執行。

如果您已設定整合，在Dynamics 365中刪除連絡人時，對促銷活動發出定期的描述檔刪除呼叫，請遵循下列步驟。 確保在此過程中未對相關記錄進行更新。

1. 向[Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)發出隱私權刪除要求

1. 監控請求，直到成功完成

1. 確認記錄不再在您的促銷活動例項中

1. （不久之後）在Dynamics中發出隱私權刪除365

1. 驗證是否已從兩個系統中刪除記錄

以下連結可協助您在每個系統中實作存取和／或刪除隱私權相關要求：

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>如果任何促銷活動自訂資源記錄包含客戶使用促銷活動時適用的個人資訊，該記錄應連結至對應的促銷活動描述檔記錄（直接或透過其他自訂資源），如此，描述檔記錄上的隱私權相關刪除也可以刪除包含個人資訊的連結自訂資源記錄；必須配置實體之間的連結和刪除選項，以啟用連結記錄的類級聯刪除。 個人資訊不應輸入至未連結至描述檔的自訂資源。

## 退出{#opt-out}

由於Microsoft Dynamics 365和Campaign之間的退出屬性不同，以及每個客戶的業務需求不同，因此選擇退出對應仍留作客戶完成的練習。  請務必確保退出選項在系統之間正確映射，以便維護最終用戶退出首選項，並且他們不會通過他們選擇退出的通道接收通信。

請注意，只有下列項目才可用於退出對應：

* 具有「不再透過電子郵件聯絡」首碼的促銷活動屬性，或

* CCPA的特定屬性

有關「描述檔實體」欄位的詳細資訊，請參閱[這裡](../../developing/using/datamodel-profile.md)。

在Dynamics 365中，大部分的退出欄位都有「donot」首碼，但是，如果資料類型相容，您也可以利用其他屬性來退出。

在布建整合時，您將有機會指定您的企業需要何種退出設定：

* **單向(Microsoft Dynamics 365 to Campaign)**:Dynamics 365是退出的真相。退出屬性將會在從Dynamics 365到Campaign Standard的一個方向上同步
* **單向（促銷活動至Microsoft Dynamics 365）**:「促銷活動標準」是退出的真相來源。退出屬性將會在從Campaign Standard到Dynamics 365的一個方向上同步
* **雙向**:Dynamics 365 AND Campaign Standard是真相的來源。退出屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有個別的程式來管理系統之間的退出同步，則可停用整合的退出資料流。

雙向選擇退出配置使用邏輯確定要寫入兩個系統的值。 邏輯會比較兩個系統之間的時間戳記（Dynamics 365中的記錄層級變更、Campaign中的屬性層級變更），以判斷哪個系統佔上風。 如果「促銷活動」包含較新的時間戳記，則會優先使用「促銷活動」值。 如果Dynamics 365包含較新的時間戳記，或者等於，則opt-out=TRUE將會成功（假設其中一個值為TRUE）。

瞭解如何在[本節](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)中選取選擇加入／退出選項。

>[!NOTE]
>
>請檢閱並視需要更新Adobe Campaign中的預設和特定類型規則，然後再在此處進行變更，以確保這些變更正確套用至所有傳出的通訊。 例如，請確定任何對應至選擇退出偏好設定的對應，都能準確反映收件者的意圖／通訊選擇，且不會不慎中斷傳送關係或交易訊息，例如客戶訂單確認。

如果您選取「**雙向**&#x200B;或&#x200B;**單向（促銷活動至Microsoft Dynamics 365）**&#x200B;選擇退出設定」，促銷活動選擇退出資料將會透過工作流程定期匯出至您的促銷活動SFTP儲存區（請參閱下方的促銷活動SFTP使用情形）。 如果您的促銷活動選擇退出工作流程停止執行，您需要盡快手動重新啟動，以降低錯過選擇退出同步的可能性。

>[!IMPORTANT]
>
>如果您需要&#x200B;**Bidirectional**&#x200B;或&#x200B;**單向(Campaign to Microsoft Dynamics 365)**&#x200B;選擇退出設定，則需要向Adobe技術聯絡人提出要求，以便在您的促銷活動實例上設定選擇退出工作流程

## 促銷活動SFTP使用

您的促銷活動SFTP儲存空間需要透過以下使用案例的整合來使用。  您需要確保您的SFTP帳戶有足夠的儲存容量來容納這些使用案例。 超過授權的SFTP儲存容量可能會嚴重削弱Campaign、整合和／或SFTP帳戶的功能使用。

| 使用案例 | 說明 |
|---|---|
| 雙向和單向(Campaign to Microsoft Dynamics 365) | 雙向和單向(Campaign to Microsoft Dynamics 365)選擇退出資料流將會使用Campaign SFTP儲存空間。 促銷活動工作流程會將增量變更匯出至SFTP資料夾。 從那裡，整合將會擷取記錄和程式。 |
| 退出記錄檔 | 在疑難排解整合時，從連接器輸出記錄檔會很有幫助。 輸出記錄檔可以開啟／關閉。 |


>[!IMPORTANT]
>
>您需負責從SFTP資料夾存取和下載的資訊。 如果資訊包含個人資料，您有責任遵守任何適用的隱私權法律和法規。 [進一步瞭解](#acs-msdyn-manage-privacy)。

## 資料管理

### 現有促銷活動資料

此整合將同步從Microsoft Dynamics 365到Campaign的連絡人和自訂實體。 整合不會修改在整合以外建立的促銷活動記錄（亦即，不是由同步工作建立），包括整合設定時現有的促銷活動記錄。

由於此整合使用Campaign中的&#x200B;**[!UICONTROL externalId]**&#x200B;欄位，將促銷活動描述檔記錄與Dynamics 365連絡人記錄同步，因此必須填入Microsoft Dynamics 365 **[!UICONTROL contactId]**&#x200B;的此促銷活動欄位(**[!UICONTROL externalId]**)，才能將您想要與Microsoft Dynamics 365同步的記錄填入。  自訂實體也會使用Microsoft Dynamics 365唯一ID進行同步化。 「促銷活動」自訂實體需要將此ID屬性包含為表格欄。 externalId欄可用來儲存此屬性值，但促銷活動自訂實體不需要它。

請記住，Microsoft Dynamics 365仍是真相的來源，而且當整合偵測到Dynamics 365端的更新時，促銷活動描述檔資料可以覆寫。  視您現有的部署而定，也可能需要其他步驟來啟用整合；因此，建議您與Adobe技術聯絡人密切合作。

>[!NOTE]
>
>由於現有客戶部署的複雜性，建議您在規劃和設定整合時與Adobe技術聯絡人合作。

### 資料同步頻率

整合採用的架構可讓更新在Microsoft Dynamics 365中發生後不久即偵測並新增至處理「佇列」（即串流，而非批次處理）。 因此，不需要指定資料流執行頻率或排程。

這個例外是雙向和Dynamics 365選擇退出資料流的促銷活動。 對於這些選擇退出設定，更新的促銷活動記錄會透過促銷活動工作流程每天匯出一次至SFTP，之後整合工具會讀取檔案並處理記錄。

### 資料使用協定

如果您位於EMEA或APAC地區，部分資料將會在美國處理，做為此項整合的一部分。 如需詳細資訊，請參閱[本區段](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 護欄和限制

>[!IMPORTANT]
>
>您的特定動作（例如初始錄入記錄、重新播放記錄資料等） 可能導致大量記錄從Microsoft Dynamics 365擷取至您的Adobe Campaign實例。 為降低效能問題的風險，建議您停止所有促銷活動程式（例如，無行銷活動、無工作流程執行等） 直到大量記錄已收錄到促銷活動中為止。

### 自訂實體

[Microsoft Dynamics 365-Adobe Campaign Standard整合](../../integrating/using/d365-acs-get-started.md)支援自訂實體，讓Dynamics 365中的自訂實體與Campaign中的對應自訂資源同步。

整合支援連結和非連結的表格。

設定自訂實體資料流時，請務必注意下列事項：

* 建立和修改促銷活動自訂資源是敏感作業，必須由專業使用者執行。
* 對於自訂實體資料流，必須在Dynamics 365中為同步化的自訂實體啟用變更追蹤。
* 如果在Dynamics 365中建立父記錄和連結的子記錄時，由於並行處理整合，因此在其父記錄之前，可能會將新的子記錄寫入Campaign。

* 如果父記錄和子記錄使用&#x200B;**1基數簡單連結**&#x200B;選項在促銷活動方面連結，子記錄將保持隱藏且無法存取（透過UI或API），直到父記錄到達Campaign。

* （假設促銷活動中&#x200B;**1基數簡單連結**）如果子記錄在Dynamics 365中更新或刪除，且該變更在父記錄顯示於促銷活動之前已寫入促銷活動（不可能，但是遠端可能），該更新或刪除不會在促銷活動中處理，且會擲回錯誤。 在更新時，相關記錄需要在Dynamics 365中再次更新，才能同步更新的記錄。 若是刪除，相關記錄需要在促銷活動端個別處理，因為Dynamics 365中不再有要刪除或更新的記錄。

* 如果您遇到您認為有隱藏的子記錄而無法訪問這些記錄的情況，可以暫時將基數連結類型更改為&#x200B;**0或1基數簡單連結**&#x200B;以訪問這些記錄。

有關促銷活動自訂資源的更完整概觀，請參閱本節[。](../../developing/using/key-steps-to-add-a-resource.md)

### 整合護欄

在計畫使用此整合時，應考慮以下護欄。 如果您認為超過這些防護欄，請洽詢您的Adobe技術代表。

* 您需要授權適當的促銷活動套件，以支援整合產生的引擎呼叫量。 超過授權的引擎呼叫量可能會導致促銷活動效能降低。

   使用下列功能，協助估計整合的引擎呼叫量：

   * 記錄插入（即新記錄）:1個引擎呼叫
   * 記錄刪除：1個引擎呼叫
   * 記錄更新：2個引擎呼叫（只有當目標籤錄與來源記錄相同時，才會有1個呼叫——亦即，如果促銷活動記錄沒有變更）

   在估計整體促銷活動引擎呼叫量時，請務必考慮其他引擎呼叫來源，包括著陸頁面、WebApps、JSSP、API、行動應用程式註冊等。

   在這裡檢視促銷活動套件資訊：https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* 整合支援最多3000萬個連絡人。

* 標準整合方案支援最多5個自訂實體，每個實體最多50欄大小。

* 在實作整合之前，您需要建立並發佈自訂資源。

* 連結表時的表深度上限為2（即表1->表2->表3）

* 對Microsoft Dynamic 365資料類型的支援有限。 如果您的資料模型包含簡單資料類型以外的資料類型（例如字串、整數、小數等），您可能需要在使用整合之前更新資料模型。

* 如果您選擇保留促銷活動自訂實體中的現有資料，則需要準備整合的資料。

* Adobe和客戶之間可能需要建立入門維護視窗。

* 請注意，整合的使用量大幅增加或「尖峰」（例如，新記錄或更新記錄的大幅增加）可能會造成資料同步的緩慢。

* 在整合中，您需要完成Microsoft Azure和Dynamics 365中的預先整合設定步驟。 請參閱本頁的配置步驟[](../../integrating/using/d365-acs-configure-d365.md)

* 預期您會將Dynamics 365和Campaign資料模型帶入整合，並加以維護。

### 整合邊界

此整合旨在解決Microsoft Dynamics 365和Campaign之間常見資料移動的一般使用案例，但並非要解決每個客戶的特定使用案例：

* 整合不會發佈任何隱私權（例如GDPR）刪除。 滿足最終用戶隱私要求的責任由客戶負責；此類要求應分別在Campaign（透過Adobe Experience Platform Privacy Service）和Dynamics 365中提出。 如有需要，整合會定期執行刪除，以協助進行資料同步。   請參閱[隱私權區段](#manage-privacy-requests)以取得詳細資訊。

* 促銷活動與Dynamics 365之間不會同步任何描述檔或自訂實體資料，但退出資訊除外（如果客戶已設定）。

* 促銷活動訂閱管理（即訂閱／取消訂閱）本身不受支援。

* 不支援從Dynamics 365內撰寫和觸發促銷活動電子郵件促銷活動。

* 整合&#x200B;**not**&#x200B;支援在Dynamics 365和Campaign Standard資料模型之間重新建立資料。 預計整合將會將一個Dynamics 365表格同步至一個Campaign表格。
