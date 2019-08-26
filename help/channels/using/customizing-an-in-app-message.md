---
title: 自訂應用程式內訊息
seo-title: 自訂應用程式內訊息
description: 自訂應用程式內訊息
seo-description: 瞭解如何使用各種選項來自訂應用程式內訊息。
page-status-flag: 從未啓動
uuid: 1d9c08ed-4de5-440d-bb51-4a437 eEC67 d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 應用程式內訊息
discoiquuid: c9c3e033-e319-447b-8d87-ff7 dd4941876
context-tags: delivery，inapContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 43183a3adc35da3dac807a888f1b694fbb9a623c

---


# 自訂應用程式內訊息{#customizing-an-in-app-message}

若要微調應用程式內訊息，Adobe Campaign可讓您在設計應用程式內時，存取一組進階選項。

應用程式內內容編輯器可讓您選擇兩種應用程式內訊息模式：

* [訊息範本](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template)：此範本可讓您使用影像或影片和動作按鈕完全自訂您的應用程式內。
* [自訂訊息](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message)：此範本可讓您匯入自訂HTML。

![](assets/inapp_customize_1.png)

**相關主題：**

* [傳送您的應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [應用程式內報告](../../reporting/using/in-app-report.md)

## 使用訊息範本自訂 {#customizing-with-a-message-template}

### 版面配置 {#layout}

**[!UICONTROL Layout]** 下拉式清單提供四種不同的選項，可根據您的訊息需求選擇：

* **[!UICONTROL Full page]**：這種版面類型涵蓋您的觀眾裝置的整個螢幕。

   它支援媒體(影像、視訊)、文字和按鈕元件。

* **[!UICONTROL Large modal]**：此版面配置會出現在大型警報樣式視窗中，您的應用程式仍會顯示在背景中。

   它支援媒體(影像、視訊)、文字和按鈕元件。

* **[!UICONTROL Small modal]**：此版面會顯示為小型警報類型視窗，您的應用程式仍會顯示在背景中。

   它支援媒體(影像、視訊)、文字和按鈕元件。

* **[!UICONTROL Alert]**：此類型的版面會顯示為原生OS警告訊息。

   它只能支援文字和按鈕元件。

* **[!UICONTROL Local notification]**：此類型的版面會顯示為橫幅訊息。

   它只能支援音效、文字和目的地。有關本機通知的更多資訊，請參閱 [自訂本機通知訊息類型](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)。

每種版面類型都可以在不同裝置(例如手機、平板電腦、平台等)上預覽，例如Android或iOS和iOS和方向，或在內容編輯器的右視窗中進行portra。

![](assets/inapp_customize_4.png)

### 媒體 {#media}

**[!UICONTROL Media]** 下拉式清單可讓您新增媒體至應用程式內訊息，為使用者建立引人入勝的體驗。

1. 選擇您 **[!UICONTROL Media Type]** 的影像和視訊。
1. **[!UICONTROL Image]** 對於媒體類型，請根據支援的格式輸入 **[!UICONTROL Media URL]** 欄位中的URL。

   如有需要，您也可以輸入可 **[!UICONTROL Bundled image]** 在裝置離線時使用的路徑。

   ![](assets/inapp_customize_5.png)

1. 如需 **[!UICONTROL Video]** 媒體類型，請在 **[!UICONTROL Media URL]** 欄位中輸入您的URL。

   然後，在觀眾裝置上或直到使用者點選播放按鈕時，輸入 **[!UICONTROL Video poster]** 您要使用的影片。

   ![](assets/inapp_customize_6.png)

### 文字 {#text}

如有需要，您也可以新增訊息標題和內容至應用程式內訊息。若要更好地個人化應用程式內訊息，您可以在內容中新增不同的個人化欄位、內容區塊和動態文字。

1. 在 **[!UICONTROL Text]** 下拉式清單中，新增欄位中的 **[!UICONTROL Message title]** 標題。

   ![](assets/inapp_customize_9.png)

1. 在 **[!UICONTROL Message content]** 欄位中加入您的內容。
1. 若要進一步個人化您的文字，請按一下 ![](assets/edit_darkgrey-24px.png) 圖示以新增個人化欄位。

   ![](assets/inapp_customize_8.png)

1. 輸入訊息內容，並視需要新增個人化欄位。

   有關個人化欄位的更多資訊，請參閱本 [節](../../designing/using/inserting-a-personalization-field.md)。

   ![](assets/inapp_customize_10.png)

1. 在預覽視窗中檢查您的訊息內容。

   ![](assets/inapp_customize_11.png)

### 按鈕 {#buttons}

您最多可以新增兩個按鈕至應用程式內訊息。

1. 在 **[!UICONTROL Buttons]** 下拉式清單中，輸入 **[!UICONTROL Primary]** 類別中第一個按鈕的文字。

   ![](assets/inapp_customize_12.png)

1. 選擇兩個動作中的哪一個 **[!UICONTROL Dismiss]** ，並 **[!UICONTROL Redirect]** 將其指派給您的主要按鈕。
1. **[!UICONTROL Secondary]** 在類別中，輸入文字時，視需要新增第二個按鈕至應用程式中。
1. 選取與第二個按鈕相關聯的動作。
1. 如果您選擇 **[!UICONTROL Redirect]** 動作，請在 **[!UICONTROL Destination URL]** 欄位中輸入您的網頁URL或深層連結。

   ![](assets/inapp_customize_13.png)

1. 在 **[!UICONTROL Destination URL]** 欄位中輸入您的網頁URL或刪除連結，如果您選擇 **[!UICONTROL Redirect]** 了動作，
1. 在預覽視窗中查看您的訊息內容，或按一下「預覽」按鈕。

   請參閱 [「預覽應用程式內訊息](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) 」頁面。

   ![](assets/inapp_customize_11.png)

### Settings {#settings}

1. **[!UICONTROL Settings]** 在類別中，選取光線和深色之間的背景顏色。
1. 選擇顯示或不關閉按鈕， **[!UICONTROL Show close button]** 提供使用者關閉應用程式內訊息的選項。
1. 選取按鈕對齊方式是否為水平或垂直 **[!UICONTROL Button alignment]** 方向。
1. 選擇您的應用程式內訊息是否可在數秒後自動關閉。

   ![](assets/inapp_customize_7.png)

## 自訂本機通知訊息類型 {#customizing-a-local-notification-message-type}

本機通知只能由應用程式在特定時間，視事件而觸發。他們會提醒使用者，即使沒有網際網路，他們的應用程式仍會發生某事。

若要自訂本機通知：

1. 從 **[!UICONTROL Content]** 您的頁面中選擇 **[!UICONTROL Local notification]****[!UICONTROL Layout]** 類別中的

   ![](assets/inapp_customize_17.png)

1. 在 **[!UICONTROL Text]** 類別下方，輸入 **[!UICONTROL Message title]** 您的和 **[!UICONTROL Message content]**。

   ![](assets/inapp_customize_18.png)

1. **[!UICONTROL Advanced option]** 在類別下方 **[!UICONTROL Wait to display]** ，選擇在觸發事件後，在螢幕上顯示本機通知的時間長度長度。
1. **[!UICONTROL Sound]** 在欄位中，輸入在收到本機通知時，行動裝置播放的音效檔檔案名稱。

   如果檔案是在行動應用程式套件中定義，則音效檔會播放。否則，會播放裝置的預設音效。

   ![](assets/inapp_customize_19.png)

1. 指定目標，以便在使用者與 **[!UICONTROL Deeplink URL]** 欄位中的本機通知互動時重新導向。
1. 若要以關鍵值配對形式傳遞裝載中的自訂資料，您可以在本機通知中新增自訂欄位。在 **[!UICONTROL Custom fields]** 類別中按一下 **[!UICONTROL Create an element]** 按鈕。
1. 輸入與 **[!UICONTROL Keys]** 每個索引鍵 **[!UICONTROL Values]** 關聯的項目。

   請注意，自訂欄位的處理與目的完全取決於行動應用程式。

1. **[!UICONTROL Apple options]** 在類別中，填寫 **[!UICONTROL Category]** 欄位以新增自訂動作的類別ID(如果您在Apple行動應用程式中可用)。

## 自訂使用自訂HTML訊息 {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>自訂HTML訊息不支援內容個人化。

**[!UICONTROL Custom message]** 模式可讓您直接匯入其中一個預先設定的HTML訊息。

若要這麼做，您只需拖放或從電腦選取檔案即可。

您的檔案必須具有特定的版面配置，只要按一下 **下載範例檔案** 選項即可。

![](assets/inapp_customize_16.png)

您也可以找到在Adobe Campaign中成功匯入的自訂HTML需求清單。

![](assets/inapp_customize_3.png)

匯入HTML後，您可以在預覽視窗中的不同裝置上找到檔案預覽。

## 預覽應用程式內訊息 {#previewing-the-in-app-message}

在傳送應用程式內訊息之前，您可以使用測試設定檔來測試您的測試設定檔，以檢查目標對象何時收到您的傳送內容。

1. 按一下 **[!UICONTROL Preview]** 按鈕。

   ![](assets/inapp_sending_2.png)

1. 按一下 **[!UICONTROL Select a test profile]** 按鈕，然後選取其中一個測試設定檔，開始預覽傳送。如需測試設定檔的詳細資訊，請參閱此 [章節](../../sending/using/managing-test-profiles-and-sending-proofs.md)。
1. 在不同裝置(例如Android、iPhone手機或平板電腦)上檢查您的訊息。您也可以檢查您的個人化欄位是否正在擷取正確資料。

   ![](assets/inapp_sending_3.png)

1. 您現在可以傳送訊息，並透過傳送報告測量其影響力。For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

