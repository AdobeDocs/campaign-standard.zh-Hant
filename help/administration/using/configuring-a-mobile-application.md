---
solution: Campaign Standard
product: campaign
title: 設定行動應用程式
description: 瞭解如何設定Adobe Campaign使用SDK V4或Experience PlatformSDK傳送推播通知或應用程式內訊息。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 7%

---


# 設定行動應用程式{#configuring-a-mobile-application}

## 使用Adobe Experience PlatformSDK {#using-adobe-experience-platform-sdk}設定行動應用程式

>[!IMPORTANT]
>
>推播通知和應用程式內建置必須由專家使用者執行。 如果您需要協助，請聯絡您的 Adobe 客戶主管或專業服務合作夥伴。

若要使用Experience PlatformSDK應用程式傳送推播通知和應用程式內訊息，行動應用程式必須在Adobe Experience PlatformExperience PlatformExperience Platform Launch中設定，並在Adobe Campaign進行設定。

有關已過時功能Mobile 4 SDK的更多資訊，請參閱此[頁面](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html)。

設定行動應用程式後，您就可以擷取其收集的PII資料，以從資料庫建立或更新描述檔。 如需更多相關資訊，請參閱本節：[根據行動應用程式資料](../../channels/using/updating-profile-with-mobile-app-data.md)建立和更新描述檔資訊。

