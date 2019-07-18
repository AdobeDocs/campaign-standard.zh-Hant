---
title: 瞭解隔離管理
seo-title: 瞭解隔離管理
description: 瞭解隔離管理
seo-description: 瞭解如何透過隔離管理最佳化您的傳遞能力。
page-status-flag: 從未啓動
uuid: 3c287865-1ada-4351-b205-51807ff9 f7
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: 監控訊息
discoiquuid: de3a50b6-ea8 f-4521-996b-c49 cc1 f3 c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5b3ea982f08e1198e8c88f78a5faf8a80b935db4

---


# Understanding quarantine management{#understanding-quarantine-management}

## About quarantines {#about-quarantines}

電子郵件地址或電話號碼可能會遭到隔離，例如，當mailbox完整或位址不存在時。

In any case, the quarantine procedure complies with specific rules described in this [section](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).

### Optimizing your delivery through quarantines {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-a-delivery)). 這將加快傳送速度，因為錯誤率對傳送速度有很大的影響。

如果無效位址的比率太高，有些網際網路存取供應商會自動認為電子郵件是垃圾郵件。因此，隔離可讓您避免這些提供者列入黑名單。

此外，四分例可排除傳送錯誤電話號碼，以降低SMS傳送成本。

For more on best practices to secure and optimize your deliveries, refer to [this page](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarantine vs blacklisting {#quarantine-vs-blacklisting}

**隔離** 僅適用於地址，而不適用於描述檔本身。這表示，如果兩個描述檔有相同的電子郵件地址，當位址遭到隔離時，兩者都會受到影響。

同樣地，電子郵件地址被四分截的個人檔案可能會更新其個人檔案並輸入新地址，然後再透過傳送動作來定位。

**另一方面，列入黑名單**&#x200B;將導致描述檔不再被任何傳送定位(例如取消訂閱(選擇退出))。For more on the blacklisting process, refer to [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>當使用者對SMS訊息與關鍵字(例如「STOP」)進行回覆，以選擇退出時，他的描述檔不會列入電子郵件選擇退出程序中。The profile phone number is sent to quarantine with the **[!UICONTROL Blacklisted]** status. 此狀態僅指電話號碼，描述檔並未列入黑名單，因此使用者仍可繼續接收電子郵件訊息。For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifying quarantined addresses {#identifying-quarantined-addresses}

可針對特定的傳送或整個平台列出隔離位址。

>[!NOTE]
>
>如果您需要移除隔離的地址，請聯絡技術管理員。

### Identifying quarantined addresses for a delivery {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifying quarantined addresses for the entire platform {#identifying-quarantined-addresses-for-the-entire-platform}

Administrators can list the addresses in quarantine for the entire platform from the **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>This menu lists quarantined elements for **email**, **SMS** and **Push notification** channels.

![](assets/quarantines1.png)

>[!NOTE]
>
>四分位數數量的增加對資料庫的「磨損」有相當的影響。例如，如果電子郵件地址的存留期是三年，而收件者表格每年增加50%，則四分位數的計算方式可能會如下所示：第一年結束：(1*0.33)/(1+0.5)=21%。第一年結束：(1.22*0.33)+0.33)/(1.5+0.75)=32.5%。

## Conditions for sending an address to quarantine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign manages quarantine according to the delivery failure type and the reason assigned during error messages qualification (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) and [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **已忽略錯誤**：忽略的錯誤並不會傳送地址給隔離。
* **錯誤**&#x200B;錯誤：對應的電子郵件地址會立即傳送給隔離。
* **柔和錯誤**：錯誤錯誤不會立即傳送位址給隔離，但會增加錯誤計數器。當錯誤計數器達到限制臨界值時，位址就會被隔離。在預設設定中，臨界值設定為五個錯誤，若兩個錯誤發生至少24小時，則會發生顯著錯誤。地址會置於第六個錯誤處。錯誤計數器臨界值可加以修改。For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   在重試後成功進行傳送時，已重新啓動之位址的錯誤計數器會重新初始化。The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user's email address is then automatically sent to quarantine with the **[!UICONTROL Blacklisted]** status. 此狀態僅指位址，描述檔未列入黑名單，因此使用者仍可繼續接收SMS訊息和推播通知。

>[!NOTE]
Adobe Campaign中的隔離區分大小寫。請務必以小寫的方式匯入電子郵件地址，以免稍後再重新鎖定。

In the list of quarantined addresses (see [Identifying quarantined addresses for the entire platform](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)), the **[!UICONTROL Error reason]** field indicates why the selected address was placed in quarantine.

![](assets/quarantines2.png)

