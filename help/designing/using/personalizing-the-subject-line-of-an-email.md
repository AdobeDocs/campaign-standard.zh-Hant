---
title: 個人化電子郵件的主旨行
seo-title: 個人化電子郵件的主旨行
description: 個人化電子郵件的主旨行
seo-description: 您可以個人化電子郵件的主旨，但也可以試用不同的主旨行，並估計其開啓率。
page-status-flag: 從未啓動
uuid: 345b5f4b-8e2c-4f8e-bce7-1e9 b40 a44932
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: design
content-type: reference
topic-tags: 個人化內容
discoiquuid: f7a5e935-54cf-422e-8459-27221409a200
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Personalizing the subject line of an email{#personalizing-the-subject-line-of-an-email}

## Personalizing an email subject {#personalizing-an-email-subject}

準備並傳送訊息是必要的訊息主旨。

>[!NOTE]
>
>如果主旨行空白，則訊息控制面板和電子郵件設計工具中會顯示警告。

To configure the email subject, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon) and fill in the **[!UICONTROL Subject]** section.

![](assets/email_designer_subject.png)

您也可以按一下對應的圖示，將個人化欄位、內容區塊和動態內容新增至主旨行。

**相關主題：**

* [插入個人化欄位](../../designing/using/inserting-a-personalization-field.md)
* [新增內容區塊](../../designing/using/adding-a-content-block.md)
* [在電子郵件中定義動態內容](../../designing/using/defining-dynamic-content-in-an-email.md)

## Predictive subject line {#predictive-subject-line}

編輯電子郵件時，您可以試用不同的主旨行，並在傳送之前先取得估計的價格。

預設會停用此功能。在匯入第一個模型時啓用。模型是特定產業專用的培訓資料集的結果。模型可讓系統在提交新主題行時預測電子郵件的開啓率。

>[!NOTE]
>
>此功能適用於電子郵件訊息，以及僅包含英文內容的資料庫。如果您的實例包含其他語言的電子郵件，培訓模型將會不一致，並導致錯誤結果。只有當您實例上已提供模型時，才會顯示可讓您測試主旨的選項。

### Testing a subject {#testing-a-subject}

若要測試您的主旨行：

1. 建立或開啓您的電子郵件。
1. 開啓內容，並在對應的輸入欄位中輸入電子郵件的主旨。
1. Click the **[!UICONTROL Test subject]** button to access the **[!UICONTROL Test your subject line]** window. 您仍然可以從此視窗編輯該主題。
1. 選取要考慮的正確模型，以進行開放率預測。有幾個模型可供使用，每個機型都對應於特定產業。
1. Click **[!UICONTROL Test]**.

然後分析您的主題。

>[!NOTE]
>
>如果主旨行太短，就無法分析它並顯示錯誤訊息。

計算幾個指標並顯示一組工具以協助您：

* **預測的開啓率**：此圖表可讓您對電子郵件與目前主旨的期定值有所概念。
* **主旨長度**：此指標可讓您查看主旨的目前長度是否正確，或是否需要較長或更短的時間。
* **彩色字詞**：測試主旨時，以綠色反白標示的單字是提高開啓率預測的最大貢獻字詞。以紅色反白標示的單字是貢獻最少的單字，而無法增加開放率預測。如果您新增或移除主題中的字詞，反白顯示的字詞將會變更。
* **類別和字詞建議**：在視窗的下半部，會顯示選定模型的一些相關類別。這些類別依重要性排序，可讓您查看主體是否包含透過核取符號關聯的單字。每個類別包含一組建議字詞，可用於您的主題，讓它更相關並提高打開率。這些字詞是在指定類別中最常使用的字詞。

>[!NOTE]
>
>從主旨分析移除個人化欄位和標點符號。就動態/條件文字而言，所有變數都視為一個主旨行。

![](assets/predictive_subject_line_example.png)

### Importing models {#importing-models}

根據預設，您的Adobe Campaign伺服器上沒有執行任何模型。有兩種方法可取得模型並啓用此功能：

* 您可以從之前電子郵件訊息的資料來培訓本端模型：

   * 如果您已使用Adobe Campaign，本端模型將會自動接受您已傳送的訊息訓練。
   * 如果您是Adobe Campaign的新手，可以從包含欄的系統/ESP擷取CSV檔案：日期、主旨、傳送、開啓。To do that, go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** and follow the instructions provided on the successive screens. 當主旨上傳完成時，請匯入本機模型，如下所述。本機模型會自動接受您上傳的資料訓練。
   * 如果您是Adobe Campaign的新手，無法取得上述CSV檔案，可以使用預先訓練的模型，或等候您在系統中有足夠的傳送資料來培訓本端模型。系統會自動判斷您目前的資料集是否包含足夠的資料來識別模式並培訓模型。

      >[!NOTE]
      >
      >您不需要定義您自己的模型所需的主旨行數。若要加以培訓，主旨行必須各有不同，而且無重復。如果資料沒有足夠的處理方式，系統將無法培訓模型。您只能在實體上使用一個培訓模型。
   To train a local model, download the subjectLineTraining.xml from [here](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) and use the [package import](../../automating/using/managing-packages.md) feature to upload it to your Adobe Campaign instance. 技術工作流程會自動為您進行訓練。

   The first time you want to train a model, an administrator can force the **[!UICONTROL SubjectLine Training workflow]** to start from the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]** menu.

   一旦上傳並接受模型後，此功能就會自動啓動，而新的選項會出現在訊息主旨行欄位旁邊。

   然後，技術工作流程將會每周自動培訓您的模型。

* 您可以匯入特定產業(醫療等)專用的預先訓練模型。using the [package import](../../automating/using/managing-packages.md) feature. These models are available [here](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) and cannot be trained.

   一旦上傳模型後，此功能就會自動啓動，而新的選項會出現在訊息主旨行欄位旁邊。

>[!NOTE]
>
>匯入及產生培訓模型只能由管理員執行。

可供使用的模型包括：

* 化妝品業：subjectInsightCosmetic.xml
* 超市產業：subjectInsightSupermarket.xml
* 醫療產業：subjectInsightMedical.xml
* 訓練模型：VisitLining. xml。

