---
title: 在Adobe Campaign Standard存檔郵件
description: 瞭解如何使用BCC電子郵件地址與Adobe Campaign Standard存檔電子郵件。
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

您可以配置Adobe Campaign以保留通過電子郵件密件抄送從您的平台發送的電子郵件副本。

特別是，如果您的組織需要存檔所有出站電子郵件以實現法規遵從性，則可以啟用此功能。 它允許您向必須指定的密件抄送電子郵件地址（傳遞收件人不可見）發送相應已發送郵件的確切隱藏副本。

啟用後，您需要從 **[!UICONTROL Archive emails]** 的子菜單。

>[!NOTE]
>
>Adobe Campaign本身不管理存檔檔案。 它確實使您能夠將您選擇的消息發送到專用地址，在該地址可以使用外部系統進行處理和存檔。

## Recommendations和限制 {#recommendations-and-limitations}

* 此功能是選取性的。請檢查您的授權合約，並聯絡您的帳戶管理員以啟用它。
* 必須將您選擇的BCC地址提供給將為您配置該地址的Adobe團隊。
* 您只能使用一個密件抄送電子郵件地址。
* 只考慮成功發送的電子郵件。 彈射不是。
* 出於隱私原因，BCC電子郵件必須由能夠安全儲存個人身份資訊(PII)的存檔系統處理。
* 建立新交貨模板時，預設情況下不啟用「電子郵件密件抄送」(Email BCC)，即使已購買該選項。 您必須在要使用的每個交貨模板中手動啟用它。

>[!NOTE]
>
>當前存檔的電子郵件仍由舊式存檔模組發送，該模組使用簡單的SMTP中繼。

## 激活電子郵件存檔 {#activating-email-archiving}

啟用後，將在 [電子郵件模板](../../start/using/marketing-activity-templates.md)，通過專用選項：

1. 轉到 **資源** > **模板** > **交貨模板**。
1. 複製現成的 **[!UICONTROL Send via email]** 的下界。
1. 選擇複製的模板。
1. 按一下 **[!UICONTROL Edit properties]** 按鈕，將選定控制項在Tab鍵次序中下移一個位置。
1. 展開 **[!UICONTROL Send]** 的子菜單。
1. 檢查 **[!UICONTROL Archive emails]** 框，以保存基於此模板的每個傳遞的所有已發送郵件的副本。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>如果開啟並按一下發送到密件抄送地址的電子郵件，則在 **[!UICONTROL Total opens]** 和 **[!UICONTROL Clicks]** 從發送分析中得出，這可能會導致一些錯誤計算。
