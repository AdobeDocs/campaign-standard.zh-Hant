---
title: 返回傳送者
seo-title: 返回傳送者
description: 返回傳送者
seo-description: 瞭解如何通知不正確的地址並排除未來的通訊。
page-status-flag: 從未啓動
uuid: 11981c2f-0b7f-4166-9da-ec6 a6 b4 b5 d5367
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 直接郵件
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610 edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Return to sender{#return-to-sender}

支援與整合傳送者資訊的直效郵件提供者進行簡單的檔案交換。這可讓對應的郵寄地址排除在未來的通訊之外。這也允許您收到不正確的通知，並透過其他管道與客戶互動，或鼓勵他更新郵寄地址。

例如，聯絡已移至新地點，但未提供您新的郵寄地址。提供者會擷取錯誤位址清單，並將此資訊傳送至Adobe Campaign，自動列入錯誤的地址。

為讓此功能運作，直接郵件預設傳送範本包含傳送記錄檔ID。因此，Adobe Campaign將能夠與提供者傳回的資訊同步設定檔和傳送資料。

![](assets/direct_mail_return_sender_1.png)

An import template is available under **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. 複製此範本以建立自己的範本。For more on using import templates, refer to [Using import templates](../../automating/using/defining-import-templates.md).

![](assets/direct_mail_return_sender_2.png)

在匯入完成後，Adobe Campaign會自動執行下列動作：

* 描述檔層級會列入黑名單錯誤的地址
* 傳送主要指標(KPI)已更新
* 傳送記錄檔已更新

