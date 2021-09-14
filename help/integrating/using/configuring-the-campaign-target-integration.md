---
title: 設定 Campaign-Target 整合
description: 了解如何設定Adobe Target整合，以開始使用Adobe Campaign中的動態內容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 4%

---

# 設定 Campaign-Target 整合{#configuring-the-campaign-target-integration}

Adobe Campaign與Adobe Target的整合可讓您在傳遞中插入動態內容。

Adobe Campaign首先需要設定，才能使用與Adobe Target的整合功能，且必須由功能管理員管理。

此過程需要以下元素：

* Adobe Experience Cloud租用戶
* Adobe Target租用戶
* 指定用來建立與Adobe Campaign連線的Adobe Target rawbox

1. 從進階功能表中，透過左上角的Adobe Campaign標誌，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。
1. 若要設定Adobe Target的伺服器和租用戶選項，請據此填入下列欄位：

   * **[!UICONTROL TNT_TenantName]**:Adobe Target租用戶的名稱。此值與Adobe Target **[!UICONTROL Client]**&#x200B;的名稱對應。
   * **[!UICONTROL TNT_EdgeServer]**:用於整合的Adobe Target伺服器。預設已提供此選項。 此值對應於Adobe Target **[!UICONTROL Server Domain]**，後跟&#x200B;**/m2**&#x200B;值。 例如：**tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

您的使用者現在可以透過Adobe Target在傳遞中新增動態影像。
