---
title: 疲勞規則
seo-title: 疲勞規則
description: 疲勞規則
seo-description: 建立疲勞規則，以管理與個人檔案之間的過度通訊。
page-status-flag: 從未啓動
uuid: fa5e3ed-36c2-4f16-b97 a-119b85 adf679
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 使用typology規則
discoiquuid: 4337a80b-0b0-4a37-bce3-Fe2121 a66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 48c725de297e3a8b2fc05be65f59cd23b2cfd7d7

---


# 疲勞規則{#fatigue-rules}

## 關於疲勞規則 {#about-fatigue-rules}

疲勞規則可讓行銷人員設定全域跨通道業務規則，自動排除促銷活動中過度詢問的個人檔案。

若要實施疲勞規則，您可以定義每個描述檔的訊息數目上限，並選取規則適用的時段。在傳送準備期間，會根據已傳送給他們的訊息數目，從傳送中排除描述檔。

>[!NOTE]
>
>若要套用疲勞規則，您必須定義傳送的聯絡日期。如果您選擇立即傳送訊息，則不會套用疲勞規則。

相關主題：

* [準備](../../administration/using/configuring-email-channel.md#preparation)
* [管理印刷樣式](../../administration/using/about-typology-rules.md#managing-typologies)
* [Typology規則](../../administration/using/about-typology-rules.md#typology-rules)

## 建立疲勞規則 {#creating-a-fatigue-rule}

若要建立並設定 **[!UICONTROL Fatigue]** 打字規則，請套用下列步驟：

1. 按一下介面左上角的Adobe Campaign標誌，然後選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**。

   ![](assets/fatigue4.png)

1. 從打字規則清單中，按一下 **[!UICONTROL Create]**。

   ![](assets/fatigue.png)

1. 在 **[!UICONTROL Rule type]** 欄位中選取 **[!UICONTROL Fatigue]**。

   ![](assets/fatigue3.png)

1. 在 **[!UICONTROL Channel]** 欄位中，選取您的規則適用的頻道。您可以選擇單一頻道(電子郵件、簡訊、直效郵件、行動應用程式)或選取 **[!UICONTROL All channels]**。請參閱 [選擇渠道](../../administration/using/fatigue-rules.md#choosing-the-channel)。

   ![](assets/fatigue5.png)

1. **[!UICONTROL General]** 在標籤中，定義每個描述檔的訊息最大數目方法。您可以選擇常數臨界值或變數。您也可以微調設定檔和傳送上的臨界值。如需詳細資訊，請參閱 [「定義臨界值](../../administration/using/fatigue-rules.md#defining-the-threshold)」。

   ![](assets/fatigue2.png)

1. 選擇套用打字規則的項目 **[!UICONTROL Sliding period]** 。如需詳細資訊，請參閱 [設定滑動段](../../administration/using/fatigue-rules.md#setting-the-sliding-period)。

   ![](assets/fatigue6.png)

   在此範例中(請參閱先前的螢幕擷取)，我們選擇在15天的滑動期間傳送最多個訊息。

1. **[!UICONTROL Application criteria]** 在標籤中，您可以選擇將此規則套用至所有傳送，或根據要傳送的訊息限制規則的適用性。只有當符合應用程式條件時，才會執行規則。例如，您只能在訊息上使用以指定字詞開頭或包含特定字母的ID來套用規則。請參閱 [限制篩選規則的適用性](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule)。

   ![](assets/fatigue20.png)

1. 選取 **[!UICONTROL Typologies]** 標籤，並將您的打字規則連結到用於傳遞的字型。請參閱 [管理typolologies](../../administration/using/about-typology-rules.md#managing-typologies) 和 [Typology規則](../../administration/using/about-typology-rules.md#typology-rules)。

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >您可以在傳送範本中定義印刷樣式，以便自動套用至使用此範本建立的所有傳送。

在傳送準備期間，會根據傳送給他們的傳送數量，將描述檔排除在傳送範圍之外。您可以在傳送記錄檔中檢視疲勞規則執行結果。請參閱 [檢視疲勞結果](../../administration/using/fatigue-rules.md#viewing-the-fatigue-results)。

![](assets/fatigue16.png)

>[!CAUTION]
>
>若要讓疲勞規則運作，您必須定義傳送的聯絡日期。如果您選擇立即傳送訊息，則不會套用疲勞規則。

## 選擇渠道 {#choosing-the-channel}

疲勞規則適用於各種管道。渠道定義在類文規則設定的 **[!UICONTROL Channel]** 欄位中。您可以選擇單一渠道或選擇 **[!UICONTROL All channels]**。

![](assets/fatigue5.png)

**可用頻道**

可使用下列管道：

* 電子郵件
* 行動電話(SMS)
* 直接郵件
* 行動應用程式：此渠道可讓您傳送推播通知給描述檔或應用程式訂閱者。如果您選擇將通知傳送至描述檔，則會與多頻道疲勞規則相容。

   >[!CAUTION]
   >
   >疲勞規則與傳送給應用程式訂閱者的推播通知不相容。如果您要傳送訊息給應用程式用戶，則不會套用疲勞規則。

* 所有通道：此選項可讓您將規則套用至所有渠道。例如，您可以決定在任何頻道上每個月傳送最多個訊息。如果您上周傳送個電子郵件至描述檔，而您今天嘗試傳送推播通知，則會排除相同的描述檔。

**傳送類型**

疲勞規則與所有傳送類型相容：單鍵傳送、遞回傳送、工作流程傳送和交易訊息。

**交易傳訊** 可用來傳送定位事件(RetEvent)和行銷訊息(定位設定檔)的服務訊息，例如重新行銷訊息。疲勞規則僅與行銷訊息相容(定位設定檔)。事件交易訊息不包含描述檔資訊，因此它們與疲勞規則不相容(即使在使用描述檔進行擴充時)。透過交易訊息的行銷訊息支援，您可以 **將疲勞規則套用到所有通道，包括行銷交易訊息**。

## 定義臨界值 {#defining-the-threshold}

每個疲勞規則定義臨界值，也就是說，可以在指定期間傳送到一個描述檔的最大訊息數量。一旦達到此臨界值後，將不會再發生任何傳送，直到考慮到期間結束為止。此程序可讓您在訊息超過設定臨界值時自動排除描述檔，以免過度詢問。

臨界值可以是常數或變數。這表示在特定時段內，臨界值不同於一個描述檔，甚至是相同的描述檔。

**使用修正臨界值**

臨界值代表在相關時段內可傳送至描述檔的最高訊息數量。

根據預設，臨界值為常數，您需要指出規則授權的最大訊息數。

![](assets/fatigue2.png)

**使用變數臨界值**

若要定義變數臨界值，請選取欄位中的 **[!UICONTROL Depends on the recipient]****[!UICONTROL Threshold type]** 值。

![](assets/fatigue15.png)

然後有兩個選項：

* 選取描述檔欄位：根據選取的欄位，臨界值會依每個描述檔而有所不同。例如，如果您已將描述檔資源使用「通訊頻率」欄位擴充，請按一下 **[!UICONTROL Threshold computation formula]** 欄位右邊的按鈕，然後選取您的欄位。對於每個描述檔，臨界值會採用「通訊頻率」欄位的值。

   ![](assets/fatigue21.png)

* 定義公式：按一下 **[!UICONTROL Threshold computation formula]** 欄位右邊的第二個按鈕，以定義進階臨界值計算公式。例如，您可以根據描述檔所屬的區段來索引授權訊息的數目。這表示屬於「Web」區段的描述檔可能會收到比其他設定檔更多的訊息。**[!UICONTROL Iif (@origin='Web', 5, 3)]** 類型公式可授權傳送個訊息至網頁區段，以及對其他區段傳送個訊息。

   ![](assets/fatigue14.png)

**改善描述檔和傳送上的臨界值**

根據預設，會將所有訊息納入臨界值計算中。核取 **[!UICONTROL Refine Threshold on profiles and deliveries]** 方塊以篩選準備傳送時要計數的設定檔和傳送。

在下列範例中，只會計入男性個人資料，且只會計入以 **電子報** 開頭的標籤。

![](assets/fatigue13.png)

改善傳送的臨界值與限制整個規則( **[!UICONTROL Application criteria]** 標籤)的適用性不同：

* **[!UICONTROL Application criteria]**：您選擇執行規則，或不根據特定標準。例如，如果您的應用程式條件是「標籤開始於電子報」，則規則只會套用至符合此條件的傳送。如果傳送的標籤以「促銷」開頭，則規則完全不會執行。
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**：所有使用此類文規則的傳送都會執行規則，但您會決定您要計數的過去和已排程傳送。例如，如果您的限制是「標籤開始於電子報」，則即使傳送標籤以「Promo」開頭，規則仍會執行。在選取的滑動期間，它會計算標籤以「電子報」開始的傳送次數。

## 設定滑動段 {#setting-the-sliding-period}

疲勞規則定義於n天滾動期間。時段設定在 **[!UICONTROL Sliding period]** 區段中，例如周、天或小時。

![](assets/fatigue6.png)

規則執行時，會考量過去傳送和排程傳送。這保證在指定的滑動期間，絕不會超過臨界值。

例如，如果您定義48小時期間，系統會在連絡人日期 **** 之前48小時內查看，且聯絡日期 **之後48小時**。因此，選取的期間會加倍，以便整合未來傳送以及先前的傳送。

若要限制計入周期間的傳送，請在「滑動期間」區段中輸入 **日** 和 **周****或** 周。計算中將會考量傳送日期最多天前傳送的傳送日期，以及在套用規則之後最長七天的時間。

## 檢視疲勞結果 {#viewing-the-fatigue-results}

在傳送準備期間，會根據傳送給他們的傳送數量，將描述檔排除在傳送範圍之外。若要檢視疲勞規則執行結果，請按一下 **[!UICONTROL Deployment]** 區塊右下角的按鈕。

![](assets/fatigue22.png)

有三個標籤可供使用，可顯示疲勞執行結果的詳細資訊，包括套用的規則名稱：

* 傳送記錄檔：

   ![](assets/fatigue17.png)

* 排除記錄：

   ![](assets/fatigue18.png)

* 排除原因：

   ![](assets/fatigue19.png)

## 檢視疲勞規則摘要報表 {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign提供關於疲勞規則的專屬報告，可協助您瞭解如何套用至促銷活動。這可讓您瞭解宣傳活動如何影響彼此，並作出正確調整。

**[!UICONTROL Fatigue rules summary]** 您可以從 **[!UICONTROL Reports]** 按鈕存取每個程式、促銷活動和訊息右上角的按鈕。

![](assets/fatigue27.png)

在畫面的左側，您可以篩選傳送日期的報表資料。依預設，選取時段會開始至目前日期之前的15天，並在15天後結束。您也可以篩選特定疲勞規則。

圓形圖顯示所選期間的下列資訊：

* **[!UICONTROL Total targeted]**：訊息準備前的總目標
* **[!UICONTROL Excluded]**：因疲勞規則應用程式而產生的排除總數
* **[!UICONTROL Other exclusions]**：因其他類型的規則而產生的排除總數
* **[!UICONTROL To deliver]**：訊息準備後要傳送的訊息總數( **[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** )**[!UICONTROL Other exclusions]**

在圖表右側，您會找到排除次數，依疲勞規則劃分。

底部表格會顯示所選時段內的所有傳送。對於每次傳送，您可以查看套用的疲勞規則和對應的排除。表格中也會顯示沒有聯絡日期的傳送。

* **[!UICONTROL 0]** 表示已套用疲勞規則，但沒有排除。
* **[!UICONTROL -N]** 表示發生N個排除。
* 空白欄位表示疲勞規則不適用。

>[!NOTE]
>
>顯示的資料不屬於您存取報表的程式、訊息或促銷活動。此報告會顯示所有組織單位的所有疲勞規則和傳送。這可讓您取得所有傳送的全域視圖，以瞭解促銷活動受到其他人的影響。

## 範例 {#examples}

疲勞管理實作有許多可能性。以下是您可以執行的一些範例：

* 使用套用至所有管道的 **常數臨界值** 來建立 **疲勞規則**：

   假設您建立多頻道規則，在滑動期間的滑動期間為常數。

   上周，您的高階個人檔案收到促銷電子郵件和交易式再行銷電子郵件。您也排定將於下周傳送的SMS。今天，您決定傳送針對所有個人檔案的推播通知。Premium描述檔將會排除在今天的推播之外，因為已達到兩周期間內的最大訊息數量。

   ![](assets/fatigue23.png)

* 根據描述檔欄位使用 **變數臨界值** 來建立 **疲勞規則**：

   您已使用「通訊限制」欄位擴充描述檔資源，為每個描述檔定義不同的臨界值。在疲勞規則中，根據此欄位定義變數臨界值，並選取天的滑動期間。讓我們來看看兩個描述檔範例：John的通訊限制為1，David的臨界值為2。這兩家公司都已收到電子報電子郵件。您現在決定傳送另一封電子郵件給他們。只有David才會收到它，因為John已被排除在目標之外。

   ![](assets/fatigue24.png)

* 使用 **臨界值計算公式建立疲勞規則**：

   您想要根據個人檔案的年齡變更臨界值。如果描述檔低於40，您想要定義限制和舊描述檔的限制，上限為2。您可以直接在疲勞規則中建立公式，根據描述檔年齡來計算臨界值，而不是為每個具有延伸欄位的描述檔定義此臨界值。在我們的範例 **[!UICONTROL Iif (@age<40, 4, 2)]**&#x200B;中，公式將會是。

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >此區域也包含使用臨界值計算公式的疲勞規則逐步範例。

* 建立疲勞規則 **，可調整描述檔和傳送** 上的臨界值：

   您已使用「Score」欄位擴充描述檔資源，也將傳送的資源擴充為「Type」欄位。您想要定義常數臨界值，但要從計算「警報」或「黑色星期五」的所有傳送，以及分數大於10的所有描述檔中排除所有傳送。當規則執行時，它將會在過去和排程的傳送之間計數，所有不屬於「警報」或「黑色星期五」的傳送都將傳送至小於10的描述檔。

   ![](assets/fatigue26.png)

以下是使用臨界值計算公式的疲勞規則逐步範例。

在此使用案例中，我們想要建立一個打字規則，防止每周傳送超過2message to premium描述檔和每周個訊息至標準設定檔。

若要識別客戶和潛在客戶，我們將描述檔資源擴充 **[!UICONTROL Status]** 為欄位，欄位包含高階描述檔，以及標準設定檔的1。

若要建立規則，請套用下列步驟：

1. 建立 **新的疲勞** 類型打字規則。
1. **[!UICONTROL Threshold]** 在區段中，我們想要建立公式，根據每個描述檔來計算臨界值。選取欄位中的 **[!UICONTROL Depends on the recipient]****[!UICONTROL Threshold type]** 值，然後按一下 **[!UICONTROL Threshold computation formula]** 欄位右邊的第二個按鈕。

   ![](assets/fatigue7.png)

1. **[!UICONTROL List of functions]** 在區段中，按兩下節點中的 **if** 函數 **[!UICONTROL Others]** 。

   ![](assets/fatigue8.png)

1. 然後在區段中選取設定檔 **的狀態****[!UICONTROL Available fields]** 。

   ![](assets/fatigue9.png)

1. 輸入所要的值以建立下列公式： **if(@ status=0,2,4)**

   ![](assets/fatigue10.png)

   此公式可讓您在狀態等於0時指派值2，並對所有其他狀態指定值4。

1. 按一下 **[!UICONTROL Confirm]** 以核准公式。
1. 指出 **[!UICONTROL Sliding period]** 規則適用的位置：7天內，將所傳送的內容限制在周內。

   ![](assets/fatigue11.png)

1. 現在連結您剛才建立的規則，以便套用到您的傳送項目。若要這麼做，請選取 **[!UICONTROL Typologies]** 標籤，然後按一 **[!UICONTROL Create element]** 下並選取用於傳送的字型。

   ![](assets/fatigue12.png)

1. 儲存規則以核准建立。

規則會套用至根據字元類型的所有傳送。
