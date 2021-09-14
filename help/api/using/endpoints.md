---
title: 端點
description: 深入了解API端點。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---

# 端點 {#endpoints}

Adobe Campaign REST API的可用端點：

* **/profileAndServices**:與現成可用的欄位互動。此端點無法存取延伸欄位。
* **/profileAndServicesExt**:與設定檔或服務自訂資源擴充期間新增的自訂欄位互動。如需自訂資源的詳細資訊，請參閱[此區段](../../api/using/custom-resources.md)。
* **/&lt;transactionalapi>**:與交易式訊息API互動（交易式訊息API端點的名稱取決於您的執行個體設定）。如需詳細資訊，請參閱[本章節](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**:與工作流程互動。如需詳細資訊，請參閱[本章節](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**:與隱私權API互動，以允許自動處理隱私權要求。如需詳細資訊，請參閱[本章節](../../api/using/creating-a-privacy-request.md)。
* **/history**:擷取設定檔的行銷歷史記錄。如需Campaign中整合式客戶設定檔的詳細資訊，請參閱[Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

預設情況下，**profileAndServices**&#x200B;和&#x200B;**profileAndServicesExt** API的可用主要資源為：

* **/profile**:從Campaign資料庫與設定檔互動。若要將設定檔新增至服務，請使用&#x200B;**/service**&#x200B;端點。 如需Campaign中設定檔的詳細資訊，請參閱[Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/service**:管理訂閱服務。如需Campaign中服務的詳細資訊，請參閱[Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>所有已擴展或已建立的其他資源僅可通過&#x200B;**ProfileAndServicesExt** API使用。 必須將它們連結到&#x200B;**Profile**&#x200B;資源，才能訪問。
