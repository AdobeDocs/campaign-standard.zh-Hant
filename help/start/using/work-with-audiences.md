---
title: 自訂清單
description: 「瞭解如何自訂Adobe Campaign Standard中的顯示畫面並對清單畫面採取行動：排序、篩選、刪除或複製元素。 清單畫面會顯示一或多個特定資源的元素。」
page-status-flag: never-activated
uuid: 3350583c-91ca-4ea5-ac14-6b6f11c4a64a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 4ba4f766-fdee-4ff0-8fe4-0612ed2b69a4
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用個人檔案與受眾

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="條件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="條件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="條件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="條件" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>客戶個人檔案</td>
<td>豐富您的資料庫</td>
<td>組織您的受眾</td>
<td>隱私權管理</td>
</tr>
</table>

## 客戶個人檔案 {#customer-profiles}

<img width="60px" alt="條件" src="assets/icon_profile.svg"/>

Adobe Campaign設定檔代表儲存在資料庫中的所有連絡人。 每個描述檔都對應至資料庫中的一個項目，其中包含要定位、限定及個別追蹤的該描述檔所需資訊。 這表示描述檔可以：客戶、潛在客戶、訂閱電子報的個人、收件者、使用者或任何其他面額（視組織而定）。

**顯示全文**

* [關於設定檔](../../audiences/using/about-profiles.md)
* [訪問組織中活動配置檔案的數量](../../audiences/using/active-profiles.md)

## 豐富您的資料庫 {#populating-database}

<img width="60px" alt="條件" src="assets/icon_populate.svg"/>

Campaign Standard提供數種工具來協助您擴充行銷資料庫。 本節詳細說明您可使用不同方法將資料插入Campaign，並參考專用檔案。

### 透過工作流程匯入資料 {#importing-data-through-workflows}

工作流程可讓您收集資料，並透過使用活動將其匯入Campaign資 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) 料庫。 本節將介紹在透過工作流程匯入資料時的一般資訊和最佳 [實務](../../automating/using/about-data-import-and-export.md)。

此外，您還可以設定範本以匯入資料。 如果您需要定期匯入具有相同結構的檔案，請使用匯入範本是最佳做法。 您可以設定兩種範本類型：

* **工作流程範本**:這些是預先設定的工作流程，您可視需要設定一次，而且每次您要匯入資料並更新資料庫時，都可重複使用。 本節將詳細介紹導入資料的工作流模 [板示例](../../automating/using/creating-import-workflow-templates.md)。

* **匯入資料範本**:像工作流程範本一樣，這些範本是以工作流程為基礎的範本，可設定為上傳檔案以更新資料庫。 在設定後，使用者可在 **[!UICONTROL Profile & audiences]** /功能表下以簡化檢視來使 **[!UICONTROL Imports]** 用它。 如需匯入資料範本的詳細資訊，請參閱專 [用檔案](../../automating/using/importing-data-with-import-templates.md)。

### 從著陸頁面收集資料 {#collecting-data-from-landing-pages}

登陸頁面是Web表單，可用來收集資料並建立或更新資料庫中的現有資訊。 其原則如下：

* 新增輸入欄位以收集資料（名字、姓氏、電子郵件等），以建立並設計您的登陸頁面。
* 將每個輸入欄位與資料庫中的相應欄位映射。
* 透過網站或訊息的直接連結，讓登陸頁面線上上提供。

For more on landing pages, refer to the [dedicated documentation](../../channels/using/getting-started-with-landing-pages.md).

**顯示全文**

* xxxx
* xxxx

### 從Microsoft Dynamics 365同步設定檔

Campaign Standard與Microsoft Dynamics 365的整合可讓您將Microsoft Dynamics 365的連絡人資料傳遞至Campaign資料庫。
然後，這些連絡人會顯示在「設定檔」清單中，並可定位在行銷促銷活動中。 For more on this integration, refer to the [dedicated documentation](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!NOTE]
>
>請注意，Campaign Standard-Microsoft Dynamics 365連接器目前處於有限可用性，並受限於多項限制，詳細說明請見說明檔案。

**顯示全文**

* xxxx
* xxxx

### 透過API呼叫匯入資料

Campaign Standard API可讓您執行更新資料庫的作業，例如設定檔或服務的建立、更新或刪除。 如需如何使用API的詳細資訊，請參閱專用 [檔案](../../api/using/get-started-apis.md)。

>[!CAUTION]
>
>在透過API呼叫執行設定檔大量建立或更新之前，請檢查與您的授權合約相應的比例限制。 有關詳細資訊，請參見[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。

**顯示全文**

* xxxx
* xxxx

## 組織您的受眾 {#organizing-audiences}

<img width="60px" alt="條件" src="assets/icon_audience.svg"/>

為了讓您傳遞相關且有效的訊息，並有效地吸引客戶，Adobe Campaign整合了進階分析和定位功能。

有了工作流程和查詢編輯器，您就可以建立受眾，這些受眾會根據不同促銷活動的資訊、活動、語言、偏好或行銷記錄來定位。 這可讓您例如篩選訂閱的描述檔，或根據不限數量的條件建立目標對象。

**顯示全文**

* [關於閱聽眾](../../audiences/using/about-audiences.md)
* [建立閱聽眾](../../audiences/using/creating-audiences.md)

## 隱私權管理 {#privacy-management}

<img width="60px" alt="條件" src="assets/icon_privacy.svg"/>

GDPR 是歐盟 (EU) 最新制定的一項隱私法規，用於協調和順應時代更新資料保護需求。GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）外，我們還將此機會作為資料處理者加入其他功能，以協助您做好準備，以做為特定GDPR要求的資料掌控者。

請參閱本指 [南](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy.html) ，進一步瞭解Adobe Campaign為協助您符合GDPR而提供的工具和功能。

**顯示全文**

* xxxx
* xxxx