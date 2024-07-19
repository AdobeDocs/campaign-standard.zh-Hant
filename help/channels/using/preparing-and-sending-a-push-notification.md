---
title: 建立和傳送推播通知
description: 請依照下列步驟，在Adobe Campaign中建立單一傳送的推播通知。
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
source-wordcount: '841'
ht-degree: 3%

---

# 準備和傳送推送通知{#preparing-and-sending-a-push-notification}

## 準備通知 {#preparing-the-notification}

使用Adobe Campaign建立推播通知的步驟如下：

1. 從&#x200B;**[!UICONTROL Marketing activities]**&#x200B;視窗，[建立新的行銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   請注意，您也可以從[行銷活動](../../start/using/marketing-activities.md#creating-a-marketing-activity)或Adobe Campaign [首頁](../../start/using/interface-description.md#home-page)建立單一推播通知。

   您也可以在工作流程中使用推播通知傳送活動。 此活動會顯示在[推播通知傳遞](../../automating/using/push-notification-delivery.md)區段中。

1. 選取 **[!UICONTROL Push notification]**。
1. 選取範本。

   ![](assets/push_notif_type.png)

   依預設，您可以選取下列兩個範本之一：

   * **[!UICONTROL Send push to Campaign profiles]**：使用此範本來鎖定已訂閱您的行動應用程式並選擇接收推播通知的Adobe Campaign CRM設定檔。 您可以將[個人化](../../designing/using/personalization.md#inserting-a-personalization-field)欄位插入推播通知，例如收件者的名字。
   * **[!UICONTROL Send push to app subscribers]**：使用此範本將推播通知傳送給所有選擇從您的應用程式接收通知的已知和匿名行動應用程式使用者。 您可以使用從行動應用程式收集的資料來個人化這些訊息。

   您也可以選取多語言範本。 如需詳細資訊，請參閱[建立多語言推播通知](../../channels/using/creating-a-multilingual-push-notification.md)。

   如需範本的詳細資訊，請參閱[管理範本](../../start/using/marketing-activity-templates.md)區段。

1. 輸入您的推播通知屬性，並在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;欄位中選取您的行動應用程式。

   請注意，下拉式清單會同時顯示SDK V4和Experience Platform SDK應用程式。

   ![](assets/push_notif_properties.png)

   您可以將推播通知連結至行銷活動。 若要這麼做，請從已建立的行銷活動中選取它。

1. 在下列畫面中，您可以指定對象，例如訂閱特定行動應用程式的所有VIP客戶。 如需詳細資訊，請參閱[建立對象](../../audiences/using/creating-audiences.md)。

   系統將會根據上個步驟中選取的行動應用程式，自動篩選您的對象。

   ![](assets/push_notif_audience.png)

1. 您現在可以自訂推播通知。 首先，選擇訊息樣式： **[!UICONTROL Alert/Message/Badge]**&#x200B;或&#x200B;**[!UICONTROL Silent push]**。 在[關於推播通知](../../channels/using/about-push-notifications.md)區段中說明推播通知型別。

   編輯推播通知的內容並定義進階選項。 請參閱[自訂推播通知](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/push_notif_content.png)

   在此設定的推播通知內容和選項會以裝載的形式傳遞至您的行動應用程式。 在[瞭解Campaign Standard推播通知裝載結構](../../administration/using/push-payload.md)技術檔案中描述了裝載的詳細結構。

1. 按一下&#x200B;**[!UICONTROL Create]**。

   ![](assets/push_notif_content_2.png)

1. 在傳送通知之前，您可以使用測試設定檔進行測試，然後在傳送傳遞之前檢視收件者將看到的內容。 從您的傳遞摘要中選取&#x200B;**[!UICONTROL Audiences]**，然後按一下&#x200B;**[!UICONTROL Test profiles]**&#x200B;索引標籤。

   如需傳送測試的詳細資訊，請參閱[測試設定檔](../../sending/using/sending-proofs.md)。

1. 選取您的測試設定檔，然後按一下&#x200B;**[!UICONTROL Preview]**&#x200B;以顯示通知：內容已使用測試設定檔資料進行個人化。
1. 檢查不同裝置上的推播通知配置：選取iPhone、Android手機、iPad或Android平板電腦以預覽呈現。

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]**&#x200B;是根據測試設定檔資料的預估值。 實際裝載大小可能有所不同。 訊息的上限為4KB。

   >[!CAUTION]
   >
   >如果裝載大小超過4KB限制，則不會傳遞訊息。

請注意，個人化資料會影響訊息大小。

## 傳送通知 {#sending-the-notification}

推播通知可透過定義對象條件傳送給Adobe Campaign中選取的對象。 以下範例中，我們選取的對象包含4位目標行動應用程式訂閱者。

1. 按一下&#x200B;**[!UICONTROL Prepare]**&#x200B;以計算目標並產生通知。

   ![](assets/push_send_1.png)

1. 完成準備工作後，**[!UICONTROL Deployment]**&#x200B;視窗就會顯示下列KPI： **[!UICONTROL Target]**&#x200B;和&#x200B;**[!UICONTROL To deliver]**。 請注意，因為排除專案，**[!UICONTROL To deliver]**&#x200B;計數會低於&#x200B;**[!UICONTROL Targeted]**&#x200B;計數，您可以按一下&#x200B;**[!UICONTROL Deployment]**&#x200B;視窗底部的![](assets/lp_link_properties.png)按鈕來檢視排除專案。

   ![](assets/push_send_2.png)

1. 在&#x200B;**[!UICONTROL Exclusion logs]**&#x200B;索引標籤中，您可以找到從傳送目標排除的所有訊息清單，以及此排除背後的原因。

   在此，我們可以看到其中一個行動應用程式訂閱者已被排除，因為該位址在封鎖清單中，而其他訂閱者則因為該設定檔重複。

   ![](assets/push_send_5.png)

1. 按一下&#x200B;**[!UICONTROL Exclusion causes]**&#x200B;索引標籤以顯示排除的訊息數量。

   ![](assets/push_send_7.png)

1. 您現在可以按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;開始傳送推播通知。
1. 透過訊息儀表板和記錄檔檢查您的傳送狀態。如需詳細資訊，請參閱[傳送訊息](../../sending/using/confirming-the-send.md)及[傳遞記錄](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

   在此範例中，訊息控制面板顯示Adobe Campaign嘗試傳送兩個推播通知：一個已成功傳遞至裝置，另一個失敗。 若要瞭解傳遞發生錯誤的原因，請按一下&#x200B;**[!UICONTROL Deployment]**&#x200B;視窗底部的![](assets/lp_link_properties.png)按鈕。

   ![](assets/push_send_4.png)

1. 從&#x200B;**[!UICONTROL Deployment]**&#x200B;視窗，按一下&#x200B;**[!UICONTROL Sending logs]**&#x200B;標籤以存取已傳送推播通知及其狀態的清單。 對於此傳遞，一個推播通知已成功傳送，而另一個由於裝置權杖錯誤而失敗。 然後，會將此訂閱者新增至封鎖清單，以供後續傳遞使用。

   >[!NOTE]
   >
   >原因可能是Adobe Campaign下游的任何失敗。 如果apns和fcm等提供者失敗，原因也會反映出來。 如需提供者失敗的詳細資訊，請參閱[Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html)和[Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref)檔案。

   ![](assets/push_send_6.png)

您現在可以使用動態報告測量推播通知傳送的影響。

**相關主題：**

* [推播通知報告](../../reporting/using/push-notification-report.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)
