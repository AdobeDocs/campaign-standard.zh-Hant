---
solution: Campaign Standard
product: campaign
title: 確認傳送
description: 瞭解如何完成訊息準備。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: 效能監控
role: User
level: Intermediate
exl-id: 0a0fe969-cdfd-4b0c-a746-081038424d86
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 17%

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

1. 正在發送消息，請稍候。 **[!UICONTROL Deployment]** 區塊會顯示傳送的進度。

>[!NOTE]
>
>如果已排程訊息，則會在達到傳送時間時傳送訊息。 如需排程訊息的詳細資訊，請參閱[本區段](../../sending/using/about-scheduling-messages.md)。

如果您使用不含彙總期間的循環傳送，則可在傳送傳遞前要求確認。設定訊息時，請開啟傳送控制面板的&#x200B;**[!UICONTROL Schedule]**&#x200B;區塊並啟用專用選項。

![](assets/confirmation_recurring_deliveries.png)

## 了解訊息指標 {#message-indicators}

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

如果KPI更新時間太長或未反映傳送記錄檔的結果，請按一下&#x200B;**[!UICONTROL Deployment]**&#x200B;視窗中的&#x200B;**[!UICONTROL Compute stats]**&#x200B;按鈕。

![](assets/sending_delivery7.png)

您可以在其中一個目標設定檔的歷史記錄中檢視訊息。 請參閱[整合式客戶設定檔](../../audiences/using/integrated-customer-profile.md)。

傳送訊息後，您可以追蹤其收件者的行為，並監控訊息以評估其影響。 如需詳細資訊，請參閱下列區段。

* [追蹤訊息](../../sending/using/tracking-messages.md)
* [監視傳遞](../../sending/using/monitoring-a-delivery.md)

### 傳送成功報表 {#delivered-status-report}

>[!NOTE]
>
>本節內容僅適用於電子郵件通道。

在每封電子郵件的&#x200B;**[!UICONTROL Summary]**&#x200B;檢視中，**[!UICONTROL Delivered]**&#x200B;百分比從100%開始，然後隨著軟退信和硬退信回報<!--from the Enhanced MTA to Campaign-->，在傳送[有效期](../../administration/using/configuring-email-channel.md#validity-period-parameters)期間逐步下降。

事實上，當所有訊息從Campaign成功中繼至Enhanced MTA（訊息傳輸代理）時，在[傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs)中會顯示為&#x200B;**[!UICONTROL Sent]**。 除非或直到該訊息的[bounce](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)從Enhanced MTA傳回至Campaign，否則它們會維持該狀態。

當從Enhanced MTA返回硬跳報文時，其狀態從&#x200B;**[!UICONTROL Sent]**&#x200B;變更為&#x200B;**[!UICONTROL Failed]**，並相應地降低&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比。

從Enhanced MTA回報軟彈跳訊息時，仍會顯示為&#x200B;**[!UICONTROL Sent]**，且&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比尚未更新。 然後，在傳送有效期間內，軟彈跳消息將[retried](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure):

* 如果在有效期結束前重試成功，則消息狀態將保持為&#x200B;**[!UICONTROL Sent]**，而&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比將保持不變。

* 否則，狀態變為&#x200B;**[!UICONTROL Failed]**，並相應地降低&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比。

因此，您必須等到有效期結束，才能看到最終的&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比，以及最終的&#x200B;**[!UICONTROL Sent]**&#x200B;和&#x200B;**[!UICONTROL Failed]**&#x200B;訊息數。

### 電子郵件意見回饋服務（測試版） {#email-feedback-service}

利用電子郵件反饋服務(EFS)功能，可以準確報告每封電子郵件的狀態，因為反饋是直接從增強MTA（郵件傳輸代理）中捕獲的。

>[!IMPORTANT]
>
>電子郵件意見回饋服務目前提供測試版功能。

傳送開始後，當訊息從促銷活動成功中繼至增強MTA時，**[!UICONTROL Delivered]**&#x200B;百分比沒有變更。

![](assets/efs-sending.png)

傳送記錄會顯示每個目標位址的&#x200B;**[!UICONTROL Pending]**&#x200B;狀態。

