---
title: 在Adobe Campaign Standard中監視傳遞能力
description: 使用Adobe Campaign Standard提供的工具來監視平台的傳遞能力。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 683341fb-fef5-4aa1-8606-9526d9ae6290
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 9%

---

# 監視傳遞能力{#monitor-deliverability}

您將會在下方找到 **[!UICONTROL Delivery throughput]** 以及Adobe Campaign提供的各種監控工具。 以下是傳遞能力監視的其他准則：
* 定期檢查整個平台的傳送輸送量，確認其是否與原始設定一致。
* 檢查傳遞範本中重試的設定是否正確（重試期間為30分鐘，重試次數超過20次）。
* 定期確認可存取退信箱，且帳戶不會過期。
* 檢查每個傳遞輸送量，確保其與傳遞內容的有效性一致（例如「快閃銷售」應在幾分鐘內傳遞，而非幾天）。
* 檢查錯誤和新隔離的數量是否與其他傳送一致。
* 請仔細查閱傳送詳細資訊，以檢查醒目提示的錯誤型別（封鎖清單、DNS問題、反垃圾郵件規則等）。

## 傳遞總處理能力 {#delivery-throughput}

此報表包含指定期間內整個平台的傳遞輸送量資訊，以測量傳遞訊息的速度。

有關詳細資訊，請參閱 [傳遞總處理能力](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

您可以透過變更時標來設定顯示的值。

有其他報表可供使用，例如 **[!UICONTROL Delivery summary]** 或 **[!UICONTROL Non-deliverables and bounces]**. 有關詳細資訊，請參閱 [動態報告](../../reporting/using/about-dynamic-reports.md).

## 監視傳遞 {#monitoring-deliveries}

訊息控制面板可讓您存取傳遞記錄： **[!UICONTROL Sending logs]**， **[!UICONTROL Exclusion logs]**， **[!UICONTROL Exclusion causes]**， **[!UICONTROL Tracking logs]** 和 **[!UICONTROL Tracked URLs]**. 其中會顯示傳送的詳細資料、已排除的目標、原因，以及開啟和點按數等追蹤資訊。

有關詳細資訊，請參閱 [監視傳遞](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## 接收警示 {#receiving-alerts}

此 **[!UICONTROL Delivery alerting]** 功能是警報管理系統，可讓一組使用者自動接收包含其傳送執行資訊的通知。

有關詳細資訊，請參閱 [發生故障時接收警報](../../sending/using/receiving-alerts-when-failures-happen.md).

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
