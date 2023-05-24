---
title: 自訂清單
description: 「瞭解如何自定義顯示和在Adobe Campaign Standard的清單螢幕上操作：排序、過濾、刪除或複製元素。 列出螢幕顯示一個或多個給定資源的元素。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 10%

---


# 使用個人資料和受眾

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
<td>客戶配置檔案</td>
<td>豐富資料庫</td>
<td>組織您的觀眾</td>
<td>隱私權管理</td>
</tr>
</table>

## 客戶配置檔案 {#customer-profiles}

<img width="60px" alt="條件" src="assets/icon_profile.svg"/>

Adobe Campaign配置檔案表示資料庫中儲存的所有聯繫人。 每個配置檔案對應於資料庫中的一個條目，該條目包含要針對、限定和單獨跟蹤該配置檔案的必要資訊。 這意味著配置檔案可以是：客戶、潛在客戶、訂閱新聞簡報的個人、收件人、用戶或任何其他面額，具體取決於組織。

**深入了解**

* [關於設定檔](../../audiences/using/about-profiles.md)
* [訪問組織中的活動配置檔案數](../../audiences/using/active-profiles.md)

## 豐富資料庫 {#populating-database}

<img width="60px" alt="條件" src="assets/icon_populate.svg"/>

Campaign Standard提供了多種工具來幫助您擴展營銷資料庫。 本部分詳細說明了可用於向市場活動中注入資料的不同方法，其中引用了專用文檔。

### 通過工作流導入資料 {#importing-data-through-workflows}

工作流允許您通過使用 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) 活動。 通過工作流導入資料時的一般資訊和最佳做法在中介紹 [此部分](../../automating/using/about-data-import-and-export.md)。

此外，還可以設定模板以導入資料。 使用導入模板是定期導入具有相同結構的檔案的最佳方法。 可以設定兩種類型的模板：

* **工作流模板**:這些是預配置的工作流，您可以根據需要設定一次，並在每次要導入資料和更新資料庫時重複使用。 有關導入資料的工作流模板示例的詳細資訊，請參見 [此部分](../../automating/using/creating-import-workflow-templates.md)。

* **導入資料模板**:與工作流模板一樣，這些模板是基於工作流的模板，設定為上載檔案以更新資料庫。 配置後，用戶可以在 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** 的子菜單。 有關導入資料模板的詳細資訊，請參閱 [專用文檔](../../automating/using/importing-data-with-import-templates.md)。

### 從登錄頁收集資料 {#collecting-data-from-landing-pages}

登錄頁是Web表單，可用於收集資料並建立或更新資料庫中的現有資訊。 其原理是：

* 通過添加輸入欄位來收集資料（名字、姓氏、電子郵件等）來建立和設計登錄頁。
* 將每個輸入欄位與資料庫中的相應欄位映射。
* 通過網站或消息的直接連結使登錄頁線上可用。

有關登錄頁的詳細資訊，請參閱 [專用文檔](../../channels/using/getting-started-with-landing-pages.md)。

**深入了解**

* xxx
* xxx

### 正在同步MicrosoftDynamics 365中的配置檔案

Campaign Standard與MicrosoftDynamics 365的整合允許您將聯繫資料從MicrosoftDynamics 365傳遞到市場活動資料庫。
然後，這些聯繫人可在「配置檔案」清單中看到，並可以在市場營銷市場活動中定位。 有關此整合的詳細資訊，請參閱 [專用文檔](../../integrating/using/d365-acs-get-started.md)。

>[!NOTE]
>
>請注意，Campaign Standard-Microsoft Dynamics 365連接器當前處於有限可用性中，並且受到多個限制，詳見文檔。

**深入了解**

* xxx
* xxx

### 通過API調用導入資料

Campaign StandardAPI允許您執行更新資料庫的操作，如配置檔案或服務的建立、更新或刪除。 有關如何使用API的詳細資訊，請參閱 [專用文檔](../../api/using/get-started-apis.md)。

>[!CAUTION]
>
>在通過API調用執行配置式成批建立或更新之前，請檢查與許可協定對應的比例限制。 如需詳細資訊，請參閱[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。

**深入了解**

* xxx
* xxx

## 組織您的觀眾 {#organizing-audiences}

<img width="60px" alt="條件" src="assets/icon_audience.svg"/>

為了讓您能夠傳遞相關和有效的資訊，並有效地吸引您的客戶，Adobe Campaign整合了高級分析和目標功能。

借助工作流和查詢編輯器，您可以構建受不同市場活動影響的受眾，具體取決於您在這些市場活動上的資訊、活動、語言、偏好或市場營銷歷史。 這樣，您就可以篩選訂閱的配置檔案，或根據無限數量的條件建立目標受眾。

**深入了解**

* [關於對象](../../audiences/using/about-audiences.md)
* [建立對象](../../audiences/using/creating-audiences.md)

## 隱私權管理 {#privacy-management}

<img width="60px" alt="條件" src="assets/icon_privacy.svg"/>

GDPR 是歐盟 (EU) 最新制定的一項隱私法規，用於協調和順應時代更新資料保護需求。GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。除了Adobe Campaign已經提供的隱私權（包括同意管理、資料保留設定和用戶角色）外，我們還將利用此機會作為資料處理器角色加入其他權能，以幫助您作為資料控制器為某些GDPR請求做好準備。

請參閱 [此部分](../../start/using/privacy.md) 瞭解Adobe Campaign為幫助您符合GDPR而提供的工具和功能的更多資訊。

**深入了解**

* xxx
* xxx