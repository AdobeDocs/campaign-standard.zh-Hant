---
title: 使用區段產生器
description: 瞭解如何使用段生成器建立受眾。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 9a6c542e-10ed-4e77-abb3-36324e1cb38f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 3%

---

# 使用區段產生器 {#using-the-segment-builder}

>[!IMPORTANT]
>
>受眾目標服務當前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

段生成器允許您根據來自的資料定義規則來構建受眾 [即時客戶概要資訊](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)。

本節介紹生成段時的全局概念。 有關段生成器本身的詳細資訊，請參閱 [段生成器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)。

段生成器介面由以下組成：

* 左窗格通過將所需欄位拖放到段生成器工作區中，提供所有可用於生成段的屬性、事件和受眾。
* 中心區域通過定義和組合可用欄位中的規則來提供構建段的工作區。
* 標題和右窗格顯示段的屬性（即段的名稱、說明和估計的限定配置檔案）。

![](assets/aep_audiences_interface.png)

## 構建段

要構建段，請執行以下步驟：

現在，段生成器應顯示在工作區中。 它允許您使用來自Adobe Experience Platform的資料構建一個段，該段最終將用於建立您的受眾。

1. 命名段，然後輸入說明（可選）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 確保在設定窗格中選擇了所需的合併策略。

   有關合併策略的詳細資訊，請參閱 [段生成器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)。

   ![](assets/aep_audiences_mergepolicy.png)

1. 在左窗格中查找所需欄位，並將其拖入中心工作區。

   ![](assets/aep_audiences_dragfield.png)

1. 配置與拖動欄位對應的規則。

   ![](assets/aep_audiences_configure_rules.png)

1. 按一下 **[!UICONTROL Create segment]** 按鈕。

## 查找段的正確欄位

左窗格列出可用於構建規則的所有屬性、事件和訪問群體。

列出的欄位是您的公司捕獲的屬性，已通過 [體驗資料模型(XDM)系統](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)。

將欄位組織為頁籤：

* **[!UICONTROL Attributes]**:可以源自您的Adobe Campaign資料庫和/或Adobe Experience Platform的現有配置檔案屬性。 它們指附於配置檔案的靜態資訊（例如，電子郵件地址、居住國、忠誠計畫狀態等）。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:標識與貴公司客戶接觸點進行過某種互動的消費者的活動，例如「兩週內訂購兩次的任何人」。 這可以從Adobe Analytics流式傳輸，或使用第三方ETL工具直接接收到Adobe Experience Platform。

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**多實體分割** 允許您根據產品、儲存或其他非配置檔案類使用附加資料擴展配置檔案資料。 連接後，來自其他類的資料將變為可用，就好像它們是配置檔案架構的本機資料。
>
>如需詳細資訊，請參閱[專屬文件](https://experienceleague.adobe.com/docs/experience-platform/segmentation/multi-entity-segmentation.html)。

預設情況下，段生成器顯示資料已存在的欄位。 要顯示完整架構，包括沒有資料的欄位，請啟用 **[!UICONTROL Show full XDM schema]** 的子菜單。

![](assets/aep_audiences_populatedfields.png)

每個欄位末尾的符號提供了有關屬性以及如何使用屬性的附加資訊。

![](assets/aep_audiences_isymbol.png)

## 定義段的規則

>[!NOTE]
>
>以下部分提供了有關規則定義的全局資訊。 有關詳細資訊，請參閱 [段生成器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)。

要構建規則，請執行以下步驟：

1. 從左窗格中查找反映規則所基於的屬性或事件的欄位。

1. 將欄位拖到中心工作區上，然後根據所需的段定義對其進行配置。 為此，提供了幾個字串和日期/時間函式。

   在下面的示例中，該規則將針對所有性別等於「男性」的概況。

   ![](assets/aep_audiences_malegender.png)

   自動在 **[!UICONTROL Segment Properties]** 的子菜單。

1. 的 **[!UICONTROL View Profiles]** 按鈕可以預覽與規則對應的前20條記錄，使您能夠快速驗證該段。

   ![](assets/aep_audiences_samplepreview.png)

   您可以根據需要添加盡可能多的附加規則，以針對正確的配置檔案。

   將規則添加到容器時，將用AND邏輯運算子將其附加到任何現有規則。 如果需要，按一下邏輯運算子以修改它。

   ![](assets/aep_audiences_andoperator.png)

一旦連結在一起，這兩條規則就形成一個容器。

## 比較欄位

段生成器允許您比較兩個欄位以定義規則。 例如，家庭地址與工作地址的郵遞區號不同的女性。

要執行此操作，請依照下列步驟執行：

1. 將要比較的第一個欄位（例如，家庭地址郵遞區號）拖到中心工作區。

   ![](assets/aep_audiences_comparing_1.png)

1. 選擇將與第一個欄位進行比較的第二個欄位（例如，工作地址郵遞區號）。

   將其拖動到中心工作區中，該工作區與第一個欄位位於 **[!UICONTROL Drop here to compare operands]** 框。

   ![](assets/aep_audiences_comparing_2.png)

1. 根據需要在兩個欄位之間配置運算子。 在本示例中，我們希望我們的網段以家庭地址不同於工作地址的配置檔案為目標。

   ![](assets/aep_audiences_comparing_3.png)

現在已配置該規則，並準備作為受眾激活。
