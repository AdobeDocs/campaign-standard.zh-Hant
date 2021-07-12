---
solution: Campaign Standard
product: campaign
title: 發生故障時接收警示
description: 了解如何使用警報管理系統。
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: 校樣
role: User
level: Beginner
exl-id: dc8bd1d3-e199-4901-9b1f-7b485879897d
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '2032'
ht-degree: 2%

---

# 發生故障時接收警示{#receiving-alerts-when-failures-happen}

## 關於傳送警報 {#about-delivery-alerting}

**傳送警報**&#x200B;功能是警報管理系統，可讓一組使用者自動接收包含其傳送執行資訊的通知。

所傳送的通知會依預設包含以下條件的報表：

* 傳送失敗
* 準備失敗的傳送
* 軟跳出錯誤率不佳的傳送
* 硬跳出錯誤率不佳的傳送
* 狀態為待定的傳送比平常長
* 吞吐量低的傳送
* 正在傳送

警報的收件者可監控Adobe Campaign正在處理的傳送，並在執行中發生問題時採取適當動作。

這些警報通知可根據特定警報標準自訂，這些警報標準是透過Adobe Campaign介面中的控制面板定義。

>[!NOTE]
>
>警報通知僅由電子郵件傳送。

傳送的通知包含：

* **[!UICONTROL Summary]**&#x200B;顯示符合您定義的准則的傳送數量，以及您為每個准則選擇的標籤/顏色。
* **[!UICONTROL Details]**&#x200B;區段會列出針對對應控制面板定義的所有傳送條件，以及每個條件的所有傳送。

![](assets/delivery-alerting_notification.png)

## 傳送警報控制面板 {#delivery-alerting-dashboards}

### 關於傳送警報控制面板 {#about-delivery-alerting-dashboards}

若要管理通知的收件者，請定義警報標準並存取警報記錄，您需要使用控制面板。

>[!NOTE]
>
>若要存取和設定控制面板和警報標準，您必須擁有管理權限或出現在&#x200B;**傳送監督者**&#x200B;安全群組中。 標準使用者無法存取Adobe Campaign介面中的控制面板。 他們只能接收警報通知。 如需Adobe Campaign中使用者與安全性的詳細資訊，請參閱[使用者類型](../../administration/using/users-management.md)和[關於安全性群組](../../administration/using/managing-groups-and-users.md#about-security-groups)。

從Adobe Campaign介面，您可以：

