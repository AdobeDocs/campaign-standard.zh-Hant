---
solution: Campaign Standard
product: campaign
title: 測試您的觸發程式
description: null
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 2%

---


# 測試您的觸發程式{#testing-your-triggers}

下列疑難排解提示將協助您解決搭配使用Adobe Campaign時最常遇到的問題：

**功能是否已啟動？**

若要檢查「觸發程式——促銷活動」整合是否已啟動，請按一下左上角的Adobe Campaign標誌，然後選取 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**。 您應該看到 **[!UICONTROL Experience Cloud Triggers]** 項目。

如果您看到，請繼續下一步。

如果沒有，請聯絡您的Adobe銷售代表或專業服務合作夥伴。 請參 [閱啟用功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**嘗試建立觸發器**

請依照在Campaign中建立 [映射觸發器中所述的步驟](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) ，建立觸發器。

如果已建立觸發器，請繼續下一步。 否則，表示觸發器端點連接失敗。 檢查Experience Cloud（啟動服務）中是否已布建觸發器。 如果沒有，請連絡您的Adobe客戶主管或專業服務合作夥伴。 需要下列資訊：

* Marketing Cloud公司名稱
* IMS 組織 ID
* Analytics登入公司（可與Marketing Cloud公司名稱相同）

**嘗試發佈觸發器**

請依照在Campaign中建立 [映射觸發器中所述的步驟](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) ，發佈觸發器。

如果發佈成功，請繼續下一步。 如果沒有，請連絡Adobe以重新啟動您的例項，然後再試一次。

**從網站產生觸發器**

按照編輯事務性消息 [模板中介紹的步驟](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) ，編輯和發佈事務性模板。 然後，測試從網站產生觸發器的程式。

如果Analytics收到觸發器，請繼續下一步驟。 否則，請檢查以下項目：

* 已為Analytics啟用觸發器
* 使用MCID和Analytics的網站已在DTM中啟用
* 建立觸發器時會使用正確的Analytics報表套裝

**促銷活動是否收到觸發器？**

否則，檢查是否從管線接收到觸發器。

如果沒有，請聯絡Adobe以檢查管線端點的設定。

如果是，請遵循下列准則：

* 檢查促銷活動資料來源中的協調ID類型。
* CustomerId資料來源是透過「客戶屬性」建立。
* 檢查資料來源ID。
* 要求Adobe在資料來源設定後重新啟動Campaign例項。
* 檢查觸發器報告中的觸發器解析問題。

**觸發器是否處於待定狀態？**

否則，請繼續下一步。 如果是，請遵循下列准則：

* 檢查交易範本是否已發佈。
* 檢查配置式是否不在denylist中。
* 檢查應用類型學規則。
* 檢查事務性消息的日誌。

**訊息有效嗎？**

如果訊息無效，請檢查下列項目：

* 若要觸發標籤為無效的擴充個人化欄位，請驗證關聯eventCusResource集合中的交易範本。
* 驗證消息格式

