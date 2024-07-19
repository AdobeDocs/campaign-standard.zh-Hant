---
title: 與Launch同步技術工作流程常見問題集
description: 關於Adobe Launch技術工作流程的常見問題
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 1%

---

# Adobe Experience Platform 同步常見問答集中的標籤 {#syncwithlaunch-faq}

您可以透過&#x200B;**[!UICONTROL Sync with Launch]**&#x200B;專用的技術工作流程，將標籤行動屬性匯入Adobe Campaign Standard。 如需詳細資訊，請參閱此[頁面](../../administration/using/technical-workflows.md)

下節列出此同步的常見問題。

## 我已建立標籤屬性（不是組織單位ALL的管理員）。 我的應用程式在Adobe Campaign中處於準備設定狀態，但無法開啟/設定。 {#configuring-property}

只有組織單位的管理員才能在Adobe Campaign Standard中設定行動應用程式。 設定後，只有指派的組織單位使用者可以編輯
應用程式。 如需組織單位的詳細資訊，請參閱此[頁面](../../administration/using/organizational-units.md)。

## 我無法在Adobe Campaign Standard中編輯已設定的行動應用程式，而行動應用程式處於唯讀模式。 {#read-mode-mobile-app}

檢查&#x200B;**[!UICONTROL Access Authorization]**&#x200B;區段中行動應用程式的組織單位。 只有指派的組織單位的使用者才能編輯行動應用程式。

如需組織單位的詳細資訊，請參閱此[頁面](../../administration/using/organizational-units.md)。

## 我是Adobe Campaign Standard組織單位ALL的管理員，但無法設定行動應用程式。 {#org-unit-mobile}

組織單位設定為「全部」的管理員應擁有所有標籤行動屬性的許可權，才能設定行動應用程式。

如需組織單位的詳細資訊，請參閱此[頁面](../../administration/using/organizational-units.md)。

## 我已建立標籤行動屬性，但我的屬性未顯示在Adobe Campaign Standard中。 {#visibility-mobile-property}

1. 檢查資料收集UI的行動屬性中是否已安裝Adobe Campaign Standard擴充功能。

1. 驗證擴充功能中執行個體的端點是否已正確設定。

1. 檢查「Launch_URL_Campaign」或「NmsServer_URL」是否正確。

1. 然後，檢查同步處理是否已使用&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;技術工作流程完成。

## 如何檢查Adobe Campaign與Adobe Experience Platform中的標籤之間的同步是否已完成？ {#sync-campaign-launch}

1. 在Adobe Campaign Standard中，從進階功能表選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流程。

1. 檢查工作流程是否已結束且沒有錯誤。

1. 在記錄中檢查是否已啟用工作流程同步並成功完成。

## 我為已設定的標籤行動應用程式重設金鑰。 如何在資料收集UI中重新設定金鑰？ {#configuring-pkey}

1. 在資料收集UI中開啟行動屬性。

1. 在Adobe Campaign Standard擴充功能中，設定要重設PKey的新URL。

1. 儲存並讓工作流程同步。

1. 同步完成後，在資料收集UI中開啟行動屬性。

1. 在已重設PKey的Adobe Campaign Standard擴充功能中，設定正確的URL。

1. 將其儲存，然後讓工作流程同步處理再次執行。

1. 只有到那時，屬性才會在Adobe Campaign中以&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;狀態出現，並且現在可以設定。

## 我想要在Adobe Campaign中設定行動屬性。 我是否必須等候技術工作流程在Adobe Experience Platform和Adobe Campaign中的標籤之間同步？

您可以立即執行工作流程：

1. 在Adobe Campaign Standard中，從進階功能表選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。

1. 開啟&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流程。

1. 按一下&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動並選取&#x200B;**[!UICONTROL Immediate execution]**。
