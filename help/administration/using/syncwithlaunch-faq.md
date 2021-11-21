---
title: 與Launch同步技術工作流程常見問題集
description: Launch技術工作流程的常見問題。
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# Adobe Launch Synchronization 常見問答集 {#syncwithlaunch-faq}

您可以透過 **[!UICONTROL Sync with Launch]** 專屬的技術工作流程。 如需詳細資訊，請參閱 [頁面](../../administration/using/technical-workflows.md)

下節列出有關此同步的常見問題。

## 我在中建立屬性 [!DNL Launch] （組織單元ALL的非管理員）。 我的應用程式在Adobe Campaign中處於「準備好設定」狀態，但無法開啟/設定它。 {#configuring-property}

只有組織單位ALL的管理員才能在Adobe Campaign Standard中設定行動應用程式。 配置後，只有已分配組織單位的用戶才能編輯應用程式。 有關組織單位的詳細資訊，請參閱 [頁面](../../administration/using/organizational-units.md).

## 我無法編輯Adobe Campaign Standard中已設定的行動應用程式，且行動應用程式僅處於讀取模式。 {#read-mode-mobile-app}

檢查 **[!UICONTROL Access Authorization]** 區段。 只有指派之組織單位的使用者才能編輯行動應用程式。

有關組織單位的詳細資訊，請參閱 [頁面](../../administration/using/organizational-units.md).

## 我是Adobe Campaign Standard中組織單位為ALL的管理員，但無法設定行動應用程式。 {#org-unit-mobile}

組織單位設為ALL的管理員應具有中所有行動屬性的權限 [!DNL Launch] 來設定行動應用程式。

有關組織單位的詳細資訊，請參閱 [頁面](../../administration/using/organizational-units.md).

## 我在 [!DNL Launch] 但我的財產在Adobe Campaign Standard不可見。 {#visibility-mobile-property}

1. 檢查Adobe Campaign Standard擴充功能是否已安裝在 [!DNL Launch].

1. 確認擴充功能中已正確設定執行個體端點。

1. 檢查「Launch_URL_Campaign」或「NmsServer_URL」是否正確。

1. 然後，檢查 [!DNL Launch] 而Adobe Campaign已完成 **[!UICONTROL syncWithLaunch]** 技術工作流程。

## 如何檢查Adobe Campaign和Launch之間的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard中，從進階功能表中選取 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. 開啟 **[!UICONTROL syncWithLaunch]** 工作流程。

1. 檢查工作流程是否已結束，且無錯誤。

1. 檢查記錄中是否已啟用工作流程同步並成功完成。

## 我在Launch中重設已設定行動應用程式的金鑰。 如何在Launch中重新設定金鑰？ {#configuring-pkey}

1. 在AdobeLaunch中開啟行動屬性。

1. 在重設PKey的Adobe Campaign Standard擴充功能中設定新URL。

1. 儲存它，並讓Adobe Campaign與 [!DNL Launch].

1. 同步完成後，在中開啟行動屬性 [!DNL Launch].

1. 在重設PKey的Adobe Campaign Standard擴充功能中設定正確的URL。

1. 儲存後，工作流程同步便可再次執行。

1. 只有在此時，屬性才會出現在 **[!UICONTROL Ready to Configure]** 狀態(在Adobe Campaign中)，現在可以設定。

## 我想在Adobe Campaign中設定行動屬性。 我是否必須等待技術工作流程在AdobeLaunch和Adobe Campaign之間同步？

您可以立即執行工作流程：

1. 在Adobe Campaign Standard中，從進階功能表中選取 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. 開啟 **[!UICONTROL syncWithLaunch]** 工作流程。

1. 按一下 **[!UICONTROL Scheduler]** 活動和選取 **[!UICONTROL Immediate execution]**.
