---
title: 測試觸發器
seo-title: 測試觸發器
description: 測試觸發器
seo-description: null
page-status-flag: 從未啓動
uuid: b3a6667d-e843-4ad6-817e-d91542 b5 f2 e2
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 整合
content-type: reference
topic-tags: 使用促銷活動與觸發器
discoiquuid: f67e69f2-09fb-4f33-b2 c3-c67 a060743 e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Testing your triggers{#testing-your-triggers}

下列疑難排解提示可協助您解決使用Adobe Campaign時可能遇到的最常見問題：

**功能是否已啓動？**

To check if the Triggers - Campaign integration is activated, click the Adobe Campaign logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. You should see the **[!UICONTROL Experience Cloud Triggers]** item.

如果您看到，請移至下一個步驟。

如果沒有，請聯絡您的Adobe銷售代表或專業服務合作夥伴。See [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**嘗試建立觸發器**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to create a trigger.

如果觸發觸發器，請移至下一個步驟。如果沒有，表示觸發端點連線失敗。檢查Experience Cloud(啓動服務)是否布建觸發器。如果沒有，請聯絡您的Adobe銷售代表或專業服務合作夥伴。需要下列資訊：

* Marketing Cloud公司名稱
* IMS OG ID
* Analytics登入公司(可與Marketing Cloud公司名稱相同)

**嘗試發佈觸發器**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to publish the trigger.

如果出版物成功，請移至下一個步驟。如果沒有，請聯絡Adobe以重新啓動您的執行個體，然後再試一次。

**從網站產生觸發器**

Follow the steps described in [Editing the transactional message template](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) to edit and publish the transactional template. 然後，從網站測試產生觸發器。

如果Analytics收到觸發器，請移至下一個步驟。如果沒有，請檢查下列項目：

* Analytics啓用觸發器
* 使用MCID和Analytics的網站已在DTM中啓用
* 建立觸發器時使用正確的Analytics報表套裝

**促銷活動會收到觸發器嗎？**

如果沒有，請檢查是否從管線接收觸發器。

如果沒有，請聯絡Adobe以檢查管線端點的組態。

如果是，請遵循下列指南行：

* 查看促銷活動資料來源中的協調ID類型。
* CustomerId DataSource是透過客戶屬性建立的。
* 檢查資料來源ID。
* 要求Adobe重新啓動DataSource設定後的促銷活動例項。
* 勾選觸發報表中的觸發剖析問題。

**觸發器是否處於擱置狀態？**

如果沒有，請移至下一個步驟。如果是，請遵循下列指南行：

* 檢查交易範本是否已發佈。
* 如果促銷活動啓用proprestyScore臨界值，請從管線檢查觸發器的傾向分數。
* 檢查描述檔未列入黑名單。
* 檢查打字規則的應用程式。
* 查看交易訊息的記錄檔。

**訊息有效嗎？**

如果訊息無效，請檢查下列項目：

* 若要觸發標示為無效的個人化欄位，請從關聯的eventResource收集驗證交易範本。
* 驗證訊息格式

