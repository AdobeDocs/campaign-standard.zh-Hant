---
title: Adobe Campaign Standard 的隱私權與同意
description: 本節概述 Adobe Campaign Standard 的隱私權、個人資料和同意管理，以及可處理這些項目的工具。
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 2879066634a8a123ef5d07d46aa96479f156a923
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 94%

---


# 隱私權與同意{#privacy-and-consent}

## 一般性建議 {#general-recommendations}

Adobe Campaign 是一款強大的工具，用於收集和處理包括個人資訊及敏感資料在內的超大資料。這就是需要謹慎管理隱私權的原因。

* 一律以負責任且符合道德的方式使用個人資訊。

* 避免傳送未經請求的電子郵件、推播通知和 SMS 訊息（「垃圾訊息」）。在打造顧客終生價值及忠誠度的過程中，Adobe 篤信許可式行銷原則，因此我們嚴格禁止使用 Adobe Campaign 傳送未經請求的訊息。

### 隱私權法規 {#privacy-regulations}

為正確處理隱私權並管理個人資料，工作時請遵循您營運業務所在地區的適用法規。這些法規包含：
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)（歐洲一般資料保護規範）
* [DPA](https://www.gov.uk/data-protection)（英國實施 GDPR 之規範）
* [歐洲隱私權與電子通訊指令](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM 法案](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)（美國法律規定商業電子郵件的規則與要求）
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)（加州消費者隱私權法案）
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)（泰國個人資料保護法案）

