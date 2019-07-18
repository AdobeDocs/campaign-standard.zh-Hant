---
title: 設定促銷活動-目標整合
seo-title: 設定促銷活動-目標整合
description: 設定促銷活動-目標整合
seo-description: 瞭解如何設定Adobe Target整合，開始在Adobe Campaign中使用動態內容。
page-status-flag: 從未啓動
uuid: 0df5701c-dc26-4c30-9af9-ef92815 d90 c
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與定位
discoiquuid: f7fb2084-dd6 f-4aa2-940f-e487136435
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring the Campaign-Target integration{#configuring-the-campaign-target-integration}

Adobe Campaign與Adobe Target之間的整合可讓您在傳遞中插入動態內容。

Adobe Campaign中首先需要使用設定，才能使用Adobe Target的整合功能，且必須由功能管理員管理。

此程序需要下列元素：

* Adobe Experience Cloud租用戶
* Adobe Target租用戶
* 指定要建立與Adobe Campaign連線的Adobe Target rawbox

1. From the advanced menu, via the Adobe Campaign logo in the top left corner, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. 若要設定Adobe Target的伺服器和租用戶選項，請依下列欄位填寫：

   * **[!UICONTROL TNT_TenantName]**：Adobe Target租用戶名稱。This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**：用於整合的Adobe Target伺服器。預設已提供此選項。This value corresponds to the Adobe Target **[!UICONTROL Server Domain]**, followed by the **/m2** value. For example: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

您的使用者現在可以使用Adobe Target在傳送中新增動態影像。
