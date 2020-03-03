---
title: 在 Adobe Experience Manager 中建立電子郵件內容.
description: 透過Adobe Experience manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9efce905cd767013a22afb2a4d642e42b6616ef1

---


# 將Adobe Experience manager內容匯入Adobe Campaign電子郵件 {#creating-email-aem}

使用本檔案，您將學習如何在Adobe Experience manager中建立和管理電子郵件內容，然後將這些內容匯入Adobe Campaign Standard，以用於您的行銷宣傳。

先決條件為：

* 存取為整合設定的AEM例項。
* 存取為整合設定的Adobe Campaign例項。
* Adobe Campaign電子郵件範本，已設定為接收AEM內容。

## 在Adobe Experience manager中存取電子郵件 {#email-content-aem}

登入您的Adobe Experience Manager製作例項，並瀏覽您的網站以存取包含您電子郵件內容的檔案夾。

>[!VIDEO](https://images-tv.adobe.com/mpcv3/2674d459-d57b-413b-9d34-9fd941666023_1575035768.854x480at800_h264.mp4)

## Creating new email content in Adobe Experience Manager {#creating-email-content-aem}

有數個Adobe Campaign專用的範本可供使用。 您必須使用其中一個範本，因為這些範本包含Adobe Campaign支援的預先定義元件。

依預設，兩個預先定義的範本可讓您建立Adobe Campaign的電子郵件內容。

* **[!UICONTROL Adobe Campaign Email]**:此範本包含可個人化的標準內容。 您可以選擇Adobe Campaign電子郵件(AC6.1)和Adobe Campaign電子郵件(ACS)。
* **[!UICONTROL Importer Page]**:此範本可讓您匯入包含HTML檔案的ZIP檔案，其中包含內容，然後您就可以個人化。

1. 在Adobe Experience Manager中建立新 **[!UICONTROL Page]**。

1. 選擇模 **[!UICONTROL Adobe Campaign Email]** 板。 有關詳細步驟，請參閱以下視頻。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 開啟您的新電子郵件內容。

1. 在中 **[!UICONTROL Page properties]**，設 **[!UICONTROL Adobe Campaign]** 置為 **[!UICONTROL Cloud Service Configuration]**。 這可讓您的內容與Adobe Campaign實例進行通訊。

   如需詳細資訊，請觀看下列影片：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 編輯和傳送電子郵件 {#editing-email-aem}

您可以新增元件和資產來編輯電子郵件內容。 個人化欄位可用來根據Adobe Campaign中收件者的資料，傳遞更相關的訊息。

若要在Adobe Experience manager中建立電子郵件內容：

1. 從sidekick存取>標籤， **[!UICONTROL Plain text]** 以編輯主旨 **[!UICONTROL Page properties]****[!UICONTROL Email]** 和電子郵件版本。

1. 透過 **[!UICONTROL Personalization fields]** 元件 **[!UICONTROL Text & Personalization]** 新增。 每個元件都與特定用法相對應：插入影像、新增個人化等。

   如需詳細資訊，請觀看下列影片：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 從標籤中 **[!UICONTROL Workflow]** 選擇驗證工 **[!UICONTROL Approve for Adobe Campaign]** 作流程。 如果Adobe Campaign使用的內容未經核准，您將無法在Adobe Campaign中傳送電子郵件。

1. 在定義內容和傳送參數後，您就可以在Adobe Campaign standard中繼續核准、準備和傳送電子郵件。

   如需詳細資訊，請觀看下列影片：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
