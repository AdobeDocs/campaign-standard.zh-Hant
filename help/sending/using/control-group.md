---
title: 在發送消息時添加控制組
description: 瞭解如何使用Adobe Campaign Standard定義訊息目標時，如何新增控制群組。
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cd38d849052e44e5a50c69d7f8184feb2227fdf4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 添加控制組 {#adding-control-group}

您可以使用控制群組來避免傳送訊息給部分觀眾，以評估促銷活動的影響。

若要在Adobe Campaign中執行此動作，請在定 <b>義傳送目標時</b> ，建立控制群組。 描述檔會隨機新增至控制群組、篩選或不篩選，或根據標準。

然後，您就可以比較收到訊息的目標群體行為與未定位之聯絡人的行為。 您也可以根據傳送記錄，在未來的促銷活動中定位控制群組。

<!--The control group is built when the delivery is prepared.-->

## 概觀 {#overview}

可從主目標隨機提取控制組和／或從特定種群中選擇。 因此，定義控制組的主要方法有兩種：
* **從** main目標擷取多個描述檔。
* **根據** 查詢中定義的條件排除某些配置檔案。

定義控制組時，可以使用這兩種方法。

在交付準備步驟中屬於控制組的所有配置檔案都將從主目標中刪除。 一旦傳送訊息，他們就不會收到。

## 從目標人口中提取 {#extraction-target-population}

若要定義控制群組，您可以選擇隨機或根據排序、百分比或固定數目的設定檔從目標人口中擷取。

### 目標提取 {#target-extraction}

首先，定義從目標中提取描述檔的方式： **隨機** 或根據排序 **而定**。

在該部 **[!UICONTROL Target extraction]** 分下，選擇以下選項之一：

* **[!UICONTROL Random sampling]**:在準備傳送時，Adobe Campaign會隨機擷取一些描述檔，這些描述檔對應您要設定的百分比或最大數目做為 [大小限制](#size-limit)。

   例如，如果您接著在區段中將臨界值設為10, **[!UICONTROL Limits]** 則控制群組將從目標群組隨機選取10%。<!--Change screenshot to match example)-->

   ![](assets/control-group-random-sampling.png)

* **[!UICONTROL Keep only the first records after sorting]**:此選項可讓您根據一或多個排序順序定義限制。

   例如：

   * 選擇字 **[!UICONTROL Age]** 段作為排序標準。
   * 將100定義為區段中的臨 **[!UICONTROL Limits]** 界值(請參閱 [大小限制](#size-limit))。
   * 保留選 **[!UICONTROL Descending sort]** 項為選中狀態。

   因此，控制組將由100個最舊的接收者組成。<!--Change screenshot to match example)-->

   ![](assets/control-group-keep-first-records.png)

   定義控制群組（包含進行少量或頻繁購買的設定檔），並比較其行為與已聯絡收件者的行為，這可能會很有趣。

>[!NOTE]
>
>如果 **[!UICONTROL No extraction]** 您不想使用選項，請選 **[!UICONTROL Target extraction]** 取。

<!--![](assets/control-group-no-extraction.png)-->

### 大小限制 {#size-limit}

無論您選 **[!UICONTROL Random sampling]** 取或 **[!UICONTROL Keep only the first records after sorting]**&#x200B;是選取，您都必須設定如何限制從主目標擷取的描述檔數目。 執行下列任一項作業：

* 選取 **[!UICONTROL Size (as a % of the initial population)]** 並填入對應的影格。

   例如，如果您設定10，則Adobe Campaign會：
   * 隨機擷取目標人口的10%。
   * 如果您選取欄 **[!UICONTROL Age]** 位作為排序標準，請從目標人口中擷取最舊10%的描述檔。

   >[!NOTE]
   >
   >如果取消選 **[!UICONTROL Descending sort]** 項，則會提取10%最年輕的配置檔案。

* 選取 **[!UICONTROL Maximum size]** 並填入對應的影格。

   例如，如果您設定100,Adobe Campaign將會：
   * 從目標人口中隨機擷取100個描述檔。
   * 如果您選取欄 **[!UICONTROL Age]** 位作為排序標準，請從目標人口中擷取100個最舊的描述檔。

   >[!NOTE]
   >
   >如果取消選 **[!UICONTROL Descending sort]** 項，則會提取100個最年輕的配置檔案。

## 排除特定人口 {#excluding-specific-population}

另一個定義控制群組的方法是使用查詢從目標中排除特定人口族群。

操作步驟：

1. From the **[!UICONTROL Target exclusion]** section, click **[!UICONTROL Define target exclusion]**.

   ![](assets/control-group-define-target-exclusion.png)

1. 使用查詢編輯器定義排 [除條件](../../automating/using/editing-queries.md)。 您也可以選取先 [前建立](../../audiences/using/about-audiences.md) 的對象。

   ![](assets/control-group-target-exclusion.png)

1. 按一下 **[!UICONTROL Confirm]**。

與查詢結果匹配的配置檔案將從目標中排除。

<!--For more on using the query editor, see the [Editing queries](../../automating/using/editing-queries.md) section.-->

## 使用案例：設定控制組 {#control-group-example}

以下範例說明如何使用這兩種方法定義控制群組：從主要目標擷取描述檔，並使用查詢排除特定人口族群。

1. 建立工作流程. [建立工作流](../../automating/using/building-a-workflow.md)區段中會列出建立工作流程的詳細步驟。
1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放 [](../../automating/using/query.md) Query活動。 連按兩下活動並定義您的目標。 <!--For example, in **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profile]**, select **[!UICONTROL Age]** with the operator **[!UICONTROL Greater than]** and type 25 in the **[!UICONTROL Value]** field.-->

1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Channels]**&#x200B;中，拖放主要目標區段之 [後的「電子郵件傳送](../../automating/using/email-delivery.md) 」活動並加以編輯。
1. 按一下傳 **[!UICONTROL Audience]** 送控制面板中的區塊。

