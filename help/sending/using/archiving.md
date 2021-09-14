---
title: 在Adobe Campaign Standard中封存訊息
description: 了解如何使用BCC電子郵件地址，使用Adobe Campaign Standard封存電子郵件。
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

您可以設定Adobe Campaign，以保留透過電子郵件密件副本從您的平台傳送的電子郵件副本。

尤其是，如果貴組織需要歸檔所有出站電子郵件以符合法規要求，您可以啟用此功能。 它可讓您將對應已傳送訊息的完全隱藏副本傳送至您必須指定的密件副本電子郵件地址（傳遞收件者不會看到）。

啟用後，您需要從電子郵件傳送範本的&#x200B;**[!UICONTROL Archive emails]**&#x200B;選項啟用電子郵件密件副本。

>[!NOTE]
>
>Adobe Campaign本身不會管理封存的檔案。 它確實可讓您將您選擇的訊息傳送至專用地址，以便使用外部系統處理和封存訊息。

## Recommendations和限制 {#recommendations-and-limitations}

* 此功能是選取性的。請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。
* 您選擇的密件副本地址必須提供給Adobe團隊，由團隊為您進行配置。
* 您只能使用一個密件副本電子郵件地址。
* 系統只會考慮成功傳送的電子郵件。 彈回數不是。
* 基於隱私理由，BCC電子郵件必須由能夠安全地儲存個人識別資訊(PII)的封存系統處理。
* 建立新的傳送範本時，即使已購買選項，預設也不會啟用電子郵件密件副本。 您必須在每個要使用的傳送範本中手動啟用。

>[!NOTE]
>
>目前封存的電子郵件仍由舊版封存模組傳送，舊版封存模組使用簡單的SMTP中繼。

## 啟用電子郵件封存 {#activating-email-archiving}

啟用後，電子郵件密件副本會透過專用選項在[電子郵件範本](../../start/using/marketing-activity-templates.md)中啟動：

1. 前往「**資源** > **範本** > **傳送範本**」。
1. 複製現成可用的&#x200B;**[!UICONTROL Send via email]**&#x200B;範本。
1. 選取重複的範本。
1. 按一下&#x200B;**[!UICONTROL Edit properties]**&#x200B;按鈕以編輯範本的屬性。
1. 展開&#x200B;**[!UICONTROL Send]**&#x200B;區段。
1. 核取&#x200B;**[!UICONTROL Archive emails]**&#x200B;方塊，以保留根據此範本每次傳送之所有已傳送訊息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果開啟並點進傳送至BCC位址的電子郵件，在傳送分析的&#x200B;**[!UICONTROL Total opens]**&#x200B;和&#x200B;**[!UICONTROL Clicks]**&#x200B;中會考量這一點，這可能會造成某些錯誤計算。
