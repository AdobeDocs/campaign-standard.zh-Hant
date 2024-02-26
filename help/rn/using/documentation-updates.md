---
title: 文件更新
description: 瞭解 Adobe Campaign Standard 文件的所有最新更新
feature: Overview
role: User
level: Beginner
exl-id: 3f77825e-cb98-4cb1-9775-a8b6995e9da1
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: ht
source-wordcount: '7258'
ht-degree: 100%

---

# 文件更新{#documentation-updates}

除了 Adobe Campaign [發行版本](../../rn/using/release-notes.md)以外，本頁還列出 Adobe Campaign Standard 檔案中的所有全新更新。

## 版本 24.1 - 2024 年冬季 {#release-24-1}

已發佈 Campaign Standard 24.1 2024 冬季版的發行說明。[深入了解](release-notes.md)

## 2023 年 12 月 {#doc-updates-dec-2023}

Android Firebase Cloud Messaging (FCM) 服務的一些重要變更將於 2024 年發行，並影響 Adobe Campaign 實施。 若要了解詳細資訊，請參閱[此技術說明](../../administration/using/push-technote.md)。

## 版本 23.2 - 2023 年秋季 {#release-23-2}

* 已發佈 Campaign Standard 23.2 2023 秋冬版的發行說明。[深入了解](release-notes.md)

* JWT (JSON Web 權杖) 目前正在折舊中，並即將由 OAuth 取代。此轉變會在 Campaign 即將發行的版本中逐步執行，並更新文件以反映這些更新。

## 2023 年 10 月 {#doc-updates-oct-2023}

