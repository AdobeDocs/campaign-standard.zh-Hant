---
solution: Campaign Standard
product: campaign
title: 瞭解隔離管理
description: 瞭解如何透過隔離管理來最佳化您的傳送能力。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: 084838ff5ff369aaaa7715f5bec87a5133093750
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 30%

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

* **** 隔離僅適用於 **地址** （或電話號碼等），不適用於設定檔本身。例如，被隔離的電子郵件地址的設定檔可以更新其設定檔並輸入新地址，然後再次被傳送動作定位。 同樣地，如果兩個設定檔的電話號碼恰好相同，則兩者在隔離號碼時都會受到影響。

   隔離的地址或電話號碼顯示在[排除日誌](identifying-quarantined-addresses-for-a-delivery)中（針對傳送），或顯示在[隔離清單](#identifying-quarantined-addresses-for-the-entire-platform)中（針對整個平台）。

* 另一方面，位於&#x200B;**denylist**&#x200B;時，會導致指定通道的&#x200B;**profile**&#x200B;不再由傳送定位，例如在取消訂閱（選擇退出）後。 例如，如果電子郵件通道封鎖清單上的設定檔有兩個電子郵件地址，則兩個地址都將從傳送中排除。 如需封鎖清單程式的詳細資訊，請參閱[關於Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)中的選擇加入和選擇退出。

   您可以在設定檔&#x200B;**[!UICONTROL General]**&#x200B;標籤的&#x200B;**[!UICONTROL No longer contact (on denylist)]**&#x200B;區段中，檢查設定檔是否位於封鎖清單中，以查看一或多個管道。 請參閱[本節](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

>[!NOTE]
>
>隔離包含&#x200B;**On denylist**&#x200B;狀態，當收件者將您的郵件報告為垃圾郵件或回覆具有關鍵字（如「STOP」）的SMS郵件時，此狀態適用。 在這種情況下，會將設定檔的相關地址或電話號碼發送到狀態為&#x200B;**[!UICONTROL On denylist]**&#x200B;的隔離區。 有關管理STOP SMS消息的詳細資訊，請參閱[此部分](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。

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

管理員可以從&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**&#x200B;功能表存取整個平台之隔離區中的電子郵件地址詳細清單。

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>隔離區數量增加是正常的效果，與資料庫的「損耗」有關。 例如，如果電子郵件地址的存留期被視為三年，而收件者表格每年增加　50%，則隔離區數量的增加計算如下：年度結束 1：(1*0.33)/(1+0.5)=22%。年度結束 2：((1.22*0.33)+0.33)/(1.5+0.75)=32.5%。

篩選器可協助您瀏覽清單。 您可以依地址、狀態及/或通道進行篩選。

![](assets/quarantines-filters.png)

您可以編輯或刪除每個條目，並建立新條目。[](#removing-a-quarantined-address)

若要編輯項目，請按一下對應的列並視需要修改欄位。

![](assets/quarantines-edit.png)

要手動添加新條目，請使用&#x200B;**[!UICONTROL Create]**&#x200B;按鈕。

![](assets/quarantines-create-button.png)

定義地址（或電話號碼等） 和通道類型。 您可以設定隔離清單中的狀態和錯誤原因。 您也可以指出發生錯誤的日期、錯誤數，並輸入錯誤文字。 如有需要，請從下拉式清單中選取上次傳送至地址的傳送。

![](assets/quarantines-create-last-delivery.png)

### 移除隔離的地址 {#removing-a-quarantined-address}

如有需要，您可以手動從隔離清單中移除地址。 此外，符合特定條件的地址還會由&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流程自動從隔離清單中刪除。 （如需技術工作流程的詳細資訊，請參閱[本區段](../../administration/using/technical-workflows.md#list-of-technical-workflows)。）

要從隔離清單中手動刪除地址，請執行以下操作之一。

>[!IMPORTANT]
從隔離區手動刪除電子郵件地址意味著您將重新開始傳送至此地址。 因此，這可能會對您的傳遞能力和IP信譽造成嚴重影響，最終可能導致您的IP位址或傳送網域遭到封鎖。 考慮從隔離區中移除任何地址時，請格外小心。 如有疑問，請聯絡傳遞能力專家。

* 從&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**&#x200B;清單中選擇地址，然後選擇&#x200B;**[!UICONTROL Delete element]**。

   ![](assets/quarantine-delete-address.png)

* 選擇地址，並將其&#x200B;**[!UICONTROL Status]**&#x200B;更改為&#x200B;**[!UICONTROL Valid]**。

   ![](assets/quarantine-valid-status.png)

   您也可以將其狀態變更為&#x200B;**[!UICONTROL On allowlist]**。 在此情況下，地址仍保留在隔離清單中，但將系統地定位該地址，即使遇到錯誤亦然。

在下列情況下，地址會自動從隔離清單中刪除：

* 成功傳送後，處於&#x200B;**[!UICONTROL Erroneous]**&#x200B;狀態的地址將從隔離清單中移除。
* 如果上次軟退信發生在10天前，則處於&#x200B;**[!UICONTROL Erroneous]**&#x200B;狀態的地址將從隔離清單中刪除。 有關軟錯誤管理的詳細資訊，請參閱[此部分](#soft-error-management)。
* 30天後，處於&#x200B;**[!UICONTROL Erroneous]**&#x200B;狀態且因&#x200B;**[!UICONTROL Mailbox full]**&#x200B;錯誤退回的地址將從隔離清單中移除。

其狀態隨後變更為&#x200B;**[!UICONTROL Valid]**。

>[!IMPORTANT]
即使收到電子郵件，狀態為&#x200B;**[!UICONTROL Quarantine]**&#x200B;或&#x200B;**[!UICONTROL On denylist]**&#x200B;的收件者也不會自動移除。

在&#x200B;**[!UICONTROL Erroneous]**&#x200B;狀態下要執行的最大重試次數和兩次重試之間的最小延遲現在取決於IP在歷史和當前指定域的執行狀況。

## 將地址傳送到隔離區的條件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign 會根據傳送失敗類型和錯誤訊息限定期間指派的原因來管理隔離區（請參閱[傳送失敗類型和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)及[退信限定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)）。

* **忽略錯誤**：忽略的錯誤不會傳送要隔離的地址。
* **硬錯誤**：會立即將相對應的電子郵件地址傳送至隔離區。
* **軟錯誤**：軟錯誤不會立即傳送要隔離的地址，但會增加錯誤計數器。有關詳細資訊，請參閱[軟錯誤管理](#soft-error-management)。

   <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

如果用戶將電子郵件歸類為垃圾郵件（[反饋循環](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)），則該郵件會自動重定向到由Adobe管理的技術郵箱。 之後，系統會自動將使用者的電子郵件地址傳送到狀態為　**[!UICONTROL On denylist]**　的隔離區。此狀態僅指位址，而設定檔不在封鎖清單上，因此使用者會繼續收到SMS訊息和推播通知。

>[!NOTE]
Adobe Campaign　中的隔離區會區分大小寫。請務必以小寫匯入電子郵件地址，如此一來，稍後就不會將它們重新設為目標。

在隔離地址清單中（請參閱[識別整個平台的隔離地址](#identifying-quarantined-addresses-for-the-entire-platform)），**[!UICONTROL Error reason]**　欄位會表示所選地址被置於隔離區的原因。

![](assets/quarantines2.png)

### 軟錯誤管理 {#soft-error-management}

與硬錯誤不同，軟錯誤不會立即傳送要隔離的地址，而會增加錯誤計數器。

在[傳送期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)將執行重試。 當錯誤計數器達到限制臨界值時，該地址就會進入隔離區。如需詳細資訊，請參閱[傳送暫時失敗後重試](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)。

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

如果上次出現重大錯誤超過10天，則重新初始化錯誤計數器。 然後，地址狀態將更改為&#x200B;**Valid**，並且該地址將通過&#x200B;**Database cleanup**&#x200B;工作流從隔離清單中刪除。 （如需技術工作流程的詳細資訊，請參閱[本區段](../../administration/using/technical-workflows.md#list-of-technical-workflows)。）
