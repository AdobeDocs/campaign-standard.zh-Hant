---
title: 從Adobe Campaign Standard推播通知顯示影像
description: 在此處瞭解如何在iOS裝置上顯示Adobe Campaign推播通知的影像
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 474c8002-4263-4617-9480-6a9b603bde8e
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 12%

---

# 新增影像和影片 iOS {#image-push}

>[!NOTE]
>
>本檔案僅適用於iOS裝置。

在本檔案中，瞭解如何從Adobe Campaign Standard iOS推播通知顯示影像。

## 步驟1：設定推播通知 {#set-up-push}

Experience Platform SDK支援推播通知。

接收推播通知的行動應用程式必須由管理員在Adobe Campaign介面中設定。

透過設定Adobe Campaign和Adobe Mobile Services，您將能夠將行動應用程式的資料用於行銷活動。 如需關於此項目的詳細資訊，請參閱此[頁面](../../administration/using/configuring-a-mobile-application.md)。

若要使用Experience Cloud SDK應用程式傳送推播通知，必須在資料收集UI中設定行動應用程式，並在Adobe Campaign中設定。 如需關於此項目的詳細資訊，請參閱此[頁面](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

## 步驟2：在Adobe Campaign中自訂推播通知 {#customize-push}

為了微調您的推播通知，Adobe Campaign 可讓您在設計推播通知時存取一組進階選項。

1. 建立推播通知。 如需關於此項目的詳細資訊，請參閱此[頁面](../../channels/using/preparing-and-sending-a-push-notification.md)。

1. 從推播通知內容頁面，存取&#x200B;**[!UICONTROL Advanced options]**&#x200B;區段。

1. 在&#x200B;**[!UICONTROL Rich media content URL]**欄位中輸入檔案的URL。
若是iOS 10或更新版本，您可以插入影像、gif、音訊和視訊檔案。

   ![](assets/push_notif_advanced_6.png)

1. 預覽並儲存推播通知。

## 步驟3：調整行動應用程式的程式碼 {#mobile-app-code}

在Adobe Campaign中自訂推播通知後，您必須設定行動應用程式以在裝置上顯示影像。

>[!NOTE]
>
>如果您的應用程式位於Objective-C，請參閱下列[檔案](https://experienceleague.adobe.com/docs/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html)。

如果您的應用程式在[!DNL Swift]中，請遵循下列步驟：

1. 開啟您的[!DNL Xcode]專案。

1. 在您的[!DNL Xcode]專案中，選取&#x200B;**[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**。

1. 選取 **[!UICONTROL Notification Service Extension]**。

   ![](assets/push_notif_advanced_12.png)

1. 檢查是否已建立&#x200B;**NotificationService.swift**&#x200B;檔案類別。

1. 編輯此類別並使用以下內容取代預設內容。
這可讓應用程式使用影像URL處理傳入引數、剖析、複製至本機，然後從推播通知顯示引數。

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

行動裝置在傳送通知時應接收下列裝載。

影像URL已對應到關鍵media-attachment-url。 這是您從應用程式程式碼的角度來看，必須處理的機碼/值組，才能下載和顯示影像。

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

## 步驟4：測試傳送推播 {#test-send-push}

您現在可以測試建置應用程式，以及您在上面的步驟2中建立的傳送。 如需準備和傳送推播通知的詳細資訊，請參閱此[頁面](../../channels/using/preparing-and-sending-a-push-notification.md)。

![](assets/push_notif_advanced_34.png)
