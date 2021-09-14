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

使用本檔案，您將學習如何在Adobe Experience Manager中建立和管理電子郵件內容，然後將這些內容匯入您的電子郵件至Adobe Campaign Standard，以用於您的行銷活動。

先決條件為：

* 存取針對整合設定的AEM例項。
* 存取針對整合設定的Adobe Campaign執行個體。
* 設定為接收AEM內容的Adobe Campaign電子郵件範本。

## 存取Adobe Experience Manager中的電子郵件 {#email-content-aem}

登入您的Adobe Experience Manager編寫執行個體並瀏覽您的網站，以存取包含您電子郵件內容的資料夾。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## 在Adobe Experience Manager中建立新電子郵件內容 {#creating-email-content-aem}

提供Adobe Campaign專用的數個範本。 您必須使用其中一個範本，因為這些範本包含Adobe Campaign支援的預先定義元件。

依預設，兩個預先定義的範本可讓您建立Adobe Campaign的電子郵件內容。

* **[!UICONTROL Adobe Campaign Email]**:此範本包含可供個人化的標準內容。您可以在Adobe Campaign電子郵件(AC6.1)和Adobe Campaign電子郵件(ACS)之間做選擇。
* **[!UICONTROL Importer Page]**:此範本可讓您匯入包含HTML檔案的ZIP檔案，其中包含您之後將能個人化的內容。

1. 在Adobe Experience Manager中，建立新的&#x200B;**[!UICONTROL Page]**。

1. 選取&#x200B;**[!UICONTROL Adobe Campaign Email]**&#x200B;範本。 有關詳細步驟，請參閱以下視頻。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 開啟您的新電子郵件內容。

1. 在&#x200B;**[!UICONTROL Page properties]**&#x200B;中，將&#x200B;**[!UICONTROL Adobe Campaign]**&#x200B;設定為&#x200B;**[!UICONTROL Cloud Service Configuration]**。 這可讓您的內容與Adobe Campaign執行個體之間通訊。

   如需詳細資訊，請觀看下列影片：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 編輯和傳送電子郵件 {#editing-email-aem}

您可以新增元件和資產，以編輯電子郵件內容。 個人化欄位可用來根據Adobe Campaign中的收件者資料，傳送更相關的訊息。

若要在Adobe Experience Manager中建立電子郵件內容：

1. 從sidekick存取&#x200B;**[!UICONTROL Page properties]** > **[!UICONTROL Email]**&#x200B;標籤，編輯主旨以及電子郵件的&#x200B;**[!UICONTROL Plain text]**&#x200B;版本。

1. 透過&#x200B;**[!UICONTROL Text & Personalization]**&#x200B;元件新增&#x200B;**[!UICONTROL Personalization fields]**。 每個元件都對應至特定用途：插入影像、新增個人化等。

   如需詳細資訊，請觀看下列影片：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 從&#x200B;**[!UICONTROL Workflow]**&#x200B;標籤中，選擇&#x200B;**[!UICONTROL Approve for Adobe Campaign]**&#x200B;驗證工作流。 如果Adobe Campaign使用的內容尚未核准，您將無法傳送電子郵件。

1. 定義內容和傳送參數後，您就可以繼續在Adobe Campaign Standard中核准、準備和傳送電子郵件。

   如需詳細資訊，請觀看下列影片：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
