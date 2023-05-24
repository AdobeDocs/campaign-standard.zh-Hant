---
title: 在市場活動和Microsoft動態之間同步資料
description: 在市場活動和Dynamics之間同步資料
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
source-wordcount: '1795'
ht-degree: 0%

---

# 同步資料

您可以將表從MicrosoftDynamics 365同步到市場活動和市場活動市場營銷指標到MicrosoftDynamics 365。 同步通過三個專用的技術工作流執行： **[!UICONTROL Microsoft Dynamics 365 to Campaign]**。 **[!UICONTROL Campaign to Microsoft Dynamics 365]**。 **[!UICONTROL Opt-In/Out]**。 請參閱本節以 [瞭解更多](../../integrating/using/d365-acs-self-service-app-workflows.md)。

>[!IMPORTANT]
>您需要停止/啟動 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流，以便將您的更改考慮在內。 [了解更多](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 將MicrosoftDynamics 365中的表映射到市場活動

的 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 頁面顯示了MicrosoftDynamics 365中的實體及其與之同步的Adobe Campaign中的自定義資源的清單。 可以添加新映射、編輯或刪除現有映射。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

下面是此表中各列的說明：

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**:此列標識MicrosoftDynamics 365中的哪個實體將是映射的資料源。

* **[!UICONTROL CAMPAIGN TABLE]**:此列標識Adobe Campaign中哪個資源將是映射的資料目標。

* **[!UICONTROL ACTIONS]**:下面列出了可能的操作：

   * 按一下 **[!UICONTROL Edit]** 表徵圖可編輯此映射。

   * 使用  **[!UICONTROL Delete]** 表徵圖以刪除表格映射。

   * 按一下 **[!UICONTROL Replay Data]** 表徵圖，重新同步MicrosoftDynamics 365表中的所有資料。 通常，整合應用程式只同步最近更改的MicrosoftDynamics 365中的資料。  但是，在某些情況下（例如，您做了更改或犯了錯誤），您可能希望所有資料都重新同步。  在這些情況下，按一下此按鈕，下次停止/啟動 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流，您的資料將開始同步。

      如果按一下 **[!UICONTROL Replay Data]** 按鈕，檢查成功，表徵圖將被禁用：它表示此表映射對的資料將與下次執行 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流。

      當以下情況為true時，不能選擇重播資料：

      * 如果「積壓」度量中有2,000,000（或更多）項與 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流(顯示在 **[!UICONTROL Workflows]** 頁)
      * 如果MicrosoftDynamics 365表中有2,000,000或更多記錄

      需要重新同步的記錄數量不同。 如果您有大量記錄，則完成同步過程可能需要一些時間。 請參閱 **[!UICONTROL Backlog]** 度量 **[!UICONTROL Workflows]** 頁面。

      >[!IMPORTANT]
      >
      > 強烈建議在發佈對Adobe Campaign Standard或MicrosoftDynamics 365的更改時停止整合工作流。 適用的更改包括：資源/實體（及其關聯欄位）、連結、標識符列等的更新。 目前正被整合使用。


## 建立新映射 {#add-a-new-mapping}

要建立新映射，請執行以下步驟：

1. 的 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 的 **[!UICONTROL Add New Mapping]** 按鈕

1. 使用下拉清單選擇要映射的MicrosoftDynamics 365和市場活動表。
頁面上的大多數其他輸入將取決於您選擇的表。

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >不能多次映射每個表。 因此，您將注意到下拉清單選擇將不包括已映射的表。

1. 按一下 **[!UICONTROL OK]** 確認：應用程式需要一個短暫的時間來閱讀與所選表關聯的欄位資訊。

然後，可以繼續映射配置。 [了解更多](#new-mapping-settings)

>[!IMPORTANT]
>
>只有在首次添加映射時，才能選擇此頁中的表。 在按一下 **[!UICONTROL Save]** 按鈕：保存後，表選擇欄位將 **只讀**。

### 編輯現有映射

如果編輯現有映射，則將看到表選擇不可編輯。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

這是按照設計進行的，因為頁面中進一步向下的輸入基於與這些表關聯的欄位。 更改表會使與這些表關聯的所有欄位無效。  如果要將表更改為映射，則需要返回到上一頁，刪除要更改的映射，並添加新映射。

### 配置單個表映射 {#new-mapping-settings}

在本節中，您將學習如何配置 **單** 將一個Microsoft動力365表映射到一個Adobe Campaign表。

可以定義以下設定：

* **[!UICONTROL Tables]**:本節列出了MicrosoftDynamics 365表的名稱和將映射到的市場活動表。
* **[!UICONTROL Field Mappings]**:瞭解詳情 [此部分](#field-mappings)
* **[!UICONTROL Field Replacements]**:瞭解詳情 [此部分](#field-replacements)
* **[!UICONTROL Filters]**:瞭解詳情 [此部分](#filters)
* **[!UICONTROL Advanced Settings]**:瞭解詳情 [此部分](#advanced-settings)

### 欄位映射 {#field-mappings}

#### 主鍵

將新的MicrosoftDynamics 365添加到市場活動表映射時，需要標識ID欄位。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

MicrosoftDynamics 365主鍵是只讀的，因為應用程式將檢測到它。

對於「市場活動」，您需要選擇哪個欄位將是唯一鍵。 它必須配置為 [CRM ID自定義資源](../../developing/using/uc-calling-resource-id-key.md) 不能有重複項。

>[!NOTE]
>
>只有在選擇後，才能選擇表上的ID欄位 **[!UICONTROL Add New Mapping]**。 如果按一下編輯按鈕編輯現有表映射，則ID欄位將為只讀。

主鍵將始終是 **[!UICONTROL Field Mappings]** 的子菜單。 作為提醒，右側列出了以下表徵圖，以提醒您這些是主鍵。

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### 添加其他欄位映射

的 **[!UICONTROL Field Mappings]** 部分允許您添加除主鍵之外的欄位映射。 要添加從MicrosoftDynamics 365到Adobe Campaign的欄位的新映射，請按一下 **[!UICONTROL Add new field mapping]** 按鈕

在清單中選擇「Microsoft動態365」和「市場活動」欄位：

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

這些清單包含與您在頁面頂部選擇的MicrosoftDynamics 365和市場活動表關聯的欄位名。

的 **[!UICONTROL Apply updates]** switcher允許您控制是否將此欄位的更新從MicrosoftDynamics 365傳播到市場活動：
* 如果已開啟 ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png)，對MicrosoftDynamics 365中值的更新將在更新發生時傳播到Adobe Campaign。

* 如果你關掉了 ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png)，當初始載入（或重播）資料時，將傳播該值，但不會傳播對MicrosoftDynamics 365中欄位的增量更新。

>[!NOTE]
>
>按一下 **[!UICONTROL Apply updates]** 列標題以更新 **全部** 開啟或關閉開關。

選擇欄位值時，您將看到下拉菜單下方顯示的資料類型。   在將值從一個欄位映射到另一個欄位時，應牢記這一點。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> 不能將多個MicrosoftDynamics 365欄位映射到單個市場活動欄位。

### 現場替換 {#field-replacements}

使用 **[!UICONTROL Add New Field Replacement]** 按鈕。

現場替換允許您標識：

* aMicrosoftDynamics 365欄位名稱（已在欄位映射部分上面添加）,
* 現有值(存在於MicrosoftDynamics 365中),
* 寫給Adobe Campaign的新價值

將為picklist 、 enumeration和boolean值提供下拉清單。 文本框將用於其他字串和數字類型。

### 篩選 {#filters}

使用 **[!UICONTROL Add New Filter]** 按鈕，選擇將哪些MicrosoftDynamics 365記錄傳播到市場活動。 您可以選擇與記錄關聯的任何欄位以添加到篩選器（不需要將欄位名稱添加到欄位映射）。

通過填寫以下資訊來指定篩選器：

* MicrosoftDynamics 365欄位名
* 比較值，
* a值(來自MicrosoftDynamics 365)如果給定記錄的欄位名稱、比較和值的計算結果為true，則記錄將傳播到Adobe Campaign。

通過設定已標籤的輸入，可以選擇如何評估這些篩選器 **[!UICONTROL Choose the filter comparison operator]**。  如果您選擇 **和**，要將記錄傳播到「市場活動」，所有篩選器必須為真。 如果您選擇 **或**，如果其中任何一條計算為true，則將傳播該記錄。

選項 **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** 控制是否希望從「市場活動」中刪除已過濾出的記錄。 如果選擇 **否** 記錄將保留在Adobe Campaign。 選擇 **是** 讓它們被整合邏輯刪除。

>[!NOTE]
>
> 如果未添加篩選器，則所有已修改的記錄都將傳播到Adobe Campaign。

### 高級設定 {#advanced-settings}

配置映射時，可以設定以下附加選項：

* 設定 **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** 選項 **是**，如果要將在MicrosoftDynamics 365中發生的刪除內容傳播到Adobe Campaign的相應欄位（基於欄位名稱映射）。 選擇 **否** 忽略Microsoft動力365的刪除。

* 設定 **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** 選項 **否** 如果要傳播到「市場活動」，則顯示值與MicrosoftDynamics 365選取清單關聯。 選擇 **是** 傳播技術價值。

## 將市場活動營銷活動同步到MicrosoftDynamics 365

的 **[!UICONTROL Campaign to Microsoft Dynamics 365]** 頁面允許您確定哪些電子郵件營銷活動將從Adobe Campaign映射到MicrosoftDynamics 365。

您可以控制的四個指標是： **發送**。 **按一下**。 **開啟**, **邊界**。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

選擇 **是** 確認您確實希望此類型的事件流到MicrosoftDynamics 365。

按一下 [這裡](../../integrating/using/d365-acs-self-service-app-workflows.md) 的子菜單。

## 選擇加入/退出工作流 {#opt-in-out-wf}

的 **選擇加入/退出** 工作流允許您確定MicrosoftDynamics 365和Adobe Campaign之間的選擇加入/退出資訊流。 這假定資料與MicrosoftDynamics 365實體&quot;contact&quot;和Adobe Campaign資源&quot;profile&quot;相關聯。

瞭解有關Opt-out管理的詳細資訊 [此部分](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out)。

請記住，您需要按一下「保存」以保存您的選擇。 還要記住，你必須阻止 **Microsoft動力365戰役** 工作流，然後按一下「播放」進行整合以合併您所做的更改。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### 選擇進/出同步方向

以下是用於同步資料的可用選項清單：

* **[!UICONTROL Disabled]**:選擇此選項時，不會在Adobe Campaign和MicrosoftDynamics 365之間移動選擇加入/退出資訊。

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**:此選項僅用於從MicrosoftDynamics 365流入/退出Adobe Campaign。 整合應用程式不允許您在此螢幕中配置流；而按一下 **[!UICONTROL Save button]**，並導航至 **[!UICONTROL Microsoft Dynamics 365 to Campaign]** 工作流。 在此工作流中，您可以編輯聯繫人/配置檔案表映射，以確定希望選擇加入/退出欄位映射的方式。

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**:此選項將使 **映射** 的子菜單。 這些輸入將允許您定義哪些Adobe Campaign欄位將資料映射到MicrosoftDynamics 365中哪些欄位。 這意味著，如果您碰巧在MicrosoftDynamics 365中手動更新值，則其值將被Adobe Campaign值覆蓋（如果它碰巧發生更改）。

* **[!UICONTROL Bidirectional]**:此選項將使 **映射** 的子菜單。 這些對將確定Microsoft動力365和Adobe Campaign的哪些欄位將相互映射。 [了解更多](../../integrating/using/d365-acs-notices-and-recommendations.md)。

### 映射

此部分僅在「選擇加入/退出同步方向」欄位設定為時適用 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** 或 **[!UICONTROL Bidirectional]**。 您可以定義MicrosoftDynamics 365中哪些欄位映射到Adobe Campaign中的輸入。

MicrosoftDynamics 365欄位名稱包括所有類型 **布爾**。

Adobe Campaign欄位名稱是一組特定於選擇加入/退出的固定值。 Adobe Campaign欄位名稱是一組特定於選擇加入/退出的固定值。 **無法更改此清單中的值集**。
