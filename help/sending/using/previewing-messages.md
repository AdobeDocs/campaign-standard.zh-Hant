---
title: 預覽訊息
description: 了解如何在內容編輯器或電子郵件設計工具中預覽訊息。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Seed Address
role: User
level: Intermediate
exl-id: ac8c1265-f530-4438-ab2d-3ca17615ca85
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 15%

---

# 預覽傳遞 {#previewing-messages}

## 預覽電子郵件 {#previewing-emails}

Campaign Standard可讓您在傳送訊息之前預覽訊息，以檢查其個人化以及收件者如何看到訊息。

訊息預覽是使用您新增至訊息目標的&#x200B;**測試設定檔**&#x200B;來執行。

對於&#x200B;**email**&#x200B;訊息，Campaign Standard可讓您使用目標設定檔來預覽訊息，而非測試設定檔。 這可讓您取得特定設定檔將收到之訊息的精確表示。 如需詳細資訊，請參閱[使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)。

若要使用測試設定檔預覽訊息，請遵循下列步驟：

1. 在[電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)中，按一下&#x200B;**[!UICONTROL Preview]**&#x200B;按鈕。

   ![](assets/sending_preview.png)

   案頭檢視和您電子郵件的回應式行動檢視會並排顯示。

1. 每次預覽時都會執行自動反垃圾郵件檢查。 按一下&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;按鈕，了解更多有關警告的資訊。

   ![](assets/sending_anti-spam_analysis.png)

1. 選取&#x200B;**[!UICONTROL Change profile]**&#x200B;按鈕，以選擇要測試個人化元素的測試設定檔。

   ![](assets/sending_test-profile.png)

1. 要退出&#x200B;**[!UICONTROL Preview]**&#x200B;模式，請按一下螢幕左上角的&#x200B;**[!UICONTROL Edit]**&#x200B;按鈕。

   ![](assets/sending_preview_edit.png)

**相關主題**

* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)
* [傳送校樣](../../sending/using/sending-proofs.md)

## 預覽SMS訊息 {#previewing-sms}

對於&#x200B;**SMS**&#x200B;訊息，Campaign Standard可讓您使用測試設定檔預覽訊息。 這可讓您取得特定設定檔將收到之訊息的精確表示。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

若要使用測試設定檔預覽SMS訊息，請遵循下列步驟：

1. 填入SMS訊息的&#x200B;**[!UICONTROL Properties]**&#x200B;並選取對象後，您就可以個人化您的傳送。 如需詳細資訊，請參閱[section](../../channels/using/personalizing-sms-messages.md)。

   ![](assets/sms_preview.png)

1. 個人化內容後，按一下&#x200B;**[!UICONTROL Create]**&#x200B;以存取&#x200B;**[!UICONTROL Summary]**&#x200B;視窗。

1. 在&#x200B;**[!UICONTROL Summary]**&#x200B;視窗中，按一下&#x200B;**[!UICONTROL Content]**&#x200B;以開始預覽您的傳送。

   ![](assets/sms_preview_2.png)

1. 按一下工具列中的&#x200B;**[!UICONTROL Preview]**。

   ![](assets/sms_preview_3.png)

1. 按一下&#x200B;**[!UICONTROL Change profile]**，接著選取您的測試設定檔&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/sms_preview_4.png)

您現在可以根據選取的測試設定檔，看到訊息的確切表示。

**相關主題**

* [關於簡訊訊息](../../channels/using/about-sms-messages.md)
* [建立簡訊訊息](../../channels/using/creating-an-sms-message.md)
* [個人化簡訊訊息](../../channels/using/personalizing-sms-messages.md)

## 預覽推播通知 {#previewing-push}

對於&#x200B;**推播通知**,Campaign Standard可讓您使用測試設定檔預覽訊息。 這可讓您取得特定設定檔將收到之訊息的精確表示。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

若要使用測試設定檔預覽推播通知，請遵循下列步驟：

1. 填入推播通知的&#x200B;**[!UICONTROL Properties]**&#x200B;並選取對象後，您就可以個人化您的傳送。 如需詳細資訊，請參閱[自訂推播通知](../../channels/using/customizing-a-push-notification.md)。

1. 個人化內容後，您可以根據預覽視窗中的裝置和作業系統，直接檢查推播通知的轉譯。

   ![](assets/push_preview.png)

1. 若要使用測試設定檔預覽推播通知，請按一下&#x200B;**[!UICONTROL Preview with test profile]**。

   ![](assets/push_preview_2.png)

1. 依序選取您的測試設定檔&#x200B;**[!UICONTROL Confirm]**。

您現在可以根據選取的測試設定檔，看到訊息的確切表示。

![](assets/push_preview_3.png)

**相關主題**

* [關於推送通知](../../channels/using/about-push-notifications.md)
* [準備和傳送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [自訂推送通知](../../channels/using/customizing-a-push-notification.md)

## 預覽應用程式內訊息 {#previewing-in-app}

對於&#x200B;**應用程式內**,Campaign Standard可讓您使用測試設定檔預覽訊息。 這可讓您取得特定設定檔將收到之訊息的精確表示。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

若要使用測試設定檔預覽應用程式內訊息，請遵循下列步驟：

1. 填入應用程式內訊息的&#x200B;**[!UICONTROL Properties]**&#x200B;後，選取您的對象並設定您的&#x200B;**[!UICONTROL Triggers]**，您就可以個人化您的傳送。 如需詳細資訊，請參閱[自訂應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)。

1. 將內容個人化後，您可以根據預覽視窗中的裝置和作業系統，直接檢查應用程式內訊息的轉譯。

   ![](assets/in_app_preview.png)

1. 若要使用測試設定檔預覽應用程式內訊息，請按一下&#x200B;**[!UICONTROL Preview]**。

   ![](assets/in_app_preview_2.png)

1. 依序選取您的測試設定檔&#x200B;**[!UICONTROL Confirm]**。

您現在可以根據選取的測試設定檔，看到訊息的確切表示。

![](assets/in_app_preview_3.png)

**相關主題**

* [關於應用程式內訊息傳送](../../channels/using/about-in-app-messaging.md)
* [準備和傳送應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [自訂應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)