* 現已推出 Experience Cloud 觸發器的新使用者介面。 它為您提供直覺式體驗，用於管理消費者行為並個人化使用者體驗。[深入了解](https://experienceleague.adobe.com/docs/experience-cloud/triggers/overview.html?lang=zh-Hant){target="_blank"}.

* 已新增備註，說明結合篩選或疲勞規則使用補漏白測試設定檔的方式。[深入了解](../../sending/using/using-traps.md)

## 版本 23.1 - 2023 春夏 {#release-23-1}

已發佈 Campaign Standard 23.1 2023 春夏版的發行說明。 [深入了解](release-notes.md)

## 2022 年 11 月 {#doc-updates-november-2022}

已新增附註，以建議避免傳送之 ID 欄位中出現空白字元。 [深入了解](../../channels/using/creating-an-email.md)

已在 **[!UICONTROL Extract file]** 工作流程活動頁面加入資訊， 以將資料擷取至具有特定編碼的 CSV 檔案。[深入了解](../../automating/using/extract-file.md)

## 版本 22.3 - 2022 年秋冬 {#release-22-3}

已發佈 Campaign Standard 22.3 2022 秋冬版的發行說明。 [深入了解](release-notes.md)

<!--Data retention periods have been updated to reflect changes coming with 22.3 release. [Read more](../../administration/using/data-retention.md)-->


## 發行版本 22.2 – 2022 年 6 月 {#release-22-2}

**該版本中包含的功能改善**

**Adobe Notification Service** - Adobe Notification Service 促銷活動，允許 Experience Cloud 解決方案提醒 Experience Cloud 的使用者注意對他們來說很重要的活動。[顯示全文](../../administration/using/sending-internal-notifications.md)。

**其他變更**

現在不建議使用 Adobe Experience Platform 資料連接器和對象目標服務的整合。 [閱讀全文](deprecated-features.md)

已詳細說明 SMTP 測試模式的使用情況。 [閱讀全文](../../administration/using/configuring-email-channel.md#smtp-test-mode)

## 2022 年 3 月 {#doc-updates-march-2022}

有一條備註指定，使用設定檔案替代傳送校樣會將記錄新增到所選檔案中。[閱讀全文](../../sending/using/testing-messages-using-target.md)

## 發行版本 22.1 – 2022 年 2 月 {#release-22-1}

**發行版本中的改進**

改進傳遞的重試機制，包括從 URL 匯入的內容。 [閱讀全文](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

針對控制稽核的選項更新存取層級：啟用/停用無法存取[功能管理員](../../administration/using/users-management.md#functional-administrators)的早期選項[稽核軌跡](../../administration/using/audit.md)。 此變更修改稽核的存取層級，為功能管理員提供控制權。 [閱讀全文](../../administration/using/audit.md#enable-disable-audit)

新的&#x200B;**工作歷史記錄**&#x200B;下拉清單已加入訊息儀表板。 [閱讀全文](../../sending/using/monitoring-a-delivery.md)

**其他變更**

針對觸發自動簡訊回覆的關鍵字新增警告說明：僅能包含字母數字字元。 [閱讀全文](../../channels/using/managing-incoming-sms.md)

已在 A/B 測試電子郵件部分加入備註：如果總人數不到 50k，則每個變數至少應佔總人數的 10%。 否則記錄將顯示警告。 [閱讀全文](../../channels/using/designing-an-a-b-test-email.md)

更新&#x200B;**傳輸檔案**&#x200B;活動的 **[!UICONTROL Delete the source files after transfer]** 選項說明，包括提醒，以在未選取選項時手動監視 SFTP 目錄中封存內容的大小。 [閱讀全文](../../automating/using/transfer-file.md)

更新&#x200B;**隱私權**&#x200B;部分所有過時連結。 [閱讀全文](../../start/using/privacy.md)

在 Campaign Standard 文件內容表格中新增指向 Campaign 控制面板文件的直接連結。

## 發行版本 21.3 – 2021 年 9 月 {#release-21-3---september-2021}

**發行版本中包含的新功能**

改進統一 Experience Cloud 介面 - [了解更多](../../start/using/interface-description.md#top-bar)

新的稽核軌跡功能 - [了解更多](../../administration/using/audit.md)

工作流程診斷模式 - [了解更多](../../automating/using/managing-execution-options.md)

**此發行版本隨附的其他文件更新**

新章節已更新如何從隔離清單中移除位址。 [了解更多](../../sending/using/understanding-quarantine-management.md#removing-a-quarantined-address)

釐清&#x200B;**隔離與封鎖清單**&#x200B;章節。[了解更多](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

## 2021 年 7 月 {#doc-updates-july-2021}

已新增新段落，說明如何讓使用者從單一登陸頁面訂閱或取消訂閱多項服務。 [顯示全文](../../channels/using/managing-landing-page-form-data.md#multiple-subscriptions)

更新並釐清&#x200B;**管理登陸頁面表單資料**&#x200B;段落。 [顯示全文](../../channels/using/managing-landing-page-form-data.md)

## 發行版本 21.2 – 2021 年 6 月 {#release-21-2---june-2021}

**發行中包含的新功能**

登陸頁面驗證 — 您現在可以將強制合約選項新增至登陸頁面。 [顯示全文](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)

已更新&#x200B;**電子郵件大小**&#x200B;區段，其中包含電子郵件大小上限的資訊，現在預設為 100 MB。 [顯示全文](../../sending/using/design-and-personalize.md#email-size)

**此版本隨附的其他文件更新**

已新增有關如何在異動推播通知中變更目標對應的資訊。 [深入了解](../../channels/using/transactional-push-notifications.md#change-target-mapping)

## 2021 年 5 月 {#doc-updates-may-2021}

已更新&#x200B;**主要設定檔**&#x200B;報告章節。 [顯示全文](../../audiences/using/active-profiles.md)

**發行計畫**&#x200B;頁面已更新為新日期。 [顯示全文](../../rn/using/release-planning.md)


## 2021 年 4 月 {#doc-updates-april-2021}

新章節將討論如何與 Adobe Experience Platform 來源及目標合作，以便在 Campaign Standard 和 Adobe Real-time Customer Data Platform (RTCDP) 之間共用資料。 [顯示全文](../../integrating/using/get-started-sources-destinations.md)

## 2021 年 3 月 {#doc-updates-march-2021}

新&#x200B;**說明與支援選項**&#x200B;頁面。 [顯示全文](../../support.md)

列出傳送訊息關鍵步驟的章節已增強，並附上其他資訊和參考。[顯示全文](../../channels/using/key-steps-to-send-a-message.md)

已新增資訊，以指定在查詢中選取 au 閱聽眾時，其定義會被複製而非參考。 [顯示全文](../../audiences/using/selecting-an-audience-in-a-message.md)

與閱聽眾目標服務和 Adobe Experience Platform 資料連接器相關的資訊已重新分組為新部分。 

**已宣告的 ID** 資料來源現在也可搭配 People 核心服務整合使用。已在行銷活動 Audience Manager 或 People 核心服務整合文件中新增資訊。 [顯示全文](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

已新增有關如何為行動應用程式實施本機追蹤的資訊。 [顯示全文](../../administration/using/local-tracking.md)

[傳遞能力](../../sending/using/about-deliverability.md)區段已更新，現在包含新 [Adobe 傳遞能力最佳實務指南](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=zh-Hant)的連結。 針對適用各種 Adobe 解決方案的傳遞能力其所有一般資訊都已移至[最佳實務指南附錄](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=zh-Hant#additional-resources)。

## 發行版本 21.1 – 2021 年 2 月 {#release-21-1---february-2021}

**發行中包含的新功能**

電子郵件回饋服務 - [顯示全文](../../sending/using/confirming-the-send.md#message-indicators)

Adobe Experience Manager 整合改進 - [瞭解詳情](../../integrating/using/creating-multilingual-email-aem.md)

統一 Experience Cloud 介面 - [瞭解詳情](../../start/using/interface-description.md#top-bar)

**此版本隨附的其他文件更新**

已新增有關如何根據電子郵件、名字、姓氏或任何自訂欄位來搜尋設定檔的資訊。[顯示全文](../../audiences/using/integrated-customer-profile.md)

新的 GetOption 函式已新增資訊，可讓您在使用外部參數呼叫工作流程時傳回指定函式的值。[顯示全文](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)

已在使用&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動後可用的新&#x200B;**[!UICONTROL filesCount]**&#x200B;輸出變數上新增了資訊。[顯示全文](../../automating/using/transfer-file.md#output-variables)

**設定電子郵件通道**&#x200B;區段已更新，以釐清最新適用的電子郵件設定。本頁面底部會列出某些仍使用於特定客戶的舊參數。[顯示全文](../../administration/using/configuring-email-channel.md)

已新增相關資訊，瞭解如何確保在先前執行的一或多個工作尚在等待執行前，不會重新排程工作流程。 [顯示全文](../../automating/using/scheduled-workflows-execution.md)

## 2020 年 12 月 {#doc-updates-december-2020}

**預測性主旨行**&#x200B;功能現已過時。[顯示全文](../../rn/using/deprecated-features.md)

**「異動訊息傳送快速入門」**&#x200B;部分現在包含[增強的架構](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)，以便更佳瞭解該過程。

將以一個端到端的使用案例，來說明異動訊息傳送的實施過程。 [顯示全文](../../channels/using/transactional-messaging-use-case.md)

**隱私權**&#x200B;區段已移至[此處](../../start/using/privacy.md)。

有新的&#x200B;**協助工具**&#x200B;頁面可供使用：其詳細說明 Adobe Campaign Standard 工作區中的協助工具支援。[顯示全文](../../start/using/accessibility.md)

已新增警告提示，為獲得最佳效能，已發佈的異動訊息數目應維持在 100 以下。[顯示全文](../../channels/using/transactional-messaging-limitations.md#transactional-message-number)

簡訊連接器通訊協定及設定頁面已移至[此處](../../administration/using/sms-protocol.md)。

**在異動訊息中使用產品清單**&#x200B;區段已移至[此處](../../designing/using/using-product-listings.md)。

## 2020 年 11 月 {#doc-updates-november-2020}

**「個人資料與角色」**&#x200B;部分已更新為使用案例情境，以說明不同角色在隱私權方面如何互動。[顯示全文](../../start/using/privacy.md#use-case-scenario)

已新增一個區段，其中列出「隱私權」的常見問題集。[顯示全文](../../start/using/privacy-faq.md)

**「隱私權」**&#x200B;部分已移動並擴充而包含兩個新頁面：[隱私權管理](../../start/using/privacy-management.md)及[管理隱私權要求](../../start/using/privacy-requests.md)。

**「異動訊息傳送」**&#x200B;部分已重新整理並收集到一個位置，以改善導覽。 [顯示全文](../../channels/using/getting-started-with-transactional-msg.md)

「Adobe Experience Platform Data Connector」區段中已新增有關隱私權管理相關資料對應驗證錯誤以及如何疑難排解的資訊。

## 發行版本 20.4 – 2020 年 10 月 {#release-20-4---october-2020}

**發行中包含的新功能**

控制組 - [瞭解詳情](../../sending/using/control-group.md)

外部 API（OAuth 支援） - [瞭解詳情](../../automating/using/external-api.md)

Journey AI 整合 - [瞭解詳情](../../sending/using/predictive.md)

**此版本隨附的其他文件更新**

關於如何使用外部參數調用工作流程的部分，已透過「運算式編輯器」中提供的新函數進行了豐富的處理。[顯示全文](../../automating/using/customizing-workflow-external-parameters.md)

已在工作流程最佳實踐中新增了有關每個工作流程要使用的活動數量的建議。[顯示全文](../../automating/using/best-practices-workflows.md#number-activities)

已新增關於「傳送」最佳實務的新區段。[顯示全文](../../sending/using/delivery-best-practices.md)

已新增區段，說明可依據其狀態及上次收到事件的時間而搜尋事件設定的新篩選器。[顯示全文](../../channels/using/configuring-transactional-event.md#searching-transactional-events)

## 2020 年 9 月 {#doc-updates-september-2020}

**「事件異動訊息」** 部分已重新整理並釐清。[顯示全文](../../channels/using/editing-transactional-message.md)

已新增警告註釋，以警告使用者有關日誌存取權限限制的問題。[顯示全文](../../administration/using/users-management.md)

已新增新的章節，以詳細說明建立新品牌的程序。[顯示全文](../../administration/using/branding.md#creating-a-brand)

全新的 Campaign Standard - Microsoft Dynamics 365 整合現已推出。[顯示全文](../../integrating/using/d365-acs-get-started.md)

已在「啟用」設定檔報告中新增匿名來源的資訊。[顯示全文](../../audiences/using/active-profiles.md)

## 2020 年 8 月 {#doc-updates-august-2020}

有關異動訊息快速入門的最新章節已供使用。[顯示全文](../../channels/using/getting-started-with-transactional-msg.md)

**異動訊息限制**&#x200B;章節已移至[此](../../channels/using/transactional-messaging-limitations.md)。

**「準備傳送」**&#x200B;部分已移至[此](../../sending/using/preparing-the-send.md)。

## 2020 年 7 月 {#doc-updates-july-2020}

新增了與 Campaign Standard 監視相關的准則。[顯示全文](../../administration/using/monitoring-guidelines.md)

外部 API 護欄和限制區段已更新。[深入了解](../../automating/using/external-api.md#guardrails)

「隱私權管理概覽」頁面已更新，其中加入泰國個人資料保護法 (PDPA) 與巴西 Lei Geral de Proteção de Dados (LGPD) 的相關資訊。[深入了解](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy-overview.html#whatisgdpr)

行動裝置頻道指南已重新整組織並改善。新的設定行動裝置頻道指南已新增有關行動設定的技術文件。[顯示全文](../../administration/using/push-tracking.md)

Campaign Standard 頁面中的「隱私權管理」已更新，其中包括如何透過隱私權核心服務整合管理隱私權請求的說明。[顯示全文](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)

新 AI 支援電子郵件的功能：傳送時間最佳化和設定檔計分。[顯示全文](../../sending/using/predictive.md)

## 2020 年 6 月 {#doc-updates-june-2020}

更新工作流程使用案例，重新組織至各主題章節。[顯示全文](../../automating/using/about-workflow-use-cases.md)

新增使用案例，以說明如何使用「控制面板」及「行銷活動工作流程」進行資料[加密](../../automating/using/managing-encrypted-data.md#use-case-gpg-encrypt)與[解密](../../automating/using/managing-encrypted-data.md#use-case-gpg-decrypt)。

舊版支援網站的參考已由新 URL 取代。[進一步瞭解](../../support.md)

自訂 Litmus 帳戶設定已從收件匣轉譯功能中移除。[顯示全文](../../sending/using/email-rendering.md)

Campaign Standard - 目前無法使用 Microsoft Dynamics 365 整合。新連接器正在開發中，未來將可供使用。相關說明頁面已移除。[顯示全文](../../integrating/using/d365-acs-get-started.md)

## 2020 年 5 月 {#doc-updates-may-2020}

Campaign Standard 概觀頁面已擴充並重新組織為主題式主題。[瞭解詳情](../../start/using/about-campaign-standard.md)

「電子郵件通道參數」區段已清楚顯示授權遮色片欄位和傳送報告 ID 的詳細資訊。[瞭解詳情](../../administration/using/configuring-email-channel.md)

核心文件現在可以使用 Adobe Experience Platform SDK 來設定行動應用程式，其中包含 Launch 平台技術工作流程中的同步應用程式 AEPSDK 的更多資訊。[了解更多](../../administration/using/configuring-a-mobile-application.md)

## 發行版本 20.3 – 2020 年 5 月 {#release-20-3---may-2020}

**發行中包含的新功能**

泰國個人資料保護法案 (PDPA) – [瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html)

External API 活動 (GA) – [瞭解詳情](../../automating/using/external-api.md)

**此版本隨附的其他文件更新**

已在工作流程屬性的　**[!UICONTROL History in days]** 欄位中新增資訊，現在包含　**[!UICONTROL Transfer file]** 活動下載的檔案。[瞭解詳情](../../automating/using/managing-execution-options.md)

在設定檔替代區段中已新增有關主旨行首碼 500 個字元限制的資訊。[瞭解詳情](../../sending/using/testing-messages-using-target.md)

核心文件中已新增「隱私權與同意」專欄。[瞭解詳情](../../start/using/privacy.md)

已新增使用案例，讓您將舊版編輯器電子郵件轉換為電子郵件設計工具。[瞭解詳情](../../designing/using/converting-emails-from-legacy-editor.md)

已新增有關電子郵件設計工具的常見問題區段。[瞭解詳情](../../designing/using/faq-email-designer.md)

## 2020 年 4 月 {#doc-updates-april-2020}

核心檔案現在提供與 Adobe Campaign Standard 檔案整合的 Microsoft Dynamics 365。[瞭解詳情](../../integrating/using/d365-acs-get-started.md)

已將其他資源新增至文件首頁。[瞭解詳情](../../campaign-standard-home.md)

Experience Cloud ID 服務 (ECID) 的相關資訊已新增至 Adobe Experience Platform 資料連接器檔案。

「異動訊息」區段已改良，提供如何存取最新異動事件和更新螢幕擷取畫面的資訊。[瞭解詳情](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

已改進分類和分類規則檔案，並更新內建分類規則的其他資訊。[瞭解詳情](../../sending/using/about-typology-rules.md)

已新增有關 **[!UICONTROL Transfer file]** 活動的 **[!UICONTROL File listing]** 動作資訊。[瞭解詳情](../../automating/using/transfer-file.md)

傳送暫時失敗後重試的說明檔案已更新，其中提供更多詳細資料，說明在升級至增強 MTA 後，如何管理重試。[瞭解詳情](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)

刪除異動訊息區段已增強並釐清。[瞭解詳情](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message)

**預覽傳送**&#x200B;區段已更新為行動傳送範例。[瞭解詳情](../../sending/using/previewing-messages.md)

已新增有關異動訊息和刪除未使用之即時事件的最佳實務。[瞭解詳情](../../channels/using/configuring-transactional-event.md#creating-an-event)

「設定電子郵件通道」區段已更新，其中說明現在由 Adobe Campaign Enhanced MTA 管理的所有電子郵件設定。[瞭解詳情](../../administration/using/configuring-email-channel.md)

「異動訊息」區段已更新，內含編輯事件設定所需權限以及如何擴充異動訊息之集合的詳細資訊。[顯示全文](../../channels/using/configuring-transactional-event.md)。

## 發行版本 20.2 – 2020 年 4 月 {#release-20-2---april-2020}

**發行中包含的新功能**

Azure Blob 整合 – [瞭解詳情](../../administration/using/external-accounts.md#microsoft-azure-external-account)

使用目標設定檔進行電子郵件測試 – [瞭解詳情](../../sending/using/testing-messages-using-target.md)

**此版本隨附的其他文件更新**

「應用程式內」訊息轉換已新增限制。[瞭解詳情](../../channels/using/customizing-an-in-app-message.md)

已新增有關如何在 **[!UICONTROL Query]** 活動中使用彙總的資訊。[瞭解詳情](../../automating/using/query.md#adding-an-aggregate)

MCPNS 在設定行動應用程式時增加了限制。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html)

新的設定指南區段已新增到管理指南中。有關相容瀏覽器和作業系統的區段已從「快速入門」指南移至本區段。Campaign Standard 網路端點的技術也已新增至本節。[瞭解詳情](../../administration/using/about-configuration-guidelines.md)

現在提供新區段，說明如何刪除事件設定。[瞭解詳情](../../channels/using/publishing-transactional-event.md#deleting-an-event)

異動訊息區段已更新，以反映多個使用者介面的微幅更新和改良。[瞭解詳情](../../channels/using/getting-started-with-transactional-msg.md)

已更新與外部 API 活動防護欄相關的資訊。[瞭解詳情](../../automating/using/external-api.md)

## 2020 年 3 月 {#doc-updates-march-2020}

核心文件已新增有關增強型 MTA 的詳細資訊，尤其是有關電子郵件處理規則和退回郵件資格的資訊。[瞭解詳情](../../administration/using/configuring-email-channel.md#email-processing-rules)

已移動並更新專用於使用電子郵件密件副本進行封存的區段。[瞭解詳情](../../sending/using/archiving.md)

「設定行動應用程式」檔案和相關頁面已更新，以反映 SDK V4 折舊。[瞭解詳情](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=zh-Hant)

Adobe Campaign Standard / Adobe Experience Manager 整合檔案已更新和改進。[瞭解詳情](../../integrating/using/configure-experience-manager.md)

Campaign 電子郵件設計工具檔案和相關頁面已更新，以反映 [!DNL Adobe Creative SDK] 折舊。[瞭解詳情](../../rn/using/deprecated-features.md)

現在提供 Campaign Standard 資料模型最佳實務的新區段。[瞭解詳情](../../developing/using/data-model-best-practices.md)

已在 **[!UICONTROL Workflow]** 內建右側新增資訊。[瞭解詳情](../../administration/using/list-of-roles.md)

已在工作流程屬性中可用的 **[!UICONTROL History in days field]** 上新增資訊。[瞭解詳情](../../automating/using/about-workflow-execution.md)

## 發行版本 20.1 – 2020 年 2 月 {#release-20-1---february-2020}

**發行版本中包含的新功能**

Adobe Experience Platform 資料連接器 (Beta)

對象目標 (Beta)

**此版本隨附的其他文件更新**

隱私權管理檔案已更新，其中包含如何為自訂設定檔資源建立 CCPA 選取退出欄位的資訊。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html)

「發行版本」已重新整理和改良。[瞭解詳情](../../rn/using/release-notes.md)

已新增與管理員安全組相關的資訊，指定組織單元已分配給該 **[!UICONTROL All (all)]** 組織單元，且無法修改。[瞭解詳情](../../administration/using/managing-groups-and-users.md)

已新增有關如何定義特定時區以在工作流程中預設使用的資訊。[瞭解詳情](../../automating/using/building-a-workflow.md)

「使用 API」指南中已新增有關新 **_forcePagination=true** 參數的資訊，可讓您對大型表格執行分頁。[瞭解詳情](../../api/using/pagination.md)

有新區段可說明可在訊息控制面板中顯示的警告。[瞭解詳情](../../channels/using/message-dashboard.md#warnings)

Adobe Campaign Enhanced MTA 說明檔案說明升級的傳送基礎架構，可改善傳送能力、吞吐量和退回數處理，現已可供使用。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/campaign-enhanced-mta.html)

已新增附註，指出應用程式伺服器和鏡像頁面伺服器 URL 必須安全，才能從 Campaign 使用者介面顯示登錄頁面和鏡像頁面預覽。[瞭解詳情](../../administration/using/branding.md#configuring-and-using-brands)

「匯出記錄檔」區段已更新，以反映「傳送記錄檔」和「追蹤記錄檔」資源中「傳送記錄檔 ID」的可用性，可匯出每個記錄檔的唯一識別碼。[瞭解詳情](../../automating/using/exporting-logs.md)

## 2020 年 1 月 {#doc-updates-january-2020}

傳遞能力文件已在 IP 認證以新區段更新。<!--[Read more](../../sending/using/ip-certification.md)-->

目前提供新區段，說明如何建立跨通道傳送工作流程。[瞭解詳情](../../automating/using/workflow-cross-channel-delivery.md)

「動態」報告的「指標」計算區段已更新。[瞭解詳情](../../reporting/using/indicator-calculation.md)

已新增有關 Adobe Campaign Standard 中行動傳送之一般方針的新頁面。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/acs-mobile.html)

「搭配使用 Campaign 及 Experience Manager」文件已更新，其中包含如何&#x200B;**使用 Campaign-Experience Manager 整合的提示**&#x200B;新區段。[瞭解詳情](../../integrating/using/integrating-with-experience-manager.md#tips-aem)

API 檔案首頁已經過改良，並重新導向不同的主題。[瞭解詳情](../../api/using/get-started-apis.md)

## 2019 年 11 月至 12 月 {#doc-updates-december-2019}

已更新「設定 S3 外部帳戶」文件。[瞭解詳情](../../administration/using/external-accounts.md#amazon-s3-external-account)

「設計電子郵件內容」區段已重新整理。[瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md)

傳送快速入門手冊已整合至核心文件並更新。[瞭解詳情](../../sending/using/about-deliverability.md)

有關如何匯出/匯入自訂資源的快速入門手冊已整合至核心文件。[瞭解詳情](../../automating/using/exporting-importing-custom-resources.md)

已新增一個新的使用案例，說明如何使用 Campaign Standard 中的工作流程來建立控制群組。

已將登陸頁面屬性相關資訊移入專用區段。[顯示全文](../../channels/using/configuring-landing-page.md)

控制面板文件已整合至新的共同作業文件集。[瞭解詳情](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)

**指標計算**&#x200B;表格已更新。[瞭解詳情](../../reporting/using/indicator-calculation.md)

API 文件集已整合至 Campaign Standard 文件。[瞭解詳情](../../api/using/get-started-apis.md)

「建立個人化電子郵件快速入門」區段已移動並更新。[顯示全文](https://helpx.adobe.com/tw/campaign/kb/acs-get-started-with-emails.html)

更新「傳遞最佳實務快速入門手冊」。[瞭解詳情](../../sending/using/delivery-best-practices.md)

資料模型已整合至 Campaign Standard 檔案。[瞭解詳情](../../developing/using/datamodel-audience.md)

新的 API 端點 **/customResources** 已新增至 API 文件。[瞭解詳情](../../api/using/interacting-with-custom-resources.md)

## 發行版本 19.4 – 2019 年 10 月 {#release-19-4---october-2019}

**此版本包含的新功能**

加州消費者隱私法 (CCPA) – [瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/acs-privacy.html#ccpa)

Microsoft Dynamics 365 整合 (GA) – [瞭解詳情](../../integrating/using/d365-acs-get-started.md)

**此版本隨附的其他文件更新**

Adobe Campaign 的錯誤訊息清單已更新。[顯示全文](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hant)

改善並加強 GDPR 快速入門手冊。該手冊現在是包含 GDPR 及 CCPA 的隱私權管理文件。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy.html)

已新增一個圖表，其中顯示異動訊息發佈程式。[瞭解詳情](../../channels/using/publishing-transactional-message.md#transactional-messaging-pub-process)

「傳送最佳實務」快速入門手冊已移動並更新。[瞭解詳情](../../sending/using/delivery-best-practices.md)

已新增新區段。它提供可讓您擴充 Campaign Standard 資料庫的不同方法的概觀。[瞭解詳情](../../audiences/using/enriching-campaign-database.md)

已新增一個區段，說明如何使用電子郵件設計工具來設定連結的樣式。[瞭解詳情](../../designing/using/styles.md#about-styling-links)

與隱私權相關的資訊已新增至 API 文件[按一下此處](../../api/using/creating-a-privacy-request.md)

## 2019 年 9 月至 10 月 {#doc-updates-october-2019}

已新增與 Campaign Standard 設定相關的新區段。[瞭解詳情](../../administration/using/about-campaign-standard-settings.md)

新增一節，說明如何傳送自動自訂確認電子郵件給已訂閱特定服務的設定檔。[瞭解詳情](../../audiences/using/confirming-subscription-to-a-service.md)

「異動訊息傳送」區段已使用最新的 UI 更新加以修改，包括使用電子郵件設計工具編輯內容。[瞭解詳情](../../channels/using/editing-transactional-message.md)

登陸頁面區段已重新組織。此外，還已新增一個區段，詳細說明設定登陸頁面的步驟。[瞭解詳情](../../channels/using/getting-started-with-landing-pages.md)

推播通知區段中已新增一個區段，說明如何根據行動應用程式訂閱資料建立和更新設定檔資訊。[瞭解詳情](../../channels/using/updating-profile-with-mobile-app-data.md)

已新增新範例，說明如何傳送包含從載入檔案活動擷取之其他資料的電子郵件。[瞭解詳情](../../automating/using/sending-email-enriched-fields.md)

已新增如何使用補漏白的新區段。[瞭解詳情](../../sending/using/using-traps.md)。

已在頁面上新增關於 **Launch_URL_Campaign** 選項的附註，說明如何使用 Adobe Experience Platform SDK 設定行動應用程式。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html)

電子郵件設計工具指南已重新整理。[瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md)

## 2019 年 8 月 {#doc-updates-august-2019}

已新增關於工作流程的使用案例，其著重於查詢的新區段。[瞭解詳情](../../automating/using/workflow-created-query-with-complement.md)

已在工作流程疑難排解區段中新增一個程序，說明如何在 Log 索引標籤中顯示 SQL 查詢。[瞭解詳情](../../automating/using/best-practices-workflows.md#troubleshooting-data-management-activities)

已新增一篇說明文章，其中包含控制面板中子網域和憑證管理的相關資訊。[瞭解詳情](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=zh-Hant)

描述內容範本和片段的區段已更新。[瞭解詳情](../../designing/using/using-reusable-content.md#content-templates)

已新增一個區段，說明如何將電子郵件內容儲存為電子郵件設計工具中的範本。[瞭解詳情](../../designing/using/using-reusable-content.md#saving-content-as-template)

## 發行版本 19.3 – 2019 年 7 月 {#release-19-3---july-2019}

**發行中包含的新功能**

外部 API 活動（公開測試版）– [瞭解詳情](../../automating/using/external-api.md)

工作流程區段報告 – [瞭解詳情](../../reporting/using/creating-a-report-workflow-segment.md)

**此版本隨附的其他文件更新**

Campaign Standard 實作指南現已上線。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/campaign-standard-implementation-guide.html)

已建立一組關於 Microsoft Dynamics 365 連接器實作與使用的新說明文章。請注意，此功能目前處於「有限可用性」。[瞭解詳情](../../integrating/using/d365-acs-get-started.md)

已在[使用參數呼叫工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md)區段中新增一個附註，內容與傳送準備及其彙總期間有關。

已新增有關如何使用已在工作流程外部訊號活動中宣告之事件變數個人化傳送標籤的資訊。[瞭解詳情](../../automating/using/external-signal.md)

已新增新區段，詳述如何在 Adobe Campaign Standard 中建立使用者。[瞭解詳情](../../administration/using/users-management.md)

現在提供新文章及簡化行銷宣傳的秘訣，包括產品文件和教學課程影片的連結。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/simplify-campaign-management.html)

已新增動態報告的疑難排解。[瞭解詳情](../../reporting/using/troubleshooting.md)

說明已新增不同應用程式內範本如何處理個人資訊的圖表。[瞭解詳情](../../channels/using/preparing-and-sending-an-in-app-message.md)

有關如何將電子郵件內容儲存為電子郵件設計工具中片段的區段已經更新。[瞭解詳情](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

已新增警告，說明額外的空白字元如何影響電子郵件內容的版面設定。[瞭解詳情](../../designing/using/personalization.md#creating-custom-content-blocks)

已新增有關「電子郵件設計工具」的建議更新區段。[瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

<!-- A new section on how to send proofs using real customer data has been added. [Read more](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs-using-additional-data) -->

已新增有關工作流程最佳實務的新區段。[瞭解詳情](../../automating/using/best-practices-workflows.md)

Campaign Standard 及 Campaign Classic 的錯誤訊息清單已更新。[瞭解詳情](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hant)

在自訂資源文件中新增警告。我們建議對自訂資源 ID 使用最多 30 個字元。這也適用於自訂資源欄位、索引和連結。[瞭解詳情](../../developing/using/creating-or-extending-the-resource.md)

## 2019 年 6 月至 7 月 {#doc-updates-2019}

新增「登錄頁面」限制的頁面。[瞭解詳情](../../channels/using/getting-started-with-landing-pages.md#landing-page-limitations)

已新增使用案例，說明如何使用複合識別金鑰呼叫設定檔。[瞭解詳情](../../developing/using/uc-calling-resource-id-key.md)

已新增建議，說明在呼叫包含參數的工作流程時，如何使用無彙總期間的循環傳送。[瞭解詳情](../../automating/using/calling-a-workflow-with-external-parameters.md)

Campaign Standard 及 Campaign Classic 的錯誤訊息清單已更新。[瞭解詳情](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hant)

在自訂資源文件中新增警告。我們建議對自訂資源 ID 使用最多 30 個字元。這也適用於自訂資源欄位、索引和連結。[瞭解詳情](../../developing/using/creating-or-extending-the-resource.md)

## 發行版本 19.2 – 2019 年 5 月 {#release-19-2---may-2019}

**此版本包含的新功能**

控制面板 – [瞭解詳情](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)

本機通知 – [瞭解詳情](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)

工作流程增強功能 – 將負載新增至外部訊號活動 – [瞭解詳情容](../../automating/using/calling-a-workflow-with-external-parameters.md)

登錄頁面增強功能 – Google reCAPTCHA – [瞭解詳情](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)

**此版本隨附的其他文件更新**

「網域名稱委派」文章已更新。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/domain-name-delegation.html)

已發佈新的「發行規劃」文章，以分享即將發行的發行日期。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/acs-release-planning.html)

直接從 Adobe Campaign 取得的內容說明連結已更新。

以下[頁面](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=zh-Hant)成為 Adobe Campaign Standard 的官方「視訊」頁面。

已新增資料保留的區段，包括標準表格的預設保留值。[瞭解詳情](../../administration/using/data-retention.md)

已新增有關更新和維護作業的區段。[瞭解詳情](../../administration/using/updates-and-maintenance-operations.md)

在&#x200B;**傳輸檔案**&#x200B;活動的新排序選項中已新增資訊。[瞭解詳情](../../automating/using/transfer-file.md)

已更新 [REST API 文件](../../api/using/get-started-apis.md)：

* 已新增一個區段，其中包含有關使用 Campaign Standard REST API 的一般資訊。
* 已提供預先設計的 API 要求集合，代表常見使用案例。
* 已新增關於如何管理組織單位的區段。
* 已新增有關如何建立服務的資訊。
* 已新增有關如何使用參數呼叫工作流程的資訊。

已新增有關新&#x200B;**測試**&#x200B;活動的資訊。[瞭解詳情](../../automating/using/test.md)

「自動化」指南已更新，其中包含相關工作流程活動的連結。[瞭解詳情](../../automating/using/workflow-interface.md#palette)

「動態」報告的「指標」計算區段已更新。[瞭解詳情](../../reporting/using/indicator-calculation.md)

已新增動態報告相容性表格，以更妥善地瞭解維度與度量之間的相容性。[瞭解詳情](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

工作流程的函式清單已更新。[瞭解詳情](../../automating/using/list-of-functions.md)

「設計內容」區段已重新整理並改良，新區段清楚說明使用現有內容使用「電子郵件設計工具」來設計電子郵件的不同方法。[瞭解詳情](../../designing/using/using-existing-content.md)

已新增如何將電子郵件內容儲存為電子郵件設計工具中片段的新區段。[瞭解詳情](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

「管理連結」區段已更新，內含如何在「電子郵件設計工具」中管理追蹤 URL 的其他資訊。[瞭解詳情](../../designing/using/links.md#inserting-a-link)

已新增新區段，以說明特定異動訊息重試過程。[瞭解詳情](../../channels/using/transactional-message-execution.md#transactional-message-retry-process)

「使用 API 擴充功能發佈資源」區段已經過釐清，並已更新為最新的 UI 變更。[瞭解詳情](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

「封存電子郵件」區段已重新命名並重新組織。[瞭解詳情](../../sending/using/archiving.md)

「建立電子郵件」區段已更新，以反映最新的介面變更。[瞭解詳情](../../channels/using/creating-an-email.md)

[SMS 連接器協議和設定](https://helpx.adobe.com/tw/campaign/kb/sms-connector-protocol-and-settings.html)知識庫文章已更新，新增選項至 SMS 外部帳戶，以限制允許連線至 SMPP 提供者的 MTA 執行個體數量。

「開始使用指南」已經過擴充和重新整理。[瞭解詳情](../../start/using/about-campaign-standard.md)

「已過時和已移除的功能」頁面已更新。[瞭解詳情](../../rn/using/deprecated-features.md)

Dreamweaver 整合區段已更新並改良。[瞭解詳情](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)

## 發行版本 19.1 – 2019 年 2 月 {#release-19-1---february-2019}

**發行中包含的新功能**

推播通道報告改進 – [瞭解詳情](../../reporting/using/push-notification-report.md)

行動應用程式的啟動整合 – [瞭解詳情](../../administration/using/configuring-a-mobile-application.md#using-adobe-experience-platform-sdk)

行動應用程式內訊息 – [瞭解詳情](../../channels/using/about-in-app-messaging.md)

工作流程增強功能 – 在[此處](../../automating/using/workflow-interface.md#duplicating-workflow-activities)及[此處](../../automating/using/load-file.md#configuration)瞭解詳情

**此版本隨附的其他文件更新**

「編輯電子郵件內容」一章中已新增建立電子郵件內容的入門體驗，以及「電子郵件設計工具」的其他增強功能。[瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)

已新增「異動傳訊」限制的區段。[瞭解詳情](../../channels/using/transactional-messaging-limitations.md)

已新增比較 Adobe Campaign 中不同電子郵件撰寫選項的區段。[瞭解詳情](../../designing/using/using-integrations.md#email-design-options-comparison)

「建立自訂內容區塊」區段已增強，並包含定位維度的詳細資料。[瞭解詳情](../../designing/using/personalization.md#creating-custom-content-blocks)

已新增警告，指出「電子郵件設計工具」不支援 Internet Explorer 11。[瞭解詳情](../../administration/using/about-configuration-guidelines.md)

「刪除資源」區段已新增有關重新起草影響的警告。[瞭解詳情](../../developing/using/deleting-a-resource.md)

有關如何新增或擴展資源的區段已經更新。[瞭解詳情](../../developing/using/creating-or-extending-the-resource.md)

已新增如何擴充設定檔自訂資源的使用案例。[瞭解詳情](../../developing/using/extending-the-profile-resource-with-a-new-field.md)

已新增有關如何連結自訂資源的資訊。[瞭解詳情](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)

已新增一項技術，說明如何從 Adobe Campaign Standard 推播通知顯示影像。[瞭解詳情](../../administration/using/image-push-notification.md)

已新增推播追蹤實作的新技術。[瞭解詳情](../../administration/using/push-tracking.md)

Campaign Standard 及 Campaign Classic 的錯誤訊息清單已更新。[瞭解詳情](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=zh-Hant)

已更新「觸發器 – Adobe Campaign Standard」整合文件。[瞭解詳情](../../integrating/using/about-adobe-experience-cloud-triggers.md)

更新直接從 Adobe Campaign 取得的內容說明連結。

在包含拒絕的檔案名稱中新增時間標記的附註。[瞭解詳情](../../automating/using/load-file.md#configuration)

已新增匯入由長度固定之欄組成欄位時的資訊。[瞭解詳情](../../automating/using/load-file.md#configuration)

已新增選項的相關資訊，讓您將拒絕項目保留在檔案中。此選項現在可讓您將後處理階段套用至包含拒絕的檔案。[瞭解詳情](../../automating/using/load-file.md#configuration)

已新增有關如何透過複製貼上作業複製工作流程活動的新區段。[瞭解詳情](../../automating/using/workflow-interface.md#duplicating-workflow-activities)

已新增查詢（[瞭解詳情](../../automating/using/query-samples.md)）及分段（[瞭解詳情](../../automating/using/segmentation.md)）活動中新選項的資訊，如果活動未擷取任何資料，則可讓您在活動後新增出站轉變。

在「更新資料」活動區段中新增新的「批次大小」欄位的資訊，可讓您定義要上傳之資料的最大批次大小。[瞭解詳情](../../automating/using/update-data.md#configuration)

在「擷取檔案」活動區段中新增新選項的資訊，讓您在出站轉變為空時停用檔案產生程式。[瞭解詳情](../../automating/using/extract-file.md#configuration)

## 發行版本 19.0 – 2019 年 1 月 {#release-19-0---january-2019}

**發行中包含的新功能**

電子郵件設計工具一般可用性 – [瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md)

異動電子郵件中的產品清單 – [瞭解詳情](../../designing/using/using-product-listings.md)

電子郵件設計工具中的行動裝置檢視 – [瞭解詳情](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)

應用程式內訊息測試版改良 – [瞭解詳情](../../channels/using/about-in-app-messaging.md)

**此版本隨附的其他文件更新**

「設計內容」指南已更新，以反映電子郵件設計工具的一般可用性和舊版電子郵件內容編輯器的淘汰。[瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md)

更新[應用程式內](../../channels/using/about-in-app-messaging.md)及[推播通知](../../channels/using/about-push-notifications.md)文件。

已新增有關 Adobe Campaign 中不同對象類型的詳細資訊。[瞭解詳情](../../audiences/using/about-audiences.md)

更新「使用者與安全性」一章，以反映地理單位的折舊。[瞭解詳情](../../administration/using/organizational-units.md)

已新增「載入資料」活動中新選項的相關資訊，可讓您將後處理階段套用至包含已拒絕記錄的檔案（例如：壓縮郵遞區號格式)。[瞭解詳情](../../automating/using/load-file.md)

已新增「更新資料」活動中新欄位的資訊，可讓您設定要上傳之資料的最大批次大小。[瞭解詳情](../../automating/using/update-data.md)

已更新[從 URL 文件匯入內容](../../designing/using/using-existing-content.md#importing-content-from-a-url)，其中包含與電子郵件設計工具相關的資訊。

Microsoft Edge（最新版本）已新增至電腦的相容瀏覽器清單。[瞭解詳情](../../administration/using/about-configuration-guidelines.md)

已新增有關「擷取檔案」活動中新選項的資訊，當入站轉變為空時，此項資訊無法產生檔案。[瞭解詳情](../../automating/using/extract-file.md)

「使用 SDK V4 設定行動應用程式」區段已移至[此處](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)。

「使用 Adobe Experience Platform SDK 設定行動應用程式」一節已移至[此處](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdk.html)。

視訊已更新並移至[此處](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=zh-Hant)。

已更新「使用者類型」區段。[瞭解詳情](../../administration/using/users-management.md)

## 發行版本 18.9 – 2018 年 9 月 {#release-18-9---september-2018}

**發行中包含的新功能**

應用程式內訊息（測試版）– [瞭解詳情](../../channels/using/about-in-app-messaging.md)

Adobe Launch 整合行動應用程式（測試版）– [瞭解詳情](../../sending/using/managing-typologies.md)

**此版本隨附的其他文件更新**

已更新推播通知指南，並變更介面。[瞭解詳情](../../channels/using/about-push-notifications.md)

已新增如何刪除對象的資訊。[瞭解詳情](../../audiences/using/creating-audiences.md#deleting-audiences)

更新推播通知內建報告區段。[瞭解詳情](../../reporting/using/push-notification-report.md)

## 發行版本 18.7 – 2018 年 7 月 {#release-18-7---july-2018}

**發行中包含的新功能**

針對行動應用程式訂閱者，提供[高優先順序旗標](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android)及[類型篩選器](../../sending/using/managing-typologies.md)。

準備時從 URL 自動匯入內容。[瞭解詳情](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

**此版本隨附的其他文件更新**

已新增有關簡訊連接器通訊協定和設定的新技術。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/sms-connector-protocol-and-settings.html)

更新 Experience Manager 與 Adobe Campaign 檔案的整合。[瞭解詳情](../../reporting/using/creating-a-custom-profile-dimension.md)

「設計內容」指南已完全重新整理，尤其是提供兩個編輯器，讓您設計電子郵件內容。[瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md)

瞭解如何從您現有的電子郵件中建立片段，讓 Creative SDK 完全可編輯外部內容。[瞭解詳情](../../designing/using/designing-from-scratch.md)

本節現在提供 HTML 屬性清單，以完全符合 Creative Designer 的[規定](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer)。

已新增多語言範本預設語言的相關資訊。[瞭解詳情](../../channels/using/multilingual-messages-template.md)

已更新「使用者與安全性」指南，以反映新 Campaign Standard 執行個體的地理單位功能折舊，以及未建立地理單位的現有執行個體（從 18.7 版開始）。[瞭解詳情](../../rn/using/deprecated-features.md)

## 發行版本 18.6 – 2018 年 6 月 {#release-18-6---june-2018}

**發行中包含的新功能**

API 檔案已更新，其中包含 **History** API 的資訊。已新增使用案例，說明如何擷取傳送至設定檔的傳送鏡像頁面。[瞭解詳情](../../api/using/interacting-with-marketing-history.md)

**此版本隨附的其他文件更新**

已更新並重新整理「觸發器 – Campaign」整合文件。[瞭解詳情](../../integrating/using/about-adobe-experience-cloud-triggers.md)

新增如何建立自訂設定檔維度的逐步使用案例。[瞭解詳情](../../reporting/using/creating-a-custom-profile-dimension.md)

協作使用 Campaign 與 Audience Manager 或 People 核心服務。[瞭解詳情](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

已更新「準備傳送」角色定義。[瞭解詳情](../../administration/using/list-of-roles.md)

在查詢活動區段中新增範例，說明如何定位在傳送中點按特定連結的設定檔。[瞭解詳情](../../automating/using/query-samples.md#targeting-profiles-who-clicked-a-specific-link-)

在 API 檔案中新增與&#x200B;**自訂篩選器**&#x200B;相關的區段。[瞭解詳情](../../api/using/filtering.md)

## 發行版本 18.5 – 2018 年 5 月 {#release-18-5---may-2018}

**發行中包含的新功能**

GDPR：核心服務整合 – [瞭解詳情](../../start/using/privacy-management.md)

推播改良功能 – 詳細的傳送回饋 – [瞭解詳情](../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification)

傳送記錄擴充功能 – [瞭解詳情](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

使用自訂設定檔資料建立動態報告 – [瞭解詳情](../../channels/using/creating-a-multilingual-push-notification.md)

**此版本隨附的其他文件更新**

已新增在 Analytics 中找到的 Campaign 度量清單。[瞭解詳情](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

已新增「管理」功能表中「授權」選項的資訊。[瞭解詳情](../../administration/using/licenses.md)

已新增如何在推播通知中使用自訂欄位的資訊。[瞭解詳情](../../channels/using/customizing-a-push-notification.md#add-custom-fields)

更新傳送最佳實務逐步指南。[瞭解詳情](../../sending/using/delivery-best-practices.md)

已新增追蹤記錄檔類型的資訊。[瞭解詳情](../../sending/using/tracking-messages.md#tracking-logs)

查詢活動節已用查詢示例更新。[瞭解詳情](../../automating/using/query.md#query-samples)

封鎖清單用的區段已更名為「瞭解加入和退出步驟」。它已更新，其中包含如何管理特定通道的選取加入，以及如何設定登錄頁面以管理選取加入和選取退出的資訊。[瞭解詳情](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

瞭解使用 Adobe 代管 SFTP 伺服器的最佳實務。[瞭解詳情](../../administration/using/external-accounts.md#sftp-external-account)

已更新與觸發器整合的支援 Analytics SKU 清單。[瞭解詳情](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)

內容編輯器檔案的某些頁面已合併，以提供更完整的檢視，以檢視可用的不同動作。[瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md)

## 發行版本 18.3 – 2018 年 3 月 {#release-18-3---march-2018}

**此版本包含的新功能**

歐盟通用資料保護規則 (GDPR) – [瞭解詳情](../../start/using/privacy.md)

適用於電子郵件的 Creative Designer – [瞭解詳情](../../designing/using/designing-content-in-adobe-campaign.md)

多語言推播傳送 – [瞭解詳情](../../channels/using/creating-a-multilingual-push-notification.md)

在異動訊息傳遞中使用自訂資源 – [瞭解詳情](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)

**此版本隨附的其他文件更新**

GDPR API 會重新分組可自動處理 GDPR 要求的功能。[瞭解詳情](../../api/using/creating-a-privacy-request.md)

已新增有關如何設定登錄頁面，讓收件者能夠列入封鎖清單的資訊。[瞭解詳情](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)

已重新整理[設定異動訊息](../../channels/using/configuring-transactional-event.md)區段，而且已新增[逐步使用案例](../../channels/using/transactional-messaging-use-case.md)。

新增技術，瞭解如何產生多語言 CSV 檔案以用於推播通知。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/acs-generate-csv-multilingual-push.html)。

已新增有關&#x200B;**更新直接郵件隔離和傳送記錄檔**&#x200B;匯入範本的資訊。[瞭解詳情](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)

更新技術工作流程清單。[瞭解詳情](../../administration/using/technical-workflows.md)

已更新排程器活動區段。[瞭解詳情](../../automating/using/scheduler.md)

更新有關 Campaign 和 Adobe 解決方案整合的說明資料清單。[瞭解詳情](../../integrating/using/get-started-campaign-integrations.md)。

更新 Campaign Standard 產品內容說明。

## 發行版本 18.2 – 2018 年 2 月 {#release-18-2---february-2018}

**發行中包含的新功能**

訂閱 – 訂閱或取消訂閱多項服務的設定檔清單 – [瞭解詳情](../../automating/using/subscription-services.md)

擴充活動 – 根據先前的轉變來擴充資料 – [瞭解詳情](../../automating/using/enrichment.md)

**此版本隨附的其他文件更新**

Campaign 和 Adobe 解決方案整合的大多數 URL 已變更！檢查您的書籤！[瞭解詳情](../../integrating/using/get-started-campaign-integrations.md)

datamodel v1 現在可用於內建資源的 SQL 結構 – [瞭解詳情](../../developing/using/datamodel-introduction.md)

已新增有關如何在傳送中準備訊息的資訊[瞭解詳情](../../sending/using/preparing-the-send.md)

發行版本已在數個頁面中重新整理，讓您可以更全面性地檢視所有不同的版本。

已更新　**[!UICONTROL Working with typologies]**　區段，以改善可見度。[瞭解詳情](../../sending/using/about-typology-rules.md)

可在 **[!UICONTROL Query]** 中定義許多其他資料時取得效能的新選項，現在已可供使用。[瞭解詳情](../../automating/using/query-samples.md)

設定檔匯入範例已更新，提供一些提示，讓您的設定檔準備好接收直接電子郵件。[瞭解詳情](../../automating/using/about-data-import-and-export.md)

工作流程中提供新活動：**[!UICONTROL Enrichment]** 活動。[瞭解詳情](../../automating/using/enrichment.md)

**[!UICONTROL Subscription Services]** 活動已更新，可支援更多使用案例，包括使用單一檔案更新多項服務的訂閱。[瞭解詳情](../../automating/using/subscription-services.md)

新增如何準備傳送的逐步使用案例。[瞭解詳情](../../sending/using/preparing-the-send.md)

已刪除包含授權清單的區段。[瞭解詳情](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf) (PDF)。

新增如何使用簡訊自動回覆的逐步使用案例。[瞭解詳情](../../channels/using/managing-incoming-sms.md#managing-stop-sms)

已新增有關如何根據使用者在循環工作流程中的時區傳送傳送的資訊。[瞭解詳情](../../automating/using/recurring-push-notifications.md)

使用逐步使用案例重新整理　**[!UICONTROL Customizing a push notification]**　區段。[瞭解詳情](../../channels/using/customizing-a-push-notification.md)

封鎖清單管理專屬的新區段。[瞭解詳情](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

已更新有關傳送失敗和隔離的資訊。[瞭解詳情](../../sending/using/monitoring-a-delivery.md)

專用於[定位對應](../../administration/using/target-mappings-in-campaign.md)及[目標維度及資源](../../automating/using/query.md#targeting-dimensions-and-resources)的新區段。

## 發行版本 18.1 – 2018 年 1 月 {#release-18-1---january-2018}

**發行中包含的新功能**

疲勞管理報告 – [瞭解詳情](../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report)

報告共用 – [瞭解詳情](../../reporting/using/reporting-interface.md#share-tab)

推播改良功能 – 在[此處](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)及[此處](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios)瞭解詳情

時區最佳化傳送 – [瞭解詳情](../../automating/using/scheduler.md)

API Signal 活動觸發 – [瞭解詳情](../../api/using/triggering-a-signal-activity.md)

**此版本隨附的其他文件更新**

已更新服務建立區段。[瞭解詳情](../../audiences/using/creating-a-service.md)

已新增使用案例，以便更妥善地瞭解安全群組和裝置。[瞭解詳情](../../administration/using/organizational-units.md)

改進動態報告中維度、度量和區段的定義和計算。[瞭解詳情](../../reporting/using/list-of-components.md)

已新增有關使用工作流程擷取入站簡訊訊息的資訊。[瞭解詳情](../../administration/using/configuring-sms-channel.md)

已新增有關「傳輸檔案」活動之「歷史化」設定的資訊。[瞭解詳情](../../automating/using/transfer-file.md)

設定與 Audience Manager 或 People 核心服務整合的指示已更新。[瞭解詳情](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

## 發行版本 17.10 – 2017 年 10 月 {#release-17-10---october-2017}

**發行中包含的新功能**

疲勞管理 – [瞭解詳情](../../sending/using/fatigue-rules.md)

內容建立：從 URL 匯入 – [瞭解詳情](../../designing/using/using-existing-content.md#importing-content-from-a-url)

**此版本隨附的其他文件更新**

更新 A/B 測試範例。[瞭解詳情](../../channels/using/designing-an-a-b-test-email.md)

有關如何在行動應用程式傳送「收集 PII」資料時建立或更新設定檔資料的新技術。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/acs-updating-profile-based-on-subscription.html)

已新增有關新匯出追蹤功能的區段。[瞭解詳情](../../administration/using/auditing-export-logs.md)

已新增有關內建套件匯出的精確度。[瞭解詳情](../../automating/using/managing-packages.md)

更新外部帳戶定義和範例。[瞭解詳情](../../administration/using/external-accounts.md)

更新許多螢幕擷取畫面，以反映查詢編輯器類別的變更。

[傳送警報](../../sending/using/receiving-alerts-when-failures-happen.md)區段已移動並重新組織。

「自訂資源」區段已用更詳細的程式加以釐清，說明如何定義 [篩選器](../../developing/using/configuring-filter-definition.md)。

更新並釐清 [如何整合](https://helpx.adobe.com/tw/campaign/kb/integrate-mobile-sdk.html) Adobe Marketing Cloud Mobile SDK 與行動應用程式以接收 Adobe Campaign Standard 推播通知的技術。

已新增技術，說明行動應用程式中接收的裝載結構。[瞭解詳情。](../../administration/using/push-payload.md)

在 Adobe Mobile Services 介面中定義回傳時，「推播」通道設定[區段](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)已隨作業系統版本上的新裝載資料更新。

簡訊檔案已更新，[簡訊自動回覆](../../channels/using/managing-incoming-sms.md#managing-stop-sms)區段已新增一些說明。

透過 API 專用於工作流程管理的新區段。[瞭解詳情](../../api/using/controlling-a-workflow.md)

新區段專用於主要金鑰，以及使用商業 ID 作為 API 中金鑰。[瞭解詳情](../../api/using/get-started-apis.md)

在 API 中新增有關簡單和多重篩選的資訊。[瞭解詳情](../../api/using/filtering.md)

## 發行版本 17.9 – 2017 年 9 月 {#release-17-9---september-2017}

**發行中包含的新功能**

電子郵件範本庫 – [瞭解詳情](../../designing/using/using-reusable-content.md#content-templates)

使用設定檔資料建立動態報告 – [瞭解詳情](../../reporting/using/about-dynamic-reports.md)

大量訂閱的增強功能 – [瞭解詳情](../../automating/using/subscription-services.md)

**此版本隨附的其他文件更新**

「動態報告」中每個可用元件的詳細清單，以及公式的某些變更。[瞭解詳情](../../reporting/using/list-of-components.md)

與 Adobe Analytics 共用的 KPI 詳細清單。[瞭解詳情](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

新動態報告影片。

新增 S3 帳戶建議。[瞭解詳情](../../administration/using/external-accounts.md#amazon-s3-account-recommendations)

已更新不同使用者類型的相關區段。[瞭解詳情](../../administration/using/users-management.md)

更新影像來源個人化的相關區段。[瞭解詳情](../../designing/using/personalization.md#personalizing-an-image-source)

在作用中設定檔報告上新增的文件。[瞭解詳情](../../audiences/using/active-profiles.md)

[傳送警報](../../sending/using/receiving-alerts-when-failures-happen.md#delivery-alerting-reasons)文件已更新，其中包含疑難排解區段，提供您在收到警報時可採取的一些動作提示。

有新的快速入門手冊可供使用：它提供一些最佳實務，可用於透過 Adobe Campaign 傳遞，從建立和定位到傳送和監控。[瞭解詳情](../../sending/using/delivery-best-practices.md)

後續訊息檔案已更新，並改良使用案例。[瞭解詳情](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)

ACS ID 上新增的文件。[瞭解詳情](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

新增加了新的加密和雜湊函式，並附上範例。[瞭解詳情](../../automating/using/list-of-functions.md)

已更新「傳輸檔案」工作流程活動的區段。[瞭解詳情](../../automating/using/transfer-file.md)

在「電子郵件傳送」工作流程活動中「傳送訊息前請求確認」選項中新增的資訊。[瞭解詳情](../../automating/using/email-delivery.md)

## 發行版本 17.7 – 2017 年 7 月 {#release-17-7---july-2017}

**發行中包含的新功能**

多語言傳送（電子郵件和簡訊）– [瞭解詳情](../../channels/using/creating-a-multilingual-email.md)

Adobe Campaign 通知 – [瞭解詳情](../../administration/using/sending-internal-notifications.md)

傳送警報 – [瞭解詳情](../../sending/using/receiving-alerts-when-failures-happen.md)

資料來源中的加密宣告 ID – [瞭解詳情](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

從 Campaign 到 Analytics 的 KPI 共用 – [瞭解詳情](../../integrating/using/about-campaign-analytics-integration.md)

直接郵件通道 – 傳回給發件人，[瞭解詳情](../../channels/using/return-to-sender.md)

**此版本隨附的其他文件更新**

已將快速入門手冊和操作說明影片重新分組至專屬區域。

已更新電子郵件轉換文件。[瞭解詳情](../../sending/using/email-rendering.md)

已更新報告指標計算表。[瞭解詳情](../../reporting/using/indicator-calculation.md)

報告檔案已更新為 4 個新度量。[瞭解詳情](../../reporting/using/list-of-components.md)

在設定檔的唯一 ID 產生中新增檔案。[瞭解詳情](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

現在，透過逐步程式記錄雙重加入機制。[瞭解詳情](../../channels/using/setting-up-a-double-opt-in-process.md)

已更新「角色清單」區段。[瞭解詳情](../../administration/using/list-of-roles.md)

## 發行版本 17.5 – 2017 年 5 月 {#release-17-5---may-2017}

**發行中包含的新功能**

直接郵件 – [瞭解詳情](../../channels/using/about-direct-mail.md)

電子郵件密件副本 – [瞭解詳情](../../sending/using/archiving.md)

**此版本隨附的其他文件更新**

「傳送」指南已重新整理，並重新命名為「通道」。[瞭解詳情](../../channels/using/get-started-communication-channels.md)

已更新所有螢幕擷取畫面以反映介面的變更。

現在有新技術可用：「將 Adobe Mobile SDK 與行動應用程式整合」。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/integrate-mobile-sdk.html)

新增了設定 People 核心服務或 Audience Manager 與 Adobe Campaign 整合的說明。[顯示全文](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

修改授權表，使某些角色的功能更加清晰。[瞭解詳情](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

更新直接從 Adobe Campaign 取得的內容說明連結。

## 發行版本 17.4 – 2017 年 4 月 {#release-17-4---april-2017}

**發行中包含的新功能**

Creative SDK的增強影像版本功能 – [瞭解詳情](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)

異動推播通知 – [瞭解詳情](../../channels/using/transactional-push-notifications.md)

循環推播通知 – [瞭解詳情](../../automating/using/push-notification-delivery.md)

Amazon Simple Storage Service (S3) 連接器 – [瞭解詳情](../../administration/using/external-accounts.md)

Dreamweaver 整合即時 – [瞭解詳情](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hant)

**此版本隨附的其他文件更新**

針對不同類型的 Adobe Campaign 使用者新增區段。[瞭解詳情](../../administration/using/users-management.md)

重新組織及擴充「工作流程手冊」。輕鬆瞭解如何[建立](../../automating/using/building-a-workflow.md)及[執行](../../automating/using/about-workflow-execution.md)工作流程、如何[鎖定目標](../../automating/using/about-targeting-activities.md)及[管理](../../automating/using/about-targeting-activities.md#enriching-data)資料、如何[匯入和匯出](../../automating/using/about-data-import-and-export.md)資料，以及如何使用工作流程資料來更新資料庫或傳送傳遞內容。

現在動態報告可使用報告指標計算，包括完整說明和計算公式。[瞭解詳情](../../reporting/using/indicator-calculation.md)

關於 Adobe Mobile Services 設定的新專屬區段，以在 Adobe Campaign 中使用推播通知和 Point of Interest 資料。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)

已更新行動應用程式設定和實作區段，包括設定和傳送推播通知的更詳細步驟。[瞭解詳情](https://helpx.adobe.com/tw/campaign/kb/configuring-app-sdkv4.html)

已更新如何在 Campaign 中處理影像的區段。[瞭解詳情](../../designing/using/images.md#setting-up-image-properties)

已更新與 Adobe Analytics for Mobile (Point of Interest) 的整合，包括設定步驟和使用案例。[瞭解詳情](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

## 發行版本 17.2 – 2017 年 3 月 {#release-17-2---march-2017}

**發行中包含的新功能**

動態報告 – [瞭解詳情](../../reporting/using/about-dynamic-reports.md)

Dreamweaver 整合 (Labs)– [瞭解詳情](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=zh-Hant)

手動傳送時間最佳化 – [瞭解詳情](../../sending/using/optimizing-the-sending-time.md)

推播通知：改進 – [瞭解詳情](../../channels/using/about-push-notifications.md)

工作流程：新訊號活動 – [瞭解詳情](../../automating/using/external-signal.md)

工作流程：新的閱讀對象活動 – [瞭解詳情](../../automating/using/read-audience.md)

興趣點資料 – [瞭解詳情](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

REST API 中的連結資源 – [瞭解詳情](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

**此版本隨附的其他文件更新**

觸發器整合：已新增兩個使用案例。[瞭解詳情](../../integrating/using/abandonment-triggers-use-cases.md)

我們重新設計了開發人員 API 文件，提供新資訊和程式碼片段，以改善使用體驗。[瞭解詳情](../../api/using/get-started-apis.md)

探索新的[讀取對象](../../automating/using/read-audience.md)及[外部訊號](../../automating/using/external-signal.md)工作流程活動的範例。

## 發行版本 17.1 – 2017 年 1 月 {#release-17-1---january-2017}

**發行中包含的新功能**

外部報告的記錄匯出 – [瞭解詳情](../../automating/using/exporting-logs.md)

Transactional Messaging API – [瞭解詳情](../../api/using/get-started-apis.md)

異動訊息的行銷功能 – [瞭解詳情](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)

**此版本隨附的其他文件更新**

增量查詢工作流活動：新的增量模式 – [瞭解詳情](../../automating/using/incremental-query.md)

排程器工作流程活動更新 – [瞭解詳情](../../automating/using/scheduler.md)

URL變更：資產核心服務 – [瞭解詳情](../../integrating/using/working-with-campaign-and-assets-core-service.md)

URL變更：人員核心服務 – [瞭解詳情](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

設定檔和對象指南已重新整理。[瞭解詳情](../../audiences/using/get-started-profiles-and-audiences.md)
