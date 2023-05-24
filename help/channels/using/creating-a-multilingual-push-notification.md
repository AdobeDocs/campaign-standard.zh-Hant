---
title: 建立多語言推送通知
description: 建立多語言推送通知，以用戶首選的語言和區域為目標。
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

## 關於多語言推送通知 {#about-multilingual-push-notification}

通過根據用戶首選的語言和區域發送消息來個性化推送通知內容。 您可以直接在內容編輯器中導入多語言推送通知內容變體，並在單次交付中發送多語言推送通知。

此功能利用收件人配置檔案中指定的首選語言或移動應用訂閱伺服器的系統語言首選項，具體取決於用於推送通知的傳遞模板。 如果沒有為特定用戶填充語言首選項，則系統將使用在建立多語言推送通知時定義的預設變數。 有關如何管理您的配置檔案和訂閱者的詳細資訊，請參閱此 [引導](../../audiences/using/get-started-profiles-and-audiences.md)。

![](assets/multivariant_push_1.png)

要將多語言內容變體用於推送通知傳遞，請執行以下步驟：

* [步驟1:上傳多語言內容變體](#step-1--upload-multilingual-content-variant)
* [步驟2:使用多語言內容變體預覽並完成推送通知](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [第3步：發送和分析多語言推送通知傳遞](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## 步驟1:上傳多語言內容變體 {#step-1--upload-multilingual-content-variant}

在個性化您的多語言推送通知之前，我們首先需要在多語言交付模板中上載內容變體並建立交付。

>[!NOTE]
>
>如果要為每個語言變型手動建立變型，也可以跳過此步驟。

1. 在 **[!UICONTROL Marketing activities]**，按一下 **[!UICONTROL Create]** 按鈕 **[!UICONTROL Push notification]**。
1. 選擇模板 **[!UICONTROL Send multilingual push to Campaign profiles]** 如果您要瞄準已訂閱您的移動應用程式或模板的Adobe Campaign配置檔案 **[!UICONTROL Send multilingual push to app subscriber]** 向已選擇從移動應用程式接收通知的所有用戶發送推送通知。

   ![](assets/multivariant_push_2.png)

1. 在中輸入您的推送通知屬性並選擇您的移動應用 **[!UICONTROL Associate a Mobile App to a delivery]** 的子菜單。

   請注意，下拉清單將同時顯示SDK V4和Adobe Experience PlatformSDK應用程式。

1. 在 **[!UICONTROL Audiences]** 窗口，拖放查詢以微調您的觀眾。

   添加的查詢取決於所選模板：選擇 **[!UICONTROL Send multilingual push to Campaign profiles]** 模板，您可以查詢移動應用程式的已知收件人。 而如果你選擇 **[!UICONTROL Send multilingual push to app subscriber]** 模板，您可以查詢已選擇加入的特定應用的所有訂閱者。
   >[!NOTE]
   >
   >如果您針對的是具有特定語言的受眾，則需要列出CSV檔案中的每種目標語言。

   ![](assets/push_notif_audience.png)

1. 在 **[!UICONTROL Manage Content Variants]** 窗口，拖放檔案或從電腦中選擇檔案。

   檔案必須是UTF8編碼的，並且必須具有特定佈局，可通過按一下 **[!UICONTROL Download the sample file]** 的雙曲餘切值。 還應使用正確的語言環境值語法。 有關檔案格式和支援的區域設定的詳細資訊，請參閱 [頁](../../channels/using/generating-csv-multilingual-push.md)。

   ![](assets/multivariant_push_4.png)

1. 上載檔案後，語言變體將自動填充到 **[!UICONTROL Variants]** 頁籤。 請注意，您可以 **[!UICONTROL Default variant]** 檔案中，如果沒有為目標用戶指定首選語言，則該檔案將是預設內容變型。

   ![](assets/multivariant_push_5.png)

1. 的 **[!UICONTROL Variant selection]** 頁籤將提供一個指令碼，以根據交付模板確定要考慮的語言首選項。 這是一個不需要您進行任何更改的現成指令碼。
1. 如果要添加導入檔案中不存在的更多變型，可按一下 **[!UICONTROL Add an element]** 按鈕並根據需要添加任意多個新語言變體。

   通過添加除從檔案上載的變數之外的變數，任何內容都不會連結到此語言。 您必須直接在交付儀表板中編輯內容。

   ![](assets/multivariant_push_6.png)

1. 按一下 **[!UICONTROL Create]** 完成配置時。 你總能回到 **[!UICONTROL Content variant]** 的子菜單。

   ![](assets/multivariant_push_8.png)

您現在可以開始個性化您的多語言推送通知。

## 步驟2:使用多語言內容變體預覽並完成推送通知 {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

上載包含內容變體的檔案後，您現在可以從推送通知傳遞中預覽不同的變體。

除了從檔案上載的變型外，還可以建立和編輯更多變型。

1. 在 **[!UICONTROL Content]** 下拉框中，您可以根據所選語言預覽推送通知內容。

   ![](assets/multivariant_push_7.png)

1. 如果未為特定語言指定內容變型，請按一下預覽下面的鈴表徵圖，開始向此語言變型添加內容。

   按一下 **[!UICONTROL Content]** 的子菜單。 在此窗口中所做的更改將僅影響一種語言。

1. 您還可以按一下內容變體，進一步自定義它，例如使用個性化欄位。

   有關如何自定義推送通知的詳細資訊，請參閱此 [節](../../channels/using/customizing-a-push-notification.md)。

   ![](assets/multivariant_push_9.png)

1. 按一下 **[!UICONTROL Content variant]** 的子菜單。

   請注意，通過添加新語言，您必須手動將內容添加到連結到添加語言的推送通知中。

   ![](assets/multivariant_push_10.png)

您的多語言推送通知交付現已準備好發送。

## 第3步：發送和分析多語言推送通知傳遞 {#step-3--send-and-analyze-multilingual-push-notification-delivery}

您的多語言內容變體推送通知現在已準備好發送給您的用戶。

1. 要開始準備發送，請按一下 **[!UICONTROL Prepare]** 按鈕
1. 當準備完成時沒有警告，可按一下 **[!UICONTROL Confirm]** 按鈕，開始發送多語種推送。

   ![](assets/multivariant_push_12.png)

1. 成功發送推送通知後，按一下 **[!UICONTROL Reports]** 表徵圖 **[!UICONTROL Dynamic reports]** 分析您交付的成功。

   ![](assets/multivariant_push_13.png)

1. 選取 **[!UICONTROL Push notification report]**。
1. 拖放 **[!UICONTROL Variant]** 維以開始篩選資料。

   ![](assets/multivariant_push_11.png)

您現在可以衡量您的多語言推送通知傳遞對收件人的影響。

**相關主題：**

* [推播通知報告](../../reporting/using/push-notification-report.md)
* [在工作流程中傳送推播通知](../../automating/using/push-notification-delivery.md)
