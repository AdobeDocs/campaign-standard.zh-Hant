---
solution: Campaign Standard
product: campaign
title: 隱私權與同意
description: 瞭解Adobe Campaign Standard中的隱私權、個人資料和許可管理
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: c76f4b6e3bc0feb50e5776836552fdceaff61ea7
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 81%

---


# 隱私權與同意 {#privacy-and-consent}

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
>如需有關GDPR、CCPA、PDPA和LGPD如何套用至Adobe Campaign的詳細資訊，請參閱[本節](../../start/using/privacy-management.md#privacy-management-regulations)。

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

將 Campaign 與其他 Experience Cloud 解決方案整合時，如果閱聽眾可以從一個系統傳輸到另一個系統（例如 [Audience Destinations 服務](../../audiences/using/aep-about-audience-destinations-service.md)、[Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md)、[Audience Manager 或 People 核心服務](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)，或是其他解決方案，如 [Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)），您需要支付額外的個人護理費用來保護資料。

[主要法規](#privacy-regulations)是指管理資料之不同實體，如下所示：
* **資料控制方**&#x200B;是決定收集、使用及分享個人資料之方式與目的的當局機關。
* **資料處理方**&#x200B;是指依據資料控制方的指示收集、使用或分享個人資料的任何個人或一方。
* **資料主體**&#x200B;是指正在收集、使用或分享個人資料的任何在世個人，以及可參照該個人資料直接或間接識別的在世個人。

因此，身為收集和分享個人資料的公司，您是資料控制方、客戶是資料主體，而 Adobe Campaign 在依您的指示處理個人資料時，會作為資料處理方。請注意，身為資料控制方，您有責任處理與資料主體的關係，例如管理[隱私權要求](#privacy-requests)。

### 使用案例方案{#use-case-scenario}

為了說明不同角色如何互動，以下是GDPR客戶體驗的高階使用案例。

在此範例中，航空公司是Adobe Campaign客戶。 該公司是&#x200B;**資料控制器**，該航空公司的所有客戶是&#x200B;**資料主體**。 勞拉是航空公司的客戶。

以下是此範例中使用的不同角色：

* **資** 料主 **題勞拉**。她是收到航空公司留言的收件人。 勞拉可能是常客，但可能會在某個時刻決定，她不希望這家航空公司提供任何個人化廣告或營銷資訊。 她會要求航空公司（根據他們的流程）刪除她的常旅客號碼。

* **阿內** 斯是 **航** 空公司的資料掌控者。她會收到Laura的請求，擷取用來識別資料主體的有用ID，並在Adobe Campaign中提交請求。

* **Adobe** Campaign是資 **料處理者**。

![](assets/privacy-gdpr-flow.png)

以下是此使用案例的一般流程：

1. **資料主體**(Laura)透過電子郵件、客戶服務或入口網站，向&#x200B;**資料掌控者**&#x200B;傳送GDPR要求。

1. **資料控制器**(Anne)透過介面或使用API將GDPR要求推送至Campaign。

1. 當&#x200B;**資料處理者**(Adobe Campaign)收到資訊後，會對GDPR要求採取動作，並傳送回應或確認給&#x200B;**資料控制者**(Anne)。

1. 然後，**資料控制器**(Anne)審閱該資訊並將其發回到&#x200B;**資料主體**(Laura)。

## 資料擷取 {#data-acquisition}

Adobe Campaign 可讓您收集資料，包括個人和敏感資訊。因此，您必須接收並監控收件者的同意。

* 讓收件者一律同意接收通訊。為此，請盡快接受選擇退出要求，並透過雙重選擇加入程式以確認同意。如需此項目的詳細資訊，請參閱[在 Campaign 中管理選擇加入和選擇退出](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)及[設定雙重選擇加入程序](../../channels/using/setting-up-a-double-opt-in-process.md)。
* 請勿匯入詐騙清單，並使用陷阱來檢查您的用戶端檔案是否未遭到詐騙使用。如需此項目的詳細資訊，請參閱[使用陷阱](../../sending/using/using-traps.md)。
* 透過同意與權限管理，您可以追蹤收件者的偏好設定，並管理組織內哪些人員可以存取哪些資料。如需詳細資訊，請參閱[本節](#consent)。
* 加速和管理收件者的隱私權要求。如需詳細資訊，請參閱[本節](#privacy-requests)。

## 隱私權管理 {#privacy-management}

隱私權管理是指可協助您遵守隱私權法規（GDPR、CCPA等）的所有程序及工具。取得[本頁](../../start/using/privacy-management.md)隱私權管理內容的概觀。

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

如需這些功能及如何在 Adobe Campaign 中管理這些功能的詳細資訊，請參閱[本節](../../start/using/privacy-management.md#consent-retention-roles)。

### 隱私權要求 {#privacy-requests}

Adobe Campaign 提供其他功能，協助您作為資料控制方，針對特定隱私權要求預作準備：

* **存取權限**&#x200B;是指資料主體有權從資料控制方取得關於其個人資料是否正在處理、處理地點及處理原因的確認。

* **被遺忘的權利**（刪除要求）為資料主體賦予權利，讓資料控制方得以清除其個人資料。

**Access**&#x200B;和&#x200B;**Delete**&#x200B;請求在[本節](../../start/using/privacy-management.md#right-access-forgotten)中顯示。

建立這些請求的實施步驟詳見[本節](../../start/using/privacy-requests.md)。 此外，您也可以在[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=zh-Hant#privacy)取得教學課程。

## 追蹤功能 {#tracking-capabilities}

藉由 Adobe Campaign 的追蹤功能，您可以使用工作階段 Cookie 及永久 Cookie 來追蹤傳送收件者的行為。如需追蹤的詳細資訊，請參閱[本節](../../sending/using/tracking-messages.md)。

>[!NOTE]
>
>《一般資料保護規範》(GDPR) 等法規規定，公司必須先取得網站使用者的同意，才能安裝 Cookie。您必須透過授權要求，向使用者通知您的網站已配備 Web 追蹤工具。

您也可以在訊息中新增[追蹤的連結](../../designing/using/links.md#about-tracked-urls)，以便在[追蹤指標](../../reporting/using/tracking-indicators.md)內建報告中測量傳送和收件者行為的影響，或是建立您自己的[專用報表](../../reporting/using/about-dynamic-reports.md)。
