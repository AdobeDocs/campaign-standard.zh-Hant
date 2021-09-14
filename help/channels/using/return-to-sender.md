---
title: 退回至寄件者
description: 了解如何收到錯誤地址的通知，並將其排除在未來通訊之外。
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# 退回至寄件者{#return-to-sender}

支援與包含「返回至寄件者」資訊的直接郵件提供者進行一般檔案交換。 這可將對應的郵遞區號排除在未來通訊之外。 這也可讓您收到錯誤地址的通知，並透過其他管道與客戶互動，或鼓勵客戶更新其郵遞區號。

例如，某個連絡人已移至新位置，但並未提供您新的郵遞區號。 提供者會擷取錯誤位址的清單，並將此資訊傳送至Adobe Campaign，以自動封鎖錯誤位址。

為了讓此功能發揮作用，直接郵件預設傳送範本在內容中包含傳送記錄檔ID。 因此，Adobe Campaign將能將設定檔和傳送資料與提供者傳回的資訊同步。

![](assets/direct_mail_return_sender_1.png)

匯入範本位於&#x200B;**[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**&#x200B;下。 複製此範本以建立您自己的範本。 有關使用導入模板的詳細資訊，請參閱[使用導入模板](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)。

![](assets/direct_mail_return_sender_2.png)

匯入完成時，Adobe Campaign會自動執行下列動作：

* 設定檔層級的封鎖清單新增了不正確的位址
* 更新傳遞主要指標(KPI)
* 傳送記錄檔已更新
