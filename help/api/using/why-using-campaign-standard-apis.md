---
title: 為何選擇 Campaign Standard API?
description: 瞭解有關Campaign StandardAPI及其使用原因的更多資訊。
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

Adobe Campaign Standard公司提供的API使現有系統能夠與市場活動平台整合，以即時解決現實世界的問題。

註冊或選擇退出頁面等公共網站需要連接到後端系統以儲存配置檔案資訊。 像Adobe Campaign這樣的後端系統具有將配置檔案資料導入並對其執行自定義操作的靈活性和能力。

以下是一些示例：

* 潛在客戶線上註冊。
* 現有客戶概況和營銷溝通偏好管理。
* 基於事件的事務性通信觸發 — 訂單確認、預訂行程、密碼重置等。
* 甚至是購物車放棄的電子郵件通信。

註冊登錄頁為客戶或潛在客戶註冊其姓名和電子郵件地址提供了一種方法。 一旦Campaign Standard獲取了個人資料資訊和偏好，它就可以根據用戶的興趣發送個性化消息。

它們是使用以下元素構建的：

1. 具有市場活動API偵聽器的註冊表。

   ![替代文字](assets/apis_uc1.png)

1. 要基於複選框執行的自定義操作。 選擇「電子郵件特別優惠」的客戶將收到與正常註冊過程相比具有禮品券的其他自定義郵件。

   ![替代文字](assets/apis_uc2.png)

1. 配置檔案在按一下電子郵件中的「更新詳細資訊」連結後，可能會更改其詳細資訊。 這會將配置檔案帶到「更新您的配置檔案和首選項詳細資訊」頁。 要執行該操作，配置檔案詳細資訊(Pkey)將傳遞到市場活動伺服器，並檢索和顯示配置檔案。 配置檔案按一下「更新」按鈕後，資訊將更新到系統中(通過PATCH命令)。

   ![替代文字](assets/apis_uc3.png)

您可以使用一組請求來幫助您熟悉Campaign StandardAPI請求。 此JSON格式的集合提供了表示常用案例的預設計API請求。

以下步驟描述了用於導入和使用集合在Campaign Standard資料庫中建立配置檔案的逐步使用案例。

>[!NOTE]
>
>我們的例子是Postman。 但是，您可以自由使用您最喜愛的REST客戶端。

1. 通過按一下下載JSON集合 [這裡](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip)。

1. 開啟Postman，然後選擇 **檔案** / **導入** 的子菜單。

1. 將下載的檔案拖放到窗口中。 預設計的API請求顯示，可供使用。

   ![替代文字](assets/postman_collection.png)

1. 選擇 **建立配置檔案** 請求，然後更新POST請求和 **標題** 頁籤，&lt;organization>。 &lt;api_key>。 &lt;access_token>)。 如需詳細資訊，請參閱[本章節](../../api/using/setting-up-api-access.md)。

   ![替代文字](assets/postman_uc1.png)

1. 填寫 **身體** 的子菜單。 **發送** 按鈕

   ![替代文字](assets/postman_uc2.png)

1. 建立對象後，主鍵(PKey)與其關聯。 它在請求響應以及其他屬性中可見。

   ![替代文字](assets/postman_uc3.png)

1. 開啟Campaign Standard實例，然後檢查是否建立了配置檔案以及負載中的所有資訊。

   ![替代文字](assets/postman_uc4.png)