1. 選取 **[!UICONTROL Control group]** 索引標籤。

   ![](assets/control-group-tab.png)

1. 從節 **[!UICONTROL Target extraction]** 中選擇 **[!UICONTROL Keep only the first records after sorting]**。
1. 依年齡排序，並保留排序 **[!UICONTROL Descending]** 選項為勾選。

   ![](assets/control-group-sorting-column.png)

1. 將100設為最大大小。 將提取目標中最舊的100個配置檔案。

1. 在區段 **[!UICONTROL Target exclusion]** 中，根據您使用查詢編輯器選擇的准則，定義將從目標中排除的描述 [檔](../../automating/using/editing-queries.md)。 例如，「年齡小於20歲」。

   ![](assets/control-group-target-exclusion-example.png)

   年齡低於20歲的描述檔將被排除。

1. 啟動 [傳送準備](../../sending/using/preparing-the-send.md) , [並確認傳送](../../sending/using/confirming-the-send.md)。

提取的描述檔（100個最舊的描述檔）和根據查詢定義的描述檔（20下的描述檔）將從主目標中撤回。 他們不會收到訊息。

## 比較結果 {#delivery-logs}

既然您已將傳送內容傳送，您可以對控制群組做什麼？

您可以提取發 **送日誌** ，以比較未接收通信的控制組與有效目標的操作方式。 您也可以使用傳送記錄檔來建 **立另一個定位**。

