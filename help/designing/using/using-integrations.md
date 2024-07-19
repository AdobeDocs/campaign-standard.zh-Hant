---
title: 透過Adobe Campaign整合設計電子郵件
description: 瞭解如何透過電子郵件Designer中的Adobe Campaign整合來設計電子郵件。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 5%

---

# 多解決方案電子郵件設計 {#multi-solution-email-design}

Adobe Campaign提供數種電子郵件製作選項。 您可以使用Dreamweaver等解決方案，編輯您的電子郵件內容，並在電子郵件Designer中建立回應式訊息。 您也可以使用Adobe Experience Manager以電子郵件傳送內容，並在Adobe Campaign Standard的電子郵件中使用。

## 在Dreamweaver中編輯內容 {#editing-content-in-dreamweaver}

Adobe Campaign Standard與Dreamweaver的整合可讓您在Dreamweaver介面中編輯電子郵件內容。 您可以存取Dreamweaver的強大介面，以設計和開發回應式電子郵件內容。

* **雙向同步**

  每當在某個產品中進行編輯時，就會即時更新另一個產品的編輯。 如果您想要在Dreamweaver中變更文字的顏色，只要您進行編輯，文字的顏色就會在Campaign中即時顯示。 此外，當您在Dreamweaver或Campaign中選取程式碼時，由於行號相同，因此選取範圍會保留在兩個產品之間，這在程式碼中尋找特定專案時非常有用。

* **透過Dreamweaver將本機影像上傳至Adobe Campaign**

  在Dreamweaver中建立或編輯電子郵件時，您只需從桌上型電腦或本機電腦中選取影像即可。 雖然Dreamweaver一律可讓您這麼做，但當Dreamweaver與Campaign連線時，本機檔案會立即上傳至Adobe Campaign伺服器：當內容變更時，不需要手動上傳影像。 此外，這可確保在Campaign中一律即時顯示最新影像。

* **在Dreamweaver中新增行銷活動個人化**

  對於電子郵件開發人員而言，不再需要新增`[[FIRSTNAME_PLACEHOLDER]]`之類的文字，也不需要查詢資料模型表格的語法。 Dreamweaver中的Campaign工具列會直接連線至您Campaign執行個體的資料模型。 這表示您可以從「名字」之類的「地址」提取任何您想要的個人化資料。 如果您已在Campaign中建立內容區塊，您也可以將這些區塊直接提取至Dreamweaver。

此功能在[此處](https://helpx.adobe.com/tw/dreamweaver/using/working-with-dreamweaver-and-campaign.html)存取的Dreamweaver檔案中有詳細說明。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

## 在Experience Manager中編輯內容 {#editing-content-in-experience-manager}

您可以在Experience Manager中編輯電子郵件內容，然後在Adobe Campaign Standard中用於一或多封電子郵件訊息。 請參閱[此文件](../../integrating/using/integrating-with-experience-manager.md)。

## 產品清單 {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="使用產品清單"
>abstract="產品清單可讓您參照資料集合並將其顯示在電子郵件內容中。"

產品清單可讓您參照電子郵件內容中的一個或多個資料集合。 這些清單可用於交易式電子郵件。 [此處](../../designing/using/using-product-listings.md)提供此功能的專屬區段。

## 電子郵件設計選項比較 {#email-design-options-comparison}

Adobe Campaign提供數種電子郵件製作選項。 下表顯示每種裝置的主要可能性、優點與限制。

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
   <td> 僅在HTML元件<br />內 </td> 
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
   <td> <strong>校訂/預覽</strong><br /> </td> 
   <td> 支援<br /> </td> 
   <td> 在Campaign<br />的AEM<br />校訂中預覽 </td> 
   <td> 在Campaign<br />中預覽和校訂 </td> 
  </tr> 
  <tr> 
   <td> <strong>產品清單</strong><br /> </td> 
   <td> 電子郵件異動訊息中支援<br /> </td> 
   <td> 不支援<br /> </td> 
   <td> 不支援<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>福利</strong><br /> </td> 
   <td> 
     <p> — 透過拖放體驗輕鬆建立電子郵件</p>
     <p> — 與舊版內容編輯器類似的功能</p>
     <p> — 片段可重複使用的內容</p>
  </td> 
   <td> 
     <p> — 在電子郵件中重複使用來自網站的資產</p>
     <p> — 運用電子郵件內容中Experience Manager的強大功能</p>
    </td> 
   <td> 
    <p> — 開發人員可直接為電子郵件編碼</p>
    <p> — 雙向同步處理</p>
    <p> — 在Dreamweaver中離線編輯並於稍後同步</p>
    <p> — 透過Dreamweaver將影像上傳至Adobe Campaign</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     <p> — 片段中沒有條件式內容</p>
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
   <td> 想要保持彈性以搭配拖放功能使用HTML元件的行銷人員<br /> </td> 
   <td> 行銷人員已使用Experience Manager，而他們想要使用基本個人化的標準電子郵件範本<br /> </td> 
   <td> 想要編碼電子郵件內容並直接與Adobe Campaign<br />整合的開發人員 </td> 
  </tr> 
  <tr> 
   <td> <strong>進一步瞭解</strong><br /> </td> 
   <td> 檢視<a href="../../designing/using/designing-content-in-adobe-campaign.md">關於電子郵件Designer</a>.<br /> </td> 
   <td> 請參閱<a href="../../integrating/using/integrating-with-experience-manager.md">與Experience Manager</a>整合。<br /> </td> 
   <td> 觀看<a href="https://helpx.adobe.com/tw/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver和Campaign</a>並觀看此<a href="#video">影片</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 教學課程影片 {#video}

本影片說明如何使用Dreamweaver建立和編輯Adobe Campaign Standard的內容。

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)提供其他Campaign Standard操作說明影片。
