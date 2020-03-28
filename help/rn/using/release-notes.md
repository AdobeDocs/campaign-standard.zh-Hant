---
title: 最新版本
description: 本頁列出Adobe Campaign Standard的所有最新版本。
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c4500832b87e986cdbbbf72b9b8c0591f64f7da8

---


# 最新版本{#latest-release}

[發行計畫](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |控 [制面板版本](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |文 [件更新](../../rn/using/documentation-updates.md) |先 [前的發行說明](../../rn/using/release-notes-2019.md) |已過 [時的功能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## 版本20.2 - 2020年3月 {#release-20-2---march-2020}

**新增功能?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob整合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure Blob儲存連接器現在可用來使用傳輸檔案工作流程活動，將資料匯入或匯 <strong>出至</strong> Adobe Campaign。 </p>
    <p>如需詳細資訊，請參閱詳 <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">細檔案</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>使用目標設定檔進行電子郵件測試</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>除了測試個人檔案外，您現在還可以在真正的目標個人檔案上測試電子郵件。 這可讓您獲得描述檔將會收到的訊息的精確表示：自訂欄位、動態和個人化資訊，包括工作流程的其他資料等。 </p>
    <p>如需詳細資訊，請參閱詳細 <a href="../../sending/using/testing-messages-using-target.md">的檔案</a> ，以及 <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">教學影片</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>新功能將於4月在「促銷活動控制面板」中發佈，包括Google TXT記錄管理、資料庫空間監控和電子郵件警報。 有關這些功能的詳細資訊，請參閱「 [Control Panel Release Note(控制面板發行說明](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html))」。

**改進**

* 交易式訊息使用者體驗已增強，介面一致性也已改善。 [閱讀更多資訊](../../channels/using/about-transactional-messaging.md)
* Campaign Standard現在可讓您使用工作流程的其他資料，將校樣傳送至測試描述檔。
* 外部API活動的護欄已更新。 [閱讀更多資訊](../../automating/using/external-api.md)

**電子郵件設計人員增強功能**

* 修正在個人化影像上多次點按時影響逸出的問題。
* 修正複製動態文字元件時，可能導致重複的黃字行的問題。 (CAMP-41249)
* 修正在表層級（而非div層級）定義填補時，Outlook中填補的問題。
* 修正在切換至HTML模式時，影像寬度被修改的問題。 (CAMP-41116)
* 修正當為圖示提供替代文字時，無法存取社交媒體元件的問題。 (CAMP-41345)
* 修正在「電子郵件設 `<br>` 計器」中使用複製貼上時，顯示可見標籤的問題。
* 修正從HTML內容切換為純文字後，HTML標籤顯示在電子郵件中的問題。 (CAMP-41138)
* 修正無法呈現只定義一個邊框之按鈕的問題。
* 修正HTML縮排中，造成Microsoft Outlook中電子郵件頁尾向左移動的問題。 (CAMP-40987)
* 修正當切換為純文字模式時，HTML中定義的系列屬性個人化欄位會複製到純文字內容的問題。 (CAMP-40365)
* 修正無法在選取的文字區段上插入連結的問題。 (CAMP-41406)
* 修正在查詢編輯器中選取時區時，日期變更的問題。 (CAMP-38277)

**其他變更**

* 「使 **用Adobe Analytics進行KPI協調** 」現在會執行至目前日期，而非在一天內執行。
* MCPNS不支援將APNS和APNS-SANDBOX新增為應用程式中的平台。 在Adobe Campaign Standard中成功新增憑證後，您現在無法再將設定變更回原來，因為MCPNS應用程式只能新增一個APNS平台（生產或沙盒）。

**體驗平台整合**

>[!NOTE]
>
>Campaign Standard中的Adobe Experience Platform功能目前為測試版，可能會經常更新，恕不另行通知。 請參閱詳細說明檔案：Experience Platform Data Connector [，觀眾](../../administration/using/aep-about-data-connector.md)[目標](../../audiences/using/aep-about-audience-destinations-service.md)

* 在工作流程記錄中，每10分鐘，Campaign現在會顯示目前執行中的工作已處理的記錄數。
* 修正匯入已從資料庫刪除的Adobe Experience Platform設定檔時可能發生的問題。
* 修正工作流程記錄中，針對匯入記錄總數顯示錯誤結果的問題。

**修補程式**

* 修正在「別名」欄位中新增空格 **後，接著建立新列項目時，Enrichment****** workflow活動可能發生的問題。 (CAMP-39229)
* 修正傳送證明訊息時，每個測試設定檔都可定位的問題。
* 修正取消發佈和刪除事件設定後發生的問題。 [閱讀更多資訊](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* 修正變更工作流程時 **「儲存** 」按鈕消失的問題。
* 修正在促銷活動處理後手動刪除隱私權要求時，即使在清除後，與要求相關的資料也無法刪除的問題。
* 修正預覽或傳送包含Adobe Experience Manager特殊字元之訊息時可能發生的問題。
* 修正執行具有數個傳入轉場的活動時，工作流程中可能發生的問題。