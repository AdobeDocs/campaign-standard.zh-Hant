---
solution: Campaign Standard
product: campaign
title: 映射啟動
description: 瞭解如何啟動資料對應
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---


# 映射啟動 {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform資料連接器目前正在測試中，可能會在不另行通知的情況下頻繁更新。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

當映射定義完成時，可以發佈映射。 在部署步驟後，將自動啟動Campaign Standard與Adobe Experience Platform之間的資料複製。 您可以隨時按一下&#x200B;**[!UICONTROL Stop]**&#x200B;按鈕來停止複製。

視您的對應修改而定，您可以選擇將所有記錄重新傳送至Adobe Experience Platform。

![](assets/aep_publishmapping.png)

從部署圖格中，您可以存取出版物記錄檔並匯出記錄檔。

![](assets/aep_publog.png)

在&#x200B;**[!UICONTROL Export jobs]**&#x200B;標籤中，您可以監視已發佈映射的導出作業。

![](assets/aep_jobstatus.png)

如果要監視所有資料導出作業，請轉至&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**&#x200B;菜單。

![](assets/aep_statusmapping.png)

資料擷取工作狀態為：

* **[!UICONTROL Created]**:建立資料提取作業並正在進行資料提取。
* **[!UICONTROL Failed]**:資料擷取工作失敗。原因欄位說明失敗的原因。 故障可以是暫時的或永久的。 在發生瞬時故障時，在配置的間隔後建立新的提取作業。 作為疑難排解的第一步，使用者可以檢查失敗的原因欄位。 如果原因將使用者重新導向至Adobe Experience PlatformUI，使用者可登入Adobe Experience Platform，並可檢查資料集中的批次狀態，以判斷確切的失敗原因。
* **[!UICONTROL Uploaded]**:首先在Adobe Experience Platform建立批，然後將資料吸收到該批。批次ID欄位顯示批次在Adobe Experience Platform的批次ID。 Adobe Experience Platform也會對批執行後置驗證。 批次會先標示為已上傳，直到Adobe Experience Platform完成貼文驗證步驟為止。 作業在上傳後持續輪詢Adobe Experience Platform批的狀態。 批可以在Adobe Experience Platform的「失敗」或「成功」狀態的貼文驗證中進行。
* **[!UICONTROL Success]**:在將批上傳到Adobe Experience Platform後，作業的狀態（平台中的後驗證）在配置的時間間隔後被檢查。「成功」狀態在Adobe Experience Platform識別了成功的資料擷取。

在某些情況下，發佈對應時，您可能會收到以下驗證錯誤。

![](assets/aep_datamapping_ccpa.png)

當您使用的XDM架構未更新為與隱私權管理相關的最新XDM欄位，且仍包含已過時的「ccpa」 XDM欄位時，就會發生此情況。

要更新XDM模式，請執行以下步驟：

1. 使用XDM對應頁面上的連結，前往Adobe Experience Platform的資料集。

1. 導覽至您的XDM架構。

1. 將&#x200B;**[!UICONTROL Profile Privacy]** mixin新增至架構。

   ![](assets/aep_datamapping_privacyfield.png)

1. 儲存結構，然後重新嘗試發佈對應。 出版物現在應該通過。

   ![](assets/aep_save_mapping.png)
