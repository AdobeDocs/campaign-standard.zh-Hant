---
title: 配置Adobe IO for Microsoft Dynamics 365整合
description: 瞭解如何設定Adobe IO for Microsoft Dynamics 365整合。
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4e05dafb087c43a13c60d6bb2f54d0e44455ea8d

---


# 配置Adobe IO for Microsoft Dynamics 365整合

在跨通道通訊中啟用您的CRM資料：瞭解布建後所需的步驟，以建立Microsoft Dynamics 365的新整合。

## 概觀

Adobe Campaign Standard - Microsoft Dynamics 365整合在本頁 [中說明](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

在本文中執行布建後步驟之前，我們假定您已布建，並擁有組織「促銷活動標準」例項的管理員存取權。  如果未發生此情況，則您需要聯絡Adobe客戶服務以完成促銷活動布建。

>[!CAUTION]
>
>管理員需要執行下列步驟。

## 配置

您必須設定API存取權，並設定Unifi的新整合。

設定是在Adobe IO中完成：您需要為Unifi建立新的整合，如此影片中所示：

>[!VIDEO](https://video.tv.adobe.com/v/27308)

### 建立新整合

若要達成此目的，請依照下列程式：

1. 導覽至 [Adobe IO Console](https://console.adobe.io/home#) ，然後從左上角的下拉式選單中選取您的Adobe IMS組織ID（請參閱下方）。

然後按一下 **[!UICONTROL New Integration]** 右上角的。

>[!NOTE]
>
>如果這是貴組織的首次整合，則頁面 **[!UICONTROL New Integration]** 的按鈕可能位於頁面中央。

1. 選擇 **[!UICONTROL Access an API]** 並按一下 **[!UICONTROL Continue]**。

1. 從區 _段中選取Adobe Campaign_ , **[!UICONTROL Experience Cloud]** 然後按一下 **[!UICONTROL Continue]**。

1. 產生憑證和金鑰。

**適用於MacOs和Linux平台**

開啟終端應用程式並執行以下命令：

```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**針對Windows平台**

* 下載openssl用戶端以產生公用憑證(例如 [Openssl windows用戶端](https://bintray.com/vszakats/generic/download_file?file_path=openssl-1.1.1-win64-mingw.zip))

* 從zip檔案解壓縮資料夾

* 開啟命令行提示並執行以下命令。

將 `<containing folder path>` 下面替換為解壓縮資料夾的路徑(例如C:\Users\labuser\Downloads\openssl-1.1.1-win64-mingw\openssl-1.1.1-win64-mingw):

```
set OPENSSL_CONF=<containing folder path>/openssl.cnf
 
cd <containing folder path>/
 
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**適用於所有平台**

依照提示完成認證要求：

```
Generating a 2048 bit RSA private key
 
.................+++
 
.......................................+++
 
writing new private key to 'private.key'
 
-----
 
You are about to be asked to enter information that will be incorporated
 
into your certificate request.
 
What you are about to enter is what is called a Distinguished Name or a DN.
 
There are quite a few fields but you can leave some blank
 
For some fields there will be a default value,
 
If you enter '.', the field will be left blank.
 
-----
```

輸入資訊後，將產生兩個檔案： **[!UICONTROL certificate_pub.crt]** 和 **[!UICONTROL private.key]**。

* **[!UICONTROL certificate_pub.crt]** 將於365天後到期。 您可以變更上述openssl命令中的天數值，以修改有效期，但定期旋轉憑證是很好的安全性實務。

* **[!UICONTROL certificate_pub.crt]** 將會用在下一個畫面中，以完成Adobe I/O Console的整合。

>[!NOTE]
>
> **[!UICONTROL private.key]** 將在Unifi的置備後步驟中稍後使用。

1. 返回Adobe I/O Console，並輸入整合的名稱和說明。

1. 上傳 **[!UICONTROL certificate_pub.crt]**

1. 選取標題中包含的產品設定檔：

   * 促銷活動例項的組織ID
   * **[!UICONTROL Administrators]**

範例： Campaign Standard - your-campaign-organizationID —— 管理員

按一下 **[!UICONTROL Create Integration]**。

![](assets/do-not-localize/MSdynACSIntegration-4B.png)

### 設定整合詳細資訊

1. Select **[!UICONTROL Continue to Integration Details]**

檢視整合詳細資訊。  當您執行Unifi布建後步驟時，需要回覆這些步驟。

![](assets/do-not-localize/MSdynACSIntegration-5.png)

1. 按一下標籤 **[!UICONTROL Services]** 並新增 **[!UICONTROL I/O Events]** 與 **[!UICONTROL I/O Management API]** 服務。  若要新增服務，請按一下選項按鈕，然後按 **[!UICONTROL Add service]**。  您將針對每項服務分別執行此動作。

當您完成服務時，您的服務應該會像下圖一樣顯示在最上方。 在產生JWT和存取Token時，您不需要完成a-部分。

![](assets/do-not-localize/MSdynACSIntegration-6.png)

促銷活動中的貼文布建現已完成。  繼續完成Microsoft [Dynamics 365的置備後步驟](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

**相關主題**

* [Adobe IO —— 服務帳戶整合](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [促銷活動標準- API存取設定](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campaign Standard - Dynamics 365整合](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
