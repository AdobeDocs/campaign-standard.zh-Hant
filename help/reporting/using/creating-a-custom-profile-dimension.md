---
title: 建立自訂設定檔維度
description: 瞭解如何根據自定義配置檔案資料建立自定義配置檔案維。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---

# 建立自訂設定檔維度{#creating-a-custom-profile-dimension}

還可以根據配置檔案自定義資源擴展期間建立的自定義配置檔案資料建立和管理報告。

在本示例中，我們要建立自定義配置檔案欄位 **忠誠計畫** 分為三個層次：金銀銅。 然後，將擴展此自定義配置檔案，使其能夠將其用作動態報告中的自定義配置檔案維。

* [步驟1:建立新配置檔案欄位](#step-1--create-a-new-profile-field)
* [步驟2:使用配置檔案欄位擴展發送日誌](#step-2--extend-the-sending-logs-with-the-profile-field)
* [第3步：建立以在會員計畫中登記的收件人為目標的交貨](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [第4步：建立動態報告以篩選具有自定義配置檔案維度的收件人](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 步驟1:建立新配置檔案欄位 {#step-1--create-a-new-profile-field}

我們首先需要建立新的配置檔案欄位 **會員計畫** 將忠誠度分配給我們的收件人：金銀銅。

>[!NOTE]
>
>自定義資源只能由管理員管理。

若要這麼做：

1. 從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** 然後 **[!UICONTROL Profile (profile)]** 自定義資源。

   ![](assets/custom_profile_1.png)

1. 從 **[!UICONTROL Data structure]** 的 **[!UICONTROL Fields]** 的 **[!UICONTROL Add field]** 按鈕

   ![](assets/custom_profile_2.png)

1. 輸入 **[!UICONTROL Label]**。 **[!UICONTROL ID]** 並選擇自定義資源 **[!UICONTROL Type]**。 這裡，我們選擇 **[!UICONTROL Text]** 因為受贈者可以選擇金銀銅。

   ![](assets/custom_profile_3.png)

1. 按一下 ![](assets/custom_profile_22.png) 表徵圖。

   ![](assets/custom_profile_12.png)

1. 在此，我們需要通過檢查 **[!UICONTROL Specify a list of authorized valued]** 通過按一下 **[!UICONTROL Create element]**。

   ![](assets/custom_profile_13.png)

1. 輸入 **[!UICONTROL Label]** 和 **[!UICONTROL Value]** 按一下 **[!UICONTROL Add]**。 在本例中，我們需要創造價值金、銀和銅。 完成時，按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/custom_profile_14.png)

1. 選取 **[!UICONTROL Screen definition]** 索引標籤。在 **[!UICONTROL Detail screen configuration]** 下拉，檢查 **[!UICONTROL Add personalized fields]** 的下界。

   ![](assets/custom_profile_4.png)

1. 按一下 **[!UICONTROL Add an element]** 按鈕。 選擇 **[!UICONTROL Type]**: **[!UICONTROL Input field]**。 **[!UICONTROL Value]** 或 **[!UICONTROL List]**，然後在此新節中添加的欄位。

   ![](assets/custom_profile_5.png)

1. 您還可以在欄位中為分區添加標題 **[!UICONTROL Customize the title of the section where the fields will be displayed]**。

   按一下 **[!UICONTROL Save]** 完成配置時。

   ![](assets/custom_profile_6.png)

1. 從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** 開始發佈自定義資源。
1. 按一下 **[!UICONTROL Prepare publication]** 然後，在準備完成後，按一下 **[!UICONTROL Publish]** 按鈕

   ![](assets/custom_profile_7.png)

您的新配置檔案欄位現在可以由您的收件人使用和選擇。

![](assets/custom_profile_8.png)

## 步驟2:使用配置檔案欄位擴展發送日誌 {#step-2--extend-the-sending-logs-with-the-profile-field}

現在，您的配置檔案欄位已建立，我們需要將發送日誌與配置檔案欄位一起擴展，以在動態報告中建立關聯的自定義配置檔案維。

在使用配置檔案欄位擴展日誌之前，請確保PII窗口已被接受，以便能夠訪問 **[!UICONTROL Sending logs extension]** 頁籤。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

>[!NOTE]
>
>只有管理員才能使用配置檔案欄位擴展日誌。

1. 從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** 然後 **[!UICONTROL Profile (profile)]** 自定義資源。
1. 開啟 **[!UICONTROL Sending logs extension]** 下拉。
1. 按一下 **[!UICONTROL Create element]** 按鈕。

   ![](assets/custom_profile_9.png)

1. 選擇以前建立的欄位，然後按一下 **[!UICONTROL Confirm]**。
1. 檢查 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 建立自定義配置檔案維。

   ![](assets/custom_profile_10.png)

   僅當接受PII窗口時，此選項才可用。 如需關於此項目的詳細資訊，請參閱此[頁面](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

1. 按一下 **[!UICONTROL Add]** 然後保存您的自定義資源。
1. 由於自定義資源已修改，因此我們需要發佈它來實施新的更改。

   從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** 開始發佈自定義資源。

1. 按一下 **[!UICONTROL Prepare publication]** 然後，在準備完成後，按一下 **[!UICONTROL Publish]** 按鈕

   ![](assets/custom_profile_7.png)

您的自定義配置檔案現在可作為報表中的自定義配置檔案維使用。

現在，您的欄位已建立，並且發送日誌已通過此配置檔案欄位擴展，您可以開始以遞送中的收件人為目標。

## 第3步：建立以在會員計畫中登記的收件人為目標的交貨 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

發佈配置檔案欄位後，您可以開始交付。 在此示例中，我們要瞄準在會員計畫中登記的每個收件人。

1. 在 **[!UICONTROL Marketing activities]** 索引標籤中，按一下 **[!UICONTROL Create]**，然後選取 **[!UICONTROL Email]**。
1. 選擇 **[!UICONTROL Email type]** 然後輸入電子郵件的屬性。
1. 要將註冊到會員計畫的收件人作為目標，請拖放 **[!UICONTROL Profiles (attributes)]** 的子菜單。
1. 從 **[!UICONTROL Field]** 下拉。

   ![](assets/custom_profile_16.png)

1. 選擇 **[!UICONTROL Filter conditions]**。 在此，我們希望將目標對象定為三個忠誠度計畫級別之一的參與者。

   ![](assets/custom_profile_17.png)

1. 按一下 **[!UICONTROL Confirm]** 完成篩選後，按一下 **[!UICONTROL Next]**。
1. 定義並個性化消息內容、發件人名稱和主題。 有關建立電子郵件的詳細資訊，請參閱 [頁](../../designing/using/designing-content-in-adobe-campaign.md)。

   然後，按一下 **[!UICONTROL Create]**。

1. 準備好後，您可以預覽併發送您的消息。 有關如何準備和發送郵件的詳細資訊，請參閱此 [頁](../../sending/using/preparing-the-send.md)。

在將電子郵件正確發送到選定的收件人後，您可以開始篩選資料並通過報告跟蹤交付成功與否。

## 第4步：建立動態報告以篩選具有自定義配置檔案維度的收件人 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

在發送交貨後，您可以使用自定義配置檔案維從 **[!UICONTROL Profile]** 的子菜單。

1. 從 **[!UICONTROL Reports]** 頁籤，選擇現成報告，或按一下 **[!UICONTROL Create]** 按鈕，從頭開始。

   ![](assets/custom_profile_18.png)

1. 在 **[!UICONTROL Dimensions]** 類別，按一下 **[!UICONTROL Profile]** 然後拖放您的自定義 **會員計畫** 自由格式表的配置檔案尺寸。

   ![](assets/custom_profile_19.png)

1. 拖放 **[!UICONTROL Processed/Sent]** 和 **[!UICONTROL Open]** 開始篩選資料的度量。

   ![](assets/custom_profile_20.png)

1. 根據需要，在工作區中拖放可視化內容。

   ![](assets/custom_profile_21.png)

**相關主題：**

* [使用自定義配置檔案資料建立有見地的報告](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
