---
title: 電子郵件呈現
description: 探索電子郵件轉換功能。
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b43e6be265ff2d8ce357ef44672a755028e2e5af
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%

---


# 電子郵件呈現{#email-rendering}

在按下按 **[!UICONTROL Send]** 鈕之前，請確定您的訊息會以最佳方式顯示在各種網頁用戶端、網頁郵件和裝置上。

為了允許此動作，Adobe Campaign會擷取轉譯，並將它提供在專用報表中。 這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

Adobe Campaign中提供的行動裝置、傳訊和 **Email轉譯** ( [Email](https://litmus.com/email-testing) )用戶端會列在 **Litmus網站**（按一下「檢視所有電子郵件用戶端」）。

## 勾選「電子郵件」轉換報表 {#checking-the-email-rendering-report}

在您建立電子郵件傳送並定義其內容以及目標群體後，請遵循下列步驟。

1. 按一 **下「對象** 」以存取 **[!UICONTROL Test profiles]** 索引標籤。

   ![](assets/email_rendering_05.png)

1. 使用查詢編輯器定義您要使用的測試設定檔，包括用於電子郵件轉譯的測 **試設定檔** 。 請參閱 [關於測試設定檔](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_rendering_06.png)

1. 檢查並確認查詢，然後儲存變更。
1. 按一下 **[!UICONTROL Test]** 動作列中的按鈕。

   ![](assets/email_rendering_07.png)

1. 選取選 **[!UICONTROL Email rendering]** 項，然後按一下 **[!UICONTROL OK]**。

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >此選 **[!UICONTROL Proof + Email rendering]** 項可讓您傳送證明並同時使用電子郵件轉譯功能。 您可以讓證明收件者核准您的訊息，同時也可以根據所定位的收件箱來測試訊息的接收方式。 在這種情況下，您也需要選取「校對測試描述檔」。 請參閱 [關於測試設定檔](../../audiences/using/managing-test-profiles.md)。

   測試傳送會傳送。

1. 傳送訊息後幾分鐘即可使用轉換縮圖。 若要存取它們，請 **[!UICONTROL Proofs]** 在下拉式 **[!UICONTROL Summary]** 清單中選取。

   ![](assets/email_rendering_03.png)

1. 從清單 **[!UICONTROL Proofs]** 中按一下圖 **[!UICONTROL Access email rendering]** 示。

   ![](assets/email_rendering_04.png)

此時會顯示專用的電子郵件轉譯報告。 請參 [閱電子郵件轉換報表說明](#email-rendering-report-description)。

**相關主題**:

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [傳送校樣](../../sending/using/sending-proofs.md)
* [查詢編輯器](../../automating/using/editing-queries.md#about-query-editor)

## 電子郵件轉換報表說明 {#email-rendering-report-description}

此報告會以電子郵件呈現方式呈現收件者的呈現方式。 電子郵件轉譯會因收件者開啟電子郵件傳送的方式而異： 在瀏覽器、行動裝置上，或透過電子郵件應用程式。

>[!NOTE]
>
>您的授權合約中會列出可用的轉譯數。 每次啟用「電 **子郵件轉譯** 」的傳送，都會將您的可用轉譯（稱為Token）減少一。

報表摘要會顯示收到、不想要（垃圾訊息）、未收到或待接收的訊息數。

![](assets/inbox_rendering_report.png)

報告分為三部分： **[!UICONTROL Mobile]**、 **[!UICONTROL Messaging clients]**&#x200B;和 **[!UICONTROL Webmails]**。 向下捲動報表，以顯示分成這三個類別的所有轉譯。

![](assets/inbox_rendering_report_3.png)

若要取得每個報表的詳細資訊，請按一下對應的資訊卡。 顯示所選接收方法的渲染。

![](assets/inbox_rendering_report_2.png)

此標 **[!UICONTROL Technical data]** 簽可讓您取得更多資訊，例如接收和擷取日期，以及電子郵件的完整標題。
