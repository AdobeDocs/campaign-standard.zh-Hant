---
title: 建立自訂設定檔維度
description: 瞭解如何根據自訂設定檔資料建立自訂設定檔維度。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 5%

---

# 建立自訂設定檔維度{#creating-a-custom-profile-dimension}

您也可以根據在設定檔自訂資源擴充期間建立的自訂設定檔資料，來建立和管理報表。

在此範例中，我們要建立自訂設定檔欄位 **熟客方案** 分為三個等級：金級、銀級和銅級。 然後，此自訂設定檔會擴充，以便作為動態報告中的自訂設定檔維度使用。

* [步驟1：建立新的設定檔欄位](#step-1--create-a-new-profile-field)
* [步驟2：使用設定檔欄位擴充傳送記錄檔](#step-2--extend-the-sending-logs-with-the-profile-field)
* [步驟3：建立傳遞目標，並定位已註冊熟客計畫的收件者](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [步驟4：建立動態報告，使用自訂設定檔維度篩選收件者](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 步驟1：建立新的設定檔欄位 {#step-1--create-a-new-profile-field}

我們首先需要建立新的設定檔欄位 **熟客方案** 會將忠誠度等級指派給我們的收件者：金級、銀級或銅級。

>[!NOTE]
>
>自訂資源只能由管理員管理。

若要這麼做：

1. 從進階功能表中，選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** 然後 **[!UICONTROL Profile (profile)]** 自訂資源。

   ![](assets/custom_profile_1.png)

1. 從 **[!UICONTROL Data structure]** 標籤，在 **[!UICONTROL Fields]** 類別，按一下 **[!UICONTROL Add field]** 按鈕。

   ![](assets/custom_profile_2.png)

1. 輸入 **[!UICONTROL Label]**， **[!UICONTROL ID]** 並選取自訂資源 **[!UICONTROL Type]**. 在此，我們選取 **[!UICONTROL Text]** 因為獲獎者可以選擇金、銀和銅。

   ![](assets/custom_profile_3.png)

1. 按一下 ![](assets/custom_profile_22.png) 圖示來定義您的欄位。

   ![](assets/custom_profile_12.png)

1. 在此，我們需要透過檢查以下專案來指定授權值： **[!UICONTROL Specify a list of authorized valued]** 並按一下以建立每個值 **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. 輸入 **[!UICONTROL Label]** 和 **[!UICONTROL Value]** 然後按一下 **[!UICONTROL Add]**. 在此範例中，我們需要建立金、銀和銅的價值。 完成時，按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/custom_profile_14.png)

1. 選取 **[!UICONTROL Screen definition]** 索引標籤。在 **[!UICONTROL Detail screen configuration]** 下拉式清單，勾選 **[!UICONTROL Add personalized fields]** 區段，以在我們的設定檔中建立新的區段。

   ![](assets/custom_profile_4.png)

1. 按一下 **[!UICONTROL Add an element]** 按鈕來建立您的新區段。 選取 **[!UICONTROL Type]**： **[!UICONTROL Input field]**， **[!UICONTROL Value]** 或 **[!UICONTROL List]**，然後在此新區段中新增的欄位。

   ![](assets/custom_profile_5.png)

1. 您也可以在欄位中的區段新增標題 **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   按一下 **[!UICONTROL Save]** 完成設定時。

   ![](assets/custom_profile_6.png)

1. 從進階功能表中，選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** 以開始發佈自訂資源。
1. 按一下 **[!UICONTROL Prepare publication]** 準備完成後，按一下 **[!UICONTROL Publish]** 按鈕。

   ![](assets/custom_profile_7.png)

您的新設定檔欄位現在已可供收件者使用及選取。

![](assets/custom_profile_8.png)

## 步驟2：使用設定檔欄位擴充傳送記錄檔 {#step-2--extend-the-sending-logs-with-the-profile-field}

現在您的設定檔欄位已建立，我們需要使用設定檔欄位擴充傳送記錄檔，以在動態報告中建立相關的自訂設定檔維度。

在使用我們的設定檔欄位擴充記錄前，請確定已接受PII視窗以存取 **[!UICONTROL Sending logs extension]** 標籤。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>管理員只能使用設定檔欄位擴充記錄檔。

1. 從進階功能表中，選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** 然後 **[!UICONTROL Profile (profile)]** 自訂資源。
1. 開啟 **[!UICONTROL Sending logs extension]** 下拉式清單。
1. 按一下 **[!UICONTROL Create element]** 按鈕。

   ![](assets/custom_profile_9.png)

1. 選取您先前建立的欄位並按一下 **[!UICONTROL Confirm]**.
1. 檢查 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 以建立您的自訂設定檔維度。

   ![](assets/custom_profile_10.png)

   只有在接受PII視窗時，才能使用此選項。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 按一下 **[!UICONTROL Add]** 然後儲存您的自訂資源。
1. 由於自訂資源已修改，因此我們需要發佈它以實施新的變更。

   從進階功能表中，選取 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** 以開始發佈自訂資源。

1. 按一下 **[!UICONTROL Prepare publication]** 準備完成後，按一下 **[!UICONTROL Publish]** 按鈕。

   ![](assets/custom_profile_7.png)

您的自訂設定檔現在可在報表中作為自訂設定檔維度使用。

現在您的欄位已建立，而且傳送記錄檔已使用此設定檔欄位擴充，您就可以開始在傳送中鎖定收件者。

## 步驟3：建立傳遞目標，並定位已註冊熟客計畫的收件者 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

您的設定檔欄位發佈後，您就可以開始傳送。 在此範例中，我們想要鎖定註冊熟客計畫的每位收件者。

1. 在 **[!UICONTROL Marketing activities]** 索引標籤中，按一下 **[!UICONTROL Create]**，然後選取 **[!UICONTROL Email]**。
1. 選擇 **[!UICONTROL Email type]** 然後輸入電子郵件的屬性。
1. 若要定位已註冊熟客方案的收件者，請拖放 **[!UICONTROL Profiles (attributes)]** 活動。
1. 從中選擇您先前建立的欄位 **[!UICONTROL Field]** 下拉式清單。

   ![](assets/custom_profile_16.png)

1. 選取您的 **[!UICONTROL Filter conditions]**. 在此，我們想要鎖定屬於三個忠誠度計畫其中一個層級的收件者。

   ![](assets/custom_profile_17.png)

1. 按一下 **[!UICONTROL Confirm]** 然後，完成篩選時，按一下 **[!UICONTROL Next]**.
1. 定義並個人化郵件內容、寄件者名稱和主旨。 如需電子郵件建立的詳細資訊，請參閱本 [頁面](../../designing/using/designing-content-in-adobe-campaign.md).

   然後，按一下 **[!UICONTROL Create]**.

1. 準備就緒後，您可以預覽並傳送訊息。 有關如何準備和傳送訊息的詳細資訊，請參閱本 [頁面](../../sending/using/preparing-the-send.md).

電子郵件正確傳送給您選取的收件者後，您就可以開始篩選資料，並追蹤傳送報表的成功情況。

## 步驟4：建立動態報告，使用自訂設定檔維度篩選收件者 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

傳送傳遞後，您可從以下位置使用自訂設定檔維度劃分報表： **[!UICONTROL Profile]** 表格。

1. 從 **[!UICONTROL Reports]** 索引標籤中，選取現成可用的報表或按一下 **[!UICONTROL Create]** 按鈕以從頭開始一個。

   ![](assets/custom_profile_18.png)

1. 在 **[!UICONTROL Dimensions]** 類別，按一下 **[!UICONTROL Profile]** 然後拖放您的自訂 **熟客方案** 設定檔維度至您的自由表格。

   ![](assets/custom_profile_19.png)

1. 拖放 **[!UICONTROL Processed/Sent]** 和 **[!UICONTROL Open]** 開始篩選資料的量度。

   ![](assets/custom_profile_20.png)

1. 視需要在工作區中拖放視覺效果。

   ![](assets/custom_profile_21.png)

**相關主題：**

* [使用自訂設定檔資料建立深入分析的報告](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
