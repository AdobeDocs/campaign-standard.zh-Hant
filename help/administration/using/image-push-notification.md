---
title: 從 Adobe Campaign Standard 推播通知顯示影像
description: 在此處瞭解如何在iOS設備上顯示Adobe Campaign推送通知中的影像
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 474c8002-4263-4617-9480-6a9b603bde8e
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 18%

---

# 新增影像和影片 iOS {#image-push}

>[!NOTE]
>
>此文檔僅適用於iOS設備。

在本文檔中，瞭解如何從Adobe Campaign StandardiOS推送通知中顯示影像。

## 步驟1:設定推送通知 {#set-up-push}

Experience PlatformSDK支援推送通知。

接收推送通知的移動應用程式必須由Adobe Campaign介面中的管理員配置。

通過配置Adobe Campaign和Adobe移動服務，您將能夠將移動應用程式的資料用於您的活動。 如需關於此項目的詳細資訊，請參閱此[頁面](../../administration/using/configuring-a-mobile-application.md)。

要使用Experience CloudSDK應用程式發送推送通知，必須在資料收集UI中設定移動應用，並在Adobe Campaign配置。 如需關於此項目的詳細資訊，請參閱此[頁面](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

## 步驟2:在Adobe Campaign自定義推送通知 {#customize-push}

為了微調您的推播通知，Adobe Campaign 可讓您在設計推播通知時存取一組進階選項。

1. 自訂推播通知. 如需關於此項目的詳細資訊，請參閱此[頁面](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 從推送通知內容頁面，訪問 **[!UICONTROL Advanced options]** 的子菜單。

1. 在 **[!UICONTROL Rich media content URL]** 的子菜單。
若是 iOS 10 或更新版本，您可以插入影像、gif、音訊和視訊檔案。

   ![](assets/push_notif_advanced_6.png)

1. 預覽並保存推送通知。

## 第3步：調整移動應用程式碼 {#mobile-app-code}

在Adobe Campaign自定義推送通知後，必須配置移動應用程式以在設備上顯示影像。

>[!NOTE]
>
>如果您的應用程式位於Objective-C中，請參閱以下內容 [文檔](https://experienceleague.adobe.com/docs/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html)。

如果你的應用在 [!DNL Swift]，請執行以下步驟：

1. 開啟 [!DNL Xcode] 項目。

1. 在 [!DNL Xcode] 項目，選擇 **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**。

1. 選取 **[!UICONTROL Notification Service Extension]**。

   ![](assets/push_notif_advanced_12.png)

1. 檢查 **NotificationService.swift** 檔案類。

1. 編輯此類，並用以下內容替換預設內容。
這允許應用程式使用影像URL處理傳入參數，分析它，在本地複製它，然後從推送通知中顯示它。

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

發送通知時，移動設備應接收以下負載。

影像URL用鍵media-attachment-url映射。 這是從應用程式碼角度必須處理的鍵/值對，才能下載和顯示影像。

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## 第4步：Test發送推送 {#test-send-push}

現在，您可以test構建應用程式和在上面步驟2中建立的交付。 有關準備和發送推送通知的詳細資訊，請參閱此 [頁](../../channels/using/preparing-and-sending-a-push-notification.md)。

![](assets/push_notif_advanced_34.png)
