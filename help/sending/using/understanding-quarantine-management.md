---
title: 瞭解隔離管理
description: 瞭解如何透過隔離管理來最佳化您的傳送能力。
page-status-flag: 從未激活
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 發送
content-type: 參考
topic-tags: 監控消息
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 瞭解隔離管理{#understanding-quarantine-management}

## 關於隔離 {#about-quarantines}

可以隔離電子郵件地址或電話號碼，例如當郵箱已滿或地址不存在時。

在任何情況下，隔離程式都符合本節所述的特定 [規則](#conditions-for-sending-an-address-to-quarantine)。

### 透過隔離最佳化傳送 {#optimizing-your-delivery-through-quarantines}

郵件準備期間會自動排除其電子郵件地址或電話號碼處於隔離狀態的配置檔案(請參 [閱標識傳送的隔離地址](#identifying-quarantined-addresses-for-a-delivery))。 這會加快傳送速度，因為錯誤率對傳送速度有顯著影響。

如果無效地址的比率過高，某些Internet訪問提供商會自動將電子郵件視為垃圾郵件。 因此，隔離可讓您避免這些提供者列入黑名單。

此外，隔離有助於減少簡訊發送成本，因為將錯誤的電話號碼排除在遞送服務之外。

如需確保傳送安全並最佳化的最佳實務，請參閱 [本頁](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html)。

### 隔離與黑名單 {#quarantine-vs-blacklisting}

**隔離** (Quarantine)僅適用於地址，而不適用於配置檔案本身。 這意味著，如果兩個配置檔案具有相同的電子郵件地址，則兩個配置檔案在隔離地址時都會受到影響。

同樣地，被隔離的電子郵件地址的配置檔案可以更新其配置檔案並輸入新地址，然後再次被傳送操作定位。

**而黑名單**，則會導致描述檔不再被任何傳送鎖定，例如在取消訂閱（選擇退出）後。 如需黑名單程式的詳細資訊，請參閱「在促 [銷活動中管理黑名單](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)」。

>[!NOTE]
>
>當使用者回覆SMS訊息時，其關鍵字如「STOP」，以選擇退出SMS傳送時，其個人檔案不會像電子郵件選擇退出程式一樣列入黑名單。 配置式電話號碼會以狀態發送到隔離 **[!UICONTROL Blacklisted]** 區。 此狀態僅指電話號碼，設定檔未列入黑名單，因此使用者會繼續收到電子郵件訊息。 如需詳細資訊，請參閱[本小節](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。

## 標識隔離地址 {#identifying-quarantined-addresses}

可以為特定傳送或整個平台列出隔離的地址。

>[!NOTE]
>
>如果您需要從隔離中刪除地址，請與技術管理員聯繫。

### 標識傳送的隔離地址 {#identifying-quarantined-addresses-for-a-delivery}

特定傳送的隔離地址在傳送準備階段中列於傳送控制面板 **[!UICONTROL Exclusion logs]** 的標籤中(請參閱 [本節](../../sending/using/monitoring-a-delivery.md#exclusion-logs))。 For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### 識別整個平台的隔離地址 {#identifying-quarantined-addresses-for-the-entire-platform}

管理員可以從菜單中列出隔離整個平台的地 **[!UICONTROL Administration > Channels > Quarantines > Addresses]** 址。

>[!NOTE]
>
>此功能表列出電子郵件、 **簡訊和推播通**&#x200B;知通 **道的隔離元素****** 。

![](assets/quarantines1.png)

>[!NOTE]
>
>檢疫數量的增加是正常的，與資料庫的「磨損」有關。 例如，如果電子郵件地址的存留期被視為三年，而收件者表每年增加50%，則隔離的增加可以計算如下：年終1:(1*0.33)/(1+0.5)=22%。 年終2:((1.22*0.33)+0.33)/(1.5+0.75)=32.5%。

## 將地址發送到隔離的條件 {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign會根據傳送失敗類型和錯誤訊息限定期間指派的原因來管理隔離(請參閱傳送失敗類型 [和原因](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) , [以及彈回郵件限定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification))。

* **忽略錯誤**:忽略的錯誤不會傳送要隔離的地址。
* **硬錯誤**:對應的電子郵件地址會立即傳送至隔離區。
* **軟錯誤**:軟錯誤不會立即發送要隔離的地址，但會增加錯誤計數器。 當錯誤計數器達到限制閾值時，地址將進入隔離。 在預設設定中，臨界值會設定為5個錯誤，其中2個錯誤若相隔至少24小時，即顯著。 地址在第六個錯誤時被置於隔離中。 可以修改錯誤計數器閾值。 For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   重試後傳送成功時，重新初始化隔離前的地址的錯誤計數器。 地址狀態在工作 **[!UICONTROL Valid]** 流兩天後變為，並從隔離清單中刪除該地 **[!UICONTROL Database cleanup]** 址。

如果使用者將電子郵件歸為垃圾訊息(**回饋迴路**)，則訊息會自動重新導向至由Campaign管理的技術郵箱。 然後，系統會自動將用戶的電子郵件地址發送到具有狀態的隔 **[!UICONTROL Blacklisted]** 離區。 此狀態僅指位址，描述檔未列入黑名單，因此使用者會繼續收到SMS訊息和推播通知。

>[!NOTE]
Adobe Campaign中的隔離區區分大小寫。 請務必以小寫匯入電子郵件地址，以便日後不會重新定位。

在隔離地址清單中(請參 [閱標識整個平台的隔離地址](#identifying-quarantined-addresses-for-the-entire-platform))，該字 **[!UICONTROL Error reason]** 段指明選定地址被置於隔離中的原因。

![](assets/quarantines2.png)

