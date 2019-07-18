---
title: 更新資料庫結構
seo-title: 更新資料庫結構
description: 更新資料庫結構
seo-description: 瞭解如何更新Adobe Campaign資料庫。
page-status-flag: 從未啓動
uuid: 6c802f4f-d298-4ca4-acdb-09f2 ad3865 b
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 新增或延伸-資源
discoiquuid: 2448b126-66b8-4608-aa6 c-8028fb1902 a4
context-tags: 部署，主要；eventCusResource，總覽
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Updating the database structure{#updating-the-database-structure}

若要讓您修改資料模型有效且能夠使用它們，必須更新資料庫結構。

>[!NOTE]
>
>Adobe會在自動更新期間自動重新整理自訂資源。

## Publishing a custom resource {#publishing-a-custom-resource}

若要套用在資源上執行的變更，您必須執行資料庫更新。

>[!NOTE]
>
>如果事件上使用的自訂資源欄位遭到修改或刪除，對應的事件將自動解除發佈。See [Configuring Transactional messaging](../../administration/using/configuring-transactional-messaging.md).

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Publishing]**.
1. By default, the option **[!UICONTROL Determine modifications since the last publication]** is checked, which means that only the changes carried out since the last update will be applied.

   >[!NOTE]
   >
   >The **[!UICONTROL Repair database structure]** reestablishes a correct configuration if the publication failed before completing. 將會刪除直接在資料庫中進行的修改，且不會使用自訂資源。

   ![](assets/schema_extension_12.png)

1. Click the **[!UICONTROL Prepare publication]** button to start the analysis. 請注意，當執行個體不會依工作流程急迫忙碌時，應先更新表格。

   To learn more on the action to perform on the Profiles &amp; Services API, refer to [Publishing a resource with API extension](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).

   ![](assets/schema_extension_13.png)

1. Once the publication has been carried out, click the **[!UICONTROL Publish]** button to apply your new configurations.
1. Once published, the **[!UICONTROL Summary]** pane of each resource indicates that the status is now **[!UICONTROL Published]** and specifies the date of the last publication.

   >[!NOTE]
   >
   >如果您對資源進行了新的變更，您必須重復此作業，才能套用變更。

   If resources have the **[!UICONTROL Pending re-draft]** status before publishing, then an additional message will appear inviting you to check your actions because publishing will result in definitive changes (deleting columns, tables...). To help you carry out this last change, an **[!UICONTROL SQL Script]** tab is available. 它提供將在出版物期間執行的SQL命令。

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >You can stop the Re-draft process by clicking the **[!UICONTROL Cancel re-draft]** button. 此動作會將資源的狀態回復回原始的狀態。

1. If your publication failed, you can always go back to the previous publication by clicking **[!UICONTROL Back to latest successful publication]**.

   請注意，如果您將出版物保持失敗狀態，快顯視窗會在您登入執行個體時開啓，提醒您修正此出版物。除非您的出版物已修正，否則您的實例將不會升級為新產品版本。

   ![](assets/schema_extension_31.png)

## Publishing a resource with API extension {#publishing-a-resource-with-api-extension}

您可以在下列情況下建立描述檔和服務API：

* When you extend the custom resources **[!UICONTROL Profiles]** or **[!UICONTROL Services]**, you can perform an update of the Profiles and Services API to integrate the fields declared in the custom resources extension.
* When you define a custom resource and you create a link between the resources **[!UICONTROL Profiles]** or **[!UICONTROL Services]** and the custom resource, you can perform an update to include the new resource in the API.

您可以在出版物畫面中選取此選項。

* 如果API尚未發佈(亦即您從未擴充資源，或者您尚未勾選此資源或其他資源的選項)，則您可以選擇建立此選項。

   ![](assets/create-profile-and-services-api.png)

* 如果API已發佈(亦即您已延長資源並勾選此選項一次)，則會強制API更新。

   確實地，當您在每次發佈時，API都會自動更新。這是為了避免中斷此API的設定檔或服務資源，並強化您的執行個體。

Note that by default, the custom resource is integrated, but, for a specific behavior, if you don't want to publish this resource, you can select the option **[!UICONTROL Hide this resource from APIs]** available in the **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

**[!UICONTROL Prepare Publication]** 在步驟之後，Adobe Campaign會在標籤 **[!UICONTROL Profiles & Services API Preview]**&#x200B;中的最新版本API與未來版本之間顯示Delta。如果您第一次延伸API，delta會將現成可用的自訂資源定義與您的擴充功能進行比較。

標籤中顯示的資訊可分為三個區段：新增、刪除和修改的元素。

![](assets/extendpandsapi_diff.png)

delta的分析是強制步驟，因為出版物步驟將修改API行為，很可能會影響到Domino效果中的周圍開發。

>[!NOTE]
>
>This publication updates the **[!UICONTROL profilesAndServicesExt]** API. **[!UICONTROL profilesAndServices]** API未更新。

For more information on the Adobe Campaign API, consult the dedicated Adobe Campaign documentation on [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
