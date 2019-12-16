---
title: 建立自訂設定檔維度
description: 瞭解如何根據自訂描述檔資料建立自訂描述檔維度。
page-status-flag: never-activated
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: customizing-reports
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# 建立自訂設定檔維度{#creating-a-custom-profile-dimension}

您也可以根據在描述檔自訂資源擴充期間建立的自訂描述檔資料，來建立和管理報表。

在此範例中，我們要建立自訂描述檔欄位 **Loyalty程式** ，將其分為三個層級：金、銀、銅。 然後，此自訂描述檔將會加以擴充，以便在動態報表中將它當做自訂描述檔維度使用。

* [步驟1:建立新的描述檔欄位](#step-1--create-a-new-profile-field)
* [步驟2:使用描述檔欄位擴充傳送記錄檔](#step-2--extend-the-sending-logs-with-the-profile-field)
* [步驟3:建立已註冊忠誠度方案的遞送定位收件者](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [步驟4:建立動態報表以篩選具有自訂描述檔維度的收件者](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 步驟1:建立新的描述檔欄位 {#step-1--create-a-new-profile-field}

我們首先需要建立新的描述檔欄位 **Loyalty方案** ，將忠誠度等級指派給收件者：金、銀或銅。

>[!NOTE]
>
>自訂資源只能由管理員管理。

若要這麼做：

1. 從進階功能表中，選擇 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** 然後選 **[!UICONTROL Profile (profile)]** 擇自訂資源。

   ![](assets/custom_profile_1.png)

1. 在標籤 **[!UICONTROL Data structure]** 的類別中，按 **[!UICONTROL Fields]** 一下按 **[!UICONTROL Add field]** 鈕。

   ![](assets/custom_profile_2.png)

1. 輸入 **[!UICONTROL Label]**, **[!UICONTROL ID]** 然後選擇自定義資源 **[!UICONTROL Type]**。 在這裡，我們選 **[!UICONTROL Text]** 擇了，因為接受者可以選擇金、銀和銅。

   ![](assets/custom_profile_3.png)

1. 按一下 ![](assets/custom_profile_22.png) 圖示以定義欄位。

   ![](assets/custom_profile_12.png)

1. 在這裡，我們需要透過按一下來檢查並建立每 **[!UICONTROL Specify a list of authorized valued]** 個值，以指定授權值 **[!UICONTROL Create element]**。

   ![](assets/custom_profile_13.png)

1. 輸入， **[!UICONTROL Label]** 然後 **[!UICONTROL Value]** 按一下 **[!UICONTROL Add]**。 在此範例中，我們需要建立價值金、銀和銅。 完成時 **[!UICONTROL Confirm]** 按一下。

   ![](assets/custom_profile_14.png)

1. 選擇選 **[!UICONTROL Screen definition]** 項卡。 在下拉 **[!UICONTROL Detail screen configuration]** 式清單中，勾選 **[!UICONTROL Add personalized fields]** 區段以在我們的描述檔中建立新區段。

   ![](assets/custom_profile_4.png)

1. 按一下 **[!UICONTROL Add an element]** 按鈕以建立新區段。 選擇 **[!UICONTROL Type]**:, **[!UICONTROL Input field]**&#x200B;或 **[!UICONTROL Value]****[!UICONTROL List]**，則新增至此新區段的欄位。

   ![](assets/custom_profile_5.png)

1. 您也可以在欄位中新增標題至您的區段 **[!UICONTROL Customize the title of the section where the fields will be displayed]**。

   完成 **[!UICONTROL Save]** 配置時按一下。

   ![](assets/custom_profile_6.png)

1. 從進階選單中，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** 以開始發佈自訂資源。
1. 完 **[!UICONTROL Prepare publication]** 成準備後，按一下按 **[!UICONTROL Publish]** 鈕。

   ![](assets/custom_profile_7.png)

您的新描述檔欄位現在可供收件者使用和選取。

![](assets/custom_profile_8.png)

## 步驟2:使用描述檔欄位擴充傳送記錄檔 {#step-2--extend-the-sending-logs-with-the-profile-field}

現在您的描述檔欄位已建立，我們需要使用我們的描述檔欄位來擴充傳送記錄檔，以在動態報表中建立相關的自訂描述檔維度。

在使用我們的描述檔欄位擴充記錄檔之前，請確定已接受PII視窗以存取標 **[!UICONTROL Sending logs extension]** 簽。 For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>管理員只能使用配置檔案欄位擴展日誌。

1. 從進階功能表中，選擇 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** 然後選 **[!UICONTROL Profile (profile)]** 擇自訂資源。
1. 開啟 **[!UICONTROL Sending logs extension]** 下拉式清單。
1. Click the **[!UICONTROL Create element]** button.

   ![](assets/custom_profile_9.png)

1. 選取您先前建立的欄位，然後按一下 **[!UICONTROL Confirm]**。
1. 勾選以 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 建立您的自訂描述檔維度。

   ![](assets/custom_profile_10.png)

   此選項僅在接受PII視窗時才可用。 For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. 按一 **[!UICONTROL Add]** 下，然後儲存自訂資源。
1. 由於自訂資源已修改，因此我們需要發佈它以實作新的變更。

   從進階選單中，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** 以開始發佈自訂資源。

1. 完 **[!UICONTROL Prepare publication]** 成準備後，按一下按 **[!UICONTROL Publish]** 鈕。

   ![](assets/custom_profile_7.png)

您的自訂描述檔現在可在報表中當做自訂描述檔維度使用。

現在您的欄位已建立，而且傳送記錄已透過此描述檔欄位加以擴充，您就可以開始在傳送中鎖定收件者。

## 步驟3:建立已註冊忠誠度方案的遞送定位收件者 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

發佈您的設定檔欄位後，您就可以開始傳送。 在此範例中，我們要定位在忠誠度方案中註冊的每個收件者。

1. 在標籤 **[!UICONTROL Marketing activities]** 中，按一下， **[!UICONTROL Create]** 然後選取 **[!UICONTROL Email]**。
1. 選擇一 **[!UICONTROL Email type]** 個，然後輸入您電子郵件的屬性。
1. 若要定位已註冊至忠誠度方案的收件者，請拖放 **[!UICONTROL Profiles (attributes)]** 活動。
1. 從下拉式清單中選取您先前 **[!UICONTROL Field]** 建立的欄位。

   ![](assets/custom_profile_16.png)

1. 選擇您的 **[!UICONTROL Filter conditions]**。 在此，我們要鎖定屬於三個忠誠度計畫等級之一的收件者。

   ![](assets/custom_profile_17.png)

1. 按一 **[!UICONTROL Confirm]** 下，然後在完成篩選後按一 **[!UICONTROL Next]**&#x200B;下。
1. 定義並個人化訊息內容、傳送者名稱和主旨。 如需建立電子郵件的詳細資訊，請參閱本 [頁](../../designing/using/designing-content-in-adobe-campaign.md)。

   然後，按一下 **[!UICONTROL Create]**。

1. 準備就緒後，您可以預覽並傳送訊息。 有關如何準備和傳送訊息的詳細資訊，請參閱本 [頁](../../sending/using/preparing-the-send.md)。

在您的電子郵件正確傳送給所選取的收件者後，您就可以開始篩選資料，並透過報表追蹤傳送的成功。

## 步驟4:建立動態報表以篩選具有自訂描述檔維度的收件者 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

在傳送傳送後，您可以使用表格中的自訂描述檔維度來劃分 **[!UICONTROL Profile]** 報表。

1. 從標 **[!UICONTROL Reports]** 簽中，選取現成可用的報表，或按一下按鈕從頭 **[!UICONTROL Create]** 開始建立報表。

   ![](assets/custom_profile_18.png)

1. 在類別 **[!UICONTROL Dimensions]** 中，按一下 **[!UICONTROL Profile]** ，然後將自訂的「忠誠度 **** 」程式描述檔維度拖放至自由表格。

   ![](assets/custom_profile_19.png)

1. 拖放和量度 **[!UICONTROL Processed/Sent]** 以開 **[!UICONTROL Open]** 始篩選資料。

   ![](assets/custom_profile_20.png)

1. 視需要將視覺化拖放至您的工作區。

   ![](assets/custom_profile_21.png)

**相關主題：**

* [使用自訂描述檔資料來建立深入洞察的報告](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
