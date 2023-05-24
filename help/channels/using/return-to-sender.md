---
title: 退回至寄件者
description: 瞭解如何收到錯誤地址的通知並將其排除在將來的通信之外。
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# 退回至寄件者{#return-to-sender}

支援與包含「返回至發件人」資訊的Direct Mail提供商的平面檔案交換。 這允許將相應的郵政地址排除在未來通信之外。 這還允許您收到錯誤地址的通知，並通過其他渠道與客戶接洽，或鼓勵客戶更新其郵政地址。

例如，聯繫人已移至新地點，但未向您提供新的郵政地址。 提供程式檢索錯誤地址清單，並將此資訊發送給Adobe Campaign，而後者會自動拒絕錯誤地址。

為了使此功能正常工作，直郵預設遞送模板在內容中包括遞送日誌ID。 因此，Adobe Campaign將能夠將配置檔案和交付資料與提供商返回的資訊同步。

![](assets/direct_mail_return_sender_1.png)

導入模板可在 **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**。 複製此模板以建立您自己的模板。 有關使用導入模板的詳細資訊，請參閱 [使用導入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)。

![](assets/direct_mail_return_sender_2.png)

導入完成後，Adobe Campaign自動執行以下操作：

* 在配置檔案級別將不正確的地址添加到denylist
* 已更新交貨主要指標(KPI)
* 已更新交貨日誌
