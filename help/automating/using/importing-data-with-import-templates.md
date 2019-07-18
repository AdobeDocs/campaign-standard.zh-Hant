---
title: 使用匯入範本匯入資料
seo-title: 使用匯入範本匯入資料
description: 使用匯入範本匯入資料
seo-description: 瞭解如何收集資料以饋送您的Campaign資料庫。
page-status-flag: 從未啓動
uuid: bfc03235-2032-448a-a9 ed-21ff2 a83 fa09
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 匯入-匯出資料
discoiquuid: fb511bb8-6be-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Importing data with import templates{#importing-data-with-import-templates}

匯入資料可讓您收集資料以饋送促銷活動的資料庫。

Alternatively to [Workflows](../../automating/using/discovering-workflows.md), Adobe Campaign offers a simplified import function that allows the user to manage certain types of import that were defined by an administrator.

The operating principle is as follows: an **administrator** defines and manages import templates (see [Defining import templates](../../automating/using/defining-import-templates.md)). These import templates are then made available to users with simplified views under the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** menu.

因此，這些使用者只需要選取要執行的匯入類型，並上傳檔案以匯入資料。管理員定義的工作流程會透明地執行，使用者可以在完成匯入後存取匯入結果的詳細資訊。

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. 有關角色的詳細資訊，請參閱[本節](../../administration/using/list-of-roles.md)。

可以根據執行的範本、執行日期及其執行狀態來篩選匯入。

1. From the imports overview, click the **[!UICONTROL Create]** button. 精靈隨即開啓。
1. 選擇您要執行的匯入類型。匯入類型對應至可用的匯入範本。
1. 如有必要，請將連結至範本的範例檔案下載至您的電腦，以檢視要匯入檔案中預期的資料類型。
1. 下載包含要在精靈中匯入之資料的檔案。
1. 開始匯入。精靈會關閉，並帶您返回使用範本所執行的匯入清單。
1. 重新整理您的頁面，然後選取剛才執行的匯入，以檢視執行詳細資料。

   ![](assets/simplified_import1.png)

現在提供匯入執行的詳細資訊。系統會將匯入的檔案以及包含已拒絕資料的檔案(未匯入資料)下載到您的電腦。
