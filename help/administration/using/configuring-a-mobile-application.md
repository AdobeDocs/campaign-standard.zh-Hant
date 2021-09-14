---
title: 設定行動應用程式
description: 探索如何設定Adobe Campaign以使用SDK V4或Experience PlatformSDK傳送推播通知或應用程式內訊息。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 7%

---

# 設定行動應用程式{#configuring-a-mobile-application}

## 使用Adobe Experience Platform SDK設定行動應用程式 {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>推播通知和應用程式內實作必須由專家使用者執行。 如果您需要協助，請聯絡您的 Adobe 客戶主管或專業服務合作夥伴。

若要透過Experience PlatformSDK應用程式傳送推播通知和應用程式內訊息，行動應用程式必須在Adobe Experience PlatformExperience PlatformExperience Platform Launch中設定，並在Adobe Campaign中設定。

如需已棄用功能Mobile第4版SDK的詳細資訊，請參閱此[page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html)。

設定行動應用程式後，您就可以擷取其收集的PII資料，以從資料庫建立或更新設定檔。 如需詳細資訊，請參閱本區段：[根據行動應用程式資料](../../channels/using/updating-profile-with-mobile-app-data.md)建立和更新設定檔資訊。

若要進一步了解Adobe Campaign Standard中使用Adobe Experience Platform SDK支援的不同行動使用案例，請參閱此[page](https://helpx.adobe.com/tw/campaign/kb/configure-launch-rules-acs-use-cases.html)。

若要完成設定，請完成下列步驟：

1. 在Adobe Campaign中，請確定您可以存取下列項目：
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   如果沒有，請連絡您的帳戶團隊。

1. 檢查您的使用者是否擁有Adobe Campaign Standard和Experience Platform Launch中的必要權限。
   * 在Adobe Campaign Standard中，確認IMS使用者屬於標準使用者和管理員產品設定檔的一部分。 此步驟可讓使用者登入Adobe Campaign Standard、導覽至Experience PlatformSDK行動應用程式頁面，以及檢視您在Experience Platform Launch中建立的行動應用程式屬性。

   * 在Experience Platform Launch中，確認您的IMS使用者屬於Experience Platform Launch產品設定檔。
此步驟可讓使用者登入Experience Platform Launch以建立和檢視屬性。 如需Experience Platform Launch中產品設定檔的詳細資訊，請參閱建立產品設定檔。 在產品設定檔中，不應設定公司或屬性的權限，但使用者應仍可登入。

   若要完成其他工作，例如安裝擴充功能、發佈應用程式、設定環境等，您必須在產品設定檔中設定權限。

1. 在Experience Platform Launch中，建立&#x200B;**[!UICONTROL Mobile property]**。 如需詳細資訊，請參閱[設定行動裝置屬性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在Experience Platform Launch中，按一下&#x200B;**[!UICONTROL Extensions]**&#x200B;標籤，前往&#x200B;**[!UICONTROL Catalog]**&#x200B;並搜尋&#x200B;**[!UICONTROL Adobe Campaign Standard]**&#x200B;擴充功能。 如需詳細資訊，請參閱[Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

1. 若要在Campaign Standard中支援位置使用案例，請安裝&#x200B;**[!UICONTROL Places]**&#x200B;擴充功能和&#x200B;**[!UICONTROL Places Monitor]**&#x200B;擴充功能。
   * 以Experience Platform Launch安裝&#x200B;**[!UICONTROL Places]**&#x200B;擴充功能。 請參閱此[page](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html)。
   * 以Experience Platform Launch安裝&#x200B;**[!UICONTROL Places Monitor]**&#x200B;擴充功能。 請參閱此[page](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. 在　Adobe Campaign Standard　中，設定您在　Experience Platform Launch　中建立的行動裝置屬性。請參閱在Adobe Campaign中設定Adobe Experience Platform Launch應用程式](../../administration/using/configuring-a-mobile-application.md#set-up-campaign) 。[

1. 將特定通道的設定新增至行動應用程式設定。如需詳細資訊，請參閱[ Adobe Campaign 中的通道特定應用程式設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 如有需要，您可以刪除Experience Platform Launch屬性。
如需詳細資訊，請參閱[刪除Experience Platform Launch應用程式](../../administration/using/configuring-a-mobile-application.md#delete-app)。

## 從Launch技術工作流程同步行動應用程式AEPSDK {#aepsdk-workflow}

在Experience Platform Launch中建立和設定您的行動屬性後，**[!UICONTROL Sync Mobile app AEPSDK from Launch]**&#x200B;技術工作流程現在會同步在Adobe Campaign Standard中匯入的AdobeLaunch行動屬性。

依預設，技術工作流程每15分鐘開始一次。 如有需要，可手動重新啟動：

1. 在Adobe Campaign Standard中，從進階功能表中選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。
1. 開啟&#x200B;**[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**&#x200B;工作流程。

   ![](assets/launch_10.png)

1. 按一下&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動。

1. 選取 **[!UICONTROL Immediate execution]**。

   ![](assets/launch_11.png)

您的工作流程現在會重新啟動並同步在Adobe Campaign Standard中匯入的AdobeLaunch行動屬性。

## 在Adobe Campaign中設定您的Adobe Experience Platform Launch應用程式 {#set-up-campaign}

若要在Campaign中使用Experience Platform Launch行動屬性，您也需在Adobe Campaign中設定此屬性。 在Adobe Campaign中，確認IMS使用者屬於標準使用者和管理員產品設定檔的一部分。

您需要等待技術工作流程執行，並將Launch行動屬性同步至Adobe Campaign。 接著，您就可以在Adobe Campaign中進行設定。

如需從Launch技術工作流程同步行動應用程式AEPSDK的詳細資訊，請參閱此[區段](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)。

>[!NOTE]
>
>依預設，將組織單位設為「全部」的管理員可以編輯行動應用程式。

1. 從高級菜單中，選擇&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

   ![](assets/launch.png)

1. 選取您在Experience Platform Launch中建立的行動應用程式。
其**[!UICONTROL Property Status]**&#x200B;應為&#x200B;**[!UICONTROL Ready to configure]**。

   >[!NOTE]
   >
   >依預設，若要擷取在Adobe啟動中建立的行動應用程式清單，Campaign Standard會使用NmsServer_URL選項中定義的值來尋找相符的屬性。
   >
   >在某些情況下，行動應用程式的Campaign端點可能與NmsServer_URL中定義的端點不同。 在此情況下，請在Launch_URL_Campaign選項中定義端點。 Campaign會使用此選項中的值，在Campaign Launch中尋找相符的屬性。

   ![](assets/launch_4.png)

1. 您可以在&#x200B;**[!UICONTROL Access Authorization]**&#x200B;區段下變更行動應用程式的組織單位，以限制特定組織單位對此行動應用程式的存取權限。 如需詳細資訊，請參閱本頁面。

   在此，管理員可以從下拉式清單中選取子組織單位，以指派子組織單位。

   ![](assets/launch_12.png)

1. 若要建立Campaign與Experience Platform Launch之間的連線，請按一下&#x200B;**[!UICONTROL Save]**。

1. 確認行動應用程式的狀態已從&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;變更為&#x200B;**[!UICONTROL Configured]**。

   當「Experience Platform Launch促銷活動」擴充功能顯示金鑰已成功設定時，您也可以確認屬性已在促銷活動中成功設定。

   ![](assets/launch_5.png)

1. 若要讓此設定生效，變更必須以Experience Platform Launch發佈。

   如需詳細資訊，請參閱[發佈設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)。

## Adobe Campaign中的通道特定應用程式設定 {#channel-specific-config}

您的行動應用程式現在已準備好用於Campaign以進行推播通知或應用程式內傳遞。 您現在可以視需要進一步設定，以建立會觸發您的應用程式內訊息和/或上傳推送憑證的事件。

1. 從高級菜單中，選擇&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

1. 選取您在Experience Platform Launch中建立和設定的行動應用程式。

1. 在&#x200B;**[!UICONTROL Mobile application properties]**&#x200B;標籤上，您可以開始新增行動應用程式中可用於應用程式內訊息的事件。

1. 要配置事件，請按一下&#x200B;**[!UICONTROL Create Element]**。

   ![](assets/launch_6.png)

1. 輸入名稱和說明。

   ![](assets/launch_7.png)

1. 按一下&#x200B;**[!UICONTROL Add]**。

   現在當您建立應用程式內訊息時，您的事件可在「觸發器」標籤上使用。 如需詳細資訊，請參閱[準備和傳送應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md)。

1. 在行動應用程式控制面板的&#x200B;**[!UICONTROL Device-specific settings]**&#x200B;區段中，針對每個裝置提供應用程式詳細資訊，包括iOS的憑證和Android的伺服器金鑰。

   上傳憑證後，訊息會通知您上傳成功，並顯示憑證的到期日。

   >[!NOTE]
   >
   >在Adobe Campaign Standard中成功新增憑證後，您將無法再將設定變回，因為MCPNS應用程式只能新增一個APNS平台（生產或沙盒）。

   ![](assets/launch_8.png)

1. 按一下&#x200B;**[!UICONTROL Mobile application subscribers]**&#x200B;標籤可查看訂閱者清單以及這些訂閱者的其他相關資訊，例如，他們是否選擇退出您的通知。

## 刪除您的Adobe Experience Platform Launch應用程式 {#delete-app}

刪除Experience Platform Launch應用程式無法還原。

>[!CAUTION]
>
>刪除Experience Platform Launch應用程式無法還原。

若要刪除您的Experience Platform Launch應用程式，請完成[刪除行動屬性](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)中的步驟。

刪除應用程式後，請在Adobe Campaign中確認您應用程式的「屬性」狀態是否已正確更新為Launch中的「已刪除」。

按一下Adobe Campaign中的應用程式，您可以按一下「從促銷活動刪除」 ，選擇從Adobe Campaign中完全移除此應用程式。

![](assets/launch_9.png)
