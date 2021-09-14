---
title: 疑難排解
description: 了解如何疑難排解共用資源時的問題。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# 疑難排解{#troubleshooting}

使用與Audience Manager或People核心服務的整合時，可能會發生錯誤。

在此情況下，請確定下列元素已正確設定：

* **外部帳戶**

   在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**&#x200B;中，確認下列外部S3帳戶已正確設定。 設定期間應已設定上述的S3伺服器。

   * **[!UICONTROL importSharedAudience]**:專用於匯入對象的S3帳戶。
   * **[!UICONTROL exportSharedAudience]**:專用於匯出受眾的S3帳戶。

* **共用資料來源**

   在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**&#x200B;中，檢查共用資料源是否設定正確。

   **[!UICONTROL Priority]** 會在已定義多個資料來源時使用。優先順序決定要使用哪個資料源來匹配按定義順序接收的別名。 **[!UICONTROL Priority]** 只有觸發器實作才需要。

   檢查調解金鑰是否正確。 是此欄位的雜湊/加密值，用來匯出和匯入對象。

   若是對宣告ID進行雜湊處理或加密，請檢查網站上是否使用相同的參數/加密演算法。

   僅支援一個加密算法：CBC模式下的AES，密鑰大小為128、192或256位，帶PKCS填充。

   如果選擇了AES加密算法，則必須正確設定以下附加欄位：

   * **AES的** 加密密鑰
   * **AES的加密** IV（初始化向量）
   * **通道** （電子郵件/簡訊/其他）:此欄位可讓您直接解密電子郵件地址和SMS號碼。確認調解金鑰符合&#x200B;**Channel**&#x200B;欄位的設定。 如果選擇「其他」，則此特定解密將不會發生，且調解密鑰將用於調解資料。

   Experience Cloud對象可能無法共用，因為技術工作流程已停止或暫停。 直接按一下資料來源中的&#x200B;**[!UICONTROL Show ImportShared Audience workflow]**&#x200B;選項，以存取&#x200B;**[!UICONTROL Import shared audience]**&#x200B;工作流程。

透過「人物」核心服務共用受眾或匯入受眾時，可能會發生缺少某些資料的情況。 只有ID（「訪客ID」或「宣告ID」）能與設定檔維度調解的記錄能夠傳輸。 來自People核心服務區段且Adobe Campaign未辨識的ID不會匯入。
