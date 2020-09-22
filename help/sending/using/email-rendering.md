---
title: 電子郵件呈現
description: 探索電子郵件呈現功能。
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
source-git-commit: 3af649cfaae195ae5e75406ca3a0743b9b1f65d2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 電子郵件呈現{#email-rendering}

在按下 **[!UICONTROL Send]** 按鈕之前，請確定您的郵件會以最佳方式顯示在各種 Web 用戶端、網頁郵件與裝置上。

為了執行此操作，Adobe Campaign 會擷取呈現，並將之用於專用報告中。這可讓您在可接收訊息的不同內容中預覽所傳送的訊息。

Litmus [網站](https://litmus.com/email-testing)列出可在 Adobe Campaign 中用於&#x200B;**電子郵件呈現**&#x200B;的行動裝置、傳送訊息與網頁郵件客戶端（請按一下&#x200B;**檢視所有電子郵件客戶端**）。

## 檢查電子郵件呈現報告 {#checking-the-email-rendering-report}

在您建立電子郵件傳送並定義其內容以及目標定位人口族群後，請遵循下列步驟。

1. 按一下「**對象**」以存取 **[!UICONTROL Test profiles]** 標籤。

   ![](assets/email_rendering_05.png)

1. 使用查詢編輯器定義您要使用的測試設定檔，包括用於&#x200B;**電子郵件呈現**&#x200B;的測試設定檔。請參閱[關於測試設定檔](../../audiences/using/managing-test-profiles.md)。

   ![](assets/email_rendering_06.png)

1. 檢查並確認查詢，然後儲存變更。
1. 按一下動作列中的 **[!UICONTROL Test]** 按鈕。

   ![](assets/email_rendering_07.png)

1. 選取 **[!UICONTROL Email rendering]** 選項，然後按一下 **[!UICONTROL OK]**。

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >**[!UICONTROL Proof + Email rendering]** 選項可讓您在傳送證明並同時使用電子郵件呈現功能。您可以讓證明收件者核准您的郵件，同時也可以根據目標收件匣來測試接收郵件的方式。在此情況下，您也需要選取「證明測試設定檔」。請參閱[關於測試設定檔](../../audiences/using/managing-test-profiles.md)。

   已傳送測試傳送。

1. 傳送郵件之後幾分鐘，即可使用呈現縮圖。若要存取縮圖，選取 **[!UICONTROL Summary]** 下拉式清單中的 **[!UICONTROL Proofs]**。

   ![](assets/email_rendering_03.png)

1. 從清單 **[!UICONTROL Proofs]** 按一下圖示 **[!UICONTROL Access email rendering]**。

   ![](assets/email_rendering_04.png)

此時會顯示專用的電子郵件呈現報告。請參閱[電子郵件呈現報告說明](#email-rendering-report-description)。

**相關主題**：

* [建立電子郵件](../../channels/using/creating-an-email.md)
* [傳送校樣](../../sending/using/sending-proofs.md)
* [查詢編輯器](../../automating/using/editing-queries.md#about-query-editor)

## 電子郵件呈現報告說明 {#email-rendering-report-description}

此報告會以收件者看到的方式來顯示電子郵件呈現。電子郵件呈現會因收件者開啟電子郵件傳送的方式而異：在瀏覽器中、行動裝置上，或是透過電子郵件應用程式。

>[!NOTE]
>
>您的授權協議中會列出可用的呈現數量。每次啟用「**電子郵件呈現**」傳送時，您的可用呈現（也稱為 Token）都會減少一次。
>
>Token帳戶是每個個別轉譯，而非整個「電子郵件」轉譯報表，這表示：
>
>**每次產生** 「收件匣」轉譯報表時，會扣除每個訊息傳送用戶端一個代號：一個Outlook 2000轉譯的Token、一個Outlook轉譯的Token、一個Apple Mail轉譯的Token，等等。
>
>**對於相同的傳送**，如果您再次產生電子郵件轉譯，可用的Token數量會依產生的轉譯數量而再次減少。


報告摘要會顯示已接收、不想要（垃圾郵件）、未接收或待接收的郵件數目。

![](assets/inbox_rendering_report.png)

報告分為三部分：**[!UICONTROL Mobile]**、**[!UICONTROL Messaging clients]** 及 **[!UICONTROL Webmails]**。向下捲動報告，以顯示分為這三種類別的所有呈現。

![](assets/inbox_rendering_report_3.png)

若要取得每個報告的詳細資料，請按一下相對應的卡片。會針對所選取接收方法來顯示呈現。

![](assets/inbox_rendering_report_2.png)

**[!UICONTROL Technical data]** 標籤可讓您取得詳細資訊，例如接收和擷取日期，以及電子郵件的完整標題。
