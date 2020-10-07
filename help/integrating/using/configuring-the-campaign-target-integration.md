---
title: 設定 Campaign-Target 整合
description: 瞭解如何設定Adobe Target整合，以開始在Adobe Campaign中使用動態內容。
page-status-flag: never-activated
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 設定 Campaign-Target 整合{#configuring-the-campaign-target-integration}

Adobe Campaign與Adobe Target之間的整合可讓您在傳遞中插入動態內容。

Adobe Campaign首先需要設定，才能使用與Adobe Target的整合功能，且必須由功能管理員管理。

此過程需要以下元素：

* Adobe Experience Cloud租用戶
* Adobe Target租用戶
* 指定Adobe Target rawbox以建立與Adobe Campaign的連線

1. 從進階功能表，透過左上角的Adobe Campaign標誌，選取 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。
1. 若要設定Adobe Target的伺服器和租用戶選項，請依此填入下列欄位：

   * **[!UICONTROL TNT_TenantName]**:Adobe Target租用戶的名稱。 此值與Adobe Target的名稱相對應 **[!UICONTROL Client]**。
   * **[!UICONTROL TNT_EdgeServer]**:用於整合的Adobe Target伺服器。 預設已提供此選項。 此值與Adobe Target相 **[!UICONTROL Server Domain]**&#x200B;對應，後跟 **/m2** 值。 例如： **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

您的使用者現在可以使用Adobe Target，將動態影像新增至傳送中。
