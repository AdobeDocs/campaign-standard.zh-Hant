---
title: 使用統一的區段產生器
description: 瞭解如何使用「統一區段產生器」來建立觀眾。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 17545fc4ea58e5220c66f90eafcbfcfca50bf661

---


# 使用統一的區段產生器 {#using-the-unified-segment-builder}

>[!IMPORTANT]
>
>觀眾目標服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

「統一區段產生器」可讓您根據來自「統一描述檔服務」的資料定義規則，以建立 [觀眾群](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)。

本節介紹建立區段時的全域概念。 如需「統一區段產生器」本身的詳細資訊，請參閱「區 [段產生器」使用指南](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

「統一區段產生器」介面的組成如下：

* 左側窗格會將所需欄位拖放至區段產生器工作區，以提供建立區段的所有屬性、事件和對象。
* 中心區域提供工作區，可從可用欄位定義並結合規則來建立區段。
* 標題和右窗格會顯示區段的屬性（例如，名稱、說明和區段的估計合格設定檔）。

![](assets/aep_audiences_interface.png)

## 建立區段

若要建立區段，請遵循下列步驟：

「統一區段產生器」現在應會顯示在您的工作區中。 它可讓您使用Adobe Experience platform中的資料來建立細分，這些資料最終將用來建立您的觀眾。

1. 命名區段，然後輸入說明（選用）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 請確定在設定窗格中已選取所要的合併原則。

   如需合併原則的詳細資訊，請參閱「區段產生器」使用指南中 [的專屬章節](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)

   ![](assets/aep_audiences_mergepolicy.png)

1. 在左窗格中尋找所要的欄位，並將它們拖曳至中心工作區。

   ![](assets/aep_audiences_dragfield.png)

1. 設定與拖曳欄位對應的規則。

   ![](assets/aep_audiences_configure_rules.png)

1. Click the **[!UICONTROL Create segment]**button.

## 尋找區段的正確欄位

左窗格列出可用於建構規則的所有屬性、事件和對象。

列出的欄位是您公司擷取的屬性，可透過 [Experience Data Model(XDM)系統使用](https://www.adobe.io/apis/experienceplatform/home/xdm.html)。

欄位會組織成標籤：

* **[!UICONTROL Attributes]**:現有的描述檔屬性，可能源自您的Adobe Campaign資料庫和／或Adobe Experience Platform。 它們指附加至描述檔的靜態資訊（例如電子郵件地址、居住國家、忠誠度方案狀態等）。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:識別與您公司客戶觸點有互動的消費者的活動，例如「兩週內訂購兩次的任何人」。 這可從Adobe Analytics串流，或使用協力廠商的ETL工具直接吸收到Adobe Experience Platform。

   ![](assets/aep_audiences_eventstab.png)

依預設，「統一區段產生器」會顯示資料所在的欄位。 要顯示完整方案，包括沒有資料的欄位，請啟用設 **[!UICONTROL Show full XDM schema]**置中的選項。

![](assets/aep_audiences_populatedfields.png)

每個欄位結尾的符號會提供屬性及其使用方式的其他資訊。

![](assets/aep_audiences_isymbol.png)

## 定義區段規則

>[!NOTE]
>
>下節提供規則定義的全域資訊。 如需詳細資訊，請參閱「區段產生 [器」使用指南](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

若要建立規則，請遵循下列步驟：

1. 從左窗格尋找反映規則所依據之屬性或事件的欄位。

1. 將欄位拖曳至中心工作區，然後根據所要的區段定義加以設定。 若要這麼做，可使用數個字串和日期／時間函式。

   在下列範例中，規則會將性別等於「男性」的所有描述檔定位。

   ![](assets/aep_audiences_malegender.png)

   區段中自動重新計算與區段對應的估計人口 **[!UICONTROL Segment Properties]**數。

1. 按 **[!UICONTROL View Profiles]**鈕可讓您預覽與規則對應的前20個記錄，讓您快速驗證區段。

   ![](assets/aep_audiences_samplepreview.png)

   您可以視需要新增任意數量的其他規則，以定位正確的描述檔。

   將規則新增至容器時，規則會附加至具有AND運算子的任何現有規則。 按一下運算子以存取選項，將其變更為OR。

   ![](assets/aep_audiences_andoperator.png)

連結在一起後，這兩個規則就會形成容器。

## 比較欄位

「統一區段產生器」可讓您比較兩個欄位以定義規則。 例如，其家鄉地址與工作地址的郵遞區號不同的女性。

若要這麼做，請依照下列步驟進行：

1. 將您要比較的第一個欄位（例如，首頁位址郵遞區號）拖曳至中心工作區。

   ![](assets/aep_audiences_comparing_1.png)

1. 選擇將與第一個欄位進行比較的第二個欄位（例如工作地址郵遞區號）。

   將它拖曳至方塊中第一個欄位所在的容器中的中心工作區 **[!UICONTROL Drop here to compare operands]**上。

   ![](assets/aep_audiences_comparing_2.png)

1. 視需要在兩個欄位之間設定運算子。 在此範例中，我們的區段要求家庭地址郵遞區號不等於工作地址1。

   ![](assets/aep_audiences_comparing_3.png)

規則現在已設定，並可立即啟動為觀眾。
