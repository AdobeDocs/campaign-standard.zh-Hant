---
title: 設定 Campaign-Target 整合
description: 瞭解如何設定Adobe Target整合，以開始在Adobe Campaign中使用動態內容。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
TQID: https://experienceleague.adobe.com/trfuEp6pEd2jFADsK6NMw6tx8ASi86ZFur56AjwnpWQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 5%

---

# 設定 Campaign-Target 整合{#configuring-the-campaign-target-integration}

Adobe Campaign與Adobe Target之間的整合可讓您在傳送中插入動態內容。

若要與Adobe Target使用整合功能，首先必須在Adobe Campaign中進行設定，且必須由功能管理員管理。

此程式需要下列元素：

* Adobe Experience Cloud租使用者
* Adobe Target租使用者
* 已指定Adobe Target rawbox來與Adobe Campaign建立連線

1. 從進階功能表，透過左上角的Adobe Campaign標誌，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**。
1. 若要設定Adobe Target的伺服器和租使用者選項，請填入下列欄位：

   * **[!UICONTROL TNT_TenantName]**： Adobe Target租使用者的名稱。 此值對應至Adobe Target **[!UICONTROL Client]**&#x200B;的名稱。
   * **[!UICONTROL TNT_EdgeServer]**：用於整合的Adobe Target伺服器。 此選項已預設提供。 此值對應至Adobe Target **[!UICONTROL Server Domain]**，後面接著&#x200B;**/m2**&#x200B;值。 例如： **tt.omtrdc.net/m2**。

   ![](assets/tar_options.png)

您的使用者現在可以使用Adobe Target在傳送中新增動態影像。
