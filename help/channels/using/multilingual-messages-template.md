---
solution: Campaign Standard
product: campaign
title: 多語言訊息範本
description: 瞭解如何根據自動細分客戶偏好的語言，透過單一傳送來定義並執行多語言電子郵件/簡訊傳送。報告每次傳送的效能，包括語言和個別層級。
audience: start
content-type: reference
topic-tags: managing-templates
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---


# 多語言訊息範本 {#multilingual-messages-template}

多語言範本是管理多語言訊息的特定範本。此類範本適用於&#x200B;**電子郵件**&#x200B;及&#x200B;**簡訊**，並可在獨立模式、工作流程或循環傳送中使用。

在多語言功能範本中，語言管理是以變體為基礎。**每個變體代表一種語言**。Adobe Campaign Standard 最多可設定 40 種變體。

Adobe Campaign 隨附設為 **EN** 的預設語言。預設語言可變更為其他變體，但絕對不應將之刪除。

在建立範本期間，您可以在訊息中新增與所需語言數目相對應的變體數目。

若要建立簡訊或電子郵件範本，請遵循下列步驟：

1. 複製現有的多語言範本（簡訊或電子郵件）。

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >您也可以按一下範本屬性中的 **[!UICONTROL Initialize content variant]** 按鈕，修改多語言範本中現有的標準範本。

1. 修改屬性以自訂標籤、追蹤等。

1. 按一下變體動態磚，以修改所需變體的數目。變體視窗隨即顯示將

   ![](assets/multi_template_variants.png)

   您可以新增或移除變體。若要新增變體，請完成 **[!UICONTROL New content variant]** 視窗。

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >請勿刪除「預設」變體，因為它是傳送至設定檔的變體，而且沒有完整的偏好語言參數。

1. 視需要自訂標籤變體，然後按一下 **[!UICONTROL Confirm]**。

1. 您也可以直接為每個變體新增內容。

您現在可以依據這個多語言範本，建立電子郵件或簡訊。

**相關主題：**

* [建立多語言電子郵件](../../channels/using/creating-a-multilingual-email.md)
* [建立設定檔](../../audiences/using/creating-profiles.md)
