---
title: 多語言訊息範本
description: 瞭解如何根據自動細分客戶偏好的語言，透過單一傳遞來定義並執行多語言電子郵件／簡訊傳送。 報告每次傳送的效能，包括語言和個別層級。
page-status-flag: never-activated
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# 多語言訊息範本 {#multilingual-messages-template}

多語言範本是管理多語言訊息的特定範本。 此類範本適用於 **Email** 和 **SMS訊息** ，並可在獨立模式、工作流程或循環傳送中使用。

在多語言功能範本中，語言管理是以變體為基礎。 **每個變體代表一種語言**。 Adobe Campaign Standard最多可設定40種變體。

Adobe Campaign隨附預設語言，設為 **EN**。 預設語言可以變更為其他變體，但絕不應刪除。

在建立範本期間，您可以在訊息中新增與所需語言數目對應的變數數目。

若要建立SMS或電子郵件範本，請遵循下列步驟：

1. 複製現有的多語言範本（SMS或電子郵件）。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >您也可以按一下範本屬性中的按鈕，修改多語言範本 **[!UICONTROL Initialize content variant]** 中現有的標準範本。

1. 修改屬性以自訂標籤、追蹤等。
1. 按一下變數方塊，修改所需變數的數目。 將顯示變型窗口

   ![](assets/multi_template_variants.png)

   您可以新增或移除變數。 要添加變型，請完成窗 **[!UICONTROL New content variant]** 口。

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >請勿刪除「預設」變體，因為它是傳送至描述檔的變體，而沒有完整的偏好語言參數。

1. 視需要自訂標籤變體，然後按一下 **[!UICONTROL Confirm]**。
1. 您也可以直接新增每個變體的內容。

您現在可以根據此多語言範本，建立電子郵件或SMS訊息。

**相關主題：**

* [建立多語言電子郵件](../../channels/using/creating-a-multilingual-email.md)
* [建立設定檔](../../audiences/using/creating-profiles.md)
