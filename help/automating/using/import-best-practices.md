---
title: 匯入最佳實務
description: 進一步瞭解將資料匯入資料庫時要遵循的最佳實務。
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
source-git-commit: b4d0aa1a9f116f022890d5eccd87730a7a513103
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---


# 匯入最佳實務 {#import-best-practices}

謹慎並遵循下面詳述的幾個簡單規則，將有助於確保資料庫內的資料一致性，並避免在資料庫更新或資料匯出期間發生常見錯誤。

## 使用匯入範本 {#using-import-templates}

大部分的匯入工作流程應包含下列活動： **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**

使用匯入範本可讓您非常方便地準備類似的匯入，並確保資料庫中的資料一致性。

在許多專案中，匯入建置時不 **[!UICONTROL Deduplication]** 會執行任何活動，因為專案中使用的檔案不會重複。 有時會從匯入不同的檔案中顯示重複項目。 因此，消除重複就很困難。 因此，重複資料消除步驟是所有導入工作流中的良好預防措施。

切勿假設傳入的資料是一致且正確的，或IT部門或Adobe Campaign主管負責處理。 在專案期間，請牢記資料清理。 在匯入資料時，可以消除重複資料、進行協調並維持一致性。

「示例：」( [Example:)中提供了為導入資料而設計的通用工作流模板的示例。 「導入工作流模板](../../automating/using/creating-import-workflow-templates.md) 」部分。

>[!NOTE]
>
>您也可以使用 [匯入範本](../../automating/using/importing-data-with-import-templates.md)。 它們是由管理員定義的工作流模板，一旦激活，則僅提供指定包含要導入的資料的檔案的可能性。

**相關主題：**

* [載入檔案活動](../../automating/using/load-file.md)
* [協調活動](../../automating/using/reconciliation.md)
* [區段活動](../../automating/using/segmentation.md)
* [重複資料消除活動](../../automating/using/deduplication.md)
* [更新資料活動](../../automating/using/update-data.md)

## 使用平面檔案格式 {#using-flat-file-formats}

匯入時最有效的格式是平面檔案。 平面檔案可以在資料庫級別以批量模式導入。

例如：

* 分隔符號： 制表符或分號
* 首行含標題
* 無字串分隔字元
* 日期格式： YYYY/MM/DD HH:mm:SS

要導入的檔案示例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## 使用壓縮 {#using-compression}

盡可能使用壓縮檔案進行匯入和匯出。 預設支援GZIP。 您可以分別在匯入檔案或擷取資料時新增前置處理，在和工作流程活動 **[!UICONTROL Load file]** 中加 **[!UICONTROL Extract file]** 入後置處理。

**相關主題：**

* [載入檔案活動](../../automating/using/load-file.md)
* [擷取檔案活動](../../automating/using/extract-file.md)

## 在增量模式中導入 {#importing-in-delta-mode}

常規導入必須在delta模式下完成。 這表示每次只會傳送已修改或新資料至Adobe Campaign，而非整個表格。

完整匯入應僅用於初始載入。

## 維護一致性 {#maintaining-consistency}

若要維持Adobe Campaign資料庫中的資料一致性，請遵循下列原則：

* 如果匯入的資料與Adobe Campaign中的參考表格相符，則應與工作流程中的該表格協調。 不應拒絕不符合的記錄。
* 確保匯入的資料一律「 **標準化」** （電子郵件、電話號碼、直效郵件位址），而且此標準化是可靠的，多年來不會變更。 如果不是這樣，有些復本可能會出現在資料庫中，而Adobe Campaign不提供進行「模糊」比對的工具，因此很難管理和移除它們。
* 事務性資料應具有協調密鑰，並與現有資料協調以避免建立重複資料。
* **依順序匯入相關檔案**。 如果匯入由多個彼此依存的檔案組成，工作流程應確保檔案的匯入順序正確。 檔案失敗時，不會導入其他檔案。
* **匯入資料**&#x200B;時，可以消除重複資料、進行協調並維持一致性。
