---
title: 建立多語言推播通知
seo-title: 建立多語言推播通知
description: 建立多語言推播通知
seo-description: 建立多語言推播通知，以您偏好的語言和地區來定位使用者。
page-status-flag: 從未啓動
uuid: d4aff741-e969-47c6-bae8-787c6 c673191
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 推播通知
discoiquuid: f9bb2235-d388-4025-9ACE-734beb0 c661
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Creating a multilingual push notification{#creating-a-multilingual-push-notification}

## About multilingual push notification {#about-multilingual-push-notification}

根據使用者偏好的語言和地區傳送訊息，以個人化推播通知內容。您可以直接在內容編輯器中讀入多語言推播通知內容變體，並在單次傳送中傳送多語言推播通知。

此功能可運用收件者描述檔中指定的偏好語言或行動應用程式用戶的系統語言偏好設定，視用於推播通知的傳送範本而定。如果未針對特定使用者填入語言偏好設定，系統會使用建立多語言推播通知時定義的預設變體。For more information on how to manage your profiles and subscribers, refer to this [guide](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

若要針對推播通知傳遞使用多語言內容變體，請依照下列步驟執行：

* [步驟1：上傳多語言內容變體](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [步驟2：使用多語言內容變數預覽並預覽推播通知](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [步驟3：傳送並分析多語言推播通知傳送](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Step 1: Upload multilingual content variant {#step-1--upload-multilingual-content-variant}

在個人化多語言推播通知之前，首先需要在多語言傳送範本中上傳內容變體，並建立傳送。

>[!NOTE]
>
>如果您想要手動為每個語言變體建立變體，也可以略過此步驟。

1. In the **[!UICONTROL Marketing activities]**, click the **[!UICONTROL Create]** button then select **[!UICONTROL Push notification]**.
1. Select the template **[!UICONTROL Send multilingual push to Campaign profiles]** if you want to target the Adobe Campaign profiles who have subscribed to your mobile application or the template **[!UICONTROL Send multilingual push to app subscriber]** to send a push notification to all users who have opted in to receive notifications from your mobile application.

   ![](assets/multivariant_push_2.png)

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   請注意，下拉式清單將同時顯示SDK V和Adobe Experience Platform SDK應用程式。

1. **[!UICONTROL Audiences]** 在視窗中，拖放查詢以微調觀眾。

   The queries added depend on the chosen template: if you chose the **[!UICONTROL Send multilingual push to Campaign profiles]** template you can query known recipients of your mobile application. Whereas if you chose the **[!UICONTROL Send multilingual push to app subscriber]** template, you can query all subscribers of a particular app who have opted in.

   ![](assets/push_notif_audience.png)

1. **[!UICONTROL Manage Content Variants]** 在視窗中，拖放您的檔案，或從電腦選取檔案。

   The file has to be UTF8 encoded and must have a specific layout which can be found by clicking the **[!UICONTROL Download the sample file]** option. 您也應針對地區設定值使用適當語法。For more information regarding the file format and the supported locales, refer to this [technote](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. After uploading your file, the language variants are automatically populated in the **[!UICONTROL Variants]** tab. Note that you can provide a **[!UICONTROL Default variant]** in the file which will be your default content variant if no preferred language is specified for the targeted user.

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]** 此標籤將提供一個指令碼，以決定要根據傳送範本考量哪個語言偏好設定。這是不需要您進行變更的現成可用指令碼。
1. If you want to add more variants not present in the imported file, you can do so by clicking the **[!UICONTROL Add an element]** button and add as many new language variants as needed.

   透過新增變數以外的變數，不會將內容連結至此語言。您必須直接在傳送控制面板中編輯內容。

   ![](assets/multivariant_push_6.png)

1. Click **[!UICONTROL Create]** when the configuration is done. You can always come back to the **[!UICONTROL Content variant]** window and make some changes from your delivery dashboard.

   ![](assets/multivariant_push_8.png)

您現在可以開始個人化您的多語言推播通知。

## Step 2: Preview and finalize a push notification using multilingual content variants {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

上傳包含內容變體的檔案後，您現在可以預覽推播通知傳送中的不同變體。

此外，也可以建立和編輯更多變數，以及從檔案上傳的變數。

1. In the **[!UICONTROL Content]** window from the delivery dashboard, the drop-down allows you to preview your push notification content depending on the chosen language.

   ![](assets/multivariant_push_7.png)

1. 如果未指定特定語言的內容變體，請按一下預覽下方的「鈴聲」圖示，以開始新增內容至此語言變體。

   By clicking the **[!UICONTROL Content]** window, the push notification represents the content from the language selected in the drop down. 在此視窗中所做的變更只會影響一種語言。

1. 您也可以按一下內容變體，以例如使用個人化欄位進一步自訂它。

   For more information on how to customize your push notification, refer to this [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Click the **[!UICONTROL Content variant]** window if you want to add or delete language variants.

   請注意，新增語言時，您必須手動新增內容至連結至新增語言的推播通知。

   ![](assets/multivariant_push_10.png)

您的多語言推播通知傳送現已準備好傳送。

## Step 3: Send and analyze multilingual push notification delivery {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多語言內容變體推播通知現在可供傳送給您的使用者。

1. To start preparing the send, click the **[!UICONTROL Prepare]** button.
1. When the preparation is finished with no warnings, you can click the **[!UICONTROL Confirm]** button to start sending your multilingual push.

   ![](assets/multivariant_push_12.png)

1. After successfully sending your push notification, click the **[!UICONTROL Reports]** icon then **[!UICONTROL Dynamic reports]** to analyze the success of your delivery.

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. Drag and drop the **[!UICONTROL Variant]** dimension to your panel to start filtering your data.

   ![](assets/multivariant_push_11.png)

您現在可以測量多語言推播通知對收件者的影響。

**相關主題：**

* [推播通知報表](../../reporting/using/push-notification-report.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)

