---
title: 放棄觸發器使用個案
seo-title: 放棄觸發器使用個案
description: 放棄觸發器使用個案
seo-description: 瞭解如何使用Experience Cloud觸發器整合這些不同的使用案例。
page-status-flag: 從未啓動
uuid: 9e236165-afd5-4155-9151-c1941 dc0 af99
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與觸發器
discoiquuid: 1b9eeec5-70bb-4d72-a3 e9-12342abf08 f7
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Abandonment Triggers use cases{#abandonment-triggers-use-cases}

本節提供不同的使用案例，可使用Adobe Campaign和Experience Cloud觸發器之間的整合來實施。您將會發現兩個使用案例範例：

* [瀏覽放棄觸發器](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger)：傳送通訊給放棄網站瀏覽的客戶。
* [搜尋放棄觸發器](../../integrating/using/abandonment-triggers-use-cases.md#search-abandonment-trigger)：與在您網站搜尋的訪客重新互動，但未進行購買。

>[!NOTE]
>
>本節所述的使用案例依賴Experience Cloud訪客ID。您也可以使用Experience Cloud宣告ID實施它們。雜湊和加密的宣告ID也受到支援。您可以直接解密加密電子郵件地址/行動電話號碼，將電子郵件/簡訊傳送至促銷活動中不存在的設定檔。但在這種情況下，無法使用個人資料資料個人化。

## Pre-requisites {#pre-requisites}

若要實施這些使用案例，您必須存取下列解決方案/核心服務：

* Adobe Campaign
* Adobe Analytics Ultimate、Premium、Foundation、OD、Select、Prime、Mobile Apps、Select或Standard。
* Experience Cloud觸發器核心服務
* Experience Cloud DTM核心服務
* Experience Cloud訪客ID和Experience Cloud人員核心服務

您也需要有工作網站。

For more information, refer to [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Browse abandonment Trigger {#browse-abandonment-trigger}

在此使用案例中，我們將建立簡單觸發，當客戶在網站上放棄瀏覽時，就會觸發此觸發器。此範例假設您已有DTM收集並推送資料至Adobe Analytics，並將您的所有事件都建立在內。

### Creating an Experience Cloud Trigger {#creating-an-experience-cloud-trigger}

1. **[!UICONTROL Manage Triggers]** 從Experience Cloud啓動核心服務功能表中選取。

   ![](assets/trigger_uc_browse_1.png)

1. Choose a trigger type ( **[!UICONTROL Abandonment]** in our use case).

   ![](assets/trigger_uc_browse_2.png)

1. 對於此使用案例，我們需要簡單的放棄觸發器。其商業目的是識別瀏覽旅行預訂網站的訪客，查看「交易」頁面，但不預訂任何旅行。在識別此對象後，我們希望在短時間內觸及他們。在此範例中，我們選擇在10分鐘後傳送觸發器。

   ![](assets/trigger_uc_browse_3.png)

### Using the trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign}

現在我們已建立Experience Cloud觸發器，讓我們在Adobe Campaign中使用它。

在Adobe Campaign中，您必須建立連結至您在Experience Cloud中建立的觸發器。

1. To create the Trigger in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud triggers]**.

   ![](assets/remarketing_1.png)

1. Click **[!UICONTROL Create]**.
1. Select the Trigger you created earlier and click **[!UICONTROL Next]**.

   ![](assets/trigger_uc_browse_5.png)

1. Select the **[!UICONTROL Email]** channel and the **[!UICONTROL Real-time event]** targeting dimension and click **[!UICONTROL Create]**.

   ![](assets/trigger_uc_browse_6bis.png)

1. 在Adobe Campaign中發佈觸發器。此程序會自動建立交易訊息範本。

   ![](assets/trigger_uc_browse_6.png)

1. To dislay the message template, click the **[!UICONTROL More]** button, on the top right, then click **[!UICONTROL Trigger Transactional Template]**.
1. 個人化其內容和傳送者詳細資訊。

   ![](assets/trigger_uc_browse_8.png)

1. 發佈訊息範本。觸發器現在已上線並功能正常。

   ![](assets/trigger_uc_browse_0.png)

### Running the scenario {#running-the-scenario}

1. 此使用案例始於透過Adobe Campaign傳送給觀眾的初始電子郵件。

   ![](assets/trigger_uc_browse_9.png)

1. 收件者開啓電子郵件。

   ![](assets/trigger_uc_browse_10.png)

1. 他點按了將他帶到您網站的連結。在此範例中，橫幅會將收件者帶到旅行預訂網站的首頁。

   ![](assets/trigger_uc_browse_11.png)

1. 收件者前往「交易」頁面，但突然停止瀏覽。在10分鐘後，Adobe Campaign會觸發傳送交易訊息。

   ![](assets/trigger_uc_browse_12.png)

1. 您隨時可以查看Experience Cloud記錄檔，查看觸發觸發的次數。

   ![](assets/trigger_uc_browse_13.png)

1. 您也可以顯示Adobe Campaign觸發報表。

   ![](assets/trigger_uc_browse_14.png)

## Search abandonment Trigger {#search-abandonment-trigger}

在這個使用案例中，我們將會建立一個觸發器，以便與造訪旅行預訂網站、搜尋目的地、找不到成功結果的訪客重新互動，之後沒有任何書籍。The general process is the same as in the previous use case (see [Browse abandonment Trigger](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger)). 我們將討論如何個人化行銷電子郵件訊息。

### Creating an Experience Cloud Trigger {#creating-an-experience-cloud-trigger-1}

依照上一個使用案例中所述的步驟建立Experience Cloud觸發器。See [Creating an Experience Cloud Trigger](../../integrating/using/abandonment-triggers-use-cases.md#creating-an-experience-cloud-trigger). 主要差異是觸發器定義。

![](assets/trigger_uc_search_1.png)

**[!UICONTROL Include Meta Data]** 此區段可讓您將從Analytics收集到的任何資料傳遞至觸發裝載。在此範例中，我們建立自訂eVar(例如eVar3)以收集訪客進入的搜尋詞。此詞語將用於傳送給同一訪客的交易電子郵件訊息中。

### Using the trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign-1}

1. 依照上一個使用案例中所述的步驟，在Adobe Campaign中建立觸發器。See [Using the trigger in Adobe Campaign](../../integrating/using/abandonment-triggers-use-cases.md#using-the-trigger-in-adobe-campaign). 主要差異在於我們在Adobe Campaign中存取和使用的方式，是在觸發裝載中推送的中繼資料。
1. In the Search Abandonment trigger you created in Adobe Campaign, click on the **[!UICONTROL Event content and enrichment]** icon to view the payload pushed to Adobe Campaign.

   ![](assets/trigger_uc_search_2.png)

1. As you can see, the custom eVar is passed in the Trigger payload and mapped to the **Event Context** table (ctx). 我們現在可以存取它，個人化交易訊息。

   ![](assets/trigger_uc_search_3.png)

1. 在此範例中，我們選擇在主旨行以及電子郵件內文中包含目的地搜尋詞。

   ![](assets/trigger_uc_search_4.png)

1. When selecting a personalized field, look for your payload meta data in the **Transactional event** (rtEvent) table then in the **Event context** (ctx) sub table.

   ![](assets/trigger_uc_search_5.png)

### Running the scenario {#running-the-scenario-1}

1. 訪客前往旅行預訂網站並搜尋目的地。在此範例中，訪客正在尋找日本，但找不到任何結果。這是我們聯絡這位訪客並推薦替代旅行計劃的機會。

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >在此使用案例中，我們假設訪客/收件者已開啓並點按源自同一網站的電子郵件。這可讓我們使用並收集visitorID並將其對應給收件者。我們只需要完成這一次。

1. 稍候幾刻，同一位訪客/收件者收到二次行銷訊息。訊息包含最近搜尋過的目的地。

   ![](assets/trigger_uc_search_7.png)

