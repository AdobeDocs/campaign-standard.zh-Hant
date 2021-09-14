---
title: 測試您的觸發程式
description: 了解疑難排解秘訣，協助您解決搭配Adobe Campaign使用觸發器時最常遇到的問題。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 1%

---

# 測試您的觸發程式{#testing-your-triggers}

下列疑難排解提示可協助您解決搭配Adobe Campaign使用觸發器時最常遇到的問題：

**是否激活了功能？**

若要檢查「觸發器 — 促銷活動」整合是否已啟用，請按一下左上角的Adobe Campaign標誌，然後選取&#x200B;**[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**。 您應該會看到&#x200B;**[!UICONTROL Experience Cloud Triggers]**&#x200B;項目。

如果您看到，請繼續下一步。

如果沒有，請聯絡您的Adobe客戶經理或專業服務合作夥伴。 請參閱[啟用功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**嘗試建立觸發器**

請依照[在Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)中建立對應觸發程式中所述的步驟，建立觸發程式。

如果已建立觸發程式，請前往下一個步驟。 否則，表示觸發端連接失敗。 檢查Triggers是否布建在Experience Cloud（啟動服務）中。 如果沒有，請聯絡您的Adobe客戶經理或專業服務合作夥伴。 需要下列資訊：

* Marketing Cloud公司名稱
* IMS 組織 ID
* Analytics登入公司(可以與Marketing Cloud公司名稱相同)

**嘗試發佈觸發器**

請依照[在Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign)中建立對應觸發程式中所述的步驟，發佈觸發程式。

如果發佈成功，請繼續執行下一個步驟。 否則，請聯繫Adobe以重新啟動您的執行個體，然後重試。

**從網站產生觸發程式**

請依照[編輯交易式訊息範本](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template)中所述步驟，編輯和發佈交易式範本。 接著，測試從網站產生觸發器的程式。

如果Analytics收到觸發器，請繼續執行下一個步驟。 否則，請檢查下列項目：

* 已針對Analytics啟用觸發器
* 使用MCID和Analytics的網站已在DTM中啟用
* 建立觸發器時會使用正確的Analytics報表套裝

**Campaign是否收到觸發程式？**

若未收到，則檢查是否從管道接收到觸發器。

否則，請與Adobe聯繫以檢查管線端點的配置。

如果是，請遵循下列准則：

* 在Campaign資料來源中檢查調解ID類型。
* CustomerId資料源是通過客戶屬性建立的。
* 檢查資料源ID。
* 在資料來源設定後，要求Adobe重新啟動Campaign執行個體。
* 檢查觸發器報告中的觸發器解析問題。

**觸發器是否處於掛起狀態？**

如果沒有，請繼續執行下一個步驟。 如果是，請遵循下列准則：

* 檢查交易式範本是否已發佈。
* 檢查設定檔是否未列在封鎖清單中。
* 檢查類型規則的應用。
* 檢查交易式訊息的記錄。

**訊息有效嗎？**

如果消息無效，請檢查以下項：

* 對於標示為無效的觸發擴充個人化欄位，請驗證關聯eventCusResource集合中的交易式範本。
* 驗證訊息格式
