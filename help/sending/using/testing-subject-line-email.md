---
title: 測試電子郵件的主旨行
description: 瞭解如何在電子郵件設計工具中定義電子郵件的主旨行。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 343ea01229779a32919bd68fd15e0c7ff6863353
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 1%

---

# 測試電子郵件的主旨行 {#testing-a-subject}


## 關於預測性主體行 {#about-predictive-subject-line}

在編輯電子郵件時，您可以嘗試不同的主旨行，並在傳送電子郵件前先估計其開放率。

此功能預設為停用。 當匯入第一個模型時，就會啟用它。 模型是特定產業的訓練資料集的結果。 模型可讓系統在提交新主旨行時預測電子郵件的開放率。

>[!NOTE]
>
>此功能適用於電子郵件訊息和僅包含英文內容的資料庫。 如果您的例項包含其他語言的電子郵件，則訓練好的模型會不一致，並導致錯誤的結果。 只有在實例上已有模型可用時，才會顯示允許測試主題的選項。

有關導入模型的詳細資訊，請參 [閱本節](#importing-models)。

## 測試主題行 {#testing-subject-line}

若要測試您的主旨行，請遵循下列步驟：

1. 建立或開啟您的電子郵件。
1. 開啟內容，並在對應的輸入欄位中輸入電子郵件的主旨。
1. 按一下 **[!UICONTROL Test subject]** 按鈕以存取視 **[!UICONTROL Test your subject line]** 窗。 您仍然可以從此視窗編輯主題。
1. 選擇要考慮開放速率預測的正確模型。 目前已推出多種機型，每種機型都對應特定產業。 有關使用模型的詳細資訊，請參 [閱本節](#importing-models)。
1. 按一下「**[!UICONTROL Test]**」。

然後會分析您的主題。

>[!NOTE]
>
>如果主題行太短，則無法分析並顯示錯誤消息。

會計算數個指標，並顯示一組工具，以協助您：

* **預計開放率**: 此圖表提供您對電子郵件及其目前主旨的開放率的概念。
* **主旨長度**: 此指標可讓您查看主題的目前長度是否正確，或是需要較長或較短。
* **彩色字詞**: 在測試主題時，以綠色強調的字詞是對提高開放率預測貢獻最大的字詞。 以紅色強調的字詞是對提高開放率預測貢獻最小的字詞。 如果您新增或移除主題中的字詞，反白顯示的字詞將會變更。
* **類別和字詞建議**: 在窗口的下部，將顯示選定模型的多個相關類別。 這些類別會依重要性順序排序，讓您查看主題是否包含透過核取符號與其關聯的字詞。 每個類別都包含一組建議字詞，可用於您的主題中，讓其更相關並提高開放率。 這些單字是特定類別中最常使用的單字。

>[!NOTE]
>
>個人化欄位和標點符號會從主題分析中移除。 在動態／條件文字中，所有變數都視為一個主題行。

![](assets/predictive_subject_line_example.png)

## 導入模型 {#importing-models}

依預設，Adobe Campaign伺服器上沒有執行任何模型。 獲取模型和激活特徵有兩種方法：

* 您可以根據先前電子郵件訊息的資料來訓練本機模型。
* 您可以匯入特定產業（醫療等）的預先訓練模型 使用套 [件匯入功能](../../automating/using/managing-packages.md) 。

### 培訓本地模型 {#training-local-model}

* 如果您已使用Adobe Campaign，本機模型將會自動接受您已傳送訊息的訓練。
* 如果您是Adobe Campaign的新手，可以從先前的系統/ESP擷取包含4欄的CSV檔案： 日期，主旨，開啟，傳送。 若要這麼做，請前往 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** 並依照後續畫面上的指示進行。 主體上載完成後，請導入本地模型，如下所述。 本機模型會自動接受您上傳之資料的訓練。
* 如果您是Adobe Campaign的新手，但無法如上所述取得CSV檔案，則可使用預先訓練好的模型 [](#pre-trained-models) ，或等到系統中有足夠的傳送資料來訓練本機模型。 系統會自動判斷您目前的資料集是否包含足夠的資料來識別模式和訓練模型。

>[!NOTE]
>
>培訓您自己的模型不需要定義主題行數。 For more on this, see [Troubleshooting](#troubleshooting).
>
>實例上只能有一個受過培訓的模型。

要培訓本地模型，請執行以下操作：
1. 從這裡下載subjectLineTraining.xml [](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) ，並使用套 [](../../automating/using/managing-packages.md) 件匯入功能將它上傳至Adobe Campaign實例。 技術工作流程會自動為您進行培訓。
1. 第一次要培訓模型時，管理員可以強制 **[!UICONTROL SubjectLine Training workflow]** 從> **[!UICONTROL Administration]** >菜 **[!UICONTROL Application settings]** 單開始 **[!UICONTROL Workflows]** 。
1. 模型上傳及訓練後，功能就會自動啟動，訊息的主旨行欄位旁會顯示新選項。
1. 然後，技術工作流程將會每週自動繼續培訓您的模型。

### 導入預先培訓的模型 {#pre-trained-models}

要訪問這些型號，請按一下 [此處](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html)。 使用套 [件匯入功能](../../automating/using/managing-packages.md) ，將模型上傳至您的Adobe Campaign例項。

可用的型號包括：

* 化妝品行業： subjectInsightComsetic.xml
* 超市業： subjectInsightSupermarket.xml
* 醫療行業： subjectInsightMedical.xml
* 培訓的模型： subjectlineTraining.xml。

這些模型是不能訓練的。

上傳模型後，功能就會自動啟動，訊息的主旨行欄位旁會顯示新選項。

>[!NOTE]
>
>導入和生成經過培訓的模型只能由管理員執行。

## 疑難排解 {#troubleshooting}

預測性主旨行是機器學習程式，會考慮您以開放率上傳的所有主旨行。 這可讓系統在提交新主旨行時預測電子郵件的開啟率。

為了能夠培訓您自己的模型，主題行必須不同且不得有重複項，無論用於培訓模型的主題行數。

主題線的質量至關重要。 如果沒有足夠的品質資料可處理，或是所有先前的主題行都太相似，系統將無法訓練模型，您可能會收到錯誤訊息。 這表示您現有的記錄集不允許提供可靠的預測建議。

在這種情況下，您應該檢閱要上傳的資料，並確定主旨行的變化足以有效地訓練模型。

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->
