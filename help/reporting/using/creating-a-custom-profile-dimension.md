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
source-git-commit: e9a4d99ddf311898c48b2b352fa13f5b59ed1fbe

---


# Creating a custom profile dimension{#creating-a-custom-profile-dimension}

也可以根據設定檔自訂資源擴充功能期間建立的自訂描述檔資料來建立和管理報表。

In this example, we want to create the custom profile field **Loyalty programs** which will be divided into three levels: gold, silver and bronze. 接著將此自訂描述檔延伸為可在動態報表中使用的自訂描述檔維度。

* [步驟1：建立新的描述檔欄位](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [步驟2：使用描述檔欄位擴充傳送記錄檔](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [步驟3：建立已註冊加入忠誠度計劃的傳送目標收件者](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [步驟4：建立動態報表以篩選具有自訂描述檔維度的收件者](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Step 1: Create a new profile field {#step-1--create-a-new-profile-field}

We first need to create the new profile field **Loyalty program** that will assign loyalty level to our recipients: gold, silver or bronze.

>[!NOTE]
>
>自訂資源只能由管理員管理。

若要這麼做：

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** then the **[!UICONTROL Profile (profile)]** custom resource.

   ![](assets/custom_profile_1.png)

1. From the **[!UICONTROL Data structure]** tab, in the **[!UICONTROL Fields]** category, click the **[!UICONTROL Add field]** button.

   ![](assets/custom_profile_2.png)

1. Enter the **[!UICONTROL Label]**, **[!UICONTROL ID]** and select the custom resource **[!UICONTROL Type]**. Here, we selected **[!UICONTROL Text]** since recipients will have the choice between gold, silver and bronze.

   ![](assets/custom_profile_3.png)

1. Click the ![](assets/custom_profile_22.png) icon to define your field.

   ![](assets/custom_profile_12.png)

1. Here, we need to specify the authorized values by checking **[!UICONTROL Specify a list of authorized valued]** and create each value by clicking **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Enter the **[!UICONTROL Label]** and **[!UICONTROL Value]** then click **[!UICONTROL Add]**. 在此範例中，我們需要建立價值金、銀和銅的價值。Click **[!UICONTROL Confirm]** when done.

   ![](assets/custom_profile_14.png)

1. Select the **[!UICONTROL Screen definition]** tab. In the **[!UICONTROL Detail screen configuration]** drop-down, check **[!UICONTROL Add personalized fields]** section to create a new section in our profile.

   ![](assets/custom_profile_4.png)

1. Click the **[!UICONTROL Add an element]** button to create your new section. Select the **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** or **[!UICONTROL List]**, then the field to add in this new section.

   ![](assets/custom_profile_5.png)

1. You can also add a title to your section in the field **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Click **[!UICONTROL Save]** when the configuration is done.

   ![](assets/custom_profile_6.png)

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** to start publishing your custom resource.
1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button.

   ![](assets/custom_profile_7.png)

您的新描述檔欄位現在可供您的收件者使用和選取。

![](assets/custom_profile_8.png)

## Step 2: Extend the sending logs with the profile field {#step-2--extend-the-sending-logs-with-the-profile-field}

現在您的描述檔欄位已建立，我們需要使用描述檔欄位擴充傳送記錄檔，以在動態報表中建立關聯的自訂描述檔維度。

Before extending the log with our profile field, make sure that the PII window was accepted to have access to the **[!UICONTROL Sending logs extension]** tab. For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>記錄檔只能透過管理員的描述檔欄位加以延伸。

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** then the **[!UICONTROL Profile (profile)]** custom resource.
1. Open the **[!UICONTROL Sending logs extension]** drop-down.
1. Click the **[!UICONTROL Create element]** button.

   ![](assets/custom_profile_9.png)

1. Select your previously created field and click **[!UICONTROL Confirm]**.
1. Check **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** to create your custom profile dimension.

   ![](assets/custom_profile_10.png)

   只有當PII視窗被接受時，才可使用此選項。For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Click **[!UICONTROL Add]** then save your custom resource.
1. 自訂資源經過修改後，我們必須發佈它才能實施新變更。

   From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** to start publishing your custom resource.

1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button.

   ![](assets/custom_profile_7.png)

您的自訂設定檔現在可作為報表中的自訂描述檔維度使用。

現在您的欄位已建立，並已透過此描述檔欄位擴充記錄檔，您可以在傳送中開始定位收件者。

## Step 3: Create a delivery targeting recipients enrolled in the loyalty program {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

在您的個人資料欄位發佈後，您就可以開始傳送。在此範例中，我們想要定位每位註冊加入忠誠度計劃的收件者。

1. From the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Email]**.
1. Choose an **[!UICONTROL Email type]** then enter your email's properties.
1. To target recipient enrolled in the loyalty program, drag and drop the **[!UICONTROL Profiles (attributes)]** activity.
1. Select your previously created field from the **[!UICONTROL Field]** drop-down.

   ![](assets/custom_profile_16.png)

1. Select your **[!UICONTROL Filter conditions]**. 在這裡，我們想要定位屬於三個忠誠度方案等級之一的收件者。

   ![](assets/custom_profile_17.png)

1. Click **[!UICONTROL Confirm]** then when done filtering, click **[!UICONTROL Next]**.
1. 定義並個人化訊息內容、傳送者名稱和主旨。For more information on email creation refer to this [page](../../designing/using/about-email-content-design.md#about-the-email-designer).

   **[!UICONTROL Create]**&#x200B;然後，按一下。

1. 準備就緒後，您可以預覽並傳送訊息。For more information on how to prepare and send your message, refer to this [page](../../sending/using/preparing-the-send.md).

將電子郵件正確傳送給所選收件者後，您就可以開始篩選資料並追蹤傳送報表是否成功。

## Step 4: Create a dynamic report to filter recipients with the custom profile dimension {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

After sending your delivery, you can breakdown reports using your custom profile dimension from the **[!UICONTROL Profile]** table.

1. From the **[!UICONTROL Reports]** tab, select an out-of-the-box report or click the **[!UICONTROL Create]** button to start one from scratch.

   ![](assets/custom_profile_18.png)

1. **[!UICONTROL Dimensions]** 在類別中，按一下，然後 **[!UICONTROL Profile]** 將自訂 **的忠誠度方案** 描述檔維度拖放到自由表格中。

   ![](assets/custom_profile_19.png)

1. Drag and drop the **[!UICONTROL Processed/Sent]** and **[!UICONTROL Open]** metrics to start filtering your data.

   ![](assets/custom_profile_20.png)

1. 視需要拖放工作區中的視覺化。

   ![](assets/custom_profile_21.png)