若要進一步瞭解使用Adobe Campaign StandardSDK支援的不同行動使用案例，請參閱此[頁面](https://helpx.adobe.com/tw/campaign/kb/configure-launch-rules-acs-use-cases.html)。

要完成配置，請完成以下步驟：

1. 在Adobe Campaign，請確定您可以存取下列項目：
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   如果沒有，請連絡您的帳戶團隊。

1. 檢查您的使用者是否擁有Adobe Campaign Standard和Experience Platform Launch的必要權限。
   * 在Adobe Campaign Standard，請確定IMS使用者是「標準使用者與管理員產品設定檔」的一部分。 此步驟可讓使用者登入Adobe Campaign Standard、導覽至Experience PlatformSDK行動應用程式頁面，以及檢視您在Experience Platform Launch中建立的行動應用程式屬性。

   * 在Experience Platform Launch中，請確定您的IMS使用者是Experience Platform Launch產品設定檔的一部分。
此步驟允許用戶登錄Experience Platform Launch以建立和查看屬性。 如需Experience Platform Launch中產品設定檔的詳細資訊，請參閱建立您的產品設定檔。 在產品設定檔中，公司或屬性上應未設定任何權限，但使用者仍可登入。

   若要完成其他工作，例如安裝擴充功能、發佈應用程式、設定環境等，您必須在產品設定檔中設定權限。

1. 在Experience Platform Launch中，建立&#x200B;**[!UICONTROL Mobile property]**。 如需詳細資訊，請參閱[設定行動裝置屬性](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)。

1. 在Experience Platform Launch中，按一下&#x200B;**[!UICONTROL Extensions]**&#x200B;頁籤，轉到&#x200B;**[!UICONTROL Catalog]** ，然後搜索&#x200B;**[!UICONTROL Adobe Campaign Standard]**&#x200B;副檔名。 如需詳細資訊，請參閱[Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

1. 若要支援Campaign Standard中的位置使用案例，請安裝&#x200B;**[!UICONTROL Places]**&#x200B;擴充功能和&#x200B;**[!UICONTROL Places Monitor]**&#x200B;擴充功能。
   * 在Experience Platform Launch中安裝&#x200B;**[!UICONTROL Places]**&#x200B;擴展。 請參閱此[頁](https://docs.adobe.com/content/help/zh-Hant/places/using/places-ext-aep-sdks/places-extension/places-extension.html)。
   * 在Experience Platform Launch中安裝&#x200B;**[!UICONTROL Places Monitor]**&#x200B;擴展。 請參閱此[頁](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. 在　Adobe Campaign Standard　中，設定您在　Experience Platform Launch　中建立的行動裝置屬性。請參閱[在Adobe Campaign設定您的Adobe Experience Platform Launch應用程式](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)。

1. 將特定通道的設定新增至行動應用程式設定。如需詳細資訊，請參閱[ Adobe Campaign 中的通道特定應用程式設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 如有需要，您可以刪除Experience Platform Launch屬性。
如需詳細資訊，請參閱[刪除Experience Platform Launch應用程式](../../administration/using/configuring-a-mobile-application.md#delete-app)。

## 從Launch技術工作流程{#aepsdk-workflow}同步行動應用程式AEPSDK

在Experience Platform Launch中建立和設定您的行動屬性後，**[!UICONTROL Sync Mobile app AEPSDK from Launch]**&#x200B;技術工作流程現在將同步在Adobe Campaign Standard匯入的Adobe啟動行動屬性。

依預設，技術工作流程每15分鐘開始一次。 如果需要，可以手動重新啟動它：

1. 在Adobe Campaign Standard，從高級菜單中選擇&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。
1. 開啟&#x200B;**[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**&#x200B;工作流程。

   ![](assets/launch_10.png)

1. 按一下&#x200B;**[!UICONTROL Scheduler]**&#x200B;活動。

1. 選取 **[!UICONTROL Immediate execution]**。

   ![](assets/launch_11.png)

您的工作流程現在會重新啟動並同步在Adobe Campaign Standard匯入的Adobe啟動行動裝置屬性。

## 在Adobe Campaign設定您的Adobe Experience Platform Launch應用程式{#set-up-campaign}

若要在Campaign中使用Experience Platform Launch行動裝置屬性，您還需要在Adobe Campaign設定此屬性。 在Adobe Campaign，請確定IMS使用者是「標準使用者與管理員產品設定檔」的一部分。

您需要等待技術工作流程執行，並將Launch mobile屬性同步至Adobe Campaign。 然後，您可以在Adobe Campaign進行配置。

如需從Launch技術工作流程同步行動應用程式AEPSDK的詳細資訊，請參閱此[章節](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)。

>[!NOTE]
>
>依預設，將組織單位設為ALL的管理員可以編輯行動應用程式。

1. 從高級菜單中，選擇&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

   ![](assets/launch.png)

1. 選擇您在Experience Platform Launch中建立的行動應用程式。
其**[!UICONTROL Property Status]**&#x200B;應為&#x200B;**[!UICONTROL Ready to configure]**。

   >[!NOTE]
   >
   >預設情況下，要檢索在Adobe啟動中建立的移動應用程式清單，Campaign Standard使用NmsServer_URL選項中定義的值來查找匹配屬性。
   >
   >在某些情況下，行動應用程式的促銷活動端點可能與NmsServer_URL中定義的端點不同。 在這種情況下，請在Launch_URL_Campaign選項中定義端點。 促銷活動會使用此選項中的值，在Adobe啟動中尋找相符的屬性。

   ![](assets/launch_4.png)

1. 您可以在&#x200B;**[!UICONTROL Access Authorization]**&#x200B;區段下變更行動應用程式的組織單位，將對此行動應用程式的存取限制為特定組織單位。 如需詳細資訊，請參閱本頁面。

   在此，管理員可以通過從下拉清單中選擇子組織單位來指定這些單位。

   ![](assets/launch_12.png)

1. 若要建立促銷活動與Experience Platform Launch之間的連線，請按一下&#x200B;**[!UICONTROL Save]**。

1. 確認行動應用程式的狀態已從&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;變更為&#x200B;**[!UICONTROL Configured]**。

   當Experience Platform Launch促銷活動擴充功能顯示已成功設定索引鍵時，您也可以驗證是否已在促銷活動中成功設定屬性。

   ![](assets/launch_5.png)

1. 要使此配置生效，更改必須以Experience Platform Launch發佈。

   如需詳細資訊，請參閱[發佈組態](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)。

## Adobe Campaign{#channel-specific-config}中特定於通道的應用程式配置

您的行動應用程式現在已可供用於Campaign中推播通知或應用程式內傳送。 您現在可視需要進一步設定，以建立會觸發您的應用程式內訊息和／或上傳推播憑證的事件。

1. 從高級菜單中，選擇&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

1. 選擇您在Experience Platform Launch中建立和設定的行動應用程式。

1. 在&#x200B;**[!UICONTROL Mobile application properties]**&#x200B;標籤上，您可以開始新增行動應用程式中可用於應用程式內訊息的事件。

1. 要配置事件，請按一下&#x200B;**[!UICONTROL Create Element]**。

   ![](assets/launch_6.png)

1. 鍵入名稱和說明。

   ![](assets/launch_7.png)

1. 按一下 **[!UICONTROL Add]**。

   現在，當您建立應用程式內訊息時，「觸發器」標籤上會顯示您的事件。 如需詳細資訊，請參閱[準備和傳送應用程式內訊息](../../channels/using/preparing-and-sending-an-in-app-message.md)。

1. 在行動應用程式儀表板的&#x200B;**[!UICONTROL Device-specific settings]**&#x200B;區段中，針對每個裝置提供應用程式詳細資訊，包括iOS的憑證和Android的伺服器金鑰。

   上傳憑證後，會出現訊息通知您上傳成功，並顯示憑證的到期日。

   >[!NOTE]
   >
   >在Adobe Campaign Standard成功新增憑證後，您將無法再將設定變回原來，因為MCPNS應用程式只能新增一個APNS平台（生產或沙盒）。

   ![](assets/launch_8.png)

1. 按一下&#x200B;**[!UICONTROL Mobile application subscribers]**&#x200B;標籤，查看訂閱者清單以及這些訂閱者的其他資訊，例如，他們是否選擇退出您的通知。

## 刪除您的Adobe Experience Platform Launch應用程式{#delete-app}

無法刪除Experience Platform Launch應用程式。

>[!CAUTION]
>
>無法刪除Experience Platform Launch應用程式。

若要刪除您的Experience Platform Launch應用程式，請完成[刪除行動裝置屬性](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)中的步驟。

刪除應用程式後，在Adobe Campaign，確認您應用程式的「屬性」狀態是否已正確更新為「在啟動中刪除」。

按一下您在Adobe Campaign的應用程式，您就可以選擇按一下「從促銷活動刪除」，將此應用程式從Adobe Campaign完全移除。

![](assets/launch_9.png)
