---
title: 促銷活動標準發行計畫
description: 本頁列出Adobe Campaign Standard即將發行的版本。
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7cd5f11ab22d0bb3b6864670cd61007e39ebf543

---


# 發行計畫 {#release-planning}

Adobe透過新增功能、增強功能和修正不斷改進其解決方案。

所有Adobe Campaign Standard例項都會隨著每個新版本升級。 升級不需要任何動作。

升級分兩個階段部署。 首先，Stage實例已升級，可讓我們的客戶測試新功能並視需要調整其配置。 隨後將升級生產實例。

所有發行日期皆可能變更：我們建議您定期造訪本頁面，以檢查更新。

請訂閱以接 [收發行通知](https://www.adobe.com/subscription/priority-product-update.html) ，直接在您的收件匣中取得有關最新Adobe Experience Cloud發行的詳細資訊。

## 版本20.2.1 - 4月發行 {#release-20-2-april-release}

環境更新會在以下指定時段內以波形進行。 有關此版本的詳細資訊，請參閱版 [本說明](../../rn/using/release-notes.md)。 如果您有任何其他問題，請聯絡 [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin)。

<table> 
 <thead> 
  <tr> 
   <th> 環境<br /> </th> 
   <th> 日期<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Stage<br /> </td> 
   <td> 2020年3月31日至4月1日<br /> </td> 
  </tr> 
  <tr> 
   <td> 製作<br /> </td> 
   <td> 2020年4月6日至9日<br /> </td> 
  </tr> 
 </tbody> 
</table>



## 問題與解答 {#questions-and-answers}

**問：影響是什麼？**

答：變更列在發行說 [明中](../../rn/using/release-notes.md)，包括相關檔案的連結。 Adobe也建議參考「已過時 [和已移除功能」頁面](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。 這些頁面適用於Stage環境升級日期的新版本。

**問：什麼是驗證程式？**

答：當您的測試執行個體升級時，Adobe建議驗證您的流程，且使用案例與此新版本搭配運作正常，並向 [Adobe Client Care報告任何問題](https://support.neolane.net/webApp/extranetLogin)。

**問：在升級過程中是否可以訪問實例？**

答：不。 在實例升級期間，數分鐘內可能無法訪問資料庫。 所有進程都會自動重新啟動。

**問：訊息是否會繼續傳送？**

答：不。 幾分鐘內不會傳送訊息。 升級一完成，程式就會自動重新啟動。

**問：工作流程是否會繼續執行並傳送傳送？**

答：不。 在建置升級期間，工作流程伺服器和MTA都會停止。 這表示工作流程將不會執行，而且傳送不會在幾分鐘內傳送。 無需執行任何操作：當例項升級後，工作流程就會重新啟動。

**問：在升級期間，追蹤訊息中的連結是否仍然有效？**

答：是的，它們會起作用。 在升級期間無法傳送新電子郵件，但已傳送電子郵件中的追蹤連結將可運作。

**問：我要如何得知升級已完成？**

答：登入「促銷活動」時，將會顯示發行通知快顯視窗及最新版本。

如有任何其他問題，請連絡 [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin)。