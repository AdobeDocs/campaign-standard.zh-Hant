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
source-git-commit: 058c59136c28e7fce2a79686919f900f410e324a
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 16%

---

# 確認傳送{#confirming-the-send}

在您j完成訊息準備並執行核准步驟後，即可傳送訊息。如需訊息準備的詳細資訊，請參閱[準備傳送](../../sending/using/preparing-the-send.md)。

只有具有&#x200B;**[!UICONTROL Start deliveries]**&#x200B;角色的使用者才能確認傳送。 如需詳細資訊，請參閱[角色清單](../../administration/using/list-of-roles.md)區段。

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## 傳送訊息 {#sending-message}

準備完成後，請依照下列步驟傳送訊息。

1. 按一下訊息動作列中的&#x200B;**[!UICONTROL Confirm send]**&#x200B;按鈕。

   ![](assets/confirm_delivery.png)

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;按鈕以完成傳送。

   ![](assets/confirm_delivery1.png)

1. 正在傳送訊息，請稍候。 **[!UICONTROL Deployment]** 區塊會顯示傳送的進度。

>[!NOTE]
>
>如果已排程訊息，則會在達到傳送時間時傳送訊息。 如需排程訊息的詳細資訊，請參閱[本區段](../../sending/using/about-scheduling-messages.md)。

如果您使用不含彙總期間的循環傳送，則可在傳送傳遞前要求確認。設定訊息時，請開啟傳遞控制面板的&#x200B;**[!UICONTROL Schedule]**&#x200B;區塊，並啟用專用選項。

![](assets/confirmation_recurring_deliveries.png)

## 瞭解訊息指標 {#message-indicators}

>[!NOTE]
>
> **部署儀表板**&#x200B;提供快速參考資料，這些資料可能與動態報告中的數字不符。 為獲得精確且可靠的資訊，建議您使用動態報告作為真相來源。 [了解更多](../../reporting/using/get-started-reporting.md)

將訊息傳送給連絡人之後，**[!UICONTROL Deployment]**&#x200B;區域會顯示您的KPI （關鍵績效指標）資料，包括：

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

如果KPI更新時間太長或未反映傳送記錄檔的結果，請按一下&#x200B;**[!UICONTROL Deployment]**&#x200B;視窗中的&#x200B;**[!UICONTROL Compute stats]**&#x200B;按鈕。

![](assets/sending_delivery7.png)

可以在其中一個目標設定檔的歷史記錄中檢視訊息。 請參閱[整合式客戶輪廓](../../audiences/using/integrated-customer-profile.md)。

傳送訊息後，您可以追蹤其收件者的行為並監控該訊息，以評估其影響。 如需詳細資訊，請參閱下列區段。

* [追蹤訊息](../../sending/using/tracking-messages.md)
* [監視傳遞](../../sending/using/monitoring-a-delivery.md)

### 傳遞成功報告 {#delivered-status-report}

>[!NOTE]
>
>本節內容僅適用於電子郵件頻道。

在每封電子郵件的&#x200B;**[!UICONTROL Summary]**&#x200B;檢視中，**[!UICONTROL Delivered]**&#x200B;百分比從100%開始，然後在整個傳遞[有效期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)逐步下降，因為軟跳出和硬跳出會被回報回<!--from the Enhanced MTA to Campaign-->。

事實上，一旦訊息從Campaign成功轉送至增強型MTA （訊息傳輸代理程式），所有訊息在[傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs)中都會顯示為&#x200B;**[!UICONTROL Sent]**。 除非或直到該訊息的[跳出](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)從Enhanced MTA傳回Campaign，否則它們會維持該狀態。

當硬退信從Enhanced MTA回傳時，其狀態會從&#x200B;**[!UICONTROL Sent]**&#x200B;變更為&#x200B;**[!UICONTROL Failed]**，而&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比會因此減少。

當從Enhanced MTA回報軟退信時，訊息仍顯示為&#x200B;**[!UICONTROL Sent]**，且&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比尚未更新。 然後，軟退信會在整個傳遞有效期內重試[](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)：

* 如果在有效期間結束前重試成功，則訊息狀態會維持為&#x200B;**[!UICONTROL Sent]**，**[!UICONTROL Delivered]**&#x200B;百分比會維持不變。

