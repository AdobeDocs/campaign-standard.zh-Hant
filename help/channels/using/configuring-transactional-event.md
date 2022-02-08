---
title: 設定異動事件
description: 瞭解如何在Adobe Campaign配置事務性事件。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 1b91fb97-fe97-4564-936c-438be7ea7bc0
source-git-commit: a6768af0cea8891411f81e1782a873b5adb70a0e
workflow-type: tm+mt
source-wordcount: '1705'
ht-degree: 5%

---

# 設定異動事件 {#configuring-transactional-event}

要與Adobe Campaign一起發送事務性消息，您首先需要通過建立和配置事件來描述事件資料的結構。

>[!IMPORTANT]
>
>僅 [功能管理員](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->具有建立和編輯事件配置的適當權限。

配置因 [事務性消息類型](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) 要發送，並在將使用的頻道上。 有關此的詳細資訊，請參閱 [特定配置](#transactional-event-specific-configurations)。

配置完成後，必須發佈事件。 請參閱 [發佈事務性事件](../../channels/using/publishing-transactional-event.md)。

## 建立事件 {#creating-an-event}

要開始，請建立與您的需要相對應的事件。

1. 按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 按一下 **[!UICONTROL Create]** 按鈕。
1. 輸入 **[!UICONTROL Label]** 和 **[!UICONTROL ID]** 為活動準備。 的 **[!UICONTROL ID]** 欄位是必需的，應以前置詞&quot;EVT&quot;開頭。 如果不使用此前置詞，則按一下後會自動添加 **[!UICONTROL Create]**。

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >ID不能超過64個字元，包括EVT前置詞。

1. 選擇將用於發送事務性消息的通道 **[!UICONTROL Email]**。 **[!UICONTROL Mobile (SMS)]** 或 **[!UICONTROL Push notification]**。 每個事件只能使用一個通道，以後不能更改。

1. 選擇與所需事件配置對應的目標維，然後按一下 **[!UICONTROL Create]**。

   基於事件的事務性消息以事件本身中包含的資料為目標，而基於配置檔案的事務性消息以Adobe Campaign資料庫中包含的資料為目標。 有關此內容的詳細資訊，請參閱 [特定配置](#transactional-event-specific-configurations)。

>[!NOTE]
>
>事務事件的數量可能會對您的平台產生影響。 為確保最佳效能，請確保刪除未使用的事件。 請參閱 [刪除事件](../../channels/using/publishing-transactional-event.md#deleting-an-event)。

## 定義事件屬性 {#defining-the-event-attributes}

在 **[!UICONTROL Fields]** 定義將整合到事件內容中的屬性，然後可用於個性化事務性消息。

添加和修改欄位的步驟與 [自定義資源](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)。

![](assets/message-center_2.png)

>[!NOTE]
>
>如果要建立多語言事務性消息，請使用 **[!UICONTROL AC_language]** ID。 這僅適用於事件事務性消息。 發佈事件後，編輯多語言事務性消息內容的步驟與多語言標準電子郵件的步驟相同。 請參閱 [建立多語言電子郵件](../../channels/using/creating-a-multilingual-email.md)。

## 定義資料集合 {#defining-data-collections}

您可以向事件內容添加一組元素，每個元素本身包括多個屬性。

此集合可用於事務性電子郵件中以添加 [產品清單](../../designing/using/using-product-listings.md) 到消息內容，例如產品清單，包括價格、參考編號、數量等。 清單的每個產品。

1. 在 **[!UICONTROL Collections]** 的 **[!UICONTROL Create element]** 按鈕

   ![](assets/message-center_collection_create.png)

1. 為集合添加標籤和ID。
1. 為清單的每個產品添加要在事務性消息中顯示的所有欄位。

   在此示例中，我們添加了以下欄位：

   ![](assets/message-center_collection_fields.png)

1. 的 **[!UICONTROL Enrichment]** 頁籤中，您可以對集合的每個項進行豐富。 這樣，您就可以使用Adobe Campaign資料庫或您建立的其他資源的資訊個性化相應產品清單的元素。

>[!NOTE]
>
>豐富集合元素的步驟與 [豐富活動內容](#enriching-the-transactional-message-content) 的子菜單。 請注意，豐富事件不允許您豐富集合：你需要在收藏中增加一個 **[!UICONTROL Collections]** 的子菜單。

一旦事件和消息發佈，您就可以在事務性消息中使用此集合。

以下是此示例的API預覽：

![](assets/message-center_collection_api-preview.png)

**相關主題：**

* [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [在交易式訊息中使用產品清單](../../designing/using/using-product-listings.md)
* [發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## 豐富活動內容 {#enriching-the-transactional-message-content}

您可以使用來自Adobe Campaign資料庫的資訊來豐富事務性消息內容，以便個性化您的消息。 例如，從每個收件人的姓氏或CRM ID中，您可以恢復資料，如其地址或出生日期，或在「配置檔案」(Profile)表格中添加的任何其它自定義欄位，以便個性化發送給他們的資訊。

利用來自擴展的資訊來豐富事務性消息內容是可能的 **[!UICONTROL Profile and services Ext API]**。 有關詳細資訊，請參見 [擴展API:發佈擴展](../../developing/using/step-2--publish-the-extension.md)

此資訊也可以儲存在新資源中。 在這種情況下，資源必須連結到 **[!UICONTROL Profile]** 或 **[!UICONTROL Service]** 直接或通過其他表。 例如，在下面的配置中，可以使用來自 **[!UICONTROL Product]** 資源（如產品類別或ID） **[!UICONTROL Product]** 資源已連結到 **[!UICONTROL Profile]** 資源。

![](assets/message-center_usecaseschema.png)

有關建立和發佈資源的詳細資訊，請參見 [此部分](../../developing/using/key-steps-to-add-a-resource.md)。

1. 在 **[!UICONTROL Enrichment]** 的 **[!UICONTROL Create element]** 按鈕

   ![](assets/message-center_addenrichment.png)

1. 選擇要將郵件連結到的資源。 在此情況下，選擇 **[!UICONTROL Profile]** 資源。

   ![](assets/message-center_new-enrichment.png)

1. 使用 **[!UICONTROL Create element]** 按鈕，將選定資源中的欄位連結到先前添加到事件中的某個欄位(請參閱 [定義事件屬性](#defining-the-event-attributes))。

   ![](assets/message-center_enrichment-join.png)

   >[!NOTE]
   >
   >如果定義了一個條件，該條件可以選擇多個收件人（例如，一個欄位可以為多個配置檔案具有相同的值），則目標不會多於一個配置檔案。

1. 在此示例中，我們協調 **[!UICONTROL Last name]** 和 **[!UICONTROL First name]** 欄位中的相應欄位 **[!UICONTROL Profile]** 資源。

   ![](assets/message-center_enrichment-join-fields.png)

   您還可以使用 **[!UICONTROL Service]** 資源。 有關服務的詳細資訊，請參見 [此部分](../../audiences/using/creating-a-service.md)。

1. 如果要建立或編輯 [基於配置檔案的事件](#profile-based-transactional-messages)，也請參見Wiki頁。 **[!UICONTROL Targeting enrichment]** 部分，選擇在傳遞執行期間用作消息目標的富集。

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >建立富集並根據 **[!UICONTROL Profile]** 基於配置檔案的事件必須使用資源。

一旦事件和消息發佈，此連結將允許您豐富事務性消息的內容。

**相關主題：**

* [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [個人化交易式訊息](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [發佈交易式訊息](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## 搜索事務事件 {#searching-transactional-events}

要訪問和搜索已建立的事務性事件，請執行以下步驟。

1. 按一下 **Adobe** 徽標，在左上角，然後選擇 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**。
1. 按一下 **[!UICONTROL Show search]** 按鈕。

   ![](assets/message-center_search-events.png)

1. 可以在 **[!UICONTROL Publication status]**。 這允許您僅顯示已發佈的事件（例如）。
1. 您還可以使用 **[!UICONTROL Last event received]**。 例如，如果輸入10，則只顯示10天前或更久之前接收的最後一個事件的事件配置。 這使您能夠顯示在給定期間內哪些事件處於非活動狀態。

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >預設值為0。 然後顯示所有事件。

## 特定配置 {#transactional-event-specific-configurations}

事務性事件配置可能因 [事務性消息類型](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) 您要發送（事件或配置檔案），並且要使用的頻道上。

以下各節詳細介紹了根據所需事務性消息應設定哪些特定配置。 有關配置事件的一般步驟的詳細資訊，請參閱 [建立事件](#creating-an-event)。

### 基於事件的事務性消息 {#event-based-transactional-messages}

您可以傳送目標定位事件的事件交易式訊息。此類交易式訊息不包含設定檔資訊：傳遞目標是由事件本身包含的資料所定義。

要發送基於事件的事務性消息，您首先需要建立並配置針對 **事件本身中包含的資料**。

1. 建立事件配置時，選擇 **[!UICONTROL Real-time event]** 目標維度（請參見） [建立事件](#creating-an-event))。
1. 將欄位添加到事件，以便能夠個性化事務性消息(請參閱 [定義事件屬性](#defining-the-event-attributes))。
1. 事件型交易式訊息應僅使用傳送事件中的資料來定義收件者和訊息內容個人化。

   但是，如果要使用Adobe Campaign資料庫中的其他資訊，則可以豐富事務性消息內容(請參見 [豐富事務性消息內容](#enriching-the-transactional-message-content))。

1. 預覽和發佈事件(請參閱 [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event))。

   在預覽事件時，REST API包含根據所選頻道指定電子郵件地址、行動電話或推送通知特定屬性的屬性。

   一旦發佈了該事件，就會自動建立連結到新事件的事務性消息。 要使事件觸發發送事務性消息，您必須 [修改](../../channels/using/editing-transactional-message.md) 和 [發佈](../../channels/using/publishing-transactional-message.md) 剛剛建立的消息。

1. 將活動整合到您的網站(請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

### 基於配置檔案的事務性消息 {#profile-based-transactional-messages}

您可以根據客戶配置檔案發送事務性消息，這允許您應用市場營銷類型規則，包括取消訂閱連結，將消息添加到全局交付報告並在客戶行程中利用它。

要發送基於配置檔案的事務性消息，您首先需要建立和配置事件目標 **Adobe Campaign資料庫的資料**。

1. 建立事件配置時，選擇 **[!UICONTROL Profile event]** 目標維度（請參見） [建立事件](#creating-an-event))。
1. 將欄位添加到事件，以便能夠個性化事務性消息(請參閱 [定義事件屬性](#defining-the-event-attributes))。 必須至少添加一個欄位才能建立富集。 您不需要建立其他欄位，如 **名字** 和 **姓氏** 因為您將能夠使用Adobe Campaign資料庫中的個性化欄位。
1. 建立富集，以將事件連結到 **[!UICONTROL Profile]** 資源(請參閱 [豐富活動內容](#enriching-the-transactional-message-content))並選擇此富集作為 **[!UICONTROL Targeting enrichment]**。

   >[!IMPORTANT]
   >
   >此步驟對於基於配置檔案的事件是必需的。

1. 預覽和發佈事件(請參閱 [預覽和發佈事件](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event))。

   預覽事件時，REST API不包含指定電子郵件地址、行動電話或推送通知特定屬性的屬性，因為將從 **[!UICONTROL Profile]** 資源。

   一旦發佈了該事件，就會自動建立連結到新事件的事務性消息。 要使事件觸發發送事務性消息，您必須 [修改](../../channels/using/editing-transactional-message.md) 和 [發佈](../../channels/using/publishing-transactional-message.md) 剛剛建立的消息……

1. 將活動整合到您的網站(請參閱 [整合事件觸發](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger))。

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### 異動推送通知 {#transactional-push-notifications}

您可以發送兩種類型的事務推式通知：
* 向已選擇從移動應用程式接收通知的所有用戶發送匿名事務推送通知。 請參閱 [配置基於事件的事務推送通知](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications)。
* 向已訂閱您的移動應用程式的Adobe Campaign配置檔案發送事務推送通知。 請參閱 [配置基於配置檔案的事務推送通知](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications)。

>[!IMPORTANT]
>
>要能夠發送事務推式通知，您需要相應地配置Adobe Campaign。 請參閱 [配置移動應用程式](../../administration/using/configuring-a-mobile-application.md)。

### 後續追蹤訊息 {#follow-up-messages}

您可以向收到特定事務性消息的客戶發送後續消息。

有關配置允許發送後續消息的事件的步驟的詳細說明，請參見 [此部分](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message)。
