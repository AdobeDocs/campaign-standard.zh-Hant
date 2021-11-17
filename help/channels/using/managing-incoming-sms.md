---
title: 管理傳入的簡訊
description: 了解如何在Adobe Campaign中管理停止SMS和儲存傳入的SMS。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 2%

---

# 管理傳入的簡訊{#managing-incoming-sms}

## 管理停止SMS {#managing-stop-sms}

當設定檔回覆透過Campaign傳送的SMS訊息時，您可以設定自動傳回給他們的訊息，以及要執行的動作。

此設定定義於 **[!UICONTROL Automatic reply sent to the MO]** 區段 [SMS路由外部帳戶](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO代表「行動產生」，這表示您可以設定對傳送簡訊的行動裝置的自動回覆。

若要這麼做：

1. 從進階功能表，透過Adobe Campaign標誌，選取 **[!UICONTROL Administration > Application settings > External accounts]** 然後 **[!UICONTROL SMS routing via SMPP]** 外部帳戶。
1. 在 **[!UICONTROL Automatic reply sent to the MO]** 類別，按一下 **[!UICONTROL Create element]** 以開始設定自動回覆。

   ![](assets/sms_mo_1.png)

1. 選擇將觸發此自動回覆的關鍵字。 關鍵字不區分大小寫。 例如，在此，如果收件者傳送「STOP」關鍵字，則會收到自動回覆。

   如果您想要傳送相同的回覆（無論關鍵字為何），請將此欄保留空白。

   ![](assets/sms_mo_2.png)

1. 在 **[!UICONTROL Short code]** 欄位中，指定通常用於傳送傳遞的數字，且將作為寄件者名稱。 您也可以決定離開 **[!UICONTROL Short code]** 欄空白，不論短碼為何，都會傳送相同的回覆。

   ![](assets/sms_mo_4.png)

1. 在欄位中輸入要傳送給收件者的答案 **[!UICONTROL Reply]**.

   若要在不傳送回覆的情況下執行動作，請將 **[!UICONTROL Reply]** 欄空白。 例如，這可讓您從隔離區中移除回覆「STOP」以外訊息之使用者的電話號碼。

   ![](assets/sms_mo_3.png)

1. 在 **[!UICONTROL Additional action]** 欄位，將動作連結至自動回覆：

   * 此 **[!UICONTROL Send to quarantine]** 動作會自動隔離設定檔電話號碼。
   * 此 **[!UICONTROL Remove from quarantine]** 操作將從隔離區中刪除配置檔案電話號碼。
   * 此 **[!UICONTROL None]** 動作可讓您只傳送訊息給收件者，而不執行動作。

   例如，在以下設定中，如果收件者傳送「STOP」關鍵字，則會自動收到取消訂閱確認，而他們的電話號碼將會以 **[!UICONTROL On denylist]** 狀態。 此狀態僅指電話號碼，而設定檔是為使用者繼續收到電子郵件訊息。

   ![](assets/sms_mo.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。

1. 從 **[!UICONTROL Advanced parameters]** 簡訊傳送 **[!UICONTROL Properties]**，您可以設定特定 **[!UICONTROL Short code]** 自動排除選擇退出的收件者。 如需詳細資訊，請參閱 [本節](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

您的收件者現在可以自動取消訂閱訊息，並透過此自動回覆傳送至隔離區。 隔離的收件者會列在 **[!UICONTROL Addresses]** 表格 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** 功能表。 如需隔離的詳細資訊，請參閱 [節](../../sending/using/understanding-quarantine-management.md).

如有需要，可儲存這些傳入的SMS。 有關詳細資訊，請參閱 [節](#storing-incoming-sms).

## 儲存傳入的SMS {#storing-incoming-sms}

在 **[!UICONTROL SMS routing via SMPP]** 外部帳戶時，您可以選擇儲存傳入的訊息，例如當訂閱者回覆SMS訊息時，以便從收件者清單中移除。

![](assets/sms_config_mo_1.png)

檢查 **[!UICONTROL Store incoming MO in the database]** 在 **[!UICONTROL SMPP channel settings]** 類別中，所有SMS都會儲存在inSMS表格中，並可透過工作流程中的查詢活動擷取。

若要這麼做：

1. 在 **[!UICONTROL SMPP channel settings]** 欄位，檢查 **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. 在 **[!UICONTROL Marketing activities]** 按一下 **[!UICONTROL Create]** 然後選取 **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. 選取您的工作流程類型。
1. 編輯工作流程的屬性，然後按一下 **[!UICONTROL Create]**. 如需建立工作流程的詳細資訊，請參閱 [節](../../automating/using/building-a-workflow.md).
1. 拖放 **[!UICONTROL Query]** 活動並連按兩下活動。
1. 在 **[!UICONTROL Properties]** 頁簽，選擇 **[!UICONTROL Incoming SMS (inSMS)]** 在 **[!UICONTROL Resource]** 欄位。

   ![](assets/sms_config_mo_4.png)

1. 然後，在 **[!UICONTROL Target]** 標籤，拖放 **[!UICONTROL Incoming SMS attributes]** 規則。

   ![](assets/sms_config_mo_5.png)

1. 在此，我們要定位從前一天開始的所有傳入郵件。 在 **[!UICONTROL Field]** 類別，選擇 **[!UICONTROL Creation date (created)]**.
1. 在 **[!UICONTROL Filter type]**，選取 **[!UICONTROL Relative]** 然後 **[!UICONTROL Level of precision]**，選擇 **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. 然後，您可以選擇從今天、前一天或最近幾天擷取資料。 按一下 **[!UICONTROL Confirm]** 查詢時。

此查詢將根據所選時間範圍檢索收到的每條STOP消息。

例如，活動可讓您建立母體，並更妥善地個人化您的傳送。
