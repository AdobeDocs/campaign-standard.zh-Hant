---
title: 與啟動同步技術工作流常見問題
description: 有關Adobe啟動技術工作流的常見問題
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Adobe Launch Synchronization 常見問答集 {#syncwithlaunch-faq}

您可以將Adobe啟動移動屬性通過 **[!UICONTROL Sync with Launch]** 專用技術工作流。 有關詳細資訊，請參閱 [頁](../../administration/using/technical-workflows.md)

下面一節列出了有關此同步的常見問題。

## 我在 [!DNL Launch] （非管理組織單位ALL）。 我的應用程式在Adobe Campaign處於「準備配置」狀態，但無法開啟/配置它。 {#configuring-property}

只有組織單位ALL的管理員才能配置Adobe Campaign Standard的移動應用程式。 配置後，只有分配的組織單位的用戶才能編輯應用程式。 有關組織單位的詳細資訊，請參閱 [頁](../../administration/using/organizational-units.md)。

## 我無法編輯Adobe Campaign Standard中已配置的移動應用程式，並且移動應用程式處於只讀模式。 {#read-mode-mobile-app}

檢查中移動應用程式的組織單位 **[!UICONTROL Access Authorization]** 的子菜單。 只有分配的組織單位的用戶才能編輯移動應用程式。

有關組織單位的詳細資訊，請參閱 [頁](../../administration/using/organizational-units.md)。

## 我是Adobe Campaign Standard組織單位ALL的管理員，但無法配置移動應用程式。 {#org-unit-mobile}

將組織單位設定為ALL的管理員應有權訪問 [!DNL Launch] 來配置移動應用程式。

有關組織單位的詳細資訊，請參閱 [頁](../../administration/using/organizational-units.md)。

## 我在 [!DNL Launch] 但我的房產在Adobe Campaign Standard看不見。 {#visibility-mobile-property}

1. 檢查Adobe Campaign Standard分機是否安裝在 [!DNL Launch]。

1. 驗證實例的端點是否在擴展中正確配置。

1. 檢查「Launch_URL_Campaign」或「NmsServer_URL」是否正確。

1. 然後，檢查 [!DNL Launch] Adobe Campaign完成了 **[!UICONTROL syncWithLaunch]** 技術工作流。

## 如何檢查Adobe Campaign和Launch之間的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard，從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟 **[!UICONTROL syncWithLaunch]** 工作流。

1. 檢查工作流是否已結束且無錯誤。

1. 簽入已啟用並成功完成工作流同步的日誌。

## 在啟動中重置已配置移動應用程式的密鑰。 如何在啟動中重新配置密鑰？ {#configuring-pkey}

1. 在「Adobe啟動」中開啟移動屬性。

1. 在重置PKey的Adobe Campaign Standard擴展中設定新URL。

1. 保存它並使工作流在Adobe Campaign和 [!DNL Launch]。

1. 同步完成後，在中開啟移動屬性 [!DNL Launch]。

1. 在重置PKey的Adobe Campaign Standard擴展中設定正確的URL。

1. 保存它，然後讓工作流同步再次運行。

1. 只有這樣，該屬性才會顯示在 **[!UICONTROL Ready to Configure]** 狀態，現在可以配置。

## 我想在Adobe Campaign配置一個移動房產。 我是否必須等待技術工作流在Adobe啟動和Adobe Campaign之間同步？

您可以立即執行工作流：

1. 在Adobe Campaign Standard，從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟 **[!UICONTROL syncWithLaunch]** 工作流。

1. 按一下 **[!UICONTROL Scheduler]** 活動和選擇 **[!UICONTROL Immediate execution]**。
