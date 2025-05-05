---
title: 擴充資料庫
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
source-wordcount: '446'
ht-degree: 2%

---

# 擴充資料庫{#enriching-the-database}

Campaign Standard提供數種工具，可協助您擴充行銷資料庫。 本節詳細說明可用來將資料插入Campaign的不同方法，以及專用檔案的參考資料。

## 透過工作流程匯入資料 {#importing-data-through-workflows}

工作流程可讓您收集資料，並透過使用[[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md)活動將其匯入Campaign資料庫。

透過工作流程匯入資料時，一般資訊和最佳實務會顯示在[本節](../../automating/using/about-data-import-and-export.md)中。

此外，您可以設定範本以匯入資料。 如果您需要定期匯入具有相同結構的檔案，使用匯入範本是最佳做法。

您可以設定兩種範本：

* **工作流程範本**：這些是預先設定的工作流程，您可以根據自己的需求設定一次，並在每次要匯入資料並更新資料庫時重複使用。

  [本節](../../automating/using/creating-import-workflow-templates.md)中詳細說明了匯入資料的工作流程範本範例。

* **匯入資料範本**：如同工作流程範本，這些範本是以工作流程為基礎，設定為上傳檔案以更新資料庫。 設定之後，使用者就可以在&#x200B;**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;功能表下使用簡化的檢視。

  如需匯入資料範本的詳細資訊，請參閱[專屬檔案](../../automating/using/importing-data-with-import-templates.md)。

## 從登入頁面收集資料 {#collecting-data-from-landing-pages}

登入頁面是網路表單，可用來收集資料，以及在資料庫中建立或更新現有資訊。

原理如下：

* 新增輸入欄位以收集資料（名字、姓氏、電子郵件等），藉此建立及設計您的登入頁面。
* 將每個輸入欄位與資料庫中的對應欄位對應。
* 透過網站或直接連結至訊息，線上上提供登入頁面。

如需登入頁面的詳細資訊，請參閱[專屬檔案](../../channels/using/getting-started-with-landing-pages.md)。

## 從Microsoft Dynamics 365同步設定檔

與Microsoft Dynamics 365整合的Campaign Standard可讓您將聯絡資料從Microsoft Dynamics 365傳遞至Campaign資料庫。
然後，這些聯絡人會顯示在設定檔清單中，並可在行銷活動中定位。

如需此整合的詳細資訊，請參閱[專屬檔案](../../integrating/using/d365-acs-get-started.md)。

>[!NOTE]
>
>請注意，Campaign Standard-Microsoft Dynamics 365聯結器目前為「有限可用性」，且有幾項限制，詳情請參閱本檔案。

## 透過API呼叫匯入資料

Campaign StandardAPI可讓您執行更新資料庫的操作，例如建立、更新或刪除設定檔或服務。

如需如何使用API的詳細資訊，請參閱[專屬檔案](../../api/using/get-started-apis.md)。

>[!IMPORTANT]
>
>在透過API呼叫執行設定檔大量建立或更新之前，請檢查與您的授權合約相對應的比例限制。 如需詳細資訊，請參閱[此頁面](https://helpx.adobe.com/tw/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