![](assets/efs-pending.png)

當從Enhanced MTA即時回報傳送至目標設定檔的訊息時，傳送記錄會顯示成功接收訊息之每個位址的&#x200B;**[!UICONTROL Sent]**&#x200B;狀態。 每次成功傳送時，**[!UICONTROL Delivered]**&#x200B;百分比會隨之增加。

當從Enhanced MTA回報硬彈回訊息時，其記錄狀態會從&#x200B;**[!UICONTROL Pending]**&#x200B;變更為&#x200B;**[!UICONTROL Failed]**，而&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;百分比會隨之增加。

當從Enhanced MTA回報軟彈跳消息時，其日誌狀態也從&#x200B;**[!UICONTROL Pending]**&#x200B;變更為&#x200B;**[!UICONTROL Failed]**，並相應地增加&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;百分比。 **[!UICONTROL Delivered]**&#x200B;百分比保持不變。 然後，在傳送[有效期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)期間重試軟跳出消息：

* 如果在有效期結束前重試成功，則消息狀態將變為&#x200B;**[!UICONTROL Sent]**，並相應地增加&#x200B;**[!UICONTROL Delivered]**&#x200B;百分比。

* 否則，狀態會維持為&#x200B;**[!UICONTROL Failed]**。 **[!UICONTROL Delivered]**&#x200B;和&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;百分比維持不變。

>[!NOTE]
>
>如需硬跳出和軟跳出的詳細資訊，請參閱[此區段](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。
>
>如需傳送暫時失敗後重試的詳細資訊，請參閱[此區段](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### EFS引入的更改 {#changes-introduced-by-efs}

下表顯示了EFS功能引入的KPI和發送日誌狀態的更改。

**使用電子郵件反饋服務**

| 傳送程式的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從促銷活動中繼至增強MTA | <ul><li>**[!UICONTROL Delivered]** 百分比從0%開始</li><li>**[!UICONTROL Bounces + errors]** 百分比從0%開始</li></ul> | 待定 |
| 從Enhanced MTA返回硬跳報文 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比中無變化</li><li>**[!UICONTROL Bounces + errors]** 百分比相應增加</li></ul> | 失敗 |
| 從Enhanced MTA返回軟彈跳報文 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比中無變化</li><li>**[!UICONTROL Bounces + errors]** 百分比相應增加</li></ul> | 失敗 |
| 軟跳出消息重試成功 | <ul><li>**[!UICONTROL Delivered]** 百分比相應增加</li><li>**[!UICONTROL Bounces + errors]** 百分比相應地減少</li></ul> | 已傳送 |
| 軟跳出訊息重試失敗 | <ul><li> **[!UICONTROL Delivered]**&#x200B;百分比中無變化 </li><li> **[!UICONTROL Bounces + errors]**&#x200B;百分比中無變化 </li></ul> | 失敗 |

**不提供電子郵件反饋服務**

| 傳送程式的步驟 | KPI摘要 | 傳送記錄檔狀態 |
|--- |--- |--- |
| 訊息已成功從促銷活動中繼至增強MTA | <ul><li>**[!UICONTROL Delivered]** 百分比從100%開始</li><li>**[!UICONTROL Bounces + errors]** 百分比從0%開始</li></ul> | 已傳送 |
| 從Enhanced MTA返回硬跳報文 | <ul><li>**[!UICONTROL Delivered]** 百分比相應地減少</li><li>**[!UICONTROL Bounces + errors]** 百分比相應增加</li></ul> | 失敗 |
| 從Enhanced MTA返回軟彈跳報文 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比中無變化</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比中無變化</li></ul> | 已傳送 |
| 軟跳出消息重試成功 | <ul><li>**[!UICONTROL Delivered]**&#x200B;百分比中無變化</li><li>**[!UICONTROL Bounces + errors]**&#x200B;百分比中無變化</li></ul> | 已傳送 |
| 軟跳出訊息重試失敗 | <ul><li>**[!UICONTROL Delivered]** 百分比相應地減少</li><li>**[!UICONTROL Bounces + errors]** 百分比相應增加</li></ul> | 失敗 |
