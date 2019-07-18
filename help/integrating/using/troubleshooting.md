---
title: 疑難排解
seo-title: 疑難排解
description: 疑難排解
seo-description: 瞭解如何疑難排解共用資源的問題。
page-status-flag: 從未啓動
uuid: 1c764dd8-e09 f-4e8 e8 e-9cr3 d714284
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: working-with-campaign-and-udience-manager-or-ople-core-service
discoiquuid: c28e1d90-8074-4127-a6 fc-ed39 d69 cdb19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Troubleshooting{#troubleshooting}

使用Audience Manager或People核心服務的整合時可能會發生錯誤。

在此情況下，請確定下列元素已正確設定：

* **外部帳戶**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, make sure that the following external S3 accounts are correctly configured. 所提及的S伺服器應該已在布建期間設定。

   * **[!UICONTROL importSharedAudience]**：專門匯入觀眾的S帳戶。
   * **[!UICONTROL exportSharedAudience]**：專門匯出觀眾的S帳戶。

* **共用資料來源**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, check that the shared data source is set properly.

   **[!UICONTROL Priority]** 時會使用多個資料來源。優先順序決定使用哪個資料來源符合所定義順序的別名。**[!UICONTROL Priority]** 僅需要觸發器實施。

   檢查協調索引鍵是否正確。此欄位是用來匯出及匯入對象的雜湊/加密值。

   若有雜湊或加密宣告的ID，請檢查您的網站上是否使用相同的參數/加密演算法。

   僅支援一個加密演算法：AES模式為128、192或256位元的CBC模式，具有PKCS間距。

   如果選取AES加密演算法，則必須正確設定下列其他欄位：

   * **AES的加密金鑰**
   * **AES的加密IV** (初始化向量)
   * **頻道** (電子郵件/簡訊/其他)：此欄位可直接解密電子郵件地址和SMS號碼。Make sure that the reconciliation key matches the setting of the **Channel** field. 如果您選取「其他」，則不會發生此特定解密，且將使用協調金鑰來協調資料。
   Experience Cloud觀眾可能無法共用，因為技術工作流程已停止或暫停。Access the **[!UICONTROL Import shared audience]** workflow by clicking directly the **[!UICONTROL Show ImportShared Audience workflow]** option in your Data source.

可能發生某些資料會在透過人員核心服務或匯入對象時分享觀眾的情形。只會傳輸ID('訪客ID'或「宣告ID」)能夠與描述檔維度協調的記錄。並非由Adobe Campaign識別的人員核心服務區段中的ID未匯入。
