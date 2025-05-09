---
title: 準備和傳送應用程式內訊息
description: 建立應用程式內訊息，以特定內容鎖定您的應用程式訂閱者。
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back;deliveryCreation,wizard
feature: In App
role: User
exl-id: ef83d991-302b-491e-9cdb-07f5da7a5971
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 80%

---

# 準備和傳送應用程式內訊息{#preparing-and-sending-an-in-app-message}

Adobe Campaign 中提供了三種類型的應用程式內訊息：

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**：此訊息類型可讓您定位已訂閱您行動應用程式的 Adobe Campaign 設定檔（CRM 設定檔）。此訊息類型可與 Adobe Campaign 中所有可用的描述檔屬性個人化，但需要 Mobile SDK 與 Campaign 應用程式內訊息服務之間的安全握手，以確保只有授權使用者才會使用包含個人和敏感資訊的訊息。

  若要在使用者的裝置上下載此訊息類型，Mobile SDK 必須傳送連結欄位，用以將行動設定檔連結至 Adobe Campaign 中的 CRM 設定檔。如需支援應用程式內部所需 SDK API 的詳細資訊，請參閱本 [頁面](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/)。

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**：此訊息類型可讓您傳送訊息給行動應用程式的所有使用者（目前或未來），即使他們在 Adobe Campaign 中沒有現有的設定檔亦然。因此，當自訂訊息時，無法個人化，因為 Adobe Campaign 中可能甚至不存在使用者設定檔。
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**：此訊息類型可讓您鎖定在 Adobe Campaign 中具有行動設定檔的行動應用程式的所有已知或匿名使用者。此訊息類型僅能使用非個人和非敏感屬性進行個人化，而且不需要 Mobile SDK 與 Adobe Campaign 的應用程式內訊息服務之間的安全交握。

  有關如何處理個人和敏感資料的詳細資訊，請參閱使用[個人和敏感資料處理行動設定檔欄位](../../channels/using/about-in-app-messaging.md#handling-mobile-profile-fields-with-personal-and-sensitive-data)。

![](assets/diagram_inapp.png)

## 準備應用程式內訊息 {#preparing-your-in-app-message}

>[!CAUTION]
>
>應用程式內個人化需仰賴連結欄位，連結欄位通常是 CRM ID 和/或行動應用程式登入 ID。當您與 Adobe Campaign 搭配使用時，應自行負責保護此連結欄位。如果您無法確保連結欄位的安全，您的個人化訊息可能會很脆弱。如果您未遵守安全的連結欄位構成、管理和保護實務，Adobe 將不負責因未經授權存取或使用任何描述檔資料而造成的損害。

使用 Adobe Campaign 建立獨立應用程式內訊息的步驟如下：

1. 從 Adobe Campaign 首頁，按一下 **[!UICONTROL In-App messaging]** 資訊卡。

   您也可以按一下 **[!UICONTROL Create]** 按鈕，從 **Marketing activities** 索引標籤建立應用程式內。

   請注意，您也可以從行銷活動或 Adobe Campaign 首頁或工作流程建立應用程式內訊息。

1. 選取&#x200B;**應用程式內訊息**。

   ![](assets/inapp_creating.png)

1. 根據客群定位需求選取適當的範本。

   ![](assets/inapp_creating_2.png)

   依預設，您可以選取下列三個立即可用的範本之一：

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. 輸入應用程式內訊息屬性，並在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;欄位中選取您的行動應用程式。

   如果您在下拉式清單中未看到任何應用程式，請確定您的行動應用程式處於&#x200B;**已設定**&#x200B;狀態。 處於&#x200B;**準備就緒**&#x200B;狀態的應用程式將不會出現在清單中。 如需行動應用程式設定的詳細資訊，請參閱本[頁面](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

   ![](assets/inapp_creating_3.png)

1. 選取您要針對應用程式內訊息鎖定的客群。您的客群會根據與此傳送相關聯的行動應用程式預先篩選。

   請注意，此步驟不是行動應用程 **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** 式的必要步驟，因為其目標是行動應用程式的所有使用者。

   ![](assets/inapp_creating_8.png)

1. 在 **[!UICONTROL Triggers]** 索引標籤中，拖放將觸發訊息的事件。選取觸發器後，您就會選取使用者執行的動作，以顯示應用程式內訊息。

   有四類事件可供使用：

   * **[!UICONTROL Mobile Application events]**：在行動應用程式中實作的自訂事件。

     有關詳細資訊，請參見本[頁面](../../administration/using/configuring-a-mobile-application.md)。

   * **[!UICONTROL Life Cycle events]**：Adobe Mobile SDK 支援的現成可用生命週期事件。

     有關生命週期事件的詳細資訊，請參閱本[頁面](https://experienceleague.adobe.com/docs/mobile-services/android/metrics.html?lang=zh-Hant)。

   * **[!UICONTROL Analytics Events]**：根據您的行動應用程式中所創作的內容，支援下列三個類別： Adobe Analytics、內容資料或檢視狀態。

     請注意，這些事件僅在您擁有Adobe Analytics授權時才可用。

   * **[!UICONTROL Places]**：以下三個類別運用即時位置資料來提供情境相關的行動體驗：放置內容資料、放置自訂中繼資料或放置事件類型。

     如需 Adobe Places 的詳細資訊，請參閱 [Places 檔案](https://experienceleague.adobe.com/docs/places/using/home.html?lang=zh-Hant)。

   ![](assets/inapp_creating_4.png)

1. 如果您使用&#x200B;**[!UICONTROL Analytics Events]**，Adobe Analytics和檢視狀態事件將會根據資料收集UI中Analytics擴充功能中設定的報表套裝自動填入，而內容資料事件則必須手動新增。

   請注意，這些事件僅在您擁有Adobe Analytics授權時才可用。

   ![](assets/inapp_creating_7.png)

1. 如果您使用 **[!UICONTROL Places]** 觸發器，Places 內容資料、Places 自訂中繼資料或 Places 事件類型將會根據所有在 Adobe Places 中建立的 Libraries 及其 Points of Interest 自動填入。

   請注意，此觸發器僅會套用至資料收集UI中Places擴充功能中選取之Libraries的Points of Interest。 有關 Places 擴充功能以及如何安裝的詳細資訊，請參閱本[文件](https://developer.adobe.com/client-sdks/solution/places)。

1. 在 **[!UICONTROL Frequency & duration]** 索引標籤中，選取觸發的頻率、開始和結束日期、一週中的某天，以及應用程式內訊息生效的當天時間。

   ![](assets/inapp_creating_5.png)

1. 編輯訊息的內容並定義進階選項。請參閱[自訂應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)。

   ![](assets/inapp_creating_6.png)

1. 按一下 **[!UICONTROL Create]**。

您的應用程式內訊息現在已準備好傳送給您的目標客群。

**相關主題：**

* [自訂應用程式內訊息](../../channels/using/customizing-an-in-app-message.md)
* [應用程式內報告](../../reporting/using/in-app-report.md)
* [在工作流程中傳送應用程式內訊息](../../automating/using/in-app-delivery.md)

## 預覽應用程式內訊息 {#previewing-the-in-app-message}

在傳送應用程式內訊息之前，您可以使用測試輪廓進行測試，以檢查目標客群收到您的傳遞內容後會看到什麼內容。

1. 按一下 **[!UICONTROL Preview]** 按鈕。

   ![](assets/inapp_sending_2.png)

1. 按一下 **[!UICONTROL Select a test profile]** 按鈕並選取其中一個測試設定檔，以開始預覽您的傳送。如需測試設定檔的詳細資訊，請參閱[本區段](../../audiences/using/managing-test-profiles.md)。
1. 在不同的裝置（例如，Android、iPhone 手機或平板電腦）上檢查您的訊息。您也可以檢查個人化欄位是否會擷取正確的資料。

   ![](assets/inapp_sending_3.png)

1. 您現在可以傳送訊息，並透過傳送報告評估其影響。

## 傳送您的應用程式內訊息 {#sending-your-in-app-message}

在您完成傳送準備並執行核准步驟後，就可以傳送訊息。

1. 按一下 **[!UICONTROL Prepare]** 可計算目標並產生訊息。

   ![](assets/inapp_sending_4.png)

1. 完成準備工作後，**「部署」**&#x200B;視窗就會顯示下列 KPI：**「目標」**&#x200B;和&#x200B;**「交付」**。

   您也可以按一下 ![](assets/lp_link_properties.png) 按鈕來核取「部署」視窗，以檢視傳送中的可能排除或錯誤。

   ![](assets/inapp_sending_5.png)

1. 按一下 **[!UICONTROL Confirm]** 以開始傳送您的應用程式內訊息。

   ![](assets/inapp_sending_6.png)

1. 透過訊息儀表板和記錄檔檢查您的傳送狀態。如需詳細資訊，請參閱本[區段](../../sending/using/monitoring-a-delivery.md)。

   **[!UICONTROL Delivered]** 及 **[!UICONTROL Sent]** KPI 計數則以成功從行銷活動傳送至訊息傳送服務的項目為基礎。請注意，這些 KPI 並不表示從訊息傳送服務成功接收或下載訊息的行動裝置計數。

   ![](assets/inapp_sending_7.png)

1. 使用傳遞報告測量應用程式內訊息的影響。如需報告的詳細資訊，請參閱[本區段](../../reporting/using/in-app-report.md)。

1. 傳送應用程式內訊息後，您可以選擇停用您的傳遞。 例如，如果您想要停止特定傳送，或想要使用相同觸發程式執行新傳送，則此功能會很有用。

   按一下&#x200B;**[!UICONTROL Deactivate]**，然後按&#x200B;**[!UICONTROL Ok]**，開始停用要求。

   ![](assets/inapp_sending_8.png)

1. 傳送請求後，您的傳送將會停用，且不會傳送其他訊息。

   請注意，您仍可存取此傳遞的報告。

   ![](assets/inapp_sending_9.png)

**相關主題：**

* [應用程式內報告](../../reporting/using/in-app-report.md)
* [在工作流程中傳送應用程式內訊息](../../automating/using/in-app-delivery.md)
