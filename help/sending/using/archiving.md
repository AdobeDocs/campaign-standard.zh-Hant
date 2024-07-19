---
title: 在Adobe Campaign Standard中封存訊息
description: 瞭解如何使用密件副本電子郵件地址，透過Adobe Campaign Standard封存電子郵件。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 5%

---

# 使用電子郵件密件副本進行歸檔{#archiving-emails}

您可以設定Adobe Campaign以保留透過電子郵件密件副本從您的平台傳送的電子郵件副本。

特別是，如果您的組織需要封存所有外寄電子郵件訊息以符合法規，您可以啟用此功能。 這可讓您將對應傳送之訊息的完全隱藏復本傳送至您必須指定的密件副本電子郵件地址（傳送收件者不可見）。

啟用後，您必須從電子郵件傳遞範本中的&#x200B;**[!UICONTROL Archive emails]**&#x200B;選項啟用電子郵件密件副本。

>[!NOTE]
>
>Adobe Campaign本身不會管理封存的檔案。 它可讓您選擇的訊息傳送至專用地址，您可在其中使用外部系統處理和封存訊息。

## Recommendations和限制 {#recommendations-and-limitations}

* 此功能是選取性的。請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。
* 您必須將您選擇的密件副本位址提供給會為您設定該位址的Adobe團隊。
* 您只能使用一個密件副本電子郵件地址。
* 只考慮已成功傳送的電子郵件。 跳出則否。
* 基於隱私權理由，密件副本電子郵件必須由能夠安全儲存個人識別資訊(PII)的封存系統處理。
* 建立新的傳遞範本時，即使已購買選項，預設也不會啟用電子郵件密件副本。 您必須在每個要使用的傳遞範本中手動啟用。

>[!NOTE]
>
>目前，使用簡單SMTP轉送的舊版封存模組仍會傳送封存電子郵件。

## 啟用電子郵件封存 {#activating-email-archiving}

啟用後，會透過專用選項在[電子郵件範本](../../start/using/marketing-activity-templates.md)中啟用電子郵件密件副本：

1. 移至&#x200B;**資源** > **範本** > **傳遞範本**。
1. 複製現成的&#x200B;**[!UICONTROL Send via email]**&#x200B;範本。
1. 選取複製的範本。
1. 按一下&#x200B;**[!UICONTROL Edit properties]**&#x200B;按鈕以編輯範本的屬性。
1. 展開&#x200B;**[!UICONTROL Send]**&#x200B;區段。
1. 核取&#x200B;**[!UICONTROL Archive emails]**&#x200B;方塊，以根據此範本保留每個傳遞的所有已傳送訊息的復本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果傳送至密件副本位址的電子郵件已開啟且被點進，則會在傳送分析的&#x200B;**[!UICONTROL Total opens]**&#x200B;和&#x200B;**[!UICONTROL Clicks]**&#x200B;中考慮這一點，這可能會造成一些計算錯誤。
