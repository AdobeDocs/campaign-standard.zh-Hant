---
solution: Campaign Standard
product: campaign
title: 預覽訊息
description: 瞭解如何在內容編輯器或電子郵件設計工具中預覽訊息。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 15%

---


# 預覽傳送 {#previewing-messages}

## 預覽電子郵件{#previewing-emails}

Campaign Standard可讓您在傳送訊息之前先預覽訊息，以檢查其個人化及收件者將如何看到訊息。

消息預覽是使用您添加到消息目標的&#x200B;**測試配置檔案**&#x200B;執行的。

對於&#x200B;**email**&#x200B;訊息，Campaign Standard可讓您使用目標描述檔來預覽訊息，而非測試描述檔。 這可讓您獲得特定描述檔將會收到之訊息的精確表示。 如需詳細資訊，請參閱[使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)。

若要使用測試設定檔預覽訊息，請依照下列步驟進行：

1. 在[電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)中，按一下&#x200B;**[!UICONTROL Preview]**&#x200B;按鈕。

   ![](assets/sending_preview.png)

   案頭檢視和回應式行動裝置檢視會並排顯示您的電子郵件。

1. 每次預覽期間會執行自動反垃圾郵件檢查。 按一下&#x200B;**[!UICONTROL Anti-spam analysis]**&#x200B;按鈕以進一步瞭解警告。

   ![](assets/sending_anti-spam_analysis.png)

1. 選擇&#x200B;**[!UICONTROL Change profile]**&#x200B;按鈕，以選擇要測試個人化元素的測試描述檔。

   ![](assets/sending_test-profile.png)

1. 要退出&#x200B;**[!UICONTROL Preview]**&#x200B;模式，請按一下螢幕左上角的&#x200B;**[!UICONTROL Edit]**&#x200B;按鈕。

   ![](assets/sending_preview_edit.png)

**相關主題**

* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)
* [傳送校樣](../../sending/using/sending-proofs.md)

## 預覽SMS訊息{#previewing-sms}

對於&#x200B;**SMS**&#x200B;訊息，Campaign Standard可讓您使用測試設定檔預覽訊息。 這可讓您獲得特定描述檔將會收到之訊息的精確表示。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

若要使用測試設定檔預覽SMS訊息，請依照下列步驟進行：

1. 在您填入SMS訊息的&#x200B;**[!UICONTROL Properties]**&#x200B;並選取受眾後，您就可以個人化您的傳送。 有關詳細資訊，請參閱[部分](../../channels/using/personalizing-sms-messages.md)。

   ![](assets/sms_preview.png)

1. 個人化您的內容後，按一下&#x200B;**[!UICONTROL Create]**&#x200B;以存取&#x200B;**[!UICONTROL Summary]**&#x200B;視窗。

1. 在&#x200B;**[!UICONTROL Summary]**&#x200B;視窗中，按一下&#x200B;**[!UICONTROL Content]**&#x200B;開始預覽傳送。

   ![](assets/sms_preview_2.png)

1. 按一下工具欄中的&#x200B;**[!UICONTROL Preview]**。

   ![](assets/sms_preview_3.png)

1. 按一下&#x200B;**[!UICONTROL Change profile]**&#x200B;以選擇您的測試設定檔，然後按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/sms_preview_4.png)

您現在可以根據選取的測試設定檔，看到訊息的精確表示。

**相關主題**

* [關於 SMS 訊息](../../channels/using/about-sms-messages.md)
* [建立 SMS 訊息](../../channels/using/creating-an-sms-message.md)
* [個人化 SMS 訊息](../../channels/using/personalizing-sms-messages.md)

## 預覽推播通知{#previewing-push}

對於&#x200B;**推播通知**,Campaign Standard可讓您使用測試設定檔預覽訊息。 這可讓您獲得特定描述檔將會收到之訊息的精確表示。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

若要使用測試設定檔預覽推播通知，請遵循下列步驟：

1. 在您填入推播通知的&#x200B;**[!UICONTROL Properties]**&#x200B;並選取受眾後，您就可以個人化您的傳送。 如需詳細資訊，請參閱[自訂推播通知](../../channels/using/customizing-a-push-notification.md)。

1. 在個人化您的內容後，您可以在預覽視窗中，根據裝置和作業系統，直接檢查推播通知的轉譯。

   ![](assets/push_preview.png)

1. 若要使用測試設定檔預覽推播通知，請按一下&#x200B;**[!UICONTROL Preview with test profile]**。

   ![](assets/push_preview_2.png)

1. 選擇測試配置檔案，然後選擇&#x200B;**[!UICONTROL Confirm]**。

您現在可以根據選取的測試設定檔，看到訊息的精確表示。

![](assets/push_preview_3.png)

**相關主題**

* [關於推播通知](../../channels/using/about-push-notifications.md)
* [準備和傳送推播通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [自訂推播通知](../../channels/using/customizing-a-push-notification.md)

## 預覽應用程式內訊息{#previewing-in-app}

對於&#x200B;**In-App**,Campaign Standard可讓您使用測試設定檔預覽訊息。 這可讓您獲得特定描述檔將會收到之訊息的精確表示。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

若要使用測試設定檔預覽應用程式內訊息，請依照下列步驟進行：

1. 在您填入應用程式內訊息的&#x200B;**[!UICONTROL Properties]**&#x200B;後，選取您的觀眾並設定&#x200B;**[!UICONTROL Triggers]**，您就可以個人化傳送內容。 如需詳細資訊，請參閱[自訂應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)。

1. 在個人化您的內容後，您可以在預覽視窗中，根據裝置和作業系統，直接檢查應用程式內訊息的轉譯。

   ![](assets/in_app_preview.png)

1. 若要使用測試設定檔預覽應用程式內訊息，請按一下&#x200B;**[!UICONTROL Preview]**。

   ![](assets/in_app_preview_2.png)

1. 選擇測試配置檔案，然後選擇&#x200B;**[!UICONTROL Confirm]**。

您現在可以根據選取的測試設定檔，看到訊息的精確表示。

![](assets/in_app_preview_3.png)

**相關主題**

* [關於應用程式內訊息傳送](../../channels/using/about-in-app-messaging.md)
* [準備和傳送應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [自訂應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)