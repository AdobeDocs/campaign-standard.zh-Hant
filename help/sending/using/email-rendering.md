---
title: 電子郵件演算
seo-title: 電子郵件演算
description: 電子郵件演算
seo-description: 探索電子郵件轉換功能。
page-status-flag: 從未啓動
uuid: c423e237-ad39-4797-ac3 a-4320894a8 f99
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: 準備與測試訊息
discoiquuid: 2b5b13c8-2e51-4985-a161-c1 d7 f0 c32 b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Email rendering{#email-rendering}

Before hitting the **[!UICONTROL Send]** button, make sure that your message will be displayed in an optimal way on a variety of web clients, web mails and devices.

若要允許此選項，Adobe Campaign會擷取演算，並可在專用報表中使用。這可讓您在可能收到的不同內容中預覽傳送的訊息。

The mobile, messaging and webmail clients available for **Email rendering** in Adobe Campaign are listed on the Litmus [website](https://litmus.com/email-testing) (click **View all email clients**).

## Checking the Email rendering report {#checking-the-email-rendering-report}

當您建立電子郵件傳送並定義其內容以及目標人口後，請遵循以下步驟。

1. Click **Audience** to access the **[!UICONTROL Test profiles]** tab.

   ![](assets/email_rendering_05.png)

1. Use the query editor to define the test profiles that you want to use, including the test profiles that are for **Email rendering** use. See [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

   ![](assets/email_rendering_06.png)

1. 檢查並確認您的查詢，然後儲存您的變更。
1. Click the **[!UICONTROL Test]** button in the action bar.

   ![](assets/email_rendering_07.png)

1. Select the **[!UICONTROL Email rendering]** option then click **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >**[!UICONTROL Proof + Email rendering]** 此選項可讓您傳送校樣並同時使用電子郵件演算功能。您可以由校訂收件者核准您的訊息，同時您也可以根據目標收件匣測試接收訊息的方式。在此情況下，您也需要選取「校對測試設定檔」。See [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

   測試傳送會傳送。

1. 傳送訊息後幾分鐘即可顯示縮圖。To access them, select **[!UICONTROL Proofs]** in the **[!UICONTROL Summary]** drop-down list.

   ![](assets/email_rendering_03.png)

1. From the **[!UICONTROL Proofs]** list, click the **[!UICONTROL Access email rendering]** icon.

   ![](assets/email_rendering_04.png)

專用的電子郵件轉換報告隨即顯示。See [Email rendering report description](../../sending/using/email-rendering.md#email-rendering-report-description).

**相關主題**：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [管理測試設定檔並傳送校樣](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [查詢編輯器](../../automating/using/editing-queries.md#about-query-editor)

## Email rendering report description {#email-rendering-report-description}

此報表會顯示收件者顯示的電子郵件轉譯。電子郵件轉譯可能因收件者開啓電子郵件傳送而異：在瀏覽器、行動裝置或透過電子郵件應用程式。

>[!NOTE]
>
>您的授權合約中會列出可用的轉譯數目。Each delivery with **Email rendering** enabled decreases your available renderings (known as tokens) by one. 如果您是Litmus客戶，可以使用您自己的Litmbus帳戶來布建並使用Adobe Campaign中的電子郵件演算。如需更多資訊，請聯絡您的Adobe銷售代表。

報表摘要會顯示收到的訊息數、不需要的(垃圾郵件)、未接收或擱置中的接收次數。

![](assets/inbox_rendering_report.png)

The report is divided into three parts: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]**, and **[!UICONTROL Webmails]**. 向下捲動報表，顯示所有歸類為這三個類別的轉譯。

![](assets/inbox_rendering_report_3.png)

若要取得每個報表的詳細資訊，請按一下對應的卡片。會針對選取的接收方法顯示演算。

![](assets/inbox_rendering_report_2.png)

**[!UICONTROL Technical data]** 此標籤可讓您取得更多資訊，例如接收和擷取日期，以及電子郵件的完整標題。
