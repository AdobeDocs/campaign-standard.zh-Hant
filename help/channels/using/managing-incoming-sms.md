---
title: 管理傳入的簡訊
description: 瞭解如何在Adobe Campaign中管理停止SMS及儲存傳入的SMS。
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

此設定是在[SMS路由外部帳戶](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)的&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;區段中定義。 MO代表「行動原始」，這表示您可以設定自動回覆給傳送SMS的行動裝置。

若要這麼做：

1. 從進階功能表，透過Adobe Campaign標誌，依序選取&#x200B;**[!UICONTROL Administration > Application settings > External accounts]**&#x200B;及&#x200B;**[!UICONTROL SMS routing via SMPP]**&#x200B;外部帳戶。
1. 在&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;類別下，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;以開始設定自動回覆。

   ![](assets/sms_mo_1.png)

1. 選擇將觸發此自動回覆的關鍵字。 關鍵字不區分大小寫。 例如，在這裡，如果收件者傳送關鍵字「STOP」，他們會收到自動回覆。

   如果您想要傳送相同的回覆，無論關鍵字為何，請將此欄保留空白。

   >[!IMPORTANT]
   >
   >僅授權英數字元。

   ![](assets/sms_mo_2.png)

1. 在&#x200B;**[!UICONTROL Short code]**&#x200B;欄位中，指定通常用於傳送傳遞並將作為寄件者名稱的數字。 您也可以決定將&#x200B;**[!UICONTROL Short code]**&#x200B;欄保留為空白，以傳送相同的回覆，無論簡短的程式碼為何。

   ![](assets/sms_mo_4.png)

1. 在欄位&#x200B;**[!UICONTROL Reply]**&#x200B;中輸入您要傳送給收件者的答案。

   若要在不傳送回覆的情況下執行動作，請將&#x200B;**[!UICONTROL Reply]**&#x200B;欄留空。 例如，這可讓您從隔離區中移除回覆「STOP」以外的訊息之使用者的電話號碼。

   ![](assets/sms_mo_3.png)

1. 在&#x200B;**[!UICONTROL Additional action]**&#x200B;欄位中，將動作連結至您的自動回覆：

   * **[!UICONTROL Send to quarantine]**&#x200B;動作會自動隔離設定檔電話號碼。
   * **[!UICONTROL Remove from quarantine]**&#x200B;動作會從隔離區移除設定檔電話號碼。
   * **[!UICONTROL None]**&#x200B;動作可讓您只傳送郵件給收件者，而不需執行動作。

   例如，在下列設定中，如果收件者傳送關鍵字「STOP」，他們將會自動收到取消訂閱確認，且他們的電話號碼將會傳送到狀態為&#x200B;**[!UICONTROL On denylist]**&#x200B;的隔離區。 此狀態僅適用於電話號碼，其設定檔為使用者可繼續接收電子郵件訊息。

   ![](assets/sms_mo.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。

1. 從簡訊傳遞&#x200B;**[!UICONTROL Properties]**&#x200B;的&#x200B;**[!UICONTROL Advanced parameters]**，您可以設定特定的&#x200B;**[!UICONTROL Short code]**&#x200B;以自動排除選擇退出的收件者。 如需詳細資訊，請參閱[本節](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)。

您的收件者現在可以自動取消訂閱您的訊息，並透過此自動回覆傳送到隔離區。 透過&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**&#x200B;功能表提供的&#x200B;**[!UICONTROL Addresses]**&#x200B;表格中列有隔離的收件者。 如需隔離的詳細資訊，請參閱此[區段](../../sending/using/understanding-quarantine-management.md)。

如有需要，可儲存這些傳入的SMS。 如需詳細資訊，請參閱此[區段](#storing-incoming-sms)。

## 儲存傳入的簡訊 {#storing-incoming-sms}

在&#x200B;**[!UICONTROL SMS routing via SMPP]**&#x200B;外部帳戶中，您可以選擇儲存傳入訊息，例如當訂閱者回覆SMS訊息「停止」以便從您的收件者清單移除時。

![](assets/sms_config_mo_1.png)

若檢查&#x200B;**[!UICONTROL SMPP channel settings]**&#x200B;類別中的&#x200B;**[!UICONTROL Store incoming MO in the database]**，所有簡訊都會儲存在inSMS表格中，並可透過工作流程中的查詢活動擷取。

若要這麼做：

1. 在&#x200B;**[!UICONTROL SMPP channel settings]**&#x200B;欄位中，核取&#x200B;**[!UICONTROL Store incoming MO in the database]**。

   ![](assets/sms_config_mo_2.png)

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;索引標籤中，按一下&#x200B;**[!UICONTROL Create]**，然後選取&#x200B;**[!UICONTROL Workflow]**。

   ![](assets/sms_config_mo_3.png)

1. 選取您的工作流程型別。
1. 編輯工作流程的內容，然後按一下&#x200B;**[!UICONTROL Create]**。 如需工作流程建立的詳細資訊，請參閱此[區段](../../automating/using/building-a-workflow.md)。
1. 拖放&#x200B;**[!UICONTROL Query]**&#x200B;活動並連按兩下該活動。
1. 在查詢的&#x200B;**[!UICONTROL Properties]**&#x200B;索引標籤中，選擇&#x200B;**[!UICONTROL Resource]**&#x200B;欄位中的&#x200B;**[!UICONTROL Incoming SMS (inSMS)]**。

   ![](assets/sms_config_mo_4.png)

1. 然後，在&#x200B;**[!UICONTROL Target]**&#x200B;索引標籤中，拖放&#x200B;**[!UICONTROL Incoming SMS attributes]**&#x200B;規則。

   ![](assets/sms_config_mo_5.png)

1. 在此，我們想要將目標鎖定在前一天的每個傳入訊息。 在&#x200B;**[!UICONTROL Field]**&#x200B;類別中，選取&#x200B;**[!UICONTROL Creation date (created)]**。
1. 在&#x200B;**[!UICONTROL Filter type]**&#x200B;中選取&#x200B;**[!UICONTROL Relative]**，然後在&#x200B;**[!UICONTROL Level of precision]**&#x200B;中選擇&#x200B;**[!UICONTROL Day]**。

   ![](assets/sms_config_mo_6.png)

1. 接著，您可以選擇從今天、前一天或最後幾天擷取資料。 設定查詢時，按一下&#x200B;**[!UICONTROL Confirm]**。

此查詢將根據所選的時間範圍擷取收到的每條STOP訊息。

例如，活動可讓您建立人口族群，並更妥善地個人化您的傳送。