>[!NOTE]
>
>如需有關GDPR、CCPA和PDPA如何套用至Adobe Campaign的詳細資訊，請參閱[本頁](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy-overview.html#whatisgdpr)。

### Adobe Experience Cloud 隱私權 {#experience-cloud-privacy}

Adobe Campaign 是 Adobe Experience Cloud 解決方案的一部分。在 Campaign 中處理隱私權的方式會依循 Adobe Experience Cloud 的一般原則，例如：

* **使用 Adobe Experience Cloud 時會收集哪些資訊**

   身為使用 Adobe Experience Cloud 解決方案的公司，您可以選擇要收集哪些資訊並傳送至您的 Adobe Experience Cloud 帳戶。可收集的資訊類型範例包含網頁瀏覽活動、IP 位址、行動裝置的位置資訊、促銷活動成功率、購買或放入購物車的項目等。

   >[!NOTE]
   >
   >而對於所有 Adobe 產品，Campaign 會收集應用程式和網站使用者的相關資訊。如需此項目的詳細資訊，請參閱 [Adobe 隱私權政策](https://www.adobe.com/privacy/policy.html)。

* **如何使用 Adobe Experience Cloud 收集資訊**

   * Adobe Experience Cloud 解決方案會使用 Cookie 和類似技術（例如網站信標，又稱為標籤或像素），讓您收集資訊。如需 Adobe Campaign Cookie 和追蹤功能的詳細資訊，請參閱[本節](#tracking-capabilities)。
   * 您也可以在行動應用程式中使用 Adobe Experience Cloud 技術。如需使用 Campaign 傳送行動傳遞的詳細資訊，請參閱[本頁](https://helpx.adobe.com/tw/campaign/kb/acs-mobile.html)。

* **使用者對於您使用 Adobe Experience Cloud 的隱私權選擇**

   Adobe 要求您提供客戶的隱私權政策，以說明：

   * 您與 Adobe Experience Cloud 相關聯的隱私權實務
   * 使用者如何針對 Adobe Experience Cloud 收集或使用其資訊進行偏好設定

   >[!NOTE]
   >
   >而對於所有 Adobe 產品，Campaign 使用者可以透過應用程式和網站，選擇退出分享收集關於他們的資訊。如需此項目的詳細資訊，請參閱 [Adobe Experience Cloud 使用資訊常見問答](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html)。

如需 Adobe Experience Cloud 隱私權的後續詳細資料，請參閱[本頁](https://www.adobe.com/privacy/marketing-cloud.html)。

## 個人資料與角色 {#personal-data}

在管理隱私權時，請務必定義哪些資料應謹慎處理，以及由哪些人員處理。
* **個人資料**&#x200B;是指可直接或間接識別在世個人的資訊。
* **敏感個人資料**&#x200B;是指與個人的種族、政治觀點、宗教信仰、犯罪背景、遺傳資訊、健康資料、性傾向、生物識別資訊，以及工會會員會籍相關的資訊。

[主要法規](#privacy-regulations)是指管理資料的不同實體，如下所示：
* **資料控制方**&#x200B;是決定收集、使用及分享個人資料之方式與目的的當局機關。
* **資料處理方**&#x200B;是指依據資料控制方的指示收集、使用或分享個人資料的任何個人或一方。
* **資料主體**&#x200B;是指正在收集、使用或分享個人資料的任何在世個人，以及可參照該個人資料直接或間接識別的在世個人。

因此，身為收集和分享個人資料的公司，您是資料控制方、客戶是資料主體，而 Adobe Campaign 在依您的指示處理個人資料時，會作為資料處理方。請注意，身為資料控制方，您有責任處理與資料主體的關係，例如管理[隱私權要求](#privacy-requests)。

將 Campaign 與其他 Experience Cloud 解決方案整合時，如果閱聽眾可以從一個系統傳輸到另一個系統（例如 [Audience Destinations 服務](../../audiences/using/aep-about-audience-destinations-service.md)、[Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md)、[Audience Manager 或 People 核心服務](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)，或是其他解決方案，如 [Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)），您需要支付額外的個人護理費用來保護資料。

## 資料擷取 {#data-acquisition}

Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

* 讓收件者一律同意接收通訊。為此，請盡快接受選擇退出要求，並透過雙重選擇加入程式以確認同意。如需此項目的詳細資訊，請參閱[在 Campaign 中管理選擇加入和選擇退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)及[設定雙重選擇加入程序](../../channels/using/setting-up-a-double-opt-in-process.md)。
* 請勿匯入詐騙清單，並使用陷阱來檢查您的用戶端檔案是否未遭到詐騙使用。如需此項目的詳細資訊，請參閱[使用陷阱](../../sending/using/using-traps.md)。
* 透過同意與權限管理，您可以追蹤收件者的偏好設定，並管理組織內哪些人員可以存取哪些資料。如需詳細資訊，請參閱[本節](#consent)。
* 加速和管理收件者的隱私權要求。如需詳細資訊，請參閱[本節](#privacy-requests)。

## 隱私權管理 {#privacy-management}

隱私權管理是指可協助您遵守隱私權法規（GDPR、CCPA等）的所有程序及工具。概述[本頁](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy-overview.html)的隱私權管理。

Adobe Campaign 提供專屬於隱私權管理的各種功能：
* 同意管理、資料保留和使用者角色。請參閱[本節](#consent)。
* 隱私權要求（存取權限與被遺忘的權利）。請參閱[本節](#privacy-requests)。
* 選擇退出個人資訊銷售（專屬於 CCPA）。請參閱[本節](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ccpa)。

[本節](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-faq.html?lang=zh-Hant#getting-started)將提供 Campaign 中主要隱私權功能及相關角色的範例。


### 同意、保留和角色 {#consent}

一開始，Adobe Campaign 會提供對隱私權至關重要的功能：

* **同意管理**：透過訂閱管理程序，您可以管理收件者的偏好設定，並追蹤哪些收件者已選擇加入何種訂閱類型。如需此項目的詳細資訊，請參閱[訂閱](../../audiences/using/about-subscriptions.md)及[登陸頁面](../../channels/using/getting-started-with-landing-pages.md)。
* **資料保留**：所有內建標準記錄表都具有預設的保留期間，通常會將其資料儲存限制在 6 個月或更短時間。您可以使用工作流程設定其他的保留期間。如需此項目的詳細資訊，請洽詢 Adobe 顧問或技術管理員。
* **權限管理**：Adobe Campaign 可讓您透過不同的預先建立或自訂角色，管理指派給各種 Campaign 運算子的權限。這可讓您管理公司內可存取、修改或匯出不同類型資料的人員。有關此項目的詳細資訊，請參閱[關於存取管理](../../administration/using/about-access-management.md)。

如需這些功能以及如何在Adobe Campaign中管理這些功能的詳細資訊，請參閱[本頁](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent)。

### 隱私權要求 {#privacy-requests}

Adobe Campaign 提供其他功能，協助您作為資料控制方，針對特定隱私權要求預作準備：

* **存取權限**&#x200B;是指資料主體有權從資料控制方取得關於其個人資料是否正在處理、處理地點及處理原因的確認。

* **被遺忘的權利**（刪除要求）為資料主體賦予權利，讓資料控制方得以清除其個人資料。

>[!NOTE]
>
>本套工具可協助您遵循 GDPR、CCPA 及 PDPA 的隱私權規範。有關這些不同規定的詳細資訊，請參見[本頁](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr)。

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

[本頁](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=zh-Hant#getting-started)會顯示&#x200B;**存取**&#x200B;及&#x200B;**刪除**&#x200B;要求。建立這些要求的實作步驟將於本頁[詳細說明](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。此外，您也可以在[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=zh-Hant#privacy)取得教學課程。

## 追蹤功能 {#tracking-capabilities}

藉由 Adobe Campaign 的追蹤功能，您可以使用工作階段 Cookie 及永久 Cookie 來追蹤傳送收件者的行為。如需追蹤的詳細資訊，請參閱[本頁](../../sending/using/tracking-messages.md)。

>[!NOTE]
>
>《一般資料保護規範》(GDPR) 等法規規定，公司必須先取得網站使用者的同意，才能安裝 Cookie。您必須透過授權要求，向使用者通知您的網站已配備 Web 追蹤工具。

您也可以在訊息中新增[追蹤的連結](../../designing/using/links.md#about-tracked-urls)，以便在[追蹤指標](../../reporting/using/tracking-indicators.md)內建報告中測量傳送和收件者行為的影響，或是建立您自己的[專用報表](../../reporting/using/about-dynamic-reports.md)。
