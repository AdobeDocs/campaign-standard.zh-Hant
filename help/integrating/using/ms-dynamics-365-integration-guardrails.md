---
title: Microsoft Dynamics 365整合護欄
description: Microsoft Dynamics 365與Campaign Standard整合護欄
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 整合護欄和邊界

## 整合護欄

在計畫使用此整合時，應考慮以下護欄。 如果您認為超過這些防護欄，請洽詢您的Adobe技術代表。

* 您需要授權適當的Campaign套件，以支援整合產生的ACS引擎呼叫量。 超過授權的引擎呼叫量可能會導致促銷活動效能降低。

   使用下列功能，協助估計整合的引擎呼叫量：

   * 記錄插入（即新記錄）:1個引擎呼叫
   * 記錄刪除：1個引擎呼叫
   * 記錄更新：2個引擎呼叫（如果目標籤錄與源記錄相同，即，如果ACS記錄沒有更改，則只有1個呼叫）

   在估計整體ACS引擎呼叫量時，請務必考慮其他引擎呼叫來源，包括登陸頁面、WebApps、JSSP、API、行動應用程式註冊等。

   在這裡檢視促銷活動套件資訊：https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* 整合支援最多3000萬個連絡人。

* 標準整合方案包括支援最多5個自訂實體

* 超過500k記錄的自訂實體需要額外諮詢時間，才能透過促銷活動工作流程執行一次（每個自訂實體）初始檔案匯入（這會產生額外成本）

* 標準整合方案包括支援最多50欄的自訂實體。

* 在實作整合之前，您需要建立並發佈自訂資源。

* 連結表時的表深度上限為2（即表1->表2->表3）

* 對Dynamic 365資料類型的支援有限。 如果您的資料模型包含簡單資料類型以外的資料類型（例如字串、整數、小數等），您可能需要在使用整合之前更新資料模型。

* 保留Campaign中現有資料的自訂實體可能會產生額外的諮詢成本，以準備整合資料。

* Adobe和客戶之間可能需要建立入門維護視窗，因為初始收錄可能會導致促銷活動速度變慢。

* 我們鼓勵您通知已知的例項，指出整合的使用量會大幅增加或「尖峰」（例如，新記錄或更新記錄會大幅增加），因為這可能會導致資料同步速度變慢。

* 在整合中，您需要完成Microsoft Azure和Dynamics 365中的預先整合設定步驟。 請參閱本頁的 [設定步驟](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* 預期您會將Dynamics 365和Campaign資料模型帶入整合，並加以維護。

## 整合邊界

此整合旨在解決Dynamics 365和Campaign之間常見資料移動的一般使用案例，但並非針對每個客戶的特定使用案例：

* 整合不會發佈任何隱私權（例如GDPR）刪除。 滿足最終用戶隱私要求的責任由客戶負責；此類要求應分別在Campaign（透過Adobe Experience Platform Privacy Service）和Dynamics 365中提出。 如有需要，整合會定期執行刪除，以協助進行資料同步。

* 促銷活動與Dynamics 365之間不會同步任何描述檔或自訂實體資料，但退出資訊除外（如果客戶已設定）。

* 促銷活動訂閱管理（即訂閱／取消訂閱）本身不受支援。

* 不支援從Dynamics 365內撰寫和觸發促銷活動電子郵件促銷活動。

* 此整合將不支援在Dynamics 365和Campaign資料模型之間重新建立資料。 預計整合將會將一個Dynamics 365表格同步至一個Campaign表格。

* 目前的整合版本沒有自助服務UI。
