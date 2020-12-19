---
solution: Campaign Standard
product: campaign
title: 端點
description: 進一步瞭解API端點。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---


# 端點 {#endpoints}

Adobe Campaign REST API的可用端點：

* **/profileAndServices**:與現成可用的欄位互動。此端點無法訪問擴展欄位。
* **/profileAndServicesExt**:與在描述檔或服務自訂資源擴充期間新增的自訂欄位互動。有關自定義資源的詳細資訊，請參閱[本節](../../api/using/custom-resources.md)。
* **/&lt;transactionalapi>**:與事務性消息API交互（事務性消息API端點的名稱取決於實例配置）。如需詳細資訊，請參閱[本章節](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**:與工作流程互動。如需詳細資訊，請參閱[本章節](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**:與隱私權API互動，允許自動處理隱私權要求。如需詳細資訊，請參閱[本章節](../../api/using/creating-a-privacy-request.md)。
* **/history**:擷取描述檔的行銷記錄。有關Campaign中整合式客戶個人檔案的詳細資訊，請參閱[ Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

根據預設，**profileAndServices**&#x200B;和&#x200B;**profileAndServicesExt** API的可用資源為：

* **/profile**:與Campaign資料庫的設定檔互動。要向服務添加配置檔案，請使用&#x200B;**/service**&#x200B;端點。 有關促銷活動中描述檔的詳細資訊，請參閱[促銷活動檔案](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/service**:管理訂閱服務。有關Campaign中服務的詳細資訊，請參閱[Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>所有已擴充或已建立的其他資源僅能透過&#x200B;**ProfileAndServicesExt** API使用。 它們必須連結到&#x200B;**Profile**&#x200B;資源，才能訪問。
