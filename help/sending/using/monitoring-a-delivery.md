---
title: 在 Adobe Campaign Standard 中監控傳送
description: 瞭解如何在 Adobe Campaign Standard 中監控傳送。
audience: sending
content-type: reference
topic-tags: monitoring-messages
context-tags: delivery,main
feature: Performance Monitoring
role: User
level: Beginner
exl-id: ddc92077-df73-411d-a161-3263581e6945
source-git-commit: ed60bde4785da9a8cc5a6cc0efcdb24e2c1f65e3
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 79%

---

# 監視傳遞{#monitoring-a-delivery}

監控傳送和衡量其影響的方法有幾種。 身為功能管理員，您可以存取訊息記錄檔和傳送記錄檔。

>[!IMPORTANT]
>
>僅功能 [管理員](../../administration/using/users-management.md#functional-administrators)，搭配 **[!UICONTROL Administration]** 角色與存取權 **全部** 單位可以存取傳送記錄、訊息記錄、追蹤記錄、排除或訂閱記錄。 非管理員使用者可以鎖定這些記錄，但從連結的表格（設定檔、傳送）開始。

* **訊息記錄檔**：可直接從訊息控制面板存取這些記錄檔。其中會顯示傳送的詳細資料、已排除的目標、原因，以及開啟和點按數等追蹤資訊。

   若要檢視訊息記錄檔，請按一下 **[!UICONTROL Deployment]** 區塊右下方的圖示。

   數個索引標籤包含關於　**[!UICONTROL Sending logs]**、**[!UICONTROL Exclusion logs]**、**[!UICONTROL Exclusion causes]**、**[!UICONTROL Tracking logs]** 及 **[!UICONTROL Tracked URLs]** 的資訊（若有的話）。請參閱[傳送記錄檔](#delivery-logs)。

   ![](assets/sending_delivery1.png)

   記錄檔包含與傳送和校樣相關的所有訊息。特定圖示可讓您識別錯誤或警告。如需詳細資訊，請參閱[核准訊息](../../sending/using/previewing-messages.md)。

   您可以按一下　**[!UICONTROL Export list]**　按鈕，以匯出記錄檔。

   ![](assets/sending_delivery2.png)

* **工作記錄檔**：您可以透過選取「 」，從訊息控制面板存取傳遞觸發的批次工作清單 **[!UICONTROL Job history]** 從 **[!UICONTROL Summary]** 下拉式清單。

   從清單中選取任何工作，以檢視所選專案的詳細資訊 **[!UICONTROL Batch job]**.

   ![](assets/sending_delivery8.png)

* **傳送警報**：為了追蹤傳送成功或失敗，Adobe Campaign　提供電子郵件警報系統，如此可傳送通知，以通知使用者發生重要的系統活動。
* **報告**：從訊息控制面板，您可以存取此特定訊息的數個報告。您也有 **[!UICONTROL Reports]** 功能表，這可讓您存取內建或自訂報告的完整清單，以便用於概述與訊息或促銷活動相關的特定度量。
* 管理員也可以匯出個別檔案中的記錄檔，以便在您自己的報告或　BI　工具中處理。如需詳細資訊，請參閱[匯出記錄檔](../../automating/using/exporting-logs.md)。

**相關主題：**

* [發生故障時接收警示](../../sending/using/receiving-alerts-when-failures-happen.md)
* [報告](../../reporting/using/about-dynamic-reports.md)

## 傳遞記錄 {#delivery-logs}

### 傳送記錄檔 {#sending-logs}

**[!UICONTROL Sending logs]** 索引標籤提供此傳送每次發生的記錄。已傳送訊息的清單及其狀態會儲存在此處。它可讓您檢視每個收件者的傳送狀態。

對於每個具有狀態 **[!UICONTROL Sent]** 的設定檔，**[!UICONTROL Date]** 欄會顯示訊息的傳送時間。

![](assets/sending_delivery3.png)

若要存取特定傳送記錄檔的詳細資料，請按一下相對應列右側的鉛筆圖示。

![](assets/sending_access-sending-log.png)

所有傳送記錄檔詳細資料都是唯讀狀態。您也可以看到鏡像頁面的預覽。

![](assets/sending_sending-log.png)

>[!NOTE]
>
>若要在 Campaign 使用者介面中顯示鏡像頁面呈現，鏡像頁面伺服器　URL　必須是安全的。在該情況下，在設定您的品牌時，請使用　https://（而非http://）[設定此 URL](../../administration/using/branding.md#configuring-and-using-brands)。

### 排除記錄檔 {#exclusion-logs}

**[!UICONTROL Exclusion logs]** 索引標籤會列出已從傳送目標排除的所有訊息，以及指定傳送失敗的原因。

![](assets/sending_delivery4.png)

### 排除原因 {#exclusion-causes}

**[!UICONTROL Exclusion causes]** 索引標籤會顯示已從目標傳送排除的訊息數量（以訊息數計算）。

![](assets/sending_delivery5.png)
