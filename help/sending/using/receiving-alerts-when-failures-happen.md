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

## 關於交付警報 {#about-delivery-alerting}

的 **傳遞警報** 功能是警報管理系統，它使一組用戶能夠自動接收包含其交付執行資訊的通知。

預設情況下，發送的通知包含基於以下條件的報告：

* 交貨失敗
* 準備失敗的交貨
* 軟彈跳錯誤率不佳的交貨
* 硬彈跳錯誤率不佳的交貨
* 狀態為掛起的交貨比通常的交貨時間長
* 具有低吞吐量的交貨
* 正在交貨

警報接收者可監控Adobe Campaign正在處理的遞送，並在執行中出現問題時採取適當行動。

這些警報通知可以根據通過Adobe Campaign介面中的儀表板定義的特定警報標準進行自定義。

>[!NOTE]
>
>警報通知僅通過電子郵件發送。

發送的通知包含：

* A **[!UICONTROL Summary]** 顯示符合您定義的標準的交貨數量以及您為每個標準選擇的標籤/顏色。
* A **[!UICONTROL Details]** 列出為相應控制面板定義的所有交貨標準以及每個標準的所有交貨。

![](assets/delivery-alerting_notification.png)

## 交付警報儀表板 {#delivery-alerting-dashboards}

### 關於交付警報儀表板 {#about-delivery-alerting-dashboards}

要管理通知的收件人，請定義警報標準並訪問警報的歷史記錄，您需要使用儀表板。

