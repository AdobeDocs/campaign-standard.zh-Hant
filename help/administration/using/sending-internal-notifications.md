---
title: 傳送內部通知
description: 瞭解如何傳送即時系統通知給您的Adobe Campaign使用者
audience: administration
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# 傳送內部通知{#sending-internal-notifications}

Adobe Campaign可讓您直接在應用程式中接收有關重要系統活動的通知。 即時通知可隨時通知相關利害關係人，並讓使用者能夠立即直接從應用程式內對活動通知採取行動。 對團隊來說，結果就是進階的靈活性、效率以及行銷活動的更順暢執行。

![](assets/pulse_3.png)

您可以為下列物件設定通知：

* **[!UICONTROL A/B Test emails]**：電子郵件建立者和修改者會收到通知，告知已選擇變體（自動模式）或需要選擇變體（手動模式）。 按一下通知會顯示對應的電子郵件。 在現成可用的A/B測試範本中，預設會啟用通知。 如果您要停用它們，請編輯電子郵件或電子郵件範本的屬性，並取消勾選下的方塊 **一般>通知**. 如需A/B測試電子郵件的詳細資訊，請參閱 [建立AB測試](../../channels/using/designing-an-a-b-test-email.md). 有關電子郵件屬性的詳細資訊，請參閱 [電子郵件屬性清單](../../administration/using/configuring-email-channel.md#list-of-email-properties).

  ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**：工作流程發生錯誤時，所選安全性群組的每位成員都會收到通知（電子郵件和應用程式內通知）。 按一下通知或電子郵件連結會顯示對應的工作流程。 現成可用的工作流程範本中，預設會停用通知。 如果您要啟動它們，請編輯工作流程或工作流程範本的屬性，並在下新增安全性群組 **一般>執行>錯誤管理>主管**. 如需安全性群組的詳細資訊，請參閱 [管理群組和使用者](../../administration/using/managing-groups-and-users.md). 有關工作流程屬性的詳細資訊，請參閱 [工作流程屬性](../../automating/using/managing-execution-options.md).

  ![](assets/pulse_1.png)
