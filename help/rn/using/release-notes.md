---
solution: Campaign Standard
product: campaign
title: 最新版本
description: 本頁詳細說明最新 Campaign Standard 版本的內容
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: 概覽
role: Business Practitioner
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: e4d5be678b49af649bd4d4dabd83bff04c675d9f
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 6%

---

# 最新版本{#latest-release}

## 發行版本21.2 – 2021 年 6 月{#release-21-2---june-2021}

下一個Campaign Standard版本包含的新功能、改良和修正項目會列在[搶鮮版發行說明](e-release-notes.md)中。

**功能改善**

* 設計登錄頁面時，您現在可以新增必要核取方塊，要求設定檔在提交表單前先選取該核取方塊。 如需詳細資訊，請參閱[詳細文件](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)。

* 針對觸發器整合，已改善觸發裝載中沒有調解資料時顯示的錯誤訊息：&quot;裝載中缺少別名資料&quot;。

* 已改善從佇列擷取推播通知的效能。

**其他變更**

* 已停用追蹤連結的URL簽章機制，以防止在第三方安全工具修改後，造成某些有效且已簽署的追蹤連結遭到錯誤封鎖的問題。

* 在多變體傳送中，如果已刪除預設變體，則使用者無法再建立語言副本。 現在會在語言副本建立期間顯示訊息。 (CAMP-48235)

* 現在預設會停用兩步驟設定檔刪除程式（自Campaign 19.4版本起即淘汰）。 之前，您必須先從Campaign介面手動停用，才能使用隱私權核心服務。 若未這麼做，會導致刪除請求在未完成的情況下維持擱置狀態。

* 引入新的「StringAgg」匯總函式以串連字串類型欄的值。 (CAMP-47077)[ 進一步瞭解](../../automating/using/list-of-functions.md#aggregates)

* 在動態報表中，已移除&#x200B;**排除校樣**&#x200B;區段。 (CAMP-46161)

* 已新增警告訊息，以在上傳iOS憑證時（未在Campaign應用程式中使用platformPrincipal值）通知使用者。

* 電子郵件的最大大小現在預設為100 MB。 此限制可防止任何可能無限增加電子郵件大小而導致系統當機的錯誤。 (CAMP-47445)[ 進一步瞭解](../../sending/using/design-and-personalize.md#email-size)

* 標準使用者現在可以使用與電子郵件設計工具的資產核心服務整合。

* 已新增新訊息，以確認成功從v4推送應用程式移轉至v5推送應用程式。

* 在建立JSONWeb Token以驗證Campaign StandardAPI期間，產品設定檔現在為&#x200B;**被視為**。 這表示分配給安全性群組（符合AdobeIO上的產品設定檔）的組織單位和角色，將套用至Campaign Standard休息API呼叫所需的IMS技術帳戶。 (CAMP-47479)

**修補程式**

* 修正了無法套用批次處理記錄表(**xtkjoblog**)表之到期選項的問題。 這會使表無法正確清除。

* 修正無法變更&#x200B;**Segmentation**&#x200B;工作流程活動中篩選器順序的問題。 (CAMP-48357)

* 修正20.4的回歸，該回歸可能導致傳遞失敗，並產生null值錯誤。 (CAMP-48591)

* 修正無法透過&#x200B;**共用** > **立即傳送報表**&#x200B;或&#x200B;**依排程傳送報表**&#x200B;功能表傳送報表的問題。 (CAMP-47798)

* 修正了因篩選從Gmail帳戶收到的追蹤事件而可能導致Gmail開啟率不正確的回歸。 (CAMP-46504)

* 修正Adobe Campaign Standard中的報表與Adobe Analytics中的報表之間資料不一致的各種問題。 (CAMP-47671, CAMP-47296)

* 修正準備失敗後無法存取傳送記錄的問題。 (CAMP-48296)

* 修正嘗試編輯、刪除或傳送自訂報表時，可能顯示錯誤訊息的問題。 (CAMP-47789, CAMP-47798)

* 修正建立新自訂資源並啟用&#x200B;**Do not synchronize**&#x200B;選項時，API呼叫失敗的問題。 (CAMP-48014)

* 修正啟用&#x200B;**Do not synchronize**&#x200B;選項的自訂資源可參考已重新起草或刪除的架構的問題。 此問題會在發佈自訂資源時造成錯誤。

* 修正在相同外部帳戶上使用多個短代碼時，SMS選擇退出的問題。

* 修正發佈資料庫後，無法存取新傳送警報准則（「您嘗試存取的資源無法連線」）的問題。 (CAMP-48221)

* 修正某些具有動態報告的Campaign執行個體中缺少追蹤記錄的問題。 已新增新的[技術工作流程](../../administration/using/technical-workflows.md)，以還原這些追蹤記錄。 (CAMP-47885)

* 修正動態報告中未顯示傳送資料的問題。 報表已設為0。 (CAMP-47480)

* 修正伺服器JavaScript HTTP用戶端無法連線至外部URL的問題。

* 修正在變更工作流程的內部名稱后，重設&#x200B;**增量查詢**&#x200B;活動的問題。 將日期欄位用作增量模式時，就會發生此問題。 (CAMP-47674)

* 修正當使用Adobe Experience Manager整合建立多語言電子郵件時，傳送摘要無法顯示預覽縮圖的問題。 使用&#x200B;**語言副本建立**&#x200B;按鈕建立電子郵件變體時，會發生此問題。 (CAMP-47810)

* 修正使用者無法從電子郵件或簡訊子傳送存取父傳送的問題。 (CAMP-47986)

* 修正透過REST API傳送交易式訊息，但遺失自訂事件時，可能導致CPU和記憶體耗用過量的問題。 (CAMP-47147)

* 修正交易式訊息API錯誤，該錯誤有時會阻止即時訊息的傳送。

* 修正使用&#x200B;**依排程傳送報表**&#x200B;選項後未收到報表的問題。 (CAMP-48583, CAMP-47786)

* 修正使用&#x200B;**立即傳送報表選項**&#x200B;後收到的報表不完整且遺失資料的問題。 (CAMP-48583)

* 修正電子郵件設計工具上傳影像時，影像的維度縮小的問題。 (CAMP-47017)

* 修正建立傳送時，無法顯示所有可用Experience Manager範本的問題。 (CAMP-48132)

* 修正傳送之「摘要」頁面中的「促銷活動」連結無法將使用者重新導向至相關促銷活動的錯誤。 (CAMP-48012)

* 修正電子郵件設計工具中，當嘗試選取資產時，資產核心服務整合持續失敗的問題。 (CAMP-47446)

* 修正由於促銷活動不支援來自Journey Orchestration之事件所傳送具有確切值（即結尾為00）的時間戳記，而封鎖某些Journey Orchestration傳送的問題。
