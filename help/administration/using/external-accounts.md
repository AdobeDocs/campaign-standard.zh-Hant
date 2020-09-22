---
title: 外部帳戶
description: 設定外部帳戶以設定與外部系統（例如 SFTP 伺服器）的連線。
page-status-flag: never-activated
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d5c6a3d4-f767-46c1-a8c0-3b9dc52dcea8
internal: n
snippet: y
context-tags: extAccount,main;extAccount,overview
translation-type: tm+mt
source-git-commit: 9ba56ca09a1ae948b6d4b1945085f59db1ade973
workflow-type: tm+mt
source-wordcount: '1774'
ht-degree: 84%

---


# 外部帳戶{#external-accounts}

外部帳戶是可讓您設定並測試對 Adobe Campaign 外部伺服器的存取權的設定。

這些外部帳戶可用於行銷活動工作流程，以存取和管理資料。

您可以設定下列外部帳戶類型：

* SFTP。如需詳細資訊，請參閱[本區段](#sftp-external-account)。
* Amazon Storage Service (S3)。如需詳細資訊，請參閱[本區段](#amazon-s3-external-account)。
* Adobe Experience Manager。如需詳細資訊，請參閱[本區段](#adobe-experience-manager-external-account)。
* Adobe Analytics。如需詳細資訊，請參閱[本區段](../../integrating/using/configure-campaign-analytics-integration.md)。
* Google reCAPTCHA。如需詳細資訊，請參閱[本區段](#google-recaptcha-external-account)。
* Microsoft Azure Blob 儲存。如需詳細資訊，請參閱[本區段](#microsoft-azure-external-account)。
* OAuth 2.0. For more on this, refer to [this section](#oauth-account).

>[!NOTE]
>
>Adobe 在產品佈建程式期間會使用其他類型的外部帳戶。從 Campaign Standard 17.9 發行，FTP 外部帳戶仍可定義，但無法再用於新的工作流程活動。如果已設定連接，則該連接仍處於啟用狀態。

管理員可在 **[!UICONTROL Administration > Application settings > External accounts]** 功能表下設定外部帳戶。

## 建立外部帳戶 {#creating-an-external-account}

Adobe Campaign 隨附一組預先定義的外部帳戶。若要設定與外部系統（例如用於檔案傳輸的 FTP 伺服器）的連線，您可以建立自己的外部帳戶。

技術流程（例如技術工作流程或宣傳工作流程）會使用外部帳戶。在工作流程中或與任何其他應用程式（Adobe Target、Experience Manager 等）進行資料交換時，您需要選取外部帳戶。

1. 按一下 **[!UICONTROL Create]** 按鈕。
1. 輸入標籤。在工作流程中選取外部帳戶時，將會使用標籤和 ID。
1. 選取要建立的帳戶類型。
1. 在相關時指定憑證、伺服器位址、連接埠號碼或金鑰，以設定帳戶的存取權。

   所需資訊通常由您所連接的伺服器提供者提供。

1. 儲存您的帳戶。

外部帳戶會建立並新增至帳戶清單。它現在可用於工作流活動和傳送屬性中的資料/檔案傳輸或路由配置。

## SFTP 外部帳戶 {#sftp-external-account}

不同的外部帳戶類型需要指定不同的資訊。

對於 SFTP 外部帳戶，請提供下列詳細資訊：

* 伺服器位址。例如，**ftp.domain.com**。
* 埠號。例如，**22**。
* SFTP伺服器憑證：用來連接至伺服器的帳戶名稱和密碼。

### Adobe 代管 SFTP 伺服器建議 {#adobe-hosted-sftp-server-recommendations}

管理用於 ETL 的檔案和資料時，這些檔案儲存在 Adobe 提供的代管 SFTP 伺服器上。此 SFTP 旨在作為臨時儲存空間，您可以在其上控製檔案的保留和刪除。

當未正確使用或監視時，此空間可快速填滿伺服器上的可用物理空間，並造成嚴重問題。這可能會導致平台上的資料遺失或損毀。

為避免此類問題，Adobe 建議遵循以下最佳實作。

* 盡可能保持最小的資料。
* 使用基於密鑰的身份驗證以避免密碼過期。支援的格式僅限 **OpenSSH** 及 **SSH2**。您必須提供公開金鑰給 Adobe 支援團隊，才能將它上傳到 Campaign 伺服器。
* 只需視需要保留資料。最大時間限制是 15 天。
* 使用工作流程正確刪除資料（管理使用資料的工作流程的保留）。
* 在 SFTP 上載和工作流程中使用批次處理。
* 處理錯誤/例外狀況。
* 時常登入 SFTP 以直接檢查其內容。
* 請記住，SFTP 硬碟的管理主要是您的責任。

此外，請注意，您嘗試從中啟動SFTP連線的公用IP必須新增至促銷活動例項的allowlist。 Adding IP addresses to the allowlist can be requested via a [support ticket](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html), along with providing the public key to use for authentication.

SFTP 伺服器可從「控制面板」進行管理。如需詳細資訊，請參閱[控制面板文件](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/sftp-management/about-sftp-management.html)。

>[!NOTE]
>
>控制面板僅適用於 AWS 代管客戶的管理員使用者。
[在此處](https://docs.adobe.com/content/help/zh-Hant/control-panel/using/faq.html#ims-org-id)查看您的執行個體是否在 AWS 上代管。

## OAuth 2.0帳戶 {#oauth-account}

若為OAuth 2.0外部帳戶，請提供下列詳細資訊：

* 授 **權類型**:僅支 **援用戶端憑證** 。
* 安 **全API URL**:輸入授權端點。
* **OAuth 2.0敏感認證**:本節是針對性質敏感的認證。 憑證值新增後，會在螢幕上遮色；到那時，它們將無法閱讀或編輯。 如果授權端點要求將特定憑證插入HTTP授權標題，而非POST內文參數，則可以為該憑證選擇「在標題中包含」選項。
* **OAuth 2.0非敏感性認證**:本節是針對性質不敏感的認證。 憑證值新增後，會顯示在畫面上；也可以編輯。  如果授權端點要求將特定憑證插入HTTP授權標題，而非POST內文參數，則可以為該憑證選擇「在標題中包含」選項。

在設定結束時，按一下「 **測試連接器** 」以確認外部帳戶設定正確。

![](assets/external_accounts_OAuth.png)

>[!NOTE]
>
>認證「Content-Type:application/x-www-form-urlencoded」和「grant_type=client_credentials」會自動新增至API呼叫；因此，您不需要在認證區段中新增它們。

## Amazon S3 外部帳戶 {#amazon-s3-external-account}

Amazon S3 伺服器欄位應填寫如下：

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

若要以S3加密模式儲存檔案，請核取 **[!UICONTROL Keep files in S3 encrypted]** 方塊。

![](assets/external_accounts_2.png)

所需資訊通常由您所連接的伺服器提供者提供。

指定與端點相關聯的 **[!UICONTROL AWS Region]**。您可以在官方的 [Amazon S3 文件](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region)中查看受支援的地區和簽名版本。

>[!NOTE]
>
>若找不到您的 AWS 地區，則應該輸入 **[!UICONTROL Receiver server]**，以後將自動將其新增到您的 URL 中。

### Amazon S3 帳戶建議 {#amazon-s3-account-recommendations}

為協助您設定 Amazon S3 帳戶，我們建議您遵循下列建議：

* 建立嚴格的儲存貯體原則，以限制對 S3 儲存貯體的存取。建立儲存貯體時，可設定儲存貯體原則。如需詳細資訊，請參閱 [Amazon S3 文件](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html)。
* 建立外部帳戶時，請核取 **[!UICONTROL Keep files in S3 encrypted]** 方塊，啟用加密以將敏感資料儲存在 S3 儲存貯體。
* 授予儲存貯體權限，以指定誰可以存取儲存貯體中的物件。有關貯體權限的詳細資訊，請參閱 [Amazon S3 文件](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)。

## Adobe Experience Manager 外部帳戶 {#adobe-experience-manager-external-account}

Adobe Experience Manager 外部帳戶用於整合 Campaign 與 Experience Manager。

[本文件](../../integrating/using/get-started-campaign-integrations.md)提供與此整合相關的程序及需求。

當您設定此新外部帳戶時，您必須提供下列詳細資訊：

* 伺服器： 輸入 Adobe Experience Manager 伺服器的 URL。例如：

   ```
   http://aem.domain.com:4502
   ```

* AEM 帳戶認證：使用可存取 Adobe Experience Manager 執行個體的帳戶。它應該是 Experience Manager 中行銷活動 - 遠端群組的帳戶部分。

## Google reCAPTCHA 外部帳戶 {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHA 設定需要 Google 帳戶。

Google reCAPTCHA 機制可讓您保護著陸頁面，使其免受機器人程式造成的垃圾郵件和濫用。這對您的客戶來說不會造成干擾，因為它不需要客戶進行任何互動，而且是以與您網站的互動為基礎。若要註冊您的網站，請參閱本[頁面](https://www.google.com/recaptcha/admin/create)。您必須選取 V3 reCAPTCHA 類型。

若要將 Google reCAPTCHA V3 新增至您的登錄頁面，您必須先在外部帳戶中進行設定。如需如何將其新增至著陸頁面的詳細資訊，請參閱[本區段](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)。

若為 Google reCAPTCHA V3 外部帳戶，請提供下列詳細資訊：

* 您外部帳戶的 **[!UICONTROL Label]** 及 **[!UICONTROL ID]**
* **[!UICONTROL Type]**：Google reCAPTCHA
* 您的 **[!UICONTROL Site key]** 和 **[!UICONTROL Site secret]**
* **[!UICONTROL Threshold]** 介於 0 和 1 之間

   0.0 **[!UICONTROL Threshold]** 值表示它可能是機器人，1.0 可能是良好的互動。預設情況下，可以使用閾值 0.5。

![](assets/external_accounts_3.png)

## Microsoft Azure Blob 儲存外部帳戶 {#microsoft-azure-external-account}

>[!NOTE]
>
>在 Adobe Campaign Standard 中設定外部帳戶所需資訊可於 Azure Portal 取得，方法是選取 **[!UICONTROL Settings]** > **[!UICONTROL Access keys]**。

Azure Blob 儲存連接器可用來匯入或匯出資料至 Adobe Campaign，使用工作流程 **[!UICONTROL Transfer file]** 活動。如需詳細資訊，請參閱本[區段](../../automating/using/transfer-file.md#azure-blob-configuration-wf)。

對於 Microsoft Azure Blob 儲存外部帳戶，請提供以下詳細資訊：

* 您外部帳戶的 **[!UICONTROL Label]** 及 **[!UICONTROL ID]**
* **[!UICONTROL Type]**：Microsoft Azure Blob 儲存
* 您的 **[!UICONTROL Account name]** 和 **[!UICONTROL Account key]**。若要瞭解在何處尋找您的帳戶名稱和金鑰，請參閱本[頁面](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage)。
* 您的 **[!UICONTROL Endpoint suffix]**。您可在 Azure 入口網站 **[!UICONTROL Access keys]** 功能表內的 **[!UICONTROL Connection string]** 找到它。如需詳細資訊，請參閱此[頁面](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage)。
* 您的 **[!UICONTROL Container]** 名稱。如果您打算使用多個容器，則需要建立與容器一樣多的外部帳戶。
* **[!UICONTROL Concurrency]** 選項可讓您微調檔案傳輸的速度。

![](assets/external_accounts_4.png)

設定之後，按一下 **[!UICONTROL Test connection]**，將 Adobe Campaign 連結至 Microsoft Azure Blob 儲存空間。

### Microsoft Azure Blob 儲存建議 {#azure-blob-recommendations}

**加密**

Adobe Campaign使用安全連線 (HTTPS) 存取您的 Microsoft Azure Blob 儲存帳戶。

**帳戶金鑰**

設定外部帳戶時，您必須使用 Azure 入口網站中可用的其中一個 **[!UICONTROL Account key]**。有關在何處查找帳戶密鑰的詳細資訊，請參閱本[頁面](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string)。

**最佳化檔案傳輸速度**

**[!UICONTROL Concurrency]** 選項可讓您微調檔案傳輸的速度。它表示用於執行檔案傳輸的執行緒數目。每個執行緒都將從 blob 下載約 1MB 的一部分。然後，它們將會排入佇列以寫入磁碟。請注意，增加執行緒數目也會增加應用程式在檔案傳輸期間使用的資源的負載。

完成檔案傳輸後，您可以在工作流程記錄檔中尋找效能度量。

**重試次數**

根據預設，Azure Blob 的檔案傳輸最多可重試 4 次。如果Azure儲存服務傳回錯誤碼，例如 503（伺服器忙碌）或 500（作業逾時），這表示您的儲存帳戶可能接近或超過擴充能力。當使用新帳戶或執行測試時，可能會發生此情況。

如果錯誤仍然存在，您可以在進階功能表 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]** 下建立選項，以增加重試次數。

如果實施，則必須按下述方式建立選項：

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
