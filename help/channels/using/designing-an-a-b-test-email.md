---
title: 設計 A/B 測試電子郵件
description: 探索A/B測試功能，並依照下列步驟從Adobe Campaign的A/B測試範本建立電子郵件。
page-status-flag: never-activated
uuid: 104f6973-68a7-4692-a90a-a5570a980ec7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: e249ba70-90d0-43f2-868c-ce9fdc7e642d
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# 設計 A/B 測試電子郵件{#designing-an-a-b-test-email}

Adobe Campaign中的A/B測試功能可讓您定義兩到三種電子郵件變體。 每個變型都被發送到種群樣本，以確定哪個樣本具有最佳結果。 一旦確定，則成功變數隨後被發送到剩餘人口。

您可以選擇變更電子郵件的內容、主旨或寄件者。

>[!NOTE]
>
>A/B測試在Adobe Experience manager中建立的電子郵件不可能。

## Creating an A/B test email {#creating-an-a-b-test-email}

您可使用標準電子郵件建立精靈來建立A/B測試，並新增A/B測試設定步驟。 建立標準電子郵件的詳細資訊，請參閱「 [建立電子郵件](../../channels/using/creating-an-email.md) 」一節。

在A/B測試的特定內容中：

1. 根據您要變更的元素，從三個A/B測試特定範本之一建立新電子郵件：

   * 傳送者A/B測試
   * 內容的A/B測試
   * 主題A/B測試
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >預設會隱藏後續和A/B測試範本。 勾選左側的A/B測試方塊(側 **[!UICONTROL Filter]** 面板)以顯示。

1. 定義電子郵件的一般屬性和目標對象，就像標準電子郵件一樣。 請參閱「建 [立觀眾](../../audiences/using/creating-audiences.md) 」區段。
1. 在建立精靈的第四個步驟中，定義A/B測試參數：

   * **[!UICONTROL Number of variants]**:您可以選擇使用兩、三種變體。 如果您選擇三種變體，則在精靈中確認此步驟後，就無法修改此選項。
   * **[!UICONTROL Winning strategy]**:選擇用於確定成功變數的標準。
   * **[!UICONTROL Target breakdown]**:選擇目標中將接收每個變數的百分比。 一旦確定成功變數，剩餘百分比將接收它。 目標描述檔會隨機選取。
   * **[!UICONTROL Winner sending method]**:選擇您是否希望成功變體在確定後自動發送，或者是否要手動確認發送給剩餘人口。
   * **[!UICONTROL Test duration]**:指定測試的持續時間。 在此期間後，會自動確定成功變數。 您可以在測試結束前從電子郵件儀表板手動選擇成功變體。

      測試必須至少一小時，才能收集所有追蹤資料並正確考慮以選擇成功變數。
   ![](assets/ab_parameters.png)

1. 定義A/B測試參數後，請傳遞至精靈的下一步，並定義電子郵件內容。 根據您選擇的範本，您可以定義多個主題、數個傳送者名稱或數個不同的內容。 使用轉盤在元素的不同變體之間導覽。 如需詳細資訊，請參閱內容 [編輯器一節](../../designing/using/designing-content-in-adobe-campaign.md) 。

   ![](assets/create_ab_testing2.png)

1. 確認建立電子郵件。 然後會顯示電子郵件控制面板。
1. 排程傳送。 定義的日期表示A/B測試的開始。
1. 檢查塊中顯示的A/B測試參 **[!UICONTROL A/B test parameters]** 數。 您可以修改測試，直到您選擇區塊以確認傳送測試（步驟9）為止。

   ![](assets/create_ab_testing3.png)

1. 準備電子郵件傳送以分析目標及要傳送的訊息數目。 請參閱「 [準備傳送](../../sending/using/preparing-the-send.md) 」區段。
1. 傳送A/B測試前，請先傳送校樣以檢查您的電子郵件。
1. 準備完成後，請確認傳送測試。 確認後，A/B測試參數便無法修改。

   A/B測試從中定義的日期開始 **[!UICONTROL Schedule]**。您可以使用和塊來追蹤 **[!UICONTROL A/B test]** 其進 **[!UICONTROL Deployment]** 度。

   如果您想要縮短測試持續時間，可隨時手動選取成功變數。

   測試完成後，區塊中會顯示摘要表 **[!UICONTROL A/B Test]** 格，這可讓您檢視測試的不同變數的各種指標。

1. 如果您已選 **[!UICONTROL Send after confirmation]** 擇作為發送方法，則必須手動選擇成功變數，以開始將其發送到其餘人口。 如果您已選 **[!UICONTROL Automatic]**&#x200B;取，則成功變數會在系統確定後立即自動傳送至剩餘人口。

   >[!NOTE]
   >
   >如果有系結，則必須手動選取成功變體。 您可以通知電子郵件建立者和修改者已選擇變體或需要選擇變體。 請參 [閱Adobe Campaign通知](../../administration/using/sending-internal-notifications.md)。

您的電子郵件現在已定義並傳送。 您可以存取其記錄檔和報表，以評估促銷活動的成功。

**相關主題**:

[建立電子郵件](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) 視訊

## 關於A/B測試指標 {#about-a-b-test-indicators}

在電子郵件儀表板中，有幾個指標可協助您測量A/B測試：點按次數、開啟次數、彈回數等。

請注意，此 **[!UICONTROL Estimated recipient reactivity]** 指標是比較點按的收件者人數與開啟電子郵件的收件者人數的比率。 例如，如果有10位收件者開啟電子郵件，而有5位收件者點按了該電子郵件。 反應率為50%。
