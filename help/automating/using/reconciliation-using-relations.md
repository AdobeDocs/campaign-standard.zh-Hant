---
title: 使用關係進行資料協調
description: 下列範例示範使用檔案中的購買資料更新資料庫的工作流程。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# 使用關係進行資料協調 {#reconciliation-relations}

下列範例示範使用檔案中的購買資料更新資料庫的工作流程。 採購資料包含參考其他維度的資料元素，例如客戶電子郵件和產品代碼。

>[!NOTE]
>
>依預 **設** ，此范 **例中使用的Transactions** 和Products資源不存在於Adobe Campaign資料庫中。 因此，它們是使用「自訂資源」功 [能預先建立](../../developing/using/data-model-concepts.md) 的。 與已匯入檔案中的電子郵件地址以及產品相對應的描述檔會事先載入資料庫。

工作流程由下列活動組成：

![](assets/reconciliation_example1.png)

* 「 [載入檔案](../../automating/using/load-file.md) 」活動，可載入並偵測要匯入之檔案的資料。 匯入的檔案包含下列資料：

   * 交易日期
   * 用戶端電子郵件地址
   * 購買產品的代碼

   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* 一種 [協調活動](../../automating/using/reconciliation.md) ，用於將購買資料綁定到資料庫配置檔案以及產品。 因此，必須定義檔案資料與配置檔案表以及產品表之間的關係。 此配置在活動的頁籤中執 **[!UICONTROL Relations]** 行：

   * 與描述檔的 **關係**: 檔案的 **client** 欄會連結至Profiles維的 **email** (電子郵 **件)欄** 。
   * 與產品的 **關係**: 檔案的 **product** 欄會連結至Profiles維度的 **productCode** 欄 **** 位。
   欄會新增至傳入資料，以參考連結維度的外鍵。

   ![](assets/reconciliation_example3.png)

* 「更 [新資料](../../automating/using/update-data.md) 」活動允許您定義要使用導入資料更新的資料庫欄位。 由於資料已被標識為屬於前一活動中 **的「事務** 」維，因此，您可以在此處使用 **[!UICONTROL Directly using the targeting dimension]** 標識選項。

   使用自動偵測欄位更新的選項，會將先前活動中設定的連結（至描述檔和產品）新增至清單 **[!UICONTROL Fields to update]**。 您也必須確保與交易日期對應的欄位正確新增至此清單。

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)
