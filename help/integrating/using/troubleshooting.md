---
title: 排除整合問題
description: 瞭解如何解決共用資源時的問題。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# 疑難排解{#troubleshooting}

使用與Audience Manager或人員核心服務整合時可能遇到錯誤。

在這種情況下，請確保正確配置了以下元素：

* **外部帳戶**

   在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**，確保正確配置了以下外部S3帳戶。 在配置過程中應配置上述S3伺服器。

   * **[!UICONTROL importSharedAudience]**:S3帳戶專用於導入受眾。
   * **[!UICONTROL exportSharedAudience]**:S3帳戶專用於導出受眾。

* **共用資料源**

   在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**，檢查共用資料源是否設定正確。

   **[!UICONTROL Priority]** 定義多個資料源時使用。 優先順序決定將使用哪個資料源與按定義的順序接收的別名匹配。 **[!UICONTROL Priority]** 僅對觸發器實現需要。

   檢查協調密鑰是否正確。 用於導出和導入受眾的是此欄位的散列/加密值。

   如果對聲明的ID進行散列或加密，請檢查您的網站上是否使用了相同的參數/加密算法。

   僅支援一種加密算法：AES在CBC模式下，密鑰大小為128、192或256位，使用PKCS填充。

   如果選擇了AES加密算法，則必須正確設定以下附加欄位：

   * **加密密鑰** AES
   * **加密IV** （初始化向量）AES
   * **頻道** （電子郵件/SMS/其他）:此欄位允許直接解密電子郵件地址和SMS號碼。 確保協調密鑰與 **頻道** 的子菜單。 如果選擇「其他」，則此特定的解密將不會發生，並且協調密鑰將用於協調資料。

   Experience Cloud受眾可能無法共用，因為技術工作流已停止或暫停。 訪問 **[!UICONTROL Import shared audience]** 通過直接按一下 **[!UICONTROL Show ImportShared Audience workflow]** 的子菜單。

當通過人員核心服務共用受眾或導入受眾時，可能會發生丟失某些資料的情況。 只傳送ID（「訪問者ID」或「聲明的ID」）與配置檔案維度對帳的記錄。 Adobe Campaign未識別的People核心服務段的ID不會導入。
