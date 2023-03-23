---
title: 透過Adobe Campaign整合設計電子郵件
description: 了解如何透過電子郵件設計工具中的Adobe Campaign整合來設計電子郵件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 8%

---

# 多解決方案電子郵件設計 {#multi-solution-email-design}

Adobe Campaign提供數個電子郵件編寫選項。 您可以使用Dreamweaver等解決方案，在電子郵件設計工具中編輯電子郵件內容並建立回應式訊息。 您也可以透過Adobe Experience Manager傳送電子郵件內容，並在Adobe Campaign Standard的電子郵件中使用。

## 在Dreamweaver中編輯內容 {#editing-content-in-dreamweaver}

Adobe Campaign Standard與Dreamweaver的整合可讓您在Dreamweaver介面中編輯電子郵件內容。 您可以存取Dreamweaver的強大介面，以設計和開發回應式電子郵件內容。

* **雙向同步**

   每當在一個產品中進行編輯時，就會在另一個產品中即時更新。 如果您想在Dreamweaver中變更文字的顏色，一旦您進行編輯，文字的顏色就會在Campaign中即時顯示。 此外，當您在Dreamweaver或Campaign中選取程式碼時，由於行號相同，因此選取項目會保留在兩個產品之間，這對尋找程式碼中的特定項目非常有用。

* **透過 Dreamweaver 將本機影像上傳至 Adobe Campaign**

   在Dreamweaver中建立或編輯電子郵件時，您只需從案頭或本機電腦選取影像即可。 雖然Dreamweaver一律允許您這麼做，但在連線Dreamweaver和Campaign時，本機檔案會立即上傳至Adobe Campaign伺服器：內容變更時，無需手動上傳影像。 此外，還可確保最新影像一律在Campaign中上線。

* **在Dreamweaver中新增Campaign個人化**

   對於電子郵件開發人員，不再需要新增 `[[FIRSTNAME_PLACEHOLDER]]` 也不需要查詢資料模型表格的語法。 Dreamweaver中的Campaign工具列會直接連線至您的Campaign執行個體的資料模型。 這表示您可以從名字到地址之類的項目，提取任何您想要的個人化資料。 如果您已在Campaign中建立內容區塊，您也可以直接將這些區塊提取至Dreamweaver。

此功能在Dreamweaver檔案（可存取）中有詳細說明 [此處](https://helpx.adobe.com/tw/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

## 編輯Experience Manager {#editing-content-in-experience-manager}

您可以以Experience Manager編輯電子郵件內容，然後用於Adobe Campaign Standard中的一或多則電子郵件訊息。 請參閱[此文件](../../integrating/using/integrating-with-experience-manager.md)。

## 產品清單 {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="使用產品清單"
>abstract="產品清單可讓您參照資料集合並將其顯示在電子郵件內容中。"

產品清單可讓您參考電子郵件內容中的一或多個資料集合。 這些清單可用於交易式電子郵件。 此功能的專屬區段已推出 [此處](../../designing/using/using-product-listings.md).

## 電子郵件設計選項比較 {#email-design-options-comparison}

Adobe Campaign提供數個電子郵件編寫選項。 下表顯示了每種方法的主要可能性、優點和限制。

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
   <td> <strong>寫入HTML</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>更新HTML</strong><br /> </td> 
   <td> 僅限HTML元件內<br /> </td> 
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
   <td> <strong>校樣/預覽</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 在AEM中預覽<br /> Campaign中的校樣<br /> </td> 
   <td> 在Campaign中預覽和校樣<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>產品清單</strong><br /> </td> 
   <td> 電子郵件交易式訊息支援<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 不支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>好處</strong><br /> </td> 
   <td> 
     <p> — 透過拖放體驗輕鬆建立電子郵件</p>
     <p> — 類似於舊版內容編輯器的功能</p>
     <p> — 可重複使用的內容及片段</p>
  </td> 
   <td> 
     <p> — 在電子郵件中重複使用網站中的資產</p>
     <p> — 運用電子郵件內容中Experience Manager的強大功能</p>
    </td> 
   <td> 
    <p> — 開發人員直接為電子郵件編碼的功能</p>
    <p> — 雙向同步</p>
    <p> — 在Dreamweaver中離線編輯及稍後同步</p>
    <p> — 透過Dreamweaver將影像上傳至Adobe Campaign</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     <p> — 片段內沒有條件式內容</p>
     <p> — 無法使用Experience Manager片段</p>
  </td> 
   <td> 
     <p> — 難以實作的進階個人化</p>
     <p> — 需要在Adobe Campaign中傳送測試</p>
  </td> 
   <td> 不支援動態內容<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>閱聽眾</strong><br /> </td> 
   <td> 行銷人員想要有彈性地搭配拖放功能使用HTML元件<br /> </td> 
   <td> 行銷人員已使用Experience Manager，但想要使用標準電子郵件範本，而幾乎不提供個人化內容<br /> </td> 
   <td> 想要編寫電子郵件內容程式碼並直接與Adobe Campaign整合的開發人員<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>若要深入了解</strong><br /> </td> 
   <td> 請參閱 <a href="../../designing/using/designing-content-in-adobe-campaign.md">關於電子郵件設計工具</a>.<br /> </td> 
   <td> 請參閱 <a href="../../integrating/using/integrating-with-experience-manager.md">與Experience Manager整合</a>.<br /> </td> 
   <td> 請參閱 <a href="https://helpx.adobe.com/tw/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver和Campaign</a> 看這個 <a href="#video">影片</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 教學課程影片 {#video}

此影片說明如何使用Dreamweaver建立和編輯Adobe Campaign Standard的內容。

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

提供其他Campaign Standard作法影片 [此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant).
