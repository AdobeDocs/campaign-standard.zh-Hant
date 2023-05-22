---
title: 建立併發送推送通知
description: 按照以下步驟在Adobe Campaign建立單發推送通知。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 4%

---

# 準備和傳送推送通知{#preparing-and-sending-a-push-notification}

## 準備通知 {#preparing-the-notification}

與Adobe Campaign建立推送通知的步驟如下：

1. 從 **[!UICONTROL Marketing activities]** 窗口， [建立新的市場營銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   請注意，也可以從 [活動](../../start/using/marketing-activities.md#creating-a-marketing-activity) 或者Adobe Campaign [首頁](../../start/using/interface-description.md#home-page)。

   您還可以在工作流中使用推式通知傳遞活動。 本練習在 [推送通知傳遞](../../automating/using/push-notification-delivery.md) 的子菜單。

1. 選取 **[!UICONTROL Push notification]**。
1. 選取範本。

   ![](assets/push_notif_type.png)

   預設情況下，您可以選擇以下兩個模板之一：

   * **[!UICONTROL Send push to Campaign profiles]**:使用此模板可以針對已訂閱您的移動應用程式並選擇接收推送通知的Adobe CampaignCRM配置檔案。 可以插入 [個性化](../../designing/using/personalization.md#inserting-a-personalization-field) 按鈕。
   * **[!UICONTROL Send push to app subscribers]**:使用此模板向所有已選擇從應用程式接收通知的已知和匿名移動應用程式用戶發送推送通知。 您可以使用從移動應用程式收集的資料個性化這些消息。

   您也可以選擇多語言模板。 有關詳細資訊，請參閱 [建立多語言推送通知](../../channels/using/creating-a-multilingual-push-notification.md)。

   有關模板的詳細資訊，請參閱 [管理模板](../../start/using/marketing-activity-templates.md) 的子菜單。

1. 在中輸入您的推送通知屬性並選擇您的移動應用 **[!UICONTROL Associate a Mobile App to a delivery]** 的子菜單。

   請注意，下拉清單將同時顯示SDK V4和Experience PlatformSDK應用程式。

   ![](assets/push_notif_properties.png)

   您可以將推送通知連結到市場活動。 為此，請從已建立的市場活動中選擇它。

1. 在下面的螢幕中，您可以指定受眾，例如，所有訂VIP閱了特定移動應用程式的客戶。 有關此的詳細資訊，請參閱 [建立受眾](../../audiences/using/creating-audiences.md)。

   您的受眾將根據上一步中選擇的移動應用程式自動篩選。

   ![](assets/push_notif_audience.png)

1. 您現在可以自定義推送通知。 首先，選擇消息樣式： **[!UICONTROL Alert/Message/Badge]** 或 **[!UICONTROL Silent push]**。 推式通知類型在 [關於推式通知](../../channels/using/about-push-notifications.md) 的子菜單。

   編輯推送通知的內容並定義高級選項。 請參閱 [自定義推送通知](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/push_notif_content.png)

   此處配置的推送通知內容和選項將以有效負載的形式傳遞到您的移動應用程式。 有關有效載荷的詳細結構，請參見 [瞭解Campaign Standard推送通知負載結構](../../administration/using/push-payload.md) 技術。

1. 按一下&#x200B;**[!UICONTROL Create]**。

   ![](assets/push_notif_content_2.png)

1. 在發送通知之前，您可以將其與test配置檔案test，然後在發送傳送之前查看收件人將看到的內容。 選擇 **[!UICONTROL Audiences]** 摘要，然後按一下 **[!UICONTROL Test profiles]** 頁籤。

   有關發送test的詳細資訊，請參閱 [Test配置檔案](../../sending/using/sending-proofs.md)。

1. 選擇test配置檔案，然後按一下 **[!UICONTROL Preview]** 要顯示通知，請執行以下操作：使用test簡檔資料個性化內容。
1. 檢查不同設備上的推送通知佈局：選擇iPhone、安卓手機、iPad或安卓平板電腦預覽渲染。

   ![](assets/push_notif_preview.png)

1. 的 **[!UICONTROL Estimated Payload Size]** 是基於test配置檔案資料的估計。 實際負載大小可能有所不同。 消息的限制為4KB。

   >[!CAUTION]
   >
   >如果負載大小超過4KB限制，則不會傳遞消息。

請注意，個性化資料會影響消息的大小。

## 發送通知 {#sending-the-notification}

通過定義受眾標準，可以將推送通知發送到Adobe Campaign的選定受眾。 例如，我們選定的受眾包括4個目標移動應用訂閱者。

1. 按一下 **[!UICONTROL Prepare]** 計算目標並生成通知。

   ![](assets/push_send_1.png)

1. 準備成功完成後， **[!UICONTROL Deployment]** 窗口顯示以下KPI: **[!UICONTROL Target]** 和 **[!UICONTROL To deliver]**。 請注意 **[!UICONTROL To deliver]** 計數低於 **[!UICONTROL Targeted]** 一個原因是排除，可通過按一下 ![](assets/lp_link_properties.png) 按鈕 **[!UICONTROL Deployment]** 的子菜單。

   ![](assets/push_send_2.png)

1. 在 **[!UICONTROL Exclusion logs]** 頁籤，您可以找到從已發送的目標中排除的所有消息的清單以及此排除的原因。

   在這裡，我們可以看到我們的一個移動應用程式訂閱者被排除，因為該地址在denylist上，而其他訂閱者則因為該配置檔案是重複的。

   ![](assets/push_send_5.png)

1. 按一下 **[!UICONTROL Exclusion causes]** 頁籤，顯示已排除的消息的卷。

   ![](assets/push_send_7.png)

1. 您現在可以按一下 **[!UICONTROL Confirm]** 開始發送推送通知。
1. 透過訊息儀表板和記錄檔檢查您的傳送狀態。有關此的詳細資訊，請參閱 [發送消息](../../sending/using/confirming-the-send.md) 和 [交付日誌](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

   在此示例中，消息儀表板顯示Adobe Campaign試圖發送兩個推式通知：一個已成功傳送到設備，另一個失敗。 要瞭解傳遞錯誤的原因，請按一下 ![](assets/lp_link_properties.png) 按鈕 **[!UICONTROL Deployment]** 的子菜單。

   ![](assets/push_send_4.png)

1. 從 **[!UICONTROL Deployment]** 的 **[!UICONTROL Sending logs]** 頁籤，以訪問已發送推送通知及其狀態的清單。 對於此傳遞，一個推送通知已成功發送，而另一個推送通知由於設備令牌錯誤而失敗。 然後，此訂戶將從進一步交貨中添加到denylist。

   >[!NOTE]
   >
   >原因可能是Adobe Campaign下游的任何失敗。 如果apns和fcm等供應商出現故障，原因也將反映出這一點。 有關提供程式故障的詳細資訊，請參閱 [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) 和 [安卓](https://firebase.google.com/docs/cloud-messaging/http-server-ref) 文檔。

   ![](assets/push_send_6.png)

現在，您可以使用動態報告來衡量推送通知傳遞的影響。

**相關主題：**

* [推播通知報告](../../reporting/using/push-notification-report.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)
