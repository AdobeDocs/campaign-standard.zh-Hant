---
title: 返回至寄件者
description: 瞭解如何收到錯誤地址的通知，並排除它，以免日後通訊。
page-status-flag: never-activated
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 2%

---


# 返回至寄件者{#return-to-sender}

支援與直接郵件提供者交換包含「傳回給寄件者」資訊的平面檔案。 這允許將相應的郵遞區號排除在將來的通訊之外。 此外，您還可以收到錯誤地址的通知，並透過其他管道與客戶互動，或鼓勵他更新其郵遞區號。

例如，聯繫人已移至新位置，但未提供您新的郵遞區號。 提供者會擷取錯誤位址的清單，並傳送此資訊給Adobe Campaign,Adobe Campaign會自動將錯誤位址新增至區塊清單。

為了使此功能發揮作用，直接郵件預設傳送模板在內容中包括傳送日誌ID。 因此，Adobe Campaign將能夠將描述檔和傳送資料與提供者傳回的資訊同步。

![](assets/direct_mail_return_sender_1.png)

導入模板位於下 **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**。 複製此範本以建立您自己的範本。 有關使用導入模板的詳細資訊，請參閱使 [用導入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)。

![](assets/direct_mail_return_sender_2.png)

匯入完成後，Adobe Campaign會自動執行下列動作：

* 配置檔案級別的塊清單中添加的地址不正確
* 傳送主要指標(KPI)已更新
* 傳送記錄檔已更新

