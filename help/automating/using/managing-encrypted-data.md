---
title: 管理已加密的資料
description: 瞭解如何管理加密的資料。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows, Encryption
role: Data Architect
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: 69c47c8f3cbb405acbef634aa1ebaef8e767f159
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 3%

---

# 管理已加密的資料 {#managing-encrypted-data}

## 關於前置處理階段 {#about-preprocessing-stages}

在某些情況下，您想要匯入Campaign伺服器的資料可能需要加密，例如如果包含PII資料。

若要能夠加密傳出資料或解密傳入資料，您需要使用[控制面板](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=zh-Hant)管理GPG金鑰。

>[!NOTE]
>
>控制面板適用於在AWS上代管的所有客戶（內部部署代管行銷執行個體的客戶除外）。

如果您不符合使用「控制面板」的資格，您必須聯絡Adobe客戶服務，以便他們為您的執行個體提供所需的加密/解密命令。 要執行此操作，請提交請求，指出：

* 將在Campaign介面中顯示的&#x200B;**標籤**，以使用命令。 例如&quot;Encrypt file&quot;。
* 要在您的執行個體上安裝的&#x200B;**命令**。

處理要求後，**[!UICONTROL Load file]**&#x200B;和&#x200B;**[!UICONTROL Extract file]**&#x200B;活動的&#x200B;**[!UICONTROL Pre-processing stage]**&#x200B;欄位中即會提供加密/解密命令。 您可以使用它們來解密或加密您要匯入或匯出的檔案。

![](assets/preprocessing-encryption.png)

**相關主題：**

* [載入檔案](../../automating/using/load-file.md)
* [擷取檔案](../../automating/using/extract-file.md)

## 使用案例：匯入使用控制面板產生的金鑰加密的資料 {#use-case-gpg-decrypt}

在此使用案例中，建立工作流程，以匯入已在外部系統中加密的資料（使用在「控制面板」中產生的金鑰）。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

執行此使用案例的步驟如下：

1. 使用「控制面板」產生金鑰組（公用/私用）。 詳細步驟可在[控制面板檔案](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data)中取得。

   * 公開金鑰將與外部系統共用，外部系統將使用公開金鑰來加密要傳送至Campaign的資料。
   * Campaign將使用私密金鑰來解密傳入的加密資料。

   ![](assets/gpg_generate.png)

1. 在外部系統中，使用從「控制面板」下載的公開金鑰，將資料加密並匯入Campaign Standard。

1. 在Campaign Standard中，建立工作流程以匯入加密資料，並使用已透過「控制面板」安裝的私密金鑰加以解密。 若要這麼做，請建置工作流程，如下所示：

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]**&#x200B;活動：將檔案從外部來源傳輸至Campaign。 在此範例中，我們要從SFTP伺服器傳輸檔案。
   * **[!UICONTROL Load file]**&#x200B;活動：將檔案中的資料載入資料庫，並使用在「控制面板」中產生的私密金鑰加以解密。

1. 開啟&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動，然後根據您的需求進行設定。 有關如何設定活動的全域概念可在[本節](../../automating/using/load-file.md)中取得。

   在&#x200B;**[!UICONTROL Protocol]**&#x200B;索引標籤中，指定您要傳輸之sftp伺服器和加密.gpg檔案的詳細資料。

   ![](assets/gpg_transfer.png)

1. 開啟&#x200B;**[!UICONTROL Load file]**&#x200B;活動，然後根據您的需求進行設定。 有關如何設定活動的全域概念可在[本節](../../automating/using/load-file.md)中取得。

   為活動新增前置處理階段，以便解密傳入的資料。 若要這麼做，請從清單中選取&#x200B;**[!UICONTROL Decryption GPG]**&#x200B;選項。

   >[!NOTE]
   >
   >請注意，您不需要指定用來解密資料的私密金鑰。 私密金鑰儲存在「控制面板」中，其會自動偵測用來解密檔案的金鑰。

   ![](assets/gpg_load.png)

1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以確認活動設定。

1. 您現在可以執行工作流程。

## 使用案例：使用安裝於控制面板的金鑰加密及匯出資料 {#use-case-gpg-encrypt}

在此使用案例中，建立工作流程，以使用安裝於控制面板的金鑰加密及匯出資料。

![](assets/do-not-localize/how-to-video.png) [在影片中探索此功能](#video)

執行此使用案例的步驟如下：

1. 使用GPG公用程式產生GPG金鑰組（公用/私用），然後將公用金鑰安裝至「控制面板」。 詳細步驟可在[控制面板檔案](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data)中取得。

   ![](assets/gpg_install.png)

1. 在Campaign Standard中，建立工作流程以匯出資料，並使用已透過「控制面板」安裝的私密金鑰進行加密。 若要這麼做，請建置工作流程，如下所示：

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]**&#x200B;活動：在此範例中，我們要執行查詢，以定位要匯出之資料庫中的資料。
   * **[!UICONTROL Extract file]**&#x200B;活動：將資料加密並擷取到檔案中。
   * **[!UICONTROL Transfer file]**&#x200B;活動：將包含加密資料的檔案傳輸至SFTP伺服器。

1. 設定&#x200B;**[!UICONTROL Query]**&#x200B;活動，從資料庫中鎖定所需的資料。 如需詳細資訊，請參閱[本章節](../../automating/using/query.md)。

1. 開啟&#x200B;**[!UICONTROL Extract file]**&#x200B;活動，然後根據您的需求（輸出檔案、欄、格式等）進行設定。 有關如何設定活動的全域概念可在[本節](../../automating/using/extract-file.md)中取得。

   為活動新增前置處理階段，以便加密要擷取的資料。 若要這麼做，請選取用來加密資料的加密GPG金鑰。

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >括弧內的值是您使用GPG加密工具產生金鑰組時所定義的&#x200B;**註解**。 請確定您選取正確的相符金鑰，否則收件者將無法解密檔案。

1. 開啟&#x200B;**[!UICONTROL Transfer file]**&#x200B;活動，然後指定您要傳送檔案的SFTP伺服器。 有關如何設定活動的全域概念可在[本節](../../automating/using/transfer-file.md)中取得。

   ![](assets/gpg-transfer-encrypt.png)

1. 您現在可以執行工作流程。 一旦執行後，查詢的資料目標將會匯出至SFTP伺服器加密的.gpg檔案中。

## 教學課程影片 {#video}

本影片說明如何使用GPG金鑰來解密資料。

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

本影片說明如何使用GPG金鑰加密資料。

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)提供其他Campaign Standard操作說明影片。
