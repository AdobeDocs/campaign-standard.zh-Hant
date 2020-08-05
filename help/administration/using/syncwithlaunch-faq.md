---
title: 與Launch技術工作流程同步常見問答集
description: 啟動技術工作流程的常見問題。
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95a7397092f6e07c84967d90908469f630f7a170
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---


# Adobe Launch Synchronization常見問答集 {#syncwithlaunch-faq}

您可以透過專屬的技術工作流程，將Adobe Launch行動裝置屬性匯入Adobe Campaign **[!UICONTROL Sync with Launch]** Standard。 For more information, refer to this [page](../../administration/using/technical-workflows.md)

下節列出了有關此同步的常見問題。

>[!NOTE]
>
>You will need to submit a ticket to Adobe Customer Care (either directly or through your Adobe contact) to have the **[!UICONTROL syncWithLaunch]** technical workflow enabled in your Campaign instance.

## 我在(組織單位 [!DNL Launch] ALL的非管理員)中建立屬性。 我的應用程式在Adobe Campaign中處於「準備好設定」狀態，但無法開啟／設定它。 {#configuring-property}

只有組織單位ALL的管理員才能在Adobe Campaign Standard中設定行動應用程式。 配置完成後，只有指定組織單位的用戶可以編輯應用程式。 For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## 我無法編輯Adobe Campaign Standard中已設定的行動應用程式，而行動應用程式僅為讀模式。 {#read-mode-mobile-app}

請在區段中檢查行動應用程式的組織 **[!UICONTROL Access Authorization ]** 單位。 只有已指派的組織單位的使用者可以編輯行動應用程式。

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## 我是Adobe Campaign Standard中組織單位為ALL的管理員，但無法設定行動應用程式。 {#org-unit-mobile}

將組織單元設定為ALL的管理員應具有中所有移動屬性的權 [!DNL Launch] 限，以配置移動應用程式。

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## 我在中建立了行動裝置屬 [!DNL Launch] 性，但Adobe Campaign Standard中看不到我的屬性。 {#visibility-mobile-property}

1. 檢查Adobe Campaign Standard擴充功能是否已安裝在中的行動裝置屬性中 [!DNL Launch]。

1. 驗證擴展中實例的端點配置是否正確。

1. 檢查「Launch_URL_Campaign」或「NmsServer_URL」是否正確。

1. 然後，檢查與Adobe Campaign之間的同 [!DNL Launch] 步是否已透過技術工作流程 **[!UICONTROL syncWithLaunch]** 完成。

## 如何檢查Adobe Campaign和Launch之間的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard的進階功能表中，選取 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟工作 **[!UICONTROL syncWithLaunch]** 流程。

1. 檢查工作流程是否已結束且無錯誤。

1. 簽入已啟用工作流同步並成功完成的日誌。

## 我已在Launch中重設已設定行動應用程式的按鍵。 如何在Launch中重新配置密鑰？ {#configuring-pkey}

1. 在Adobe Launch中開啟行動裝置屬性。

1. 在重設PKey的Adobe Campaign Standard擴充功能中設定新URL。

1. 儲存它，讓工作流程在Adobe Campaign和之間同步 [!DNL Launch]。

1. 同步完成後，在中開啟mobile屬性 [!DNL Launch]。

1. 在已重設PKey的Adobe Campaign Standard擴充功能中設定正確的URL。

1. 儲存並讓工作流程重新同步。

1. 只有這樣，屬性才會出現 **[!UICONTROL Ready to Configure]** 在Adobe Campaign中的狀態，而且現在可以設定。

## 我想在Adobe Campaign中設定行動裝置屬性。 我是否必須等待技術工作流程在Adobe Launch和Adobe Campaign之間同步？

您可以立即執行工作流：

1. 在Adobe Campaign Standard的進階功能表中，選取 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟工作 **[!UICONTROL syncWithLaunch]** 流程。

1. Click on the **[!UICONTROL Scheduler]** activity and select **[!UICONTROL Immediate execution]**.
