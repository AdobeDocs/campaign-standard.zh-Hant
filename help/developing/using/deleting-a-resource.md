---
title: 刪除資源
description: 瞭解如何刪除資源
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

若要刪除資源，相關資源必須是&#x200B;**[!UICONTROL Draft]**。 資源處於&#x200B;**[!UICONTROL Draft]**&#x200B;狀態，如果：

* 它剛剛建立且尚未發佈。
* 如果已發佈，則必須重新起草資源。

>[!IMPORTANT]
>
>重新起草和刪除自訂資源是敏感性作業，可能會影響其他資源。 這些動作只能由專家使用者執行。

若要重新草稿並刪除已發佈的資源：

1. 選取您要重新草擬的資源。
1. 按一下動作列中的 **[!UICONTROL Re-draft]** 按鈕。

   ![](assets/schema_extension_uc26.png)

1. 按一下&#x200B;**[!UICONTROL Ok]**。

   >[!IMPORTANT]
   >
   >此動作是確定的：資源的資料庫表格或欄及其資料將在修改發佈時永久刪除，這可能會導致其他自訂資源的連結中斷。 只有資源定義仍然可用。

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >如果您重新草擬現成可用的&#x200B;**設定檔(profile)**&#x200B;資源的擴充功能，也必須重新草擬您可能已定義的任何&#x200B;**測試設定檔(seedMember)**&#x200B;擴充功能。 如需擴充設定檔資源的詳細資訊，請參閱[本節](../../developing/using/extending-the-profile-resource-with-a-new-field.md)。

1. Publish資源。 如需詳細步驟，請參閱[發佈自訂資源](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)。

   資源接著會進入&#x200B;**草稿**&#x200B;模式，其啟用狀態為&#x200B;**[!UICONTROL Inactive]**。

1. 在&#x200B;**[!UICONTROL List]**&#x200B;模式中，檢查要刪除的資源，然後按一下![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**&#x200B;圖示。

   ![](assets/schema_extension_uc28.png)

您的資源會從資料模型刪除。

>[!NOTE]
>
>如果修改或刪除用於事件之自訂資源的欄位，則相對應的事件將會自動取消發佈。請參閱[取消發佈交易式事件](../../channels/using/publishing-transactional-event.md#unpublishing-an-event)。
