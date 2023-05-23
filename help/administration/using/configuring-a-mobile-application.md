---
title: 設定行動應用程式
description: 瞭解如何配置Adobe Campaign以使用Experience PlatformSDK發送推送通知或應用內消息
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 3%

---

# 設定行動應用程式{#configuring-a-mobile-application}

## 使用Adobe Experience PlatformSDK配置移動應用程式 {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
> Adobe Experience Platform Launch已被改名為Adobe Experience Platform的一套資料收集技術。 因此，在產品文檔中已進行了一些術語更改。 請參閱 [下文](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html) 的下一頁。

請注意，推送通知和In-App實現必須由專家用戶執行。 要獲得幫助，請與您的Adobe客戶主管或專業服務合作夥伴聯繫。

要使用Experience PlatformSDK應用程式發送推送通知和In-App消息，必須在資料收集UI中設定移動應用程式並在Adobe Campaign中配置。

設定移動應用程式後，您可以檢索它收集的PII資料，以從資料庫建立或更新配置檔案。 有關詳細資訊，請參閱本節： [基於移動應用資料建立和更新簡檔資訊](../../channels/using/updating-profile-with-mobile-app-data.md)。

要瞭解有關使用Adobe Experience PlatformSDK在Adobe Campaign Standard支援的不同移動使用案例的更多資訊，請參閱此 [頁](../../administration/using/supported-mobile-use-cases.md)。

要完成配置，請完成以下步驟：

1. 在Adobe Campaign，確保可以訪問以下內容：
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   如果沒有，請與您的客戶團隊聯繫。

1. 檢查您的用戶是否在Adobe Campaign Standard和Adobe Experience Platform擁有必要的權限。
   * 在Adobe Campaign Standard，確保IMS用戶是標準用戶和管理員產品配置檔案的一部分。 此步驟允許用戶登錄到Adobe Campaign Standard，導航到Experience PlatformSDK移動應用頁面，並查看在資料收集UI中建立的移動應用屬性。

   * 在「資料收集UI」中，確保您的IMS用戶是Experience Platform Launch產品配置檔案的一部分。
