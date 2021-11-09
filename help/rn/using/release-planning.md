---
title: Campaign Standard 發行計畫
description: 本頁列出 Adobe Campaign Standard 即將發行的版本。
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: 85c42129e105999483d23865f2534c90406251e4
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 74%

---

# 發行規劃 {#release-planning}

Adobe透過新增功能、增強功能和修正持續改善其解決方案。

所有 Adobe Campaign Standard 執行個體都會隨著每個新版本升級。升級不需要任何動作。

升級分兩個階段部署。首先，Stage例項已升級，可讓您測試新功能，並視需要調整您的設定。 然後會升級生產執行個體。

所有發行日期皆可能變更：請定期造訪本頁面，以檢查更新。

## 版本22.1 - 2022年2月發行 {#release-22-1-release}

環境更新會在以下指定時段內以波形進行。已透過電子郵件向每位客戶傳達確切日期。

有關此版本的詳細資訊，請參閱 [發行說明](../../rn/using/release-notes.md) 升級日期。

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
   <td>2022年2月8-9日<br /> </td>
  </tr>
  <tr>
   <td>生產<br /> </td>
   <td>2022年2月15至22日<br /> </td>
  </tr>
 </tbody>
</table>

如果您有任何其他問題，請聯絡 [Adobe Client Care](https://helpx.adobe.com/tw/enterprise/using/support-for-experience-cloud.html)。

## 問答集 {#questions-and-answers}

**問：影響是什麼？**

答：變更列在[發行版本](../../rn/using/release-notes.md)中，包括相關檔案的連結。Adobe 也建議參閱[已過時和已移除功能](../../rn/using/deprecated-features.md)頁面。這些頁面適用於 Stage 環境升級日期的新版本。

**問：什麼是驗證程式？**

答：當您的測試執行個體升級時，Adobe 建議驗證您的流程，且使用案例與此新版本搭配運作正常，並向 [Adobe Client Care](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) 報告任何問題。

**問：在升級過程中是否可以存取執行個體？**

答：否。在執行個體升級期間，數分鐘內可能無法存取資料庫。所有程序都會自動重新啟動。

**問：訊息是否會繼續傳送？**

答：否。幾分鐘內不會傳送訊息。升級完成後，進程將自動重新啟動。

**問：工作流程是否會繼續執行並傳送傳送？**

答：否。在建置升級期間，工作流程伺服器和 MTA 都會停止。因此，工作流程將不會執行，且傳送不會在幾分鐘內傳送。 無需執行任何操作：當執行個體升級後，工作流程就會重新啟動。

**問：在升級期間，追蹤訊息中的連結是否仍然有效？**

答：是，它們可正常運作。在升級期間無法傳送新電子郵件，但已傳送電子郵件中的追蹤連結將可運作。

**問：如何知道升級已完成？**

答：登入 Campaign 時，將會顯示版本通知快顯視窗及最新版本。

如有任何其他問題，請聯絡 [Adobe Client Care](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)。
