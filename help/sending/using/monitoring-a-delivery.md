---
title: 監控傳送
seo-title: 監控傳送
description: 監控傳送
seo-description: 瞭解如何監控傳送。
page-status-flag: 從未啓動
uuid: 7772c607-debd-40fd-8322-4d49119979 b4
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: 監控訊息
discoiquuid: eb9fa216-4568-423a-9396-1f7b82181ae9
context-tags: 傳送，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Monitoring a delivery{#monitoring-a-delivery}

有幾種方式可監控傳送並評估其影響：

* **訊息記錄**：可直接從訊息控制面板存取這些記錄檔。它們會顯示傳送的詳細資料、目標已排除的目標，以及追蹤資訊(例如開啓和點按)。

   To view the message logs, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   Several tabs contain information (if it exists) regarding the **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** and **[!UICONTROL Tracked URLs]**. See [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   ![](assets/sending_delivery1.png)

   記錄檔包含所有與傳送和校樣有關的訊息。特定圖示可讓您識別錯誤或警告。For more on this, see [Approving messages](../../sending/using/previewing-messages.md).

   You can export the log by clicking the **[!UICONTROL Export list]** button.

   ![](assets/sending_delivery2.png)

* **傳送警報**：為追蹤傳送成功或失敗，Adobe Campaign提供電子郵件警報系統，可傳送通知通知使用者重要系統活動。
* **報表**：從訊息控制面板，您可以存取此特定訊息的數個報表。You also have a **[!UICONTROL Reports]** menu that allows you to access a complete list of built-in or custom reports that you can use to outline specific metrics related to your message or campaign.
* 管理員也可以將記錄匯出成個別檔案，以便在您自己的報表或BI工具中處理。For more on this, see [Exporting logs](../../automating/using/exporting-logs.md).

**相關主題：**

* [在發生失敗時接收警報](../../sending/using/receiving-alerts-when-failures-happen.md)
* [報表](../../reporting/using/about-dynamic-reports.md)

## Delivery logs {#delivery-logs}

### Sending logs {#sending-logs}

**[!UICONTROL Sending logs]** 此標籤提供此傳送的每個事件的歷史記錄。已傳送訊息及其狀態的清單儲存在此處。它可讓您檢視每個收件者的傳送狀態。

For each profile with a **[!UICONTROL Sent]** status, the **[!UICONTROL Date]** column shows when the message was sent.

![](assets/sending_delivery3.png)

### Exclusion logs {#exclusion-logs}

**[!UICONTROL Exclusion logs]** 此標籤會列出已從目標傳送的所有訊息，並指定傳送失敗的原因。

![](assets/sending_delivery4.png)

### Exclusion causes {#exclusion-causes}

**[!UICONTROL Exclusion causes]** 此標籤會顯示從目標傳送排除的訊息數量(以訊息數量為單位)。

![](assets/sending_delivery5.png)