此步驟允許用戶登錄到資料收集UI以建立和查看屬性。 有關資料收集UI中產品配置檔案的詳細資訊，請參閱 [建立您的產品配置檔案](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/manage-permissions.html#gain-admin-rights-for-a-tags-product-profile)。 在產品配置檔案中，不應對公司或屬性設定任何權限，但用戶仍應能夠登錄。

   要完成其他任務，如安裝擴展、發佈應用、配置環境等，您需要在產品配置檔案中設定權限。

1. 在資料收集UI中，建立 **[!UICONTROL Mobile property]**。 如需詳細資訊，請參閱[設定行動裝置屬性](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property)。

1. 在資料收集UI中，按一下 **[!UICONTROL Extensions]** 頁籤，轉到 **[!UICONTROL Catalog]**，並搜索 **[!UICONTROL Adobe Campaign Standard]** 擴展。 有關詳細資訊，請參見 [Adobe Campaign Standard](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard)。

1. 要支援Campaign Standard中的位置使用案例，請安裝 **[!UICONTROL Places]** 資料收集UI中的擴展。 請參閱此 [頁](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html)。

1. 在Adobe Campaign Standard，配置在資料收集UI中建立的移動屬性。 請參閱 [在Adobe Campaign設定您的Adobe Experience Platform Launch應用程式](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)。

1. 將特定通道的設定新增至行動應用程式設定。如需詳細資訊，請參閱[ Adobe Campaign 中的通道特定應用程式設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)。

1. 如果需要，可以刪除標籤屬性。
有關詳細資訊，請參見 [刪除應用程式](../../administration/using/configuring-a-mobile-application.md#delete-app)。

## 從啟動技術工作流同步移動應用AEPSDK {#aepsdk-workflow}

在資料收集UI中建立和配置移動屬性後， **[!UICONTROL Sync Mobile app AEPSDK from Launch]** 技術工作流現在將同步在Adobe Campaign Standard導入的標籤移動屬性。

預設情況下，技術工作流每15分鐘啟動一次。 如果需要，可以手動重新啟動它：

1. 在Adobe Campaign Standard，從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**。
1. 開啟 **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** 工作流。

   ![](assets/launch_10.png)

1. 按一下 **[!UICONTROL Scheduler]** 的子菜單。

1. 選取 **[!UICONTROL Immediate execution]**。

   ![](assets/launch_11.png)

您的工作流現在將重新啟動並同步在Adobe Campaign Standard導入的標籤移動屬性。

## 在Adobe Campaign設定應用程式 {#set-up-campaign}

要在市場活動中使用標籤移動屬性，您還必須在Adobe Campaign配置此屬性。 在Adobe Campaign，確保IMS用戶是標準用戶和管理員產品配置檔案的一部分。

您必須等待技術工作流運行並將標籤移動屬性同步到Adobe Campaign。 然後，您可以在Adobe Campaign配置它。

有關從「啟動」技術工作流同步Mobile應用AEPSDK的詳細資訊，請參閱此 [節](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)。

>[!NOTE]
>
>預設情況下，將組織單位設定為ALL的管理員可以編輯移動應用程式。

1. 從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

   ![](assets/launch.png)

1. 選擇在資料收集UI中建立的移動應用程式。
其 **[!UICONTROL Property Status]** 應該 **[!UICONTROL Ready to configure]**。

   >[!NOTE]
   >
   >預設情況下，要檢索在資料收集UI中建立的移動應用程式清單，Campaign Standard使用NmsServer_URL選項中定義的值來查找匹配的屬性。
   >
   >在某些情況下，移動應用程式的市場活動終結點可能不同於NmsServer_URL中定義的終結點。 在這種情況下，在 `Launch_URL_Campaign` 的雙曲餘切值。 市場活動將使用此選項中的值在資料收集UI中查找匹配屬性。

   ![](assets/launch_4.png)

1. 您可以在 **[!UICONTROL Access Authorization]** 將此移動應用程式的訪問權限限制到特定組織單位。 如需詳細資訊，請參閱本頁面。

   在此，管理員可以通過從下拉清單中選擇子組織單位來分配這些單位。

   ![](assets/launch_12.png)

1. 要在Adobe Experience Platform的「活動」和標籤之間建立連接，請按一下 **[!UICONTROL Save]**。

1. 驗證移動應用的狀態是否已從 **[!UICONTROL Ready to Configure]** 至 **[!UICONTROL Configured]**。

   當「市場活動」擴展顯示已成功設定密鑰時，您還可以驗證是否在「市場活動」中成功設定了屬性。

   ![](assets/launch_5.png)

1. 要使此配置生效，需要在資料收集UI中發佈更改。

   有關詳細資訊，請參見 [發佈配置](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

## 在Adobe Campaign的特定於渠道的應用程式配置 {#channel-specific-config}

您的移動應用程式現在已準備好在市場活動中用於推送通知或應用內交付。 現在，如果需要，您可以進一步配置它，以建立將觸發In-App消息和/或上載推式證書的事件。

1. 從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**。

1. 選擇在資料收集UI中建立和配置的移動應用程式。

1. 在 **[!UICONTROL Mobile application properties]** 頁籤，您可以開始添加在移動應用程式中可用於In-App消息的事件。

1. 要配置事件，請按一下 **[!UICONTROL Create Element]**。

   ![](assets/launch_6.png)

1. 鍵入名稱和說明。

   ![](assets/launch_7.png)

1. 按一下&#x200B;**[!UICONTROL Add]**。

   建立In-App消息時，您的事件現在可在「觸發器」頁籤上使用。 有關詳細資訊，請參見 [準備和發送應用內消息](../../channels/using/preparing-and-sending-an-in-app-message.md)。

1. 在 **[!UICONTROL Device-specific settings]** 在移動應用程式儀表板的部分，為每個設備提供應用程式詳細資訊，包括iOS的證書和Android的伺服器密鑰。

   上載證書後，將顯示一條消息通知您上載成功並顯示證書的過期日期。

   >[!NOTE]
   >
   >在Adobe Campaign Standard成功添加證書後，您將無法再更改您的設定，因為只能將一個APNS平台（生產或沙盒）添加到MCPNS應用。

   ![](assets/launch_8.png)

1. 按一下 **[!UICONTROL Mobile application subscribers]** 頁籤，查看訂閱伺服器清單以及有關這些訂閱伺服器的其他資訊，例如，他們是否選擇不使用您的通知。

## 刪除應用程式 {#delete-app}

>[!CAUTION]
>
>無法刪除應用程式。

要刪除應用程式，請完成中的步驟 [刪除移動屬性](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#deleting-mobile-properties-in-the-data-collection-ui)。

刪除應用程式後，在Adobe Campaign，驗證應用程式的屬性狀態是否已正確更新為「在啟動時刪除」。

通過按一下您在Adobe Campaign的應用程式，您可以選擇通過按一下「從市場活動中刪除」從Adobe Campaign完全刪除此應用程式。

![](assets/launch_9.png)
