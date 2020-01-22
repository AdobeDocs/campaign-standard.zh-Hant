---
title: '透過Adobe Campaign整合設計電子郵件 '
description: 瞭解如何透過電子郵件設計工具中的Adobe Campaign整合來設計電子郵件。
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# 多解決方案電子郵件設計 {#multi-solution-email-design}

Adobe Campaign提供數種電子郵件編寫選項。 您可以使用Dreamweaver等解決方案，在電子郵件設計工具中編輯您的電子郵件內容並建立回應式訊息。 您也可以使用Adobe Experience manager以電子郵件傳送內容，並在Adobe Campaign standard的電子郵件中使用。

## 在Dreamweaver中編輯內容 {#editing-content-in-dreamweaver}

與Dreamweaver整合的Adobe Campaign standard可讓您在Dreamweaver介面中編輯電子郵件內容。 您可以存取Dreamweaver的強大介面，來設計和開發互動式電子郵件內容。

* **雙向同步**

   每當在一個產品中進行編輯時，就會在另一個產品中即時更新。 如果您想要在Dreamweaver中變更文字的顏色，當您進行編輯時，文字的顏色就會在Campaign中即時顯示。 此外，當您在Dreamweaver或Campaign中選取程式碼時，由於行號相同，因此這兩個產品之間的選擇仍會保留，這在尋找程式碼中的特定項目時非常有用。

* **透過Dreamweaver將本機影像上傳至Adobe Campaign**

   在Dreamweaver中建立或編輯電子郵件時，您只需從桌上型電腦或本機電腦選取影像。 雖然Dreamweaver一律允許您這麼做，但是當Dreamweaver和Campaign連線時，本機檔案會立即上傳至Adobe Campaign伺服器：不需要隨著內容變更手動上傳影像。 此外，它可確保最新影像永遠在Campaign中顯示。

* **在Dreamweaver中新增Campaign個人化**

   對於電子郵件開發人員，您不再需要新增類似文字 `[[FIRSTNAME_PLACEHOLDER]]` ，也不需要尋找資料模型表格的語法。 Dreamweaver中的Campaign工具列會直接連線至您的Campaign例項的資料模型。 這表示您可以從「名字」到「地址」之類的項目，提取任何個人化所需的資料。 如果您已在Campaign中建立內容區塊，您也可以直接將這些區塊拖曳至Dreamweaver。

此功能在Dreamweaver說明檔案中有詳細 [說明](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html)。 此外，還 [提供](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html) 展示影片。

## 在Experience manager中編輯內容 {#editing-content-in-experience-manager}

您可以在Experience manager中編輯電子郵件內容，然後在Adobe Campaign standard中用於一或多則電子郵件訊息。 請參閱[此文件](../../integrating/using/integrating-with-experience-manager.md)。

## 電子郵件設計選項比較 {#email-design-options-comparison}

Adobe Campaign提供數種電子郵件編寫選項。 下表顯示了每種方案的主要可能性、優點和限制。

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer<br /> </th> 
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
   <td> 僅在HTML元件內<br /> </td> 
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
   <td> 在促銷活動的AEM<br /> Proof中預覽<br /> </td> 
   <td> 在Campaign中預覽和校樣<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>產品清單</strong><br /> </td> 
   <td> 電子郵件交易訊息支援<br /> </td> 
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
     <p>-運用Experience manager在電子郵件內容中的強大功能</p>
    </td> 
   <td> 
    <p>-讓開發人員直接編寫電子郵件程式碼</p>
    <p>-雙向同步</p>
    <p>-在Dreamweaver中離線編輯並稍後進行同步化</p>
    <p>-透過Dreamweaver將影像上傳至Adobe Campaign</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>限制</strong><br /> </td> 
   <td> 
     <p>-片段中沒有條件內容</p>
     <p>-無法使用Experience manager片段</p>
  </td> 
   <td> 
     <p>-難以實作的進階個人化</p>
     <p>-需要在Adobe Campaign中傳送測試</p>
  </td> 
   <td> 不支援動態內容<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>受眾</strong><br /> </td> 
   <td> 想要保留使用HTML元件與拖放功能結合的彈性的行銷人員<br /> </td> 
   <td> 已使用Experience Manager的行銷人員，希望使用標準電子郵件範本，而且幾乎不需個人化<br /> </td> 
   <td> 想要撰寫電子郵件內容程式碼並直接與Adobe Campaign整合的開發人員<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>若要進一步瞭解</strong><br /> </td> 
   <td> 請參 <a href="../../designing/using/designing-content-in-adobe-campaign.md">閱電子郵件設計工具</a>。<br /> </td> 
   <td> See <a href="../../integrating/using/integrating-with-experience-manager.md">Integrating with Experience Manager</a>.<br /> </td> 
   <td> 請參 <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">閱Dreamweaver和Campaign</a> ，並觀看此 <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">影片</a>。<br /> </td> 
  </tr> 
 </tbody> 
</table>
