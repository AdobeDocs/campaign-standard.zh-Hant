---
title: 瞭解隔離管理
description: 瞭解如何透過隔離管理來最佳化您的傳送能力。
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 121ec37cef6193d3a7085b6d0296b6a2e7cafa06
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 81%

---


# 瞭解隔離管理{#understanding-quarantine-management}

## 關於隔離 {#about-quarantines}

例如信箱容量已滿或地址不存在時，您可以隔離電子郵件地址。

在任何情況下，隔離程序都符合本區段 [所述的特定規則](#conditions-for-sending-an-address-to-quarantine)。

### 透過隔離最佳化傳送 {#optimizing-your-delivery-through-quarantines}

郵件準備期間會自動排除其電子郵件地址或電話號碼處於隔離狀態的設定檔（請參閱[識別傳送的隔離地址](#identifying-quarantined-addresses-for-a-delivery)）。這會加快傳送速度，因為錯誤率對傳送速度有顯著影響。

如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。因此，隔離可讓您避免被這些提供者添加到塊清單中。

此外，隔離有助於減少簡訊傳送成本，因為將錯誤的電話號碼排除在遞送服務之外。

如需確保傳送安全並最佳化的最佳實務，請參閱[本頁面](https://helpx.adobe.com/tw/campaign/kb/delivery-best-practices.html)。

### 隔離與塊清單 {#quarantine-vs-block-list}

**隔離** (Quarantine)　僅適用於地址，而不適用於設定檔本身。這代表如果兩個設定檔具有相同的電子郵件地址，則兩個設定檔在隔離地址時都會受到影響。

同樣地，被隔離的電子郵件地址的設定檔可以更新其設定檔並輸入新地址，然後再次被傳送動作設為目標。

Being on the **block list**, on the other hand, will result in the profile no longer being targeted by any delivery, for example after an unsubscription (opt-out). 如需區塊清單程式的詳細資訊，請參 [閱關於促銷活動中的選擇加入和選擇退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

>[!NOTE]
>
>當使用者回覆SMS訊息時，其關鍵字如「STOP」，以選擇退出SMS傳送時，其描述檔不會像電子郵件選擇退出程式一樣新增至區塊清單。 會將設定檔電話號碼傳送到隔離區，且狀態為　**[!UICONTROL On block list]**。此狀態僅指電話號碼，設定檔不在區塊清單中，因此使用者會繼續收到電子郵件訊息。 如需詳細資訊，請參閱[本區段](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。

## 識別隔離地址 {#identifying-quarantined-addresses}

可以為特定傳送或整個平台列出隔離的地址。

>[!NOTE]
>
>如果您需要從隔離區中刪除地址，請與技術管理員聯絡。

### 識別傳送的隔離地址 {#identifying-quarantined-addresses-for-a-delivery}

在傳送準備階段期間，會將特定傳送的隔離地址中列在傳送控制面板的　**[!UICONTROL Exclusion logs]**　索引標籤中（請參閱[本區段](../../sending/using/monitoring-a-delivery.md#exclusion-logs)）。如需傳送準備的詳細資訊，請參閱[本區段](../../sending/using/preparing-the-send.md)。

![](assets/exclusion_logs.png)

### 識別整個平台的隔離地址 {#identifying-quarantined-addresses-for-the-entire-platform}

管理員可以從 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 功能表列出整個平台之隔離區中的地址。

>[!NOTE]
>
>此功能表會列出&#x200B;**電子郵件**、**簡訊**&#x200B;和&#x200B;**推播通知**&#x200B;通道的隔離元素。

![](assets/quarantines1.png)

>[!NOTE]
>
>隔離區數量增加是正常效應，與資料庫的「損耗」有關。例如，如果電子郵件地址的存留期被視為三年，而收件者表格每年增加　50%，則隔離區數量的增加計算如下：年度結束 1：(1*0.33)/(1+0.5)=22%。年度結束 2：((1.22*0.33)+0.33)/(1.5+0.75)=32.5%。

## 將地址傳送到隔離區的條件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign 會根據傳送失敗類型和錯誤訊息限定期間指派的原因來管理隔離區（請參閱[傳送失敗類型和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)及[退信限定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)）。

* **忽略錯誤**：忽略的錯誤不會傳送要隔離的地址。
* **硬錯誤**：會立即將相對應的電子郵件地址傳送至隔離區。
* **軟錯誤**：軟錯誤不會立即傳送要隔離的地址，但會增加錯誤計數器。當錯誤計數器達到限制臨界值時，該地址就會進入隔離區。在預設設定中，臨界值會設定為　5　個錯誤，其中　2　個錯誤若相隔至少　24　小時，即為顯著錯誤。會將地址放置到隔離區的第五個錯誤。可以修改錯誤計數器臨界值。如需詳細資訊，請參閱此[頁面](../../administration/using/configuring-email-channel.md#email-channel-parameters)。

   重試之後傳送成功時，重新初始化隔離前地址的錯誤計數器。地址狀態變更為　**[!UICONTROL Valid]**，而且會在兩天之後，由　**[!UICONTROL Database cleanup]**　工作流程從隔離區清單中刪除該地址。

如果使用者將電子郵件歸類為垃圾訊息（**回饋迴路**），則訊息會自動重新導向至由　Campaign　管理的技術信箱。之後，系統會自動將使用者的電子郵件地址傳送到狀態為　**[!UICONTROL On block list]**　的隔離區。此狀態僅指地址，描述檔不在區塊清單中，因此使用者會繼續接收SMS訊息和推播通知。

>[!NOTE]
Adobe Campaign　中的隔離區會區分大小寫。請務必以小寫匯入電子郵件地址，如此一來，稍後就不會將它們重新設為目標。

在隔離地址清單中（請參閱[識別整個平台的隔離地址](#identifying-quarantined-addresses-for-the-entire-platform)），**[!UICONTROL Error reason]**　欄位會表示所選地址被置於隔離區的原因。

![](assets/quarantines2.png)

