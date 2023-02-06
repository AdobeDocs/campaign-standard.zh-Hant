---
title: 瞭解隔離管理
description: 瞭解如何透過隔離管理來最佳化您的傳送能力。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: eec8c66d4947e04cd0eb3dcf0f09d395d9db68b9
workflow-type: tm+mt
source-wordcount: '1365'
ht-degree: 25%

---

# 瞭解隔離管理{#understanding-quarantine-management}

## 關於隔離 {#about-quarantines}

例如信箱容量已滿或地址不存在時，您可以隔離電子郵件地址。

在任何情況下，隔離程序都符合本區段 [所述的特定規則](#conditions-for-sending-an-address-to-quarantine)。

### 透過隔離最佳化傳送 {#optimizing-your-delivery-through-quarantines}

郵件準備期間會自動排除其電子郵件地址或電話號碼處於隔離狀態的設定檔（請參閱[識別傳送的隔離地址](#identifying-quarantined-addresses-for-a-delivery)）。這會加快傳送速度，因為錯誤率對傳送速度有顯著影響。

如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。因此，隔離可讓您避免被這些提供者新增至封鎖清單。

此外，隔離有助於減少簡訊傳送成本，因為將錯誤的電話號碼排除在遞送服務之外。

如需確保傳送安全並最佳化的最佳實務，請參閱[本頁面](../../sending/using/delivery-best-practices.md)。

### 隔離與封鎖清單 {#quarantine-vs-denylist}

隔離和封鎖清單不適用於相同的物件：

* **隔離** 僅適用於 **地址** （或電話號碼等），而非設定檔本身。 例如，被隔離的電子郵件地址的設定檔可以更新其設定檔並輸入新地址，然後再次被傳送動作定位。 同樣地，如果兩個設定檔的電話號碼恰好相同，則兩者在隔離號碼時都會受到影響。

   隔離的地址或電話號碼顯示在 [排除記錄](#identifying-quarantined-addresses-for-a-delivery) （用於傳遞）或 [隔離清單](#identifying-quarantined-addresses-for-the-entire-platform) （適用於整個平台）。

* 在 **封鎖清單**，則會產生 **設定檔** 不再被傳送設為目標，例如在取消訂閱（選擇退出）後，針對指定通道。 例如，如果電子郵件通道封鎖清單上的設定檔有兩個電子郵件地址，則兩個地址都將從傳送中排除。 如需封鎖清單程式的詳細資訊，請參閱 [關於Campaign中的加入和退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

   您可以檢查設定檔是否位於封鎖清單中，以取得 **[!UICONTROL No longer contact (on denylist)]** 設定檔的區段 **[!UICONTROL General]** 標籤。 請參閱[本節](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

>[!NOTE]
>
>隔離包括 **封鎖清單上** 狀態，此狀態適用於收件者以垃圾訊息回報訊息，或回覆具有關鍵字（例如「STOP」）的SMS訊息時。 在此情況下，會將設定檔的相關地址或電話號碼傳送至隔離區，並搭配 **[!UICONTROL On denylist]** 狀態。 有關管理停止SMS消息的詳細資訊，請參閱 [本節](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

<!--When a user replies to an SMS message with a keyword such as STOP in order to opt-out from SMS deliveries, his profile is not added to the denylist like in the email opt-out process. Instead, the profile's phone number is sent to quarantine with the **[!UICONTROL On denylist]** status. This status refers to the phone number only, meaning that the profile will continue receiving email messages.<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## 識別隔離地址 {#identifying-quarantined-addresses}

可針對特定傳送或整個平台顯示隔離的地址。

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### 識別傳送的隔離地址 {#identifying-quarantined-addresses-for-a-delivery}

在傳送準備階段期間，會將特定傳送的隔離地址中列在傳送控制面板的　**[!UICONTROL Exclusion logs]**　索引標籤中（請參閱[本區段](../../sending/using/monitoring-a-delivery.md#exclusion-logs)）。如需傳送準備的詳細資訊，請參閱[本區段](../../sending/using/preparing-the-send.md)。

![](assets/exclusion_logs.png)

### 識別整個平台的隔離地址 {#identifying-quarantined-addresses-for-the-entire-platform}

管理員可以從 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 功能表。

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>隔離區數量增加是正常的效果，與資料庫的「損耗」有關。 例如，如果電子郵件地址的存留期被視為三年，而收件者表格每年增加50%，則隔離區數量的增加計算如下：年底1:(1)&#42;0.33)/(1+0.5)=22%。 2年末：(1.22&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

篩選器可協助您瀏覽清單。 您可以依地址、狀態及/或通道進行篩選。

![](assets/quarantines-filters.png)

您可以編輯或 [刪除](#removing-a-quarantined-address) 每個項目，以及建立新項目。

若要編輯項目，請按一下對應的列並視需要修改欄位。

![](assets/quarantines-edit.png)

要手動添加新條目，請使用 **[!UICONTROL Create]** 按鈕。

![](assets/quarantines-create-button.png)

定義地址（或電話號碼等） 和通道類型。 您可以設定隔離清單中的狀態和錯誤原因。 您也可以指出發生錯誤的日期、錯誤數，並輸入錯誤文字。 如有需要，請從下拉式清單中選取上次傳送至地址的傳送。

![](assets/quarantines-create-last-delivery.png)

## 從隔離區中刪除地址 {#removing-a-quarantined-address}

### 自動更新 {#unquarantine-auto}

符合特定條件的地址會由資料庫清理工作流程自動從隔離清單中刪除。 深入了解技術工作流程，請參閱 [本節](../../administration/using/technical-workflows.md#list-of-technical-workflows).

在下列情況下，地址會自動從隔離清單中刪除：

* 中的地址 **[!UICONTROL Erroneous]** 成功傳送後，狀態將從隔離清單中移除。
* 中的地址 **[!UICONTROL Erroneous]** 如果上次軟退信發生在10天前，則狀態將從隔離清單中移除。 有關軟錯誤管理的詳細資訊，請參見 [本節](#soft-error-management).
* 中的地址 **[!UICONTROL Erroneous]** 與 **[!UICONTROL Mailbox full]** 30天後，錯誤將從隔離清單中移除。

其狀態接著會變更為 **[!UICONTROL Valid]**.

要執行的最大重試次數，如果 **[!UICONTROL Erroneous]** 現在，狀態和兩次重試之間的最小延遲會根據IP在歷史和目前指定網域的執行狀況而定。


>[!IMPORTANT]
>
>地址位於 **[!UICONTROL Quarantine]** 或 **[!UICONTROL Denylisted]** 即使收到電子郵件，狀態也不會遭到移除。


### 手動更新 {#unquarantine-manual}

您也可以手動取消地址隔離。  要手動從隔離清單中刪除地址，可以從隔離清單中將其刪除，或將其狀態更改為 **[!UICONTROL Valid]**.

* 從 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 清單和選取 **[!UICONTROL Delete element]**.

   ![](assets/quarantine-delete-address.png)

* 選擇地址並更改其 **[!UICONTROL Status]** to **[!UICONTROL Valid]**.

   ![](assets/quarantine-valid-status.png)


### 大量更新 {#unquarantine-bulk}

您可能需要對隔離清單執行大量更新，例如在ISP中斷時。 在這種情況下，電子郵件會錯誤標示為退信，因為無法成功傳送給收件者。 必須從隔離清單中刪除這些地址。

若要執行此動作，請建立工作流程並新增 **[!UICONTROL Query]** 活動，以篩選所有受影響的收件者。 識別後，即可從隔離清單中移除，並納入未來的Campaign電子郵件傳送。

根據事件的時間範圍，以下是此查詢的建議准則。

* **錯誤文本（隔離文本）** 包含「550-5.1.1」和 **錯誤文本（隔離文本）** 包含&quot;support.ISP.com&quot;

   其中「support.ISP.com」可以是：&quot;support.apple.com&quot;或&quot;support.google.com&quot;，例如

* **更新狀態(@lastModified)** MM/DD/YYYY HH時或之後:MM:SS AM
* **更新狀態(@lastModified)** 在MM/DD/YYYY HH之前或之前:MM:SS PM

取得受影響收件者的清單後，請新增 **[!UICONTROL Update data]** 活動將其電子郵件地址狀態設定為 **[!UICONTROL Valid]** 以便將其從隔離清單中由 **[!UICONTROL Database cleanup]** 工作流程。 您也可以從隔離表格中刪除它們。

## 將地址傳送到隔離區的條件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign 會根據傳送失敗類型和錯誤訊息限定期間指派的原因來管理隔離區（請參閱[傳送失敗類型和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)及[退信限定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)）。

* **忽略錯誤**：忽略的錯誤不會傳送要隔離的地址。
* **硬錯誤**：會立即將相對應的電子郵件地址傳送至隔離區。
* **軟錯誤**：軟錯誤不會立即傳送要隔離的地址，但會增加錯誤計數器。有關詳細資訊，請參閱 [軟錯誤管理](#soft-error-management).

   <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

如果使用者將電子郵件歸類為垃圾訊息([反饋迴路](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops))，則訊息會自動重新導向至由Adobe管理的技術信箱。 之後，系統會自動將使用者的電子郵件地址傳送到狀態為　**[!UICONTROL On denylist]**　的隔離區。此狀態僅指位址，而設定檔不在封鎖清單上，因此使用者會繼續收到SMS訊息和推播通知。

>[!NOTE]
>
>Adobe Campaign　中的隔離區會區分大小寫。請務必以小寫匯入電子郵件地址，如此一來，稍後就不會將它們重新設為目標。

在隔離地址清單中（請參閱[識別整個平台的隔離地址](#identifying-quarantined-addresses-for-the-entire-platform)），**[!UICONTROL Error reason]**　欄位會表示所選地址被置於隔離區的原因。

![](assets/quarantines2.png)

### 軟錯誤管理 {#soft-error-management}

與硬錯誤不同，軟錯誤不會立即傳送要隔離的地址，而會增加錯誤計數器。

將在 [傳遞期間](../../administration/using/configuring-email-channel.md#validity-period-parameters). 當錯誤計數器達到限制臨界值時，該地址就會進入隔離區。有關詳細資訊，請參閱 [傳送暫時失敗後重試](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

如果上次出現重大錯誤超過10天，則重新初始化錯誤計數器。 然後地址狀態變更為 **有效** 而且會由 **資料庫清理** 工作流程。 (如需技術工作流程的詳細資訊，請參閱 [本節](../../administration/using/technical-workflows.md#list-of-technical-workflows).)
