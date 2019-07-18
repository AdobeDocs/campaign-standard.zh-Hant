---
title: 熱門點按
seo-title: 熱門點按
description: 熱門點按
seo-description: 透過「Hot Click-the-the-the-the-box」報告，瞭解客戶在您傳送時點按的位置。
page-status-flag: 從未啓動
uuid: 7ed49dd3-d7 ee-466a-9a7 b-d2 aa16961667
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 報告功能
content-type: reference
topic-tags: 報表清單
discoiquuid: ecc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: Delivery HotclicksReport，main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Hot clicks{#hot-clicks}

This report can be accessed from the **[!UICONTROL Reports]** button in each delivery or transactional message.

![](assets/delivery_reports_hot-clicks_4.png)

它會以每個連結的點按百分比呈現訊息內容(HTML和/或文字)。

![](assets/delivery_reports_10.png)

如果您為傳送建立動態內容，則可以檢視每個條件所定義的百分比。For more on inserting conditional content in a delivery, see [Defining dynamic content](../../designing/using/defining-dynamic-content-in-a-landing-page.md).

例如，假設您使用下列條件建立了傳送：

* 如果收件者是男性或女性，主要影像上的連結就不同。
* 您也新增了特殊選件的連結，僅限25以上的收件者看得到。

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

依預設，不會選取任何描述檔。只會針對未知的收件者以及25歲以下或年齡不明的收件者按一下點擊。

![](assets/delivery_reports_hot-clicks_1.png)

To display clicks for women, click the **[!UICONTROL Change profile]** button and select a female test profile. 若要顯示男性的點按次數，請按類似方式繼續，然後選取男性測試設定檔。

![](assets/delivery_reports_hot-clicks_2.png)

To display clicks for recipients over 25, click the **[!UICONTROL Change profile]** button and select a test profile whose birth date is matching this condition.

For more on test profiles, see [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

>[!NOTE]
>
>特定連結的點按次數是傳送中所有條件內容的點按總次數百分比。因此，如果您定義動態內容，則特定測試設定檔所顯示的百分比總計可能不等於100。

同樣地，對於週期性傳送和交易訊息，您可以選取對應至您要顯示之動態內容的測試設定檔，但也可以根據選取的執行傳送來檢視點按百分比。

執行傳送是不可操作的非功能技術訊息，在下列情況下建立：

* 每次執行或更新循環傳送。

   例如，如果管理此傳送的工作流程每月執行一次，每個月將會有一次執行傳送。此外，每次更新內容時，都會建立額外的執行傳送。

   For more on recurring email deliveries, see [Email delivery](../../automating/using/email-delivery.md).

* 根據交易訊息，每個月預設一次，且每次編輯交易訊息並重新發佈。

   For more on transactional messages, see [About transactional messaging](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>因為每個執行的追蹤URL ID不同，因此無法匯總指定訊息的所有執行傳送資料。它只能顯示一次執行一次傳送。

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

依預設，會選取最後一個執行傳送。Click the **[!UICONTROL Change execution delivery]** button to select another one.

![](assets/delivery_reports_hot-clicks_3.png)

只會顯示所選傳送執行的點按百分比。