>[!IMPORTANT]
>
>您必須擁有管 [理員角色](../../administration/using/users-management.md#functional-administrators) ，並成為組織單 **[!UICONTROL All]** 位的一 [員](../../administration/using/organizational-units.md) ，才能連線至Adobe Campaign。 如果您想要限制特定使用者或使用者群組的存取權，請勿將其連結至 **[!UICONTROL All]** 能夠存取傳送記錄的裝置。

### 檢查傳送記錄檔 {#checking-logs}

要查看消息發送後哪些配置檔案已從目標中刪除，請檢查 **[!UICONTROL Delivery logs]**。 如需傳送記錄檔的詳細資訊以及如何存取記錄檔，請參 [閱本節](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

* 在標籤中 **[!UICONTROL Sending logs]** ，您可以看到已提取和排除的配置檔案。 他們擁有 **[!UICONTROL Ignored]** 失敗 **[!UICONTROL Control group]** 的地位和原因。

   ![](assets/control-group-sending-logs.png)

* 您也可以檢查標 **[!UICONTROL Exclusion causes]** 簽，查看傳送中未包含的描述檔數目。

   ![](assets/control-group-exclusion-causes.png)

### 使用控制組日誌 {#using-logs}

傳送後，您可以使用傳送記錄來篩選未收到訊息的描述檔。 請遵循下列步驟：

1. 建立工作流程. [建立工作流](../../automating/using/building-a-workflow.md)區段中會列出建立工作流程的詳細步驟。
1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放 [](../../automating/using/query.md) Query活動。
1. 在標 **[!UICONTROL Properties]** 簽中，設 **[!UICONTROL Delivery logs]** 置為 **[!UICONTROL Resource]** 和 **[!UICONTROL Profile]** 作為 **[!UICONTROL Targeting dimension]**。

   ![](assets/control-group-delivery-properties.png)

1. 在 **[!UICONTROL Target]** 索引標籤中，按一下 **[!UICONTROL Delivery logs]**。
1. 拖放並選 **[!UICONTROL Status]** 取為 **[!UICONTROL Ignored]** 篩選條件。

   ![](assets/control-group-status-ignored.png)

1. 按一下 **[!UICONTROL Confirm]**。

1. 仍然在標 **[!UICONTROL Target]** 簽中，拖放並選 **[!UICONTROL Nature of failure]** 取 **[!UICONTROL Control group]** 作為篩選條件。

   ![](assets/control-group-nature-of-failure.png)

1. 按一下 **[!UICONTROL Confirm]**。

   ![](assets/control-group-delivery-target.png)

然後，您可以使用Extract檔案活動和 **Transfer檔案活動** (例如 **** )導出日誌資料。 這可讓您在自己的報告工具中，與控制群組相比，分析有效目標上的促銷活動結果。 For more on exporting logs, see [this section](../../automating/using/exporting-logs.md).

### 定位控制群組 {#targeting-control-group}

若要根據未收到訊息的描述檔進行定位，您也可以使用傳送記錄檔。 請遵循下列步驟：

1. 建立工作流程. [建立工作流](../../automating/using/building-a-workflow.md)區段中會列出建立工作流程的詳細步驟。
1. 在 **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**&#x200B;中，拖放第一個 [](../../automating/using/query.md) 查詢活動。
1. 在標 **[!UICONTROL Properties]** 簽中，確保選 **[!UICONTROL Profile]** 擇資源作為和 **[!UICONTROL Resource]** 。 **[!UICONTROL Targeting dimension]**

   ![](assets/control-group-delivery-properties-profile.png)

1. 在標籤 **[!UICONTROL Target]** 中，展開 **[!UICONTROL Delivery]** 並拖放 **[!UICONTROL Delivery logs]**。

   ![](assets/control-group-query-delivery-logs.png)

1. 在視窗 **[!UICONTROL Add a rule]** 中，拖放 **[!UICONTROL Delivery]**。

   ![](assets/control-group-rule-delivery.png)

1. 選擇您傳送的電子郵件作為篩選條件。 按一下 **[!UICONTROL Confirm]**。

   ![](assets/control-group-email-sent.png)

1. 返回窗 **[!UICONTROL Add a rule]** 口，拖放並選 **[!UICONTROL Status]** 擇 **[!UICONTROL Ignored]** 作為篩選條件。 按一下 **[!UICONTROL Confirm]**。

   ![](assets/control-group-status-ignored.png)

1. 拖放並選 **[!UICONTROL Nature of failure]** 取為 **[!UICONTROL Control group]** 篩選條件。 按一下 **[!UICONTROL Confirm]**。

   ![](assets/control-group-nature-of-failure.png)

1. 請確定條件都與 **AND** Boolean運算子對齊。

   ![](assets/control-group-delivery-logs-conditions.png)

1. 按一下 **[!UICONTROL Confirm]**。

您現在可以定位未收到第一則訊息的描述檔，因為這些描述檔是控制群組的一部分，並傳送另一封電子郵件給他們。

在相同的工作流程中，您也可以建立另一個查詢來定位已收到電子郵件的描述檔，並傳送不同的訊息給他們。

![](assets/control-group-targeted-by-delivery.png)