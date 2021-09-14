---
title: 匯入最佳實務
description: 進一步了解將資料匯入資料庫時應遵循的最佳實務。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
exl-id: bb651b91-145f-4e87-92dd-a8b04662e380
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 2%

---

# 匯入最佳實務 {#import-best-practices}

>[!CAUTION]
>
>使用此功能時，請記得您的Adobe Campaign合約所規定的SFTP儲存空間、資料庫儲存空間和作用中設定檔限制。

謹慎並遵循以下所述的幾個簡單規則，將有助於確保資料庫內的資料一致性，並避免在資料庫更新或資料匯出期間出現常見錯誤。

## 使用匯入範本 {#using-import-templates}

大部分的匯入工作流程應包含下列活動：**[!UICONTROL Load file]**、**[!UICONTROL Reconciliation]**、**[!UICONTROL Segmentation]**、**[!UICONTROL Deduplication]**、**[!UICONTROL Update data]**。

使用匯入範本可讓您非常方便準備類似的匯入，並確保資料庫內的資料一致性。

在許多專案中，匯入是在沒有&#x200B;**[!UICONTROL Deduplication]**&#x200B;活動的情況下建置，因為專案中使用的檔案沒有重複項目。 有時會從匯入不同的檔案中出現重複項目。 因此，去重複化是困難的。 因此，重複資料刪除步驟是所有匯入工作流程中的妥善考量。

不要基於以下假設：傳入的資料是一致且正確的，或者IT部門或Adobe Campaign主管將負責處理。 在專案期間，請牢記資料清理。 匯入資料時，請刪除重複項目、調解及維護一致性。

[示例中提供了為導入資料而設計的通用工作流模板的示例：匯入工作流程範本](../../automating/using/creating-import-workflow-templates.md)區段。

>[!NOTE]
>
>您也可以使用[匯入範本](../../automating/using/importing-data-with-import-templates.md)。 它們是由管理員定義的工作流模板，激活後僅提供指定包含要導入的資料的檔案的可能性。

**相關主題：**

* [載入檔案活動](../../automating/using/load-file.md)
* [調解活動](../../automating/using/reconciliation.md)
* [細分活動](../../automating/using/segmentation.md)
* [重複資料刪除活動](../../automating/using/deduplication.md)
* [更新資料活動](../../automating/using/update-data.md)

## 使用平面檔案格式 {#using-flat-file-formats}

匯入的最有效格式是平面檔案。 可在資料庫級別以批量模式導入普通檔案。

例如：

* 分隔符：制表符或分號
* 帶標題的第一行
* 無字串分隔符
* 日期格式：YYYY/MM/DD HH:mm:SS

要匯入的檔案範例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## 使用壓縮 {#using-compression}

盡可能使用壓縮檔案進行匯入和匯出。 預設支援GZIP。 您可以分別在&#x200B;**[!UICONTROL Load file]**&#x200B;和&#x200B;**[!UICONTROL Extract file]**&#x200B;工作流程活動中，在匯入檔案時新增預處理，或在擷取資料時新增後處理。

**相關主題：**

* [載入檔案活動](../../automating/using/load-file.md)
* [擷取檔案活動](../../automating/using/extract-file.md)

## 在增量模式下導入 {#importing-in-delta-mode}

常規導入必須在增量模式下完成。 這表示每次只會傳送已修改或新資料至Adobe Campaign，而非整個表格。

完整匯入應僅用於初始載入。

## 維護一致性 {#maintaining-consistency}

若要維持Adobe Campaign資料庫中的資料一致性，請遵循下列原則：

* 如果匯入的資料符合Adobe Campaign中的參考表格，則應在工作流程中與該表格調解。 不應拒絕不符合的記錄。
* 確保匯入的資料始終為&#x200B;**&quot;normalized&quot;**（電子郵件、電話號碼、直接郵件地址），並且此標準化是可靠的，且多年內不會更改。 若非如此，某些重複項目可能會出現在資料庫中，而由於Adobe Campaign不提供執行「模糊」比對的工具，因此管理和移除這些項目將非常困難。
* 交易式資料應具有調解金鑰，並與現有資料調解，以避免建立重複項目。
* **依序匯入相關檔案**。如果匯入由多個彼此相依的檔案組成，工作流程應確定檔案的匯入順序正確。 檔案失敗時，不會匯入其他檔案。
* **匯入資料時，請刪除重複項目**、調解及維護一致性。
