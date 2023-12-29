---
title: 疑難排解整合問題
description: 瞭解如何在共用資源時疑難排解問題。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---

# 疑難排解{#troubleshooting}

使用與Audience Manager或People核心服務整合時可能會發生錯誤。

在此情況下，請確定下列元素已正確設定：

* **外部帳戶**

  在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**，確定下列外部S3帳戶已正確設定。 布建期間應已設定上述S3伺服器。

   * **[!UICONTROL importSharedAudience]**：專用於匯入對象的S3帳戶。
   * **[!UICONTROL exportSharedAudience]**：專用於匯出受眾的S3帳戶。

* **共用的資料來源**

  在 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**，檢查共用資料來源是否已正確設定。

  **[!UICONTROL Priority]** 定義多個資料來源時使用。 優先順序會決定要使用哪個資料來源來比對以定義順序收到的別名。 **[!UICONTROL Priority]** 僅適用於Triggers實施。

  檢查調解金鑰是否正確。 這是此欄位的雜湊/加密值，用於匯出和匯入對象。

  若是雜湊或加密宣告ID，請檢查您的網站上是否使用相同的引數/加密演演算法。

  僅支援一個加密演演算法：CBC模式的AES，金鑰大小為128、192或256位元，具有PKCS邊距。

  如果選取了AES加密演演算法，則必須正確設定下列其他欄位：

   * **加密金鑰** 適用於AES
   * **加密IV** AES的（初始化向量）
   * **頻道** （電子郵件/簡訊/其他）：此欄位允許直接解密電子郵件地址和簡訊號碼。 請確定調解金鑰與 **頻道** 欄位。 如果您選取[其他]，將不會發生這個特定的解密，而且調解金鑰將會用來調解資料。

  Experience Cloud對象可能不會共用，因為技術工作流程已停止或暫停。 存取 **[!UICONTROL Import shared audience]** 直接按一下 **[!UICONTROL Show ImportShared Audience workflow]** 資料來源中的選項。

透過People核心服務共用對象或匯入對象時，可能會遺失部分資料。 只有其ID （「訪客ID」或「宣告ID」）能夠與設定檔維度調解的記錄才會轉移。 Adobe Campaign無法辨識的People核心服務區段之ID不會匯入。
