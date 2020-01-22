---
title: 設定登錄頁面的主要步驟
description: 瞭解設定著陸頁面的主要步驟
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# 著陸頁面快速入門 {#getting-started-with-landing-pages}

## 關於登錄頁面 {#about-landing-pages}

Campaign隨附著著陸頁面，這些網頁表單可用來擷取您受眾的資訊、提供服務訂閱、顯示資料以及擴充您的資料庫。 著陸頁面也可用於取得或更新現有的描述檔。

著陸頁面也可用來設定雙重選擇加入機制，讓您保護平台不受錯誤或無效的電子郵件地址或垃圾郵件機器人。 如需詳細資訊，請參閱專 [用使用案例](../../channels/using/setting-up-a-double-opt-in-process.md)。

設定著陸頁面的主要步驟如下：

![](assets/lp_steps.png)

在本頁中，您將會找到這些步驟的相關資訊，以及專用檔案的參考，以取得更多詳細資訊。

**相關主題：**

* [建立著陸頁面教學課程影片](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/landing-pages/landing-page-create-and-edit.html) （影片）
* [建立服務](../../audiences/using/creating-a-service.md)
* [設定雙重加入程 序](setting-up-a-double-opt-in-process.md)

## 著陸頁面限制{#landing-page-limitations}

下節列出您在開始設定登陸頁面之前應注意的限制。

**寫入和更新資料**

* 著陸頁面僅限於 **[!UICONTROL Profile]**和**[!UICONTROL Subscription]** 資源。 您可以儲存記錄，並從 **[!UICONTROL Profile]**訂閱／取消訂閱中更新記錄**[!UICONTROL Service]**。
有關資源配置的詳細資訊，請 [參閱配置資源的資料結構](../../developing/using/configuring-the-resource-s-data-structure.md)。

>[!CAUTION]
>
>著陸頁面無法顯示或更新來自和以外任何其他資源的 **[!UICONTROL Profile]**資料**[!UICONTROL Subscription]**。

**預載**

* 著陸頁面無法自動顯示記錄清單，也無法列出已訂閱描述檔的服務。 有關服務的詳細資訊，請參閱本 [頁](../../audiences/using/creating-a-service.md)。

* 具有預先填入表單的登陸頁面（資料已預先載入頁面）只能從Adobe Campaign電子郵件存取。 無法從網站頁面存取此類表格。

**調解**

* 協調行為如下：一找到匹配，協調進程就會停止。 這表示協調只能在一個配置檔案記錄上進行，在存在重複項時，不能在多個記錄上進行。

例如，您想要傳送下列贏取登陸頁面至您的描述檔，以使用描述檔的行動號碼更新您的Campaign資料庫。

![](assets/landing_page_limitation_1.png)

如果您的其中一個描述檔填入著陸頁面，但已有重複的描述檔，則會更新具有最早建立日期的相符描述檔，因為描述檔會根據其建立日期來排定優先順序。

這裡只更新了第一個描述檔，因為它是最舊的項目。

![](assets/landing_page_limitation_2.png)

**測試著陸頁面**

* 著陸頁面僅適用於描述檔，而非測試描述檔，這表示著陸頁面無法作為電子郵件證明的一部分進行測試。

## 步驟1 —— 設定著陸頁面範本 {#configure-the-landing-page-template}

設定著陸頁面之前，第一步是設定符合您需求的著陸頁面範本。 範本準備就緒後，所有以該範本為基礎的著陸頁面都會預先設定所需參數。

1. 從進階功能表，透過Adobe Campaign標誌，選取 **[!UICONTROL Resources]**/**[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]**，然後複製您要使用的範本。
1. 在範本屬性中，指定著陸頁面必須具有的所有共同參數。 例如：定位維度、已識別或未識別訪客的頁面存取參數、訪客進行表單驗證的特定動作、內容中使用的品牌／標誌等。 如需著陸頁面屬性的詳細資訊，請參 [閱本節](../../channels/using/configuring-landing-page.md)
1. 儲存您的修改。

如需著陸頁面範本的詳細資訊，請參 [閱本節](../../channels/using/getting-started-with-landing-pages.md)。

![](assets/lp-steps1.png)

## 步驟2 —— 建立和設定著陸頁面 {#create-and-configure-the-landing-page}

從上一步驟中定義的範本，在方案或促銷活動中建立新的著陸頁面。

1. 根據所要的範本建立著陸頁面。
1. 輸入著陸頁面的一般參數（標籤、說明等）。
1. 接著您將存取著陸頁面控制面板。 視需要編輯著陸頁面屬性(請參 [閱設定著陸頁面](../../channels/using/configuring-landing-page.md))。 依預設，屬性是著陸頁面範本中設定的屬性。
基於安全性原因和平台效能，強烈建議您在著陸頁面屬性中設定到期日。 完成後，著陸頁面將在選取的日期自動取消發佈。 For more on validity parameters, refer to [this section](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >您的修改僅對正在編輯的著陸頁面有效。 如果您想要將這些修改套用至其他著陸頁面，您可以在專用的範本中執行這些修改，然後從該範本建立其他著陸頁面。

## 步驟3 —— 設計著陸頁面 {#design-the-landing-page}

您現在可以定義著陸頁面的內容。 依預設，著陸頁面包含三個可透過捲動箭頭存取的頁面：主要內容頁面、確認頁面和錯誤頁面。

![](assets/lp-steps4.png)

每個頁面上預設會設定數個欄位。 如有必要，您可以編輯其屬性和對應。

您也可以設定在個人檔案按一下確認按鈕後，其行為方式，並根據您的需求（影像、個人化欄位等）個人化內容。 例如，您可以在登陸頁面的確認頁面上插入描述檔的名字，以感謝他們註冊。

如需著陸頁面設計的詳細資訊，請參閱 [本節](../../channels/using/designing-a-landing-page.md)。

## 步驟4 —— 測試著陸頁面 {#test-the-landing-page}

一旦定義著陸頁面後，您就可以模擬其執行方式，並在登陸頁面可線上使用時加以動作。

![](assets/lp-steps5.png)

>[!CAUTION]
>
>著陸頁面測試只能使用描述檔進行，而不能使用測試描述檔。 提交表單時，選取的描述檔資料將會實際更新。 若要避免修改真實的個人檔案，請使用假的客戶個人檔案。

如果您對著陸頁面的運作方式感到滿意，可以發佈它，讓它線上上使用。

如需如何測試著陸頁面的詳細資訊，請參閱 [本節](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-)。

## 步驟發佈登陸頁面 {#publish-the-landing-page}

測試成功後，您就可以使用控制面板中動作列 **[!UICONTROL Publish]**的按鈕來發佈著陸頁面。 監控塊顯示發佈的進展和狀態。

發佈著陸頁面可讓其線上存取。 發佈後，您隨時都可以更新：若要這麼做，您必須在每次修改後重新發佈。 您也可以隨時解除發佈著陸頁面，使其不再可用。

![](assets/lp-steps6.png)

發佈後，您的登陸頁面就可供使用。 然後，您可以設定不同的機制來訪問該機制，以便在資料庫中獲取新配置檔案或獲取有關現有配置檔案的其他資訊。

如需登陸頁面發佈的詳細資訊，請參 [閱本節](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page)。
