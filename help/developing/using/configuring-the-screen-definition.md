---
solution: Campaign Standard
product: campaign
title: 設定螢幕定義
description: 瞭解如何根據資源資料結構定義新的 Adobe Campaign 畫面。
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: cusResource,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 100%

---


# 設定螢幕定義{#configuring-the-screen-definition}

在建立資源或向現有資源新增欄位時，可以定義希望這些欄位在介面中的顯示方式。

此步驟並非必要步驟，因為您仍可以填入資源，並透過工作流程、對象和 REST API 存取其資料。

在　**[!UICONTROL Screen definition]**　索引標籤中，您可以：

* 在導覽窗格中新增自訂資源的存取權限
* 個人化顯示組成資源的元素清單的方式
* 定義資源每個要素的詳細資訊檢視的顯示方式

## 從導覽功能表啟用存取 {#enabling-access-from-the-navigation-menu}

如果您希望資源有專用的畫面，可以從導航菜單中使其可用。

1. 從資源的　**[!UICONTROL Screen definition]**　頁籤展開該 **[!UICONTROL Navigation]** 區段。
1. 核取該 **[!UICONTROL Add an entry in the 'Client data' section]** 方塊可允許從導航窗格存取此資源。

   ![](assets/schema_extension_19.png)

資源將作為子項目顯示在 **[!UICONTROL Client data]** 區段中。

## 定義預設清單設定 {#defining-the-default-list-configuration}

畫面定義的 **[!UICONTROL List configuration]** 區段可讓您定義預設顯示在資源概觀中的欄和資訊。

1. 核取&#x200B;**[!UICONTROL Customize the list configuration]** 該方塊以定義資源欄的顯示方式。
1. 使用 **[!UICONTROL Create element]** 按鈕從已建立的欄位中選取欄位。
1. 建立的欄位將顯示在清單中。您可以編輯其標籤和寬度。

   ![](assets/schema_extension_20.png)

1. 在 **[!UICONTROL Simple search]** 區段中，核取 **[!UICONTROL Specify the fields to be taken into account in the search]** 以定義將包含在搜尋中的欄位。

   >[!IMPORTANT]
   >
   >此設定將替換預設搜尋中使用的欄位。

1. 在 **[!UICONTROL Advanced filtering]** 區段中，核取 **[!UICONTROL Add search fields]** 方塊以新增簡單搜尋欄位以外的其他欄位。例如，如果您從已建立的欄位中選取 &quot;date&quot; 欄位，使用者將可執行僅參考日期的搜尋。
1. 您可以修改這兩種搜尋類型的欄位順序。
1. 對於進階搜尋，您可以新增連結到連結資源的欄位。這些篩選器會出現在產生畫面的 **[!UICONTROL Search]** 功能表中。

現在已定義資源的概觀畫面。

## 定義詳細畫面設定 {#defining-the-detail-screen-configuration}

畫面定義的 **[!UICONTROL Detail screen configuration]** 區段可讓您定義將顯示在資源每個元素的詳細資訊畫面中的欄和資訊。

1. 展開該 **[!UICONTROL Detail screen configuration]** 區段並核取 **[!UICONTROL Define a detail screen]** 以設定與資源的每個元素對應的畫面。如果不核取此方塊，則無法存取此資源元素的詳細檢視。
1. 只要按一下，您就可從自訂資源新增所有欄位。若要這麼做，請按一下 ![](assets/addallfieldsicon.png) 圖示或使用 **[!UICONTROL Add an element]** 按鈕。
1. 從為此資源建立的元素中選取一個元素並指定欄位類型：

   * **[!UICONTROL Input field]**：是可編輯的欄位。
   * **[!UICONTROL Value]**：是唯讀欄位。
   * **[!UICONTROL List]**：是表格。
   * **[!UICONTROL Separator]**：將您的元素分割成類別。

   ![](assets/schema_extension_23.png)

1. 新增的元素會顯示在清單中。您可以編輯其標籤。

   ![](assets/schema_extension_22.png)

1. 視需要新增 **[!UICONTROL Separator]** 個元素，將元素分割為不同類別。

   這可讓您顯示分隔符號，以更好地組織您的視窗。

   ![](assets/schema_extension_25.png)

資源的詳細資訊畫面現在已設定。

## 資料區段的動作 {#actions-on-data-section}

這些設定可讓您在自訂資源畫面中顯示控制欄。有三種可用選項：

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**：此選項可讓您啟動建立資源的元素。因此，使用者可以新增其他記錄。

   >[!NOTE]
   >
   >您必須先啟動連結至資源的詳細資訊畫面，才能使此選項可用。

* **[!UICONTROL Authorize duplicating]**：此選項可讓您啟動連結到自定義資源的資料重複刪除記錄。
* **[!UICONTROL Authorize deleting]**：此選項可讓您啟動連結到自訂資源的刪除記錄。
