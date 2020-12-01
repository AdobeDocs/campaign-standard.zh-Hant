---
solution: Campaign Standard
product: campaign
title: 設計 A/B 測試電子郵件
description: 探索 A/B 測試功能，並依照以下步驟從 Adobe Campaign 的 A/B 測試範本建立電子郵件。
audience: channels
content-type: reference
topic-tags: email-messages
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 100%

---


# 設計 A/B 測試電子郵件{#designing-an-a-b-test-email}

Adobe Campaign 中的 A/B 測試功能允許您定義兩至三種電子郵件變體。已將每個變體發送至母體樣本，以確定哪個樣本具有最佳結果。一旦確定後，則會將成功變體發送至剩餘母體。

您可以選取更改電子郵件的內容、主旨或寄件者。

>[!NOTE]
>
>無法對在 Adobe Experience Manager 中建立的電子郵件進行 A/B 測試。

## 建立 A/B 測試電子郵件 {#creating-an-a-b-test-email}

您可使用標準電子郵件建立精靈來建立 A/B 測試，並新增 A/B 測試設定之步驟。如需建立標準電子郵件的詳細資訊，請參閱[建立電子郵件](../../channels/using/creating-an-email.md)區段。

在 A/B 測試的特定內容中：

1. 根據您想要更改的元素，從三個 A/B 測試特定範本之一中建立新電子郵件：

   * 寄件者的 A/B 測試
   * 內容的 A/B 測試
   * 主旨的 A/B 測試

   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >預設會隱藏後續與 A/B 測試範本。勾選左側的 A/B 測試方塊（**[!UICONTROL Filter]** 側面面板）以顯示。

1. 定義電子郵件的一般屬性與目標對象，就像標準電子郵件一樣。請參閱[建立對象](../../audiences/using/creating-audiences.md)區段。
1. 在建立精靈的第四個步驟中，定義 A/B 測試參數：

   * **[!UICONTROL Number of variants]**：您可以選取使用兩種或三種變體。如果您選取三種變體，則在精靈中確認此步驟後，就無法修改此選項。
   * **[!UICONTROL Winning strategy]**：選取用於確定成功變體的標準。
   * **[!UICONTROL Target breakdown]**：選取目標中將接收每個變體的百分比。一旦確定成功變體後，剩餘百分比將接收它。目標設定檔是隨機選取的。
   * **[!UICONTROL Winner sending method]**：選取您是否希望在確定成功變體後自動發送，或者是否要手動確認發送至剩餘母體。
   * **[!UICONTROL Test duration]**：指定測試的持續時間。在此期間後，會自動確定成功變體。您可以在測試結束前從電子郵件控制面板手動選取成功變體。

      測試必須至少進行一個小時，以便收集所有追蹤資料並正確地考慮以選取成功變體。
   ![](assets/ab_parameters.png)

1. 定義 A/B 測試參數後，請轉至精靈的下一步，並定義電子郵件內容。根據您所選取的範本，您可以定義多個主旨、數個寄件者名稱或數個不同內容。使用浮動切換在元素的不同變體之間進行導覽。如需詳細資訊，請參閱[內容編輯器](../../designing/using/designing-content-in-adobe-campaign.md)區段。

   ![](assets/create_ab_testing2.png)

1. 確認建立電子郵件。然後會顯示電子郵件控制面板。
1. 排程傳送。定義的日期表示 A/B 測試的開始。
1. 檢查 **[!UICONTROL A/B test parameters]** 區塊中顯示的 A/B 測試參數。您可以修改測試，直到您透過選取區塊以確認傳送測試（步驟 9）為止。

   ![](assets/create_ab_testing3.png)

1. 準備電子郵件傳送以分析目標及要傳送之訊息數量。請參閱[準備傳送](../../sending/using/preparing-the-send.md)區段。
1. 在傳送 A/B 測試之前，請先傳送證明以檢查您的電子郵件。
1. 準備完成後，請確認傳送測試。確認後，A/B 測試參數便無法修改。

   A/B 測試從 **[!UICONTROL Schedule]**&#x200B;中定義的日期開始 。您可以使用 **[!UICONTROL A/B test]** 與 **[!UICONTROL Deployment]** 區塊來追蹤進度。

   如果您想要縮短測試的持續時間，可以隨時手動選取成功變體。

   測試完成後，**[!UICONTROL A/B Test]** 區塊中會顯示摘要資料表，允許您檢視所測試的不同變體的各種指標。

1. 如果您已選取 **[!UICONTROL Send after confirmation]** 作為發送方法，則必須手動選取成功變體，以開始將其傳送至剩餘母體。如果您已選取 **[!UICONTROL Automatic]**，則成功變數會在系統確定後立即自動傳送至剩餘母體。

   >[!NOTE]
   >
   >如果此處打結，則必須手動選取成功變體。您可以通知電子郵件建立者與修改者已選取變體或需要選取變體。請參閱 [Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)。

您的電子郵件現在已定義並傳送。您可以存取其日誌與報告，以評估行銷活動的成功。

## 關於 A/B 測試指標 {#about-a-b-test-indicators}

在電子郵件控制面板中，有數個指標可以協助您測量 A/B 測試： 點按次數、開啟次數、彈出次數等。

請注意，**[!UICONTROL Estimated recipient reactivity]** 指標是將點按的收件者人數量與開啟電子郵件的收件者人數量相比之比率。例如，如果有 10 位收件者開啟電子郵件，而有 5 位收件者按了該電子郵件。反應率為 50%。
