---
title: 退回至寄件者
description: 瞭解如何收到錯誤地址的通知，並將其排除在未來的通訊之外。
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

支援與Direct Mail提供者交換包含Return to Sender資訊的平面檔案。 如此一來，對應的郵寄地址便可從未來的通訊中排除。 這也允許您收到地址錯誤的通知，並透過其他管道與客戶互動，或鼓勵他們更新郵寄地址。

例如，連絡人已移至新位置，但未提供您新的郵寄地址。 提供者會擷取錯誤位址清單，並將此資訊傳送至Adobe Campaign，由後者自動封鎖錯誤位址。

為了讓此功能運作，直接郵件預設傳遞範本在內容中包含傳遞記錄ID。 因此，Adobe Campaign將能夠將設定檔和傳送資料與提供者傳回的資訊同步。

![](assets/direct_mail_return_sender_1.png)

**[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**&#x200B;下有匯入範本。 複製此範本以建立您自己的範本。 有關使用匯入範本的詳細資訊，請參閱[使用匯入範本](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)。

![](assets/direct_mail_return_sender_2.png)

匯入完成後，Adobe Campaign會自動執行下列動作：

* 在設定檔層級將錯誤地址新增到封鎖清單
* 傳遞主要指標(KPI)已更新
* 傳送記錄已更新
