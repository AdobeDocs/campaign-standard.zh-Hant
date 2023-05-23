---
title: 管理已加密的資料
description: 瞭解如何管理加密資料。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 4%

---

# 管理已加密的資料 {#managing-encrypted-data}

## 關於預處理階段 {#about-preprocessing-stages}

在某些情況下，您要導入市場活動伺服器的資料可能需要加密，例如，如果它包含PII資料。

要能夠加密傳出資料或解密傳入資料，您需要使用 [控制面板](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=zh-Hant)。

>[!NOTE]
>
>控制面板可供AWS托管的所有客戶使用（不包括在內部托管其營銷實例的客戶）。

如果您沒有資格使用「控制面板」，則需要與「Adobe客戶服務」聯繫，以便他們為您的實例提供所需的加密/解密命令。 為此，請提交一個請求，指明：

* 的 **標籤** 將顯示在「市場活動」介面中以使用該命令。 例如「加密檔案」。
* 的 **命令** 安裝到實例上。

一旦處理了請求，加密/解密命令將在 **[!UICONTROL Pre-processing stage]** 的 **[!UICONTROL Load file]** 和 **[!UICONTROL Extract file]** 活動。 您可以使用它們來解密或加密要導入或導出的檔案。

![](assets/preprocessing-encryption.png)

**相關主題：**

* [載入檔案](../../automating/using/load-file.md)
* [擷取檔案](../../automating/using/extract-file.md)

## 用例：導入使用控制面板生成的密鑰加密的資料 {#use-case-gpg-decrypt}

在此使用情形中，使用「控制面板」中生成的密鑰構建工作流以導入在外部系統中加密的資料。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

執行此使用情形的步驟如下：

1. 使用「控制面板」生成密鑰對（公共/專用）。 有關詳細步驟，請參閱 [控制面板文檔](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data)。

   * 公鑰將與外部系統共用，外部系統將使用公鑰加密要發送到市場活動的資料。
   * 市場活動將使用私鑰來解密傳入的加密資料。

   ![](assets/gpg_generate.png)

1. 在外部系統中，使用從控制面板下載的公鑰對要導入到Campaign Standard的資料進行加密。

1. 在Campaign Standard中，構建工作流以導入加密資料並使用通過控制面板安裝的私鑰對其進行解密。 為此，請按如下方式構建工作流：

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** 活動：將檔案從外部來源傳輸到市場活動。 在本示例中，我們要從SFTP伺服器傳輸檔案。
   * **[!UICONTROL Load file]** 活動：將資料從檔案載入到資料庫中，並使用控制面板中生成的私鑰對其進行解密。

1. 開啟 **[!UICONTROL Transfer file]** 活動，然後根據您的需要配置。 有關如何配置活動的全局概念，請參見 [此部分](../../automating/using/load-file.md)。

   在 **[!UICONTROL Protocol]** 頁籤，指定有關sftp伺服器和要傳輸的加密.gpg檔案的詳細資訊。

   ![](assets/gpg_transfer.png)

1. 開啟 **[!UICONTROL Load file]** 活動，然後根據需要配置。 有關如何配置活動的全局概念，請參見 [此部分](../../automating/using/load-file.md)。

   向活動添加預處理階段以解密傳入資料。 要執行此操作，請選擇 **[!UICONTROL Decryption GPG]** 的子菜單。

   >[!NOTE]
   >
   >請注意，您不需要指定用於解密資料的私鑰。 專用密鑰儲存在「控制面板」中，「控制面板」將自動檢測用於解密檔案的密鑰。

   ![](assets/gpg_load.png)

1. 按一下 **[!UICONTROL OK]** 確認活動配置。

1. 您現在可以運行工作流。

## 用例：使用控制面板上安裝的密鑰加密和導出資料 {#use-case-gpg-encrypt}

在此使用情形中，請構建工作流，以便使用「控制面板」上安裝的密鑰加密和導出資料。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

執行此使用情形的步驟如下：

1. 使用GPG實用程式生成GPG密鑰對（公共/私有），然後將公鑰安裝到控制面板上。 有關詳細步驟，請參閱 [控制面板文檔](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data)。

   ![](assets/gpg_install.png)

1. 在Campaign Standard中，構建工作流以導出資料並使用通過控制面板安裝的私鑰對其進行加密。 為此，請按如下方式構建工作流：

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** 活動：在此示例中，我們要執行查詢以針對要從要導出的資料庫中的資料。
   * **[!UICONTROL Extract file]** 活動：將資料加密並提取到檔案中。
   * **[!UICONTROL Transfer file]** 活動：將包含加密資料的檔案傳輸到SFTP伺服器。

1. 配置 **[!UICONTROL Query]** 活動，以從資料庫中確定所需資料的目標。 如需詳細資訊，請參閱[本章節](../../automating/using/query.md)。

1. 開啟 **[!UICONTROL Extract file]** 活動，然後根據您的需要（輸出檔案、列、格式等）配置。 有關如何配置活動的全局概念，請參見 [此部分](../../automating/using/extract-file.md)。

   向活動添加預處理階段，以加密要提取的資料。 為此，請選擇用於加密資料的加密GPG密鑰。

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >括弧中的值是 **注釋** 在使用GPG加密工具生成密鑰對時定義的密鑰對。 請確保選擇了正確的匹配密鑰，否則收件人將無法解密該檔案。

1. 開啟 **[!UICONTROL Transfer file]** 活動，然後指定要向其發送檔案的SFTP伺服器。 有關如何配置活動的全局概念，請參見 [此部分](../../automating/using/transfer-file.md)。

   ![](assets/gpg-transfer-encrypt.png)

1. 您現在可以運行工作流。 一旦執行，查詢所生成的資料目標將導出到SFTP伺服器中，並生成加密的.gpg檔案。

## 教學課程影片 {#video}

此視頻顯示如何使用GPG密鑰解密資料。

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

此視頻顯示如何使用GPG密鑰加密資料。

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

可提供其他Campaign Standard操作視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)。
