---
title: 刪除資源
seo-title: 刪除資源
description: 刪除資源
seo-description: '瞭解如何刪除資源 '
page-status-flag: 從未啓動
uuid: de de27589-1fa5-412c-8e5a-a-a4976 de05715
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 開發
content-type: reference
topic-tags: 新增或延伸-資源
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2 c8 f44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Deleting a resource{#deleting-a-resource}

To delete a resource, the resource in question must be a **[!UICONTROL Draft]**. The resource is in **[!UICONTROL Draft]** status if:

* 它剛建立且尚未發佈。
* 如果已發佈，則必須重新草擬資源。

>[!CAUTION]
>
>重新起草和刪除自訂資源是敏感性作業，可能會影響其他資源。這些動作只能由專家使用者執行。

若要重新草稿和刪除已發佈的資源：

1. 選取您要重新草稿的資源。
1. Click the **[!UICONTROL Re-draft]** button in the action bar.

   ![](assets/schema_extension_uc26.png)

1. Click **[!UICONTROL Ok]**.

   >[!CAUTION]
   >
   >此動作具有決定性：資源的資料庫表格或欄及其資料會在修改後永久刪除，這可能會導致其他自訂資源中的連結中斷。只有資源定義才能使用。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >If you re-draft an extension of the out-of-the-box **Profiles (profile)** resource, you must also re-draft any **Test profile (seedMember)** extension you may have defined. For more on extending the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. 發佈資源。For more detailed steps, refer to [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   The resource then goes into **Draft** mode and its activation status is **[!UICONTROL Inactive]**.

1. **[!UICONTROL List]** 在模式中，檢查要刪除的資源，然後按一下 ![](assets/delete_darkgrey-24px.png)**[!UICONTROL Delete element]** 圖示。

   ![](assets/schema_extension_uc28.png)

您的資源會從資料模型中刪除。

>[!NOTE]
>
>如果事件上使用的自訂資源欄位遭到修改或刪除，對應的事件將自動解除發佈。See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

