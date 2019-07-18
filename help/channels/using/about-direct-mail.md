---
title: 關於直接郵件
seo-title: 關於直接郵件
description: 關於直接郵件
seo-description: 瞭解Adobe Campaign中直效郵件頻道的主要特點。
page-status-flag: 從未啓動
uuid: 24add992-2ee-4b73-81c9-cda3 e921 ab16
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 直接郵件
discoiquuid: e1fff39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery，DirectMailContent，back；Delivery Creation，精靈
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About direct mail{#about-direct-mail}

直接郵件是離線頻道，可讓您個人化並產生直效郵件提供者所需的檔案。它可讓您在客戶歷程中混合線上和離線通道。

>[!NOTE]
>
>此功能為選擇性功能。請檢查您的授權合約。The **[!UICONTROL Export]** role is required to use direct mail. 請聯絡您的管理員。

線上頻道可讓您建立訊息(電子郵件、簡訊、行動應用程式傳送等)並直接從Adobe Campaign傳送給您的觀眾。離線渠道則不同。當您準備直效郵件傳送時，Adobe Campaign會產生一個檔案，其中包含所有目標設定檔和所選的聯絡資訊(例如，郵寄地址)。然後，您就可以將此檔案傳送給您的直接郵件提供者，負責處理實際傳送的內容。

下節說明如何建立並產生單鍵直接郵件傳送。您也可以在工作流程中加入直效郵件活動，協調結合線上和線下通道的宣傳活動。For more on this, refer to the [Workflows](../../automating/using/workflow-data-and-processes.md) guide.

Adobe Campaign中的使用者程序如下：

1. 建立傳送
1. 選擇對象
1. 定義內容
1. 設定連絡人日期
1. 產生檔案

## Recommendations {#recommendations}

### Direct mail providers {#direct-mail-providers}

首先，您需要聯絡直接郵件供應商並收集他們的建議。識別擷取檔案中需要包含的描述檔資訊，以便將通訊個人化並傳送給觀眾。例如，第一個和姓氏、郵寄地址、促銷代碼等。These fields are the ones that you will add in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) tab of the direct mail's content.

Make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. 如果啓用此選項，描述檔將會新增至目標。It is not, it will excluded by a typology rule during the preparation phase (see [Creating the direct mail](../../channels/using/creating-the-direct-mail.md)). 在設定檔匯入期間，請勿忘記更新此欄位。

![](assets/direct_mail_22.png)

### Postal addresses {#postal-addresses}

When you add the fields to include in the extraction file, the postal address fields are available in the **[!UICONTROL Location]** node.

Adobe Campaign提供一組預先定義的計算欄位，遵循最常見的郵遞區號標準化。The fields are available in the **[!UICONTROL Postal address]** node.

An address can contain up to six lines by default: the first calculated field ( **[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

