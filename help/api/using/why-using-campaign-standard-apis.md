---
title: 為何選擇 Campaign Standard API?
description: 深入了解Campaign StandardAPI及其使用原因。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: ef045e5d-cd02-44a0-9a1e-d468483a38d9
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 3%

---

# 為何使用 Campaign Standard API {#why-using-campaign-standard-apis}

Adobe Campaign Standard提供API，可讓現有系統與Campaign平台整合，以即時解決實際問題。

註冊或退出頁面等公開網站需要連線至後端系統，以儲存設定檔資訊。 像Adobe Campaign這樣的後端系統具有將設定檔資料內嵌至其中，以及對其執行自訂作業的彈性和功能。

以下是一些範例：

* 潛在客戶線上註冊。
* 現有客戶設定檔和行銷通訊偏好管理。
* 以事件為基礎的交易式通訊觸發 — 訂單確認、預訂行程、密碼重設等。
* 甚至購物車放棄電子郵件通訊。

註冊登錄頁面可讓客戶或潛在客戶註冊其名稱和電子郵件地址。 一旦Campaign Standard擷取設定檔資訊和偏好設定後，就可以根據人員的興趣傳送個人化訊息。

這些量度是以下元素建置：

1. 具有促銷活動API接聽程式的註冊表單。

   ![替代文字](assets/apis_uc1.png)

1. 要根據核取方塊採取的自訂動作。 與一般註冊程式相比，選擇「電子郵件特別優惠方案」的客戶會收到不同的自訂郵件，內含禮品券。

   ![替代文字](assets/apis_uc2.png)

1. 按一下電子郵件中的「更新詳細資料」連結後，設定檔可能會變更其詳細資料。 這會將設定檔導向「更新您的設定檔和偏好設定詳細資訊」頁面。 若要執行操作，會將設定檔詳細資訊(Pkey)傳遞至Campaign伺服器，並擷取及呈現設定檔。 設定檔按一下「更新」按鈕後，資訊就會更新至系統(透過PATCH命令)。

   ![替代文字](assets/apis_uc3.png)

此請求集合可協助您熟悉Campaign StandardAPI請求。 此JSON格式集合提供代表常見使用案例的預先設計API要求。

下列步驟說明逐步使用案例，以匯入和使用集合，在Campaign Standard資料庫中建立設定檔。

>[!NOTE]
>
>我們的範例使用Postman。 不過，您可以隨意使用您最喜愛的REST客戶端。

1. 按一下以下載JSON集合 [此處](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. 開啟Postman，然後選取 **檔案** / **匯入** 功能表。

1. 將下載的檔案拖放至視窗中。 預先設計的API請求隨即顯示，可供使用。

   ![替代文字](assets/postman_collection.png)

1. 選取 **建立設定檔** 請求，然後更新POST請求和 **標題** 頁簽，以及您自己的資訊(&lt;organization>, &lt;api_key>, &lt;access_token>)。 如需詳細資訊，請參閱[本章節](../../api/using/setting-up-api-access.md)。

   ![替代文字](assets/postman_uc1.png)

1. 填入 **主體** 索引標籤，其中包含您要新增至新設定檔的資訊，然後按一下 **傳送** 按鈕執行請求。

   ![替代文字](assets/postman_uc2.png)

1. 建立對象後，主鍵(PKey)便與其關聯。 它會顯示在請求回應中，以及其他屬性中。

   ![替代文字](assets/postman_uc3.png)

1. 開啟您的Campaign Standard例項，然後檢查是否已建立設定檔以及裝載中的所有資訊。

   ![替代文字](assets/postman_uc4.png)
