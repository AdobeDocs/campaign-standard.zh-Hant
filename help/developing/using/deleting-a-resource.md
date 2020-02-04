---
title: 刪除資源
description: '瞭解如何刪除資源 '
page-status-flag: never-activated
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f7f4f3d81f4e6a540b3317f283c1e2311ccc65a

---


# 刪除資源{#deleting-a-resource}

要刪除資源，相關資源必須是 **[!UICONTROL Draft]**。 如果滿足以下條件，則資**[!UICONTROL Draft]** 源處於狀態：

* 它剛剛建立，尚未發佈。
* 如果已經發佈，則必須重新起草資源。

>[!CAUTION]
>
>重新起草和刪除自定義資源是可能影響其他資源的敏感操作。 這些動作必須僅由專家使用者執行。

要重新草擬和刪除已發佈的資源，請執行以下操作：

1. 選擇要重新繪製的資源。
1. 按一下 **[!UICONTROL Re-draft]**動作列中的按鈕。

   ![](assets/schema_extension_uc26.png)

1. 按一下 **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >這一行動是明確的：在發佈修改時，資源的資料庫表或列及其資料將被永久刪除，這可能導致來自其他自定義資源的連結中斷。 只有資源定義仍可用。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >如果重新繪製現成可用的配置檔案（配置檔案）資源的擴展，則還必須重新繪製您可能已定義的 **Test配置檔案(seedMember)****** 。 如需擴充描述檔資源的詳細資訊，請參 [閱本節](../../developing/using/extending-the-profile-resource-with-a-new-field.md)。

1. 發佈資源。 如需詳細步驟，請參閱 [發佈自訂資源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   然後，資源會進入 **Draft** （草稿）模式，其啟動狀態為 **[!UICONTROL Inactive]**。

1. 在模 **[!UICONTROL List]**式中，檢查要刪除的資源，然後按一下![](assets/delete_darkgrey-24px.png)圖**[!UICONTROL Delete element]** 標。

   ![](assets/schema_extension_uc28.png)

資源會從資料模型中刪除。

>[!NOTE]
>
>如果修改或刪除了用於事件的自定義資源的欄位，則相應的事件將自動取消發佈。 See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

