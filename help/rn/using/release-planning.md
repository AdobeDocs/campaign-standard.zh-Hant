---
solution: Campaign Standard
product: campaign
title: Campaign Standard 發行計畫
description: 本頁列出 Adobe Campaign Standard 即將發行的版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 100%

---


# 發行計畫 {#release-planning}

Adobe 透過新增功能、增強功能和修正不斷改進其解決方案。

所有 Adobe Campaign Standard 執行個體都會隨著每個新版本升級。升級不需要任何動作。

升級分兩個階段部署。首先，Stage 執行個體已升級，可讓我們的客戶測試新功能並視需要調整其配置。隨後將升級生產執行個體。

所有發行日期皆可能變更：我們建議您定期造訪本頁面，以檢查更新。

**新增功能！**&#x200B;訂閱 [Campaign Standard 發行通知](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU)，直接在收件匣中取得有關即將發行的詳細資訊。

## 版本 21.1 - 2 月發行{#release-21-1-release}

環境更新會在以下指定時段內以波形進行。有關此版本的詳細資訊，請參閱[版本說明](../../rn/using/release-notes.md)。如果您有任何其他問題，請聯絡 [Adobe Client Care](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)。

<table>
 <thead>
  <tr>
   <th> 環境<br /> </th>
   <th> 日期<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Stage<br /> </td>
   <td>2021 年 1 月 25 日至 27 日<br /> </td>
  </tr>
  <tr>
   <td> 製作<br /> </td>
   <td>2021 年 2 月 1 日至 8 日<br /> </td>
  </tr>
 </tbody>
</table>

## 問題與解答 {#questions-and-answers}

**問：影響是什麼？**

答：變更列在[發行版本](../../rn/using/release-notes.md)中，包括相關檔案的連結。Adobe 也建議參閱[已過時和已移除功能](../../rn/using/deprecated-features.md)頁面。這些頁面適用於 Stage 環境升級日期的新版本。

**問：什麼是驗證程式？**

答：當您的測試執行個體升級時，Adobe 建議驗證您的流程，且使用案例與此新版本搭配運作正常，並向 [Adobe Client Care](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html) 報告任何問題。

**問：在升級過程中是否可以存取執行個體？**

答：否。在執行個體升級期間，數分鐘內可能無法存取資料庫。所有程序都會自動重新啟動。

**問：訊息是否會繼續傳送？**

答：否。幾分鐘內不會傳送訊息。升級一完成，程式就會自動重新啟動。

**問：工作流程是否會繼續執行並傳送傳送？**

答：否。在建置升級期間，工作流程伺服器和 MTA 都會停止。這表示工作流程將不會執行，而且傳送不會在幾分鐘內傳送。無需執行任何操作：當執行個體升級後，工作流程就會重新啟動。

**問：在升級期間，追蹤訊息中的連結是否仍然有效？**

答：是，它們可正常運作。在升級期間無法傳送新電子郵件，但已傳送電子郵件中的追蹤連結將可運作。

**問：我要如何得知升級已完成？**

答：登入 Campaign 時，將會顯示版本通知快顯視窗及最新版本。

如有任何其他問題，請聯絡 [Adobe Client Care](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)。
