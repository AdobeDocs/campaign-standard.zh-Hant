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
source-wordcount: '1442'
ht-degree: 22%

---

# 瞭解隔離管理{#understanding-quarantine-management}

## 關於隔離 {#about-quarantines}

例如信箱容量已滿或地址不存在時，您可以隔離電子郵件地址。

在任何情況下，隔離程序都符合本區段 [所述的特定規則](#conditions-for-sending-an-address-to-quarantine)。

### 透過隔離最佳化傳送 {#optimizing-your-delivery-through-quarantines}

郵件準備期間會自動排除其電子郵件地址或電話號碼處於隔離狀態的設定檔（請參閱[識別傳送的隔離地址](#identifying-quarantined-addresses-for-a-delivery)）。這會加快傳送速度，因為錯誤率對傳送速度有顯著影響。

如果無效地址的比率過高，某些網際網路存取提供者會自動將電子郵件視為垃圾郵件。因此，隔離可讓您避免被這些提供者新增到封鎖清單中。

此外，隔離有助於減少簡訊傳送成本，因為將錯誤的電話號碼排除在遞送服務之外。

如需確保傳送安全並最佳化的最佳實務，請參閱[本頁面](../../sending/using/delivery-best-practices.md)。

### 隔離與封鎖清單 {#quarantine-vs-denylist}

隔離和封鎖清單不適用於相同的物件：

* **隔離** 僅適用於 **地址** （或電話號碼等），而不是個人資料本身。 例如，被隔離的電子郵件地址的設定檔可以更新其設定檔並輸入新地址，然後再次被傳送動作設為目標。 同樣地，如果兩個設定檔碰巧擁有相同的電話號碼，則兩個設定檔在隔離該號碼時都會受到影響。

  隔離的地址或電話號碼會顯示在 [排除記錄檔](#identifying-quarantined-addresses-for-a-delivery) （針對傳遞）或在 [隔離清單](#identifying-quarantined-addresses-for-the-entire-platform) （適用於整個平台）。

* 位於 **封鎖清單**&#x200B;另一方面，將會導致 **設定檔** 不再被傳送定位，例如在針對指定頻道取消訂閱（選擇退出）後。 例如，如果電子郵件頻道封鎖清單上的設定檔有兩個電子郵件地址，則兩個地址都會從傳送中排除。 有關封鎖清單程式的詳細資訊，請參閱 [關於Campaign中的加入和退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

  您可以檢查設定檔是否位於一或多個頻道的封鎖清單中 **[!UICONTROL No longer contact (on denylist)]** 設定檔的區段 **[!UICONTROL General]** 標籤。 請參閱[本節](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

>[!NOTE]
>
>隔離包括 **在封鎖清單上** 狀態，當收件者將您的訊息回報為垃圾訊息，或回覆具有關鍵字（例如「STOP」）的SMS訊息時套用。 在這種情況下，設定檔的相關地址或電話號碼會傳送到隔離區，並包含 **[!UICONTROL On denylist]** 狀態。 有關管理STOP SMS訊息的詳細資訊，請參閱 [本節](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

&lt;! — 當使用者回覆SMS訊息時，其關鍵字如STOP以選擇退出SMS傳送，其設定檔未新增到封鎖清單，就像電子郵件選擇退出程式一樣。 相反地，設定檔的電話號碼會傳送到隔離區，並包含 **[!UICONTROL On denylist]** 狀態。 此狀態僅適用於電話號碼，表示設定檔將繼續接收電子郵件訊息。<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## 識別隔離地址 {#identifying-quarantined-addresses}

可以為特定傳送或整個平台顯示隔離的地址。

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### 識別傳送的隔離地址 {#identifying-quarantined-addresses-for-a-delivery}

在傳送準備階段期間，會將特定傳送的隔離地址中列在傳送控制面板的　**[!UICONTROL Exclusion logs]**　索引標籤中（請參閱[本區段](../../sending/using/monitoring-a-delivery.md#exclusion-logs)）。如需傳送準備的詳細資訊，請參閱[本區段](../../sending/using/preparing-the-send.md)。

![](assets/exclusion_logs.png)

### 識別整個平台的隔離地址 {#identifying-quarantined-addresses-for-the-entire-platform}

管理員可以從以下位置存取整個平台之隔離區中的電子郵件地址詳細清單： **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 功能表。

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>隔離區數量的增加是正常效果，與資料庫的「損耗」有關。 例如，如果電子郵件地址的存留期被視為三年，而收件者表格每年增加50%，則隔離區數量的增加計算如下：年度結束1：(1&#42;0.33)/(1+0.5)=22%。 年度結束2：((1.22)&#42;0.33)+0.33)/(1.5+0.75)=32.5%。

篩選器可協助您瀏覽清單。 您可以篩選地址、狀態和/或頻道。

![](assets/quarantines-filters.png)

您可以編輯或 [刪除](#removing-a-quarantined-address) 以及建立新專案。

若要編輯專案，請按一下對應的列，並視需要修改欄位。

![](assets/quarantines-edit.png)

若要手動新增專案，請使用 **[!UICONTROL Create]** 按鈕。

![](assets/quarantines-create-button.png)

定義地址（或電話號碼等） 和管道型別。 您可以設定隔離清單中的狀態和錯誤原因。 您也可以指出發生錯誤的日期、錯誤數目，並輸入錯誤文字。 如有需要，請從下拉式清單中選取最後傳送至該地址的傳遞。

![](assets/quarantines-create-last-delivery.png)

## 從隔離中移除地址 {#removing-a-quarantined-address}

### 自動更新 {#unquarantine-auto}

符合特定條件的地址會由資料庫清理工作流程自動從隔離清單中刪除。 進一步瞭解技術工作流程，請參閱 [本節](../../administration/using/technical-workflows.md#list-of-technical-workflows).

在下列情況下，地址會自動從隔離清單中移除：

* 中的地址 **[!UICONTROL Erroneous]** 成功傳送後，狀態會從隔離清單中移除。
* 中的地址 **[!UICONTROL Erroneous]** 如果最後一次軟退信發生在10天以前，則會從隔離清單中移除狀態。 如需軟性錯誤管理的詳細資訊，請參閱 [本節](#soft-error-management).
* 中的地址 **[!UICONTROL Erroneous]** 已退回的狀態 **[!UICONTROL Mailbox full]** 錯誤將在30天後從隔離清單中移除。

其狀態然後變更為 **[!UICONTROL Valid]**.

在下列情況下要執行的最大重試次數： **[!UICONTROL Erroneous]** 狀態以及重試之間的最小延遲現在取決於IP在歷史和目前指定網域的執行狀況。


>[!IMPORTANT]
>
>地址在中的收件者 **[!UICONTROL Quarantine]** 或 **[!UICONTROL Denylisted]** 即使他們收到電子郵件，狀態也不會移除。


### 手動更新 {#unquarantine-manual}

您也可以手動解除隔離地址。  若要從隔離清單手動移除地址，您可以將其從隔離清單中移除或將其狀態變更為 **[!UICONTROL Valid]**.

* 從中選擇地址 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 清單並選取 **[!UICONTROL Delete element]**.

  ![](assets/quarantine-delete-address.png)

* 選取地址並變更其 **[!UICONTROL Status]** 至 **[!UICONTROL Valid]**.

  ![](assets/quarantine-valid-status.png)


### 大量更新 {#unquarantine-bulk}

您可能需要對隔離清單執行大量更新，例如ISP中斷的情況。 在這種情況下，電子郵件會錯誤標籤為退回，因為它們無法成功傳遞給收件者。 必須從隔離清單中移除這些地址。

若要執行此動作，請建立工作流程並新增 **[!UICONTROL Query]** 活動，用於篩選掉所有受影響的收件者。 識別後，可將它們從隔離清單中移除，並包含在未來的Campaign電子郵件傳送中。

根據事件的時間範圍，以下是此查詢的建議准則。

* **錯誤文字（隔離文字）** 包含「550-5.1.1」和 **錯誤文字（隔離文字）** 包含&quot;support.ISP.com&quot;

  其中「support.ISP.com」可以是：例如「support.apple.com」或「support.google.com」

* **更新狀態(@lastModified)** YYYY/MM/DD HH當天或之後:MM:SS AM
* **更新狀態(@lastModified)** 在MM/DD/YYYY HH或之前:MM:SS PM

取得受影響的收件者清單後，請新增 **[!UICONTROL Update data]** 活動以將其電子郵件地址狀態設為 **[!UICONTROL Valid]** 因此它們會由從隔離清單中移除 **[!UICONTROL Database cleanup]** 工作流程。 您也可以從隔離表中刪除它們。

## 將地址傳送到隔離區的條件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign 會根據傳送失敗類型和錯誤訊息限定期間指派的原因來管理隔離區（請參閱[傳送失敗類型和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)及[退信限定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)）。

* **忽略錯誤**：忽略的錯誤不會傳送要隔離的地址。
* **硬錯誤**：會立即將相對應的電子郵件地址傳送至隔離區。
* **軟錯誤**：軟錯誤不會立即傳送要隔離的地址，但會增加錯誤計數器。有關詳細資訊，請參閱 [軟性錯誤管理](#soft-error-management).

  <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

如果使用者將電子郵件歸類為垃圾訊息([回饋迴路](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops))，郵件會自動重新導向至Adobe所管理的技術信箱。 之後，系統會自動將使用者的電子郵件地址傳送到狀態為　**[!UICONTROL On denylist]**　的隔離區。此狀態僅適用於地址，而且設定檔不在封鎖清單中，因此使用者會繼續收到SMS訊息和推播通知。

>[!NOTE]
>
>Adobe Campaign　中的隔離區會區分大小寫。請務必以小寫匯入電子郵件地址，如此一來，稍後就不會將它們重新設為目標。

在隔離地址清單中（請參閱[識別整個平台的隔離地址](#identifying-quarantined-addresses-for-the-entire-platform)），**[!UICONTROL Error reason]**　欄位會表示所選地址被置於隔離區的原因。

![](assets/quarantines2.png)

### 軟性錯誤管理 {#soft-error-management}

與硬錯誤相反，軟錯誤不會立即傳送要隔離的地址，而是會增加錯誤計數器。

重試將執行於 [傳遞期間](../../administration/using/configuring-email-channel.md#validity-period-parameters). 當錯誤計數器達到限制臨界值時，該地址就會進入隔離區。有關詳細資訊，請參閱 [傳送暫時失敗後重試](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

如果最後一次重大錯誤發生在10天以前，則會重新初始化錯誤計數器。 然後，地址狀態會變更為 **有效** 並且會由將其從隔離區清單中刪除 **資料庫清理** 工作流程。 (如需技術工作流程的詳細資訊，請參閱 [本節](../../administration/using/technical-workflows.md#list-of-technical-workflows).)