* 否則，狀態會變更為&#x200B;**[!UICONTROL Failed]**，而&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比會相應減少。

因此，您必須等到有效期間結束才能檢視最終的&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比，以及最終的&#x200B;**[!UICONTROL Sent]**&#x200B;和&#x200B;**[!UICONTROL Failed]**&#x200B;則訊息數目。

### 電子郵件回饋服務（測試版） {#email-feedback-service}

使用電子郵件回饋服務(EFS)功能，可準確報告每封電子郵件的狀態，因為回饋會直接從Enhanced MTA （訊息傳輸代理程式）擷取。

>[!IMPORTANT]
>
>電子郵件回饋服務目前是以Beta版形式提供。

開始傳遞後，當訊息成功從Campaign轉送至Enhanced MTA時，**[!UICONTROL Delivered]**&#x200B;百分比沒有變更。

![](assets/efs-sending.png)

傳遞記錄顯示每個目標地址的&#x200B;**[!UICONTROL Pending]**&#x200B;狀態。

![](assets/efs-pending.png)

當從Enhanced MTA即時回報訊息傳送至目標設定檔時，傳送記錄會顯示成功收到訊息之每個位址的&#x200B;**[!UICONTROL Sent]**&#x200B;狀態。 每次成功傳遞時，**[!UICONTROL Delivered]**&#x200B;百分比都會相應增加。

當硬退信從Enhanced MTA回傳時，其記錄狀態會從&#x200B;**[!UICONTROL Pending]**&#x200B;變更為&#x200B;**[!UICONTROL Failed]**，而&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;百分比會相應增加。

當從Enhanced MTA回報軟退信時，其記錄狀態也會從&#x200B;**[!UICONTROL Pending]**&#x200B;變更為&#x200B;**[!UICONTROL Failed]**，而&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;百分比也會相應增加。 **[!UICONTROL Delivered]**&#x200B;百分比保持不變。 然後，會在整個傳遞[有效期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)重試軟退信訊息：

* 如果在有效期間結束前重試成功，則訊息狀態會變更為&#x200B;**[!UICONTROL Sent]**，而&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比會相應增加。

* 否則，狀態會維持為&#x200B;**[!UICONTROL Failed]**。 **[!UICONTROL Delivered]**&#x200B;和&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;百分比保持不變。

>[!NOTE]
>
>如需硬退信和軟退信的詳細資訊，請參閱[本節](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。
>
>如需傳送暫時失敗後重試的詳細資訊，請參閱[本節](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### EFS匯入的變更 {#changes-introduced-by-efs}

下表顯示EFS功能所引進的KPI和傳送記錄檔狀態的變更。

**電子郵件回饋服務**

| 傳送程式中的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從Campaign轉送至增強型MTA | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比從0%開始</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比從0%開始</li></ul> | 待處理 |
| 系統會從Enhanced MTA回報硬跳出訊息 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比沒有變更</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比會相應增加</li></ul> | 失敗 |
| 系統會從Enhanced MTA回報軟退信訊息 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比沒有變更</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比會相應增加</li></ul> | 失敗 |
| 軟退信重試成功 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比會相應增加</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比會相應減少</li></ul> | 已傳送 |
| 軟退信重試失敗 | <ul><li> **[!UICONTROL Delivered]**&#x200B;百分比沒有變更 </li><li> **[!UICONTROL Bounces + errors]**&#x200B;百分比沒有變更 </li></ul> | 失敗 |

**沒有電子郵件回饋服務**

| 傳送程式中的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從Campaign轉送至增強型MTA | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比從100%開始</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比從0%開始</li></ul> | 已傳送 |
| 系統會從Enhanced MTA回報硬跳出訊息 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比會相應減少</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比會相應增加</li></ul> | 失敗 |
| 系統會從Enhanced MTA回報軟退信訊息 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比沒有變更</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比沒有變更</li></ul> | 已傳送 |
| 軟退信重試成功 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比沒有變更</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比沒有變更</li></ul> | 已傳送 |
| 軟退信重試失敗 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比會相應減少</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比會相應增加</li></ul> | 失敗 |
