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

您可以透過&#x200B;**[!UICONTROL Sync with Launch]**&#x200B;專用的技術工作流程，將AdobeLaunch行動裝置屬性匯入Adobe Campaign Standard。 如需詳細資訊，請參閱此[page](../../administration/using/technical-workflows.md)

下節列出有關此同步的常見問題。

## 我在[!DNL Launch]中建立了屬性（組織單元ALL的非管理員）。 我的應用程式在Adobe Campaign中處於「準備好設定」狀態，但無法開啟/設定它。 {#configuring-property}

只有組織單位ALL的管理員才能在Adobe Campaign Standard中設定行動應用程式。 設定後，只有指派之組織單位的使用者才能編輯
應用程式。 有關組織單位的詳細資訊，請參閱此[page](../../administration/using/organizational-units.md)。

## 我無法編輯Adobe Campaign Standard中已設定的行動應用程式，且行動應用程式僅處於讀取模式。 {#read-mode-mobile-app}

在&#x200B;**[!UICONTROL Access Authorization]**&#x200B;區段中檢查行動應用程式的組織單位。 只有指派之組織單位的使用者才能編輯行動應用程式。

有關組織單位的詳細資訊，請參閱此[page](../../administration/using/organizational-units.md)。

## 我是Adobe Campaign Standard中組織單位為ALL的管理員，但無法設定行動應用程式。 {#org-unit-mobile}

組織單位設為ALL的管理員應具有[!DNL Launch]中所有移動屬性的權限，以配置移動應用程式。

有關組織單位的詳細資訊，請參閱此[page](../../administration/using/organizational-units.md)。

## 我在[!DNL Launch]中建立行動屬性，但Adobe Campaign Standard中未顯示我的屬性。 {#visibility-mobile-property}

1. 檢查[!DNL Launch]的行動屬性中是否已安裝Adobe Campaign Standard擴充功能。

1. 確認擴充功能中已正確設定執行個體端點。

1. 檢查「Launch_URL_Campaign」或「NmsServer_URL」是否正確。

1. 接著，檢查[!DNL Launch]與Adobe Campaign之間的同步是否已透過&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;技術工作流程完成。

## 如何檢查Adobe Campaign和Launch之間的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard中，從進階功能表中選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流程。

1. 檢查工作流程是否已結束，且無錯誤。

1. 檢查記錄中是否已啟用工作流程同步並成功完成。

## 我在Launch中重設已設定行動應用程式的金鑰。 如何在Launch中重新設定金鑰？ {#configuring-pkey}

1. 在AdobeLaunch中開啟行動屬性。

1. 在重設PKey的Adobe Campaign Standard擴充功能中設定新URL。

1. 儲存，並讓工作流程在Adobe Campaign和[!DNL Launch]之間同步。

1. 同步完成後，在[!DNL Launch]中開啟行動屬性。

1. 在重設PKey的Adobe Campaign Standard擴充功能中設定正確的URL。

1. 儲存後，工作流程同步便可再次執行。

1. 只有在此時，屬性才會在Adobe Campaign中顯示為&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;狀態，且現在可以設定。

## 我想在Adobe Campaign中設定行動屬性。 我是否必須等待技術工作流程在AdobeLaunch和Adobe Campaign之間同步？

您可以立即執行工作流程：

1. 在Adobe Campaign Standard中，從進階功能表中選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流程。

1. 按一下&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動並選取&#x200B;**[!UICONTROL Immediate execution]**。
