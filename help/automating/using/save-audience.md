---
title: 儲存閱聽眾
description: 「儲存對象」活動可讓您更新現有對象，或從工作流程上游計算的人口中建立新對象。
page-status-flag: 從未激活
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 定位活動
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 儲存閱聽眾{#save-audience}

## 說明 {#description}

![](assets/save_audience.png)

此活 **[!UICONTROL Save audience]** 動可讓您更新現有對象，或從工作流程上游計算的人口中建立新對象。 從此活動建立或更新的對象為「清 **單** 」 **或「檔案** 」對象。 它們會新增至應用程式對象清單，並透過功能表提供 **[!UICONTROL Audiences]** 使用。

>[!NOTE]
>
>如果透過活動建立的 **[!UICONTROL Save audience]** 觀眾已經豐富了其他資料，您將無法使用這些資料來個人化獨立傳送。 它們只能從在工作流程中執行的傳送中使用。

此活動也可讓您將描述檔匯出為Adobe Experience cloud觀眾／區段。 如此一來，您便可在其他Adobe Experience cloud解決方案中利用這些受眾。 如需共用觀眾的詳細資訊，請參 [閱使用促銷活動和人員核心服務](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。

## 使用內容 {#context-of-use}

此活 **[!UICONTROL Save audience]** 動主要用於將人口族群轉換為可重複使用的觀眾，讓人口族群在相同的工作流程中計算。

## 配置 {#configuration}

1. 將活動 **[!UICONTROL Save audience]** 拖放至工作流程中。
1. 在其他定位活動（例如查詢、交叉點、聯合或排除）之後進行連接。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 選擇要執行的操作：

   * **[!UICONTROL Update an existing audience]**:選取現有對象，然後選擇更新類型：

      * **[!UICONTROL Replace audience content with new data]**:整個觀眾內容都會被取代。 舊資料丟失。 僅保留儲存觀眾活動之傳入轉場的資料。
      * **[!UICONTROL Complete audience with new data]**:保留舊的觀眾資料，並新增儲存觀眾活動傳入轉場的資料。
   * **[!UICONTROL Create then update an audience]**:輸入對象名稱並選擇更新類型。 如果對象尚未存在，則會建立它。 如果已存在，則會根據所選模式更新：

      * **[!UICONTROL Replace audience content with new data]**:整個觀眾內容都會被取代。 舊資料丟失。 僅保留儲存觀眾活動之傳入轉場的資料。

         警告：此選項會清除已更新對象的對象類型和定位維度。

      * **[!UICONTROL Complete audience with new data]**:保留舊的觀眾資料，並新增儲存觀眾活動傳入轉場的資料。

         警告：如果更新對象的對象類型或目標維度與工作流程的目前設定不相容，此選項會造成錯誤。 例如，您無法使用來自查詢的設定檔來完成檔案類型對象。
   * **[!UICONTROL Create a new audience]**:輸入要建立的對象名稱。 建立觀眾的時間和日期會自動新增至觀眾名稱。 如此一來，每次執行工作流程時，觀眾都會變得獨特。
   * **[!UICONTROL Share in Adobe Experience Cloud]**:如果您有目標設定檔，而您想要將觀眾匯出至Adobe Experience Cloud，請選取此選項，然後選取現有的共用觀眾或建立新觀眾。

      同時選取與 **[!UICONTROL Shared Data source]** 觀眾中所含資料的資源對應的資料，以便在Adobe Experience cloud中正確調節資料。

      使用此選項，共用的觀眾不會新增至功能表中可用的Adobe Campaign觀眾清 **[!UICONTROL Audiences]** 單。

      >[!NOTE]
      >
      >只有在管理員已設定Adobe Experience cloud的共用觀眾功能時，才可使用此選項。 如需詳細資訊，請參 [閱使用促銷活動和人員核心服務](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)。
   更新期間儲存或可用的對象類型取決於工作流程上游的活動。

   如果觀眾的定位維度在儲存時未知（例如，如果來自匯入的檔案），則會建立或更新觀眾為類型觀 **[!UICONTROL File]** 眾。

   如果儲存時已定義儲存對象的定位維度（例如，如果來自定位、查詢後等），則會將對象儲存或更新為類型對 **[!UICONTROL List]** 像。

   接著，儲存的觀眾內容便可在觀眾的詳細資料檢視中取用，您可從選單存取該 **[!UICONTROL Audiences]** 內容。 此視圖中可用的列對應於工作流保存對象活動的傳入過渡的列。 例如：讀入檔案的欄、從查詢新增的其他資料。

1. 確認活動的設定並儲存工作流程。

## Example {#example}

此範例中定義的工作流程會顯示定期的受眾更新，以利鎖定：

* 它會使用 **[!UICONTROL Scheduler]**
* 您可以使用 **[!UICONTROL Query]** 恢復所有預訂到可用不同應用程式服務的配置檔案。
* 活 **[!UICONTROL Save audience]** 動會刪除自上次工作流程執行以來已從服務取消訂閱的描述檔，並新增新訂閱的描述檔，以更新觀眾。

![](assets/save_audience_example_1.png)

活動 **[!UICONTROL Save audience]** 的配置如下：

![](assets/save_audience_example_2.png)

