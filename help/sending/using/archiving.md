---
solution: Campaign Standard
product: campaign
title: 在Adobe Campaign Standard歸檔郵件
description: 瞭解如何使用密件副本電子郵件地址與Adobe Campaign Standard封存電子郵件。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: 效能監控
role: 商務從業人員
level: 中階程度
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
translation-type: tm+mt
source-git-commit: f7d77f524a6c141066056e53fc8616f35189fc39
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 6%

---

# 使用電子郵件密件副本進行歸檔{#archiving-emails}

您可以設定Adobe Campaign，將透過電子郵件密件副本從您的平台傳送的電子郵件副本保留下來。

尤其是，如果您的組織需要封存所有傳出電子郵件訊息以符合法規，您可以啟用此功能。 它可讓您將對應已傳送訊息的完全隱藏副本傳送至您必須指定的密件副本電子郵件地址（傳送收件者不可見）。

啟用後，您必須從電子郵件傳送範本的&#x200B;**[!UICONTROL Archive emails]**&#x200B;選項啟用電子郵件密件副本。

>[!NOTE]
>
>Adobe Campaign本身不管理歸檔檔案。 它確實可讓您將您選擇的訊息傳送至專用位址，以便使用外部系統處理及封存。

## Recommendations和限制{#recommendations-and-limitations}

* 此功能是選取性的。請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。
* 您選擇的密件副本地址必須提供給將為您配置的Adobe團隊。
* 您只能使用一個密件副本電子郵件地址。
* 只會將成功傳送的電子郵件納入考量。 彈回數不是。
* 出於隱私原因，密件副本電子郵件必須由能夠安全地儲存個人識別資訊(PII)的歸檔系統處理。
* 建立新的傳送範本時，即使已購買選項，依預設不會啟用電子郵件密件副本。 您必須在每個要使用的傳送範本中手動啟用它。

>[!NOTE]
>
>目前，歸檔電子郵件仍由使用簡單SMTP中繼的舊式歸檔模組發送。

## 激活電子郵件歸檔{#activating-email-archiving}

啟用後，電子郵件密件副本會透過專用選項在[電子郵件範本](../../start/using/marketing-activity-templates.md)中啟動：

1. 前往「**資源** > **範本** > **傳送範本**」。
1. 複製現成可用的&#x200B;**[!UICONTROL Send via email]**&#x200B;範本。
1. 選擇複製的模板。
1. 按一下&#x200B;**[!UICONTROL Edit properties]**&#x200B;按鈕以編輯範本的屬性。
1. 展開&#x200B;**[!UICONTROL Send]**&#x200B;部分。
1. 選中&#x200B;**[!UICONTROL Archive emails]**&#x200B;框，以保存基於此模板的每個傳送的所有已發送消息副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果已開啟並點進傳送至密件副本位址的電子郵件，則會在傳送分析的&#x200B;**[!UICONTROL Total opens]**&#x200B;和&#x200B;**[!UICONTROL Clicks]**&#x200B;中考慮此問題，這可能會造成一些誤算。
