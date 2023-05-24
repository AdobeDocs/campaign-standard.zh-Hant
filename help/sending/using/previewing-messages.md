---
title: 預覽訊息
description: 瞭解如何在內容編輯器或電子郵件設計器中預覽郵件。
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

Campaign Standard允許您在發送郵件之前預覽郵件，以便檢查郵件的個性化以及收件人將如何查看郵件。

使用 **Test配置檔案** 添加到郵件目標。

對於 **電子郵件** 消息，Campaign Standard允許您使用目標配置檔案預覽消息，而不是test配置檔案。 這允許您獲得特定配置檔案將接收的消息的準確表示形式。 如需詳細資訊，請參閱[使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)。

要使用test配置檔案預覽消息，請執行以下步驟：

1. 在 [電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)，按一下 **[!UICONTROL Preview]** 按鈕

   ![](assets/sending_preview.png)

   案頭視圖和電子郵件的響應移動視圖並排顯示。

1. 在每次預覽期間執行自動反垃圾郵件檢查。 按一下 **[!UICONTROL Anti-spam analysis]** 的子菜單。

   ![](assets/sending_anti-spam_analysis.png)

1. 選擇 **[!UICONTROL Change profile]** 按鈕，選擇要test個性化元素的test配置檔案。

   ![](assets/sending_test-profile.png)

1. 退出 **[!UICONTROL Preview]** 模式，按一下 **[!UICONTROL Edit]** 按鈕。

   ![](assets/sending_preview_edit.png)

**相關主題**

* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)
* [傳送校樣](../../sending/using/sending-proofs.md)

## 預覽SMS消息 {#previewing-sms}

對於 **簡訊** 消息，Campaign Standard允許您使用test配置檔案預覽消息。 這允許您獲得特定配置檔案將接收的消息的準確表示形式。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

要使用test配置檔案預覽SMS消息，請執行以下步驟：

1. 一旦你填了 **[!UICONTROL Properties]** 您的SMS消息和選擇的受眾，您可以個性化您的傳遞。 有關詳細資訊，請參閱 [節](../../channels/using/personalizing-sms-messages.md)。

   ![](assets/sms_preview.png)

1. 個性化內容後，按一下 **[!UICONTROL Create]** 訪問 **[!UICONTROL Summary]** 的子菜單。

1. 從 **[!UICONTROL Summary]** 窗口，按一下 **[!UICONTROL Content]** 開始預覽交貨。

   ![](assets/sms_preview_2.png)

1. 按一下 **[!UICONTROL Preview]** 的子菜單。

   ![](assets/sms_preview_3.png)

1. 按一下 **[!UICONTROL Change profile]** 選擇test配置檔案 **[!UICONTROL Confirm]**。

   ![](assets/sms_preview_4.png)

現在，您可以根據所選的test配置檔案查看消息的準確表示形式。

**相關主題**

* [關於簡訊訊息](../../channels/using/about-sms-messages.md)
* [建立簡訊訊息](../../channels/using/creating-an-sms-message.md)
* [個人化簡訊訊息](../../channels/using/personalizing-sms-messages.md)

## 預覽推送通知 {#previewing-push}

對於 **推送通知**,Campaign Standard允許您使用test配置檔案預覽消息。 這允許您獲得特定配置檔案將接收的消息的準確表示形式。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

要使用test配置檔案預覽推送通知，請執行以下步驟：

1. 一旦你填了 **[!UICONTROL Properties]** 您的推送通知和選擇您的受眾，您可以個性化您的交付。 有關詳細資訊，請參閱 [自定義推送通知](../../channels/using/customizing-a-push-notification.md)。

1. 個性化內容後，您可以直接在預覽窗口中根據設備和作業系統檢查推送通知的呈現。

   ![](assets/push_preview.png)

1. 要使用test配置式預覽推送通知，請按一下 **[!UICONTROL Preview with test profile]**。

   ![](assets/push_preview_2.png)

1. 選擇test配置檔案 **[!UICONTROL Confirm]**。

現在，您可以根據所選的test配置檔案查看消息的準確表示形式。

![](assets/push_preview_3.png)

**相關主題**

* [關於推送通知](../../channels/using/about-push-notifications.md)
* [準備和傳送推送通知](../../channels/using/preparing-and-sending-a-push-notification.md)
* [自訂推送通知](../../channels/using/customizing-a-push-notification.md)

## 預覽應用內消息 {#previewing-in-app}

對於 **應用程式內**,Campaign Standard允許您使用test配置檔案預覽消息。 這允許您獲得特定配置檔案將接收的消息的準確表示形式。 如需詳細資訊，請參閱[管理測試設定檔](../../audiences/using/managing-test-profiles.md)。

要使用test配置檔案預覽In-App消息，請執行以下步驟：

1. 一旦你填了 **[!UICONTROL Properties]** In-App消息，選擇您的受眾並設定 **[!UICONTROL Triggers]**，您可以個性化您的交貨。 有關詳細資訊，請參閱 [自定義In-App消息](../../channels/using/customizing-an-in-app-message.md)。

1. 個性化內容後，您可以直接在預覽窗口中根據設備和作業系統檢查In-App消息的呈現。

   ![](assets/in_app_preview.png)

1. 要使用test配置式預覽In-App消息，請按一下 **[!UICONTROL Preview]**。

   ![](assets/in_app_preview_2.png)

1. 選擇test配置檔案 **[!UICONTROL Confirm]**。

現在，您可以根據所選的test配置檔案查看消息的準確表示形式。

![](assets/in_app_preview_3.png)

**相關主題**

* [關於應用程式內訊息傳送](../../channels/using/about-in-app-messaging.md)
* [準備和傳送應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [自訂應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)
