---
title: 在 Adobe Experience Manager 中建立電子郵件內容.
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---

# 將Adobe Experience Manager內容匯入Adobe Campaign電子郵件 {#creating-email-aem}

透過此檔案，您將瞭解如何在Adobe Experience Manager中建立和管理電子郵件內容，然後將其匯入至Adobe Campaign Standard，用於行銷活動。

先決條件為：

* 存取針對整合設定的AEM執行個體。
* 存取針對整合設定的Adobe Campaign執行個體。
* 設定為接收AEM內容的Adobe Campaign電子郵件範本。

## 在Adobe Experience Manager中存取電子郵件 {#email-content-aem}

登入您的Adobe Experience Manager編寫執行個體並瀏覽您的網站，以存取包含您的電子郵件內容的資料夾。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## 在Adobe Experience Manager中建立新電子郵件內容 {#creating-email-content-aem}

有數個Adobe Campaign專屬的範本可供使用。 您必須使用其中一個範本，因為它們包含Adobe Campaign支援的預先定義元件。

依預設，有兩個預先定義的範本可讓您建立Adobe Campaign的電子郵件內容。

* **[!UICONTROL Adobe Campaign Email]**：此範本包含您可以個人化的標準內容。 您可以在Adobe Campaign電子郵件(AC6.1)和Adobe Campaign電子郵件(ACS)之間選擇。
* **[!UICONTROL Importer Page]**：此範本可讓您匯入包含HTML檔案的ZIP檔案，其中包含您之後可個人化的內容。

1. 在Adobe Experience Manager中，建立新的 **[!UICONTROL Page]**.

1. 選取 **[!UICONTROL Adobe Campaign Email]** 範本。 如需詳細步驟，請參閱以下影片。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 開啟您的新電子郵件內容。

1. 在 **[!UICONTROL Page properties]**，設定 **[!UICONTROL Adobe Campaign]** 作為 **[!UICONTROL Cloud Service Configuration]**. 如此一來，您的內容就能與Adobe Campaign執行個體通訊。

   如需詳細資訊，請觀看下列影片：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 編輯和傳送電子郵件 {#editing-email-aem}

您可以新增元件和資產來編輯電子郵件內容。 個人化欄位可用於根據Adobe Campaign中的收件者資料，傳遞更具相關性的訊息。

若要在Adobe Experience Manager中建立電子郵件內容：

1. 編輯主旨以及 **[!UICONTROL Plain text]** 存取您的電子郵件版本 **[!UICONTROL Page properties]** > **[!UICONTROL Email]** tab鍵從sidekick移出。

1. 新增 **[!UICONTROL Personalization fields]** 透過 **[!UICONTROL Text & Personalization]** 元件。 每個元件都與特定的使用方式相對應：插入影像、新增個人化等。

   如需詳細資訊，請觀看下列影片：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 從 **[!UICONTROL Workflow]** 索引標籤中，選取 **[!UICONTROL Approve for Adobe Campaign]** 驗證工作流程。 如果您使用Adobe Campaign中尚未核准的內容，便無法傳送電子郵件。

1. 定義內容和傳送引數後，您可以在Adobe Campaign Standard中繼續核准、準備和傳送電子郵件。

   如需詳細資訊，請觀看下列影片：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
