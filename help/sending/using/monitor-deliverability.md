---
title: 監測Adobe Campaign Standard的交付能力
description: 使用Adobe Campaign Standard提供的工具來監控您的平台的可交付性。
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
source-wordcount: '306'
ht-degree: 10%

---

# 監視傳遞能力{#monitor-deliverability}

在下面，您將查找 **[!UICONTROL Delivery throughput]** 報告以及Adobe Campaign提供的各種監測工具。 以下是有關交付性監控的一些附加准則：
* 定期檢查整個平台的交付吞吐量，以驗證其是否與原始設定一致。
* 檢查傳遞模板中是否正確設定了重試次數（重試週期為30分鐘，重試次數超過20次）。
* 定期驗證彈出郵箱是否可訪問，且帳戶不會過期。
* 檢查每個傳遞吞吐量，確保其與傳遞內容的有效性一致(例如「快閃銷售」應在幾分鐘內完成，而不是幾天)。
* 檢查錯誤數和新隔離數是否與其他交貨一致。
* 請仔細查閱交付日誌，以檢查突出顯示的錯誤類型（密文清單、DNS問題、反垃圾郵件規則等）。

## 傳遞總處理能力 {#delivery-throughput}

此報告包含給定時段內整個平台的傳遞吞吐量資訊，以衡量消息傳遞的速度。

有關此的詳細資訊，請參閱 [交付吞吐量](../../reporting/using/delivery-throughput.md)。

![](assets/delivery_reports_1.png)

可以通過更改時間刻度來配置顯示的值。

其他報告可用，如 **[!UICONTROL Delivery summary]** 或 **[!UICONTROL Non-deliverables and bounces]**。 有關此的詳細資訊，請參閱 [動態報告](../../reporting/using/about-dynamic-reports.md)。

## 監視傳遞 {#monitoring-deliveries}

消息儀表板允許您訪問傳遞日誌： **[!UICONTROL Sending logs]**。 **[!UICONTROL Exclusion logs]**。 **[!UICONTROL Exclusion causes]**。 **[!UICONTROL Tracking logs]** 和 **[!UICONTROL Tracked URLs]**。 其中會顯示傳送的詳細資料、已排除的目標、原因，以及開啟和點按數等追蹤資訊。

有關此的詳細資訊，請參閱 [監控交付](../../sending/using/monitoring-a-delivery.md)。

![](assets/sending_delivery1.png)

## 接收警報 {#receiving-alerts}

的 **[!UICONTROL Delivery alerting]** 功能是警報管理系統，它使一組用戶能夠自動接收包含其交付執行資訊的通知。

有關此的詳細資訊，請參閱 [在失敗時接收警報](../../sending/using/receiving-alerts-when-failures-happen.md)。

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
