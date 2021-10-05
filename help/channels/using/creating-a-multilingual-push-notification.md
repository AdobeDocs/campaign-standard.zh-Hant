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

此功能會根據用於推播通知的傳送範本，運用收件者設定檔中指定的偏好語言，或行動應用程式訂閱者的系統語言偏好設定。 如果未為特定使用者填入語言偏好設定，系統將使用建立多語言推播通知時所定義的預設變體。 有關如何管理配置檔案和訂閱者的詳細資訊，請參閱本[指南](../../audiences/using/get-started-profiles-and-audiences.md)。

![](assets/multivariant_push_1.png)

若要在推播通知傳送中使用多語言內容變體，請遵循下列步驟：

* [步驟1:上傳多語言內容變體](#step-1--upload-multilingual-content-variant)
* [步驟2:使用多語言內容變體預覽並完成推播通知](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [步驟3:傳送及分析多語言推播通知傳送](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 步驟1:上傳多語言內容變體 {#step-1--upload-multilingual-content-variant}

在個人化您的多語言推播通知之前，我們必須先以多語言傳送範本上傳內容變體，並建立傳送。

>[!NOTE]
>
>如果您想要手動建立每個語言變體的變體，也可以略過此步驟。

1. 在&#x200B;**[!UICONTROL Marketing activities]**&#x200B;中，按一下&#x200B;**[!UICONTROL Create]**&#x200B;按鈕，然後選擇&#x200B;**[!UICONTROL Push notification]**。
1. 如果您想要鎖定已訂閱您行動應用程式的Adobe Campaign設定檔或範本&#x200B;**[!UICONTROL Send multilingual push to app subscriber]**，以傳送推播通知給選擇從行動應用程式接收通知的所有使用者，請選取範本&#x200B;**[!UICONTROL Send multilingual push to Campaign profiles]**。

   ![](assets/multivariant_push_2.png)

1. 輸入推播通知屬性，並在&#x200B;**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;欄位中選取您的行動應用程式。

   請注意，下拉式清單會同時顯示SDK V4和Adobe Experience Platform SDK應用程式。

1. 在&#x200B;**[!UICONTROL Audiences]**&#x200B;視窗中，拖放查詢以微調您的對象。

   新增的查詢取決於選取的範本：如果您選擇&#x200B;**[!UICONTROL Send multilingual push to Campaign profiles]**&#x200B;範本，則可查詢行動應用程式的已知收件者。 而若您選擇&#x200B;**[!UICONTROL Send multilingual push to app subscriber]**&#x200B;範本，則可查詢已選擇加入之特定應用程式的所有訂閱者。
   >[!NOTE]
   >
   >如果您鎖定具有特定語言的對象，您需要在CSV檔案中列出每個目標語言。

   ![](assets/push_notif_audience.png)

1. 在&#x200B;**[!UICONTROL Manage Content Variants]**&#x200B;視窗中，拖放檔案或從電腦選取檔案。

   檔案必須經過UTF8編碼，且必須具有特定版面，按一下&#x200B;**[!UICONTROL Download the sample file]**&#x200B;選項即可找到。 您也應對地區設定值使用正確的語法。 有關檔案格式和支援的地區設定的詳細資訊，請參閱此[page](../../channels/using/generating-csv-multilingual-push.md)。

   ![](assets/multivariant_push_4.png)

1. 上傳檔案後，語言變體會自動填入&#x200B;**[!UICONTROL Variants]**&#x200B;標籤中。 請注意，如果未為目標使用者指定偏好語言，則您可以在檔案中提供&#x200B;**[!UICONTROL Default variant]**，作為預設內容變體。

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]**&#x200B;標籤將提供指令碼，以根據傳送範本決定要考慮的語言偏好設定。 這是現成可用的指令碼，不需要您進行任何變更。
1. 如果要添加更多不存在於導入檔案中的變體，可以按一下&#x200B;**[!UICONTROL Add an element]**&#x200B;按鈕並根據需要添加任意數量的新語言變體來執行此操作。

   借由新增從檔案上傳的變體以外的變體，任何內容都不會連結至此語言。 您必須直接在傳送控制面板中編輯內容。

   ![](assets/multivariant_push_6.png)

1. 完成配置後，按一下&#x200B;**[!UICONTROL Create]**。 您一律可以返回&#x200B;**[!UICONTROL Content variant]**&#x200B;視窗，並從傳送控制面板進行一些變更。

   ![](assets/multivariant_push_8.png)

您現在可以開始個人化多語言推播通知。

## 步驟2:使用多語言內容變體預覽並完成推播通知 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

上傳包含內容變體的檔案後，您現在可以預覽推播通知傳送的不同變體。

除了從檔案上傳的變體外，您也可以建立和編輯更多變體。

1. 在傳遞控制面板的&#x200B;**[!UICONTROL Content]**&#x200B;視窗中，下拉式清單可讓您根據所選語言預覽推播通知內容。

   ![](assets/multivariant_push_7.png)

1. 如果未為特定語言指定內容變體，請按一下預覽下的鈴聲表徵圖，開始將內容添加到此語言變體。

   按一下&#x200B;**[!UICONTROL Content]**&#x200B;視窗，推播通知即代表下拉式清單中所選語言的內容。 在此視窗中所做的變更只會影響一種語言。

1. 您也可以按一下內容變體來進一步自訂，例如使用個人化欄位。

   如需如何自訂推播通知的詳細資訊，請參閱此[區段](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/multivariant_push_9.png)

1. 如果要添加或刪除語言變體，請按一下&#x200B;**[!UICONTROL Content variant]**&#x200B;窗口。

   請注意，新增語言後，您必須手動將內容新增至連結至新增語言的推播通知。

   ![](assets/multivariant_push_10.png)

您的多語言推播通知傳送現在已準備好傳送。

## 步驟3:傳送及分析多語言推播通知傳送 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多語言內容變體推播通知現在已準備好傳送給您的使用者。

1. 若要開始準備傳送，請按一下&#x200B;**[!UICONTROL Prepare]**&#x200B;按鈕。
1. 準備完成後，若沒有警告，您可以按一下&#x200B;**[!UICONTROL Confirm]**&#x200B;按鈕，開始傳送多語言推播。

   ![](assets/multivariant_push_12.png)

1. 成功傳送推播通知後，按一下&#x200B;**[!UICONTROL Reports]**&#x200B;圖示，然後按一下&#x200B;**[!UICONTROL Dynamic reports]**&#x200B;以分析傳送是否成功。

   ![](assets/multivariant_push_13.png)

1. 選取 **[!UICONTROL Push notification report]**。
1. 將&#x200B;**[!UICONTROL Variant]**&#x200B;維度拖放至面板，以開始篩選資料。

   ![](assets/multivariant_push_11.png)

您現在可以測量多語言推播通知傳送對收件者的影響。

**相關主題：**

* [推播通知報告](../../reporting/using/push-notification-report.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)
