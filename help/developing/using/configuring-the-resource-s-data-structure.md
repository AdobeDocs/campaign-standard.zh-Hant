---
title: 設定資源的資料結構
seo-title: 設定資源的資料結構
description: 設定資源的資料結構
seo-description: 瞭解如何設定資料結構。
page-status-flag: 從未啓動
uuid: 60Fe80c0-9df6-4808-a432-60a1977216 ea
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 新增或延伸-資源
discoiquuid: 4f22ee35-1d5f-4c75-95b4-3e38b85de26e
context-tags: CusResource，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 888cf4cd7bfa7f82bfe70c408f8c2785c51c36e2

---


# 設定資源的資料結構{#configuring-the-resource-s-data-structure}

建立新的自訂資源後，您必須設定資料結構。

編輯資源時 **[!UICONTROL Data structure]** ，您可以新增：

* [欄位](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)
* [識別碼](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [索引索引](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)
* [連結](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)
* [傳送記錄檔](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

## 新增欄位至資源 {#adding-fields-to-a-resource}

您可以新增欄位至資源，以儲存不屬於方塊資料模型之一部分的資料。

1. 使用 **[!UICONTROL Create element]** 按鈕建立欄位。
1. 指定標籤、ID、欄位類型，並定義此欄位授權的最大長度。

   **[!UICONTROL ID]** 欄位為強制欄位，且每個欄位都必須是唯一欄位。

   >[!NOTE]
   >
   >如果您將 **[!UICONTROL Label]** 欄位保留空白，它會自動從ID完成。
   >建議您最多使用30個字元。

   ![](assets/schema_extension_4.png)

1. 若要修改其中一個欄位，請勾選 **[!UICONTROL Edit Properties]** 按鈕。

   ![](assets/schema_extension_24.png)

1. **[!UICONTROL Field definition]** 在畫面中，您可以定義將用於對象和定位的類別，甚至新增說明。

   ![](assets/schema_extension_5.png)

1. 如果您需要定義將提供給使用者的值(列舉值)，請勾選 **[!UICONTROL Specify a list of authorized values]** 此選項。

   然後，按一下並 **[!UICONTROL Create element]** 指定一個 **[!UICONTROL Label]** 和 **[!UICONTROL Value]**。視需要新增多個值。

1. 新增欄位後，請勾選 **[!UICONTROL Add audit fields]** 方塊以納入建立日期、建立資源的使用者、日期，以及上次修改的作者。
1. 勾選 **[!UICONTROL Add access authorization management fields]** 方塊以納入具有該特定資源存取權限的欄位。

   這些欄位會顯示在資料和中繼資料中，並在資料庫更新完成後顯示。如需詳細資訊，請參閱 [更新資料庫結構](../../developing/using/updating-the-database-structure.md) 區段。

1. 檢查 **[!UICONTROL Add automatic ID]** 欄位以自動產生ID。請注意，現有實體將維持空白。
1. 若要修改資源元素名稱在清單和建立步驟中出現的方式，請核取 **[!UICONTROL Personalize the resource title]** 方塊。從您為此資源建立的欄位中選取欄位。

   ![](assets/schema_extension_18.png)

現在已定義您的資源欄位。

## 定義識別金鑰 {#defining-identification-keys}

每個資源至少必須有一個唯一金鑰。例如，您可以指定索引鍵，讓兩個產品在購買表格中都無法使用相同的ID。

1. 如果您想要自動產生技術金鑰，並增量產生，請在 **[!UICONTROL Automatic primary key]** 區段中指定該儲存區的大小。

   ![](assets/schema_extension_6.png)

1. 使用 **[!UICONTROL Create element]** 按鈕來建立索引鍵。

   預設 **[!UICONTROL Label]** 會完成和 **[!UICONTROL ID]** 欄位，但您可以加以編輯。

   >[!NOTE]
   >
   >建議您最多使用30個字元。

1. 若要定義組成此索引鍵的元素，請按一下 **[!UICONTROL Create element]** 並選取您為此資源建立的欄位。

   ![](assets/schema_extension_7.png)

   已建立的索引鍵會顯示在 **[!UICONTROL Custom keys]** 區段中。

現在會建立資源的識別金鑰。

## 定義索引 {#defining-indexes}

索引可以參考一或多個資源欄位。索引可讓資料庫排序記錄，以便更輕鬆地復原記錄。它們可最佳化SQL查詢的效能。

建議您定義索引，但不是強制的。

1. 使用 **[!UICONTROL Create element]** 按鈕建立索引。

   ![](assets/schema_extension_26.png)

1. 預設 **[!UICONTROL Label]** 會完成和 **[!UICONTROL ID]** 欄位，但您可以加以編輯。

   >[!NOTE]
   >
   >建議您最多使用30個字元。

1. 若要定義組成此索引的元素，請選取您為此資源建立的欄位。

   ![](assets/schema_extension_27.png)

1. Click **[!UICONTROL Confirm]**.

建立的索引會顯示在 **[!UICONTROL Index]** 區段中的清單中。

## 使用其他資源定義連結 {#defining-links-with-other-resources}

連結詳細說明一個表格與其他表格的關聯。

1. 使用 **[!UICONTROL Create element]** 按鈕建立目標資源的連結。
1. Click **[!UICONTROL Select a target resource]**.

   ![](assets/schema_extension_28.png)

1. 資源以字母順序顯示，可依名稱篩選。其技術名稱會以括號顯示。

   從清單中選取元素，然後按一下 **[!UICONTROL Confirm]**。

   ![](assets/schema_extension_9.png)

1. 根據 **[!UICONTROL Link type]** 基數選擇。視選取的基數類型而定，如果刪除或複製記錄，行為可能會有所不同。

   各種連結類型如下：

   * **[!UICONTROL 1 cardinality simple link]**：來源表格的一次事件可在目標表格的大部份發生對應的事件。
   * **[!UICONTROL N cardinality collection link]**：來源表格的一次事件可有數個目標表格的對應次數，但某個定位表格的來源表格可能會有大部分對應的事件。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：來源表格有一個出現在目標表格或無的情況下。請注意，這種 **[!UICONTROL Link type]** 情況可能會造成效能問題。
   ![](assets/schema_extension_29.png)

1. **[!UICONTROL New link]** 在畫面中，預設會完成和 **[!UICONTROL Label]****[!UICONTROL ID]** 欄位，但您可以加以編輯。

   >[!NOTE]
   >
   >建議您最多使用30個字元。

   >[!CAUTION]
   >
   >建立後，無法重新命名連結。若要重新命名連結，您必須將其刪除並再次建立連結。

1. **[!UICONTROL Category for the audience and targeting]** 清單可讓您將此連結指派給類別，讓它更能顯示在查詢編輯器工具中。
1. 視需要， **[!UICONTROL Reverse link definition]** 此區段可讓您顯示目標資源中資源的標籤和ID。
1. 定義 **[!UICONTROL Behavior if deleted/duplicated]** 區段中連結參照的記錄行為。

   依預設，一旦連結不再參照目標記錄，將會刪除目標記錄。

   ![](assets/schema_extension_16.png)

1. **[!UICONTROL Join definition]** 在區段中，選取預設 **[!UICONTROL Use the primary keys to make the join]** 選項，但您可以選擇兩個選項：

   * **[!UICONTROL Use the primary key to make the join]**：此加入定義可讓您使用描述檔主要索引鍵與購買的主要索引鍵協調。
   * **[!UICONTROL Define specific join conditions]**：此加入定義可讓您手動選取將加入兩個資源的欄位。請注意，如果資料未正確設定， **「購買** 記錄」將無法顯示。
   ![](assets/schema_extension_17.png)

建立的連結會顯示在 **[!UICONTROL Links]** 區段中的清單中。

**範例：使用「描述檔」資源連結建立的資源**

在此範例中，我們想要將新的資源 **購買** 與 **描述檔** 自訂資源連結：

1. 建立新 **的購買** 資源。
1. 若要將它與 **「描述檔** 」自訂資源連結，請將此區段中的 **[!UICONTROL Links]** 區段取消顯示 **[!UICONTROL Data structure]****[!UICONTROL Create element]**，然後按一下。
1. 在這裡選取目標資源 **[!UICONTROL Profiles (profile)]**。
1. 在此範例中，請保持選取 **[!UICONTROL 1 cardinality simple link]** 的預設連結類型。

   ![](assets/custom_resource_link_to_profile_2.png)

1. 選擇加入定義，在此處保留預設 **[!UICONTROL Use the primary key to make the join]**&#x200B;值。

   ![](assets/custom_resource_link_to_profile_3.png)

1. 如有需要，您可以定義詳細畫面，以便編輯 **「購買」** 並將其連結至描述檔。

   將 **[!UICONTROL Detail screen configuration]** 區段取消顯示， **[!UICONTROL Define a detail screen]** 並勾選以設定對應至資源每個元素的畫面。如果您未勾選此方塊，將無法存取此資源的詳細資料檢視。

1. Click **[!UICONTROL Create element]**.
1. 選取您的連結資源並按一下 **[!UICONTROL Add]**。

   然後選取 **[!UICONTROL Client data]** &gt;， **[!UICONTROL Purchase]**&#x200B;即可在進階功能表中提供您的新資源。

   ![](assets/custom_resource_link_to_profile_4.png)

1. 完成設定 **[!UICONTROL Confirm]**&#x200B;後，按一下。

   您現在可以發佈新資源。

新增此連結後， **「購買** 」索引標籤會新增至「 **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Profiles]** 」功能表中的描述檔詳細資料畫面。請注意，此為 **[!UICONTROL Profile]** 資源專屬。

![](assets/custom_resource_link_to_profile.png)

## 定義傳送記錄檔延伸模組 {#defining-sending-logs-extension}

傳送記錄延伸功能可讓您：

* **新增描述檔自訂欄位來擴充動態報表功能**
* 使用 **區段代碼和描述檔資料來擴充傳送記錄資料**

**使用區段代碼擴充**

使用者可以使用來自工作流程引擎的區段代碼來擴充記錄檔。

區段代碼必須定義在工作流程中。

若要啓動此擴充功能，請查看選項 **[!UICONTROL Add segment code]**。

![](assets/sendinglogsextension_1.png)

有關區段代碼的詳細資訊，請參閱 [區段](../../automating/using/segmentation.md) 區段。

**使用描述檔欄位擴充**

>[!NOTE]
>
>管理員應該使用自訂欄位擴充描述檔資源。

![](assets/sendinglogsextension_2.png)

按一下 **[!UICONTROL Add field]** 並從描述檔資源中選取任何自訂欄位。

若要產生連結至「描述檔」維度的新子維度，請查看 **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** 選項。

![](assets/sendinglogsextension_3.png)

您可以從動態報表中將自訂欄位維度拖放到自由表格中。

如需動態報表的詳細資訊，請參閱元件 [清單](../../reporting/using/list-of-components-.md)。

>[!CAUTION]
>
>傳送至動態報表的欄位數限制為20。

## 編輯資源屬性 {#editing-resource-properties}

在自訂資源畫面中 **[!UICONTROL Summary]** ，窗格會指出新建立資源的狀態。您可以管理其存取及其一般屬性。

![](assets/schema_extension_3.png)

1. 按一下 **[!UICONTROL Edit properties]** 按鈕以新增說明。

   ![](assets/schema_extension_30.png)

1. 如有需要，請修改資源的標籤和ID。

   >[!NOTE]
   >
   >建議您最多使用30個字元。

1. 如果您需要將此資源的存取限制在特定組織單位，請在此處指定。只有授權單位的使用者才能在應用程式中使用此資源。
1. 儲存修改。

您的修改會儲存。您需要再次發佈資源以套用這些資源。

## 產生個人檔案和自訂資源的唯一ID {#generating-a-unique-id-for-profiles-and-custom-resources}

根據預設，設定檔和自訂資源在建立時沒有商業ID。您可以啓用在建立元素時自動產生唯一ID的選項。此ID可用於：

* 在外部工具中輕鬆識別匯出的記錄。
* 匯入在其他應用程式中處理之更新資料時的協調記錄。

它只能啓用設定檔和自訂資源。

1. 建立描述檔資源的擴充功能或建立新資源。
1. 在資料結構定義中，勾選 **[!UICONTROL Add automatic ID field]** 選項，位於 **[!UICONTROL Fields]** 區段下方。
1. 儲存並發佈對資源所做的修改。如果您希望此機制可套用至透過API建立的元素，請檢查延伸API的選項。

**[!UICONTROL ACS ID]** 現在，當手動建立新元素、從API或從匯入工作流程插入新元素時，就可使用此欄位。ACS ID欄位為UUID欄位，並建立索引。

匯出描述檔或自訂資源時，現在您可以新增 **[!UICONTROL ACS ID]** 該欄(如果已為該資源啓用)。您可以在外部工具中重復使用此ID來識別記錄。

![](assets/export_id_field.png)

重新匯入已在其他應用程式中處理/更新的資料時(例如CRM)，您可以輕鬆地與此唯一ID協調。

>[!NOTE]
>
>在啓動選項之前，不會針對建立的設定檔或元素更新 **[!UICONTROL ACS ID]** 欄位。只有新記錄將具有ACS ID。此欄位為唯讀模式。您無法修改它。

