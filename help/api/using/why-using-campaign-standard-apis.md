---
title: 為何使用Campaign Standard API?
description: 進一步瞭解Campaign Standard API及其使用原因。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2b04a5efdde3153d3ede0ad8bc4f56cd4a5fa1df
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---


# Why use Campaign Standard APIs {#why-using-campaign-standard-apis}

Adobe Campaign Standard提供API，可讓現有系統與ACS平台整合，以即時解決實際問題。

註冊或選擇退出頁面等公開網站需要連線至後端系統，以儲存設定檔資訊。 Adobe Campaign等後端系統具備將描述檔資料內嵌在其中並執行自訂作業的彈性和能力。

以下是一些範例：

* 潛在客戶線上註冊。
* 現有客戶個人檔案和行銷通訊偏好管理。
* 事件型交易通訊觸發——訂單確認、預訂行程、密碼重設等。
* 甚至購物車放棄電子郵件通訊。

註冊登陸頁面可讓客戶或潛在客戶註冊其姓名和電子郵件地址。 一旦Campaign Standard擷取了個人檔案資訊和偏好設定，就可以根據個人興趣傳送個人化訊息。

它們以下列元素建立：

1. 具有促銷活動API監聽器的註冊表單。

   ![alt text](assets/apis_uc1.png)

1. 要根據複選框執行的自定義操作。 與一般註冊程式相比，選擇「電子郵件特別優惠」的客戶會收到另一封自訂郵件，並附贈禮券。

   ![alt text](assets/apis_uc2.png)

1. 在按一下電子郵件中的「更新詳細資訊」連結後，描述檔可能會變更其詳細資訊。 這會將描述檔帶到「更新您的描述檔和偏好設定詳細資訊」頁面。 若要執行此作業，描述檔詳細資訊(Pkey)會傳遞至促銷活動伺服器，並擷取並呈現描述檔。 配置檔案按一下「更新」按鈕後，資訊將更新到系統中（通過PATCH命令）。

   ![alt text](assets/apis_uc3.png)

您可使用一系列請求，以協助您熟悉Campaign Standard API請求。 此JSON格式的系列提供預先設計的API要求，代表常用案例。

下列步驟說明在Campaign Standard資料庫中匯入並使用系列以建立描述檔的逐步使用案例。

>[!NOTE]
>
>我們的例子是郵遞員。 不過，您可以使用您最愛的REST客戶端。

1. 按一下這裡下載JSON [系列](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip)。

1. 開啟「郵遞員」，然後選取「 **檔案** /匯 **入」功能表** 。

1. 將下載的檔案拖放至視窗中。 預先設計的API要求會顯示，可供使用。

   ![alt text](assets/postman_collection.png)

1. 選擇「 **建立描述檔****** 」請求，然後使用您自己的資訊(&lt;ORGANIZATION>、&lt;API_KEY>、&lt;ACCESS_TOKEN>)更新「貼文」請求和「標題」標籤。 如需詳細資訊，請參閱[本區段](../../api/using/setting-up-api-access.md)。

   ![alt text](assets/postman_uc1.png)

1. 使用您要新 **增至新描述檔的資訊填入「內文** 」索引標籤，然後按一下「傳送」 **** 按鈕以執行請求。

   ![alt text](assets/postman_uc2.png)

1. 建立對象後，主鍵(PKey)與其關聯。 在響應中以及其他屬性中可見。

   ![alt text](assets/postman_uc3.png)

1. 開啟您的Campaign Standard例項，然後檢查描述檔是否已建立，並包含裝載的所有資訊。

   ![alt text](assets/postman_uc4.png)
