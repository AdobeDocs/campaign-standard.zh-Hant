---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard 的隱私權管理
description: 深入瞭解 Adobe Campaign Standard 的隱私權管理功能。
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: a9afa91302684ddd37a94a9999d90bf8c8e7abee
workflow-type: tm+mt
source-wordcount: '964'
ht-degree: 90%

---


# 隱私權管理 {#privacy-management}

Adobe Campaign提供一套工具，可協助您遵守[隱私權規定](#privacy-management-regulations)（包括GDPR、CCPA、PDPA、LGPD）。

以下是Adobe Campaign為確保GDPR和其他隱私權法規的準備而提供的五大功能：

![](assets/privacy-gdpr-use-cases.png)

* **存取權**

* **刪除權**

如需詳細資訊，請參閱[存取權與被遺忘權](#right-access-forgotten)。

* **同意管理**

* **資料保留**

* **權限管理**

有關詳細資訊，請參閱[同意、保留和角色](#consent-retention-roles)。

<!--This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

It also contains information on important features to manage Privacy ([consent, data retention and user roles](#consent-retention-roles)), as well as best practices to help you with your Privacy compliance when using Adobe Campaign.-->

## 隱私權管理規定{#privacy-management-regulations}

Adobe Campaign 的功能可協助您遵循下列法規：

* **GDPR**（[一般資料保護規範](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)）是歐盟 (EU) 的隱私權法律，其可為歐盟國家協調資料保護要求並以現代化方式規範資料保護要求。請遵循下列連結，以尋找有關GDPR的一般資訊：

   * https://www.adobe.com/privacy/general-data-protection-regulation.html
   * https://www.adobe.com/marketing-cloud/campaign/general-data-protection-regulation.html

* **CCPA**（[加州消費者隱私保護法](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)）為加州居民提供新的個資權利，並對在加州經營業務的特定實體賦予資料保護責任。
* **PDPA**（[個人資料保護法案](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)）是新的隱私權法令，該法協調泰國的資料保護要求並以現代化方式加以規範。
* **LGPD** ([Lei Geral de Proteção de Dados](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) 將於 2021 年初生效，所有於巴西收集或處理個人資料的公司皆適用。

所有這些規定皆適用於持有上述地區或國家（歐盟、加州、泰國、巴西）資料主體資料的 Adobe Campaign客 戶。

>[!NOTE]
>
>如需關於個人資料及管理資料之不同實體（資料控制方、資料處理方和資料主體）的詳細資訊，請參閱[個人資料和人員](../../start/using/privacy.md#personal-data)。

## 存取權限與被遺忘的權利 {#right-access-forgotten}

為協助您加速隱私權準備，Adobe Campaign 可讓您處理&#x200B;**存取**&#x200B;和&#x200B;**刪除**&#x200B;要求。

* **存取權限**&#x200B;是指資料主體有權從資料控制方取得關於其個人資料是否正在處理、處理地點及基於何種目的的確認。資料控制方應免費提供電子格式的個人資料副本。

* 「**被遺忘的權利**」（刪除要求）也稱為「資料抹除」，其可賦予「資料主體」權利，讓資料庫控制方得以清除其個人資料、停止進一步散發資料，並可能讓第三方停止處理資料。

如要瞭解如何建立&#x200B;**存取**&#x200B;及&#x200B;**刪除**&#x200B;要求，以及 Adobe Campaign 如何處理這些要求，請參閱[實作步驟](../../start/using/privacy-requests.md#about-privacy-requests)。

[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=zh-Hant#privacy)也提供關於 Campaign Standard 隱私權管理的教學課程。

>[!NOTE]
>
>如需關於個人資料及管理資料之不同實體（資料控制方、資料處理方和資料主體）的詳細資訊，請參閱[個人資料和人員](../../start/using/privacy.md#personal-data)。

## 同意、保留和角色 {#consent-retention-roles}

除了最新的&#x200B;**存取權限**&#x200B;及&#x200B;**被遺忘的權利**&#x200B;以外，Adobe Campaign 還提供其他對隱私權至關重要的功能：

* [同意管理](#consent-management)：偏好設定管理的訂閱功能
* [資料保留](#data-retention)：所有標準記錄表上的資料保留期間，可以使用工作流程設定其他保留期間
* [權限管理](#rights-management)：由具名權限管理的資料存取

### 同意管理 {#consent-management}

同意表示資料主體同意處理與資料主體相關的個人資料。資料控制方應負責取得該項處理的任何必要同意。雖然 Adobe Campaign 可能會提供一些功能，以協助與服務相關的客戶管理同意，但 Adobe 不負責同意。客戶應與自己的法律部門合作，以決定自己的流程和實務，以取得任何必要的同意。

Adobe Campaign 自始至終都採用有助於管理同意部分的功能。透過訂閱管理程式，客戶可以追蹤哪些收件者已選擇訂閱類型，無論是電子報、每日或每週促銷或任何其他類型的行銷方案。

![](assets/privacy-consent-management.png)

如需「同意」管理的詳細資訊，請參閱[關於訂閱](../../audiences/using/about-subscriptions.md)及[開始使用登陸頁面](../../channels/using/getting-started-with-landing-pages.md)。

除了 Adobe Campaign 提供的同意管理工具以外，您還可以追蹤消費者是否選擇退出個人資訊銷售。請參閱[本節](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)。

### 資料保留 {#data-retention}

關於保留，Campaign 中的內建記錄表有預先設定的保留期間，通常將其資料儲存時間限制在六個月或更短時間。

以下是內建表格的預設保留值。請注意，保留設定是由 Adobe 技術管理員在實施期間所設定，每個實作的值可能會因客戶需求而有所不同。

* **整合追蹤**：6 個月
* **傳送記錄**：6 個月
* **追蹤記錄**：6 個月
* **事件**：1 個月
* **事件處理統計資料**：6 個月
* **封存事件**：6 個月
* **臨時實體**：7 天
* **忽略的管線事件**：1 個月
* **傳送警報**：1 個月
* **匯出稽核**：6 個月

與刪除類似，使用標準工作流程功能，即可設定任何自訂表格的保留期間。

請洽詢 Adobe 顧問或技術管理員，以進一步瞭解保留，或是您是否需要為自訂表格設定保留。

### 權限管理 {#rights-management}

Adobe Campaign 可讓您透過不同的預先建立或自訂角色，管理指派給各種 Campaign 運算子的權限。

其中一項好處是，這可讓您管理公司內可存取不同類型資料的人員。例如，您可能有不同的行銷人員涵蓋不同的地域，而每個行銷人員只能存取其地域的資料。

同樣地，此功能也可讓您為每個使用者設定不同的功能，例如限制哪些人可以傳送傳遞，或是在與隱私權管理更相關的領域，限制哪些人員可以修改或匯出資料。

![](assets/privacy-user-management.png)

如需存取管理、的詳細資訊，請參閱[本節](../../administration/using/about-access-management.md)。