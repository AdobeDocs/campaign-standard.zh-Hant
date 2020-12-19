---
solution: Campaign Standard
product: campaign
title: 疑難排解
description: 瞭解如何疑難排解共用資源時的問題。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---


# 疑難排解{#troubleshooting}

使用與Audience Manager或People核心服務整合時可能會發生錯誤。

在此情況下，請確定下列元素已正確設定：

* **外部帳戶**

   在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**&#x200B;中，請確定以下外部S3帳戶已正確配置。 在設定期間應已配置上述S3伺服器。

   * **[!UICONTROL importSharedAudience]**:S3帳戶專用於匯入觀眾。
   * **[!UICONTROL exportSharedAudience]**:S3帳戶專用於匯出觀眾。

* **共用資料來源**

   在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，檢查共用資料源是否已正確設定。

   **[!UICONTROL Priority]** 在定義多個資料來源時使用。優先順序決定將使用哪個資料源與按定義順序接收的別名匹配。 **[!UICONTROL Priority]** 只有觸發器實作才需要。

   檢查協調密鑰是否正確。 此欄位的雜湊／加密值可用來匯出和匯入觀眾。

   若是散列或加密宣告的ID，請檢查您的網站上是否使用相同的參數／加密演算法。

   僅支援一個加密演算法：AES在CBC模式下，密鑰大小為128、192或256位，PKCS填充。

   如果選擇了AES加密算法，則必須正確設定以下附加欄位：

   * **AES的** 加密密鑰
   * **AES的Encryption IV** (Initialization Vector)
   * **頻道** （電子郵件／簡訊／其他）:此欄位可讓您直接解密電子郵件地址和簡訊號碼。確保協調密鑰與&#x200B;**Channel**&#x200B;欄位的設定匹配。 如果選擇「其他」，則不會發生此特定解密，並且會使用協調密鑰來協調資料。

   由於技術工作流程已停止或暫停，Experience Cloud觀眾可能無法共用。 直接按一下資料來源中的&#x200B;**[!UICONTROL Show ImportShared Audience workflow]**&#x200B;選項，以存取&#x200B;**[!UICONTROL Import shared audience]**&#x200B;工作流程。

透過「人員」核心服務共用觀眾或匯入觀眾時，可能會發生遺失部分資料的情況。 只會傳送ID（「訪客ID」或「Declared ID」）與描述檔維度可協調的記錄。 不會匯入Adobe Campaign未識別之「人員」核心服務區段的ID。
