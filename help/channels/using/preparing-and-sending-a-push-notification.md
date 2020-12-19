---
solution: Campaign Standard
product: campaign
title: 建立並傳送推播通知
description: 請依照下列步驟，在Adobe Campaign中建立單一傳送推播通知。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 4%

---


# 準備和傳送推播通知{#preparing-and-sending-a-push-notification}

## 準備通知{#preparing-the-notification}

使用Adobe Campaign建立推播通知的步驟如下：

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;視窗中，[建立新的行銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   請注意，您也可以從[促銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)或從Adobe Campaign [首頁](../../start/using/interface-description.md#home-page)建立單一推播通知。

   您也可以在工作流程中使用推播通知傳送活動。 此活動顯示在[推播通知傳送](../../automating/using/push-notification-delivery.md)區段中。

1. 選取 **[!UICONTROL Push notification]**。
1. 選取範本。

   ![](assets/push_notif_type.png)

   依預設，您可以選取下列兩個範本之一：

   * **[!UICONTROL Send push to Campaign profiles]**:使用此範本來定位已訂閱您行動應用程式並選擇接收推播通知的Adobe Campaign CRM設定檔。您可以將[personalization](../../designing/using/personalization.md#inserting-a-personalization-field)欄位插入您的推播通知，例如收件者的名字。
   * **[!UICONTROL Send push to app subscribers]**:使用此範本，將推播通知傳送給所有已知和匿名行動應用程式使用者，這些使用者已選擇從您的應用程式接收通知。您可以透過從行動應用程式收集的資料個人化這些訊息。

   您也可以選擇多語言範本。 如需詳細資訊，請參閱「建立多語言推播通知[」。](../../channels/using/creating-a-multilingual-push-notification.md)

   有關模板的詳細資訊，請參閱[管理模板](../../start/using/marketing-activity-templates.md)部分。

1. 輸入您的推播通知屬性，並在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;欄位中選取您的行動應用程式。

   請注意，下拉式清單將同時顯示SDK V4和Experience Platform SDK應用程式。

   ![](assets/push_notif_properties.png)

   您可以將推播通知連結至促銷活動。 若要這麼做，請從已建立的促銷活動中選取它。

1. 在下列畫面中，您可以指定對象，例如所有訂閱特定行動應用程式的VIP客戶。 如需詳細資訊，請參閱[建立觀眾](../../audiences/using/creating-audiences.md)。

   系統會根據上一步驟中選取的行動應用程式，自動篩選您的觀眾。

   ![](assets/push_notif_audience.png)

1. 您現在可以自訂推播通知。 首先，選擇消息樣式：**[!UICONTROL Alert/Message/Badge]**&#x200B;或&#x200B;**[!UICONTROL Silent push]**。 推播通知類型在[關於推播通知](../../channels/using/about-push-notifications.md)區段中有說明。

   編輯推播通知的內容並定義進階選項。 請參閱[自訂推播通知](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/push_notif_content.png)

   此處設定的推播通知內容和選項會以裝載的形式傳遞至您的行動應用程式。 [瞭解ACS推播通知有效載荷結構](https://helpx.adobe.com/tw/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)技術中介紹了有效載荷的詳細結構。

1. 按一下 **[!UICONTROL Create]**。

   ![](assets/push_notif_content_2.png)

1. 在傳送通知之前，您可以使用測試設定檔來測試通知，然後在傳送傳送之前，先查看收件者將看到的內容。 從傳送摘要中選擇&#x200B;**[!UICONTROL Audiences]**，然後按一下&#x200B;**[!UICONTROL Test profiles]**&#x200B;頁籤。

   如需傳送測試的詳細資訊，請參閱[測試描述檔](../../sending/using/sending-proofs.md)。

1. 選擇您的測試設定檔，然後按一下&#x200B;**[!UICONTROL Preview]**&#x200B;以顯示通知：內容會與測試描述檔資料個人化。
1. 檢查不同裝置上的推播通知配置：選取iPhone、Android手機、iPad或Android平板電腦以預覽演算。

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]**&#x200B;是根據測試描述檔資料的估計值。 實際負載大小可能有所不同。 訊息的限制為4KB。

   >[!CAUTION]
   >
   >如果裝載大小超過4KB限制，則不會傳送訊息。

請注意，個人化資料會影響訊息的大小。

## 傳送通知{#sending-the-notification}

推播通知可透過定義對象條件，傳送至Adobe Campaign中的選定對象。 在下列範例中，我們選取的對象包括4個目標行動應用程式訂閱者。

1. 按一下&#x200B;**[!UICONTROL Prepare]**&#x200B;計算目標並生成通知。

   ![](assets/push_send_1.png)

1. 準備成功完成後，**[!UICONTROL Deployment]**&#x200B;窗口將顯示以下KPI:**[!UICONTROL Target]**&#x200B;和&#x200B;**[!UICONTROL To deliver]**。 請注意，由於排除項目，**[!UICONTROL To deliver]**&#x200B;計數低於&#x200B;**[!UICONTROL Targeted]**&#x200B;計數，您可按一下&#x200B;**[!UICONTROL Deployment]**&#x200B;視窗底部的![](assets/lp_link_properties.png)按鈕來檢視這些項目。

   ![](assets/push_send_2.png)

1. 在&#x200B;**[!UICONTROL Exclusion logs]**&#x200B;標籤中，您可以找到從已傳送的目標中排除的所有消息的清單以及排除的原因。

   在這裡，我們可以看到我們的行動應用程式訂閱者被排除，因為該位址在登入清單上，而其他訂閱者則因為描述檔是重複的。

   ![](assets/push_send_5.png)

1. 按一下&#x200B;**[!UICONTROL Exclusion causes]**&#x200B;頁籤以顯示已排除消息的卷。

   ![](assets/push_send_7.png)

1. 您現在可以按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;開始傳送推播通知。
1. 透過訊息儀表板和記錄檔檢查您的傳送狀態。有關詳細資訊，請參閱[發送消息](../../sending/using/confirming-the-send.md)和[發送日誌](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

   在此範例中，訊息控制面板會顯示Adobe Campaign嘗試傳送兩個推播通知：一個設備已成功傳送到設備，另一個設備失敗。 要瞭解傳送錯誤的原因，請按一下&#x200B;**[!UICONTROL Deployment]**&#x200B;窗口底部的![](assets/lp_link_properties.png)按鈕。

   ![](assets/push_send_4.png)

1. 在&#x200B;**[!UICONTROL Deployment]**&#x200B;視窗中，按一下&#x200B;**[!UICONTROL Sending logs]**&#x200B;標籤以存取已傳送的推播通知清單及其狀態。 對於此傳送，一個推播通知已成功傳送，而另一個則因裝置Token錯誤而失敗。 然後，此訂閱者會從進一步的傳送新增至denylist。

   >[!NOTE]
   >
   >原因可能是Adobe Campaign下游的任何失敗。 如果apns和fcm等提供者出現故障，原因也將反映出這一點。 有關提供者故障的詳細資訊，請參閱[Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html)和[Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref)檔案。

   ![](assets/push_send_6.png)

您現在可以使用動態報表測量推播通知傳送的影響。

**相關主題：**

* [推播通知報告](../../reporting/using/push-notification-report.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)
