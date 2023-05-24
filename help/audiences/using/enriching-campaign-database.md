---
title: 豐富資料庫
description: 瞭解豐富資料庫的各種方法。
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 3%

---

# 豐富資料庫{#enriching-the-database}

Campaign Standard提供了多種工具來幫助您擴展營銷資料庫。 本部分詳細說明了可用於向市場活動中注入資料的不同方法，其中引用了專用文檔。

## 通過工作流導入資料 {#importing-data-through-workflows}

工作流允許您通過使用 [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) 活動。

通過工作流導入資料時的一般資訊和最佳做法在中介紹 [此部分](../../automating/using/about-data-import-and-export.md)。

此外，還可以設定模板以導入資料。 如果需要定期導入具有相同結構的檔案，則使用導入模板是最佳做法。

可以設定兩種類型的模板：

* **工作流模板**:這些是預配置的工作流，您可以根據需要設定一次，並在每次要導入資料和更新資料庫時重複使用。

   有關導入資料的工作流模板示例的詳細資訊，請參見 [此部分](../../automating/using/creating-import-workflow-templates.md)。

* **導入資料模板**:與工作流模板一樣，這些模板是基於工作流的模板，設定為上載檔案以更新資料庫。 配置後，用戶可以在 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** 的子菜單。

   有關導入資料模板的詳細資訊，請參閱 [專用文檔](../../automating/using/importing-data-with-import-templates.md)。

## 從登錄頁收集資料 {#collecting-data-from-landing-pages}

登錄頁是Web表單，可用於收集資料並建立或更新資料庫中的現有資訊。

其原理是：

* 通過添加輸入欄位來收集資料（名字、姓氏、電子郵件等）來建立和設計登錄頁。
* 將每個輸入欄位與資料庫中的相應欄位映射。
* 通過網站或消息的直接連結使登錄頁線上可用。

有關登錄頁的詳細資訊，請參閱 [專用文檔](../../channels/using/getting-started-with-landing-pages.md)。

## 正在同步MicrosoftDynamics 365中的配置檔案

Campaign Standard與MicrosoftDynamics 365的整合允許您將聯繫資料從MicrosoftDynamics 365傳遞到市場活動資料庫。
然後，這些聯繫人可在「配置檔案」清單中看到，並可以在市場營銷市場活動中定位。

有關此整合的詳細資訊，請參閱 [專用文檔](../../integrating/using/d365-acs-get-started.md)。

>[!NOTE]
>
>請注意，Campaign Standard-Microsoft Dynamics 365連接器當前處於有限可用性中，並且受到多個限制，詳見文檔。

## 通過API調用導入資料

Campaign StandardAPI允許您執行更新資料庫的操作，如配置檔案或服務的建立、更新或刪除。

有關如何使用API的詳細資訊，請參閱 [專用文檔](../../api/using/get-started-apis.md)。

>[!IMPORTANT]
>
>在通過API調用執行配置式成批建立或更新之前，請檢查與許可協定對應的比例限制。 如需詳細資訊，請參閱[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
