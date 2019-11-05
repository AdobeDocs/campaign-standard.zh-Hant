---
title: 設定螢幕定義
description: 瞭解如何根據資源資料結構定義新的Adobe Campaign畫面。
page-status-flag: 從未激活
uuid: 40848197-b1a0-4018-bfc3-7df64fb83307
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 開發
content-type: 參考
topic-tags: 添加或擴展資源
discoiquuid: 9dabb328-ac0c-49fd-8996-8d56341ee7ac
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 設定螢幕定義{#configuring-the-screen-definition}

在建立資源或向現有資源添加新欄位時，可以定義希望這些欄位在介面中的顯示方式。

此步驟並非必要步驟，因為您仍可以填入資源，並透過工作流程、對象和REST API存取其資料。

在標籤 **[!UICONTROL Screen definition]** 中，您可以：

* 在導覽窗格中新增自訂資源的存取權
* 個性化顯示組成資源的元素清單的方式
* 定義資源每個要素的詳細資訊視圖的顯示方式

## 從導覽功能表啟用存取 {#enabling-access-from-the-navigation-menu}

如果您希望資源有專用的螢幕，可以從導航菜單中使其可用。

1. 從資源 **[!UICONTROL Screen definition]** 的頁籤展開該 **[!UICONTROL Navigation]** 部分。
1. 選中該 **[!UICONTROL Add an entry in the 'Client data' section]** 框可允許從導航窗格訪問此資源。

   ![](assets/schema_extension_19.png)

資源將作為子條目顯示在節 **[!UICONTROL Client data]** 中。

## 定義預設清單配置 {#defining-the-default-list-configuration}

屏 **[!UICONTROL List configuration]** 幕定義部分允許您定義預設顯示在資源概述中的列和資訊。

1. 選中 **[!UICONTROL Customize the list configuration]** 該框以定義資源列的顯示方式。
1. 使用按 **[!UICONTROL Create element]** 鈕從已建立的欄位中選擇欄位。
1. 建立的欄位將顯示在清單中。 您可以編輯其標籤和寬度。

   ![](assets/schema_extension_20.png)

1. 在區 **[!UICONTROL Simple search]** 段中，選中 **[!UICONTROL Specify the fields to be taken into account in the search]** 以定義將包含在搜尋中的欄位。

   >[!CAUTION]
   >
   >此配置將替換預設搜索中使用的欄位。

1. 在區段 **[!UICONTROL Advanced filtering]** 中，核取方塊以 **[!UICONTROL Add search fields]** 新增簡單搜尋欄位以外的其他欄位。 例如，如果您從已建立的欄位中選取「日期」欄位，使用者將可執行僅參考日期的搜尋。
1. 您可以修改這兩種搜索類型的欄位順序。
1. 對於高級搜索，您可以添加連結到連結資源的欄位。 這些篩選器會出現在 **[!UICONTROL Search]** 產生的畫面功能表中。

現在已定義資源的概述螢幕。

## 定義詳細畫面設定 {#defining-the-detail-screen-configuration}

屏 **[!UICONTROL Detail screen configuration]** 幕定義部分允許您定義將顯示在資源每個元素的詳細資訊螢幕中的列和資訊。

1. 展開該 **[!UICONTROL Detail screen configuration]** 部分並檢 **[!UICONTROL Define a detail screen]** 查以配置與資源的每個元素對應的螢幕。 如果不選中此框，則無法訪問此資源元素的詳細視圖。
1. 只要按一下，您就可從自訂資源新增所有欄位。 若要這麼做，請按一下 ![](assets/addallfieldsicon.png) 圖示或使用按 **[!UICONTROL Add an element]** 鈕。
1. 從為此資源建立的元素中選擇一個元素並指定欄位類型：

   * **[!UICONTROL Input field]**:是可編輯的欄位。
   * **[!UICONTROL Value]**:是只讀欄位。
   * **[!UICONTROL List]**:是桌子。
   * **[!UICONTROL Separator]**:將您的元素分割成類別。
   ![](assets/schema_extension_23.png)

1. 新增的元素會顯示在清單中。 您可以編輯其標籤。

   ![](assets/schema_extension_22.png)

1. 視需要新增 **[!UICONTROL Separator]** 多個元素，將元素分割為不同類別。

   這可讓您顯示分隔符號，以更好地組織您的視窗。

   ![](assets/schema_extension_25.png)

資源的詳細資訊螢幕現在已配置。

## 資料區段的動作 {#actions-on-data-section}

這些設定可讓您在自訂資源畫面中顯示控制列。 有三種可用選項：

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**:此選項允許您激活建立資源的元素。 因此，用戶可以添加其他記錄。

   >[!NOTE]
   >
   >您必須先啟動連結至資源的詳細資訊畫面，才能使此選項可用。

* **[!UICONTROL Authorize duplicating]**:此選項允許您激活連結到自定義資源的重複記錄。
* **[!UICONTROL Authorize deleting]**:此選項允許您激活連結到自定義資源的刪除記錄。

