---
title: 確認傳送
description: 瞭解如何完成訊息準備。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 0a0fe969-cdfd-4b0c-a746-081038424d86
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 18%

---

# 確認傳送{#confirming-the-send}

在您j完成訊息準備並執行核准步驟後，即可傳送訊息。如需訊息準備的詳細資訊，請參閱[準備傳送](../../sending/using/preparing-the-send.md)。

僅具有 **[!UICONTROL Start deliveries]** 角色可以確認發送。 如需詳細資訊，請參閱[角色清單](../../administration/using/list-of-roles.md)區段。

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## 發送消息 {#sending-message}

準備完成後，請按照以下步驟發送您的消息。

1. 按一下 **[!UICONTROL Confirm send]** 按鈕。

   ![](assets/confirm_delivery.png)

1. 通過按一下 **[!UICONTROL OK]** 按鈕

   ![](assets/confirm_delivery1.png)

1. 正在發送消息，請稍候。 **[!UICONTROL Deployment]** 區塊會顯示傳送的進度。

>[!NOTE]
>
>如果消息已計畫，則在到達發送時發送消息。 如需排程訊息的詳細資訊，請參閱[本區段](../../sending/using/about-scheduling-messages.md)。

如果您使用不含彙總期間的循環傳送，則可在傳送傳遞前要求確認。配置消息時，開啟 **[!UICONTROL Schedule]** 並激活專用選項。

![](assets/confirmation_recurring_deliveries.png)

## 瞭解消息指示器 {#message-indicators}

將消息傳送給聯絡人之後，**[!UICONTROL Deployment]** 區域會顯示您的 KPI（關鍵績效指標）資料，包含：

* 要傳送的訊息數量
* 已傳送的訊息數量
* 已傳送的訊息百分比
* 退信及錯誤的百分比
* 已開啟訊息的百分比
* 訊息中的點按百分比（電子郵件）

   >[!NOTE]
   >
   >**[!UICONTROL Open rate]** 及 **[!UICONTROL Click-through rate]** 每小時會更新一次。

![](assets/sending_delivery.png)

如果KPI更新時間過長或未反映發送日誌的結果，請按一下 **[!UICONTROL Compute stats]** 按鈕 **[!UICONTROL Deployment]** 的子菜單。

![](assets/sending_delivery7.png)

可以在目標配置檔案之一的歷史記錄中查看該消息。 請參閱[整合式客戶設定檔](../../audiences/using/integrated-customer-profile.md)。

一旦發送郵件，您就可以跟蹤其收件人的行為，並監視它以衡量其影響。 如需詳細資訊，請參閱下列區段。

* [追蹤訊息](../../sending/using/tracking-messages.md)
* [監視傳遞](../../sending/using/monitoring-a-delivery.md)

### 交付成功報告 {#delivered-status-report}

>[!NOTE]
>
>本節僅適用於電子郵件通道。

在 **[!UICONTROL Summary]** 查看每封電子郵件 **[!UICONTROL Delivered]** 百分比從100%開始，然後在整個交貨期間逐漸下降 [有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters)當軟硬邊界被報回時<!--from the Enhanced MTA to Campaign-->。

