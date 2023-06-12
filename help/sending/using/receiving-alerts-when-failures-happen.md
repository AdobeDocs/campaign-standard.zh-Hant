---
title: 發生故障時接收警示
description: 瞭解如何使用警報管理系統。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Proofs
role: User
level: Beginner
exl-id: dc8bd1d3-e199-4901-9b1f-7b485879897d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2031'
ht-degree: 2%

---

# 發生故障時接收警示{#receiving-alerts-when-failures-happen}

## 關於傳遞警報 {#about-delivery-alerting}

此 **傳遞警報** 功能是一種警報管理系統，可讓一組使用者自動接收包含其傳送執行資訊的通知。

傳送的通知包含預設根據以下條件的報告：

* 失敗的傳遞
* 準備失敗的傳遞
* 具有不良軟退信錯誤率的傳遞
* 硬跳出錯誤率不佳的傳遞
* 具有待定狀態的傳遞比平常更長
* 低輸送量的傳遞
* 傳遞進行中

警報的收件者可監控Adobe Campaign正在處理的傳送，並在執行中發生問題時採取適當的動作。

您可以根據Adobe Campaign介面中透過「 」控制面板定義的特定警報條件，自訂這些警報通知。

>[!NOTE]
>
>警報通知僅透過電子郵件傳送。

傳送的通知包含：

* A **[!UICONTROL Summary]** 顯示符合您定義之條件的傳遞數目，以及您為每個條件選擇的標籤/顏色。
* A **[!UICONTROL Details]** 區段會列出為對應控制面板定義的所有傳送條件，以及每個條件的所有傳送。

![](assets/delivery-alerting_notification.png)

## 傳遞警報儀表板 {#delivery-alerting-dashboards}

### 關於傳送警報儀表板 {#about-delivery-alerting-dashboards}

若要管理通知的收件者、定義警示條件並存取警示歷史記錄，您必須使用控制面板。

