---
title: 瞭解傳遞失敗
seo-title: 瞭解傳遞失敗
description: 瞭解傳遞失敗
seo-description: 瞭解如何透過Campaign管理傳遞失敗。
page-status-flag: 從未啓動
uuid: 2735aua05-7b6f-47c9-98c4-a15 cc33 be39 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: 監控訊息
discoiquuid: 38452841-4cd4-4f92-a5 c3-1dfdd54 ff4 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Understanding delivery failures{#understanding-delivery-failures}

## About delivery failures {#about-delivery-failures}

傳送無法傳送至描述檔時，遠端伺服器會自動傳送錯誤訊息，由Adobe Campaign平台挑選，並可判斷電子郵件地址或電話號碼是否應遭到隔離。See [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

>[!NOTE]
>
>**電子郵件** 錯誤訊息(或「彈回數」)會受到Inmail程序的符合資格。**SMS** 錯誤訊息(或「狀態報表」的「SR」)受到MTA程序的符合。

在傳送準備期間，如果地址遭到隔離或描述檔列入黑名單時，也可以排除訊息。Excluded messages are listed in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**相關主題：**

* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [管理促銷活動中的黑名單](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifying delivery failures for a message {#identifying-delivery-failures-for-a-message}

Once a delivery is sent, the **[!UICONTROL Sending logs]** tab (see [this section](../../sending/using/monitoring-a-delivery.md#sending-logs)) allows you to view the delivery status for each profile and the associated failure type and reason (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

另外還提供專屬的立即可用報告。此報告詳細說明傳送期間遇到的整體硬體和柔和錯誤，以及彈回數的自動處理。For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Delivery failure types and reasons {#delivery-failure-types-and-reasons}

當傳送失敗時，有三種類型的錯誤：

* **硬碟：「hard」錯誤表示無效的位址。** This including a error message that that the address is invalid，such as：「未知使用者」。
* **Soft**：這可能是暫時錯誤，或無法分類的錯誤，例如：「無效網域」或「Mailbox完整」。
* **已忽略**：這是已知的暫時錯誤，例如「離開辦公室」或技術錯誤，例如傳送者類型為「postmaster」。

傳送失敗的可能原因為：

* **[!UICONTROL User unknown]** (硬式類型)：地址不存在。本個人檔案不會嘗試進一步傳送。
* **[!UICONTROL Quarantined address]** (硬式類型)：地址已置於隔離中。
* **[!UICONTROL Unreachable]** (Soft/Hard type)：訊息傳送鏈中發生錯誤(發生在SMTP繼電器、暫時無法連線的網域等)。根據提供者傳回的錯誤，將會直接傳送位址給隔離，或再試一次，直到Campaign收到「隔離」狀態，或直到錯誤數目達到5為止。
* **[!UICONTROL Address empty]** (硬式類型)：未定義地址。
* **[!UICONTROL Mailbox full]** (柔和類型)：此使用者的郵箱已滿，無法接受更多訊息。此地址可從隔離清單中移除，以進行另一個嘗試。30天後自動移除。

   In order for the address to be automatically removed from the list of quarantined addresses, the **[!UICONTROL Database cleanup]** technical workflow must be started.

* **[!UICONTROL Refused]** (Soft/Hard type)：因為安全性回饋是垃圾郵件報告，所以已將地址置於隔離中。根據提供者傳回的錯誤，將會直接傳送位址給隔離，或再試一次，直到Campaign收到「隔離」狀態，或直到錯誤數目達到5為止。
* **[!UICONTROL Duplicate]**：已在區段中偵測到地址。
* **[!UICONTROL Not defined]** (柔和類型)：此地址的資格是因為錯誤尚未增加。

   當伺服器傳送新錯誤訊息時，就會發生此類型的錯誤：可能是孤立的錯誤，但如果再次發生，錯誤計數器會增加，會提醒技術團隊。

* **[!UICONTROL Error ignored]**：地址位於白名單中，電子郵件將會傳送至任何情況。
* **[!UICONTROL Blacklisted address]**：傳送時，地址已列入黑名單。
* **[!UICONTROL Account disabled]** (Soft/Hard type)：當網際網路存取提供者(IAP)偵測到長時間閒置時，就可以關閉使用者的帳戶：然後無法傳送使用者地址。The Soft or Hard type depends upon the type of error received: if the account is temporarily disabled due to six months of inactivity and can still be activated, the status **[!UICONTROL Erroneous]** will be assigned and the delivery will be tried again. 如果收到的錯誤訊號指出帳戶已永久停用，則會直接傳送至「隔離」。
* **[!UICONTROL Not connected]**：設定檔的行動電話會關閉或未連線至網路。
* **[!UICONTROL Invalid domain]** (柔和類型)：電子郵件地址的網域不正確或不再存在。此描述檔將會再度定位，直到錯誤計數達到5為止。之後，記錄會設為「隔離」狀態，且不會再進行重試。
* **[!UICONTROL Text too long]**：SMS訊息中的字元數超出限制。For more on this, see [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**：SMS訊息包含一或多個編碼，但編碼不受支援。&amp;For more on this, see [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Retries after a delivery temporary failure {#retries-after-a-delivery-temporary-failure}

If a message fails due to a temporary error of the **Ignored** type, retries will be performed during the delivery duration. For more on the types of errors, see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

若要修改傳送的持續時間，請移至傳送或傳送範本的進階參數，並指定對應欄位中所要的持續時間。The advanced delivery properties are presented in [this section](../../administration/using/configuring-email-channel.md#validity-period-parameters).

預設設定允許每小時重試五次，之後一次重試天。The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Synchronous and asynchronous errors {#synchronous-and-asynchronous-errors}

傳送在傳送(非同步錯誤)後，就會立即失敗(同步錯誤)或更新版本。

* **同步錯誤**：Adobe Campaign傳送伺服器與遠端伺服器聯繫的遠端伺服器傳回錯誤訊息，不允許傳送至描述檔的伺服器。
* **非同步錯誤**：接收伺服器稍後重新傳送了反彈郵件或SR。非同步錯誤可能會在傳送後一周內發生。

## Bounce mail qualification {#bounce-mail-qualification}

傳送失敗錯誤訊息(或「彈回數」)會由Adobe Campaign平台挑選，並由Inmail程序取得，以豐富電子郵件管理規則的清單。

此清單僅供管理員使用，且包含Adobe Campaign用來限定發佈失敗的所有規則。

To access it, click the **[!UICONTROL Adobe Campaign]** logo, at the top left, then select **[!UICONTROL Administration > Channels > Email > Email processing rules]**.

For more on this, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

彈回數可能具有下列資格狀態：

* **[!UICONTROL To qualify]**：彈回數必須符合資格。必須由「傳送能力」團隊完成資格，以確保平台提供能力正常運作。只要不符合資格，就不會使用反彈郵件來充實電子郵件處理規則的清單。
* **[!UICONTROL Keep]**：彈回數是合格的，「更新」將會用於 **「更新」，** 以與現有的電子郵件處理規則比較，並豐富清單。
* **[!UICONTROL Ignore]**：彈回數是合格的，但無法用於「 **更新」以提供功能** 工作流程。因此不會傳送至用戶端實例。

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)

## Optimizing mail deliverability with double opt-in mechanism {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

傳送電子郵件時，需要使用雙加入機制。它可保護平台不會出現錯誤或無效的電子郵件地址、垃圾郵件，並防止可能出現垃圾郵件抱怨。

原則是傳送電子郵件以確認訪客的合約，然後將其儲存為「促銷活動」資料庫中的「個人檔案」：訪客會填寫線上登陸頁面，然後收到電子郵件，並必須按一下確認連結中的，以完成訂閱。

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
