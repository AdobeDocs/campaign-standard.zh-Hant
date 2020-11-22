---
solution: Campaign Standard
product: campaign
title: 在Adobe Campaign Standard中封存訊息
description: 瞭解如何使用密件副本電子郵件地址使用Adobe Campaign Standard封存電子郵件。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 5%

---


# 使用電子郵件密件副本進行歸檔{#archiving-emails}

您可以設定Adobe Campaign，以保留透過電子郵件密件副本從您的平台傳送的電子郵件副本。

尤其是，如果您的組織需要封存所有傳出電子郵件訊息以符合法規，您可以啟用此功能。 它可讓您將對應已傳送訊息的完全隱藏副本傳送至您必須指定的密件副本電子郵件地址（傳送收件者不可見）。

啟用後，您必須從電子郵件傳送範本中的選 **[!UICONTROL Archive emails]** 項啟用電子郵件密件副本。

>[!NOTE]
>
>Adobe Campaign本身不會管理封存的檔案。 它確實可讓您將您選擇的訊息傳送至專用位址，以便使用外部系統處理及封存。

## 建議與限制 {#recommendations-and-limitations}

* 此功能是選取性的。請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。
* 您選擇的密件副本位址必須提供給將為您設定的Adobe團隊。
* 您只能使用一個密件副本電子郵件地址。
* 只會將成功傳送的電子郵件納入考量。 彈回數不是。
* 出於隱私原因，密件副本電子郵件必須由能夠安全地儲存個人識別資訊(PII)的歸檔系統處理。
* 建立新的傳送範本時，即使已購買選項，依預設不會啟用電子郵件密件副本。 您必須在每個要使用的傳送範本中手動啟用它。

>[!NOTE]
>
>目前，已封存的電子郵件無法與Adobe Campaign Enhanced MTA一起傳送，即使您已升級至Enhanced MTA亦然。

## 啟動電子郵件封存 {#activating-email-archiving}

啟用後，電子郵件密件副本會透過專 [用選項](../../start/using/marketing-activity-templates.md)，在電子郵件範本中啟動：

1. 前往「 **資源** >范 **本** > **傳送範本**」。
1. 複製現成可用的范 **[!UICONTROL Send via email]** 本。
1. 選擇複製的模板。
1. Click the **[!UICONTROL Edit properties]** button to edit the template&#39;s properties.
1. 展開該 **[!UICONTROL Send]** 部分。
1. 核取方 **[!UICONTROL Archive emails]** 塊，以根據此範本保留每個傳送之所有已傳送訊息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果開啟並點進傳送至密件副本位址的電子郵件，則會在傳送分析中考慮 **[!UICONTROL Total opens]** 這 **[!UICONTROL Clicks]** 一點，這可能會造成一些誤算。