---
title: 疑難排解
description: 瞭解如何疑難排解共用資源時的問題。
page-status-flag: never-activated
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---


# 疑難排解{#troubleshooting}

使用與Audience Manager或People核心服務整合時可能會發生錯誤。

在此情況下，請確定下列元素已正確設定：

* **外部帳戶**

   在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**&#x200B;中，請確定下列外部S3帳戶已正確設定。 在設定期間應已配置上述S3伺服器。

   * **[!UICONTROL importSharedAudience]**:S3帳戶專用於匯入觀眾。
   * **[!UICONTROL exportSharedAudience]**:S3帳戶專用於匯出觀眾。

* **共用資料來源**

   在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，檢查共用資料來源是否已正確設定。

   **[!UICONTROL Priority]** 在定義多個資料來源時使用。 優先順序決定將使用哪個資料源與按定義順序接收的別名匹配。 **[!UICONTROL Priority]** 只有觸發器實作才需要。

   檢查協調密鑰是否正確。 此欄位的雜湊／加密值可用來匯出和匯入觀眾。

   若是散列或加密宣告的ID，請檢查您的網站上是否使用相同的參數／加密演算法。

   僅支援一個加密演算法：AES在CBC模式下，密鑰大小為128、192或256位，PKCS填充。

   如果選擇了AES加密算法，則必須正確設定以下附加欄位：

   * **AES的加密金鑰** (Encryption Key for AES)
   * **AES的Encryption IV** (Initialization Vector)
   * **渠道** （電子郵件／簡訊／其他）:此欄位可讓您直接解密電子郵件地址和簡訊號碼。 請確定協調鍵與「渠道」欄位的設 **置** 。 如果選擇「其他」，則不會發生此特定解密，並且會使用協調密鑰來協調資料。

   由於技術工作流程已停止或暫停，Experience Cloud觀眾可能無法共用。 直接按一 **[!UICONTROL Import shared audience]** 下資料來源中的選 **[!UICONTROL Show ImportShared Audience workflow]** 項，以存取工作流程。

透過「人員」核心服務共用觀眾或匯入觀眾時，可能會發生遺失部分資料的情況。 只會傳送ID（「訪客ID」或「Declared ID」）與描述檔維度可協調的記錄。 不會匯入Adobe Campaign未識別之「人員」核心服務區段的ID。
