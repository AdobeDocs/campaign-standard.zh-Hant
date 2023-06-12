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

僅限具有下列專案的使用者： **[!UICONTROL Start deliveries]** 角色可以確認傳送。 如需詳細資訊，請參閱[角色清單](../../administration/using/list-of-roles.md)區段。

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## 傳送訊息 {#sending-message}

準備完成後，請依照下列步驟傳送訊息。

1. 按一下 **[!UICONTROL Confirm send]** 在訊息的動作列中找到的按鈕。

   ![](assets/confirm_delivery.png)

1. 按一下 **[!UICONTROL OK]** 按鈕。

   ![](assets/confirm_delivery1.png)

1. 正在傳送訊息，請稍候。 **[!UICONTROL Deployment]** 區塊會顯示傳送的進度。

>[!NOTE]
>
>如果已排程訊息，則會在達到傳送時間時傳送訊息。 如需排程訊息的詳細資訊，請參閱[本區段](../../sending/using/about-scheduling-messages.md)。

如果您使用不含彙總期間的循環傳送，則可在傳送傳遞前要求確認。設定訊息時，請開啟 **[!UICONTROL Schedule]** 區塊的傳送控制面板並啟動專用選項。

![](assets/confirmation_recurring_deliveries.png)

## 瞭解訊息指標 {#message-indicators}

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

如果KPI更新時間過長或未反映傳送記錄檔的結果，請按一下 **[!UICONTROL Compute stats]** 中的按鈕 **[!UICONTROL Deployment]** 視窗。

![](assets/sending_delivery7.png)

可以在其中一個目標設定檔的歷史記錄中檢視訊息。 請參閱[整合式客戶設定檔](../../audiences/using/integrated-customer-profile.md)。

傳送訊息後，您可以追蹤其收件者的行為，並監控該訊息以評估其影響。 如需詳細資訊，請參閱下列區段。

* [追蹤訊息](../../sending/using/tracking-messages.md)
* [監視傳遞](../../sending/using/monitoring-a-delivery.md)

### 傳遞成功報告 {#delivered-status-report}

>[!NOTE]
>
>本節內容僅適用於電子郵件頻道。

在 **[!UICONTROL Summary]** 每封電子郵件的檢視， **[!UICONTROL Delivered]** 百分比從100%開始，然後在整個傳送過程中逐步下降 [有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters)，因為系統回報軟跳出和硬跳出<!--from the Enhanced MTA to Campaign-->.

事實上，所有訊息都會顯示為 **[!UICONTROL Sent]** 在 [傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs) 只要成功從Campaign轉送至Enhanced MTA （訊息傳輸代理程式）。 除非或直至 [跳出](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) ，該訊息的訊息會從Enhanced MTA傳回Campaign。

當硬跳出訊息從Enhanced MTA回傳時，其狀態會從 **[!UICONTROL Sent]** 至 **[!UICONTROL Failed]** 和 **[!UICONTROL Delivered]** 百分比會據此減少。

當從Enhanced MTA回報軟退信時，仍會顯示為 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比尚未更新。 然後，軟跳出訊息會 [已重試](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) 在整個傳遞有效期間：

* 如果在有效期結束前重試成功，則訊息狀態將保持為 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比保持不變。

* 否則，狀態會變更為 **[!UICONTROL Failed]** 和 **[!UICONTROL Delivered]** 百分比會據此減少。

因此，您必須等到有效期結束才能看到最終結果 **[!UICONTROL Delivered]** 百分比，以及最終數量 **[!UICONTROL Sent]** 和 **[!UICONTROL Failed]** 訊息。

### 電子郵件回饋服務（測試版） {#email-feedback-service}

使用電子郵件回饋服務(EFS)功能，可準確報告每封電子郵件的狀態，因為回饋會直接從Enhanced MTA （訊息傳輸代理程式）擷取。

>[!IMPORTANT]
>
>電子郵件回饋服務目前提供測試版功能。

開始傳送後，此專案沒有變更 **[!UICONTROL Delivered]** 訊息成功從Campaign轉送至Enhanced MTA時的百分比。

![](assets/efs-sending.png)

傳遞記錄顯示 **[!UICONTROL Pending]** 每個目標地址的狀態。

