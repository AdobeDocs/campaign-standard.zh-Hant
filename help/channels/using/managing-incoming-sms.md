---
title: 管理傳入的簡訊
description: 瞭解如何在Adobe Campaign管理停止簡訊和儲存傳入簡訊。
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

## 管理停止SMS {#managing-stop-sms}

當配置檔案答復通過市場活動發送的SMS消息時，您可以配置自動發回給它們的消息以及要執行的操作。

此配置在 **[!UICONTROL Automatic reply sent to the MO]** 的下界 [SMS路由外部帳戶](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)。 MO代表「Mobile Suriced」，這意味著您可以配置對發送SMS的移動設備的自動回復。

若要這麼做：

1. 從高級菜單中，通過Adobe Campaign徽標選擇 **[!UICONTROL Administration > Application settings > External accounts]** 然後 **[!UICONTROL SMS routing via SMPP]** 外部帳戶。
1. 在 **[!UICONTROL Automatic reply sent to the MO]** 類別，按一下 **[!UICONTROL Create element]** 開始配置自動回復。

   ![](assets/sms_mo_1.png)

1. 選擇將觸發此自動答復的關鍵字。 關鍵字不區分大小寫。 例如，在此處，如果收件人發送關鍵字「STOP」，則他們將收到自動答復。

   如果無論關鍵字是什麼，都要發送相同的答復，請將此列留空。

   >[!IMPORTANT]
   >
   >僅授權字母數字字元。

   ![](assets/sms_mo_2.png)

1. 在 **[!UICONTROL Short code]** 欄位中，指定通常用於發送遞送且將用作發件人名稱的數字。 您也可以決定 **[!UICONTROL Short code]** 列為空，以發送相同的答復，無論短代碼是什麼。

   ![](assets/sms_mo_4.png)

1. 在欄位中鍵入要發送給收件人的答案 **[!UICONTROL Reply]**。

   要執行操作而不發送回復，請 **[!UICONTROL Reply]** 列為空。 例如，這允許您從隔離區中刪除用「STOP」以外的消息回復的用戶的電話號碼。

   ![](assets/sms_mo_3.png)

1. 在 **[!UICONTROL Additional action]** 欄位，將操作連結到自動答復：

   * 的 **[!UICONTROL Send to quarantine]** 操作會自動隔離配置檔案電話號碼。
   * 的 **[!UICONTROL Remove from quarantine]** 操作將從隔離中刪除配置檔案電話號碼。
   * 的 **[!UICONTROL None]** 操作允許您只將消息發送到您的收件人，而不執行操作。

   例如，在下面的配置中，如果收件人發送關鍵字「STOP」，則他們將自動收到取消訂閱確認，並且其電話號碼將與 **[!UICONTROL On denylist]** 狀態。 此狀態僅指電話號碼，配置檔案是為了用戶繼續接收電子郵件。

   ![](assets/sms_mo.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。

1. 從 **[!UICONTROL Advanced parameters]** 發送的簡訊 **[!UICONTROL Properties]**，可以設定 **[!UICONTROL Short code]** 自動排除已選擇退出的收件人。 有關此項的詳細資訊，請參閱 [此部分](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)。

您的收件人現在可以自動取消訂閱您的郵件，並通過此自動答復發送到隔離區。 隔離的收件人列在 **[!UICONTROL Addresses]** 表 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** 的子菜單。 有關隔離的詳細資訊，請參閱此 [節](../../sending/using/understanding-quarantine-management.md)。

如果需要，可以儲存這些傳入的SMS。 有關此的詳細資訊，請參閱此 [節](#storing-incoming-sms)。

## 儲存傳入的SMS {#storing-incoming-sms}

在 **[!UICONTROL SMS routing via SMPP]** 外部帳戶，您可以選擇儲存傳入消息，例如，當訂閱者回復「STOP」到SMS消息時，以便從您的收件人清單中刪除。

![](assets/sms_config_mo_1.png)

通過檢查 **[!UICONTROL Store incoming MO in the database]** 的 **[!UICONTROL SMPP channel settings]** 類別中，所有SMS都將儲存在inSMS表中，並且可以通過工作流中的查詢活動來檢索。

若要這麼做：

1. 在 **[!UICONTROL SMPP channel settings]** 欄位，檢查 **[!UICONTROL Store incoming MO in the database]**。

   ![](assets/sms_config_mo_2.png)

1. 在 **[!UICONTROL Marketing activities]** 按鈕 **[!UICONTROL Create]** 選擇 **[!UICONTROL Workflow]**。

   ![](assets/sms_config_mo_3.png)

1. 選擇您的工作流類型。
1. 編輯工作流的屬性，然後按一下 **[!UICONTROL Create]**。 有關建立工作流的詳細資訊，請參閱 [節](../../automating/using/building-a-workflow.md)。
1. 拖放 **[!UICONTROL Query]** 並按兩下該活動。
1. 在 **[!UICONTROL Properties]** 的子菜單。 **[!UICONTROL Incoming SMS (inSMS)]** 的 **[!UICONTROL Resource]** 的子菜單。

   ![](assets/sms_config_mo_4.png)

1. 然後，在 **[!UICONTROL Target]** 頁籤，拖放 **[!UICONTROL Incoming SMS attributes]** 規則。

   ![](assets/sms_config_mo_5.png)

1. 在此，我們要針對從前一天開始的所有傳入消息。 在 **[!UICONTROL Field]** 類別，選擇 **[!UICONTROL Creation date (created)]**。
1. 在 **[!UICONTROL Filter type]**&#x200B;選中 **[!UICONTROL Relative]** 然後 **[!UICONTROL Level of precision]**&#x200B;選項 **[!UICONTROL Day]**。

   ![](assets/sms_config_mo_6.png)

1. 然後，您可以選擇從今天、前一天或過去幾天檢索資料。 按一下 **[!UICONTROL Confirm]** 的子菜單。

此查詢將根據所選時間範圍檢索收到的每條STOP消息。

例如，此活動允許您構建人口並更好地個性化交付。
