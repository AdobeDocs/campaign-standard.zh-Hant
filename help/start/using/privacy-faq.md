---
title: 隱私權常見問答集
description: 瞭解 Adobe Campaign Standard 中的隱私權、個人資料和同意管理
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
feature: Privacy
role: Business Practitioner
level: Intermediate
exl-id: 8f8ce032-5cff-44d3-9d3b-52511dbcaaab
translation-type: ht
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: ht
source-wordcount: '814'
ht-degree: 100%

---

# 隱私權常見問答集{#privacy-faq}

以下是使用 Adobe Campaign 時，有關隱私權與同意的常見問答集。

## 主要條款{#key-terms}

**隱私權的主要條款為何？**

以下所列出的項目會連結至 Adobe Campaign 中與隱私權和同意相關的主要條款與概念：

* [隱私權管理法規](../../start/using/privacy-management.md#privacy-management-regulations)
* [個人資料與角色](../../start/using/privacy.md#personal-data)
* [存取權限與被遺忘的權利](../../start/using/privacy-management.md#right-access-forgotten)
* [同意、保留和角色](../../start/using/privacy-management.md#consent-retention-roles)

## 隱私權法規準備{#privacy-regulations-readiness}

**Adobe Campaign 對遵守最新的隱私權法規有何建議？**

Adobe 不提供法律建議。您應該與自己的法律顧問合作，確保他們採取一切必要步驟，以便做好 GDPR、CCPA、PDPA、LGPD 或任何其他適用法規的準備。

**準備資料存取和刪除請求**

* 識別接收/回應資料主體請求的過程，包括指定隱私權聯絡點。

* 審查儲存在 Adobe Campaign 中的各種客戶資料，並確定唯一識別碼（可能不止一個）。

* 確定資料主體身份確認的驗證/驗證政策和過程。

* 請確定資料主體的回應易於理解。

**考慮同意**

* 視需要列出並更新 GDPR 資料擷取的所有接觸點（例如，考慮語言、同意機制和同意記錄檔）。

* 請確定所有行銷電子郵件都包含取消訂閱的連結。

* 評估電子郵件行銷的全球策略，以決定地理特定的實施。

**瞭解您的資料**

* 審查所有資料匯入並擷取資料流入 Adobe Campaign 的來源，以及記錄用於行銷工作的欄位。

* 從您的 Adobe Campaign 資料庫移除任何未使用的資料屬性。

* 使用 Adobe Campaign 中可用的資料來擷取資料，並為收件者提供更佳的個人化體驗。

* 審查和更新資料存取權限以協助確保 Adobe Campaign 的使用者僅能充分運用執行其促銷活動所需的資料，但不能存取其他資料。

* 確保 Adobe Campaign 的每位使用者都擁有執行其所需工作的適當存取權，但沒有執行其他工作的任何其他權利。

## 保留使用者參與{#preserve-user-engagement}

**資料控制方如何在對使用者參與影響最小的情況下獲得同意？**

在某些行銷活動需要同意的情況下，消費者同意需要有效（即沒有沉默作為同意或預先選取的核取方塊）、未捆綁銷售，並且可能不以提供服務為條件。

有時甚至需要重新整理某些同意，才能繼續使用後續的資料。

行銷人員不會將這些增強的同意要求視為對有價市場的風險，而是可以將它們視為品牌參與度和忠誠度以及客戶滿意度和信任的真正指標。

## 管理同意{#manage-consent}

**資料控制方如何在 Adobe Campaign 中管理同意？**

與大多數行銷人員透過自訂資料欄位或一個或多個服務善用的情況相比，Adobe Campaign 已經提供了在更高層級上管理同意的功能。

行銷人員應洽詢其法律顧問，以取得如何進行的指引，然後善用 Adobe Campaign 中內建的功能。

例如，將 Adobe Campaign 中的資料模型擴充為不僅在人們選擇加入時追蹤，還可追蹤選擇加入的時間標記，以及擷取精確同意範圍的某類指標。

## 資料刪除{#data-deletion}

**Adobe Campaign 中的資料控制方可以根據資料主體的客戶請求刪除哪些資料？**

所有與資料主體相關的資料都會被刪除，包括現成可用的表格和自訂表格。

技術上，所有連結至資料主體相關`integrity="own"`的資料都將被刪除。

作為資料控制方，您可以選擇透過更改資料架構中定義的連結的完整性來自訂此內容（例如，若您有商業理由不刪除某些資料）。

**刪除傳送和追蹤記錄時，報告會受到哪些影響？**

Adobe Campaign 中的報告是以根據來自傳送和追蹤記錄彙總資料計算的指標為基礎。因此，移除個別記錄檔時，不應該影響報告上顯示的度量。

## 重新匯入資料{#re-import-data}

**通常在 Adobe Campaign 中，記錄會從外部資料來源上傳。我是否需要留意稍後可能重新匯入資料？**

作為資料控制方，您需要確保在收到刪除請求時，從所有系統刪除資料主體的所有必要資料。

## 再次選擇加入{#opt-in-again}

**資料主體（其資料已從 Adobe Campaign 中清除）可以稍後再次選擇加入嗎？**

資料主體可能會再次選擇加入，或在其資料從 Adobe Campaign 中刪除後以新收件者身分新增。

您可以使用稽核軌跡，其詳細說明執行上次刪除的時間以及建立新收件者的時間。
