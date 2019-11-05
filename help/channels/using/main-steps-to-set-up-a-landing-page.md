---
title: 設定登錄頁面的主要步驟
description: 瞭解設定著陸頁面的主要步驟
page-status-flag: 從未激活
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: 勒梅特
products: SG_CAMPAIGN/STANDARD
audience: 頻道
content-type: 參考
topic-tags: 著陸頁面
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 設定登錄頁面的主要步驟 {#main-steps-create-a-landing-page}

## 關於建立著陸頁面

設定著陸頁面的主要步驟如下：

![](assets/lp_steps.png)

在本頁中，您將會找到這些步驟的相關資訊，以及專用檔案的參考，以取得更多詳細資訊。

## 設定著陸頁面範本 {#configure-the-landing-page-template}

設定著陸頁面之前，第一步是設定符合您需求的著陸頁面範本。 範本準備就緒後，所有以該範本為基礎的著陸頁面都會預先設定所需參數。

1. 從進階功能表，透過Adobe Campaign標誌，選取 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]**，然後複製您要使用的範本。
1. 在範本屬性中，指定著陸頁面必須具有的所有共同參數。 例如：定位維度、已識別或未識別訪客的頁面存取參數、訪客進行表單驗證的特定動作、內容中使用的品牌／標誌等。
1. 儲存您的修改。

如需著陸頁面範本的詳細資訊，請參 [閱本節](../../channels/using/about-landing-pages.md)。

![](assets/lp-steps1.png)

## 建立並設定著陸頁面 {#create-and-configure-the-landing-page}

從上一步驟中定義的範本，在方案或促銷活動中建立新的著陸頁面。

1. 根據所要的範本建立著陸頁面。
1. 輸入著陸頁面的一般參數（標籤、說明等）。
1. 接著您將存取著陸頁面控制面板。 視需要編輯著陸頁面屬性。 依預設，屬性是著陸頁面範本中設定的屬性。
基於安全性原因和平台效能，強烈建議您在著陸頁面屬性中設定到期日。 完成後，著陸頁面將在選取的日期自動取消發佈。 For more on validity parameters, refer to [this section](../../channels/using/sharing-a-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >您的修改僅對正在編輯的著陸頁面有效。 如果您想要將這些修改套用至其他著陸頁面，您可以在專用的範本中執行這些修改，然後從該範本建立其他著陸頁面。

## 設計著陸頁面 {#design-the-landing-page}

您現在可以定義著陸頁面的內容。 依預設，著陸頁面包含三個可透過捲動箭頭存取的頁面：主要內容頁面、確認頁面和錯誤頁面。

![](assets/lp-steps4.png)

每個頁面上預設會設定數個欄位。 如有必要，您可以編輯其屬性和對應。

您也可以設定在個人檔案按一下確認按鈕後，其行為方式，並根據您的需求（影像、個人化欄位等）個人化內容。 例如，您可以在登陸頁面的確認頁面上插入描述檔的名字，以感謝他們註冊。

如需著陸頁面設計的詳細資訊，請參閱 [本節](../../channels/using/designing-a-landing-page.md)。

## 測試著陸頁面 {#test-the-landing-page}

一旦定義著陸頁面後，您就可以模擬其執行方式，並在登陸頁面可線上使用時加以動作。

![](assets/lp-steps5.png)

>[!CAUTION]
>
>著陸頁面測試只能使用描述檔進行，而不能使用測試描述檔。 提交表單時，選取的描述檔資料將會實際更新。 若要避免修改真實的個人檔案，請使用假的客戶個人檔案。

如果您對著陸頁面的運作方式感到滿意，可以發佈它，讓它線上上使用。

如需如何測試著陸頁面的詳細資訊，請參閱 [本節](../../channels/using/sharing-a-landing-page.md#testing-the-landing-page-)。

## 發佈登陸頁面 {#publish-the-landing-page}

測試成功後，您就可以使用控制面板中動作列 **[!UICONTROL Publish]** 的按鈕來發佈著陸頁面。 監控塊顯示發佈的進展和狀態。

發佈著陸頁面可讓其線上存取。 發佈後，您隨時都可以更新：若要這麼做，您必須在每次修改後重新發佈。 您也可以隨時解除發佈著陸頁面，使其不再可用。

![](assets/lp-steps6.png)

發佈後，您的登陸頁面就可供使用。 然後，您可以設定不同的機制來訪問該機制，以便在資料庫中獲取新配置檔案或獲取有關現有配置檔案的其他資訊。

如需登陸頁面發佈的詳細資訊，請參 [閱本節](../../channels/using/sharing-a-landing-page.md#publishing-a-landing-page)。
