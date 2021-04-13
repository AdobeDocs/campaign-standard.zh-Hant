---
solution: Campaign Standard
product: campaign
title: 自訂資源
description: 進一步瞭解使用API進行自訂資源管理/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
translation-type: tm+mt
source-git-commit: 01e4eb027b55815c3680b26691e61cbe5b63ee8c
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 3%

---

# 與自訂資源互動 {#interacting-with-custom-resources}

**/customResources**&#x200B;端點可讓您在REST中公開Campaign自訂資源。 根據此API，可使用自訂實體與外部端點之間的整合。

/customResources端點的行為與/profileAndServices端點完全相同。

此API中公開的自訂資源包括：

* 未在/profileAndServicesExt下公開的所有項
* 所有與個人檔案無關的實體，以及這些實體的子孫。
* 預設情況下，所有與任何事物無關的實體及其子孫。

>[!NOTE]
>/profileAndServicesExt下可用的自訂資源不會公開於/customResources API中。


以下是從自訂資源擷取中繼資料的範例：

```
GET /customResources/resourceType/<customResourceName>
```

要執行建立、更新或刪除，使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>隱私權API端點和工作流程(/privacy/privacyTool)不會管理未連結至描述檔實體的自訂資源。
>您有責任為這些自訂資源管理和清除任何PII。 有關隱私工具的詳細資訊，請按一下這裡[。](../../api/using/creating-a-privacy-request.md)
