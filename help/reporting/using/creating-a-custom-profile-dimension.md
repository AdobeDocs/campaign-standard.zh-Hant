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

在此範例中，我們要建立自訂設定檔欄位&#x200B;**忠誠度計畫**，該計畫將分為三個層級：金級、銀級和銅級。 然後，此自訂設定檔會擴充，以便作為動態報告中的自訂設定檔維度使用。

* [步驟1：建立新的設定檔欄位](#step-1--create-a-new-profile-field)
* [步驟2：使用設定檔欄位擴充傳送記錄檔](#step-2--extend-the-sending-logs-with-the-profile-field)
* [步驟3：建立傳遞目標，並定位已註冊熟客計畫的收件者](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [步驟4：建立動態報告，使用自訂設定檔維度篩選收件者](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 步驟1：建立新的設定檔欄位 {#step-1--create-a-new-profile-field}

我們首先需要建立新的設定檔欄位&#x200B;**熟客方案**，將熟客等級指派給我們的收件者：金級、銀級或銅級。

>[!NOTE]
>
>自訂資源只能由管理員管理。

若要這麼做：

1. 從進階功能表，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然後選取&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;自訂資源。

   ![](assets/custom_profile_1.png)

1. 從&#x200B;**[!UICONTROL Data structure]**&#x200B;索引標籤的&#x200B;**[!UICONTROL Fields]**&#x200B;類別中，按一下&#x200B;**[!UICONTROL Add field]**&#x200B;按鈕。

   ![](assets/custom_profile_2.png)

1. 輸入&#x200B;**[!UICONTROL Label]**、**[!UICONTROL ID]**&#x200B;並選取自訂資源&#x200B;**[!UICONTROL Type]**。 在此處，我們選取&#x200B;**[!UICONTROL Text]**，因為收件者可選擇使用金級、銀級和銅級。

   ![](assets/custom_profile_3.png)

1. 按一下![](assets/custom_profile_22.png)圖示以定義您的欄位。

   ![](assets/custom_profile_12.png)

1. 在此，我們需要透過檢查&#x200B;**[!UICONTROL Specify a list of authorized valued]**&#x200B;來指定授權值，並按一下&#x200B;**[!UICONTROL Create element]**&#x200B;來建立每個值。

   ![](assets/custom_profile_13.png)

1. 輸入&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Value]**，然後按一下&#x200B;**[!UICONTROL Add]**。 在此範例中，我們需要建立金、銀和銅的價值。 完成時，按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/custom_profile_14.png)

1. 選取 **[!UICONTROL Screen definition]** 索引標籤。在&#x200B;**[!UICONTROL Detail screen configuration]**&#x200B;下拉式清單中，核取&#x200B;**[!UICONTROL Add personalized fields]**&#x200B;區段以在我們的設定檔中建立新區段。

   ![](assets/custom_profile_4.png)

1. 按一下&#x200B;**[!UICONTROL Add an element]**&#x200B;按鈕以建立新區段。 選取&#x200B;**[!UICONTROL Type]**： **[!UICONTROL Input field]**、**[!UICONTROL Value]**&#x200B;或&#x200B;**[!UICONTROL List]**，然後選取要新增到此新區段中的欄位。

   ![](assets/custom_profile_5.png)

1. 您也可以在欄位&#x200B;**[!UICONTROL Customize the title of the section where the fields will be displayed]**&#x200B;的章節中新增標題。

   組態完成時，按一下&#x200B;**[!UICONTROL Save]**。

   ![](assets/custom_profile_6.png)

1. 從進階功能表中選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]**&#x200B;以開始發佈您的自訂資源。
1. 按一下&#x200B;**[!UICONTROL Prepare publication]**，然後在準備完成時，按一下&#x200B;**[!UICONTROL Publish]**&#x200B;按鈕。

   ![](assets/custom_profile_7.png)

您的新設定檔欄位現在已可供收件者使用及選取。

![](assets/custom_profile_8.png)

## 步驟2：使用設定檔欄位擴充傳送記錄檔 {#step-2--extend-the-sending-logs-with-the-profile-field}

現在您的設定檔欄位已建立，我們需要使用設定檔欄位擴充傳送記錄檔，以在動態報告中建立相關的自訂設定檔維度。

在使用我們的設定檔欄位擴充記錄檔之前，請確定已接受PII視窗以存取&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;標籤。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>管理員只能使用設定檔欄位擴充記錄檔。

1. 從進階功能表，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**，然後選取&#x200B;**[!UICONTROL Profile (profile)]**&#x200B;自訂資源。
1. 開啟&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;下拉式清單。
1. 按一下 **[!UICONTROL Create element]** 按鈕。

   ![](assets/custom_profile_9.png)

1. 選取您先前建立的欄位並按一下&#x200B;**[!UICONTROL Confirm]**。
1. 檢查&#x200B;**[!UICONTROL Add this field in Dynamic reporting as a new dimension]**&#x200B;以建立您的自訂設定檔維度。

   ![](assets/custom_profile_10.png)

   只有在接受PII視窗時，才能使用此選項。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 按一下&#x200B;**[!UICONTROL Add]**，然後儲存您的自訂資源。
1. 由於自訂資源已修改，因此我們需要發佈它以實施新的變更。

   從進階功能表中選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]**&#x200B;以開始發佈您的自訂資源。

1. 按一下&#x200B;**[!UICONTROL Prepare publication]**，然後在準備完成時，按一下&#x200B;**[!UICONTROL Publish]**&#x200B;按鈕。

   ![](assets/custom_profile_7.png)

您的自訂設定檔現在可在報表中作為自訂設定檔維度使用。

現在您的欄位已建立，而且傳送記錄檔已使用此設定檔欄位擴充，您就可以開始在傳送中鎖定收件者。

## 步驟3：建立傳遞目標，並定位已註冊熟客計畫的收件者 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

您的設定檔欄位發佈後，您就可以開始傳送。 在此範例中，我們想要鎖定註冊熟客計畫的每位收件者。

1. 在 **[!UICONTROL Marketing activities]** 索引標籤中，按一下 **[!UICONTROL Create]**，然後選取 **[!UICONTROL Email]**。
1. 選擇&#x200B;**[!UICONTROL Email type]**，然後輸入電子郵件的內容。
1. 若要定位已註冊熟客方案的收件者，請拖放&#x200B;**[!UICONTROL Profiles (attributes)]**&#x200B;活動。
1. 從&#x200B;**[!UICONTROL Field]**&#x200B;下拉式清單中選取您先前建立的欄位。

   ![](assets/custom_profile_16.png)

1. 選取您的&#x200B;**[!UICONTROL Filter conditions]**。 在此，我們想要鎖定屬於三個忠誠度計畫其中一個層級的收件者。

   ![](assets/custom_profile_17.png)

1. 按一下&#x200B;**[!UICONTROL Confirm]**，然後在完成篩選時，按一下&#x200B;**[!UICONTROL Next]**。
1. 定義並個人化郵件內容、寄件者名稱和主旨。 如需電子郵件建立的詳細資訊，請參閱此[頁面](../../designing/using/designing-content-in-adobe-campaign.md)。

   然後，按一下&#x200B;**[!UICONTROL Create]**。

1. 準備就緒後，您可以預覽並傳送訊息。 有關如何準備和傳送訊息的詳細資訊，請參閱此[頁面](../../sending/using/preparing-the-send.md)。

電子郵件正確傳送給您選取的收件者後，您就可以開始篩選資料，並追蹤傳送報表的成功情況。

## 步驟4：建立動態報告，使用自訂設定檔維度篩選收件者 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

傳送傳遞後，您可以使用&#x200B;**[!UICONTROL Profile]**&#x200B;表格中的自訂設定檔維度來劃分報表。

1. 從「**[!UICONTROL Reports]**」索引標籤中，選取現成可用的報表，或按一下「**[!UICONTROL Create]**」按鈕以從頭開始建立。

   ![](assets/custom_profile_18.png)

1. 在&#x200B;**[!UICONTROL Dimensions]**&#x200B;類別中，按一下&#x200B;**[!UICONTROL Profile]**，然後將您的自訂&#x200B;**熟客方案**&#x200B;設定檔維度拖放至您的自由表格。

   ![](assets/custom_profile_19.png)

1. 拖放&#x200B;**[!UICONTROL Processed/Sent]**&#x200B;和&#x200B;**[!UICONTROL Open]**&#x200B;量度以開始篩選您的資料。

   ![](assets/custom_profile_20.png)

1. 視需要在工作區中拖放視覺效果。

   ![](assets/custom_profile_21.png)

**相關主題：**

* [使用自訂設定檔資料建立深入分析的報告](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