* 建立和管理傳送警報控制面板。 請參閱[建立傳送警報控制面板](#creating-a-delivery-alerting-dashboard)。
* 定義和管理每個控制面板的傳送警報標準。 例如，您可以根據準備失敗的傳送或只有低吞吐量的傳送來建立警報。 請參閱[關於警報條件](#about-alerting-criteria)。
* 修改每個控制面板的條件參數。 請參閱[條件參數](#criteria-parameters)。
* 為每個控制面板定義一組收件者。

   例如，您只想通知具有管理權限的使用者已失敗的傳送。 不過，您希望行銷使用者以軟跳出錯誤率接收有關傳送的資訊。 因此，您需要建立兩個不同的控制面板，並定義每個收件者群組所需的條件。

* 存取每個控制面板所有已傳送警報的歷史記錄。

   選取控制面板時，預設會顯示此控制面板的上次傳送警報。 所有已傳送的警報都會列在畫面左側。 按一下&#x200B;**[!UICONTROL History]**&#x200B;清單中的項目以存取對應的警報。

![](assets/delivery-alerting_dashboard.png)

### 建立傳送警報控制面板 {#creating-a-delivery-alerting-dashboard}

如果您想要根據特定條件傳送通知給不同的使用者群組，則需要使用數個控制面板。 若要建立新控制面板：

1. 前往 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**。
1. 選取 **[!UICONTROL Delivery alerting dashboards]** 並按一下 **[!UICONTROL Create]**。
1. 勾選&#x200B;**[!UICONTROL Enabled]**&#x200B;方塊以啟用目前的控制面板。

   如果停用此選項，則不再傳送連結至此控制面板的通知。 預設會停用此選項。

   ![](assets/delivery-alerting_dashboard_general.png)

1. 從&#x200B;**[!UICONTROL Alert group]**&#x200B;下拉清單中選擇要通知的收件者組。 要修改或建立組，請參閱[建立安全組並分配用戶](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users)。
1. 在&#x200B;**[!UICONTROL Delivery alerting criteria]**&#x200B;區段中，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;以新增條件。 請參閱[關於警報條件](#about-alerting-criteria)。
1. 選取 **[!UICONTROL Edit properties]** 按鈕。在&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;標籤中，定義要如何套用條件。 請參閱[條件參數](#criteria-parameters)。
1. 按一下&#x200B;**[!UICONTROL Create]**&#x200B;以儲存控制面板。

現在，每當傳送符合您在此控制面板中定義的准則時，警報通知就會傳送至指定的使用者群組。

## 傳送警報條件 {#delivery-alerting-criteria}

### 關於警報條件 {#about-alerting-criteria}

若要存取傳送警報條件，請前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**&#x200B;並選取&#x200B;**[!UICONTROL Delivery alerting criteria]**。

![](assets/delivery-alerting_criteria.png)

下列條件可用於傳送警報控制面板：

* **[!UICONTROL Deliveries failed]**:在定義範圍內排程的任何傳送，皆顯示錯誤狀態。
* **[!UICONTROL Deliveries with preparation failed]**:在定義範圍內修改的任何傳送，其準備步驟（目標計算和內容產生）已失敗。如需詳細資訊，請參閱[準備傳送](../../sending/using/preparing-the-send.md)。
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**:在定義範圍內排程的任何傳送，其狀態至少 **[!UICONTROL In progress]**&#x200B;為，軟退信錯誤率大於定義的百分比。
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**:在定義範圍內排程的任何傳送，其狀態至少為 **[!UICONTROL In progress]**，且硬退信錯誤率大於定義的百分比。
* **[!UICONTROL Deliveries with long start pending]**:在定義範圍內排程的任何傳送， **[!UICONTROL Start pending]** 其狀態會長於定義的持 **[!UICONTROL Start pending]** 續時間，狀態表示系統尚未考慮訊息。
* **[!UICONTROL Deliveries with low throughput]**:任何開始傳送的時間都超過定義的持續時間，且少於已處理訊息的定義百分比，且吞吐量低於定義值。
* **[!UICONTROL Deliveries in progress]**:在定義範圍內排程的任何傳送，且狀態 **[!UICONTROL In progress]** 為。

>[!NOTE]
>
>套用至上述條件的所有參數皆有預設值。 這些值可在傳送警報控制面板的&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;標籤中變更。 請參閱[條件參數](#criteria-parameters)。

您可以從&#x200B;**[!UICONTROL Delivery alerting criteria]**&#x200B;清單中選擇任何項目以訪問其詳細資訊。

![](assets/delivery-alerting_criteria_definition.png)

對於每個條件，您可以定義下列設定：

* **[!UICONTROL Indicators to add in alerts]**，表示與所選准則對應之傳送， **[!UICONTROL Details]** 通知區段中將顯示的欄。

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**，表示通知摘要中傳送標準旁會出現的標籤和顏色。

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**:如果一個傳送符合標準，則在監控期間內發送的每個通知中重複該標準。否則，對於一個傳送，根據警報標準，一天只會傳送一個警報（第一次發生時）。

   依預設，所有條件的此選項會設為每天一次。

**相關主題：**

* [傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [警報頻率](#alerting-frequency)
* [行銷活動圖示和狀態](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### 建立傳送警報標準 {#creating-a-delivery-alerting-criterion}

您可以建立新的傳送警報條件，以更符合您的需求。

例如，您可以建立新條件，以傳送列出狀態為&#x200B;**[!UICONTROL Finished]**&#x200B;之所有傳送的通知。

若要這麼做，您必須先擴充&#x200B;**Delivery**&#x200B;資源，並新增篩選器，讓您只能選取狀態為&#x200B;**[!UICONTROL Finished]**&#x200B;的傳送。

1. 前往&#x200B;**Adobe Campaign** > **Administration** > **Development** > **Custom resources**，然後按一下&#x200B;**[!UICONTROL Create]**。
1. 選擇&#x200B;**[!UICONTROL Extend an existing resource]**，從下拉清單中選擇&#x200B;**[!UICONTROL Delivery]**&#x200B;資源，然後按一下&#x200B;**[!UICONTROL Create]**&#x200B;進行編輯。

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   有關擴展現有資源的詳細資訊，請參閱[定義資源](../../developing/using/creating-or-extending-the-resource.md)。

1. 在&#x200B;**[!UICONTROL Delivery]**&#x200B;資源中，前往&#x200B;**[!UICONTROL Filter definition]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add an element]**&#x200B;以建立篩選器。

   ![](assets/delivery-alerting_new-filter.png)

1. 編輯新篩選器定義：在&#x200B;**[!UICONTROL Filter definition]**&#x200B;視窗中，將&#x200B;**[!UICONTROL Status]**&#x200B;項目拖放至工作區中，並選取&#x200B;**[!UICONTROL Finished]**&#x200B;作為篩選條件。

   ![](assets/delivery-alerting_filter-status.png)

   如需建立和編輯自訂篩選器的詳細資訊，請參閱[定義篩選器](../../developing/using/configuring-filter-definition.md)。

1. 儲存您的變更並發佈資源。 如需詳細資訊，請參閱[發佈自訂資源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   篩選器已建立，現在可以在新的傳送警報標準中選取。

1. 前往&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**，選取&#x200B;**[!UICONTROL Delivery alerting criteria]**，然後按一下&#x200B;**[!UICONTROL Create]**。
1. 在&#x200B;**[!UICONTROL Delivery filter applied by this criterion]**&#x200B;下拉式清單中，選取您剛建立的篩選器。

   ![](assets/delivery-alerting_cus-filter.png)

   您可以使用與預設條件相同的方式來定義條件的設定。 請參閱[關於警報條件](#about-alerting-criteria)。

建立後，這些條件即可新增至傳送警報控制面板及其他條件。 請參閱[關於傳送警報控制面板](#about-delivery-alerting-dashboards)。

![](assets/delivery-alerting_new-criterion.png)

**相關主題：**

[新增或擴充資源](../../developing/using/key-steps-to-add-a-resource.md)

## 傳送警報參數 {#delivery-alerting-parameters}

### 條件參數 {#criteria-parameters}

在[傳送警報控制面板](#creating-a-delivery-alerting-dashboard)的&#x200B;**[!UICONTROL Criteria parameters]**&#x200B;標籤中，您可以定義套用至此控制面板中所選准則的設定。

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**:例如，如果您在此欄位中輸入100，則只會針對目標等於或大於100個收件者的傳送傳送傳送通知。此參數會套用至所有條件。
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**:目前時間之前和之後的小時數。系統只會考慮在此時間範圍內具有聯絡日期的傳送。 此參數會套用至所有條件。 依預設，此欄位的值會設為24小時。

   有關聯繫日期的詳細資訊，請參閱[關於計畫](../../sending/using/about-scheduling-messages.md)。

* **[!UICONTROL Maximum ratio of soft bounce errors]**:所有傳送都會傳送通知，其軟退信錯誤率大於指定值。依預設，此欄位的值會設為0.05(5%)。

   有關軟退信錯誤的詳細資訊，請參閱[退信限定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)和[傳送失敗類型清單](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Maximum ratio of hard bounce errors]**:所有傳送都會傳送通知，且硬退信錯誤率大於指定值。依預設，此欄位的值會設為0.05(5%)。

   有關硬退信錯誤的詳細資訊，請參閱[退信限定](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)和[傳送失敗類型清單](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)。

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**:對於狀態超過此欄位中指 **[!UICONTROL Start pending]** 定持續時間的所有傳送， **[!UICONTROL Start pending]** 會傳送通知，表示系統尚未考慮訊息。
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**:條件只會考 **[!UICONTROL In progress]** 慮超過指定持續時間的已開始傳送(狀態 **[!UICONTROL Deliveries with low throughput]** )。
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**:只有處理訊息的百分比低於指定百分比的傳送才會考慮此 **[!UICONTROL Deliveries with low throughput]** 准則。
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**:此准則只會考慮吞吐量低於指定值的傳 **[!UICONTROL Deliveries with low throughput]** 送。
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**:只考慮處理訊息百分比高於指定百分比的傳送。

### 警報頻率 {#alerting-frequency}

**[!UICONTROL Frequency of delivery alerting]**&#x200B;選項可定義兩個警報傳送之間的延遲。 預設會設為10分鐘。

您可以透過&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;功能表變更此設定。

>[!NOTE]
>
>此選項適用於Adobe Campaign中定義的所有控制面板。 您無法為每個控制面板設定特定頻率。

## 傳送警報原因 {#delivery-alerting-reasons}

**傳送警報**&#x200B;功能可透過電子郵件和控制面板，讓所有相關的Adobe Campaign使用者自動得知傳送執行狀態。

現在，當您收到傳送警報通知時，以下提供一些您可以執行的秘訣。

首先，檢查傳送的&#x200B;**Log**&#x200B;標籤，以檢視與傳送和校樣相關的所有資訊。 紅色和黃色圖示可讓您識別錯誤或警告。 紅色圖示表示無法開始傳送的重大錯誤。

若要檢視傳送每次發生的歷史記錄，請選取&#x200B;**[!UICONTROL Sending logs]**&#x200B;標籤。 它包含已傳送訊息的清單及其狀態。 您可以在此處檢查每個收件者（**[!UICONTROL Sent]**、**[!UICONTROL Pending]**、**[!UICONTROL Failed]**&#x200B;等）的傳送狀態。 如需詳細資訊，請參閱[傳送記錄檔](../../sending/using/monitoring-a-delivery.md#sending-logs)。

根據傳送符合的條件接收警報通知的幾個可能原因如下。

* **[!UICONTROL Deliveries failed]**:此條件會通知您所有狀態有錯誤的傳送。可能是因為：

   * 傳送伺服器（MTA、訊息傳輸代理）出現問題
   * Adobe Campaign傳送伺服器與接收伺服器之間的連線逾時
   * 傳遞能力問題
   * 錯誤的工作流程

   如果傳送是透過工作流程觸發，請檢查該工作流程是否正確啟動。 有關詳細資訊，請參閱[執行工作流](../../automating/using/about-workflow-execution.md)。 否則，請聯絡您的Adobe Campaign管理員以解決問題。

* **[!UICONTROL Deliveries with preparation failed]**:在下列情況下，在準備傳送時可能會發生錯誤：

   * 傳遞缺少主題。
   * 個人化欄位中的語法錯誤。
   * 目標丟失。
   * 傳送超過大小限制。

   如需詳細資訊，請參閱[準備傳送](../../sending/using/preparing-the-send.md)。 不過，在訊息分析期間通常會發現這些錯誤。 請參閱[控制規則](../../sending/using/control-rules.md)。

* **[!UICONTROL Delivery with bad error ratio for soft bounces]**&#x200B;警報的可能原因可能是：

   * 收件者的伺服器關閉。
   * 收件者的信箱已滿。

   如需詳細資訊，請檢查傳送記錄檔的&#x200B;**[!UICONTROL Exclusion logs]**&#x200B;和&#x200B;**[!UICONTROL Exclusion causes]**&#x200B;標籤。 請參閱[排除記錄](../../sending/using/monitoring-a-delivery.md#exclusion-logs)。

   **[!UICONTROL Delivery with bad error ratio for hard bounces]**&#x200B;警報的可能原因可能是：

   * 收件者會新增至封鎖清單，表示他們不想再聯絡。
   * 收件者的電子郵件地址不存在。
   * 收件者的網域不存在。
   * 收件者的伺服器正在封鎖傳送。

   若要避免軟退信和硬退信錯誤，請遵循下列最佳實務：

   * 建立篩選類型規則，以在傳送分析期間排除訊息目標的一部分，例如隔離的收件者。 請參閱[建立篩選規則](../../sending/using/filtering-rules.md)。
   * 定期更新客戶資料庫以維護良好的隔離管理流程。 請參閱[關於隔離](../../sending/using/understanding-quarantine-management.md#about-quarantines)。
   * 一般而言，請盡可能改善傳遞能力。 請參閱Adobe Campaign [傳遞能力](../../sending/using/about-deliverability.md)詳細檔案，並聯絡您的Adobe Campaign管理員以取得協助。



* **[!UICONTROL Deliveries with long start pending]**:這通常表示在MTA（訊息傳輸代理）層級有問題。執行程式正在等待某些資源的可用性。 MTA可能尚未啟動。

   **[!UICONTROL Deliveries with low throughput]**:同樣地，這是傳遞能力問題，表示MTA太慢。

   如需這些問題的詳細資訊，請聯絡您的Adobe Campaign管理員。

**相關主題：**

* [瞭解傳遞故障](../../sending/using/understanding-delivery-failures.md)
* [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)
* [關於 Campaign 中的選擇加入和選擇退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
