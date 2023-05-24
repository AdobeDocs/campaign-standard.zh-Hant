---
title: 設定 Campaign-Target 整合
description: 瞭解如何配置Adobe Target整合以開始在Adobe Campaign使用動態內容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 4%

---

# 設定 Campaign-Target 整合{#configuring-the-campaign-target-integration}

Adobe Campaign和Adobe Target的整合使您可以在交付中插入動態內容。

Adobe Campaign首先需要配置才能使用與Adobe Target的整合功能，必須由職能管理員管理。

此過程需要以下元素：

* Adobe Experience Cloud租客
* Adobe Target租客
* 指定與Adobe Campaign建立聯繫的Adobe Target羅布克

1. 從高級菜單中，通過左上角的Adobe Campaign徽標，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。
1. 要為Adobe Target配置伺服器和租戶選項，請相應填寫以下欄位：

   * **[!UICONTROL TNT_TenantName]**:Adobe Target租戶的名字。 此值與Adobe Target **[!UICONTROL Client]**。
   * **[!UICONTROL TNT_EdgeServer]**:Adobe Target伺服器用於整合。 預設情況下已提供此選項。 此值與Adobe Target **[!UICONTROL Server Domain]**，後跟 **/m2** 值。 例如： **tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

您的用戶現在可以在與Adobe Target的交貨中添加動態映像。
