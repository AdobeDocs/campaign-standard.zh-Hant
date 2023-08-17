---
title: 測試您的觸發程式
description: 了解疑難排解秘訣，以協助您解決在搭配Adobe Campaign使用觸發程式時可能遇到的最常見問題。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# 測試您的觸發程式{#testing-your-triggers}

下列疑難排解提示可協助您解決搭配Adobe Campaign使用觸發器時可能遇到的最常見問題：

**功能是否啟用？**

若要檢查是否已啟動Triggers - Campaign整合，請按一下左上方的Adobe Campaign標誌，然後選取 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. 您應該會看到 **[!UICONTROL Experience Cloud Triggers]** 個專案。

如果您看到這個訊息，請繼續進行下一個步驟。

如果沒有，請連絡您的Adobe客戶主管或專業服務合作夥伴。 另請參閱 [啟動功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**嘗試建立觸發器**

請依照中所述的步驟操作 [在Campaign中建立對應的觸發程式](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 以建立觸發器。

如果觸發器已建立，請繼續進行下一個步驟。 如果沒有，則表示觸發端點連線失敗。 檢查是否在Experience Cloud （啟用服務）中布建觸發程式。 若非如此，請聯絡您的Adobe客戶主管或專業服務合作夥伴。 需要下列資訊：

* Marketing Cloud公司名稱
* 組織 ID
* Analytics登入公司(可以與Marketing Cloud公司名稱相同)

**嘗試發佈觸發程式**

請依照中所述的步驟操作 [在Campaign中建立對應的觸發程式](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 以發佈觸發器。

如果發佈成功，請繼續進行下一個步驟。 如果沒有，請聯絡Adobe以重新啟動您的執行個體，然後再試一次。

**從網站產生觸發程式**

請依照中所述的步驟操作 [編輯異動訊息範本](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) 以編輯及發佈交易式範本。 接著，測試從網站產生觸發程式。

如果Analytics收到觸發程式，請繼續進行下一個步驟。 如果沒有，請核取下列專案：

* 已為Analytics啟用觸發程式
* DTM已啟用MCID和Analytics所使用的網站
* 建立觸發程式時會使用正確的Analytics報表套裝

**Campaign是否收到觸發程式？**

如果沒有，則檢查是否從管道收到觸發程式。

如果沒有，請聯絡Adobe以檢查配管端點的配置。

如果是，請遵循下列准則：

* 檢查Campaign資料來源中的調解ID型別。
* CustomerId資料來源是透過客戶屬性所建立。
* 檢查資料來源識別碼。
* 請求Adobe在資料來源設定後重新啟動Campaign執行個體。
* 檢查觸發程式報告中的觸發程式剖析問題。

**觸發程式是否處於擱置狀態？**

如果沒有，請繼續進行下一個步驟。 如果是，請遵循下列准則：

* 檢查交易式範本是否已發佈。
* 檢查設定檔是否不在封鎖清單上。
* 檢查型別規則的套用。
* 檢查異動訊息的記錄。

**訊息是否有效？**

如果訊息無效，請檢查下列專案：

* 對於標籤為無效的觸發擴充個人化欄位，請從關聯的eventCusResource集合驗證交易式範本。
* 驗證訊息格式
