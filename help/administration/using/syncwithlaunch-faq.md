---
title: 與啟動同步技術工作流常見問題
description: 有關Adobe啟動技術工作流的常見問題
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Adobe Experience Platform 同步常見問答集中的標籤 {#syncwithlaunch-faq}

您可以通過 **[!UICONTROL Sync with Launch]** 專用技術工作流。 有關詳細資訊，請參閱 [頁](../../administration/using/technical-workflows.md)

下面一節列出了有關此同步的常見問題。

## 我建立了一個標籤屬性（非管理組織單元ALL）。 我的應用程式在Adobe Campaign處於「準備配置」狀態，但無法開啟/配置它。 {#configuring-property}

只有組織單位ALL的管理員才能配置Adobe Campaign Standard的移動應用程式。 配置後，只有分配的組織單位的用戶才能編輯應用程式。 有關組織單位的詳細資訊，請參閱 [頁](../../administration/using/organizational-units.md)。

## 我無法編輯Adobe Campaign Standard中已配置的移動應用程式，並且移動應用程式處於只讀模式。 {#read-mode-mobile-app}

檢查中移動應用程式的組織單位 **[!UICONTROL Access Authorization]** 的子菜單。 只有分配的組織單位的用戶才能編輯移動應用程式。

有關組織單位的詳細資訊，請參閱 [頁](../../administration/using/organizational-units.md)。

## 我是Adobe Campaign Standard組織單位ALL的管理員，但無法配置移動應用程式。 {#org-unit-mobile}

將組織單位設定為ALL的管理員應擁有配置移動應用程式的所有標籤移動屬性的權限。

有關組織單位的詳細資訊，請參閱 [頁](../../administration/using/organizational-units.md)。

## 我建立了一個標籤移動屬性，但我的屬性在Adobe Campaign Standard不可見。 {#visibility-mobile-property}

1. 檢查Adobe Campaign Standard擴展是否安裝在資料收集UI的mobile屬性中。

1. 驗證實例的端點是否在擴展中正確配置。

1. 檢查「Launch_URL_Campaign」或「NmsServer_URL」是否正確。

1. 然後，檢查同步是否已完成 **[!UICONTROL syncWithLaunch]** 技術工作流。

## 如何檢查Adobe Campaign和Adobe Experience Platform中的標籤之間的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard，從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟 **[!UICONTROL syncWithLaunch]** 工作流。

1. 檢查工作流是否已結束且無錯誤。

1. 簽入已啟用並成功完成工作流同步的日誌。

## 我為已配置的標籤移動應用程式重置密鑰。 如何在資料收集UI中重新配置密鑰？ {#configuring-pkey}

1. 在資料收集UI中開啟mobile屬性。

1. 在重置PKey的Adobe Campaign Standard擴展中設定新URL。

1. 保存並同步工作流。

1. 同步完成後，在資料收集UI中開啟移動屬性。

1. 在重置PKey的Adobe Campaign Standard擴展中設定正確的URL。

1. 保存它，然後讓工作流同步再次運行。

1. 只有這樣，該屬性才會顯示在 **[!UICONTROL Ready to Configure]** 狀態，現在可以配置。

## 我想在Adobe Campaign配置一個移動房產。 我是否必須等待技術工作流在Adobe Experience Platform和Adobe Campaign的標籤之間同步？

您可以立即執行工作流：

1. 在Adobe Campaign Standard，從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟 **[!UICONTROL syncWithLaunch]** 工作流。

1. 按一下 **[!UICONTROL Scheduler]** 活動和選擇 **[!UICONTROL Immediate execution]**。
