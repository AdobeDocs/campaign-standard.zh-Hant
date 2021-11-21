---
title: 刪除資源
description: '了解如何刪除資源 '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: 4ddfdbcc-a154-4c10-a97e-73ad888d1f1f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---

# 刪除資源{#deleting-a-resource}

若要刪除資源，相關資源必須是 **[!UICONTROL Draft]**. 資源位於 **[!UICONTROL Draft]** 狀態（如果）:

* 它剛剛建立，尚未發佈。
* 如果已經發佈，則必須重新起草資源。

>[!IMPORTANT]
>
>重新起草和刪除自訂資源是可能影響其他資源的敏感操作。 這些動作只能由專家使用者執行。

要重新草稿和刪除已發佈的資源，請執行以下操作：

1. 選取要重新繪製的資源。
1. 按一下動作列中的 **[!UICONTROL Re-draft]** 按鈕。

   ![](assets/schema_extension_uc26.png)

1. 按一下&#x200B;**[!UICONTROL Ok]**。

   >[!IMPORTANT]
   >
   >這一行動是明確的：發佈修改時，資源的資料庫表或列及其資料將被永久刪除，這可能導致其他自訂資源的連結中斷。 只有資源定義將保持可用。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >如果重新繪製現成可用的擴展 **設定檔（設定檔）** 資源，您也必須重新草稿任何 **測試配置檔案(seedMember)** 您可能已定義的擴充功能。 如需擴充設定檔資源的詳細資訊，請參閱 [本節](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. 發佈資源。 如需更多詳細步驟，請參閱 [發佈自訂資源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   然後，資源會進入 **草稿** 模式及其激活狀態為 **[!UICONTROL Inactive]**.

1. 在 **[!UICONTROL List]** 模式，檢查要刪除的資源，然後按一下 ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** 表徵圖。

   ![](assets/schema_extension_uc28.png)

資源會從資料模型中刪除。

>[!NOTE]
>
>如果修改或刪除用於事件之自訂資源的欄位，則相對應的事件將會自動取消發佈。請參閱 [取消發佈交易式事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
