---
title: 自訂清單
description: 「瞭解如何在Adobe Campaign Standard中自訂顯示並在清單熒幕上操作：排序、篩選、刪除或複製元素。 列出畫面會顯示一或多個指定資源的元素。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 11%

---


# 使用設定檔和對象

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
<td>客戶設定檔</td>
<td>擴充您的資料庫</td>
<td>組織您的對象</td>
<td>隱私權管理</td>
</tr>
</table>

## 客戶設定檔 {#customer-profiles}

<img width="60px" alt="條件" src="assets/icon_profile.svg"/>

Adobe Campaign設定檔代表儲存在資料庫中的所有連絡人。 每個設定檔都對應資料庫中的一個專案，其中包含設定檔要定位、限定及個別追蹤的必要資訊。 這表示設定檔可以是：客戶、潛在客戶、訂閱電子報的個人、收件者、使用者或任何其他面額（視組織而定）。

**深入了解**

* [關於設定檔](../../audiences/using/about-profiles.md)
* [存取組織中的作用中設定檔數目](../../audiences/using/active-profiles.md)

## 擴充您的資料庫 {#populating-database}

<img width="60px" alt="條件" src="assets/icon_populate.svg"/>

Campaign Standard提供數種工具，可協助您擴充行銷資料庫。 本節詳細說明可用來將資料插入Campaign的不同方法，以及專用檔案的參考資料。

### 透過工作流程匯入資料 {#importing-data-through-workflows}

工作流程可讓您收集資料，並使用將其匯入Campaign資料庫。 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) 活動。 透過工作流程匯入資料時的一般資訊和最佳實務會顯示在 [本節](../../automating/using/about-data-import-and-export.md).

此外，您可以設定範本以匯入資料。 使用匯入範本是定期匯入具有相同結構的檔案的最佳做法。 您可以設定兩種範本：

* **工作流程範本**：這些是預先設定的工作流程，您可以視需要設定一次，並在每次想要匯入資料及更新資料庫時重複使用。 有關匯入資料的工作流程範本範例，請參閱 [本節](../../automating/using/creating-import-workflow-templates.md).

* **匯入資料範本**：與工作流程範本類似，這些範本是以工作流程為基礎，設定為上傳檔案以更新資料庫。 在設定之後，使用者可在下方以簡化的檢視加以使用 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** 功能表。 有關匯入資料範本的詳細資訊，請參閱 [專屬檔案](../../automating/using/importing-data-with-import-templates.md).

### 從登入頁面收集資料 {#collecting-data-from-landing-pages}

登入頁面是網路表單，可用來收集資料，以及在資料庫中建立或更新現有資訊。 原理如下：

* 新增輸入欄位以收集資料（名字、姓氏、電子郵件等），藉此建立及設計您的登入頁面。
* 將每個輸入欄位與資料庫中的對應欄位對應。
* 透過網站或直接連結至訊息，線上上提供登入頁面。

如需登入頁面的詳細資訊，請參閱 [專屬檔案](../../channels/using/getting-started-with-landing-pages.md).

**深入了解**

* xxxx
* xxxx

### 從Microsoft Dynamics 365同步設定檔

與Microsoft Dynamics 365整合的Campaign Standard可讓您將聯絡資料從Microsoft Dynamics 365傳遞至Campaign資料庫。
然後，這些聯絡人會顯示在設定檔清單中，並可在行銷活動中定位。 如需此整合的詳細資訊，請參閱 [專屬檔案](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>請注意，Campaign Standard-Microsoft Dynamics 365聯結器目前為「有限可用性」，且有幾項限制，詳情請參閱本檔案。

**深入了解**

* xxxx
* xxxx

### 透過API呼叫匯入資料

Campaign StandardAPI可讓您執行更新資料庫的操作，例如建立、更新或刪除設定檔或服務。 如需如何使用API的詳細資訊，請參閱 [專屬檔案](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>在透過API呼叫執行設定檔大量建立或更新之前，請檢查與您的授權合約相對應的比例限制。 如需詳細資訊，請參閱[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。

**深入了解**

* xxxx
* xxxx

## 組織您的對象 {#organizing-audiences}

<img width="60px" alt="條件" src="assets/icon_audience.svg"/>

為了讓您傳送相關且有效的訊息，並有效地與您的客戶互動，Adobe Campaign整合了進階分析和目標定位功能。

有了工作流程與查詢編輯器，您就可以根據您擁有的資訊、活動、語言、偏好設定或行銷記錄，建立不同行銷活動鎖定的對象。 舉例來說，這可讓您篩選已訂閱的設定檔，或根據不限數量的條件建立目標對象。

**深入了解**

* [關於對象](../../audiences/using/about-audiences.md)
* [建立對象](../../audiences/using/creating-audiences.md)

## 隱私權管理 {#privacy-management}

<img width="60px" alt="條件" src="assets/icon_privacy.svg"/>

GDPR 是歐盟 (EU) 最新制定的一項隱私法規，用於協調和順應時代更新資料保護需求。GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。除了Adobe Campaign所提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）之外，我們還將以資料處理者的角色利用此機會，加入其他功能，以協助您做好準備，以利您作為資料控制者，處理特定GDPR請求。

請參閱 [本節](../../start/using/privacy.md) 進一步瞭解Adobe Campaign所提供的工具和功能，協助您符合GDPR規定。

**深入了解**

* xxxx
* xxxx