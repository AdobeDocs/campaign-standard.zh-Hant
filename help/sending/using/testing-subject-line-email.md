---
title: 測試電子郵件的主旨行
description: 瞭解如何在電子郵件設計工具中定義電子郵件的主旨行。
page-status-flag: 從未激活
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 發送
content-type: 參考
topic-tags: 編輯——電子郵件——內容
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---

# 測試電子郵件的主旨行 {#testing-a-subject}

若要測試您的主旨行，請遵循下列步驟：

1. 建立或開啟您的電子郵件。
1. 開啟內容，並在對應的輸入欄位中輸入電子郵件的主旨。
1. 按一下 **[!UICONTROL Test subject]** 按鈕以存取視 **[!UICONTROL Test your subject line]** 窗。 您仍然可以從此視窗編輯主題。
1. 選擇要考慮開放速率預測的正確模型。 目前已推出多種機型，每種機型都對應特定產業。
1. Click **[!UICONTROL Test]**.

然後會分析您的主題。

>[!NOTE]
>
>如果主題行太短，則無法分析並顯示錯誤消息。

會計算數個指標，並顯示一組工具，以協助您：

* **預計開放率**:此圖表提供您對電子郵件及其目前主旨的開放率的概念。
* **主旨長度**:此指標可讓您查看主題的目前長度是否正確，或是需要較長或較短。
* **彩色字詞**:在測試主題時，以綠色強調的字詞是對提高開放率預測貢獻最大的字詞。 以紅色強調的字詞是對提高開放率預測貢獻最小的字詞。 如果您新增或移除主題中的字詞，反白顯示的字詞將會變更。
* **類別和字詞建議**:在窗口的下部，將顯示選定模型的多個相關類別。 這些類別會依重要性順序排序，讓您查看主題是否包含透過核取符號與其關聯的字詞。 每個類別都包含一組建議字詞，可用於您的主題中，讓其更相關並提高開放率。 這些單字是特定類別中最常使用的單字。

>[!NOTE]
>
>個人化欄位和標點符號會從主題分析中移除。 在動態／條件文字中，所有變數都視為一個主題行。

![](assets/predictive_subject_line_example.png)

## 導入模型 {#importing-models}

依預設，Adobe Campaign伺服器上沒有執行任何模型。 獲取模型和激活特徵有兩種方法：

* 您可以根據先前電子郵件訊息的資料來訓練本機模型：

   * 如果您已使用Adobe Campaign，本機模型將會自動接受您已傳送訊息的訓練。
   * 如果您是Adobe Campaign的新手，可以從先前的系統/ESP擷取包含4欄的CSV檔案：日期、主旨、傳送、開啟。 若要這麼做，請前往 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** 並依照後續畫面上的指示進行。 主體上載完成後，請導入本地模型，如下所述。 本機模型會自動接受您上傳之資料的訓練。
   * 如果您是Adobe Campaign的新手，但無法如上所述取得CSV檔案，則可使用預先訓練好的模型，或等到系統中有足夠的傳送資料來訓練本機模型。 系統會自動判斷您目前的資料集是否包含足夠的資料來識別模式和訓練模型。

      >[!NOTE]
      >
      >培訓您自己的模型不需要定義主題行數。 為了能夠進行培訓，主題線必須多樣化，沒有重複。 如果沒有足夠的資料進行處理，系統將無法對模型進行訓練。 實例上只能有一個受過培訓的模型。
   若要訓練本機模型，請從這裡下載subjectLineTraining.xml [](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，然後使用套件 [匯入功能](../../automating/using/managing-packages.md) ，將它上傳至您的Adobe Campaign實例。 技術工作流程會自動為您進行培訓。

   第一次要培訓模型時，管理員可以強制 **[!UICONTROL SubjectLine Training workflow]** 從&gt; **[!UICONTROL Administration]** &gt;菜 **[!UICONTROL Application settings]** 單開始 **[!UICONTROL Workflows]** 。

   模型上傳及訓練後，功能就會自動啟動，訊息的主旨行欄位旁會顯示新選項。

   然後，技術工作流程將會每週自動繼續培訓您的模型。

* 您可以匯入特定產業（醫療等）的預先訓練模型使用套 [件匯入功能](../../automating/using/managing-packages.md) 。 這些模型可 [供使用](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) ，而且無法接受培訓。

   上傳模型後，功能就會自動啟動，訊息的主旨行欄位旁會顯示新選項。

>[!NOTE]
>
>導入和生成經過培訓的模型只能由管理員執行。

可用的型號包括：

* 化妝品行業：subjectInsightComsetic.xml
* 超市業：subjectInsightSupermarket.xml
* 醫療行業：subjectInsightMedical.xml
* 培訓的模型：subjectlineTraining.xml。
