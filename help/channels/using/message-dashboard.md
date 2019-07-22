---
title: 訊息控制面板
seo-title: 訊息控制面板
description: 訊息控制面板
seo-description: 瞭解訊息控制面板的用途，包括動作列和各種功能區塊。
page-status-flag: 從未啓動
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e467913
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 關於通訊頻道
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: 傳送，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 25d997b2e5aa41e29e49ab047398b3db811bd6b6

---


# Message dashboard{#message-dashboard}

訊息控制面板是由不同圖示組成的工作區-重新群組至動作列，並可讓您建立訊息參數並傳送給您。以下列出這些元素。

![](assets/delivery_dashboard_2.png)

## Gray bar {#gray-bar}

灰色列會重新整理與您訊息連結的各種圖示。

* **[!UICONTROL Summary]**：顯示/隱藏訊息的主要資訊。
* **[!UICONTROL Edit properties]**：可讓您編輯訊息 [的進階參數](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**：可讓您存取訊息相關的報表。

**相關主題：**

* [設定渠道](../../administration/using/about-channel-configuration.md)
* [存取報表](../../reporting/using/about-dynamic-reports.md)

## Action bar {#action-bar}

動作列有不同的圖示，可讓您與您的訊息互動。

![](assets/delivery_dashboard_4.png)

視已設定的參數和已完成的進度而定，某些圖示可能無法使用。

* **[!UICONTROL Show proofs]**：顯示/隱藏已傳送的校樣清單(如果有的話)。當您已傳送校樣時，此按鈕才會啓用。

   For more on proofs, see [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

* **[!UICONTROL Send a test]**：可讓您選擇要使用的核准模式： **[!UICONTROL Email rendering]**&#x200B;或 **[!UICONTROL Proof]** 兩者皆為電子郵件。For more on test profiles, see [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   只有在您建立測試設定檔後，才會啓用此按鈕。

   >[!NOTE]
   >
   >For an SMS message, there is no other choice: it is automatically a **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**：開始準備傳送。**[!UICONTROL Deployment]** 區塊隨即出現，並顯示準備結果。只有在輸入目標後，才會顯示此按鈕。您可以隨時使用對應的按鈕停止準備。

   For more on message preparation, [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**：確認傳送訊息。The sending statistics appear in the **[!UICONTROL Deployment]** block. 此按鈕只會在傳送完成後顯示。You can stop or pause the send at any time using the **Stop send** and **[!UICONTROL Pause]** buttons.

   For more on confirming sending, see [Sending messages](../../sending/using/confirming-the-send.md).

## Blocks {#blocks}

主畫面由不同區塊組成。按一下區塊內部以存取對應的參數畫面：

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**：可讓您追蹤訊息準備進度或傳送進度。按一下此區塊右下方區段中的按鈕，即可存取傳送和分析記錄檔。只有在準備好傳送後，才會顯示此區塊。如需詳細資訊，請參閱。See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**：可讓您建立訊息的主要目標以及測試設定檔。See [Creating audiences](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**：可讓您指定訊息傳送的日期。See [Scheduling](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**：可讓您定義訊息的內容並加以預覽。See [Defining content](../../designing/using/designing-content-in-adobe-campaign.md).

