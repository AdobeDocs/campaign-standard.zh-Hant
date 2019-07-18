---
title: 傳送內部通知
seo-title: 傳送內部通知
description: 傳送內部通知
seo-description: 瞭解如何傳送即時系統通知給您的Adobe Campaign使用者。
page-status-flag: 從未啓動
uuid: f196f025-dbb9-4268-9d7 d-ff626994 b447
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 應用程式設定
discoiquuid: 4d51229a-745a-4f24-b1 c2-22fa203 b499 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Sending internal notifications{#sending-internal-notifications}

Adobe Campaign可讓您直接在應用程式中接收有關重要系統活動的通知。即時通知可讓相關利益相關者得知資訊，並讓使用者能夠立即直接對應用程式中的活動通知採取行動。為團隊帶來更高的敏捷性、效率和更順暢的促銷活動執行。

![](assets/pulse_3.png)

您可以設定下列物件的通知：

* **[!UICONTROL A/B Test emails]**：電子郵件製作程式和修飾詞會收到通知，指出已選取變體(自動模式)或需要選擇變體(手動模式)。按一下通知會顯示對應的電子郵件。預設會在立即可用的A/B測試範本中啓動通知。If you want to deactivate them, edit the properties of the email or the email template and uncheck the box located under **General &gt; Notifications**. For more information on A/B Test emails, refer to [Creating an AB Test](../../channels/using/designing-an-a-b-test-email.md). For more on email properties, refer to [List of email properties](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**：當工作流程發生錯誤時，會通知所選保全群組的每位成員(電子郵件和應用程式內通知)。按一下通知或電子郵件連結會顯示對應的工作流程。預設會停用預設工作流程範本中的通知。If you want to activate them, edit the properties of the workflow or workflow template and add a security group under **General &gt; Execution &gt; Error management &gt; Supervisors**. For more information on security groups, refer to [Managing groups and users](../../administration/using/managing-groups-and-users.md). For more on workflow properties, refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties).

   ![](assets/pulse_1.png)

