---
title: 關於隱私管理
description: 瞭解有關使用API進行隱私管理的詳細資訊
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# 關於隱私管理 {#about-privacy-management}

Campaign StandardAPI提供了允許自動處理與隱私法規（如GDPR和CCPA）相關的請求的功能。

您可以執行的操作如下：

* 建立新的隱私請求，
* 監視隱私請求，
* 檢索隱私資料檔案，
* 管理配置檔案的CCPA選擇退出狀態。

隱私API終結點為 **/privacy/privacyTool**。 資源元資料中提供了PrivacyTool資源說明和關聯篩選器。 請參閱 [元資料機制](../../api/using/metadata-mechanism.md)。

CCPA選擇退出使用 **ccpaOptOut** 配置檔案屬性。

有關Adobe Campaign Standard和隱私保護的詳細資訊，請參閱 [專用文檔](../../start/using/privacy-requests.md)。
