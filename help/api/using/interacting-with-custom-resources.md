---
title: 自訂資源
description: 進一步了解使用API進行自訂資源管理/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 3%

---

# 與自訂資源互動 {#interacting-with-custom-resources}

**/customResources**&#x200B;端點可讓您在REST中公開Campaign自訂資源。 根據此API，可使用自訂實體與外部端點之間的整合。

/customResources端點的行為與/profileAndServices端點完全相同。

此API中公開的自訂資源為：

* 未在/profileAndServicesExt下公開的所有實體
* 所有與個人資料沒有關聯的實體，對於這些實體來說，還包括他們的子女和孫輩。
* 預設情況下，所有與任何事物無關的實體及其子女和孫輩。

>[!NOTE]
>/profileAndServicesExt下可用的自訂資源不會公開於/customResources API中。


以下是從自訂資源擷取中繼資料的範例：

```
GET /customResources/resourceType/<customResourceName>
```

要執行建立、更新或刪除，將使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>隱私權API端點和工作流程(/privacy/privacyTool)無法管理未連結至設定檔實體的自訂資源。
>您有責任管理和清除這些自訂資源的任何PII。 有關隱私工具的詳細資訊，請[按一下這裡](../../api/using/creating-a-privacy-request.md)。
