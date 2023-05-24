---
title: 端點
description: 瞭解有關API端點的詳細資訊。
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

Adobe CampaignREST API的可用端點：

* **/profileAndServices**:與框外欄位交互。 此終結點無法訪問擴展欄位。
* **/profileAndServicesExt**:與配置檔案或服務自定義資源擴展期間添加的自定義欄位交互。 有關自定義資源的詳細資訊，請參閱 [此部分](../../api/using/custom-resources.md)。
* **/&lt;transactionalapi>**:與事務性消息API交互（事務性消息API終結點的名稱取決於實例配置）。 如需詳細資訊，請參閱[本章節](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**:與工作流交互。 如需詳細資訊，請參閱[本章節](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**:與隱私API交互以允許隱私請求的自動處理。 如需詳細資訊，請參閱[本章節](../../api/using/creating-a-privacy-request.md)。
* **/歷史記錄**:檢索配置檔案的市場營銷歷史記錄。 有關市場活動中整合客戶配置檔案的詳細資訊，請參閱 [市場活動文檔](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

預設情況下，可用於 **配置檔案和服務** 和 **配置檔案和服務擴展** API包括：

* **/配置檔案**:與市場活動資料庫中的配置檔案交互。 要向服務添加配置檔案，請使用 **/服務** 端點。 有關「市場活動」中的配置檔案的詳細資訊，請參閱 [市場活動文檔](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/服務**:管理訂閱服務。 有關「市場活動」中服務的詳細資訊，請參閱 [市場活動文檔](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>所有已擴展或建立的其他資源都可通過 **配置檔案和服務擴展** 僅API。 它們必須與 **配置檔案** 資源，以便可訪問。
