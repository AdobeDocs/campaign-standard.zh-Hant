---
title: 管理加密的資料
description: 瞭解如何管理加密資料。
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---


# 管理加密的資料 {#managing-encrypted-data}

在某些情況下，您要匯入促銷活動伺服器的資料可能需要加密，例如，如果包含PII資料。

若要匯入或匯出加密檔案，您必須先聯絡Adobe客戶服務，以便他們提供您的執行個體所需的加密／解密指令。

若要這麼做，請提交指示：

* 將 **在** 「促銷活動」介面中顯示的標籤，以使用命令。 例如「加密檔案」。
* 要安 **裝在** 實例上的命令。
例如，要使用PGP解密檔案，命令將是：

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

處理請求後，加密／解密命令將可在和活動 **[!UICONTROL Pre-processing stage]** 的欄位中 **[!UICONTROL Load file]** 使 **[!UICONTROL Extract file]** 用。 您可以使用這些檔案解密或加密要導入或導出的檔案。

![](assets/preprocessing-encryption.png)

**相關主題：**

* [載入檔案](../../automating/using/load-file.md)
* [擷取檔案](../../automating/using/extract-file.md)
