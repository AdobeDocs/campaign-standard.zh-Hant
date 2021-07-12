---
solution: Campaign Standard
product: campaign
title: 傳送內部通知
description: 了解如何傳送即時系統通知給您的Adobe Campaign使用者。
audience: administration
content-type: reference
topic-tags: application-settings
feature: 執行個體設定
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 2%

---

# 傳送內部通知{#sending-internal-notifications}

Adobe Campaign可讓您直接在應用程式中接收有關重要系統活動的通知。 即時通知可隨時向相關利害關係人提供相關資訊，讓使用者能夠立即直接從應用程式內對活動通知採取行動。 團隊的結果是進階的靈活性、效率，以及更順暢的行銷活動執行。

![](assets/pulse_3.png)

您可以為下列物件設定通知：

* **[!UICONTROL A/B Test emails]**:電子郵件建立者和修改者會收到選擇變體（自動模式）或需要選擇變體（手動模式）的通知。按一下通知會顯示對應的電子郵件。 預設會在現成可用的A/B測試範本中啟動通知。 如果要停用它們，請編輯電子郵件或電子郵件範本的屬性，並取消勾選&#x200B;**一般>通知**&#x200B;下方的方塊。 如需A/B測試電子郵件的詳細資訊，請參閱[建立AB測試](../../channels/using/designing-an-a-b-test-email.md)。 有關電子郵件屬性的詳細資訊，請參閱[電子郵件屬性清單](../../administration/using/configuring-email-channel.md#list-of-email-properties)。

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:當工作流程發生錯誤時，所選安全性群組的每個成員都會收到通知（電子郵件和應用程式內通知）。按一下通知或電子郵件連結，會顯示對應的工作流程。 預設會在現成可用的工作流程範本中停用通知。 如果要激活它們，請編輯工作流或工作流模板的屬性，並在&#x200B;**「常規」>「執行」>「錯誤管理」>「監管者」**&#x200B;下添加安全組。 有關安全組的詳細資訊，請參閱[管理組和用戶](../../administration/using/managing-groups-and-users.md)。 有關工作流屬性的詳細資訊，請參閱[工作流屬性](../../automating/using/managing-execution-options.md)。

   ![](assets/pulse_1.png)
