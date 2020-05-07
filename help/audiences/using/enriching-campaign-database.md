---
title: 豐富資料庫
description: 瞭解豐富資料庫的各種方法。
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 豐富資料庫{#enriching-the-database}

Campaign Standard提供數種工具來協助您擴充行銷資料庫。 本節詳細說明您可使用不同方法將資料插入Campaign，並參考專用檔案。

## 透過工作流程匯入資料 {#importing-data-through-workflows}

工作流程可讓您收集資料，並透過使用活動將其匯入Campaign資 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) 料庫。

本節將介紹在透過工作流程匯入資料時的一般資訊和最佳 [實務](../../automating/using/importing-data.md)。

此外，您還可以設定範本以匯入資料。 如果您需要定期匯入具有相同結構的檔案，請使用匯入範本是最佳做法。

您可以設定兩種範本類型：

* **工作流程範本**: 這些是預先設定的工作流程，您可視需要設定一次，而且每次您要匯入資料並更新資料庫時，都可重複使用。

   本節將詳細介紹導入資料的工作流模 [板示例](../../automating/using/importing-data.md#example--import-workflow-template)。

* **匯入資料範本**: 像工作流程範本一樣，這些範本是以工作流程為基礎的範本，可設定為上傳檔案以更新資料庫。 在設定後，使用者可在 **[!UICONTROL Profile & audiences]** /功能表下以簡化檢視來使 **[!UICONTROL Imports]** 用它。

   如需匯入資料範本的詳細資訊，請參閱專 [用檔案](../../automating/using/importing-data-with-import-templates.md)。

## 從著陸頁面收集資料 {#collecting-data-from-landing-pages}

登陸頁面是Web表單，可用來收集資料並建立或更新資料庫中的現有資訊。

其原則如下：

* 新增輸入欄位以收集資料（名字、姓氏、電子郵件等），以建立並設計您的登陸頁面。
* 將每個輸入欄位與資料庫中的相應欄位映射。
* 透過網站或訊息的直接連結，讓登陸頁面線上上提供。

如需著陸頁面的詳細資訊，請參閱專 [用檔案](../../channels/using/getting-started-with-landing-pages.md)。

## 從Microsoft Dynamics 365同步設定檔

Campaign Standard與Microsoft Dynamics 365的整合可讓您將Microsoft Dynamics 365的連絡人資料傳遞至Campaign資料庫。
然後，這些連絡人會顯示在「設定檔」清單中，並可定位在行銷促銷活動中。

如需此整合的詳細資訊，請參閱專 [用檔案](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

>[!NOTE]
>
>請注意，Campaign Standard-Microsoft Dynamics 365連接器目前處於有限可用性，並受限於多項限制，詳細說明請見說明檔案。

## 透過API呼叫匯入資料

Campaign Standard API可讓您執行更新資料庫的作業，例如設定檔或服務的建立、更新或刪除。

如需如何使用API的詳細資訊，請參閱專用 [檔案](../../api/using/get-started-apis.md)。

>[!CAUTION]
>
>在透過API呼叫執行設定檔大量建立或更新之前，請檢查與您的授權合約相應的比例限制。 有關詳細資訊，請參見[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
