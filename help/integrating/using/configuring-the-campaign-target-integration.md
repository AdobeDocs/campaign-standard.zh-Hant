---
title: 設定 Campaign-Target 整合
description: 瞭解如何設定Adobe target整合，以開始在Adobe Campaign中使用動態內容。
page-status-flag: 從未激活
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 整合
content-type: 參考
topic-tags: 搭配促銷活動和目標運作
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 設定 Campaign-Target 整合{#configuring-the-campaign-target-integration}

Adobe Campaign與Adobe target之間的整合可讓您在傳遞中插入動態內容。

Adobe Campaign首先需要設定，才能使用與Adobe target的整合功能，且必須由功能管理員管理。

此過程需要以下元素：

* Adobe Experience cloud租用戶
* Adobe target租用戶
* 指定Adobe Target rawbox以建立與Adobe Campaign的連線

1. 從進階功能表，透過左上角的Adobe Campaign標誌，選取 **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**。
1. 若要設定Adobe Target的伺服器和租用戶選項，請依此填入下列欄位：

   * **[!UICONTROL TNT_TenantName]**:Adobe target租用戶的名稱。 此值與Adobe Target的名稱相對應 **[!UICONTROL Client]**。
   * **[!UICONTROL TNT_EdgeServer]**:用於整合的Adobe Target伺服器。 預設已提供此選項。 此值與Adobe Target相 **[!UICONTROL Server Domain]**&#x200B;對應，後跟 **/m2** 值。 例如： **tt.omtrdc.net/m2**。
   ![](assets/tar_options.png)

您的使用者現在可以使用Adobe Target，將動態影像新增至傳送中。
