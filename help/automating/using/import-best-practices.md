---
title: 匯入最佳實務
description: 瞭解有關將資料導入資料庫時要遵循的最佳做法的更多資訊。
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
>在使用此功能時，請記住根據您的Adobe Campaign合同規定的SFTP儲存、資料庫儲存和活動配置檔案限制。

謹慎並遵循下面詳細介紹的幾個簡單規則將有助於確保資料庫中的資料一致性，並避免在資料庫更新或資料導出過程中出現常見錯誤。

## 使用導入模板 {#using-import-templates}

大多數導入工作流應包含以下活動： **[!UICONTROL Load file]**。 **[!UICONTROL Reconciliation]**。 **[!UICONTROL Segmentation]**。 **[!UICONTROL Deduplication]**。 **[!UICONTROL Update data]**。

使用導入模板可以非常方便地準備類似的導入，並確保資料庫中的資料一致性。

在許多項目中，進口是在沒有 **[!UICONTROL Deduplication]** 活動，因為項目中使用的檔案沒有重複項。 導入不同檔案時有時會出現重複項。 因此，重複資料消除很困難。 因此，重複資料消除步驟是所有導入工作流中的一個良好預防措施。

不要假設傳入的資料是一致和正確的，或者IT部門或Adobe Campaign主管會處理它。 在項目期間，應牢記資料清理。 在導入資料時執行重複資料消除、協調和維護一致性。

為導入資料而設計的通用工作流模板的示例在 [示例：導入工作流模板](../../automating/using/creating-import-workflow-templates.md) 的子菜單。

>[!NOTE]
>
>您還可以使用 [導入模板](../../automating/using/importing-data-with-import-templates.md)。 它們是由管理員定義的工作流模板，一旦激活，只能提供指定包含要導入資料的檔案的可能性。

**相關主題：**

* [載入檔案活動](../../automating/using/load-file.md)
* [協調活動](../../automating/using/reconciliation.md)
* [細分活動](../../automating/using/segmentation.md)
* [重複資料消除活動](../../automating/using/deduplication.md)
* [更新資料活動](../../automating/using/update-data.md)

## 使用平面檔案格式 {#using-flat-file-formats}

最有效的導入格式是平面檔案。 可以在資料庫級別以批量模式導入平面檔案。

例如：

* 分隔符：制表符或分號
* 第一行帶標題
* 無字串分隔符
* 日期格式：YYYY/MM/DD HH:mm:SS

要導入的檔案示例：

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## 使用壓縮 {#using-compression}

盡可能使用壓縮檔案進行導入和導出。 預設情況下支援GZIP。 在導入檔案時可添加預處理，在提取資料時可添加後處理，分別位於 **[!UICONTROL Load file]** 和 **[!UICONTROL Extract file]** 工作流活動。

**相關主題：**

* [載入檔案活動](../../automating/using/load-file.md)
* [提取檔案活動](../../automating/using/extract-file.md)

## 在增量模式下導入 {#importing-in-delta-mode}

常規導入必須在增量模式下完成。 這意味著每次只向Adobe Campaign發送修改的或新的資料，而不是整個表。

完全導入應僅用於初始載入。

## 維護一致性 {#maintaining-consistency}

為了保持Adobe Campaign資料庫的資料一致性，請遵循以下原則：

* 如果導入的資料與Adobe Campaign的引用表匹配，則應與工作流中的該表協調。 不匹配的記錄應被拒絕。
* 確保導入的資料始終 **&quot;規範化&quot;** （電子郵件、電話號碼、直接郵件地址），並且此正常化是可靠的，並且多年內不會更改。 如果不是這樣，資料庫中可能會出現一些重複項，而由於Adobe Campaign沒有提供進行「模糊」匹配的工具，因此很難管理和刪除這些重複項。
* 事務性資料應具有協調密鑰，並與現有資料協調以避免建立重複項。
* **按順序導入相關檔案**。 如果導入由多個相互依賴的檔案組成，則工作流應確保以正確的順序導入檔案。 檔案失敗時，不導入其他檔案。
* **重複資料消除**&#x200B;在導入資料時協調並維護一致性。
