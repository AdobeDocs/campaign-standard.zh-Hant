---
solution: Campaign Standard
product: campaign
title: 與Launch技術工作流程同步常見問答集
description: 啟動技術工作流程的常見問題。
audience: administration
content-type: reference
topic-tags: users-and-security
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---


# Adobe Launch Synchronization 常見問答集 {#syncwithlaunch-faq}

您可以透過&#x200B;**[!UICONTROL Sync with Launch]**&#x200B;專屬的技術工作流程，將Adobe Launch行動裝置屬性匯入Adobe Campaign Standard。 如需詳細資訊，請參閱此[頁面](../../administration/using/technical-workflows.md)

下節列出了有關此同步的常見問題。

## 我在[!DNL Launch]（組織單位ALL的非管理員）中建立屬性。 我的應用程式在Adobe Campaign中處於「準備好設定」狀態，但無法開啟／設定它。{#configuring-property}

只有組織單位ALL的管理員才能在Adobe Campaign Standard中設定行動應用程式。 在設定好後，只有已指派組織單位的使用者可以編輯
應用程式。 有關組織單位的詳細資訊，請參閱此[頁](../../administration/using/organizational-units.md)。

## 我無法編輯Adobe Campaign Standard中已設定的行動應用程式，而行動應用程式僅為讀模式。{#read-mode-mobile-app}

在&#x200B;**[!UICONTROL Access Authorization ]**&#x200B;區段中檢查行動應用程式的組織單位。 只有已指派的組織單位的使用者可以編輯行動應用程式。

有關組織單位的詳細資訊，請參閱此[頁](../../administration/using/organizational-units.md)。

## 我是Adobe Campaign Standard中組織單位為ALL的管理員，但無法設定行動應用程式。{#org-unit-mobile}

將組織單元設定為ALL的管理員應具有[!DNL Launch]中所有移動屬性的權限，以配置移動應用程式。

有關組織單位的詳細資訊，請參閱此[頁](../../administration/using/organizational-units.md)。

## 我在[!DNL Launch]中建立了行動屬性，但Adobe Campaign Standard中看不到我的屬性。{#visibility-mobile-property}

1. 檢查[!DNL Launch]中的行動裝置屬性中是否已安裝Adobe Campaign Standard擴充功能。

1. 驗證擴展中實例的端點配置是否正確。

1. 檢查「Launch_URL_Campaign」或「NmsServer_URL」是否正確。

1. 然後，檢查[!DNL Launch]和Adobe Campaign之間的同步是否已透過&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;技術工作流程完成。

## 如何檢查Adobe Campaign和Launch之間的同步是否已完成？{#sync-campaign-launch}

1. 在Adobe Campaign Standard的進階功能表中，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流程。

1. 檢查工作流程是否已結束且無錯誤。

1. 簽入已啟用工作流同步並成功完成的日誌。

## 我已在Launch中重設已設定行動應用程式的按鍵。 如何在Launch中重新配置密鑰？{#configuring-pkey}

1. 在Adobe Launch中開啟行動裝置屬性。

1. 在重設PKey的Adobe Campaign Standard擴充功能中設定新URL。

1. 儲存它，讓工作流程在Adobe Campaign和[!DNL Launch]之間同步。

1. 同步完成後，在[!DNL Launch]中開啟mobile屬性。

1. 在已重設PKey的Adobe Campaign Standard擴充功能中設定正確的URL。

1. 儲存並讓工作流程重新同步。

1. 只有如此，屬性才會出現在Adobe Campaign的&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;狀態，現在可以設定。

## 我想在Adobe Campaign中設定行動裝置屬性。 我是否必須等待技術工作流程在Adobe Launch和Adobe Campaign之間同步？

您可以立即執行工作流：

1. 在Adobe Campaign Standard的進階功能表中，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流程。

1. 按一下&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動並選擇&#x200B;**[!UICONTROL Immediate execution]**。
