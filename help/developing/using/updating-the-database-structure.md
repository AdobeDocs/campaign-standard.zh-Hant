---
title: 更新資料庫結構
seo-title: 更新資料庫結構
description: 更新資料庫結構
seo-description: 瞭解如何更新Adobe Campaign資料庫。
page-status-flag: 從未激活
uuid: 6c802f4f-d298-4ca4-acdb-09f2ad3865b9
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 開發
content-type: 參考
topic-tags: 添加或擴展資源
discoiquuid: 2448b126-66b8-4608-aa6c-8028fb1902a4
context-tags: deploy,main;eventCusResource，概述
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# 更新資料庫結構{#updating-the-database-structure}

要使您對資料模型的修改生效並能夠使用，需要更新資料庫結構。

>[!NOTE]
>
>自訂資源會在Adobe執行自動更新期間自動重新整理。

## 發佈自訂資源 {#publishing-a-custom-resource}

要應用對資源執行的更改，必須執行資料庫更新。

>[!NOTE]
>
>如果修改或刪除了用於事件的自定義資源的欄位，則相應的事件將自動取消發佈。 請參 [閱配置事務性消息](../../administration/using/configuring-transactional-messaging.md)。

1. 從進階功能表，透過Adobe Campaign標誌，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**，然後 **[!UICONTROL Publishing]**。
1. 依預設會勾選 **[!UICONTROL Determine modifications since the last publication]** 選項，這表示僅套用自上次更新後所進行的變更。

   >[!NOTE]
   >
   >如果 **[!UICONTROL Repair database structure]** 發佈在完成之前失敗，則重新建立正確的配置。 將刪除直接在資料庫中執行且未使用自定義資源的任何修改。

   ![](assets/schema_extension_12.png)

1. 按一下 **[!UICONTROL Prepare publication]** 按鈕以啟動分析。 請注意，當執行個體未因工作流程而忙碌時，應進行大型表格更新。

   若要進一步瞭解在Profiles &amp; Services API上執行的動作，請參閱「 [Publishing a resource with API extension](#publishing-a-resource-with-api-extension)」。

   ![](assets/schema_extension_13.png)

1. 發佈完成後，按一下按鈕以 **[!UICONTROL Publish]** 應用新配置。
1. 發佈後，每 **[!UICONTROL Summary]** 個資源的窗格會指出狀態現在為 **[!UICONTROL Published]** 並指定上次發佈的日期。

   >[!NOTE]
   >
   >如果對資源進行了新更改，則必須對要應用的更改重複此操作。

   如果資源在發佈 **[!UICONTROL Pending re-draft]** 前具有狀態，則會出現其他訊息，邀請您檢查動作，因為發佈會導致最終變更（刪除欄、表格……）。 為協助您執行上次的變更，可使用 **[!UICONTROL SQL Script]** 標籤。 它提供將在發佈期間執行的SQL命令。

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >按一下按鈕可以停止「重新繪製」 **[!UICONTROL Cancel re-draft]** 進程。 此操作會將資源的狀態恢復為原始狀態。

1. 如果您的出版物失敗，您隨時都可以按一下，返回上一個出版物 **[!UICONTROL Back to latest successful publication]**。

   請注意，如果您的出版物處於失敗狀態，當您登入您的例項時，會立即開啟一個快顯視窗，提醒您修正此出版物。 除非您的出版物已修正，否則您的實例將不會升級為新產品版本。

   ![](assets/schema_extension_31.png)

## 使用API擴充功能發佈資源 {#publishing-a-resource-with-api-extension}

在下列情況下，您可以建立描述檔和服務API:

* 當您擴充自訂資源 **[!UICONTROL Profiles]** 或 **[!UICONTROL Services]**&#x200B;時，可執行Profiles and Services API的更新，以整合自訂資源擴充功能中宣告的欄位。
* 當您定義自訂資源並建立資源或自訂資 **[!UICONTROL Profiles]** 源之 **[!UICONTROL Services]** 間的連結時，您可以執行更新，將新資源納入API中。

您可以在出版物畫面中選取此選項。

* 如果尚未發佈API（亦即，若您尚未擴充資源，或您尚未針對此資源或其他資源勾選此選項），您可以選擇是否建立它。

   ![](assets/create-profile-and-services-api.png)

* 如果API已發佈（亦即您已擴充資源並勾選此選項一次），則會強制進行API更新。

   事實上，一旦建立API後，每次您再次發佈API時，就會自動更新它。 這是為了避免中斷此API的描述檔或服務資源，並損害您的例項。

請注意，自訂資源依預設會整合，但是，若您不想發佈此資源，則可選擇中的可 **[!UICONTROL Hide this resource from APIs]** 用選項 **[!UICONTROL Resource Properties]**。

![](assets/removefromextoption.png)

步驟後， **[!UICONTROL Prepare Publication]** Adobe Campaign會在標籤中的出版物後，顯示API目前版本與未來版本之間的差值 **[!UICONTROL Profiles & Services API Preview]**。 如果您第一次擴充API,Delta會比較現成可用的自訂資源定義與您的擴充功能。

頁籤中顯示的資訊分為三個部分：新增、刪除和修改的元素。

![](assets/extendpandsapi_diff.png)

由於發佈步驟將修改API行為，因此對delta的分析是必備步驟，而且很可能會影響周圍的開發，產生多米諾效應。

>[!NOTE]
>
>此出版物會更新 **[!UICONTROL profilesAndServicesExt]** API。 未 **[!UICONTROL profilesAndServices]** 更新API。

如需Adobe Campaign API的詳細資訊，請參閱 [Adobe IO上的專屬Adobe Campaign檔案](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html)。
