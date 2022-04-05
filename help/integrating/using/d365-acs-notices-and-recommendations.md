---
title: 市場活動和MicrosoftDynamics 365資料管理
description: 瞭解Campaign Standard和MicrosoftDynamics 365如何管理常見資料
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '2507'
ht-degree: 1%

---

# 最佳實務和限制 {#acs-msdyn-best-practices}

## 管理資料 {#acs-msdyn-manage-data}

對於聯繫人和自定義實體同步，此整合將處理 **Microsoft動力365，真相之源**。  對同步屬性的任何更改都應在Dynamics 365中完成，而不應在Adobe Campaign Standard)。  如果在「市場活動」中進行更改，則在同步過程中，這些更改最終會在「市場活動」中被覆蓋，因為同步是單向的。

整合可以根據需要配置，以便在Dynamics 365中刪除聯繫人時向市場活動發出配置檔案刪除呼叫，以幫助維護資料完整性。 但是，配置檔案刪除與隱私刪除不同。 市場活動中的隱私刪除將刪除市場活動配置檔案記錄和相關日誌條目；而常規配置檔案刪除只會刪除市場活動配置檔案記錄，將殘餘部分留在市場活動日誌中。 如果在整合中啟用了配置檔案刪除功能，則需要執行其他步驟才能正確處理資料主題隱私請求。 請參閱中的步驟 [下面的隱私部分](#manage-privacy-requests)。

## 隱私權{#acs-msdyn-manage-privacy}

此整合旨在在MicrosoftDynamics 365和Adobe Campaign Standard之間傳輸最終用戶資料。 如果最終用戶資料中包含此資料，則此資料包括個人資訊。  作為資料控制員，您的公司負責遵守適用於您收集和使用個人資料的任何隱私法律和法規。

此整合旨在在MicrosoftDynamics 365和Adobe Campaign Standard之間傳輸最終用戶資料(包括但不限於個人資訊（如果其包含在您的最終用戶資料中）。 作為資料控制員，您的公司負責遵守適用於您收集和使用個人資料的任何隱私法律和法規。

整合不會發佈任何資料主題隱私（例如，GDPR）刪除或處理任何其他隱私請求（選擇退出除外）。 處理隱私請求時，您應在MicrosoftDynamics 365和「活動」(通過Adobe Experience Platform Privacy Service)中獨立執行。

如果已將整合配置為在Dynamics 365中刪除聯繫人時向市場活動發出定期配置檔案刪除呼叫，則應執行以下步驟。 確保在此過程中未對有關記錄進行任何更新。

1. 發出隱私刪除請求 [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. 監視請求，直到成功完成

1. 驗證記錄是否不再位於市場活動實例中

1. （不久後）在Dynamics 365中發佈隱私刪除

1. 驗證記錄是否已從兩個系統中刪除

下面是幫助指導您在每個系統中實施訪問和/或刪除隱私相關請求的連結：

* [Microsoft動力365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>如果任何市場活動自定義資源記錄包含適用於客戶使用市場活動的個人資訊，則此類記錄應連結到相應的市場活動配置檔案記錄（直接或通過其他自定義資源），以便配置檔案記錄上的隱私相關刪除也可以刪除包含個人資訊的連結的自定義資源記錄；必須配置實體之間的連結和刪除選項，以啟用此類級聯式刪除連結的記錄。 個人資訊不應輸入到未連結到配置檔案的自定義資源中。

## 選擇退出 {#opt-out}

由於MicrosoftDynamics 365和市場活動之間的退出選項屬性不同，以及每個客戶的業務要求不同，退出選項映射被留待客戶完成。  必須確保在系統之間正確映射退出選項，以便保持最終用戶退出首選項，並且他們不會通過他們選擇退出的通道接收通信。

請注意，只有以下項才能用於選擇退出映射：

* 具有「不再通過聯繫」前置詞（例如，不再通過電子郵件聯繫）的市場活動屬性，或

* CCPA的特定屬性

有關配置檔案實體欄位的詳細資訊 [這裡](../../developing/using/datamodel-profile.md)。

在Dynamics 365中，大多數opt-out欄位具有「donot」前置詞，但是，如果資料類型相容，您還可以利用其他屬性來opt-out。

在設定整合時，您將有機會指定您為業務所需的選擇退出配置：

* **單向(MicrosoftDynamics 365到市場活動)**:Dynamics 365是退出選擇的真相來源。 Opt-out屬性將在從Dynamics 365到Campaign Standard的一個方向上同步
* **單向(MicrosoftDynamics 365營銷活動)**:Campaign Standard是退出選擇的真相來源。 從Campaign Standard到Dynamics 365將在一個方向上同步退出屬性
* **雙向**:Dynamics 365 ANDCampaign Standard是真理的源泉。 Opt-out屬性將在Campaign Standard和Dynamics 365之間雙向同步

或者，如果您有單獨的過程來管理系統之間的選擇退出同步，則可以禁用整合的選擇退出資料流。

雙向選擇退出配置使用邏輯來確定要寫入兩個系統的值。 該邏輯比較兩個系統之間的時間戳（Dynamics 365中的記錄級更改、市場活動中的屬性級更改），以確定哪個系統佔上風。 如果「市場活動」包含較新的時間戳，則「市場活動」值將佔上風。 如果Dynamics 365包含較新的時間戳，或者它們相等，則opt-out=TRUE將獲勝（假定其中一個值為TRUE）。

瞭解如何在中選擇選擇加入/退出選項 [此部分](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf)。

>[!NOTE]
>
>請在進行此處更改之前，查看並更新Adobe Campaign的預設和特定類型規則，以確保此類更改正確應用於所有傳出通信。 例如，請確保指向選擇退出首選項的任何映射都準確地反映了收件人的意圖/通信選擇，並且不會無意中中斷關係或事務性消息（如客戶訂單確認）的傳遞。

如果選擇了 **雙向** 或 **單向(MicrosoftDynamics 365營銷活動)** 選擇退出配置，市場活動選擇退出資料將通過工作流定期導出到您的市場活動SFTP儲存區（請參閱下面的市場活動SFTP使用情況）。 如果您的市場活動選擇退出工作流停止運行，您需要盡快手動重新啟動以減少錯過選擇退出同步的可能性。

>[!IMPORTANT]
>
>如果你需要 **雙向** 或 **單向(MicrosoftDynamics 365營銷活動)** 選擇退出配置，您需要向Adobe技術聯繫人請求在市場活動實例上設定選擇退出工作流

## 市場活動SFTP使用情況

您的市場活動SFTP儲存需要在以下使用案例中進行整合。  您需要確保您的SFTP帳戶有足夠的儲存容量來容納這些使用情形。 超過許可的SFTP儲存容量可能會嚴重影響市場活動、整合和/或SFTP帳戶的功能使用。

| 使用案例 | 說明 |
|---|---|
| 雙向和單向(Campig to Bendicial Dynamics 365) | 雙向和單向(MicrosoftDynamics 365的活動)選擇退出資料流將利用活動SFTP儲存。 市場活動工作流將增量更改導出到SFTP資料夾。 從那裡，整合將收集記錄和流程。 |
| 選擇退出日誌 | 在排除整合故障時，從連接器輸出日誌將很有幫助。 可以開啟/關閉輸出日誌。 |


>[!IMPORTANT]
>
>您負責從SFTP資料夾訪問和下載的資訊。 如果資訊包含個人資料，您應負責遵守任何適用的隱私法律和法規。 [了解更多資訊](#acs-msdyn-manage-privacy)。

## 資料管理

### 現有市場活動資料

此整合將將聯繫人和自定義實體從MicrosoftDynamics 365同步到市場活動。 在整合之外建立的市場活動記錄（即，不是由同步作業建立的）不會由整合修改，包括整合配置時存在的市場活動記錄。

因為這個整合 **[!UICONTROL externalId]** 「市場活動」欄位，用於將市場活動配置檔案記錄與Dynamics 365聯繫人記錄同步，此「市場活動」欄位(**[!UICONTROL externalId]** )必須填充MicrosoftDynamics 365 **[!UICONTROL contactId]** 從MicrosoftDynamics 365同步的記錄。  自定義實體也使用MicrosoftDynamics 365唯一ID進行同步。 市場活動自定義實體需要將此ID屬性作為表列。 外部Id列可用於儲存此屬性值，但市場活動自定義實體不需要它。

請記住，MicrosoftDynamics 365仍是真相的來源，並且當整合檢測到Dynamics 365端的更新時，市場活動配置檔案資料可以被覆蓋。  還可能需要其他步驟來啟用整合，具體取決於您現有的部署；因此，建議您與Adobe技術聯繫人密切合作。

>[!NOTE]
>
>由於現有客戶部署的複雜性，建議您在規劃和設定整合時與Adobe技術聯繫人合作。

### 資料同步頻率

該整合利用一種體系結構，該體系結構允許在MicrosoftDynamics 365中發生更新（即流處理，而不是批處理）後不久檢測更新並將其添加到處理「隊列」中。 因此，無需指定資料流運行頻率或調度。

這種情況的例外是雙向和Camping to Dynamics 365 opt-out資料流。 對於這些選擇退出配置，更新的市場活動記錄將通過市場活動工作流每天導出一次到SFTP，然後整合工具將讀取檔案並處理記錄。

### 資料使用協定

如果您位於EMEA或APAC地區，則部分資料將在美國處理，作為此整合的一部分。 如需詳細資訊，請參閱[本區段](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 護欄和限制

>[!IMPORTANT]
>
>您的某些操作（例如，初始接收記錄、重放記錄資料等） 可能導致從MicrosoftDynamics 365將大量記錄攝取到您的Adobe Campaign實例。 為降低效能問題的風險，建議您停止所有市場活動流程（例如，無市場活動、無工作流運行等） 直到大量記錄被攝入市場活動。

### 自定義實體

的 [Microsoft動力365-Adobe Campaign Standard一體化](../../integrating/using/d365-acs-get-started.md) 支援自定義實體，使Dynamics 365中的自定義實體能夠與市場活動中的相應自定義資源同步。

整合支援連結表和非連結表。

配置自定義實體資料流時，必須注意以下事項：

* 建立和修改市場活動自定義資源是敏感操作，必須僅由專家用戶執行。
* 對於自定義實體資料流，必須在Dynamics 365中為同步的自定義實體啟用更改跟蹤。
* 如果在Dynamics 365中幾乎同時建立父記錄和連結的子記錄，則由於整合的並行處理，新子記錄在其父記錄之前被寫入市場活動的可能性很小。

* 如果父項和子項在「市場活動」端使用 **1個基數簡單連結** 選項，在父記錄到達「市場活動」之前，子記錄將保持隱藏且不可訪問（通過UI或API）。

* (假設 **1個基數簡單連結** 在市場活動中)如果在Dynamics 365中更新或刪除了子記錄，並且在市場活動中顯示父記錄之前將該更改寫入市場活動（不可能，但是可能是遠程），則該更新或刪除將不會在市場活動中處理，並且將引發錯誤。 在更新的情況下，需要在Dynamics 365中再次更新有關的記錄，以便同步更新的記錄。 在刪除的情況下，需要在市場活動方面單獨處理有關的記錄，因為Dynamics 365中不再有要刪除或更新的記錄。

* 如果遇到您認為有隱藏的子記錄並且無法訪問這些記錄的情況，則可以將基數連結類型臨時更改為 **0或1基數簡單連結** 來訪問那些記錄。

可以找到市場活動定制資源的更全面概覽 [此部分](../../developing/using/key-steps-to-add-a-resource.md)。

### 整合護欄

在計畫使用此整合時，應考慮以下護欄。 如果您認為超過這些護欄，請咨詢您的Adobe技術代表。

* 您需要授權適當的市場活動包，以支援整合生成的引擎呼叫量。 超過許可的引擎調用量可能會導致市場活動效能下降。

   使用以下內容幫助從整合中估計引擎調用量：

   * 記錄插入（即新記錄）:1個引擎呼叫
   * 記錄刪除：1個引擎呼叫
   * 記錄更新：2個引擎呼叫（如果目標籤錄與來源記錄相同，則僅1個呼叫 — 即，如果市場活動記錄沒有更改）

   在估計整個市場活動引擎調用量時，必須考慮其他引擎調用來源，包括登錄頁、WebApps、JSSP、API、移動應用註冊等。

   在此處查看Adobe Campaign Standard包資訊： [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)

* 該整合最多支援1500萬條記錄，用於市場活動中與資源的初始同步。 增量同步受Adobe Campaign Standard包的限制。

* 標準整合產品包括對多達20個自定義實體的支援，每個實體的大小最多為50列。

* 在實施整合之前，您需要建立並發佈自定義資源。

* 連結表時的最大表深度為兩個（即表1->表2->表3）

* 整合支援每個自定義資源最多5個連結列。 在自定義資源之間連結多列可能會對效能產生顯著影響。 **0或1基數簡單連結** 優先於 **1個基數簡單連結**。

* 整合支援基元MicrosoftDynamics 365資料類型（布爾型、整數型、小數型、雙精度型、字串型、DateTime型、日期型）和Adobe Campaign Standard資料類型（整數型、布爾型、浮點型、雙精度型、日期型、日期時間型、字串型）之間的轉換。 更多高級資料類型將解釋為字串，並按原樣同步。

* 登機維護窗口可能需要在Adobe和客戶之間建立。

* 請注意，整合的使用量顯著增加或「峰值」（例如，新記錄或更新記錄的急劇增加）可能會導致資料同步速度減慢。

* 作為整合的一部分，您應在MicrosoftAzure和Dynamics 365中完成整合前配置步驟。 請參閱配置步驟 [此頁](../../integrating/using/d365-acs-configure-d365.md)

* 預計您將將Dynamics 365和Campaign資料模型引入整合併維護它們。

### 整合邊界

此整合旨在解決MicrosoftDynamics 365和市場活動之間常見資料移動的一般使用情形，但它並不旨在解決每個客戶特有的每個使用情形：

* 整合不會發出任何隱私（如GDPR）刪除。 滿足最終用戶隱私請求的責任由客戶承擔；應在運動(通過Adobe Experience Platform Privacy Service)和Dynamics 365中獨立提出這種要求。 如果需要，整合可以發出常規刪除，以幫助實現資料同步。   審閱 [隱私部分](#manage-privacy-requests) 的子菜單。

* 將不會將任何配置檔案或自定義實體資料從市場活動同步到Dynamics 365，但選擇退出資訊除外（如果由客戶配置）。

* 市場活動訂閱管理（即訂閱/未訂閱）不受本機支援。

* 不支援從Dynamics 365內撰寫和觸發市場活動電子郵件活動。

* 整合可以 **不** 支援在Dynamics 365和Campaign Standard資料模型之間重構資料。 預計整合將將一個Dynamics 365表同步到一個Campaign表。
