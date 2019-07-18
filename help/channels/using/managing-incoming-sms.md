---
title: 管理傳入的SMS
seo-title: 管理傳入的SMS
description: 管理傳入的SMS
seo-description: 瞭解如何在Adobe Campaign中管理停止SMS並儲存傳入的SMS。
page-status-flag: 從未啓動
uuid: f063052b-96ef-41b6-bf1 b-4006de73 f0 b9
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: sms-messages
discoiquuid: ee1970e6-1ced-46e0-94e6-8337768300ee
delivercontext-tags: 傳送，SMSContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Managing incoming SMS{#managing-incoming-sms}

## Managing STOP SMS {#managing-stop-sms}

當描述檔回覆是透過促銷活動傳送的SMS訊息時，您可以設定自動傳回給他的訊息，以及執行的動作。

This configuration is defined in the **[!UICONTROL Automatic reply sent to the MO]** section of the [SMS Routing external account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO代表「Mobile Origination」，這表示您可以對傳送SMS的行動裝置設定自動回覆。

若要這麼做：

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]** then the **[!UICONTROL SMS routing via SMPP]** external account.
1. **[!UICONTROL Automatic reply sent to the MO]** 在類別下方，按一下 **[!UICONTROL Create element]** 以開始設定自動回覆。

   ![](assets/sms_mo_1.png)

1. 選擇要觸發此自動回覆的關鍵字。關鍵字不區分大小寫。例如，如果收件者傳送關鍵字「停止」，則會收到自動回覆。

   無論關鍵字是甚麼，如果您要傳送相同的回覆，請將此欄保持空白。

   ![](assets/sms_mo_2.png)

1. In the **[!UICONTROL Short code]** field, specify a number that is usually used to send deliveries and will serve as a sender name. You can also decide to leave the **[!UICONTROL Short code]** column empty, to send the same reply no matter what the short code.

   ![](assets/sms_mo_4.png)

1. Type in the answer you want to send to your recipients in the field **[!UICONTROL Reply]**.

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. 例如，這可讓您從以非「停止」訊息的使用者的手機號碼中移除回覆。

   ![](assets/sms_mo_3.png)

1. **[!UICONTROL Additional action]** 在欄位中，將動作連結至自動回覆：

   * **[!UICONTROL Send to quarantine]** 動作會自動四分裂描述檔電話號碼。
   * **[!UICONTROL Remove from quarantine]** 此動作會移除隔離的設定檔電話號碼。
   * **[!UICONTROL None]** 此動作可讓您只傳送訊息給收件者，而不需執行動作。
   For example, in the configuration below, if recipients send the keyword "STOP", they will automatically receive an unsubscription confirmation and their phone number will be sent to quarantine with the **[!UICONTROL Blacklisted]** status. 此狀態僅指電話號碼，描述檔並未列入黑名單，因此使用者仍可繼續接收電子郵件訊息。

   ![](assets/sms_mo.png)

您的收件者現在可以自動取消訂閱您的訊息，並使用此自動回覆進行隔離。The quarantined recipients are listed in the **[!UICONTROL Addresses]** table available through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** menu. For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

如有需要，可儲存這些傳入的SMS。For more information on this, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

## Storing incoming SMS {#storing-incoming-sms}

**[!UICONTROL SMS routing via SMPP]** 在外部帳戶中，您可以選擇儲存傳入訊息，例如當訂閱者回覆SMS訊息時，將其從收件者清單中移除。

![](assets/sms_config_mo_1.png)

By checking **[!UICONTROL Store incoming MO in the database]** in the **[!UICONTROL SMPP channel settings]** category, all SMS will be stored in the inSMS table and can be retrieved via a query activity in a workflow.

若要這麼做：

1. In the **[!UICONTROL SMPP channel settings]** field, check **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. **[!UICONTROL Marketing activities]** 在標籤中，按一下 **[!UICONTROL Create]** 然後選取 **[!UICONTROL Workflow]**。

   ![](assets/sms_config_mo_3.png)

1. 選取您的工作流程類型。
1. Edit the properties of your workflow, then click **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Drag and drop a **[!UICONTROL Query]** activity and double-click the activity.
1. In the **[!UICONTROL Properties]** tab of the query, choose **[!UICONTROL Incoming SMS (inSMS)]** in the **[!UICONTROL Resource]** field.

   ![](assets/sms_config_mo_4.png)

1. Then, in the **[!UICONTROL Target]** tab, drag and drop the **[!UICONTROL Incoming SMS attributes]** rule.

   ![](assets/sms_config_mo_5.png)

1. 在這裡，我們想要定位前一天的每個傳入訊息。In the **[!UICONTROL Field]** category, select **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**, select **[!UICONTROL Relative]** then in **[!UICONTROL Level of precision]**, choose **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. 然後您可以選擇擷取今天或過去幾天的資料。Click **[!UICONTROL Confirm]** when your query is configured.

此查詢會擷取根據所選時間範圍所接收的每個停止訊息。

此活動可讓您建立人口族群，並更好地個人化您的傳遞。
