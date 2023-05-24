---
title: 在 Adobe Experience Manager 中建立電子郵件內容.
description: 通過Adobe Experience Manager整合，您可以直接在中創AEM建內容，稍後在Adobe Campaign使用。
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

# 將Adobe Experience Manager內容導入Adobe Campaign電子郵件 {#creating-email-aem}

使用此文檔，您將學習如何在Adobe Experience Manager建立和管理電子郵件內容，然後將這些內容導入您的電子郵件到Adobe Campaign Standard，以用於您的市場營銷活動。

先決條件為：

* 對為集AEM成配置的實例的訪問。
* 訪問為整合配置的Adobe Campaign實例。
* 配置為接收內容的Adobe Campaign電AEM子郵件模板。

## 訪問Adobe Experience Manager的電子郵件 {#email-content-aem}

登錄到您的Adobe Experience Manager創作實例並瀏覽您的站點以訪問包含電子郵件內容的資料夾。

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## 在Adobe Experience Manager建立新電子郵件內容 {#creating-email-content-aem}

提供了幾個Adobe Campaign特有的模板。 您必須使用其中一個模板，因為它們包含Adobe Campaign支援的預定義元件。

預設情況下，兩個預定義模板允許您為Adobe Campaign建立電子郵件內容。

* **[!UICONTROL Adobe Campaign Email]**:此模板包含可個性化的標準內容。 您可以選擇Adobe Campaign電子郵件(AC6.1)和Adobe Campaign電子郵件(ACS)。
* **[!UICONTROL Importer Page]**:此模板允許您導入包含HTML檔案的ZIP檔案，該檔案包含內容，然後您就可以對其進行個性化設定。

1. 在Adobe Experience Manager，建立 **[!UICONTROL Page]**。

1. 選擇 **[!UICONTROL Adobe Campaign Email]** 的下界。 有關詳細步驟，請參閱以下視頻。
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. 開啟新電子郵件內容。

1. 在 **[!UICONTROL Page properties]**。 **[!UICONTROL Adobe Campaign]** 的 **[!UICONTROL Cloud Service Configuration]**。 這樣，您的內容與您的Adobe Campaign實例之間便可進行通信。

   有關詳細資訊，請觀看以下視頻：

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## 編輯和發送電子郵件 {#editing-email-aem}

您可以通過添加元件和資產來編輯電子郵件內容。 個性化欄位可用於根據Adobe Campaign的接收者資料傳遞更相關的消息。

要在Adobe Experience Manager建立電子郵件內容：

1. 編輯主題以及 **[!UICONTROL Plain text]** 通過訪問 **[!UICONTROL Page properties]** > **[!UICONTROL Email]** 從旁邊踢來。

1. 添加 **[!UICONTROL Personalization fields]** 通過 **[!UICONTROL Text & Personalization]** 元件。 每個元件對應於特定用法：插入影像、添加個性化等。

   有關詳細資訊，請觀看以下視頻：
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. 從 **[!UICONTROL Workflow]** 頁籤 **[!UICONTROL Approve for Adobe Campaign]** 驗證工作流。 如果Adobe Campaign使用的內容未經批准，您將無法在該地區發送電子郵件。

1. 定義內容和發送參數後，您可以在Adobe Campaign Standard繼續批准、準備和發送電子郵件。

   有關詳細資訊，請觀看以下視頻：

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
