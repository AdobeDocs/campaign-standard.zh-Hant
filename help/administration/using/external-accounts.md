---
title: 外部帳戶
seo-title: 外部帳戶
description: 外部帳戶
seo-description: 設定外部帳戶以使用外部系統(例如SFTP伺服器)設定連線。
page-status-flag: 從未啓動
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 應用程式設定
discoiquuid: d5c6a3d4-f767-46c1-a8 c0-3b9 dc52 dcua8
internal: n
snippet: y
context-tags: extAccount，main；extAccount，overview
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# External accounts{#external-accounts}

外部帳戶可讓您設定並測試對Adobe Campaign外部伺服器的存取權。

這些外部帳戶可用於促銷活動工作流程，以存取和管理資料。

您可以設定下列類型的外部帳戶：

* SFTP。For more on this, refer to [this section](../../administration/using/external-accounts.md#sftp-external-account).
* Amazon Storage Service(S3)。For more on this, refer to [this section](../../administration/using/external-accounts.md#amazon-s3-external-account).
* Adobe Experience Manager。For more on this, refer to [this section](../../administration/using/external-accounts.md#adobe-experience-manager-external-account).
* Adobe Analytics。For more on this, refer to [this section](../../integrating/using/configure-campaign-analytics-integration.md).
* Google ReCAPTCHA.For more on this, refer to [this section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

>[!NOTE]
>
>Adobe在產品布建過程中會使用其他類型的外部帳戶。在Campaign Standard17.9版本中，FTP外部帳戶仍然可以定義，但無法用於新的工作流程活動中。如果您已設定連線，則仍會啓用連線。

External accounts can be configured by administrators under the **[!UICONTROL Administration > Application settings > External accounts]** menu.

## Creating an external account {#creating-an-external-account}

Adobe Campaign隨附一組預先定義的外部帳戶。若要使用外部系統設定連線，例如檔案傳輸使用的FTP伺服器，您可以建立自己的外部帳戶。

技術流程會使用外部帳戶，例如技術工作流程或促銷活動工作流程。在工作流程中設定檔案傳輸或與任何其他應用程式(Adobe Target、Experience Manager等)交換檔案時，您需要選取外部帳戶。

1. Click the **[!UICONTROL Create]** button.
1. 輸入標籤。在工作流程中選取外部帳戶時，將會使用標籤和ID。
1. 選擇您要建立的帳戶類型。
1. 指定憑證、伺服器位址、連接埠號碼和索引鍵，以設定帳戶存取權限。

   必要資訊通常由您連線到的伺服器提供。

1. 儲存您的帳戶。

外部帳戶會建立並新增至帳戶清單。它現在可用於工作流程活動和傳送屬性中的資料/檔案傳輸或路由設定。

## SFTP external account {#sftp-external-account}

不同的外部帳戶類型需要指定不同的資訊。

對於SFTP外部帳戶，請提供下列詳細資訊：

* 伺服器位址。For example, **ftp.domain.com**.
* 連接埠號碼。****&#x200B;例如22。
* SFTP伺服器認證：帳戶名稱和密碼。

### Adobe hosted SFTP server recommendations {#adobe-hosted-sftp-server-recommendations}

管理檔案和資料時，這些檔案會儲存在Adobe提供的裝載SFTP伺服器上。此SFTP設為暫時儲存空間，可用來控制檔案的保留和刪除。

當未正確使用或監控時，此空間可快速填滿伺服器可用的實體空間，並造成嚴重的問題。這可能會導致平台資料遺失或損毀。

為避免發生此類問題，Adobe建議遵循下列最佳實務：

* 盡可能保留最低資料。
* 使用金鑰驗證以避免密碼過期。Supported formats are **OpenSSH** and **SSH2** only. 您必須提供公開金鑰給Adobe支援團隊，以便在促銷活動伺服器上上傳。
* 只需視需要保留資料。15天是最大時間限制。
* 使用工作流程可正確刪除資料(管理使用資料的工作流程的保留率)。
* 使用SFTP上傳以及工作流程中的批次處理。
* 處理錯誤/例外狀況。
* 有時候，登入SFTP可直接檢查位於何處。
* 請記住，SFTP磁碟管理主要是您的責任。

此外，請注意，您嘗試啓動SFTP連線的公用IP必須列在促銷活動例項上。Whitelisting of IP addresses can be requested via a [support ticket](https://support.neolane.net), along with providing the public key to use for authentication.

可從「控制台」管理SFTP伺服器。For more information, refer to the [Control Panel documentation](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html).

>[!NOTE]
>
>「控制台」僅適用於AWS代管客戶的管理員使用者。
Check if your instance is hosted on AWS [here](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID).

## Amazon S3 external account {#amazon-s3-external-account}

Amazon S伺服器欄位應填入如下：

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

To store your file in S3 encrypted mode, check the **[!UICONTROL Keep files in S3 encrypted]** box.

![](assets/external_accounts_2.png)

必要資訊通常由您連線到的伺服器提供。

Specify the **[!UICONTROL AWS Region]** associated to your endpoint. You can check the supported regions and signature versions in the official [Amazon S3 documentation](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) .

### Amazon S3 account recommendations {#amazon-s3-account-recommendations}

為了協助您設定Amazon S帳戶，我們建議您遵循下列建議：

* 建立嚴格的貯體原則以限制對S個貯體的存取。建立貯體時可以設定貯體原則。For more information, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* While creating an external account, enable the encryption to store sensitive data in the S3 bucket by checking the **[!UICONTROL Keep files in S3 encrypted]** box.
* 授予貯體權限，以指定誰可以存取儲存貯體中的物件。For more information on bucket permission, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)

## Adobe Experience Manager external account {#adobe-experience-manager-external-account}

在整合Campaign與Experience Manager時，會使用Adobe Experience Manager外部帳戶。

[本文件](../../integrating/using/about-campaign-integrations.md)提供有關此項整合的程序與需求。

當您設定此新外部帳戶時，必須提供下列詳細資訊：

* 伺服器：輸入Adobe Experience Manager伺服器的URL。For example, **http://aem.domain.com:4502**.
* AEM帳戶認證：使用將存取Adobe Experience Manager實例的帳戶。它應該是Experience Manager中促銷活動遠端群組的一部分。

## Google reCAPTCHA external account {#google-recaptcha-external-account}

>[!NOTE]
>
>Google reCAPTCHA設定需要Google帳戶。

Google ReCAPTCHA機制可讓您保護登陸頁面，避免因機器人造成的垃圾郵件和濫用。這對您的客戶不具妨礙，因為它不需要任何互動，並且是根據與網站的互動。To register your site, refer to this [page](https://www.google.com/recaptcha/admin/create). 您必須選擇V3reCAPTCHA類型。

若要將Google ReCAPTCHA V新增至您的登陸頁面，您必須先在外部帳戶中進行設定。For more information on how to add it to your landing page, refer to this [section](../../channels/using/designing-a-landing-page.md#setting-google-recaptcha).

對於Google reCAPTCHA V外部帳戶，請提供下列詳細資訊：

* A **[!UICONTROL Label]** and **[!UICONTROL ID]** of your external account
* **[!UICONTROL Type]**：Google ReCAPTCHA
* Your **[!UICONTROL Site key]** and **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** between 0 and 1

   **[!UICONTROL Threshold]** 0.0值表示機器人可能是機器人和1.0的良好互動。根據預設，您可以使用0.5的臨界值。

![](assets/external_accounts_3.png)

