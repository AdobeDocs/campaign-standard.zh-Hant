---
title: 通過Adobe Campaign整合設計電子郵件
description: 瞭解如何通過電子郵件設計器中的Adobe Campaign整合來設計電子郵件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 8%

---

# 多解決方案電子郵件設計 {#multi-solution-email-design}

Adobe Campaign提供了幾個電子郵件創作選項。 您可以使用Dreamweaver等解決方案在電子郵件設計器中編輯電子郵件內容並建立響應消息。 您還可以向Adobe Experience Manager發送電子郵件內容，並在您在Adobe Campaign Standard的電子郵件中使用。

## 編輯Dreamweaver內容 {#editing-content-in-dreamweaver}

Adobe Campaign Standard與Dreamweaver的整合使您可以在Dreamweaver介面中編輯電子郵件內容。 您可以訪問Dreamweaver強大的介面來設計和開發快速響應的電子郵件內容。

* **雙向同步**

   每當在一個產品中進行編輯時，就會在另一個產品中即時更新。 如果要更改Dreamweaver中文本的顏色，一旦進行編輯，文本的顏色即會在「市場活動」中顯示。 此外，當您在Dreamweaver或市場活動中選擇代碼時，由於行號相同，因此在兩種產品之間仍會進行選擇，這在查找代碼中的特定內容時非常有用。

* **透過 Dreamweaver 將本機影像上傳至 Adobe Campaign**

   在Dreamweaver內建立或編輯電子郵件時，您只需從案頭或本地電腦中選擇影像。 雖然Dreamweaver始終允許您執行此操作，但當Dreamweaver和市場活動連接時，本地檔案會立即上載到Adobe Campaign伺服器：無需在內容更改時手動上載影像。 此外，它還確保最新影像始終處於「活動」中。

* **在Dreamweaver添加市場活動個性化**

   對於電子郵件開發人員，不再需要像 `[[FIRSTNAME_PLACEHOLDER]]` 也不能查找資料模型表的語法。 Dreamweaver市場活動工具欄直接連接到您的市場活動實例的資料模型。 這意味著您可以從名字到地址之類的東西中提取任何您想要個性化的資料。 如果您在市場活動中建立了內容塊，您也可以將這些內容塊直接拉入Dreamweaver。

這一功能在可查閱的Dreamweaver檔案中詳述 [這裡](https://helpx.adobe.com/tw/dreamweaver/using/working-with-dreamweaver-and-campaign.html)。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

## 在Experience Manager中編輯內容 {#editing-content-in-experience-manager}

電子郵件內容可以以Experience Manager方式編輯，然後用於Adobe Campaign Standard的一封或多封電子郵件。 請參閱[此文件](../../integrating/using/integrating-with-experience-manager.md)。

## 產品清單 {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="使用產品清單"
>abstract="產品清單可讓您參照資料集合並將其顯示在電子郵件內容中。"

產品清單允許您引用電子郵件內容中的一個或多個資料集合。 這些清單可用於事務性電子郵件。 此功能的專用部分可用 [這裡](../../designing/using/using-product-listings.md)。

## 電子郵件設計選項比較 {#email-design-options-comparison}

Adobe Campaign提供了幾個電子郵件創作選項。 下表顯示了每種辦法的主要可能性、好處和限制。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> 電子郵件設計工具<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>開始空白電子郵件</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 支援<br /> </td> 
   <td> 支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>寫HTML</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> 僅在HTML元件內<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本個性化</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 支援<br /> </td> 
   <td> 支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>高級個性化</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 不支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>校樣/預覽</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 預覽位AEM置<br /> 市場活動中的證明<br /> </td> 
   <td> 市場活動中的預覽和證明<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>產品清單</strong><br /> </td> 
   <td> 電子郵件事務性消息中支援<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 不支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>好處</strong><br /> </td> 
   <td> 
     <p> — 通過拖放體驗輕鬆構建電子郵件</p>
     <p> — 類似於舊式內容編輯器的功能</p>
     <p> — 可重用的帶片段內容</p>
  </td> 
   <td> 
     <p> — 在電子郵件中重新使用網站中的資產</p>
     <p> — 利用電子郵件內容中的Experience Manager功能</p>
    </td> 
   <td> 
    <p> — 開發人員直接編碼電子郵件的功能</p>
    <p> — 雙向同步</p>
    <p> — 在Dreamweaver離線編輯並稍後同步</p>
    <p> — 通過Dreamweaver向Adobe Campaign上傳影像</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     <p> — 片段中沒有條件內容</p>
     <p> — 無法使用Experience Manager片段</p>
  </td> 
   <td> 
     <p> — 難於實施的高級個性化</p>
     <p> — 需要在Adobe Campaign派test</p>
  </td> 
   <td> 不支援動態內容<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>閱聽眾</strong><br /> </td> 
   <td> 希望保持靈活性以將HTML元件與拖放功能結合使用的營銷商<br /> </td> 
   <td> 營銷人員已在使用希望使用標準電子郵件模板且很少個性化的Experience Manager<br /> </td> 
   <td> 希望編碼電子郵件內容並直接與Adobe Campaign整合的開發人員<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>瞭解更多資訊</strong><br /> </td> 
   <td> 請參閱 <a href="../../designing/using/designing-content-in-adobe-campaign.md">關於電子郵件設計器</a>。<br /> </td> 
   <td> 請參閱 <a href="../../integrating/using/integrating-with-experience-manager.md">與Experience Manager整合</a>。<br /> </td> 
   <td> 請參閱 <a href="https://helpx.adobe.com/tw/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver和競選</a> 看這個 <a href="#video">視頻</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 教程視頻 {#video}

此視頻顯示如何使用Dreamweaver為Adobe Campaign Standard建立和編輯內容。

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

可提供其他Campaign Standard操作視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)。
