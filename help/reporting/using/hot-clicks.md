---
title: 熱點點擊
description: 透過現成可用的熱門點選報告，瞭解客戶在傳送時點選的位置。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 5af37156-e93b-4ae9-9856-053364f211ef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# 熱點點擊{#hot-clicks}

此報表可從以下位置存取： **[!UICONTROL Reports]** 每個傳遞或交易式訊息中的按鈕。

![](assets/delivery_reports_hot-clicks_4.png)

它會顯示訊息內容(HTML和/或文字)以及每個連結的點按百分比。

![](assets/delivery_reports_10.png)

如果您為傳送建立了動態內容，即可檢視您所定義每個條件的百分比。 如需在傳遞中插入條件式內容的詳細資訊，請參閱 [定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

例如，假設您建立的傳送符合以下條件：

* 如果收件者是男性或女性，則主要影像上的連結會不同。
* 您也新增了特殊優惠的連結，但僅限25歲以上的收件者看到。

傳送訊息之後，請選取 **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** 從傳遞控制面板。

依預設，不會選取任何設定檔。 僅顯示性別不明的收件者以及25歲以下或年齡不明的收件者的點按。

![](assets/delivery_reports_hot-clicks_1.png)

若要顯示女性的點按次數，請按一下 **[!UICONTROL Change profile]** 按鈕並選取女性測試設定檔。 若要顯示男性的點按次數，請以類似方式繼續並選取男性測試設定檔。

![](assets/delivery_reports_hot-clicks_2.png)

若要顯示25歲以上收件者的點選次數，請按一下 **[!UICONTROL Change profile]** 按鈕並選取其出生日期符合此條件的測試設定檔。

如需測試設定檔的詳細資訊，請參閱 [關於測試設定檔](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>特定連結的點按次數是傳遞中所有條件式內容的總點按次數的百分比。 因此，如果您定義了動態內容，則針對特定測試設定檔顯示的總百分比可能不等於100。

同樣地，對於循環傳送和交易式訊息，您可以選取與您要顯示之動態內容對應的測試設定檔，但您也可以根據所選的執行傳送檢視點按百分比。

執行傳送是無法執行且無法運作的技術訊息，會在下列情況下建立：

* 每次執行或更新循環傳送時。

  例如，如果管理此傳送的工作流程每月執行一次，則每月將有一個執行傳送。 此外，每次更新傳送的內容時，都會建立額外的執行傳送。

  如需定期電子郵件傳送的詳細資訊，請參閱 [電子郵件傳遞](../../automating/using/email-delivery.md).

* 根據預設，交易式訊息每月會發佈一次，且每次都會編輯並再次發佈交易式訊息。

  如需異動訊息的詳細資訊，請參閱 [開始使用異動訊息](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>由於每個執行的追蹤URL的ID不同，因此無法彙總指定訊息的所有執行傳遞的熱點按資料。 一次只能針對一個執行傳送顯示它。

傳送訊息之後，請選取 **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** 從傳遞控制面板。

依預設，會選取最後一個執行傳送。 按一下 **[!UICONTROL Change execution delivery]** 按鈕以選取另一個按鈕。

![](assets/delivery_reports_hot-clicks_3.png)

系統只會顯示所選傳送執行的點按百分比。
