---
title: 擴充資料庫
description: 了解擴充資料庫的各種方法。
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

# 擴充資料庫{#enriching-the-database}

Campaign Standard提供數種工具，可協助您擴充行銷資料庫。 本節詳細說明您可用來將資料插入Campaign的不同方法，以及專用檔案的參考。

## 透過工作流程匯入資料 {#importing-data-through-workflows}

工作流程可讓您透過 [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) 活動。

透過工作流程匯入資料時的一般資訊和最佳實務顯示於 [本節](../../automating/using/about-data-import-and-export.md).

此外，您也可以設定範本以匯入資料。 如果您需要定期匯入具有相同結構的檔案，最好使用匯入範本。

您可以設定兩種類型的範本：

* **工作流程範本**:這些是預先配置的工作流，您可以根據需要設定一次，並在每次要導入資料和更新資料庫時重複使用。

   匯入資料的工作流程範本範例在 [本節](../../automating/using/creating-import-workflow-templates.md).

* **匯入資料範本**:與工作流模板一樣，這些模板是基於工作流的模板，設定為上載檔案以更新資料庫。 設定後，使用者可在 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** 功能表。

   如需匯入資料範本的詳細資訊，請參閱 [專屬檔案](../../automating/using/importing-data-with-import-templates.md).

## 從登錄頁面收集資料 {#collecting-data-from-landing-pages}

登錄頁面是網頁表單，可用來收集資料，以及建立或更新資料庫中的現有資訊。

原則如下：

* 新增輸入欄位以收集資料（名字、姓氏、電子郵件等），以建立並設計您的登錄頁面。
* 將每個輸入欄位與資料庫中的對應欄位對應。
* 讓登錄頁面可透過網站或透過訊息的直接連結線上取得。

如需登錄頁面的詳細資訊，請參閱 [專屬檔案](../../channels/using/getting-started-with-landing-pages.md).

## 從Microsoft Dynamics同步設定檔365

Campaign Standard與Microsoft Dynamics 365的整合可讓您將聯絡資料從Microsoft Dynamics 365傳遞至Campaign資料庫。
然後，這些聯絡人會顯示在「設定檔」清單中，並可定位在行銷活動中。

如需此整合的詳細資訊，請參閱 [專屬檔案](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>請注意，Campaign Standard-Microsoft Dynamics 365連接器目前處於有限可用性，且受數個限制的限制，詳情請見本檔案。

## 透過API呼叫匯入資料

Campaign StandardAPI可讓您執行更新資料庫的操作，例如設定檔或服務的建立、更新或刪除。

如需如何使用API的詳細資訊，請參閱 [專屬檔案](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>在透過API呼叫執行設定檔大量建立或更新之前，請檢查與您的授權合約相對應的比例限制。 如需詳細資訊，請參閱[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
