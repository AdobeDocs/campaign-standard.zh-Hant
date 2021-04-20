---
solution: Campaign Standard
product: campaign
title: '透過Adobe Campaign整合設計電子郵件 '
description: 瞭解如何透過電子郵件設計人員的Adobe Campaign整合來設計電子郵件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 6%

---


# 多解決方案電子郵件設計 {#multi-solution-email-design}

Adobe Campaign提供數種電子郵件編寫選項。 您可以使用Dreamweaver等解決方案，在電子郵件設計人員中編輯電子郵件內容並建立回應式訊息。 您也可以透過電子郵件傳送內容給Adobe Experience Manager，並在Adobe Campaign Standard的電子郵件中使用。

## 在Dreamweaver編輯內容{#editing-content-in-dreamweaver}

Adobe Campaign Standard與Dreamweaver的整合可讓您在Dreamweaver介面中編輯電子郵件內容。 您可以存取Dreamweaver的強大介面，來設計和開發互動式電子郵件內容。

* **雙向同步**

   每當在一個產品中進行編輯時，就會在另一個產品中即時更新。 如果您想要變更Dreamweaver文字的色彩，當您編輯時，文字的色彩就會在Campaign中即時顯示。 此外，當您在Dreamweaver或促銷活動中選取程式碼時，由於行號相同，因此這兩個產品之間的選擇仍會保留，這在尋找程式碼中的特定項目時非常有用。

* **透過 Dreamweaver 將本機影像上傳至 Adobe Campaign**

   在Dreamweaver建立或編輯電子郵件時，您只需從桌上型電腦或本機電腦選取影像即可。 雖然Dreamweaver一直允許您這麼做，但在Dreamweaver和促銷活動連線時，本機檔案會立即上傳至Adobe Campaign伺服器：不需要隨著內容變更手動上傳影像。 此外，它可確保最新影像永遠在Campaign中顯示。

* **在Dreamweaver新增Campaign個人化**

   對於電子郵件開發人員，您不再需要新增例如`[[FIRSTNAME_PLACEHOLDER]]`等文字，也不需要尋找資料模型表格的語法。 Dreamweaver的「促銷活動」工具列會直接連線至您的「促銷活動」例項的資料模型。 這表示您可以從「名字」到「地址」之類的項目，提取任何個人化所需的資料。 如果您已在促銷活動中建立內容區塊，您也可以將這些區塊直接拉入Dreamweaver。

此功能在可訪問[此處](https://helpx.adobe.com/tw/dreamweaver/using/working-with-dreamweaver-and-campaign.html)的Dreamweaver文檔中有詳細說明。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

## 在Experience Manager{#editing-content-in-experience-manager}中編輯內容

電子郵件內容可以Experience Manager編輯，然後用於Adobe Campaign Standard的一或多封電子郵件。 請參閱[此文件](../../integrating/using/integrating-with-experience-manager.md)。

## 產品清單{#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="使用產品清單"
>abstract="產品清單可讓您參考資料收集並顯示在電子郵件內容中。"

產品清單可讓您參考電子郵件內容中的一或多個資料集合。 這些清單可用於交易電子郵件。 此功能的專用部分[此處](../../designing/using/using-product-listings.md)。

## 電子郵件設計選項比較{#email-design-options-comparison}

Adobe Campaign提供數種電子郵件編寫選項。 下表顯示了每種方案的主要可能性、優點和限制。

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
   <td> <strong>編寫HTML</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> 僅限HTML元件內部<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>基本個人化</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 支援<br /> </td> 
   <td> 支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>進階個人化</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 不支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>校對／預覽</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 在促銷活AEM動中預覽<br />校對<br /> </td> 
   <td> 在促銷活動中預覽和校樣<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>產品清單</strong><br /> </td> 
   <td> 電子郵件事務性消息<br />支援 </td> 
   <td> 不支援<br /> </td> 
   <td> 不支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>優點</strong><br /> </td> 
   <td> 
     <p>-透過拖放體驗輕鬆建立電子郵件</p>
     <p>-類似於舊版內容編輯器的功能</p>
     <p>-可重複使用的內容及片段</p>
  </td> 
   <td> 
     <p>-在電子郵件中重複使用網站中的資產</p>
     <p>-運用電子郵件內容中的Experience Manager功能</p>
    </td> 
   <td> 
    <p>-讓開發人員直接編寫電子郵件程式碼</p>
    <p>-雙向同步</p>
    <p>-在Dreamweaver離線編輯，稍後進行同步化</p>
    <p>-透過Dreamweaver上傳影像至Adobe Campaign</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     <p>-片段中沒有條件內容</p>
     <p>-無法使用Experience Manager片段</p>
  </td> 
   <td> 
     <p>-難以實作的進階個人化</p>
     <p>-需要在Adobe Campaign</p>
  </td> 
   <td> 不支援的動態內容<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>閱聽眾</strong><br /> </td> 
   <td> 想要保持靈活彈性，搭配拖放功能使用HTML元件的行銷人員<br /> </td> 
   <td> 已使用Experience Manager的行銷人員，想要使用標準電子郵件範本，而且幾乎不需個人化<br /> </td> 
   <td> 想要撰寫電子郵件內容程式碼並直接與Adobe Campaign整合的開發人員<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>若要進一步瞭解</strong><br /> </td> 
   <td> 請參閱<a href="../../designing/using/designing-content-in-adobe-campaign.md">關於電子郵件設計器</a>。<br /> </td> 
   <td> 請參閱<a href="../../integrating/using/integrating-with-experience-manager.md">與Experience Manager</a>整合。<br /> </td> 
   <td> 請參閱<a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver和促銷活動</a>並觀看此<a href="#video">影片</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 教學課程影片{#video}

此影片示範如何使用Dreamweaver為Adobe Campaign Standard建立和編輯內容。

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

其他Campaign Standardhow-to影片可在[這裡](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)取得。
