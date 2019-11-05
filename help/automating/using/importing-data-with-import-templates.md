---
title: 使用匯入範本匯入資料
description: 瞭解如何收集資料以饋送您的Campaign資料庫。
page-status-flag: 從未激活
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 參考
topic-tags: 導入和導出資料
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 使用匯入範本匯入資料{#importing-data-with-import-templates}

匯入資料可讓您收集資料，以饋送您的促銷活動資料庫。

或者， [Adobe Campaign](../../automating/using/discovering-workflows.md)提供簡化的匯入功能，讓使用者管理管理員定義的特定匯入類型。

其工作原理是：管理 **員定義** ，並管理導入模板(請參閱 [定義導入模板](../../automating/using/defining-import-templates.md))。 然後，這些匯入範本會提供給「 &gt;」功能表下具有簡化檢視 **[!UICONTROL Profiles & audiences]** 的使 **[!UICONTROL Imports]** 用者。

因此，這些使用者只需要選擇要執行的匯入類型，並上傳包含要匯入資料的檔案。 管理員定義的工作流將對用戶透明地執行，用戶在導入完成後可以訪問導入結果的詳細資訊。

>[!NOTE]
>
>具有和角色的用戶可以管理導入數 **[!UICONTROL GENERIC IMPORT (import)]** 據 **[!UICONTROL WORKFLOW (workflow)]** 函式。 有關角色的詳細資訊，請參閱[本節](../../administration/using/list-of-roles.md)。

可以根據導入的執行模板、其執行日期和執行狀態來過濾導入。

1. 在匯入概述中，按一下 **[!UICONTROL Create]** 按鈕。 嚮導開啟。
1. 選擇要執行的導入類型。 導入類型與可用的導入模板對應。
1. 如有必要，請將連結至範本的範例檔案下載至您的電腦，以檢視要匯入的檔案中預期的資料類型。
1. 下載包含要在精靈中匯入之資料的檔案。
1. 開始匯入。 嚮導將關閉並帶您返回使用模板執行的導入清單。
1. 重新整理您的頁面，並選取您剛執行的匯入，以檢視執行詳細資料。

   ![](assets/simplified_import1.png)

現在可取得匯入執行的詳細資訊。 已匯入的檔案以及包含已拒絕資料（未匯入的資料）的檔案都可下載至您的電腦。
