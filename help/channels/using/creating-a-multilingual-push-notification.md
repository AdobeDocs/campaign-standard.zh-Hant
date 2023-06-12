---
title: 建立多語言推送通知
description: 建立多語言推播通知，以使用者偏好的語言和地區為目標。
audience: channels
content-type: reference
topic-tags: push-notifications
feature: Push
role: User
level: Intermediate
exl-id: 1b81f6e9-cb31-4664-af78-22e70043fbc8
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 2%

---

# 建立多語言推送通知{#creating-a-multilingual-push-notification}

## 關於多語言推播通知 {#about-multilingual-push-notification}

根據使用者偏好的語言和地區傳送訊息，個人化您的推播通知內容。 您可以在內容編輯器中直接匯入多語言推播通知內容變體，並在單一傳送中傳送多語言推播通知。

此功能會根據用於推播通知的傳遞範本，利用收件者設定檔中指定的慣用語言或行動應用程式訂閱者的系統語言偏好設定。 如果沒有為特定使用者填入語言偏好設定，系統將使用建立多語言推播通知時定義的預設變體。 有關如何管理設定檔和訂閱者的詳細資訊，請參閱此 [指南](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

若要針對推播通知傳送使用多語言內容變體，請遵循下列步驟：

* [步驟1：上傳多語言內容變體](#step-1--upload-multilingual-content-variant)
* [步驟2：使用多語言內容變體預覽和完成推播通知](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [步驟3：傳送和分析多語言推播通知傳遞](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 步驟1：上傳多語言內容變體 {#step-1--upload-multilingual-content-variant}

在個人化您的多語言推播通知之前，我們首先需要上傳多語言傳送範本中的內容變體並建立傳送。

>[!NOTE]
>
>如果您想要手動為每個語言變體建立變體，也可以跳過此步驟。

1. 在 **[!UICONTROL Marketing activities]**，按一下 **[!UICONTROL Create]** 按鈕，然後選取 **[!UICONTROL Push notification]**.
1. 選取範本 **[!UICONTROL Send multilingual push to Campaign profiles]** 如果您想要鎖定已訂閱您的行動應用程式或範本的Adobe Campaign設定檔 **[!UICONTROL Send multilingual push to app subscriber]** 傳送推播通知給選擇接收來自您的行動應用程式通知的所有使用者。

   ![](assets/multivariant_push_2.png)

1. 輸入您的推播通知屬性，然後在以下位置選取您的行動應用程式： **[!UICONTROL Associate a Mobile App to a delivery]** 欄位。

   請注意，下拉式清單會同時顯示SDK V4和Adobe Experience Platform SDK應用程式。

1. 在 **[!UICONTROL Audiences]** 視窗，拖放查詢以微調您的對象。

   新增的查詢取決於所選的範本：如果您選擇 **[!UICONTROL Send multilingual push to Campaign profiles]** 範本您可以查詢行動應用程式的已知收件者。 而如果您選擇 **[!UICONTROL Send multilingual push to app subscriber]** 範本後，您可以查詢特定應用程式中選擇加入的所有訂閱者。
   >[!NOTE]
   >
   >如果您以特定語言鎖定對象，則需要在CSV檔案中列出每個鎖定目標的語言。

   ![](assets/push_notif_audience.png)

1. 在 **[!UICONTROL Manage Content Variants]** 視窗，拖放您的檔案，或從您的電腦中選取檔案。

   檔案必須經過UTF8編碼，且必須具有特定版面，您可在按一下 **[!UICONTROL Download the sample file]** 選項。 您也應該使用適當的語法對地區設定值。 有關檔案格式和支援的語言環境的詳細資訊，請參閱此 [頁面](../../channels/using/generating-csv-multilingual-push.md).

   ![](assets/multivariant_push_4.png)

1. 上傳檔案後，語言變體會自動填入 **[!UICONTROL Variants]** 標籤。 請注意，您可以提供 **[!UICONTROL Default variant]** 如果未為目標使用者指定偏好語言，則該檔案將是您的預設內容變體。

   ![](assets/multivariant_push_5.png)

1. 此 **[!UICONTROL Variant selection]** 索引標籤會提供指令碼，以根據傳遞範本決定要考慮的語言偏好設定。 這是現成可用的指令碼，不需要您進行任何變更。
1. 如果您想要新增更多未出現在匯入檔案中的變體，可以按一下 **[!UICONTROL Add an element]** 按鈕並視需要新增任意數量的新語言變體。

   透過新增從檔案上傳的變體以外的變體，任何內容都不會連結至此語言。 您必須直接在傳送控制面板中編輯內容。

   ![](assets/multivariant_push_6.png)

1. 按一下 **[!UICONTROL Create]** 完成設定時。 您可以隨時返回 **[!UICONTROL Content variant]** 視窗中，並從您的傳遞控制面板進行一些變更。

   ![](assets/multivariant_push_8.png)

您現在可以開始個人化多語言推播通知。

## 步驟2：使用多語言內容變體預覽和完成推播通知 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

上傳包含內容變體的檔案後，您現在可以從推播通知傳送中預覽不同的變體。

除了從檔案上傳的變體外，也可以建立並編輯更多變體。

1. 在 **[!UICONTROL Content]** 從傳送控制面板的視窗，下拉式清單可讓您根據所選的語言預覽推播通知內容。

   ![](assets/multivariant_push_7.png)

1. 如果未針對特定語言指定內容變體，請按一下預覽下方的鈴鐺圖示，以開始將內容新增至此語言變體。

   按一下 **[!UICONTROL Content]** 視窗中，推播通知代表下拉式選單中所選語言的內容。 在此視窗中所做的變更只會影響一種語言。

1. 您也可以按一下內容變體以進一步自訂它，例如使用個人化欄位。

   有關如何自訂推播通知的詳細資訊，請參閱此 [區段](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. 按一下 **[!UICONTROL Content variant]** 視窗。

   請注意，新增語言後，您必須手動將內容新增至連結至新增語言的推播通知。

   ![](assets/multivariant_push_10.png)

您的多語言推播通知傳送現已準備就緒，可供傳送。

## 步驟3：傳送和分析多語言推播通知傳遞 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多語言內容變體推送通知現已準備就緒，可傳送給使用者。

1. 若要開始準備傳送，請按一下 **[!UICONTROL Prepare]** 按鈕。
1. 完成準備作業且無警告時，您可以按一下 **[!UICONTROL Confirm]** 按鈕以開始傳送您的多語言推播。

   ![](assets/multivariant_push_12.png)

1. 成功傳送推播通知後，請按一下 **[!UICONTROL Reports]** 圖示然後 **[!UICONTROL Dynamic reports]** 以分析傳送是否成功。

   ![](assets/multivariant_push_13.png)

1. 選取 **[!UICONTROL Push notification report]**。
1. 拖放 **[!UICONTROL Variant]** 維度來開始篩選資料。

   ![](assets/multivariant_push_11.png)

您現在可以測量多語言推播通知傳送對收件者的影響。

**相關主題：**

* [推播通知報告](../../reporting/using/push-notification-report.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)
