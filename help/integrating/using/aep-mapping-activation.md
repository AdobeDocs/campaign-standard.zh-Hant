---
title: 對應啟動
description: 瞭解如何激活資料映射
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d7ca0de6-7f7b-4e31-877c-909d962c5f53
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# 對應啟動 {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform資料連接器目前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

完成映射定義後，可以發佈映射。 在部署步驟後，Campaign Standard和Adobe Experience Platform之間的資料複製將自動啟動。 您可以隨時按一下 **[!UICONTROL Stop]** 按鈕

根據您對映射的修改，您可以選擇將所有記錄重新發送到Adobe Experience Platform。

![](assets/aep_publishmapping.png)

從部署磁貼，可以訪問發佈日誌並導出日誌。

![](assets/aep_publog.png)

在 **[!UICONTROL Export jobs]** 頁籤，可以監視已發佈映射的導出作業。

![](assets/aep_jobstatus.png)

如果要監視所有資料導出作業，請轉到 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** 的子菜單。

![](assets/aep_statusmapping.png)

資料接收作業狀態為：

* **[!UICONTROL Created]**:建立資料接收作業，並且正在進行資料接收。
* **[!UICONTROL Failed]**:資料接收作業失敗。 「原因」欄位描述了失敗的原因。 故障可以是暫時的或永久的。 在出現暫時性故障時，在配置的間隔後建立新的接收作業。 作為故障排除的第一步，用戶可以檢查故障原因欄位。 如果原因將用戶重定向到Adobe Experience PlatformUI，則用戶可以登錄Adobe Experience Platform，並可以檢查資料集中的批處理狀態以確定確切的失敗原因。
* **[!UICONTROL Uploaded]**:首先在Adobe Experience Platform建立批，然後將資料接收到該批。 批ID欄位顯示批在Adobe Experience Platform的批ID。 Adobe Experience Platform還對批執行後驗證。 批首先標籤為已上載，直到Adobe Experience Platform完成後驗證步驟。 一個作業在上載後繼續輪詢Adobe Experience Platform以瞭解批的狀態。 批可以在Adobe Experience Platform的失敗或成功狀態後驗證中進行。
* **[!UICONTROL Success]**:將批上載到Adobe Experience Platform後，在配置的時間間隔後檢查作業（平台中的後驗證）的狀態。 狀態「成功」在Adobe Experience Platform發現成功接收資料。

在某些情況下，在發佈映射時可能會出現以下驗證錯誤。

![](assets/aep_datamapping_ccpa.png)

當您使用的XDM架構尚未使用與隱私管理相關的最新XDM欄位更新，並且仍包含已棄用的&quot;ccpa&quot; XDM欄位時，就會發生這種情況。

要更新XDM架構，請執行以下步驟：

1. 使用XDM映射頁上的連結轉到Adobe Experience Platform上的資料集。

1. 導航到XDM架構。

1. 添加 **[!UICONTROL Profile Privacy]** 混合到架構中。

   ![](assets/aep_datamapping_privacyfield.png)

1. 保存架構，然後重試發佈映射。 該出版物現在應通過。

   ![](assets/aep_save_mapping.png)
