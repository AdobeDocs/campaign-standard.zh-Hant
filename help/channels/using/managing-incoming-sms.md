---
title: 管理傳入的簡訊
description: 瞭解如何在Adobe Campaign中管理STOP SMS及儲存傳入的SMS。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: 30d0c2552bea3a7cbd8500be4e8c0c74e5a40a99
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# 管理傳入的簡訊{#managing-incoming-sms}

## 管理停止簡訊 {#managing-stop-sms}

當設定檔回覆透過Campaign傳送的SMS訊息時，您可以設定自動傳回給他們的訊息，以及要執行的動作。

此設定在 **[!UICONTROL Automatic reply sent to the MO]** 部分 [SMS路由外部帳戶](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO代表「行動原始」，這表示您可以設定自動回覆給傳送SMS的行動裝置。

若要這麼做：

1. 從進階功能表中，透過Adobe Campaign標誌選取 **[!UICONTROL Administration > Application settings > External accounts]** 然後 **[!UICONTROL SMS routing via SMPP]** 外部帳戶。
1. 在 **[!UICONTROL Automatic reply sent to the MO]** 類別，按一下 **[!UICONTROL Create element]** 以開始設定您的自動回覆。

   ![](assets/sms_mo_1.png)

1. 選擇將觸發此自動回覆的關鍵字。 關鍵字不區分大小寫。 例如，在這裡，如果收件者傳送關鍵字「STOP」，他們將收到自動回覆。

   如果您想要傳送相同的回覆，無論關鍵字為何，請將此欄留空。

   >[!IMPORTANT]
   >
   >僅授權英數字元。

   ![](assets/sms_mo_2.png)

1. 在 **[!UICONTROL Short code]** 欄位中，指定用來傳送傳遞及當作寄件者名稱的數字。 您也可以決定離開 **[!UICONTROL Short code]** 欄空白，無論簡短的程式碼為何，都可傳送相同的回覆。

   ![](assets/sms_mo_4.png)

1. 在欄位中輸入您要傳送給收件者的答案 **[!UICONTROL Reply]**.

   若要在不傳送回覆的情況下執行動作，請將 **[!UICONTROL Reply]** 欄空白。 例如，這可讓您從隔離區中移除回覆「STOP」以外的訊息之使用者的電話號碼。

   ![](assets/sms_mo_3.png)

1. 在 **[!UICONTROL Additional action]** 欄位，將動作連結至您的自動回覆：

   * 此 **[!UICONTROL Send to quarantine]** 動作會自動隔離設定檔電話號碼。
   * 此 **[!UICONTROL Remove from quarantine]** 動作會將設定檔電話號碼從隔離區中移除。
   * 此 **[!UICONTROL None]** 動作可讓您只傳送訊息給收件者，而不需執行動作。

   例如，在下列設定中，如果收件者傳送關鍵字「STOP」，他們會自動收到取消訂閱確認，而他們的電話號碼會傳送到隔離區，並附上 **[!UICONTROL On denylist]** 狀態。 此狀態僅適用於電話號碼，而設定檔則可讓使用者繼續接收電子郵件訊息。

   ![](assets/sms_mo.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。

1. 從 **[!UICONTROL Advanced parameters]** 您的SMS傳送 **[!UICONTROL Properties]**，您可以設定 **[!UICONTROL Short code]** 以自動排除選擇退出的收件者。 如需詳細資訊，請參閱 [本節](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

收件者現在可以自動取消訂閱您的訊息，並透過此自動回覆傳送到隔離區。 隔離的收件者會列於 **[!UICONTROL Addresses]** 表格可透過 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** 功能表。 如需隔離的詳細資訊，請參閱此 [區段](../../sending/using/understanding-quarantine-management.md).

如有需要，可儲存這些傳入的SMS。 如需詳細資訊，請參閱此 [區段](#storing-incoming-sms).

## 儲存傳入的簡訊 {#storing-incoming-sms}

在 **[!UICONTROL SMS routing via SMPP]** 外部帳戶，您可以選擇儲存傳入訊息，例如，當訂閱者回覆「STOP」簡訊以便從您的收件者清單中移除時。

![](assets/sms_config_mo_1.png)

透過檢查 **[!UICONTROL Store incoming MO in the database]** 在 **[!UICONTROL SMPP channel settings]** 類別中，所有簡訊都會儲存在inSMS表格中，並可透過工作流程中的查詢活動加以擷取。

若要這麼做：

1. 在 **[!UICONTROL SMPP channel settings]** 欄位，檢查 **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. 在 **[!UICONTROL Marketing activities]** 標籤，按一下 **[!UICONTROL Create]** 然後選取 **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. 選取您的工作流程型別。
1. 編輯工作流程的屬性，然後按一下 **[!UICONTROL Create]**. 如需工作流程建立的詳細資訊，請參閱此 [區段](../../automating/using/building-a-workflow.md).
1. 拖放 **[!UICONTROL Query]** 活動並連按兩下該活動。
1. 在 **[!UICONTROL Properties]** 索引標籤中，選擇 **[!UICONTROL Incoming SMS (inSMS)]** 在 **[!UICONTROL Resource]** 欄位。

   ![](assets/sms_config_mo_4.png)

1. 然後，在 **[!UICONTROL Target]** 標籤，拖放 **[!UICONTROL Incoming SMS attributes]** 規則。

   ![](assets/sms_config_mo_5.png)

1. 在此，我們想要鎖定前一天傳入的每封郵件。 在 **[!UICONTROL Field]** 類別，選取 **[!UICONTROL Creation date (created)]**.
1. 在 **[!UICONTROL Filter type]**，選取 **[!UICONTROL Relative]** 然後進入 **[!UICONTROL Level of precision]**，選擇 **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. 然後，您可以選擇從今天、前一天或最後幾天擷取資料。 按一下 **[!UICONTROL Confirm]** 設定查詢時。

此查詢將根據所選的時間範圍擷取收到的每個STOP訊息。

例如，活動可讓您建立人口族群，並更好地個人化您的傳送。