>[!NOTE]
>
>若要存取和設定控制面板和警示條件，您必須擁有管理許可權或顯示在 **傳遞主管** 安全性群組。 標準使用者無法存取Adobe Campaign介面中的儀表板。 他們只能收到警報通知。 如需Adobe Campaign中使用者和安全性的詳細資訊，請參閱 [使用者型別](../../administration/using/users-management.md) 和 [關於安全性群組](../../administration/using/managing-groups-and-users.md#about-security-groups).

從Adobe Campaign介面，您可以：

* 建立和管理傳遞警報儀表板。 另請參閱 [建立傳遞警報儀表板](#creating-a-delivery-alerting-dashboard).
* 定義和管理每個儀表板的傳送警報條件。 例如，您可以根據準備失敗的傳送或只有低輸送量的傳送來建立警報。 另請參閱 [關於警示條件](#about-alerting-criteria).
* 修改每個圖示板的條件引數。 另請參閱 [條件引數](#criteria-parameters).
* 為每個儀表板定義一組收件者。

   例如，您只想通知具有管理許可權的使用者失敗的傳送。 但是，您希望行銷使用者收到有關具有軟退信錯誤率的傳送資訊。 因此，您需要建立兩個不同的儀表板，並定義您想要用於每個收件者群組的條件。

* 存取每個控制面板所有已傳送警示的歷史記錄。

   選取儀表板時，預設會顯示該儀表板的上次傳送警報。 所有已傳送的警報都會列在畫面左側。 按一下 **[!UICONTROL History]** 清單以存取對應的警示。

![](assets/delivery-alerting_dashboard.png)

### 建立傳遞警報儀表板 {#creating-a-delivery-alerting-dashboard}

如果您想要根據特定條件將通知傳送給不同的使用者群組，您需要使用數個控制面板。 若要建立新儀表板：

1. 前往 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**。
1. 選取 **[!UICONTROL Delivery alerting dashboards]** 並按一下 **[!UICONTROL Create]**。
1. 檢查 **[!UICONTROL Enabled]** 方塊以啟動目前儀表板。

   如果停用此選項，則不再傳送連結至此儀表板的通知。 此選項預設為停用。

   ![](assets/delivery-alerting_dashboard_general.png)

1. 從中選擇您要通知的收件者群組 **[!UICONTROL Alert group]** 下拉式清單。 若要修改或建立群組，請參閱 [建立安全性群組並指派使用者](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. 從 **[!UICONTROL Delivery alerting criteria]** 區段，按一下 **[!UICONTROL Create element]** 以新增條件。 另請參閱 [關於警示條件](#about-alerting-criteria).
1. 選取 **[!UICONTROL Edit properties]** 按鈕。在 **[!UICONTROL Criteria parameters]** 索引標籤中，定義套用條件的方式。 另請參閱 [條件引數](#criteria-parameters).
1. 按一下 **[!UICONTROL Create]** 以儲存控制面板。

現在，每次傳送符合您在此控制面板中定義的條件時，都會傳送警報通知給指定的使用者群組。

## 傳遞警報條件 {#delivery-alerting-criteria}

### 關於警示條件 {#about-alerting-criteria}

若要存取傳遞警報條件，請前往 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** 並選取 **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

下列條件可用於傳送警報儀表板：

* **[!UICONTROL Deliveries failed]**：在定義的範圍內排程的任何傳遞，具有錯誤狀態。
* **[!UICONTROL Deliveries with preparation failed]**：在定義的範圍內修改的任何傳送，其準備步驟（目標計算和內容產生）已失敗。 如需詳細資訊，請參閱 [準備傳送](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**：在定義的範圍內排程的任何傳遞，其狀態至少為 **[!UICONTROL In progress]**，軟跳出錯誤率大於定義的百分比。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**：在定義的範圍內排程的任何傳遞，其狀態至少為 **[!UICONTROL In progress]**，硬跳出錯誤率大於定義的百分比。
* **[!UICONTROL Deliveries with long start pending]**：已排程在定義範圍內的任何傳遞，具有 **[!UICONTROL Start pending]** 超過定義持續時間的狀態， **[!UICONTROL Start pending]** 狀態表示系統尚未考慮訊息。
* **[!UICONTROL Deliveries with low throughput]**：任何傳送的開始時間超過定義的持續時間，且已處理訊息的百分比低於定義的，而輸送量低於定義的值。
* **[!UICONTROL Deliveries in progress]**：已排程在定義範圍內的任何傳遞，具有 **[!UICONTROL In progress]** 狀態。

>[!NOTE]
>
>套用至上述條件的所有引數都有預設值。 這些值可在以下位置變更： **[!UICONTROL Criteria parameters]** 「傳送警報」控制面板的「 」標籤。 另請參閱 [條件引數](#criteria-parameters).

您可以從以下專案選取任何專案： **[!UICONTROL Delivery alerting criteria]** 清單以存取其詳細資訊。

![](assets/delivery-alerting_criteria_definition.png)

對於每個條件，您可以定義下列設定：

* **[!UICONTROL Indicators to add in alerts]**，表示會顯示在通知的欄位 **[!UICONTROL Details]** 與所選條件相對應的傳遞區段。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**，表示在通知摘要中傳送條件旁顯示的標籤和顏色。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**：如果符合一次傳送的條件，則會在監控期間內傳送的每個通知中重複執行此條件。 否則，對於一次傳遞，警示條件一天只傳送一個警示（在第一次發生時）。

   依預設，此選項會針對所有條件設定為每天一次。

**相關主題：**

* [傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [警報頻率](#alerting-frequency)
* [行銷活動圖示和狀態](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### 建立傳遞警報條件 {#creating-a-delivery-alerting-criterion}

您可以建立新的傳送警報條件，以更符合您的需求。

例如，您可以建立新條件，讓系統傳送通知，列出具有下列條件的所有傳送： **[!UICONTROL Finished]** 狀態。

若要這麼做，您必須先延伸 **傳遞** 並新增篩選器，讓您僅選取具有的傳送 **[!UICONTROL Finished]** 狀態。

1. 前往 **Adobe Campaign** > **管理** > **開發** > **自訂資源** 並按一下 **[!UICONTROL Create]**.
1. 選取 **[!UICONTROL Extend an existing resource]**，選取 **[!UICONTROL Delivery]** 資源，然後按一下 **[!UICONTROL Create]** 以編輯它。

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   如需擴充現有資源的詳細資訊，請參閱 [定義資源](../../developing/using/creating-or-extending-the-resource.md).

1. 在 **[!UICONTROL Delivery]** 資源，前往 **[!UICONTROL Filter definition]** 標籤並按一下 **[!UICONTROL Add an element]** 以建立篩選器。

   ![](assets/delivery-alerting_new-filter.png)

1. 編輯新的篩選器定義：在 **[!UICONTROL Filter definition]** 視窗，拖放 **[!UICONTROL Status]** 專案並選取 **[!UICONTROL Finished]** 作為篩選條件。

   ![](assets/delivery-alerting_filter-status.png)

   如需建立和編輯自訂篩選器的詳細資訊，請參閱 [定義篩選器](../../developing/using/configuring-filter-definition.md).

1. 儲存變更並發佈資源。 如需詳細資訊，請參閱 [發佈自訂資源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   篩選器已建立，現在可以在新的傳送警報條件中選取。

1. 前往 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**，選取 **[!UICONTROL Delivery alerting criteria]** 並按一下 **[!UICONTROL Create]**.
1. 在 **[!UICONTROL Delivery filter applied by this criterion]** 下拉式清單，選取您剛才建立的篩選器。

   ![](assets/delivery-alerting_cus-filter.png)

   您可以用與預設條件相同的方式定義條件的設定。 另請參閱 [關於警示條件](#about-alerting-criteria).

建立後，這些條件即可新增至傳送警報控制面板及其他條件。 另請參閱 [關於傳送警報儀表板](#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**相關主題：**

[新增或擴充資源](../../developing/using/key-steps-to-add-a-resource.md)

## 傳遞警報引數 {#delivery-alerting-parameters}

### 條件引數 {#criteria-parameters}

在 **[!UICONTROL Criteria parameters]** 的索引標籤 [傳遞警報儀表板](#creating-a-delivery-alerting-dashboard)，您可以定義套用至此儀表板中所選條件的設定。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**：例如，如果您在此欄位中輸入100，則系統只會針對目標等於或大於100個收件者的傳送傳送傳送通知。 此引數會套用至所有條件。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**：目前時間之前和之後的小時數。 只會考慮聯絡日期在此時間範圍內的傳遞。 此引數會套用至所有條件。 此欄位的值預設為24小時。

   如需聯絡日期的詳細資訊，請參閱 [關於排程](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**：對於軟跳出錯誤率大於指定值的所有傳送，都會傳送通知。 此欄位的值預設為0.05 (5%)。

   如需軟退信錯誤的詳細資訊，請參閱 [退回郵件資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) 和 [傳遞失敗型別清單](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**：對於硬跳出錯誤率大於指定值的所有傳送，都會傳送通知。 此欄位的值預設為0.05 (5%)。

   如需硬跳出錯誤的詳細資訊，請參閱 [退回郵件資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) 和 [傳遞失敗型別清單](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**：針對具有的所有傳遞傳送傳送通知 **[!UICONTROL Start pending]** 狀態超過此欄位中指定的持續時間， **[!UICONTROL Start pending]** 狀態表示系統尚未考慮訊息。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**：僅傳遞開始(使用 **[!UICONTROL In progress]** 「 」會考慮超過指定期間的「 」狀態 **[!UICONTROL Deliveries with low throughput]** 條件。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**：只會考慮已處理訊息百分比低於指定百分比的傳遞， **[!UICONTROL Deliveries with low throughput]** 條件。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**：只會考慮輸送量低於指定值的傳送， **[!UICONTROL Deliveries with low throughput]** 條件。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**：系統只會考慮已處理訊息百分比高於指定百分比的傳遞。

### 警報頻率 {#alerting-frequency}

此 **[!UICONTROL Frequency of delivery alerting]** 選項可定義兩個警報傳送之間的延遲。 預設為10分鐘。

您可以透過 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 功能表。

>[!NOTE]
>
>此選項適用於Adobe Campaign中定義的所有儀表板。 您無法為每個儀表板設定特定的頻率。

## 傳遞警報原因 {#delivery-alerting-reasons}

此 **傳遞警報** 此功能可讓您透過電子郵件和控制面板，自動通知所有涉及的Adobe Campaign使用者傳遞執行狀態。

現在，當您收到傳送警報通知時，以下提供一些您可以做什麼的提示。

首先，檢查傳送的 **記錄** 標籤以檢視與傳遞和校樣相關的所有資訊。 紅色和黃色圖示可讓您識別錯誤或警告。 紅色圖示表示嚴重錯誤，導致傳送無法啟動。

若要檢視每次傳送的歷史記錄，請選取 **[!UICONTROL Sending logs]** 標籤。 它包含已傳送訊息的清單及其狀態。 您可以在此處檢查每個收件者的傳遞狀態( **[!UICONTROL Sent]**， **[!UICONTROL Pending]**， **[!UICONTROL Failed]**、等)。 如需詳細資訊，請參閱 [傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs).

根據傳送所符合的條件，接收警報通知的幾項可能原因如下。

* **[!UICONTROL Deliveries failed]**：此條件會通知您所有狀態錯誤的傳送。 原因可能是：

   * 傳遞伺服器（MTA、訊息傳輸代理程式）發生問題
   * Adobe Campaign傳遞伺服器與接收伺服器之間的連線逾時
   * 傳遞能力問題
   * 錯誤的工作流程

   如果傳遞是由工作流程觸發，請檢查該工作流程是否已正確啟動。 如需詳細資訊，請參閱 [執行工作流程](../../automating/using/about-workflow-execution.md). 否則，請聯絡您的Adobe Campaign管理員以解決問題。

* **[!UICONTROL Deliveries with preparation failed]**：在下列情況下傳送準備期間可能會發生錯誤：

   * 傳遞缺少主旨。
   * 個人化欄位中有錯誤的語法。
   * 目標遺失。
   * 傳遞超過大小限制。

   如需詳細資訊，請參閱 [準備傳送](../../sending/using/preparing-the-send.md). 不過，這些錯誤通常會在訊息分析期間發現。 另請參閱 [控制規則](../../sending/using/control-rules.md).

* 的可能原因 **[!UICONTROL Delivery with bad error ratio for soft bounces]** 警報可以是：

   * 收件者的伺服器已關閉。
   * 收件者的信箱已滿。

   如需詳細資訊，請檢視 **[!UICONTROL Exclusion logs]** 和 **[!UICONTROL Exclusion causes]** 傳遞記錄的標籤。 另請參閱 [排除記錄](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   的可能原因 **[!UICONTROL Delivery with bad error ratio for hard bounces]** 警報可以是：

   * 收件者會新增至封鎖清單，這表示他們不想再被聯絡。
   * 收件者的電子郵件地址不存在。
   * 收件者的網域不存在。
   * 收件者的伺服器正在封鎖傳遞。

   若要避免軟跳出和硬跳出錯誤，請遵循下列最佳實務：

   * 建立篩選型別規則，以在傳遞分析期間排除訊息目標的一部分，例如隔離的收件者。 另請參閱 [建立篩選規則](../../sending/using/filtering-rules.md).
   * 定期更新客戶資料庫，以維持良好的隔離管理流程。 另請參閱 [關於隔離](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * 一般而言，儘可能改善傳遞能力。 請參閱Adobe Campaign [傳遞能力](../../sending/using/about-deliverability.md) 提供詳細檔案，並聯絡Adobe Campaign管理員以尋求協助。



* **[!UICONTROL Deliveries with long start pending]**：這通常表示MTA （訊息轉移代理程式）層級有問題。 執行程式正在等待某些資源的可用性。 MTA可能尚未啟動。

   **[!UICONTROL Deliveries with low throughput]**：同樣地，這是傳遞能力問題，表示MTA太慢。

   如需這些問題的詳細資訊，請聯絡您的Adobe Campaign管理員。

**相關主題：**

* [瞭解傳遞故障](../../sending/using/understanding-delivery-failures.md)
* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [關於 Campaign 中的選擇加入和選擇退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
