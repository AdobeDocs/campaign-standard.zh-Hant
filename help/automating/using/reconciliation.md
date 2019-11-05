---
title: 調解
description: 「協調」活動允許您將未標識的資料連結到現有資源。
page-status-flag: 從未激活
uuid: 7884db8c-1717-4724-be15-3b0b32cc071
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 資料管理活動
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: 協調，主
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 調解{#reconciliation}

## 說明 {#description}

![](assets/reconciliation.png)

此活 **[!UICONTROL Reconciliation]** 動可讓您將未識別的資料連結至現有資源。

## 使用內容 {#context-of-use}

此活 **[!UICONTROL Reconciliation]** 動主要用於資料管理，並意味著兩種不同的使用案例：

* 添加關係：標籤 **[!UICONTROL Links]** 可讓您在傳入資料和數個其他Adobe Campaign資料庫維度之間新增連結。

   例如，包含購買資料的檔案也可能包含識別所購買產品及購買者的資訊。 因此，檔案資料會關 **注另外兩個維度**（購買除外）:「產 **品** 」和「 **描述檔** 」維度。 然後，需要在這些維和「購買」維 **之間建立關係** （請參閱以下示例）。

   定義關係時，將向傳入資料添加列以引用連結維的外鍵。

   >[!NOTE]
   >
   >此操作表示連結維的資料已在資料庫中。 例如，如果您匯入購買檔案，顯示何時購買了哪些產品、客戶等，則產品和客戶端必須已存在於資料庫中。

* 資料識別：標 **[!UICONTROL Identification]** 簽可讓您將傳入資料連結至Adobe Campaign資料庫中現有維度的欄。 在活動後，資料被標識為屬於定義的維。

   例如，您可以接著執行儲存對象、資料庫更新等。

例如，活動 **[!UICONTROL Reconciliation]** 可放在載入資料活動之後，以便將非標準資料匯入資料庫。

## 配置 {#configuration}

1. 在包含目標維度不直 **[!UICONTROL Reconciliation]** 接來自Adobe Campaign之人口族群的轉場後，將活動拖放至工作流程中。 如需詳細資訊，請參閱「定 [位維度和資源」](../../automating/using/query.md#targeting-dimensions-and-resources)。
1. 選擇活動，然後使用顯示的快 ![](assets/edit_darkgrey-24px.png) 速操作中的按鈕將其開啟。
1. 如果要定義傳入資料與其他資料庫維之間的連結，請轉至該選 **[!UICONTROL Links]** 項卡。

   視需要新增關係。 對於每個關係，首先選擇連結的維，然後在連結詳細資訊中指定相應的欄位。

1. 如果您只想識別傳入的資料，請前往標籤並 **[!UICONTROL Identification]** 勾選方 **[!UICONTROL Identify the document from the working data]** 塊。

   選擇要協調傳入資料的目標維度。

   新增協調條件，將傳入的轉換記錄連結至選取的定位維度記錄。 如果指定了多個標準，則必須對這些標準進行驗證，以使其所有資料之間的連結能夠工作。

   選擇模 **[!UICONTROL Processing unidentified source lines]** 式：

   * **[!UICONTROL Ignore them]**:只有可識別的資料會保留在活動的對外轉移中。
   * **[!UICONTROL Keep in the outbound population]**:入站轉變中的所有資料都保存在活動的出站轉變中。

1. 確認活動的設定並儲存工作流程。

## 範例1:關係定義 {#example-1--relation-definition}

下列範例示範使用檔案中的購買資料更新資料庫的工作流程。 採購資料包含參考其他維度的資料元素，例如客戶電子郵件和產品代碼。

>[!NOTE]
>
>依預 **設** ，此范 **例中使用的Transactions** 和Products資源不存在於Adobe Campaign資料庫中。 因此，它們是使用「自訂資源」功 [能預先建立](../../developing/using/data-model-concepts.md) 的。 與已匯入檔案中的電子郵件地址以及產品相對應的描述檔會事先載入資料庫。

工作流程由下列活動組成：

![](assets/reconciliation_example1.png)

* 一 **[!UICONTROL Load file]** 個活動，它載入並檢測要導入的檔案的資料。 匯入的檔案包含下列資料：

   * 交易日期
   * 用戶端電子郵件地址
   * 購買產品的代碼
   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* 將購 **[!UICONTROL Reconciliation]** 買資料系結至資料庫描述檔及產品的活動。 因此，必須定義檔案資料與配置檔案表以及產品表之間的關係。 此配置在活動的頁籤中執 **[!UICONTROL Relations]** 行：

   * 與描述檔的 **關係**:檔案的 **client** 欄會連結至Profiles維的 **email** (電子郵 **件)欄** 。
   * 與產品的 **關係**:檔案的 **product** 欄會連結至Profiles維度的 **productCode** 欄 **** 位。
   欄會新增至傳入資料，以參考連結維度的外鍵。

   ![](assets/reconciliation_example3.png)

* 活動 **[!UICONTROL Update data]** 允許您定義要使用導入的資料進行更新的資料庫欄位。 由於資料已被標識為屬於前一活動中 **的「事務** 」維，因此，您可以在此處使用 **[!UICONTROL Directly using the targeting dimension]** 標識選項。

   使用自動偵測欄位更新的選項，會將先前活動中設定的連結（至描述檔和產品）新增至清單 **[!UICONTROL Fields to update]**。 您也必須確保與交易日期對應的欄位正確新增至此清單。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## 範例2:身份識別 {#example-2--identification}

下列範例示範從包含新用戶端的匯入檔案直接建立描述檔對象的工作流程。 它由以下活動組成：

![](assets/identification_example2.png)

* 一 **[!UICONTROL Load file]** 個活動，它載入並檢測要導入的檔案的資料。 匯入的檔案包含下列資料：

   ```
   lastname;firstname;email;dateofbirth
   jackman;megan;megan.jackman@testmail.com;07/08/1975
   phillips;edward;phillips@testmail.com;09/03/1986
   weaver;justin;justin_w@testmail.com;11/15/1990
   martin;babeth;babeth_martin@testmail.net;11/25/1964
   reese;richard;rreese@testmail.com;02/08/1987
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
   grimes;daryl;daryl_890@testmail.com;12/06/1979
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
   ```

* 活 **[!UICONTROL Reconciliation]** 動，將載入檔案的每列連結到配置檔案維列。 無法識別的檔案記錄（遺失資料、不相容的資料類型等）會被忽略，以保留最終觀眾資料的完整性。

   ![](assets/identification_example1.png)

* 一種 **[!UICONTROL Save audience]** 活動，可儲存設定檔的觀眾。

   ![](assets/identification_example3.png)

