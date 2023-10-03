---
title: 最新版本
description: 本頁詳細說明最新 Campaign Standard 版本的內容
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1271bc0128c583e9b39ef98a422487e1df20fce
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 59%

---


# 最新版本{#latest-release}

![控制面板](assets/do-not-localize/cp-icon.png) **新控制面板版本**。 [了解更多](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=zh-Hant){target="_blank"}。



## 版本 23.2 - 2023 年秋冬發行 {#fall-23}

>[!AVAILABILITY]
>
>此版本僅適用於一組組織（可用性限制）。 如需詳細資訊，請聯絡您的Adobe代表。

### 功能改進 {#fall-23-rn-improvements}

* **與Adobe Experience Manager整合**. 在Adobe Experience Manager中建立異動訊息的個人化傳送範本時，您現在可以選取並使用下拉式清單中Campaign Standard定義的個人化欄位。 [了解更多](../../integrating/using/creating-email-experience-manager.md)

* **Cookie有效期**  — 預設Cookie有效期限現已設定為6個月，以符合法國資料保護局(CNIL)的建議。

* **設定檔搜尋改善**  — 已最佳化設定檔搜尋，以便減少搜尋逾時情況

* **本地化**  — 指稱一組設定檔以接收訊息時，「對象」一詞的翻譯在下列語言的所有數位體驗產品中得到協調：

   * 德文：Zielgruppe
   * 巴西葡萄牙文：público-alvo
   * 西班牙文：público destinatario

  這些變更將在下一個UI和檔案版本中逐步推出。


### 其他變更 {#fall-23-rn-other-changes}

* 異動訊息現在支援使用多個以逗號分隔的親和度。

### 修正 {#fall-23-rn-fixes}

* 修正了在使用大型工作流程時，可能導致效能問題的回歸。 (CAMP-53369)
* 修正工作流程警報或通知中的電子郵件連結無法運作的問題。 (CAMP-51874)

## 版本 23.1 - 2023 春/夏版 {#apr-23}

### 功能改進 {#e-rn-improvements}

* 推播訊息服務已經過現代化改造，以改善支援。 (CAMP-47959)
* 簡訊訊息傳送服務已經過改善，以提供更高的穩定性。(CAMP-52217)
* Adobe 已修復許多協助工具，以便提高應用程式的整體易用性。 以下是協助工具改善的幾個範例：
   * 許多畫面中的介面鍵盤協助工具已最佳化。
   * 已增強觸控螢幕使用者專用的應用程式。
   * 已變更介面數個項目的顏色，以便改善可見度。

### 其他變更 {#e-rn-changes}

* 已新增現成可用的&#x200B;**報告擴充建立工作流程**。 將目標對應從一個執行個體匯入另一個執行個體後，只要執行工作流程即可匯入對應的報告擴充項目。(CAMP-52452)

### 已修復的問題{#e-rn-patches}

* 修正在顯示&#x200B;**熱點點按**&#x200B;報告時可能導致超時錯誤的問題。(CAMP-51582)
* 修正可能導致您無法使用與&#x200B;**位置**&#x200B;服務整合的問題。(CAMP-51923)
* 修正可能導致工作流程排程器無法正常運作的問題。(CAMP-52003)
* 修正檢視含有大量資料之自訂動態報告的 PDF 版本時，無法顯示劃分詳細資料的問題。(CAMP-52178)
* 修正存取報告時可能顯示錯誤的問題。 (CAMP-52500)
* 修正誤將此帳戶 SMS 連接器參數的&#x200B;**限制 MTA 執行個體**&#x200B;套用到所有通道而非僅套用至 SMS 的問題。(CAMP-52640)
