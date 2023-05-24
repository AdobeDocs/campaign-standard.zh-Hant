---
title: 熱點點擊
description: 通過「熱點按一下開箱即用」報告，瞭解客戶在交貨中的點擊位置。
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
source-wordcount: '477'
ht-degree: 0%

---

# 熱點點擊{#hot-clicks}

可以從 **[!UICONTROL Reports]** 按鈕。

![](assets/delivery_reports_hot-clicks_4.png)

它以每個連結上的點擊百分比顯示消息內容(HTML和/或文本)。

![](assets/delivery_reports_10.png)

如果您為交付建立了動態內容，則可以查看您定義的每個條件的百分比。 有關在傳遞中插入條件內容的詳細資訊，請參見 [定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

例如，假設您建立了具有以下條件的交貨：

* 如果接受者是男性或女性，則主影像上的連結會有所不同。
* 您還添加了一個特惠連結，該特惠僅對25歲以上的收件人可見。

發送消息後，選擇 **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** 從交貨儀表板。

預設情況下，未選擇任何配置檔案。 只顯示性別未知的接收者和年齡未知的25歲以下接收者的按一下。

![](assets/delivery_reports_hot-clicks_1.png)

要顯示女性的點擊量，請按一下 **[!UICONTROL Change profile]** 按鈕，選擇母test配置檔案。 要顯示男性的點擊量，請按類似方式繼續並選擇男性test配置檔案。

![](assets/delivery_reports_hot-clicks_2.png)

要顯示25歲以上的收件人的按一下，請按一下 **[!UICONTROL Change profile]** 按鈕，然後選擇出生日期與此條件匹配的test配置檔案。

有關test配置檔案的詳細資訊，請參閱 [關於test配置檔案](../../audiences/using/managing-test-profiles.md)。

>[!NOTE]
>
>特定連結上的按一下次數是傳遞中所有條件內容的總按一下次數的百分比。 因此，如果定義了動態內容，則為特定test配置檔案顯示的百分比總數可能不等於100。

同樣，對於循環交貨和事務性消息，您可以選擇與要顯示的動態內容對應的test配置檔案，但您也可以根據所選執行交貨查看按一下的百分比。

執行傳遞是在以下情況下建立的不可操作且無功能的技術消息：

* 每次執行或更新循環交貨時。

   例如，如果每月執行一次管理此交貨的工作流，則每月將執行一次交貨。 此外，每次更新遞送的內容時，都會建立附加的執行遞送。

   有關定期電子郵件遞送的詳細資訊，請參閱 [電子郵件傳遞](../../automating/using/email-delivery.md)。

* 預設情況下，事務性消息每月一次，每次編輯並再次發佈事務性消息時都是如此。

   有關事務性消息的詳細資訊，請參見 [事務性消息服務入門](../../channels/using/getting-started-with-transactional-msg.md)。

>[!NOTE]
>
>由於跟蹤的URL的ID對於每個執行都不同，因此不能針對給定消息的所有執行傳遞聚合熱點擊資料。 一次只能顯示一個執行傳遞。

發送消息後，選擇 **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** 從交貨儀表板。

預設情況下，將選擇最後一個執行傳遞。 按一下 **[!UICONTROL Change execution delivery]** 按鈕。

![](assets/delivery_reports_hot-clicks_3.png)

只顯示所選交貨執行的按一下百分比。
