---
title: 最佳化訊息傳送
seo-title: 最佳化訊息傳送
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d5d9d50474142306457a8c76a24388c3c574791d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 最佳化傳送 {#optimize-delivery}

在開始建立傳送之前，您可以採取數個動作來保護並最佳化上游傳送程式。

以下章節概述最佳化Adobe Campaign設定的最佳實務和建議程式。 遵循這些實務可將下游可能遇到的問題降到最低。

## 平台效能

數個因素會直接影響伺服器效能並減緩平台速度：

* 個人化元素的數量和類型：電子郵件中的個人化會從資料庫中提取每個收件者的資料。 如果有許多個人化元素，會增加準備傳送所需的資料量。  在本節中進一步瞭解電子郵件個 [人化](../../designing/using/personalization.md)

* 伺服器載入：當促銷活動同時處理許多不同的工作時，可能會降低效能。 伺服器需要協調所有傳送的所有傳入和傳出資料，以確保資料正確且準時。

   **TIP** —— 為避免此問題，請與團隊中的其他成員協調交貨的排程，以確保最佳效能。

* 工作流 [執行](../../automating/using/about-workflow-execution.md):監控工作流程是避免平台效能問題的關鍵。 依照本頁所列 [的准則](../../automating/using/monitoring-workflow-execution.md)。 進一步瞭解工作 [流程最佳實務](../../automating/using/best-practices-workflows.md) 。

* 您可運用「促銷 [活動控制面板」功能](https://docs.adobe.com/content/help/en/control-panel/using/discover-control-panel/key-features.html) ，使用效能監控功 [能來監控平台](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/about-performance-monitoring.html) 。

## 檢查網路配置 {#network-config}

若要在處理大量電子郵件時最佳化傳送，並避免被誤認為是垃圾郵件發送者，請確定您有合法的網路組態，不會嘗試隱藏伺服器的身分。

**提示**: 使用與您品牌網站對應的透明寄件者位址。 例如，這家旅行社管理著華倫天奴連鎖酒店。 它擁有其網站的valentino.com網域。 為推廣巴黎的華倫天奴酒店，它使用paris.valentino.com子網域。 因此，相關的發件人地址可以是hotel@paris.valentino.com。

## 傳遞能力管理{#deliverability-management}

若要在不反彈或標示為垃圾訊息的情況下進入收件者的收件匣，您必須改善訊息的傳遞率。

* 什麼是傳遞能力？

   * 它是指決定電子郵件是否能被收件者伺服器接受的因素。 ISP（網際網路服務供應商）會過濾掉其識別為垃圾訊息的電子郵件，或封鎖影像下載。 如果他們判斷某個網域傳送的電子郵件過多，他們會設定接受該寄件者寄送之電子郵件的數量限制。

   * 在檢查您的電子郵件是否具有傳遞能力時，您希望將重點放在四個主要類別：資料品質、訊息和內容、傳送基礎架構和聲譽。 有關本主題的深入探討，請參 [閱本節](../../sending/using/about-deliverability.md)。

* 啟動新平台時，請套用本頁中詳 [細的建議](../../sending/using/starting-new-platform.md)。

* 請連絡您的Adobe代表以取得協助。

## 隔離管理 {#quarantine-management}

維護良好的隔離管理流程符合您的最大利益。

當您開始在新平台上傳送電子郵件時，可能會使用未完全限定的位址清單。 如果您發送到無效地址或蜜罐地址（郵箱僅用於誘騙垃圾郵件發送者），這將開始削弱您平台的聲譽。 良好的隔離管理流程有助於：維持位址品質、避免網際網路存取供應商的拒絕清單，並降低錯誤率、加速傳送和總處理能力。

**提示**

* 在傳送分析期間，預設會排除隔離地址的收件者：它們不是目標。 這會加快傳送速度，因為錯誤率對傳送速度有顯著影響。例如，當收件箱已滿或地址不存在時，可以隔離電子郵件地址。 [進一步瞭解](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign會根據傳回的錯誤類型管理錯誤位址。 如需詳細資訊，請參閱[本章節](../../sending/using/understanding-quarantine-management.md)。

* 如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。因此，隔離可讓您避免被這些提供者添加到拒絕清單。

* 隔離管理也有助於降低SMS傳送成本，將錯誤的電話號碼排除在傳送途中。

## 雙重加入機制 {#double-opt-in}

為避免傳送訊息至無效位址、限制不當通訊並改善寄件者信譽，Adobe建議實作訂閱後確認的雙重選擇加入機制。 這有助於確保收件者有意訂閱。

本節將說明實作此機制的 [詳細資訊](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

進一步瞭解 [設定檔和受眾](../../audiences/using/get-started-profiles-and-audiences.md)。
