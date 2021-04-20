---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard的可交付性監測
description: 使用Adobe Campaign Standard提供的工具監控平台的傳遞能力。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 10%

---


# 監視傳遞能力{#monitor-deliverability}

以下是&#x200B;**[!UICONTROL Delivery throughput]**&#x200B;報告以及Adobe Campaign提供的不同監控工具的詳細資訊。 以下是有關交付能力監控的一些附加准則：
* 定期檢查整個平台的傳送吞吐量，以確認其是否與原始設定一致。
* 檢查傳送範本中的重試設定是否正確（重試期間為30分鐘，重試次數超過20次）。
* 定期確認彈回信箱是否可存取，且帳戶不會過期。
* 檢查每個傳送吞吐量，以確定其與傳送內容的有效性一致(例如：&#39;flash銷售&#39;應在幾分鐘內完成，而非數天內完成)。
* 檢查錯誤數和新隔離數量是否與其他遞送一致。
* 請仔細查閱傳送記錄，以檢查反白顯示的錯誤類型（登入清單、DNS問題、反垃圾訊息規則等）。

## 傳送總處理能力 {#delivery-throughput}

此報表包含特定時段內整個平台的傳送吞吐量資訊，以測量傳送訊息的速度。

有關詳細資訊，請參閱[傳送吞吐量](../../reporting/using/delivery-throughput.md)。

![](assets/delivery_reports_1.png)

您可以變更時標來設定顯示的值。

其他報表也可用，例如&#x200B;**[!UICONTROL Delivery summary]**&#x200B;或&#x200B;**[!UICONTROL Non-deliverables and bounces]**。 如需詳細資訊，請參閱[動態報表](../../reporting/using/about-dynamic-reports.md)。

## 監視傳遞{#monitoring-deliveries}

訊息控制面板可讓您存取傳送記錄檔：**[!UICONTROL Sending logs]**、**[!UICONTROL Exclusion logs]**、**[!UICONTROL Exclusion causes]**、**[!UICONTROL Tracking logs]**&#x200B;和&#x200B;**[!UICONTROL Tracked URLs]**。 其中會顯示傳送的詳細資料、已排除的目標、原因，以及開啟和點按數等追蹤資訊。

有關詳細資訊，請參閱[監視傳送](../../sending/using/monitoring-a-delivery.md)。

![](assets/sending_delivery1.png)

## 接收警報{#receiving-alerts}

**[!UICONTROL Delivery alerting]**&#x200B;功能是警報管理系統，可讓一組使用者自動接收包含其傳送內容執行資訊的通知。

有關詳細資訊，請參閱[發生故障時接收警報](../../sending/using/receiving-alerts-when-failures-happen.md)。

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
