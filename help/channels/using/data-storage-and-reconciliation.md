---
title: 資料儲存與協調
seo-title: 資料儲存與協調
description: 資料儲存與協調
seo-description: Adobe Campaign可讓您定義在使用者提交著陸頁面中輸入的資料後，如何管理該資料。
page-status-flag: 從未啓動
uuid: 5b222ea2-6628-457f-a618-bc0 e5 eb93 dd
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 登陸頁面
discoiquuid: 899c7152-f415-4df9-b4 b4-5ff3470 a4 e32
context-tags: LandingPage，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Data storage and reconciliation{#data-storage-and-reconciliation}

資料協調參數可讓您定義在著陸頁面上輸入的資料在使用者提交後是如何管理的。

若要這麼做：

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_parameters_4.png)

1. Select the **[!UICONTROL Reconciliation key]**: these database fields (for example: email, first name, last name) are used to determine whether the visitor has a profile that is already known in the Adobe Campaign database. 這可讓您根據定義的更新策略參數，更新或建立描述檔。
1. Define the **[!UICONTROL Form parameter mapping]**: this section allows you to map the landing page field parameters and those used in the reconciliation key.
1. Select the **[!UICONTROL Update strategy]**: if the reconciliation key recovers an existing database profile, you can choose for this profile to be updated with the data entered in the form or instead prevent this update.

