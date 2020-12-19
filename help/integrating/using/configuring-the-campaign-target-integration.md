---
solution: Campaign Standard
product: campaign
title: 設定 Campaign-Target 整合
description: 瞭解如何設定Adobe Target整合，以開始在Adobe Campaign中使用動態內容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 4%

---


# 設定 Campaign-Target 整合{#configuring-the-campaign-target-integration}

Adobe Campaign與Adobe Target之間的整合可讓您在傳遞中插入動態內容。

Adobe Campaign首先需要設定，才能使用與Adobe Target的整合功能，且必須由功能管理員管理。

此過程需要以下元素：

* Adobe Experience Cloud租用戶
* Adobe Target租用戶
* 指定Adobe Target rawbox以建立與Adobe Campaign的連線

1. 從進階功能表，透過左上角的Adobe Campaign標誌，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。
1. 若要設定Adobe Target的伺服器和租用戶選項，請依此填入下列欄位：

   * **[!UICONTROL TNT_TenantName]**:Adobe Target租用戶的名稱。此值與Adobe Target **[!UICONTROL Client]**&#x200B;的名稱相對應。
   * **[!UICONTROL TNT_EdgeServer]**:用於整合的Adobe Target伺服器。預設已提供此選項。 此值與Adobe Target **[!UICONTROL Server Domain]**&#x200B;對應，後面接著&#x200B;**/m2**&#x200B;值。 例如：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

您的使用者現在可以使用Adobe Target，將動態影像新增至傳送中。
