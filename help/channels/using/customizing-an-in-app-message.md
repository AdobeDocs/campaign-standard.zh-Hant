---
title: 自訂應用程式內訊息
description: 瞭解如何使用各種選項來自訂您的應用程式內訊息。
page-status-flag: never-activated
uuid: 1d9c08ed-4de5-440d-bf51-4a437eec67d5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: c9c3e033-e319-447b-8d87-ff7dd4941876
context-tags: delivery,inAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4efc42fd6b656c7723ed52f704c801113f9b3817
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 100%

---


# 自訂應用程式內訊息{#customizing-an-in-app-message}

若要微調您的應用程式內訊息，Adobe Campaign 可讓您在設計應用程式內訊息時存取一組進階選項。

應用程式內內容編輯器可讓您在兩種應用程式內訊息模式之間進行選取：

* [訊息範本](#customizing-with-a-message-template)：此範本可讓您使用影像或影片及動作按鈕，以完全自訂應用程式內訊息。
* [自訂訊息](#customizing-with-a-custom-html-message)：此範本可讓您匯入自訂 HTML。

![](assets/inapp_customize_1.png)

>[!NOTE]
>
> 應用程式內訊息呈現僅支援 Android API 19 及更新版本。

**相關主題：**

* [傳送您的應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [應用程式內報告](../../reporting/using/in-app-report.md)
* [實施本機通知追蹤](../../administration/using/local-tracking.md)

## 使用訊息範本自訂 {#customizing-with-a-message-template}

### 版面 {#layout}

根據您的訊息傳送需求，**[!UICONTROL Layout]** 下拉式清單提供四種不同的選項供您選取：

* **[!UICONTROL Full page]**：此類型的版面包含對象裝置的整個螢幕。

   其支援媒體（影像、影片）、文字及按鈕元件。

* **[!UICONTROL Large modal]**：此版面會顯示在大型警報樣式視窗中，而您的應用程式仍會顯示在背景中。

   其支援媒體（影像、影片）、文字及按鈕元件。

* **[!UICONTROL Small modal]**：此版面會顯示為小型警報類型視窗中，而您的應用程式仍會顯示在背景中。

   其支援媒體（影像、影片）、文字及按鈕元件。

* **[!UICONTROL Alert]**：此類型的版面會以原生作業系統 (OS) 警告訊息的形式顯示。

   其只能支援文字及按鈕元件。

* **[!UICONTROL Local notification]**：此類型的版面會以橫幅訊息的形式顯示。

   其只能支援音效、文字和目的地。如需本機通知的詳細資訊，請參閱[自訂本機通知訊息類型](#customizing-a-local-notification-message-type)。

每種類型的版面都可以在不同裝置（例如，手機、平板電腦、平台（如　Android 或 iOS）和方向（例如，內容編輯器右視窗的橫向或縱向））上進行預覽。

![](assets/inapp_customize_4.png)

### 媒體 {#media}

**[!UICONTROL Media]** 下拉式清單可讓您將媒體新增至應用程式內訊息，為使用者建立引人入勝的體驗。

1. 在影像與影片之間選取 **[!UICONTROL Media Type]**。
1. 對於 **[!UICONTROL Image]** 媒體類型，根據支援的格式，在 **[!UICONTROL Media URL]** 欄位中輸入您的 URL。

   如有需要，您也可以輸入 **[!UICONTROL Bundled image]** 的路徑，此路徑可在裝置離線時使用。

   ![](assets/inapp_customize_5.png)

1. 對於 **[!UICONTROL Video]** 媒體類型，請在　**[!UICONTROL Media URL]**　欄位中輸入您的 URL。

   之後，輸入您要在對象裝置上下載影片時使用的　**[!UICONTROL Video poster]**，或是直到使用者輕觸播放按鈕為止。

   ![](assets/inapp_customize_6.png)

### 文字 {#text}

如有需要，您也可以將訊息標題及內容新增至應用程式內訊息。為了更妥善地個人化您的應用程式內訊息，您可以將不同的個人化欄位、內容區塊及動態文字新增至內容。

1. 在 **[!UICONTROL Text]** 下拉式清單中的 **[!UICONTROL Message title]** 欄位中新增標題。

   ![](assets/inapp_customize_9.png)

1. 在 **[!UICONTROL Message content]** 欄位中新增您的內容。
1. 若要進一步個人化您的文字，請按一下 ![](assets/edit_darkgrey-24px.png) 圖示以新增個人化欄位。

   ![](assets/inapp_customize_8.png)

1. 視需要，輸入您的訊息內容並新增個人化欄位。

   如需個人化欄位的詳細資訊，請參閱[區段](../../designing/using/personalization.md#inserting-a-personalization-field)。

   ![](assets/inapp_customize_10.png)

1. 在預覽視窗中檢查您的訊息內容。

   ![](assets/inapp_customize_11.png)

### 按鈕 {#buttons}

您最多可以在應用程式內訊息中新增兩個按鈕。

1. 在 **[!UICONTROL Buttons]** 下拉式清單中，在 **[!UICONTROL Primary]** 類別中輸入第一個按鈕的文字。

   ![](assets/inapp_customize_12.png)

1. 選取將會指派給主要按鈕的兩個動作 **[!UICONTROL Dismiss]** 及 **[!UICONTROL Redirect]**。
1. 在 **[!UICONTROL Secondary]** 類別中，視需要輸入文字，而將第二個按鈕新增至您的應用程式內訊息。
1. 選取與第二個按鈕相關聯的動作。
1. 如果您選取 **[!UICONTROL Redirect]** 動作，請在 **[!UICONTROL Destination URL]** 欄位中輸入網頁 URL 或深層連結。

   ![](assets/inapp_customize_13.png)

1. 如果您選取的是 **[!UICONTROL Redirect]** 動作，請在 **[!UICONTROL Destination URL]** 欄位中輸入您的網頁 URL 或深層連結。
1. 在預覽視窗中或按一下「預覽」按鈕，檢查您的訊息內容。

   請參閱「[預覽應用程式內訊息](#previewing-the-in-app-message)」頁面。

   ![](assets/inapp_customize_11.png)

### 設定 {#settings}

1. 在 **[!UICONTROL Settings]** 類別中，在明暗之間選取背景顏色。
1. 選取是否顯示包含 **[!UICONTROL Show close button]** 選項的關閉按鈕，讓使用者可以解除應用程式內訊息。
1. 選取按鈕對齊方式與 **[!UICONTROL Button alignment]** 選項保持水平或垂直。
1. 選取您的應用程式內訊息是否可在數秒後自動解除。

   ![](assets/inapp_customize_7.png)

## 自訂本機通知訊息類型 {#customizing-a-local-notification-message-type}

本機通知只能由應用程式在特定時間內觸發，且會視事件而定。即使未存取網際網路，通知仍會提醒使用者應用程式中發生某些事情。
若要瞭解如何追蹤本機通知，請參閱本[頁面](../../administration/using/local-tracking.md)。

若要自訂本機通知：

1. 從 **[!UICONTROL Content]** 頁面選取　**[!UICONTROL Layout]**　類別中的 **[!UICONTROL Local notification]**

   ![](assets/inapp_customize_17.png)

1. 在 **[!UICONTROL Text]** 類別下方，輸入 **[!UICONTROL Message title]** 及 **[!UICONTROL Message content]**。

   ![](assets/inapp_customize_18.png)

1. 在類別 **[!UICONTROL Advanced option]** 的　**[!UICONTROL Wait to display]**　欄位中，選取觸發事件後，本機通知在螢幕上顯示的時間長短（以秒數表示）。
1. 在 **[!UICONTROL Sound]** 欄位中，輸入在接收本機通知時，行動裝置會播放之音效檔案的檔名（連同副檔名）。

   如果已在行動應用程式的套件中定義檔案，則傳送通知時會播放音效檔案。否則，會播放裝置的預設音效。

   ![](assets/inapp_customize_19.png)

1. 當使用者在 **[!UICONTROL Deeplink URL]** 欄位中與本機通知互動時，請指定要將使用者重新導向的目的地。
1. 若要以鍵值對的形式，在裝載中傳遞自訂資料，您可以將自訂欄位新增至本機通知。在 **[!UICONTROL Custom fields]** 類別中，按一下 **[!UICONTROL Create an element]** 按鈕。
1. 輸入 **[!UICONTROL Keys]**，然後再輸入與每個鍵相關聯的　**[!UICONTROL Values]**。

   請注意，自訂欄位的處理與用途完全視行動應用程式而定。

1. 在 **[!UICONTROL Apple options]** 類別中，如果自訂動作可在　Apple　行動應用程式中使用，請填入 **[!UICONTROL Category]** 欄位，為自訂動作新增類別　ID。

## 使用自訂 HTML 訊息自訂 {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>自訂 HTML 訊息不支援內容個人化。

**[!UICONTROL Custom message]** 模式可讓您直接匯入其中一個預先設定的 HTML 訊息。

若要執行此操作，您只需要從電腦拖放或選取檔案即可。

您的檔案必須具有特定版面，按一下「**下載範例檔案**」選項即可找到此版面。

![](assets/inapp_customize_16.png)

您也可以在 Adobe Campaign 中找到成功匯入的自訂 HTML 需求清單。

![](assets/inapp_customize_3.png)

匯入 HTML 之後，您就可以在預覽視窗的不同裝置上找到檔案的預覽。

## 預覽應用程式內訊息 {#previewing-the-in-app-message}

在傳送應用程式內訊息之前，您可以使用測試設定檔進行測試，以檢查目標對象收到您的傳遞內容後會看到什麼內容。

1. 按一下 **[!UICONTROL Preview]** 按鈕。

   ![](assets/inapp_sending_2.png)

1. 按一下 **[!UICONTROL Select a test profile]** 按鈕並選取其中一個測試設定檔，以開始預覽您的傳送。如需測試設定檔的詳細資訊，請參閱[本區段](../../audiences/using/managing-test-profiles.md)。
1. 在不同的裝置（例如，Android、iPhone 手機或平板電腦）上檢查您的訊息。您也可以檢查個人化欄位是否會擷取正確的資料。

   ![](assets/inapp_sending_3.png)

1. 您現在可以傳送訊息，並透過傳送報告來評估其影響。如需報告的詳細資訊，請參閱[本區段](../../reporting/using/in-app-report.md)。

