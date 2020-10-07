---
title: 熱點點按
description: 透過「快速點按現成可用報表」，瞭解客戶在何處點按您的遞送。
page-status-flag: never-activated
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 熱點點按{#hot-clicks}

您可從每個傳送或交易訊息 **[!UICONTROL Reports]** 中的按鈕存取此報表。

![](assets/delivery_reports_hot-clicks_4.png)

它以每個連結的點按百分比呈現訊息內容（HTML和／或文字）。

![](assets/delivery_reports_10.png)

如果您為傳送建立動態內容，則可以檢視您定義之每個條件的百分比。 如需在傳送中插入條件式內容的詳細資訊，請參 [閱定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

例如，假設您建立的傳送包含下列條件：

* 如果收件者是男性或女性，則主影像上的連結會有所不同。
* 您也新增了特殊選件的連結，該連結只會顯示給25歲以上的收件者。

傳送訊息後，從傳送控制面板 **[!UICONTROL Reports]** 中選 **[!UICONTROL Hot clicks]** 取>。

預設情況下，未選擇任何配置檔案。 只會顯示性別未知的收件者，以及年齡未滿25歲或未知的收件者的點按。

![](assets/delivery_reports_hot-clicks_1.png)

若要顯示女性的點按次數，請按一 **[!UICONTROL Change profile]** 下按鈕並選取女性測試設定檔。 若要顯示男性的點按次數，請以類似方式進行，並選取男性測試設定檔。

![](assets/delivery_reports_hot-clicks_2.png)

若要顯示25歲以上收件者的點按次數，請按一 **[!UICONTROL Change profile]** 下按鈕並選取出生日期符合此條件的測試描述檔。

如需測試設定檔的詳細資訊，請參 [閱關於測試設定檔](../../audiences/using/managing-test-profiles.md)。

>[!NOTE]
>
>特定連結的點按次數是傳送中所有條件內容點按總數的百分比。 因此，如果您定義動態內容，特定測試描述檔顯示的百分比總數可能不等於100。

同樣地，對於週期性傳送和事務性訊息，您可以選取與您要顯示的動態內容對應的測試描述檔，但您也可以根據選取的執行傳送來檢視點按百分比。

執行傳送是在下列情況下建立的不可操作且無功能的技術訊息：

* 每次執行或更新循環傳送時。

   例如，如果每月執行一次管理此傳送的工作流程，則每月會執行一次傳送。 此外，每次更新傳送的內容時，都會建立額外的執行傳送。

   如需循環傳送電子郵件的詳細資訊，請參 [閱電子郵件傳送](../../automating/using/email-delivery.md)。

* 預設情況下，每月只對事務性消息執行一次，而且每次編輯並再次發佈事務性消息時。

   有關事務性消息的詳細資訊，請參 [閱事務性消息快速入門](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>由於每個執行的追蹤URL ID不同，因此無法針對指定訊息的所有執行傳送來匯整熱點點按資料。 一次只能顯示一個執行傳送。

傳送訊息後，從傳送控制面板 **[!UICONTROL Reports]** 中選 **[!UICONTROL Hot clicks]** 取>。

依預設，會選取上次執行傳送。 按一下按 **[!UICONTROL Change execution delivery]** 鈕以選取另一個按鈕。

![](assets/delivery_reports_hot-clicks_3.png)

只會顯示所選傳送執行的點按百分比。
