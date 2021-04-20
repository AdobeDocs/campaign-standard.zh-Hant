---
solution: Campaign Standard
product: campaign
title: 在 Adobe Experience Manager 中建立電子郵件內容.
description: 透過Adobe Experience Manager整合，您可以直接在中建立內容，AEM並稍後在Adobe Campaign使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 2%

---


# 將Adobe Experience Manager內容導入Adobe Campaign電子郵件{#creating-email-aem}

使用本檔案，您將學習如何在Adobe Experience Manager建立和管理電子郵件內容，然後將這些內容匯入您的電子郵件至Adobe Campaign Standard，以用於行銷宣傳。

先決條件為：

* 存取為整AEM合設定的例項。
* 存取為整合設定的Adobe Campaign例項。
* 配置為接收內容的Adobe Campaign電AEM子郵件模板。

## 訪問Adobe Experience Manager的電子郵件{#email-content-aem}

登入您的Adobe Experience Manager編寫例項，並瀏覽您的網站以存取包含您電子郵件內容的資料夾。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## 在Adobe Experience Manager建立新的電子郵件內容{#creating-email-content-aem}

有幾個Adobe Campaign特有的模板可供使用。 您必須使用其中一個範本，因為這些範本包含Adobe Campaign支援的預先定義元件。

根據預設，兩個預先定義的範本可讓您建立Adobe Campaign的電子郵件內容。

* **[!UICONTROL Adobe Campaign Email]**:此範本包含可個人化的標準內容。您可以選擇「Adobe Campaign電子郵件(AC6.1)」和「Adobe Campaign電子郵件(ACS)」。
* **[!UICONTROL Importer Page]**:此範本可讓您匯入包含HTML檔案的ZIP檔案，其中包含內容，然後您就可以個人化。

1. 在Adobe Experience Manager，建立新的&#x200B;**[!UICONTROL Page]**。

1. 選擇&#x200B;**[!UICONTROL Adobe Campaign Email]**&#x200B;模板。 有關詳細步驟，請參閱以下視頻。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 開啟您的新電子郵件內容。

1. 在&#x200B;**[!UICONTROL Page properties]**&#x200B;中，將&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;設為&#x200B;**[!UICONTROL Cloud Service Configuration]**。 如此可讓您的內容與您的Adobe Campaign實例進行通訊。

   如需詳細資訊，請觀看下列影片：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 編輯和傳送電子郵件{#editing-email-aem}

您可以新增元件和資產來編輯電子郵件內容。 個人化欄位可用來根據Adobe Campaign的收件者資料傳遞更相關的訊息。

要在Adobe Experience Manager建立電子郵件內容：

1. 從sidekick存取&#x200B;**[!UICONTROL Page properties]** > **[!UICONTROL Email]**&#x200B;標籤，編輯您電子郵件的主旨和&#x200B;**[!UICONTROL Plain text]**&#x200B;版本。

1. 通過&#x200B;**[!UICONTROL Text & Personalization]**&#x200B;元件添加&#x200B;**[!UICONTROL Personalization fields]**。 每個元件都與特定用法相對應：插入影像、新增個人化等。

   如需詳細資訊，請觀看下列影片：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 從&#x200B;**[!UICONTROL Workflow]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL Approve for Adobe Campaign]**&#x200B;驗證工作流。 如果電子郵件使用的內容未經核准，您將無法在Adobe Campaign傳送電子郵件。

1. 定義內容和傳送參數後，您就可以在Adobe Campaign Standard繼續核准、準備和傳送電子郵件。

   如需詳細資訊，請觀看下列影片：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