事實上，所有消息都顯示為 **[!UICONTROL Sent]** 的 [發送日誌](../../sending/using/monitoring-a-delivery.md#sending-logs) 一旦它們成功從市場活動轉發到增強的MTA（消息傳輸代理）。 除非或直到 [彈](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) 從增強型MTA到「活動」傳遞該消息。

當硬跳消息從增強MTA返回報告時，其狀態將從 **[!UICONTROL Sent]** 至 **[!UICONTROL Failed]** 和 **[!UICONTROL Delivered]** 百分比相應減少。

從增強MTA返回軟跳跳消息時，它們仍顯示為 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比尚未更新。 然後軟跳跳消息 [重試](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) 在整個交貨有效期內：

* 如果在有效期結束前重試成功，則消息狀態將保持為 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比保持不變。

* 否則，狀態將更改為 **[!UICONTROL Failed]** 和 **[!UICONTROL Delivered]** 百分比相應減少。

因此，您必須等到有效期結束後才能查看最終版本 **[!UICONTROL Delivered]** 百分比，以及 **[!UICONTROL Sent]** 和 **[!UICONTROL Failed]** 消息。

### 電子郵件反饋服務（測試版） {#email-feedback-service}

借助電子郵件反饋服務(EFS)功能，可以準確報告每封電子郵件的狀態，因為反饋會直接從增強的MTA（郵件傳輸代理）中捕獲。

>[!IMPORTANT]
>
>電子郵件反饋服務目前可作為測試版功能使用。

一旦開始交貨， **[!UICONTROL Delivered]** 成功將消息從「市場活動」中繼到「增強的MTA」時的百分比。

![](assets/efs-sending.png)

交貨日誌顯示 **[!UICONTROL Pending]** 每個目標地址的狀態。

![](assets/efs-pending.png)

當從增強型MTA即時報告到目標配置檔案的消息傳遞時，傳遞日誌將顯示 **[!UICONTROL Sent]** 成功接收消息的每個地址的狀態。 的 **[!UICONTROL Delivered]** 每次成功交付時，百分比都相應增加。

當硬跳消息從增強MTA返回報告時，其日誌狀態將從 **[!UICONTROL Pending]** 至 **[!UICONTROL Failed]** 和 **[!UICONTROL Bounces + errors]** 百分比相應增加。

當軟跳跳消息從增強MTA返回報告時，其日誌狀態也會更改 **[!UICONTROL Pending]** 至 **[!UICONTROL Failed]** 和 **[!UICONTROL Bounces + errors]** 百分比相應增加。 的 **[!UICONTROL Delivered]** 百分比保持不變。 然後在整個傳送過程中重試軟彈跳消息 [有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* 如果在有效期結束前重試成功，則消息狀態將更改為 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比相應增加。

* 否則，狀態將保持為 **[!UICONTROL Failed]**。 的 **[!UICONTROL Delivered]** 和 **[!UICONTROL Bounces + errors]** 百分比保持不變。

>[!NOTE]
>
>有關硬邊界和軟邊界的詳細資訊，請參閱 [此部分](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。
>
>有關傳遞臨時失敗後重試的更多資訊，請參見 [此部分](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### EFS引入的更改 {#changes-introduced-by-efs}

下表顯示了EFS功能引入的KPI和發送日誌狀態的更改。

**使用電子郵件反饋服務**

| 發送過程中的步驟 | KPI摘要 | 正在發送日誌狀態 |
|--- |--- |--- |
| 已成功將消息從市場活動中轉到增強的MTA | <ul><li>**[!UICONTROL Delivered]** 百分比以0%開始</li><li>**[!UICONTROL Bounces + errors]** 百分比以0%開始</li></ul> | 待處理 |
| 從增強的MTA返回硬跳消息 | <ul><li>未更改 **[!UICONTROL Delivered]** 百分比</li><li>**[!UICONTROL Bounces + errors]** 百分比相應增加</li></ul> | 失敗 |
| 從增強的MTA返回軟彈跳消息 | <ul><li>未更改 **[!UICONTROL Delivered]** 百分比</li><li>**[!UICONTROL Bounces + errors]** 百分比相應增加</li></ul> | 失敗 |
| 軟彈跳消息重試成功 | <ul><li>**[!UICONTROL Delivered]** 百分比相應增加</li><li>**[!UICONTROL Bounces + errors]** 百分比相應減少</li></ul> | 已傳送 |
| 軟跳轉消息重試失敗 | <ul><li> 未更改 **[!UICONTROL Delivered]** 百分比 </li><li> 未更改 **[!UICONTROL Bounces + errors]** 百分比 </li></ul> | 失敗 |

**沒有電子郵件反饋服務**

| 發送過程中的步驟 | KPI摘要 | 正在發送日誌狀態 |
|--- |--- |--- |
| 已成功將消息從市場活動中轉到增強的MTA | <ul><li>**[!UICONTROL Delivered]** 百分比從100%開始</li><li>**[!UICONTROL Bounces + errors]** 百分比以0%開始</li></ul> | 已傳送 |
| 從增強的MTA返回硬跳消息 | <ul><li>**[!UICONTROL Delivered]** 百分比相應減少</li><li>**[!UICONTROL Bounces + errors]** 百分比相應增加</li></ul> | 失敗 |
| 從增強的MTA返回軟彈跳消息 | <ul><li>未更改 **[!UICONTROL Delivered]** 百分比</li><li>未更改 **[!UICONTROL Bounces + errors]** 百分比</li></ul> | 已傳送 |
| 軟彈跳消息重試成功 | <ul><li>未更改 **[!UICONTROL Delivered]** 百分比</li><li>未更改 **[!UICONTROL Bounces + errors]** 百分比</li></ul> | 已傳送 |
| 軟跳轉消息重試失敗 | <ul><li>**[!UICONTROL Delivered]** 百分比相應減少</li><li>**[!UICONTROL Bounces + errors]** 百分比相應增加</li></ul> | 失敗 |
