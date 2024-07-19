---
title: 在Campaign和Microsoft Dynamics之間同步資料
description: 在Campaign和Dynamics之間同步資料
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 0%

---

# 同步資料

您可以將表格從Microsoft Dynamics 365同步至Campaign，並將促銷活動行銷量度同步至Microsoft Dynamics 365。 同步處理會透過三個專屬的技術工作流程執行： **[!UICONTROL Microsoft Dynamics 365 to Campaign]**、**[!UICONTROL Campaign to Microsoft Dynamics 365]**、**[!UICONTROL Opt-In/Out]**。 請參閱本節，以[瞭解更多](../../integrating/using/d365-acs-self-service-app-workflows.md)。

>[!IMPORTANT]
>您必須停止/啟動&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流程，才能將您的變更列入考量。 [了解更多](../../integrating/using/d365-acs-self-service-app-workflows.md)
>

## 將表格從Microsoft Dynamics 365對應至Campaign

**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;頁面會顯示Microsoft Dynamics 365中的實體清單，以及這些實體將與其同步的Adobe Campaign中的自訂資源。 您可以新增對應、編輯或刪除現有的對應。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

以下是此表格中每個欄的說明：

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**：此欄會識別Microsoft Dynamics 365中的哪個實體將會是對應資料的來源。

* **[!UICONTROL CAMPAIGN TABLE]**：此資料行會識別Adobe Campaign中的哪個資源將會是對應資料的目的地。

* **[!UICONTROL ACTIONS]**：可能的動作如下：

   * 按一下&#x200B;**[!UICONTROL Edit]**&#x200B;圖示以編輯此對應。

   * 使用&#x200B;**[!UICONTROL Delete]**&#x200B;圖示刪除表格對應。

   * 按一下&#x200B;**[!UICONTROL Replay Data]**&#x200B;圖示以重新同步Microsoft Dynamics 365表格中的所有資料。 通常整合應用程式只會同步處理最近變更的Microsoft Dynamics 365資料。  但是，在某些情況下（例如您進行了變更或犯了錯誤），您可能希望重新同步所有資料。  在這些情況下，您可以按一下此按鈕，當您下次停止/啟動&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流程時，您的資料就會開始同步。

     如果您按一下「**[!UICONTROL Replay Data]**」按鈕且檢查成功，圖示將會停用：表示此資料表對應配對的資料將會在下次執行&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流程時重新同步。

     當下列情況為真時，您無法選取重新執行資料：

      * 如果與&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流程相關聯的待處理專案量度中有2,000,000 （或更多）個專案（顯示在&#x200B;**[!UICONTROL Workflows]**&#x200B;頁面中）
      * 如果Microsoft Dynamics 365表格中有2,000,000筆或以上的記錄

     需要重新同步處理的記錄數量不一。 如果您有大量記錄，則可能需要一些時間來完成同步化程式。 當整合應用程式運作以完成同步程式時，請參考&#x200B;**[!UICONTROL Workflows]**&#x200B;頁面中的&#x200B;**[!UICONTROL Backlog]**&#x200B;量度。

     >[!IMPORTANT]
     >
     > 強烈建議您在發佈變更至Adobe Campaign Standard或Microsoft Dynamics 365時停止整合工作流程。 適用的變更包括：更新資源/實體（及其相關欄位）、連結、識別碼欄等。 整合目前正在使用的專案。
     >

## 建立新對應 {#add-a-new-mapping}

若要建立新對應，請遵循下列步驟：

1. 在&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;頁面中，按一下&#x200B;**[!UICONTROL Add New Mapping]**&#x200B;按鈕。

1. 使用下拉式清單來選取要對映的Microsoft Dynamics 365和Campaign表格。
頁面上的大部分其他輸入內容將取決於您選擇的表格。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >您無法對應每個資料表多次。 因此，您會注意到，下拉式清單選項不會包含已對應的表格。

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以確認：應用程式需要一段時間來讀取與所選表格相關的欄位資訊。

