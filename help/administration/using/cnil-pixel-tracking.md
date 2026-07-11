---
title: CNIL對電子郵件追蹤畫素的指引
description: 瞭解CNIL關於電子郵件追蹤畫素的更新指引，以及可支援您合規努力的Adobe Campaign Standard控制項。
audience: administration
role: Admin
level: Experienced
hide: true
source-git-commit: 75f1f4ad8f7173f4601c9cff1ea93bf4092f274d
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 0%

---


# 瞭解CNIL更新的電子郵件追蹤畫素指南 {#cnil-pixel-tracking}

>[!BEGINSHADEBOX]

**在此頁面上：**&#x200B;瞭解CNIL於2026年4月關於電子郵件追蹤畫素的建議，並探索Adobe Campaign Standard控制項 — 追蹤啟動、連結層級追蹤、同意資料模型、選擇退出機制和報告 — 以支援您的合規工作。

>[!ENDSHADEBOX]

這篇文章僅供參考。 這不是法律建議，也不保證您遵守適用法律。 底下所述的Adobe Campaign Standard產品功能是建置區塊，若妥善設定和運作，可支援相容的實作。 每位客戶都有責任決定及遵守其適用法律義務。

## 概觀 {#overview}

在2026年4月14日，法國資料保護機構&#x200B;*全國資訊與自由委員會* (CNIL)發佈了一項關於在電子郵件中使用追蹤畫素的[建議](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)。 此指引澄清何時需要同意，並強調正確同意實務對於電子郵件畫素追蹤的重要性。 此政策可能會影響任何實體傳送電子郵件給法國訂閱者的傳送實務。

CNIL從建議之日起提供三個月的時間，讓公司通知其電子郵件收件者（「使用者」）追蹤畫素的存在、其目的和使用者選擇退出的權利。 在此轉換期間，客戶應通知使用者畫素追蹤的相關資訊，並視需要提供選擇退出。 預計CNIL將在2026年7月14日之後開始執行活動。

隨著CNIL和其他監管機構釐清追蹤畫素和相關問題的指引，Adobe將繼續監控更新，並通知客戶支援Adobe Campaign Standard等電子郵件行銷的Adobe產品的技術功能。

Adobe電子郵件行銷執行應用程式，包括Adobe Journey Optimizer、Journey Optimizer B2B、Adobe Campaign和Marketo Engage，可提供可協助客戶在傳送或電子郵件層級管理開啟追蹤的控制項。 根據適用的CNIL指引和其他法律，客戶有責任決定自己的合規義務，但這些功能可能會支援客戶合規工作。

### 什麼是電子郵件追蹤畫素 {#tracking-pixel}

電子郵件追蹤畫素是內嵌在電子郵件HTML中的1x1透明影像。 收件者的電子郵件使用者端載入該影像時，畫素會偵測伺服器並記錄時間戳記、裝置型別、電子郵件使用者端等資料，有時還會偵測大致位置的IP位址。 然後，該記錄會繫結至收件者的記錄，讓行銷人員檢視電子郵件是否已開啟。

### 客戶支援 {#support}

尋求協助實作上述變更的客戶可與其現有的Adobe生態系統互動。 如有關於所引用Adobe功能的技術問題，請聯絡您的客戶成功經理或技術客戶經理。

## 與電子郵件追蹤相關的Adobe Campaign Standard功能 {#acs-functionality}

客戶在設定架構時，可以使用Adobe Campaign Standard的原生追蹤、結構描述和個人化機制來處理某些元素。

### 電子郵件分類 {#email-classification}

使用自訂欄位來擴充傳送範本，以指出電子郵件的型別（驗證、僅限傳送能力、異動、有同意的行銷、B2B潛在客戶）。 在Campaign Standard中，傳遞範本可包含流入報表和工作流程邏輯的自訂欄位。 此分類會決定每個傳送適合哪種追蹤。

[瞭解如何建立及使用傳遞範本](../../channels/using/creating-an-email.md)

### 同意資料模型 {#consent-data-model}

