---
title: 使用區段產生器
description: 瞭解如何使用區段產生器建立受眾。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 9a6c542e-10ed-4e77-abb3-36324e1cb38f
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 3%

---

# 使用區段產生器 {#using-the-segment-builder}

>[!IMPORTANT]
>
>Audience Destinations服務目前為測試版，可能會經常更新，恕不另行通知。 客戶需在Azure上代管（目前僅限北美地區使用Beta版）才能存取這些功能。 如果您想要存取許可權，請聯絡Adobe客戶服務。

區段產生器可讓您根據來自[即時客戶個人檔案](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)的資料定義規則，藉此建立對象。

本節介紹建立區段時的全域概念。 如需區段產生器本身的詳細資訊，請參閱[區段產生器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)。

「區段產生器」介面的組成如下：

* 左窗格將所有屬性、事件和對象拖放至區段產生器工作區，以便建立區段。
* 中央區域會提供一個工作區，讓您藉由定義並結合可用欄位中的規則來建立區段。
* 標題和右側窗格會顯示區段的屬性（即名稱、說明，以及區段的預估合格設定檔）。

![](assets/aep_audiences_interface.png)

## 建立區段

若要建立區段，請依照下列步驟進行：

區段產生器現在應該會顯示在您的工作區中。 它可讓您使用Adobe Experience Platform的資料來建立區段，這些資料最終將用來建立您的對象。

1. 為區段命名，然後輸入說明（選擇性）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 確保在設定窗格中選取所需的合併原則。

   如需合併原則的詳細資訊，請參閱[區段產生器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)中的專屬章節。

   ![](assets/aep_audiences_mergepolicy.png)

1. 在左窗格中尋找所需的欄位，並將其拖曳至中央工作區。

   ![](assets/aep_audiences_dragfield.png)

1. 設定與拖曳欄位對應的規則。

   ![](assets/aep_audiences_configure_rules.png)

1. 按一下 **[!UICONTROL Create segment]** 按鈕。

## 尋找區段的正確欄位

左窗格會列出可用來建構規則的所有屬性、事件和對象。

列出的欄位是貴公司擷取的屬性，並已透過[體驗資料模型(XDM)系統](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)提供。

欄位會整理為索引標籤：

* **[!UICONTROL Attributes]**：現有的設定檔屬性，可以源自您的Adobe Campaign資料庫和/或Adobe Experience Platform。 他們是指附加至設定檔的靜態資訊（例如電子郵件地址、居住國家/地區、忠誠計畫狀態等）。

  ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**：識別與您公司的客戶接觸點有所互動的消費者的活動，例如「兩週內訂購兩次的任何人」。 您可以從Adobe Analytics串流處理或使用協力廠商ETL工具直接擷取至Adobe Experience Platform。

  ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**多實體分段**&#x200B;可讓您根據產品、商店或其他非設定檔類別，以其他資料擴充設定檔資料。 連線後，其他類別的資料將變得可用，就好像它們是設定檔結構描述的原生資料。
>
>如需詳細資訊，請參閱[專屬文件](https://experienceleague.adobe.com/docs/experience-platform/segmentation/multi-entity-segmentation.html)。

依預設，區段產生器會顯示已有資料存在的欄位。 若要顯示完整結構描述，包括資料不存在的欄位，請從設定中啟用&#x200B;**[!UICONTROL Show full XDM schema]**&#x200B;選項。

![](assets/aep_audiences_populatedfields.png)

每個欄位結尾的符號提供有關屬性及其使用方式的其他資訊。

![](assets/aep_audiences_isymbol.png)

## 定義區段的規則

>[!NOTE]
>
>下節提供有關規則定義的全域資訊。 如需詳細資訊，請參閱[區段產生器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)。

若要建立規則，請依照下列步驟進行：

1. 從左窗格中尋找欄位，以反映規則所依據的屬性或事件。

1. 將欄位拖曳至中央工作區，然後根據所需的區段定義進行設定。 為此，可使用多個字串和日期/時間函式。

   在以下範例中，規則將目標設定為性別等於「男性」的所有設定檔。

   ![](assets/aep_audiences_malegender.png)

   對應至區段的預估母體會在&#x200B;**[!UICONTROL Segment Properties]**&#x200B;區段中自動重新計算。

1. **[!UICONTROL View Profiles]**&#x200B;按鈕會提供規則對應的前20筆記錄預覽，讓您快速驗證區段。

   ![](assets/aep_audiences_samplepreview.png)

   您可以視需要新增許多其他規則，以定位正確的設定檔。

   將規則新增至容器時，該規則會附加至任何具有AND邏輯運運算元的現有規則。 如有需要，請按一下邏輯運運算元加以修改。

   ![](assets/aep_audiences_andoperator.png)

將兩個規則連結在一起後，會形成一個容器。

## 比較欄位

區段產生器可讓您比較兩個欄位以定義規則。 例如，家庭地址與工作地址位於不同郵遞區號的女性。

要執行此操作，請依照下列步驟執行：

1. 將您要比較的第一個欄位（例如住家地址郵遞區號）拖曳至中心工作區。

   ![](assets/aep_audiences_comparing_1.png)

1. 選取第二個欄位（例如工作地址郵遞區號），與第一個欄位進行比較。

   將其拖曳至中心工作區，該工作區與&#x200B;**[!UICONTROL Drop here to compare operands]**&#x200B;方塊中的第一個欄位位於相同的容器中。

   ![](assets/aep_audiences_comparing_2.png)

1. 視需要設定兩個欄位之間的運運算元。 在此範例中，我們希望區段能定位住家地址與工作地址不同的設定檔。

   ![](assets/aep_audiences_comparing_3.png)

規則現已設定完畢，可隨時作為對象啟用。
