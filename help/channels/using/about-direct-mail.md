---
title: 關於直接郵件
description: 瞭解Adobe Campaign中直效郵件通道的主要特性。
page-status-flag: never-activated
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# 關於直接郵件{#about-direct-mail}

直效郵件是一種離線渠道，可讓您個人化並產生直效郵件供應商所需的檔案。 它可讓您在客戶歷程中混合使用線上和線下通道。

>[!NOTE]
>
>此功能為選擇性。 請檢查您的授權合約。 使用 **[!UICONTROL Export]** 直接郵件時需要角色。 請聯絡您的管理員。

線上通道可讓您建立訊息（電子郵件、簡訊、行動應用程式傳送等）並直接從Adobe Campaign傳送給您的觀眾。 離線通道則不同。 當您準備直接郵寄時，Adobe Campaign會產生一個檔案，其中包含所有目標設定檔和選取的聯絡資訊（例如郵遞區號）。 然後，您就可以將此檔案傳送給直接郵件提供者，由他們負責實際傳送。

下節將說明如何建立並產生單次直接郵件傳送。 您也可以將直接郵件活動納入工作流程，以協調結合線上和線下通道的宣傳活動。 如需詳細資訊，請參閱「工作 [流程](../../automating/using/workflow-data-and-processes.md) 」指南。

Adobe Campaign中的使用者程式如下：

1. 建立傳送
1. 選擇對象
1. 定義內容
1. 設定連絡人日期
1. 生成檔案

## 建議 {#recommendations}

### 直接郵件提供者 {#direct-mail-providers}

首先，您需要聯絡直效郵件供應商並收集其建議。 識別摘取檔案中需要包含哪些描述檔資訊，以便個人化通訊並傳送給觀眾。 例如，名字和姓氏、郵遞區號、促銷代碼等。 這些欄位是您要在直接郵件內容的「定 [義抽取](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) 」頁籤中添加的欄位。

請確定您已勾選設定 **[!UICONTROL Address specified]** 檔資訊中的方塊。 如果此選項已啟用，則會將描述檔新增至目標。 它不是，在準備階段會被排除在類型規則中(請參 [閱建立直效郵件](../../channels/using/creating-the-direct-mail.md))。 在匯入描述檔時，請勿忘記更新此欄位。

![](assets/direct_mail_22.png)

### 郵遞區號 {#postal-addresses}

添加要包含在抽取檔案中的欄位時，節點中將提供郵遞區 **[!UICONTROL Location]** 域。

Adobe Campaign提供一組預先定義的計算欄位，這些欄位會遵循最常見的郵遞區號標準化。 這些欄位在節點中可 **[!UICONTROL Postal address]** 用。

預設情況下，地址最多可包含6行：第一個計算欄位(**[!UICONTROL Line 1]** 包含名字和姓氏)、下一行包含郵遞區號（路等），最後一行包含郵遞區號和城鎮。

![](assets/direct_mail_23.png)

