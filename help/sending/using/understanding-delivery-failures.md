---
title: 瞭解傳送故障
description: 瞭解如何使用 Campaign 管理傳送失敗。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: 92a83400-447a-4d23-b05c-0ea013042ffa
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 59%

---

# 瞭解傳遞故障{#understanding-delivery-failures}

## 關於傳送失敗 {#about-delivery-failures}

當傳送無法傳送至輪廓時，遠端伺服器會自動傳送錯誤訊息，此錯誤訊息會由 Adobe Campaign 平台擷取，並限定為隔離電子郵件地址或電話號碼。請參閱[退回電子郵件鑑定](#bounce-mail-qualification)。

>[!NOTE]
>
>**電子郵件**&#x200B;錯誤訊息（或「退信」）由 Enhanced MTA（同步退信）或 inMail 程序（非同步退信）限定。
>
>**簡訊錯誤訊息（或 &quot;SR&quot; 作為 &quot;Status Report&quot;）會由 MTA 程序限定。**

如果地址被隔離或設定檔位於封鎖清單中，也可以在傳送準備期間排除訊息。 已排除的訊息會列在傳送控制面板的　**[!UICONTROL Exclusion logs]**　索引標籤中（請參閱[本區段](../../sending/using/monitoring-a-delivery.md#exclusion-logs)）。

![](assets/exclusion_logs.png)

**相關主題：**

* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [關於 Campaign 中的選擇加入和選擇退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
* [退回](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)

## 識別訊息的傳遞失敗 {#identifying-delivery-failures-for-a-message}

傳送傳送後，**[!UICONTROL Sending logs]**　索引標籤（請參閱[本區段](../../sending/using/monitoring-a-delivery.md#sending-logs)）可讓您檢視每個輪廓的傳送狀態，以及相關的失敗類型和原因（請參閱[傳送失敗類型和原因](#delivery-failure-types-and-reasons)）。

![](assets/sending_logs.png)

此外，也提供專屬的現成可用報表。此報表詳細說明傳送期間遇到的整體硬式和軟式錯誤，以及自動處理退信。如需詳細資訊，請參閱[本區段](../../reporting/using/bounce-summary.md)。

## 傳遞失敗型別和原因 {#delivery-failure-types-and-reasons}

傳送失敗時有三種錯誤類型：

* **硬式**：「硬式」錯誤表示地址無效。這包含明確指出地址無效的錯誤訊息，例如：&quot;未知使用者&quot;。
* **軟式**：這可能是暫時錯誤，或無法分類的錯誤，例如：「無效域」或「信箱已滿」。
* **已忽略**：這是已知為暫時的錯誤，例如「不在辦公室」，或是技術錯誤，例如，如果傳送者類型是 &quot;postmaster&quot;。

傳送失敗的可能原因有：

| 錯誤標籤 | 錯誤型別 | 說明 |
| ---------|----------|---------|
| **[!UICONTROL User unknown]** | 強烈 | 地址不存在。 此輪廓不會再嘗試傳送。 |
| **[!UICONTROL Quarantined address]** | 強烈 | 地址被放入隔離區。 |
| **[!UICONTROL Unreachable]** | 軟/硬 | 訊息傳送鏈中發生錯誤（例如暫時無法存取網域）。 根據提供者傳回的錯誤，將直接傳送地址給隔離，或者重新嘗試傳送，直到 Campaign 收到證明隔離狀態正確的錯誤或錯誤數達到 5 為止。 |
| **[!UICONTROL Address empty]** | 強烈 | 地址未定義。 |
| **[!UICONTROL Mailbox full]** | 柔光 | 此使用者的信箱已滿，無法接受更多郵件。 可以從隔離清單中刪除此地址，以進行另一次嘗試。30天後自動移除。 為了從隔離位址清單自動移除位址，您必須啟動 **[!UICONTROL Database cleanup]** 技術工作流程。 |
| **[!UICONTROL Refused]** | 軟/硬 | 由於安全反饋為垃圾郵件報告，該地址已被置於隔離狀態。 根據提供者傳回的錯誤，將直接傳送地址給隔離，或者重新嘗試傳送，直到 Campaign 收到證明隔離狀態正確的錯誤或錯誤數達到 5 為止。 |
| **[!UICONTROL Duplicate]** | 已忽略 | 區段中已偵測到該位址。 |
| **[!UICONTROL Not defined]** | 柔光 | 該位址正在限定中，因為錯誤尚未增加。 當伺服器傳送新錯誤訊息時，會發生此類錯誤：它可能是孤立的錯誤，但如果再次發生，錯誤計數器會增加，這會提醒技術團隊。 |
| **[!UICONTROL Error ignored]** | 已忽略 | 此地址在允許清單上，無論如何，都會寄送電子郵件給它。 |
| **[!UICONTROL Address on denylist]** | 強烈 | 地址已在傳送時新增到封鎖清單中。 |
| **[!UICONTROL Account disabled]** | 軟/硬 | 當網際網路存取提供者(IAP)偵測到長時間的不活動時，它可以關閉使用者帳戶：傳送至使用者位址的作業將無法進行。 「軟式」或「硬式」類型取決於收到的錯誤類型：如果帳戶因為 6 個月的閒置而暫時停用，而且仍可啟動，則會指派狀態 **[!UICONTROL Erroneous]** 並再次嘗試傳送。如果收到錯誤訊號表明帳戶已永久停用，則會直接將其發送到隔離。 |
| **[!UICONTROL Not connected]** | 已忽略 | 當傳送訊息時，設定檔的行動電話已關閉或未連線至網路。 |
| **[!UICONTROL Invalid domain]** | 柔光 | 電子郵件地址的網域不正確或已不存在。 此輪廓將再次定位，直到錯誤計數達到5。之後，記錄將設定為「隔離」狀態，不會再重試。 |
| **[!UICONTROL Text too long]** | 已忽略 | SMS訊息中的字元數量超過限制。 如需詳細資訊，請參閱簡訊編碼、長度和音譯[&#128279;](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)。 |
| **[!UICONTROL Character not supported by encoding]** | 已忽略 | SMS訊息包含一或多個編碼不支援的字元。 有關詳細資訊，請參閱[字元表- GSM標準](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)。 |


**相關主題：**
* [硬退信](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)
* [軟退信](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#soft-bounces)

## 傳送暫時失敗後重試 {#retries-after-a-delivery-temporary-failure}

如果訊息因暫時錯誤而失敗，則在傳送期間將執行重試。 如需錯誤類型的詳細資訊，請參閱[傳送失敗類型和原因](#delivery-failure-types-and-reasons)。

重試次數（在傳送開始後應執行多少次重試）和重試之間的最小延遲現在是<!--managed by the Adobe Campaign Enhanced MTA,-->，這是根據IP在歷史和目前指定網域的執行狀況而定。 會忽略 Campaign 中的&#x200B;**重試次數**&#x200B;設定。

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

要修改傳送的持續時間，請轉至傳送或傳遞範本的進階參數，並編輯&#x200B;**[!UICONTROL Delivery duration]**&#x200B;有效期間[區段的 &#x200B;](../../administration/using/configuring-email-channel.md#validity-period-parameters) 欄位。

>[!IMPORTANT]
>
>**您的 Campaign 傳送中的&#x200B;**&#x200B;[!UICONTROL Delivery duration]&#x200B;**參數現在僅在設為 3.5 天或更少時使用。** 如果您定義的值超過　3.5　天，則不會考慮該值。

例如，如果您希望某個傳遞的重試在一天後停止，您可以將傳遞持續時間設為&#x200B;**1d**，重試佇列中的訊息將在一天後移除。

>[!NOTE]
>
>一旦訊息在重試佇列中超過3.5天且無法傳送，訊息將逾時，其狀態將在<!--from **[!UICONTROL Sent]**-->傳送記錄檔&#x200B;**[!UICONTROL Failed]**&#x200B;中更新[至](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS
The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## 同步與非同步錯誤 {#synchronous-and-asynchronous-errors}

傳送可能會立即失敗（同步錯誤），或稍後傳送失敗（非同步錯誤）。

* **同步錯誤**：由 Adobe Campaign 傳送伺服器連絡的遠端伺服器會立即傳回錯誤訊息，不可傳送至輪廓的伺服器。
* **非同步錯誤**：接收伺服器稍後會重新發送退回郵件或 SR。傳送後一週內，可能會發生非同步錯誤。

## 退回郵件資格 {#bounce-mail-qualification}

對於同步傳送失敗錯誤訊息，Adobe Campaign Enhanced MTA （訊息傳輸代理程式）會決定退信型別和資格，並將該資訊傳回至Campaign。

>[!NOTE]
>
> Campaign **[!UICONTROL Message qualification]** 表格中的退信鑑定不再使用。

inMail 程序仍會透過 **[!UICONTROL Inbound email]** 規則來限定非同步退信。若要存取這些規則，請按一下左上方的&#x200B;**Adobe**&#x200B;標誌，然後選取&#x200B;**[!UICONTROL Administration > Channels > Email > Email processing rules]**&#x200B;並選取&#x200B;**[!UICONTROL Bounce mails]**。 如需此規則的詳細資訊，請參閱[本節](../../administration/using/configuring-email-channel.md#email-processing-rules)。

如需有關退信和各種退信的詳細資訊，請參閱[本節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)。

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS

Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **Adobe** logo, in the top-left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## 使用雙重加入機制最佳化電子郵件傳遞能力 {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

傳送電子郵件時，最佳作法是雙重加入機制。它可保護平台免受錯誤或無效的電子郵件地址、垃圾郵件機器人，並防止可能的垃圾郵件投訴。

原則是先傳送電子郵件以確認訪客的同意，再將其儲存為「設定檔」至您的Campaign資料庫：訪客填寫線上登入頁面，然後會收到電子郵件，必須按一下確認連結才能完成訂閱。

如需詳細資訊，請參閱[本節](../../channels/using/setting-up-a-double-opt-in-process.md)。
