---
title: 建立自訂描述檔維度
seo-title: 建立自訂描述檔維度
description: 建立自訂描述檔維度
seo-description: 瞭解如何根據自訂描述檔資料建立自訂描述檔維度。
page-status-flag: 從未啓動
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 報告功能
content-type: reference
topic-tags: 自訂報表
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# 建立自訂描述檔維度{#creating-a-custom-profile-dimension}

也可以根據設定檔自訂資源擴充功能期間建立的自訂描述檔資料來建立和管理報表。

在此範例中，我們想要建立自訂設定檔欄位 **忠誠度方案** ，其可分為三個層級：黃金、銀和銅。接著將此自訂描述檔延伸為可在動態報表中使用的自訂描述檔維度。

* [步驟1：建立新的描述檔欄位](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [步驟2：使用描述檔欄位擴充傳送記錄檔](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [步驟3：建立已註冊加入忠誠度計劃的傳送目標收件者](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [步驟4：建立動態報表以篩選具有自訂描述檔維度的收件者](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 步驟1：建立新的描述檔欄位 {#step-1--create-a-new-profile-field}

我們首先需要建立新的個人檔案欄位 **忠誠度方案** ，將忠誠度等級指派給收件者：黃金、銀或銅。

>[!NOTE]
>
>自訂資源只能由管理員管理。

若要這麼做：

1. 從進階功能表中，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** 然後自 **[!UICONTROL Profile (profile)]** 訂資源。

   ![](assets/custom_profile_1.png)

1. 從 **[!UICONTROL Data structure]** 標籤中，在 **[!UICONTROL Fields]** 類別中按一下 **[!UICONTROL Add field]** 按鈕。

   ![](assets/custom_profile_2.png)

1. 輸入 **[!UICONTROL Label]**&#x200B;並 **[!UICONTROL ID]** 選取自訂資源 **[!UICONTROL Type]**。在這裡，我們選擇 **[!UICONTROL Text]** 了因為收件者將可以選擇黃金、銀和銅。

   ![](assets/custom_profile_3.png)

1. 按一下 ![](assets/custom_profile_22.png) 圖示以定義您的欄位。

   ![](assets/custom_profile_12.png)

1. 在這裡，我們需要透過按一下 **[!UICONTROL Specify a list of authorized valued]** 並建立每個值來指定授權值 **[!UICONTROL Create element]**。

   ![](assets/custom_profile_13.png)

1. 輸入然後 **[!UICONTROL Label]****[!UICONTROL Value]** 按 **[!UICONTROL Add]**&#x200B;一下。在此範例中，我們需要建立價值金、銀和銅的價值。完成時按一下 **[!UICONTROL Confirm]** 。

   ![](assets/custom_profile_14.png)

1. 選取 **[!UICONTROL Screen definition]** 標籤。在 **[!UICONTROL Detail screen configuration]** 下拉式清單中，檢查 **[!UICONTROL Add personalized fields]** 區段以建立個人檔案中的新章節。

   ![](assets/custom_profile_4.png)

1. 按一下 **[!UICONTROL Add an element]** 按鈕以建立新區段。選擇 **[!UICONTROL Type]**&#x200B;下列項目： **[!UICONTROL Input field]****[!UICONTROL Value]** 或 **[!UICONTROL List]**&#x200B;新增至此新區段中的欄位。

   ![](assets/custom_profile_5.png)

1. 您也可以在欄位中新增標題至您的區段 **[!UICONTROL Customize the title of the section where the fields will be displayed]**。

   在 **[!UICONTROL Save]** 完成設定時按一下。

   ![](assets/custom_profile_6.png)

1. 從進階功能表中，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** 開始發佈您的自訂資源。
1. 按一下 **[!UICONTROL Prepare publication]** 完成準備後，按一下 **[!UICONTROL Publish]** 按鈕。

   ![](assets/custom_profile_7.png)

您的新描述檔欄位現在可供您的收件者使用和選取。

![](assets/custom_profile_8.png)

## 步驟2：使用描述檔欄位擴充傳送記錄檔 {#step-2--extend-the-sending-logs-with-the-profile-field}

現在您的描述檔欄位已建立，我們需要使用描述檔欄位擴充傳送記錄檔，以在動態報表中建立關聯的自訂描述檔維度。

在將記錄檔擴充為我們的描述檔欄位之前，請確定PII視窗已被接受，以便存取 **[!UICONTROL Sending logs extension]** 標籤。如需更多資訊，請參閱本 [頁](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>記錄檔只能透過管理員的描述檔欄位加以延伸。

1. 從進階功能表中，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** 然後自 **[!UICONTROL Profile (profile)]** 訂資源。
1. 開啓 **[!UICONTROL Sending logs extension]** 下拉式清單。
1. 按一下 **[!UICONTROL Create element]** 按鈕。

   ![](assets/custom_profile_9.png)

1. 選取您先前建立的欄位，然後按一下 **[!UICONTROL Confirm]**。
1. 勾選 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 以建立您的自訂描述檔維度。

   ![](assets/custom_profile_10.png)

   只有當PII視窗被接受時，才可使用此選項。如需更多資訊，請參閱本 [頁](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 按一下然後 **[!UICONTROL Add]** 儲存您的自訂資源。
1. 自訂資源經過修改後，我們必須發佈它才能實施新變更。

   從進階功能表中，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** 開始發佈您的自訂資源。

1. 按一下 **[!UICONTROL Prepare publication]** 完成準備後，按一下 **[!UICONTROL Publish]** 按鈕。

   ![](assets/custom_profile_7.png)

您的自訂設定檔現在可作為報表中的自訂描述檔維度使用。

現在您的欄位已建立，並已透過此描述檔欄位擴充記錄檔，您可以在傳送中開始定位收件者。

## 步驟3：建立已註冊加入忠誠度計劃的傳送目標收件者 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

在您的個人資料欄位發佈後，您就可以開始傳送。在此範例中，我們想要定位每位註冊加入忠誠度計劃的收件者。

1. 從 **[!UICONTROL Marketing activities]** 標籤中按一下， **[!UICONTROL Create]** 然後選取 **[!UICONTROL Email]**。
1. 選擇然後 **[!UICONTROL Email type]** 輸入您的電子郵件屬性。
1. 若要鎖定忠誠度計劃的收件者，請拖放 **[!UICONTROL Profiles (attributes)]** 活動。
1. 從 **[!UICONTROL Field]** 下拉式清單中選取先前建立的欄位。

   ![](assets/custom_profile_16.png)

1. 選擇您 **[!UICONTROL Filter conditions]**&#x200B;的。在這裡，我們想要定位屬於三個忠誠度方案等級之一的收件者。

   ![](assets/custom_profile_17.png)

1. 按一下之後按一下 **[!UICONTROL Confirm]** ，按 **[!UICONTROL Next]**&#x200B;一下。
1. 定義並個人化訊息內容、傳送者名稱和主旨。有關電子郵件建立的更多資訊，請參閱本 [頁](../../designing/using/about-email-content-design.md#about-the-email-designer)。

   **[!UICONTROL Create]**&#x200B;然後，按一下。

1. 準備就緒後，您可以預覽並傳送訊息。如需準備和傳送訊息的詳細資訊，請參閱本 [頁](../../sending/using/preparing-the-send.md)。

將電子郵件正確傳送給所選收件者後，您就可以開始篩選資料並追蹤傳送報表是否成功。

## 步驟4：建立動態報表以篩選具有自訂描述檔維度的收件者 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

傳送傳送後，您可以從 **[!UICONTROL Profile]** 表格使用自訂描述檔維度來劃分報表。

1. 從 **[!UICONTROL Reports]** 標籤中選擇立即可用的報表，或按一下 **[!UICONTROL Create]** 按鈕以從頭開始。

   ![](assets/custom_profile_18.png)

1. **[!UICONTROL Dimensions]** 在類別中，按一下，然後 **[!UICONTROL Profile]** 將自訂 **的忠誠度方案** 描述檔維度拖放到自由表格中。

   ![](assets/custom_profile_19.png)

1. 拖放和 **[!UICONTROL Processed/Sent]****[!UICONTROL Open]** 度量開始篩選您的資料。

   ![](assets/custom_profile_20.png)

1. 視需要拖放工作區中的視覺化。

   ![](assets/custom_profile_21.png)

**相關主題：**

* [使用自訂描述檔資料建立具洞察力的報表](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
