---
title: 設定 Campaign-Target 整合
description: 瞭解如何設定Adobe Target整合，以開始在Adobe Campaign中使用動態內容。
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

Adobe Campaign與Adobe Target之間的整合可讓您在傳送中插入動態內容。

若要與Adobe Target使用整合功能，首先必須在Adobe Campaign中進行設定，且必須由功能管理員管理。

此程式需要下列元素：

* Adobe Experience Cloud租使用者
* Adobe Target租使用者
* 已指定Adobe Target rawbox來與Adobe Campaign建立連線

1. 從進階功能表，透過左上方的Adobe Campaign標誌選取 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. 若要設定Adobe Target的伺服器和租使用者選項，請填入下列欄位：

   * **[!UICONTROL TNT_TenantName]**：Adobe Target租使用者的名稱。 此值對應至Adobe Target的名稱 **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**：用於整合的Adobe Target伺服器。 此選項已預設提供。 此值對應至Adobe Target **[!UICONTROL Server Domain]**，後面接著 **/m2** 值。 例如： **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

您的使用者現在可以使用Adobe Target在傳送中新增動態影像。
