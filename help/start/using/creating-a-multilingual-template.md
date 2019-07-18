---
title: 建立多語言範本
seo-title: 建立多語言範本
description: 建立多語言範本
seo-description: 瞭解如何透過自動分段客戶的慣用語言，透過單次傳送定義及執行多語言電子郵件/簡訊傳送。報告每個傳送至語言和個別層級的效能。
page-status-flag: 從未啓動
uuid: 7a2cd5f7-c0 fc-4825-a770-a62816 c66 b3 f
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: 管理範本
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92 eb4518 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a multilingual template{#creating-a-multilingual-template}

多語言範本是管理多語言訊息的特定範本。

This kind of template is available for **Email and SMS messages** and useable in standalone mode, within a workflow or in a recurring delivery.

在多語言功能範本中，語言管理是以變體為基礎。**每個變數代表一種語言。**

Adobe Campaign Standard最多可設定40個變體。

Adobe Campaign隨附預設語言，設定為EN。預設語言可以變更為另一個變體，但絕不應加以刪除。

在建立範本期間，您可以新增與訊息中所需語言數目對應的變數數目。

若要執行SMS或電子郵件範本，請遵循下列步驟：

1. 複製現有的多語言範本(SMS或電子郵件)。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >You can also modify an existing standard template in a multilingual template by clicking on the **[!UICONTROL Initialize content variant]** button in the template properties.

1. 修改屬性以自訂標籤、追蹤等。
1. 按一下變數圖標以修改所需變數的數目。顯示變數視窗

   ![](assets/multi_template_variants.png)

   您可以新增或移除變數。To add a variant, complete the **[!UICONTROL New content variant]** window.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >請勿刪除「預設」變體，因為它是傳送至描述檔的變體，而不會使用已完成的慣用語言參數。

1. 視需要自訂標籤變體，並按一下確認。
1. 您也可以直接新增每個變體的內容。

您現在可以根據此多語言版範本，準備建立電子郵件或SMS訊息。

**相關主題：**

* [建立多語言電子郵件](../../channels/using/creating-a-multilingual-email.md)
* [建立描述檔](../../audiences/using/creating-profiles.md)

