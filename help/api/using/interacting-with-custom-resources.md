---
title: 與自訂資源互動
description: 瞭解有關使用API進行自定義資源管理的詳細資訊/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 4%

---

# 與自訂資源互動 {#interacting-with-custom-resources}

的 **/customResources** 終結點允許您在REST中公開市場活動自定義資源。 基於此API，可在自定義實體和外部端點之間整合。

/customResources終結點的行為與/profileAndServices終結點完全相同。

此API中公開的自定義資源包括：

* 未在/profileAndServicesExt下公開的所有實體
* 所有與側寫無關的實體，以及這些實體的子女和孫輩。
* 預設情況下，所有與任何事物沒有關聯的實體，以及它們的子孫。

>[!NOTE]
>在/profileAndServicesExt下可用的自定義資源在/customResources API中不公開。


以下是從自定義資源檢索元資料的示例：

```
GET /customResources/resourceType/<customResourceName>
```

要執行建立、更新或刪除，將使用GET、POST、PATCH、DELETE。

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>隱私API終結點和工作流(/privacy/privacyTool)未管理未連結到配置檔案實體的自定義資源。
>您將負責管理和清理這些自定義資源的任何PII。 有關隱私工具的詳細資訊， [按一下這裡](../../api/using/creating-a-privacy-request.md)。