![](assets/efs-pending.png)

當從Enhanced MTA即時回報訊息傳送至目標設定檔時，傳送記錄會顯示 **[!UICONTROL Sent]** 成功收到訊息的每個位址的狀態。 此 **[!UICONTROL Delivered]** 百分比會隨著每次成功傳遞而相應增加。

從Enhanced MTA回報硬跳出訊息時，其記錄狀態會從 **[!UICONTROL Pending]** 至 **[!UICONTROL Failed]** 和 **[!UICONTROL Bounces + errors]** 百分比會相應增加。

當從Enhanced MTA回報軟退信時，其記錄狀態也會從 **[!UICONTROL Pending]** 至 **[!UICONTROL Failed]** 和 **[!UICONTROL Bounces + errors]** 百分比會相應增加。 此 **[!UICONTROL Delivered]** 百分比保持不變。 然後，軟跳出訊息會在整個傳遞期間重試 [有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters)：

* 如果在有效期結束前重試成功，則訊息狀態會變更為 **[!UICONTROL Sent]** 和 **[!UICONTROL Delivered]** 百分比會相應增加。

* 否則，狀態會維持為 **[!UICONTROL Failed]**. 此 **[!UICONTROL Delivered]** 和 **[!UICONTROL Bounces + errors]** 百分比保持不變。

>[!NOTE]
>
>如需硬跳出和軟跳出的詳細資訊，請參閱 [本節](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>如需傳送暫時失敗後重試的詳細資訊，請參閱 [本節](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### EFS匯入的變更 {#changes-introduced-by-efs}

下表顯示EFS功能所引進的KPI和傳送記錄檔狀態的變更。

**使用電子郵件回饋服務**

| 傳送程式中的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從Campaign轉送至Enhanced MTA | <ul><li>**[!UICONTROL Delivered]** 百分比從0%開始</li><li>**[!UICONTROL Bounces + errors]** 百分比從0%開始</li></ul> | 待處理 |
| 系統會從Enhanced MTA回報硬跳出的訊息 | <ul><li>無變更 **[!UICONTROL Delivered]** 百分比</li><li>**[!UICONTROL Bounces + errors]** 百分比會相應增加</li></ul> | 失敗 |
| 系統會從Enhanced MTA回報軟退信訊息 | <ul><li>無變更 **[!UICONTROL Delivered]** 百分比</li><li>**[!UICONTROL Bounces + errors]** 百分比會相應增加</li></ul> | 失敗 |
| 軟退信重試成功 | <ul><li>**[!UICONTROL Delivered]** 百分比會相應增加</li><li>**[!UICONTROL Bounces + errors]** 百分比會據此減少</li></ul> | 已傳送 |
| 軟退信重試失敗 | <ul><li> 無變更 **[!UICONTROL Delivered]** 百分比 </li><li> 無變更 **[!UICONTROL Bounces + errors]** 百分比 </li></ul> | 失敗 |

**無電子郵件回饋服務**

| 傳送程式中的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從Campaign轉送至Enhanced MTA | <ul><li>**[!UICONTROL Delivered]** 百分比從100%開始</li><li>**[!UICONTROL Bounces + errors]** 百分比從0%開始</li></ul> | 已傳送 |
| 系統會從Enhanced MTA回報硬跳出的訊息 | <ul><li>**[!UICONTROL Delivered]** 百分比會據此減少</li><li>**[!UICONTROL Bounces + errors]** 百分比會相應增加</li></ul> | 失敗 |
| 系統會從Enhanced MTA回報軟退信訊息 | <ul><li>無變更 **[!UICONTROL Delivered]** 百分比</li><li>無變更 **[!UICONTROL Bounces + errors]** 百分比</li></ul> | 已傳送 |
| 軟退信重試成功 | <ul><li>無變更 **[!UICONTROL Delivered]** 百分比</li><li>無變更 **[!UICONTROL Bounces + errors]** 百分比</li></ul> | 已傳送 |
| 軟退信重試失敗 | <ul><li>**[!UICONTROL Delivered]** 百分比會據此減少</li><li>**[!UICONTROL Bounces + errors]** 百分比會相應增加</li></ul> | 失敗 |