然後，您可以繼續對應設定。 [了解更多](#new-mapping-settings)

>[!IMPORTANT]
>
>第一次新增對應時，您只能在此頁面中選擇表格。 在按一下&#x200B;**[!UICONTROL Save]**&#x200B;按鈕之前，請確定您已選取正確的資料表：儲存後，資料表選取欄位將是&#x200B;**唯讀**。

### 編輯現有的對應

如果您編輯現有的對應，則會看到表格選取專案無法編輯。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

這是特意設計的，因為頁面中更下方的輸入內容是根據與這些表格關聯的欄位而定。 變更資料表會使與這些資料表關聯的所有欄位無效。  如果您想要變更要對應的表格，則需要返回上一頁，刪除您要變更的對應，然後新增對應。

### 設定個別表格對應 {#new-mapping-settings}

在本節中，您將瞭解如何設定一個Microsoft Dynamics 365表格與一個Adobe Campaign表格的&#x200B;**單一**&#x200B;對應。

您可以定義下列設定：

* **[!UICONTROL Tables]**：此區段列出Microsoft Dynamics 365表格的名稱，以及此表格將對應至的Campaign表格。
* **[!UICONTROL Field Mappings]**：在[本節](#field-mappings)中瞭解更多
* **[!UICONTROL Field Replacements]**：在[本節](#field-replacements)中瞭解更多
* **[!UICONTROL Filters]**：在[本節](#filters)中瞭解更多
* **[!UICONTROL Advanced Settings]**：在[本節](#advanced-settings)中瞭解更多

### 欄位對應 {#field-mappings}

#### 主索引鍵

將新的Microsoft Dynamics 365新增至Campaign表格對應時，您需要識別ID欄位。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Microsoft Dynamics 365主索引鍵是唯讀的，因為應用程式會偵測到它。

針對Campaign，您需要選取將作為唯一索引鍵的欄位。 它必須設定為[CRM ID自訂資源](../../developing/using/uc-calling-resource-id-key.md)，而且不能有重複專案。

>[!NOTE]
>
>選取&#x200B;**[!UICONTROL Add New Mapping]**&#x200B;後，您只能選擇表格上的識別碼欄位。 如果您按一下編輯按鈕來編輯現有的表格對應，則ID欄位將為唯讀。

主索引鍵永遠是&#x200B;**[!UICONTROL Field Mappings]**&#x200B;區段中列出的第一個欄位名稱。 提醒您，右側會列出下列圖示，提醒您這些是主要索引鍵。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 新增其他欄位對應

**[!UICONTROL Field Mappings]**&#x200B;區段可讓您新增主索引鍵以外的欄位對應。 若要新增從Microsoft Dynamics 365到Adobe Campaign的欄位對應，請按一下&#x200B;**[!UICONTROL Add new field mapping]**&#x200B;按鈕。

選取清單中的Microsoft Dynamics 365和Campaign欄位：

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

這些清單包含與您在頁面頂端選取的Microsoft Dynamics 365和Campaign表格相關聯的欄位名稱。

**[!UICONTROL Apply updates]**&#x200B;切換器可讓您控制此欄位的更新是否會從Microsoft Dynamics 365傳播至Campaign：
* 如果開啟![](assets/do-not-localize/d365-to-acs-icon-switch-on.png)，則Microsoft Dynamics 365中值的更新會在更新發生時傳播至Adobe Campaign。

* 如果您關閉![](assets/do-not-localize/d365-to-acs-icon-switch-off.png)，則會在資料最初載入（或重播）時傳播值，但不會傳播Microsoft Dynamics 365中欄位的增量更新。

>[!NOTE]
>
>按一下&#x200B;**[!UICONTROL Apply updates]**&#x200B;資料行標題以將&#x200B;**所有**&#x200B;的切換更新為開啟或關閉。
>

當您選取欄位值時，您會看到資料型別顯示在下拉式功能表的下方。   將值從一個欄位對應到另一個欄位時，請謹記這一點。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 您無法將多個Microsoft Dynamics 365欄位對應至單一行銷活動欄位。

### 欄位取代 {#field-replacements}

使用&#x200B;**[!UICONTROL Add New Field Replacement]**&#x200B;按鈕來定義新的欄位取代。

欄位取代可讓您識別：

* Microsoft Dynamics 365欄位名稱（已於上方欄位對應區段中新增），
* 現有值(存在於Microsoft Dynamics 365中)，以及
* 要寫入Adobe Campaign的新值

會提供選取清單、分項清單和布林值的下拉式清單。 文字方塊將用於其他字串和數值型別。

### 篩選器 {#filters}

使用&#x200B;**[!UICONTROL Add New Filter]**&#x200B;按鈕來選取將傳播至Campaign的Microsoft Dynamics 365記錄。 您可以選擇與記錄關聯的任何欄位以新增到篩選器（欄位名稱不需要新增到欄位對應）。

您可以填寫下列資訊來指定篩選器：

* Microsoft Dynamics 365欄位名稱
* 比較值，以及
* 值(來自Microsoft Dynamics 365)
如果欄位名稱、比較和值的評估結果為指定記錄為true，則記錄會傳播至Adobe Campaign。

您可以設定標示為&#x200B;**[!UICONTROL Choose the filter comparison operator]**&#x200B;的輸入，來選擇這些篩選的評估方式。  如果您選擇&#x200B;**And**，所有篩選器都必須為true，記錄才會傳播至Campaign。 如果您選擇&#x200B;**或**，如果其中任何一項評估為true，則會傳播記錄。

選項&#x200B;**[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]**&#x200B;控制您是否要從Campaign中刪除已篩選掉的記錄。 如果您選取&#x200B;**否**，則記錄將保留在Adobe Campaign中。 選取&#x200B;**是**&#x200B;讓整合邏輯刪除它們。

>[!NOTE]
>
> 如果未新增篩選器，則所有已修改的記錄都會傳播至Adobe Campaign。
>

### 進階設定 {#advanced-settings}

設定對應時，您可以設定下列其他選項：

* 如果您想要將Microsoft Dynamics 365中發生的刪除專案傳播至Adobe Campaign中的對應欄位（根據欄位名稱對應），請將&#x200B;**[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]**&#x200B;選項設為&#x200B;**是**。 選取&#x200B;**否**&#x200B;以忽略Microsoft Dynamics 365中的刪除。

* 如果您想要將與Microsoft Dynamics 365挑選清單相關聯的顯示值傳播至Campaign，請將&#x200B;**[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]**&#x200B;選項設為&#x200B;**否**。 選取&#x200B;**是**&#x200B;以傳播技術值。

## 同步化行銷活動行銷事件至Microsoft Dynamics 365

**[!UICONTROL Campaign to Microsoft Dynamics 365]**&#x200B;頁面可讓您識別哪些電子郵件行銷事件將會從Adobe Campaign對應至Microsoft Dynamics 365。

您可以控制的四個量度是： **傳送**、**點按**、**開啟**&#x200B;和&#x200B;**跳出**。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

選取&#x200B;**是**&#x200B;以確認您確實希望該型別的事件流入Microsoft Dynamics 365。

按一下[這裡](../../integrating/using/d365-acs-self-service-app-workflows.md)以取得這些電子郵件事件流程的詳細資訊。

## 選擇加入/退出工作流程 {#opt-in-out-wf}

**選擇加入/退出**&#x200B;工作流程可讓您識別Microsoft Dynamics 365與Adobe Campaign之間選擇加入/退出資訊的流程。 這是假設資料與Microsoft Dynamics 365實體「聯絡人」和Adobe Campaign資源「設定檔」相關聯。

深入瞭解[本節](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)中的選擇退出管理。

請記住，您需要按一下「儲存」以儲存您的選擇。 也請記住，您必須停止&#x200B;**Microsoft Dynamics 365**&#x200B;行銷活動的工作流程，然後按一下「播放」整合以合併您的變更。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### 選擇加入/退出同步化方向

以下是同步資料的可用選項清單：

* **[!UICONTROL Disabled]**：選取此選項時，不會在Adobe Campaign和Microsoft Dynamics 365之間移動選擇加入/退出資訊。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**：此選項僅用來將選擇加入/退出從Microsoft Dynamics 365流程到Adobe Campaign。 整合應用程式不會讓您在此畫面中設定流程；請改為按一下&#x200B;**[!UICONTROL Save button]**，並導覽至&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;工作流程。 在此工作流程中，您可以編輯聯絡人/設定檔表格對應，以識別您希望選擇加入/退出欄位對應的方式。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**：此選項會使&#x200B;**對應**&#x200B;區段可見。 這些輸入可讓您定義哪些Adobe Campaign欄位會將資料對應到Microsoft Dynamics 365中的哪些欄位。 這表示如果您剛好在Microsoft Dynamics 365中手動更新某個值，則一旦發生變更，其值將被Adobe Campaign值覆寫。

* **[!UICONTROL Bidirectional]**：此選項會使&#x200B;**對應**&#x200B;區段可見。 這些配對可識別Microsoft Dynamics 365和Adobe Campaign中彼此對應的欄位。 [了解更多](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### 對映

此節僅適用於選擇加入/退出同步化方向欄位設為&#x200B;**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;或&#x200B;**[!UICONTROL Bidirectional]**&#x200B;時。 您可以定義Microsoft Dynamics 365中的哪些欄位對應到Adobe Campaign中的哪些輸入。

Microsoft Dynamics 365欄位名稱包含所有型別&#x200B;**布林值**&#x200B;的欄位名稱。

Adobe Campaign欄位名稱是一組固定的值，專用於選擇加入/退出。 Adobe Campaign欄位名稱是一組固定的值，專用於選擇加入/退出。 **無法變更此清單中的值集**。
