---
solution: Campaign Standard
product: campaign
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
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 7%

---

# 管理傳入的簡訊{#managing-incoming-sms}

## 管理停止SMS {#managing-stop-sms}

當描述檔回覆透過 Campaign 傳送的 SMS 訊息時，您可以設定自動傳回給他的訊息，以及要執行的動作。

此配置在[SMS路由外部帳戶](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)的&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;部分中定義。 MO代表「行動產生」，這表示您可以設定對傳送簡訊的行動裝置的自動回覆。

若要這麼做：

1. 從進階功能表，透過Adobe Campaign標誌，依序選取&#x200B;**[!UICONTROL Administration > Application settings > External accounts]**&#x200B;和&#x200B;**[!UICONTROL SMS routing via SMPP]**&#x200B;外部帳戶。
1. 在&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;類別下，按一下&#x200B;**[!UICONTROL Create element]**&#x200B;以開始設定自動回覆。

   ![](assets/sms_mo_1.png)

1. 選擇將觸發此自動回覆的關鍵字。 關鍵字不區分大小寫。 例如，在此，如果收件者傳送「STOP」關鍵字，則會收到自動回覆。

   如果您想要傳送相同的回覆（無論關鍵字為何），請將此欄保留空白。

   ![](assets/sms_mo_2.png)

1. 在&#x200B;**[!UICONTROL Short code]**&#x200B;欄位中，指定通常用於傳送傳遞的數字，並將作為寄件者名稱。 您也可以決定將&#x200B;**[!UICONTROL Short code]**&#x200B;欄保留為空白，以傳送相同的回覆，無論使用什麼簡短代碼。

   ![](assets/sms_mo_4.png)

1. 在欄位&#x200B;**[!UICONTROL Reply]**&#x200B;中輸入要傳送給收件者的答案。

   若要在不傳送回覆的情況下執行動作，請將&#x200B;**[!UICONTROL Reply]**&#x200B;欄留空。 例如，這可讓您從隔離區中移除回覆「STOP」以外訊息之使用者的電話號碼。

   ![](assets/sms_mo_3.png)

1. 在&#x200B;**[!UICONTROL Additional action]**&#x200B;欄位中，將動作連結至自動回覆：

   * **[!UICONTROL Send to quarantine]**&#x200B;動作會自動隔離設定檔電話號碼。
   * **[!UICONTROL Remove from quarantine]**&#x200B;動作會將設定檔電話號碼從隔離區中移除。
   * **[!UICONTROL None]**&#x200B;動作可讓您只傳送訊息給收件者，而不執行動作。

   例如，在以下配置中，如果收件者發送關鍵字「STOP」，則會自動收到取消訂閱確認，並且其電話號碼將被發送到狀態為&#x200B;**[!UICONTROL On denylist]**&#x200B;的隔離區。 此狀態僅指電話號碼，而設定檔是為使用者繼續收到電子郵件訊息。

   ![](assets/sms_mo.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。

1. 從SMS傳送&#x200B;**[!UICONTROL Properties]**&#x200B;的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;中，您可以設定特定&#x200B;**[!UICONTROL Short code]**&#x200B;以自動排除選擇退出的收件者。 有關詳細資訊，請參閱[此部分](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)。

您的收件者現在可以自動取消訂閱訊息，並透過此自動回覆傳送至隔離區。 隔離的收件者列在&#x200B;**[!UICONTROL Addresses]**&#x200B;表格中，該表格可透過&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**&#x200B;功能表取得。 有關隔離的詳細資訊，請參閱此[節](../../sending/using/understanding-quarantine-management.md)。

如有需要，可儲存這些傳入的SMS。 有關詳細資訊，請參閱此[節](#storing-incoming-sms)。

## 儲存傳入的SMS {#storing-incoming-sms}

在&#x200B;**[!UICONTROL SMS routing via SMPP]**&#x200B;外部帳戶中，您可以選擇儲存傳入的消息，例如當訂閱者回覆SMS消息時，以便從收件者清單中刪除。

![](assets/sms_config_mo_1.png)

透過檢查&#x200B;**[!UICONTROL SMPP channel settings]**&#x200B;類別中的&#x200B;**[!UICONTROL Store incoming MO in the database]**，所有SMS都會儲存在inSMS表格中，且可透過工作流程中的查詢活動擷取。

若要這麼做：

1. 在&#x200B;**[!UICONTROL SMPP channel settings]**&#x200B;欄位中，檢查&#x200B;**[!UICONTROL Store incoming MO in the database]**。

   ![](assets/sms_config_mo_2.png)

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;標籤中，按一下&#x200B;**[!UICONTROL Create]**，然後選擇&#x200B;**[!UICONTROL Workflow]**。

   ![](assets/sms_config_mo_3.png)

1. 選取您的工作流程類型。
1. 編輯工作流的屬性，然後按一下&#x200B;**[!UICONTROL Create]**。 如需建立工作流程的詳細資訊，請參閱此[區段](../../automating/using/building-a-workflow.md)。
1. 拖放&#x200B;**[!UICONTROL Query]**&#x200B;活動並連按兩下該活動。
1. 在查詢的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤中，在&#x200B;**[!UICONTROL Resource]**&#x200B;欄位中選擇&#x200B;**[!UICONTROL Incoming SMS (inSMS)]**。

   ![](assets/sms_config_mo_4.png)

1. 然後，在&#x200B;**[!UICONTROL Target]**&#x200B;標籤中，拖放&#x200B;**[!UICONTROL Incoming SMS attributes]**&#x200B;規則。

   ![](assets/sms_config_mo_5.png)

1. 在此，我們要定位從前一天開始的所有傳入郵件。 在&#x200B;**[!UICONTROL Field]**&#x200B;類別中，選擇&#x200B;**[!UICONTROL Creation date (created)]**。
1. 在&#x200B;**[!UICONTROL Filter type]**&#x200B;中，選擇&#x200B;**[!UICONTROL Relative]**，然後在&#x200B;**[!UICONTROL Level of precision]**&#x200B;中，選擇&#x200B;**[!UICONTROL Day]**。

   ![](assets/sms_config_mo_6.png)

1. 然後，您可以選擇從今天、前一天或最近幾天擷取資料。 配置查詢時，按一下&#x200B;**[!UICONTROL Confirm]**。

此查詢將根據所選時間範圍檢索收到的每條STOP消息。

例如，活動可讓您建立母體，並更妥善地個人化您的傳送。
