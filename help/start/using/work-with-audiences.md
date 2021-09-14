---
title: 自訂清單
description: 「了解如何自訂顯示以及在Adobe Campaign Standard中的清單畫面上操作：排序、篩選、刪除或複製元素。 列出螢幕，顯示一或多個指定資源的元素。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 11%

---


# 使用設定檔與閱聽眾

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
<td>擴充資料庫</td>
<td>組織您的對象</td>
<td>隱私權管理</td>
</tr>
</table>

## 客戶設定檔 {#customer-profiles}

<img width="60px" alt="條件" src="assets/icon_profile.svg"/>

Adobe Campaign設定檔代表儲存在資料庫中的所有連絡人。 每個設定檔都對應至資料庫中的一個項目，該項目包含要定位、限定和個別追蹤該設定檔的必要資訊。 這表示設定檔可以是：客戶、潛在客戶、訂閱電子報的個人、收件者、使用者或任何其他面額（視組織而定）。

**顯示全文**

* [關於設定檔](../../audiences/using/about-profiles.md)
* [存取組織中的作用中設定檔數目](../../audiences/using/active-profiles.md)

## 擴充資料庫 {#populating-database}

<img width="60px" alt="條件" src="assets/icon_populate.svg"/>

Campaign Standard提供數種工具，可協助您擴充行銷資料庫。 本節詳細說明您可用來將資料插入Campaign的不同方法，以及專用檔案的參考。

### 透過工作流程匯入資料 {#importing-data-through-workflows}

工作流程可讓您透過[**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md)活動來收集資料，並將其匯入Campaign資料庫。 透過工作流程匯入資料時的一般資訊和最佳實務會顯示在[此區段](../../automating/using/about-data-import-and-export.md)中。

此外，您也可以設定範本以匯入資料。 如果您需要定期匯入具有相同結構的檔案，最好使用匯入範本。 您可以設定兩種類型的範本：

* **工作流程範本**:這些是預先設定的工作流程，您可以根據需求設定一次，並在每次要匯入資料和更新資料庫時重複使用。[本區段](../../automating/using/creating-import-workflow-templates.md)中會詳細說明匯入資料的工作流程範本範例。

* **匯入資料範本**:與工作流模板一樣，這些模板是基於工作流的模板，設定為上載檔案以更新資料庫。設定後，使用者可透過&#x200B;**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;功能表下的簡化檢視加以使用。 有關匯入資料範本的詳細資訊，請參閱[專用檔案](../../automating/using/importing-data-with-import-templates.md)。

### 從登錄頁面收集資料 {#collecting-data-from-landing-pages}

登錄頁面是網頁表單，可用來收集資料，以及建立或更新資料庫中的現有資訊。 原則如下：

* 新增輸入欄位以收集資料（名字、姓氏、電子郵件等），以建立並設計您的登錄頁面。
* 將每個輸入欄位與資料庫中的對應欄位對應。
* 讓登錄頁面可透過網站或透過訊息的直接連結線上取得。

如需登錄頁面的詳細資訊，請參閱[專用檔案](../../channels/using/getting-started-with-landing-pages.md)。

**顯示全文**

* xx
* xx

### 從Microsoft Dynamics 365同步配置檔案

Campaign Standard與Microsoft Dynamics 365的整合可讓您將聯絡資料從Microsoft Dynamics 365傳遞至Campaign資料庫。
然後，這些聯絡人會顯示在「設定檔」清單中，並可定位在行銷活動中。 如需此整合的詳細資訊，請參閱[專用檔案](../../integrating/using/d365-acs-get-started.md)。

>[!NOTE]
>
>請注意，Campaign Standard- Microsoft Dynamics 365連接器目前處於有限可用性，且受到幾項限制，詳細說明於本檔案中。

**顯示全文**

* xx
* xx

### 透過API呼叫匯入資料

Campaign StandardAPI可讓您執行更新資料庫的操作，例如設定檔或服務的建立、更新或刪除。 如需如何使用API的詳細資訊，請參閱[專用檔案](../../api/using/get-started-apis.md)。

>[!CAUTION]
>
>在透過API呼叫執行設定檔大量建立或更新之前，請檢查與您的授權合約相對應的比例限制。 如需詳細資訊，請參閱[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。

**顯示全文**

* xx
* xx

## 組織您的對象 {#organizing-audiences}

<img width="60px" alt="條件" src="assets/icon_audience.svg"/>

為了讓您傳遞相關且有效的訊息，並有效地與客戶互動，Adobe Campaign整合了進階分析和鎖定功能。

有了工作流程和查詢編輯器，您可以根據您對不同行銷活動的資訊、活動、語言、偏好設定或行銷記錄，建立將會被您不同行銷活動鎖定的對象。 例如，這可讓您篩選訂閱的設定檔，或根據不限數量的條件建立目標對象。

**顯示全文**

* [關於對象](../../audiences/using/about-audiences.md)
* [建立對象](../../audiences/using/creating-audiences.md)

## 隱私權管理 {#privacy-management}

<img width="60px" alt="條件" src="assets/icon_privacy.svg"/>

GDPR 是歐盟 (EU) 最新制定的一項隱私法規，用於協調和順應時代更新資料保護需求。GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）之外，我們還以資料處理者的角色，利用此機會加入其他功能，以協助您做好準備，以便擔任資料控管者，處理特定GDPR請求。

請參閱本[指南](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=zh-Hant)以進一步了解Adobe Campaign為協助您遵循GDPR而提供的工具和功能。

**顯示全文**

* xx
* xx