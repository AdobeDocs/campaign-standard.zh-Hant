---
title: 設定螢幕定義
seo-title: 設定螢幕定義
description: 設定螢幕定義
seo-description: 瞭解如何根據資源資料結構定義新的Adobe Campaign畫面。
page-status-flag: 從未啓動
uuid: 40848197-b1 a0-4018-bc3-7df64 fb86307
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 新增或延伸-資源
discoiquuid: 9dabb328-ac0 c-49fd-8996-1d56341 ee7 ac
context-tags: CusResource，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b3291f7c0cbede6a3180ad4a4ab8a365720f5031

---


# Configuring the screen definition{#configuring-the-screen-definition}

建立資源或新增欄位至現有資源時，您可以定義要如何顯示在介面中。

此步驟不是強制性的，因為您仍可透過工作流程、觀眾和REST API填入資源並存取資料。

In the **[!UICONTROL Screen definition]** tab, you can:

* 新增對導覽窗格中自訂資源的存取權
* 將組成資源的元素清單個人化
* 定義顯示資源之每個元素的詳細檢視方式

## Enabling access from the navigation menu {#enabling-access-from-the-navigation-menu}

如果您希望資源有專屬螢幕，可以從導覽功能表中使用。

1. From the **[!UICONTROL Screen definition]** tab of the resource, unfold the **[!UICONTROL Navigation]** section.
1. Check the **[!UICONTROL Add an entry in the 'Client data' section]** box to allow access to this resource from the navigation pane.

   ![](assets/schema_extension_19.png)

The resource will appear as a sub-entry within the **[!UICONTROL Client data]** section.

## Defining the default list configuration {#defining-the-default-list-configuration}

The **[!UICONTROL List configuration]** section of the screen definition lets you define the columns and information that will be displayed by default in the overview of a resource.

1. Check the **[!UICONTROL Customize the list configuration]** box to define the way the columns of the resource are displayed.
1. Use the **[!UICONTROL Create element]** button to select a field from those that you have created.
1. 建立的欄位會顯示在清單中。您可以編輯其標籤及其寬度。

   ![](assets/schema_extension_20.png)

1. In the **[!UICONTROL Simple search]** section, check the **[!UICONTROL Specify the fields to be taken into account in the search]** to define which fields will be included in the search.

   >[!CAUTION]
   >
   >此組態取代預設搜尋中使用的欄位。

1. In the **[!UICONTROL Advanced filtering]** section, check the **[!UICONTROL Add search fields]** box to add additional fields beyond the simple search field. 例如，如果您從建立的欄位選取「日期」欄位，使用者將能夠執行僅參照日期的搜尋。
1. 您可以修改兩個搜尋類型的欄位順序。
1. 對於進階搜尋，您可以新增連結至連結資源的欄位。These filters appear in the **[!UICONTROL Search]** menu of the generated screen.

現在已定義資源的概述畫面。

## Defining the detail screen configuration {#defining-the-detail-screen-configuration}

The **[!UICONTROL Detail screen configuration]** section of the screen definition lets you define the columns and information that will be displayed in the detail screen of each element of the resource.

1. Unfold the **[!UICONTROL Detail screen configuration]** section and check the **[!UICONTROL Define a detail screen]** to configure the screen that corresponds to each element of the resource. 如果您未勾選此方塊，將無法存取此資源的詳細資料檢視。
1. 只要按一下，即可從自訂資源新增所有欄位。To do this, click the ![](assets/addallfieldsicon.png) icon or use the **[!UICONTROL Add an element]** button.
1. 從為此資源建立的元素中選取元素，並指定欄位類型：

   * **[!UICONTROL Input field]**：是可編輯欄位。
   * **[!UICONTROL Value]**：為唯讀欄位。
   * **[!UICONTROL List]**：是表格。
   * **[!UICONTROL Separator]**：將您的元素分割為類別。
   ![](assets/schema_extension_23.png)

1. 新增的元素會顯示在清單中。您可以編輯其標籤。

   ![](assets/schema_extension_22.png)

1. Add as many **[!UICONTROL Separator]** as needed to split your elements into different categories.

   這可讓您顯示分隔符號以更好地組織視窗。

   ![](assets/schema_extension_25.png)

資源的詳細畫面現在已設定。

## Actions on data section {#actions-on-data-section}

這些設定可讓您在自訂資源畫面中顯示控制列。有三個可用選項：

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**：此選項可讓您啓用資源的建立元素。因此，使用者可以新增其他記錄。

   >[!NOTE]
   >
   >您必須先啓動連結至資源的詳細畫面，才能提供此選項。

* **[!UICONTROL Authorize duplicating]**：此選項可讓您啓用連結至自訂資源的記錄。
* **[!UICONTROL Authorize deleting]**：此選項可讓您啓動連結至自訂資源的記錄。

