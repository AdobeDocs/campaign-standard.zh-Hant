---
title: 端點
description: 進一步瞭解API端點。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f251e4b5187aa09f65a5d8d6215f208a09cd9159

---


# 端點 {#endpoints}

Adobe Campaign REST API的可用端點：

* **/profileAndServices**:與現成可用的欄位互動。 此端點無法訪問擴展欄位。
* **/profileAndServicesExt**:與在描述檔或服務自訂資源擴充期間新增的自訂欄位互動。 For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI&gt;**:與事務性消息API交互（事務性消息API端點的名稱取決於實例配置）。 如需詳細資訊，請參閱[本小節](../../api/using/managing-transactional-messages.md)。
* **/workflow/execution**:與工作流程互動。 如需詳細資訊，請參閱[本小節](../../api/using/controlling-a-workflow.md)。
* **/privacy/privacyTool**:與隱私權API互動，允許自動處理隱私權要求。 如需詳細資訊，請參閱[本小節](../../api/using/creating-a-privacy-request.md)。
* **/history**:擷取描述檔的行銷記錄。 有關Campaign中整合式客戶個人檔案的詳細資訊，請參閱 [Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)。

依預設，profileAndServices和profileServicesExt **API的可用****** 主要資源為：

* **/profile**:與Campaign資料庫的設定檔互動。 要向服務添加配置檔案，請使用 **/service端點** 。 如需有關Campaign中描述檔的詳細資訊，請參閱 [Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)。
* **/service**:管理訂閱服務。 有關Campaign中服務的詳細資訊，請參閱 [Campaign檔案](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)。

>[!NOTE]
>
>所有已擴充或建立的其他資源都只能透過 **ProfileAndServicesExt** API使用。 必須將其連結至 **Profile** 資源，才能存取。
