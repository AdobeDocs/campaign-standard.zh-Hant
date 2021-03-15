---
solution: Campaign Standard
product: campaign
title: 設定 Campaign-Target 整合
description: 瞭解如何設定Adobe Target整合，以開始使用Adobe Campaign的動態內容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: 觸發器
role: 資料架構師
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# 設定 Campaign-Target 整合{#configuring-the-campaign-target-integration}

Adobe Campaign與Adobe Target的整合可讓您將動態內容插入您的傳送。

在Adobe Campaign，首先需要配置才能使用與Adobe Target的整合功能，必須由職能管理員管理。

此過程需要以下元素：

* Adobe Experience Cloud租客
* Adobe Target租客
* 指定與Adobe Campaign建立聯繫的Adobe Targetrawbox

1. 從進階功能表，透過左上角的Adobe Campaign標誌，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。
1. 若要設定Adobe Target的伺服器和租用戶選項，請依此填入下列欄位：

   * **[!UICONTROL TNT_TenantName]**:Adobe Target租戶的名字。此值與Adobe Target的名稱&#x200B;**[!UICONTROL Client]**&#x200B;相對應。
   * **[!UICONTROL TNT_EdgeServer]**:Adobe Target伺服器用於整合。預設已提供此選項。 此值對應於Adobe Target **[!UICONTROL Server Domain]**，後面跟著&#x200B;**/m2**&#x200B;值。 例如：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

您的使用者現在可以在Adobe Target的發佈中新增動態影像。
