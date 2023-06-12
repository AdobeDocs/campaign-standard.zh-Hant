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

您可以設定Adobe Campaign以保留透過電子郵件密件副本從您的平台傳送的電子郵件復本。

特別是，如果您的組織需要封存所有傳出電子郵件訊息以符合規定，您可以啟用此功能。 它可讓您將對應已傳送訊息的完全隱藏復本傳送至您必須指定的密件副本電子郵件地址（傳送收件者無法看見）。

啟用後，您需要從以下位置啟用電子郵件密件副本： **[!UICONTROL Archive emails]** 電子郵件傳遞範本中的選項。

>[!NOTE]
>
>Adobe Campaign本身不會管理封存的檔案。 它可讓您選擇將訊息傳送至專用地址，您可使用外部系統從該地址進行處理和封存。

## Recommendations和限制 {#recommendations-and-limitations}

* 此功能是選取性的。請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。
* 您必須將您選擇的密件副本地址提供給將為您設定該地址的Adobe團隊。
* 您只能使用一個密件副本電子郵件地址。
* 只考慮成功傳送的電子郵件。 跳出則否。
* 基於隱私權考量，密件副本電子郵件必須由能夠安全儲存個人識別資訊(PII)的封存系統處理。
* 建立新傳遞範本時，預設不會啟用電子郵件密件副本，即使已購買選項亦然。 您必須在每個要使用的傳遞範本中手動啟用。

>[!NOTE]
>
>目前，封存的電子郵件仍會由使用簡單SMTP轉送的舊版封存模組傳送。

## 啟用電子郵件封存 {#activating-email-archiving}

啟用後，電子郵件密件副本會在以下位置啟動： [電子郵件範本](../../start/using/marketing-activity-templates.md)，透過專用選項：

1. 前往 **資源** > **範本** > **傳遞範本**.
1. 複製現成可用的專案 **[!UICONTROL Send via email]** 範本。
1. 選取複製的範本。
1. 按一下 **[!UICONTROL Edit properties]** 按鈕以編輯範本的屬性。
1. 展開 **[!UICONTROL Send]** 區段。
1. 檢查 **[!UICONTROL Archive emails]** 方塊以根據此範本保留每個傳遞的所有已傳送訊息的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果傳送至密件副本地址的電子郵件被開啟並按過，這將會在 **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** 傳送分析，這可能會導致某些計算錯誤。
