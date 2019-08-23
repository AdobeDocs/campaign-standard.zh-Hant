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
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 建立多語言推播通知{#creating-a-multilingual-push-notification}

## 關於多語言推播通知 {#about-multilingual-push-notification}

根據使用者偏好的語言和地區傳送訊息，以個人化推播通知內容。您可以直接在內容編輯器中讀入多語言推播通知內容變體，並在單次傳送中傳送多語言推播通知。

此功能可運用收件者描述檔中指定的偏好語言或行動應用程式用戶的系統語言偏好設定，視用於推播通知的傳送範本而定。如果未針對特定使用者填入語言偏好設定，系統會使用建立多語言推播通知時定義的預設變體。如需如何管理個人檔案和訂閱者的詳細資訊，請參閱本 [指南](../../audiences/using/about-profiles-and-audiences.md)。

![](assets/multivariant_push_1.png)

若要針對推播通知傳遞使用多語言內容變體，請依照下列步驟執行：

* [步驟1：上傳多語言內容變體](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [步驟2：使用多語言內容變數預覽並預覽推播通知](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [步驟3：傳送並分析多語言推播通知傳送](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 步驟1：上傳多語言內容變體 {#step-1--upload-multilingual-content-variant}

在個人化多語言推播通知之前，首先需要在多語言傳送範本中上傳內容變體，並建立傳送。

>[!NOTE]
>
>如果您想要手動為每個語言變體建立變體，也可以略過此步驟。

1. 然後 **[!UICONTROL Marketing activities]**&#x200B;按一下 **[!UICONTROL Create]** 按鈕，然後選取 **[!UICONTROL Push notification]**。
1. 如果您想要 **[!UICONTROL Send multilingual push to Campaign profiles]** 定位已訂閱行動應用程式或範本的 **[!UICONTROL Send multilingual push to app subscriber]** Adobe Campaign設定檔，請選取範本，以便將推播通知傳送給選擇接收行動應用程式通知的所有使用者。

   ![](assets/multivariant_push_2.png)

1. 輸入您的推播通知屬性，然後在 **[!UICONTROL Associate a Mobile App to a delivery]** 欄位中選取您的行動應用程式。

   請注意，下拉式清單將同時顯示SDK V和Adobe Experience Platform SDK應用程式。

1. **[!UICONTROL Audiences]** 在視窗中，拖放查詢以微調觀眾。

   新增的查詢取決於選擇的範本：如果您選擇 **[!UICONTROL Send multilingual push to Campaign profiles]** 範本，可以查詢行動應用程式的已知收件者。如果您選擇 **[!UICONTROL Send multilingual push to app subscriber]** 範本，則可以查詢已選擇加入的特定應用程式的所有訂閱者。

   ![](assets/push_notif_audience.png)

1. **[!UICONTROL Manage Content Variants]** 在視窗中，拖放您的檔案，或從電腦選取檔案。

   檔案必須編碼為UTF8，且必須擁有特定的版面配置，才能按一下 **[!UICONTROL Download the sample file]** 選項。您也應針對地區設定值使用適當語法。如需檔案格式和支援地區設定的詳細資訊，請參閱此 [TechNote](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html)。

   ![](assets/multivariant_push_4.png)

1. 上傳檔案後，語言變數會自動填入 **[!UICONTROL Variants]** 索引標籤中。請注意，如果目標 **[!UICONTROL Default variant]** 使用者未指定慣用的語言，您可以在檔案中提供預設內容變體。

   ![](assets/multivariant_push_5.png)

1. **[!UICONTROL Variant selection]** 此標籤將提供一個指令碼，以決定要根據傳送範本考量哪個語言偏好設定。這是不需要您進行變更的現成可用指令碼。
1. 如果您想要新增更多未顯示在匯入檔案中的變數，可以按一下 **[!UICONTROL Add an element]** 按鈕，並視需要新增新的語言變數。

   透過新增變數以外的變數，不會將內容連結至此語言。您必須直接在傳送控制面板中編輯內容。

   ![](assets/multivariant_push_6.png)

1. 在 **[!UICONTROL Create]** 完成設定時按一下。您隨時可以回到 **[!UICONTROL Content variant]** 視窗，並從傳送儀表板進行一些變更。

   ![](assets/multivariant_push_8.png)

您現在可以開始個人化您的多語言推播通知。

## 步驟2：使用多語言內容變數預覽並預覽推播通知 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

上傳包含內容變體的檔案後，您現在可以預覽推播通知傳送中的不同變體。

此外，也可以建立和編輯更多變數，以及從檔案上傳的變數。

1. 從傳送控制面板 **[!UICONTROL Content]** 的視窗中，下拉式清單可讓您根據選擇的語言預覽推播通知內容。

   ![](assets/multivariant_push_7.png)

1. 如果未指定特定語言的內容變體，請按一下預覽下方的「鈴聲」圖示，以開始新增內容至此語言變體。

   按下 **[!UICONTROL Content]** 視窗，推播通知就代表從下拉式清單中選取的語言中所選取的內容。在此視窗中所做的變更只會影響一種語言。

1. 您也可以按一下內容變體，以例如使用個人化欄位進一步自訂它。

   如需如何自訂推播通知的詳細資訊，請參閱此 [章節](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/multivariant_push_9.png)

1. 如果您想要新增或刪除語言變數，請按一下 **[!UICONTROL Content variant]** 視窗。

   請注意，新增語言時，您必須手動新增內容至連結至新增語言的推播通知。

   ![](assets/multivariant_push_10.png)

您的多語言推播通知傳送現已準備好傳送。

## 步驟3：傳送並分析多語言推播通知傳送 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多語言內容變體推播通知現在可供傳送給您的使用者。

1. 若要開始準備傳送，請按一下 **[!UICONTROL Prepare]** 按鈕。
1. 當準備完成時，您可以按一下 **[!UICONTROL Confirm]** 按鈕，開始傳送多語言推播。

   ![](assets/multivariant_push_12.png)

1. 成功傳送推播通知後，按一下 **[!UICONTROL Reports]** 圖示以 **[!UICONTROL Dynamic reports]** 分析傳送成功與否。

   ![](assets/multivariant_push_13.png)

1. 選取 **[!UICONTROL Push notification report]**。
1. 將 **[!UICONTROL Variant]** 維度拖放至面板，開始篩選資料。

   ![](assets/multivariant_push_11.png)

您現在可以測量多語言推播通知對收件者的影響。

**相關主題：**

* [推播通知報表](../../reporting/using/push-notification-report.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)
* [使用一個工作流程觸及多語言受眾](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