>[!NOTE]
>
>要訪問和配置儀表板和警報標準，您必須具有管理權限或顯示在 **交貨主管** 安全組。 標準用戶無法訪問Adobe Campaign介面中的儀表板。 他們只能接收警報通知。 有關Adobe Campaign用戶和安全性的詳細資訊，請參見 [用戶類型](../../administration/using/users-management.md) 和 [關於安全組](../../administration/using/managing-groups-and-users.md#about-security-groups)。

從Adobe Campaign介面，您可以：

* 建立和管理交付警報儀表板。 請參閱 [建立交付警報儀表板](#creating-a-delivery-alerting-dashboard)。
* 定義和管理每個儀表板的交付警報標準。 例如，您可以基於準備失敗的交貨或僅以低吞吐量的交貨生成警報。 請參閱 [關於警報標準](#about-alerting-criteria)。
* 修改每個操控板的條件參數。 請參閱 [條件參數](#criteria-parameters)。
* 為每個儀表板定義一組收件人。

   例如，您希望僅通知具有失敗交貨管理權限的用戶。 但是，您希望市場營銷用戶以軟彈跳錯誤率接收有關交貨的資訊。 因此，您需要建立兩個不同的儀表板並定義每個接收人組所需的標準。

* 訪問每個儀表板的所有已發送警報的歷史記錄。

   選擇儀表板時，預設情況下將顯示此儀表板的上次發送警報。 所有發送的警報都列在螢幕左側。 按一下 **[!UICONTROL History]** 清單以訪問相應的警報。

![](assets/delivery-alerting_dashboard.png)

### 建立交付警報儀表板 {#creating-a-delivery-alerting-dashboard}

如果要根據特定條件向不同的用戶組發送通知，則需要使用多個儀表板。 要建立新儀表板：

1. 前往 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**。
1. 選取 **[!UICONTROL Delivery alerting dashboards]** 並按一下 **[!UICONTROL Create]**。
1. 檢查 **[!UICONTROL Enabled]** 框，以激活當前操控板。

   如果禁用此選項，則不再發送連結到此儀表板的通知。 預設情況下禁用此選項。

   ![](assets/delivery-alerting_dashboard_general.png)

1. 選擇要從中通知的收件人組 **[!UICONTROL Alert group]** 的子菜單。 要修改或建立組，請參閱 [建立安全組並分配用戶](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)。
1. 從 **[!UICONTROL Delivery alerting criteria]** ，按一下 **[!UICONTROL Create element]** 的子菜單。 請參閱 [關於警報標準](#about-alerting-criteria)。
1. 選取 **[!UICONTROL Edit properties]** 按鈕。在 **[!UICONTROL Criteria parameters]** 頁籤。 請參閱 [條件參數](#criteria-parameters)。
1. 按一下 **[!UICONTROL Create]** 按鈕。

現在，每次交付符合您在此儀表板中定義的條件時，都會向指定的用戶組發送警報通知。

## 交付警報標準 {#delivery-alerting-criteria}

### 關於警報標準 {#about-alerting-criteria}

要訪問交付警報標準，請轉到 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** 選擇 **[!UICONTROL Delivery alerting criteria]**。

![](assets/delivery-alerting_criteria.png)

以下標準可用於交付警報儀表板：

* **[!UICONTROL Deliveries failed]**:在定義範圍內計畫的任何交貨，狀態錯誤。
* **[!UICONTROL Deliveries with preparation failed]**:在定義範圍內修改的任何傳遞，其準備步驟（目標計算和內容生成）已失敗。 有關此的詳細資訊，請參閱 [準備發送](../../sending/using/preparing-the-send.md)。
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**:在定義範圍內計畫的任何交貨，其狀態至少為 **[!UICONTROL In progress]**，軟彈跳錯誤率大於定義的百分比。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**:在定義範圍內計畫的任何交貨，其狀態至少為 **[!UICONTROL In progress]**，硬彈跳錯誤率大於定義的百分比。
* **[!UICONTROL Deliveries with long start pending]**:在定義範圍內計畫的任何交貨， **[!UICONTROL Start pending]** 狀態超過定義的持續時間， **[!UICONTROL Start pending]** 狀態表示系統尚未考慮消息。
* **[!UICONTROL Deliveries with low throughput]**:任何傳送的啟動時間都超過定義的持續時間，並且處理的消息的百分比小於定義的百分比，吞吐量低於定義的值。
* **[!UICONTROL Deliveries in progress]**:在定義範圍內計畫的任何交貨， **[!UICONTROL In progress]** 狀態。

>[!NOTE]
>
>應用於上述條件的所有參數都具有預設值。 可以在 **[!UICONTROL Criteria parameters]** 的子菜單。 請參閱 [條件參數](#criteria-parameters)。

可以從 **[!UICONTROL Delivery alerting criteria]** 清單以訪問其詳細資訊。

![](assets/delivery-alerting_criteria_definition.png)

對於每個標準，可以定義以下設定：

* **[!UICONTROL Indicators to add in alerts]**，表示將出現在通知的 **[!UICONTROL Details]** 的子菜單。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**，表示通知摘要中交貨標準旁邊的標籤和顏色。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**:如果滿足一個遞送的標準，則在監測期間內發送的每個通知中重複該標準。 否則，每天（第一次發生時）只會根據一個傳遞的警報標準發送一個警報。

   預設情況下，此選項設定為所有條件的每天一次。

**相關主題：**

* [傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [警報頻率](#alerting-frequency)
* [行銷活動圖示和狀態](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### 建立傳遞警報標準 {#creating-a-delivery-alerting-criterion}

您可以建立新的交付警報標準，以更好地滿足您的需求。

例如，您可以建立新標準，以便通過 **[!UICONTROL Finished]** 狀態。

為此，您首先需要擴展 **交貨** 並添加新篩選器，以便您只選擇具有 **[!UICONTROL Finished]** 狀態。

1. 轉到 **Adobe Campaign** > **管理** > **開發** > **自定義資源** 按一下 **[!UICONTROL Create]**。
1. 選擇 **[!UICONTROL Extend an existing resource]**，選擇 **[!UICONTROL Delivery]** 從下拉清單中按一下 **[!UICONTROL Create]** 編輯。

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   有關擴展現有資源的詳細資訊，請參見 [定義資源](../../developing/using/creating-or-extending-the-resource.md)。

1. 在 **[!UICONTROL Delivery]** 資源，轉到 **[!UICONTROL Filter definition]** 頁籤 **[!UICONTROL Add an element]** 的子菜單。

   ![](assets/delivery-alerting_new-filter.png)

1. 編輯新篩選器定義：的 **[!UICONTROL Filter definition]** 窗口，拖放 **[!UICONTROL Status]** 項到工作區，然後選擇 **[!UICONTROL Finished]** 按鈕。

   ![](assets/delivery-alerting_filter-status.png)

   有關建立和編輯自定義篩選器的詳細資訊，請參閱 [定義篩選器](../../developing/using/configuring-filter-definition.md)。

1. 保存更改並發佈資源。 有關此的詳細資訊，請參閱 [發佈自定義資源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   過濾器已建立，現在可以在新的傳遞警報標準中選擇。

1. 轉到 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**&#x200B;選中 **[!UICONTROL Delivery alerting criteria]** 按一下 **[!UICONTROL Create]**。
1. 在 **[!UICONTROL Delivery filter applied by this criterion]** 下拉清單中，選擇您剛建立的篩選器。

   ![](assets/delivery-alerting_cus-filter.png)

   可以以與預設條件相同的方式定義條件的設定。 請參閱 [關於警報標準](#about-alerting-criteria)。

建立後，這些條件可以添加到交付警報控制板以及其他條件中。 請參閱 [關於交付警報儀表板](#about-delivery-alerting-dashboards)。

![](assets/delivery-alerting_new-criterion.png)

**相關主題：**

[新增或擴充資源](../../developing/using/key-steps-to-add-a-resource.md)

## 傳遞警報參數 {#delivery-alerting-parameters}

### 條件參數 {#criteria-parameters}

在 **[!UICONTROL Criteria parameters]** 頁籤 [交付警報儀表板](#creating-a-delivery-alerting-dashboard)，可定義應用於此儀表板中選定條件的設定。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**:例如，如果在此欄位中輸入100，則系統只會為目標等於或大於100個收件人的交貨發送通知。 此參數適用於所有條件。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**:當前時間之前和之後的小時數。 只考慮在此時間範圍內具有聯繫日期的交貨。 此參數適用於所有條件。 預設情況下，此欄位的值設定為24小時。

   有關聯繫日期的詳細資訊，請參閱 [關於計畫](../../sending/using/about-scheduling-messages.md)。

* **[!UICONTROL Maximum ratio of soft bounce errors]**:系統會為所有交貨發送一個通知，其軟彈跳錯誤率大於指定值。 預設情況下，此欄位的值設定為0.05(5%)。

   有關軟彈跳錯誤的詳細資訊，請參閱 [退信郵件資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) 和 [傳遞失敗類型清單](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Maximum ratio of hard bounce errors]**:所有交貨的硬彈跳錯誤率大於指定值時都會發送通知。 預設情況下，此欄位的值設定為0.05(5%)。

   有關硬彈跳錯誤的詳細資訊，請參閱 [退信郵件資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) 和 [傳遞失敗類型清單](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**:將為所有交貨發送一個通知， **[!UICONTROL Start pending]** 狀態超過此欄位中指定的持續時間， **[!UICONTROL Start pending]** 狀態表示系統尚未考慮消息。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**:僅開始交貨(使用 **[!UICONTROL In progress]** 狀態)的指定持續時間內， **[!UICONTROL Deliveries with low throughput]** 標準。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**:只有處理郵件百分比低於指定百分比的交貨才考慮 **[!UICONTROL Deliveries with low throughput]** 標準。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**:只有吞吐量低於指定值的交貨才考慮 **[!UICONTROL Deliveries with low throughput]** 標準。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**:只考慮具有高於指定百分比的已處理郵件百分比的交貨。

### 警報頻率 {#alerting-frequency}

的 **[!UICONTROL Frequency of delivery alerting]** 選項允許定義兩個警報發送之間的延遲。 預設情況下，它設定為10分鐘。

您可以通過 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 的子菜單。

>[!NOTE]
>
>此選項適用於在Adobe Campaign定義的所有儀表板。 不能為每個儀表板設定特定頻率。

## 交付警報原因 {#delivery-alerting-reasons}

的 **傳遞警報** 該功能通過電子郵件和儀表板自動將交付執行狀態通知您所有參與的Adobe Campaign用戶。

現在，當您收到遞送警報通知時，下面是您可以執行的操作的一些提示。

首先，檢查送貨人 **日誌** 頁籤，查看與交貨和校樣相關的所有資訊。 紅色和黃色表徵圖允許您識別錯誤或警告。 紅色表徵圖指示阻止啟動傳遞的嚴重錯誤。

要查看交貨每次發生的歷史記錄，請選擇 **[!UICONTROL Sending logs]** 頁籤。 它包含已發送郵件及其狀態的清單。 您可以在此處檢查每個收件人的交貨狀態( **[!UICONTROL Sent]**。 **[!UICONTROL Pending]**。 **[!UICONTROL Failed]**&#x200B;等)。 有關此的詳細資訊，請參閱 [正在發送日誌](../../sending/using/monitoring-a-delivery.md#sending-logs)。

以下是根據交付時滿足的標準接收警報通知的幾個可能原因。

* **[!UICONTROL Deliveries failed]**:此條件通知您所有狀態錯誤的交貨。 原因可能是：

   * 傳遞伺服器（MTA、消息傳輸代理）出現問題
   * Adobe Campaign傳送伺服器與接收伺服器之間的連接超時
   * 可交付性問題
   * 錯誤的工作流

   如果使用工作流觸發傳遞，請檢查該工作流是否正確啟動。 有關此的詳細資訊，請參閱 [執行工作流](../../automating/using/about-workflow-execution.md)。 否則，請與您的Adobe Campaign管理員聯繫以解決問題。

* **[!UICONTROL Deliveries with preparation failed]**:在以下情況下，在交付準備過程中可能會出錯：

   * 交貨缺少主題。
   * 個性化欄位中的語法錯誤。
   * 目標丟失。
   * 交貨超出大小限制。

   有關此的詳細資訊，請參閱 [準備發送](../../sending/using/preparing-the-send.md)。 但是，在消息分析過程中通常會發現這些錯誤。 請參閱 [控制規則](../../sending/using/control-rules.md)。

* 可能的原因 **[!UICONTROL Delivery with bad error ratio for soft bounces]** 警報可以是：

   * 收件人的伺服器已關閉。
   * 收件人的郵箱已滿。

   有關詳細資訊，請檢查 **[!UICONTROL Exclusion logs]** 和 **[!UICONTROL Exclusion causes]** 的子菜單。 請參閱 [排除日誌](../../sending/using/monitoring-a-delivery.md#exclusion-logs)。

   可能的原因 **[!UICONTROL Delivery with bad error ratio for hard bounces]** 警報可以是：

   * 收件人將添加到denylist中，這意味著他們不再希望與其聯繫。
   * 收件人的電子郵件地址不存在。
   * 收件人的域不存在。
   * 收件人的伺服器正在阻止傳遞。

   要避免軟和硬彈跳錯誤，請遵循以下最佳實踐：

   * 構建篩選類型規則以在傳遞分析期間排除郵件目標的一部分，如隔離的收件人。 請參閱 [建立篩選規則](../../sending/using/filtering-rules.md)。
   * 定期更新客戶資料庫以維護良好的隔離管理流程。 請參閱 [關於隔離](../../sending/using/understanding-quarantine-management.md#about-quarantines)。
   * 一般來說，盡可能提高交付能力。 見Adobe Campaign [可交付性](../../sending/using/about-deliverability.md) 詳細文檔並與Adobe Campaign管理員聯繫以獲取幫助。



* **[!UICONTROL Deliveries with long start pending]**:這通常意味著在MTA（消息傳送代理）級別存在問題。 執行過程正在等待某些資源的可用性。 MTA可能尚未啟動。

   **[!UICONTROL Deliveries with low throughput]**:同樣，這是一個可交付性問題，意味著MTA太慢。

   有關這些問題的詳細資訊，請與您的Adobe Campaign管理員聯繫。

**相關主題：**

* [瞭解傳遞故障](../../sending/using/understanding-delivery-failures.md)
* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [關於 Campaign 中的選擇加入和選擇退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