透過Campaign Standard自訂資源機制（**管理>開發>自訂資源**）擴充設定檔資源，以包含每個用途的同意標幟、同意時間戳記和最近開啟的日期（僅限日期 — 無時間元件）。 連結至設定檔的個別自訂資源會擷取支援個別同意證明的僅附加同意事件記錄。 由於Campaign Standard登入頁面可以直接寫入設定檔欄位，因此目前的同意狀態是可控的；提交偏好設定後，同意記錄會透過Adobe Campaign Standard REST API (`/profileAndServicesExt`)寫入。

[瞭解如何建立或擴充資源](../../developing/using/creating-or-extending-the-resource.md)

[瞭解如何透過API與自訂資源互動](../../api/using/interacting-with-custom-resources.md)

### 畫素發光 {#pixel-emission}

Adobe Campaign Standard透過傳遞或範本屬性中的&#x200B;**[!UICONTROL Activate tracking]**&#x200B;切換在傳遞層級控制追蹤。 對於開啟追蹤不合法的傳遞（僅限驗證、重新請求電子郵件），此切換為停用。 對於適合使用個別用途畫素放射的傳送，一種方法是停用標準自動插入畫素，並使用包含條件1×1追蹤影像元素（每個用途一個）的內容區塊，其中每個影像會獲派URL類別(`PIX_DELIV`、`PIX_PERF`、`PIX_PROFILE`、`PIX_FRAUD`)，且僅當收件者的對應同意旗標為true時才會顯示。

[瞭解如何設定電子郵件追蹤引數](configuring-email-channel.md#tracking-parameters)

[瞭解如何在電子郵件Designer中管理追蹤的URL](../../designing/using/links.md#about-tracked-urls)

[瞭解如何新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)

### 撤銷 {#withdrawal}

將&#x200B;**管理追蹤器偏好設定**&#x200B;連結新增至每個電子郵件頁尾，區別於取消訂閱連結。 連結指向透過`recipientId`或`urlSubscription`機制驗證的Campaign Standard登陸頁面；收件者切換其針對不同用途的同意標幟並提交。 確認時，對Campaign Standard REST API的小型呼叫會將撤銷事件寫入同意記錄。 建議指出此連結本身可免除追蹤需求的安全性。

[瞭解如何設定選擇加入和選擇退出登入頁面](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)

[瞭解如何開始使用登入頁面](../../channels/using/getting-started-with-landing-pages.md)

### 同意證明 {#consent-proof}

每個同意變更（註冊時擷取、從偏好設定頁面更新、到期）都會在同意記錄自訂資源中建立一列，其中會包含措辭的版本代碼、擷取時間戳記、擷取來源和範圍。 此記錄可透過Campaign Standard Explorer查詢、透過REST API公開，並可透過排程的工作流程匯出，以供DPO檢閱。

[瞭解如何透過API與自訂資源互動](../../api/using/interacting-with-custom-resources.md)

### 重新請求控管 {#re-solicitation}

設定檔上的自訂`cusLastPixelRefusalDate`欄位，加上排除該欄位在選定期間內之設定檔的型別篩選規則，可防止重新向在此期間拒絕的收件者請求。 排程的工作流程會標籤過時記錄並將到期事件寫入同意記錄，藉此管理客戶的同意到期時間範圍。

[瞭解如何使用型別規則](../../sending/using/about-typology-rules.md)

[瞭解如何管理型別規則](../../sending/using/managing-typology-rules.md)

### 報告 {#reporting}

Campaign Standard動態報表是以URL類別和設定檔維度為基礎所建立。 以上介紹的根據用途的URL類別會在動態報告中顯示為新的維度，讓運運算元能夠依用途切割開啟和點選資料。 當URL類別設定完成時，系統就會以原生方式顯示同意追蹤和未同意追蹤的區別。

[瞭解如何開始使用動態報告](../../reporting/using/about-dynamic-reports.md)

[瞭解追蹤指標](../../reporting/using/tracking-indicators.md)
