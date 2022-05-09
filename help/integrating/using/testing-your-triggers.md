---
title: 測試您的觸發程式
description: 瞭解故障排除技巧，以幫助您解決在將觸發器與Adobe Campaign配合使用時可能遇到的最常見問題。
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

以下故障排除提示可幫助您解決在使用「觸發器」(Triggers withAdobe Campaign)時可能遇到的最常見問題：

**功能是否已激活？**

要檢查是否激活了「觸發器 — 市場活動整合」，請按一下左上角的Adobe Campaign徽標，然後選擇 **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**。 您應該看到 **[!UICONTROL Experience Cloud Triggers]** 的子菜單。

如果您看到它，請繼續下一步。

如果沒有，請與您的Adobe客戶主管或專業服務合作夥伴聯繫。 請參閱 [激活功能](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality)。

**嘗試建立觸發器**

按照中介紹的步驟操作 [在市場活動中建立映射觸發器](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 來建立觸發器。

如果建立了觸發器，請轉到下一步。 否則，表示觸發器端點連接失敗。 檢查是否在Experience Cloud（激活服務）中設定了觸發器。 如果沒有，請與您的Adobe客戶經理或專業服務合作夥伴聯繫。 需要以下資訊：

* Marketing Cloud公司名稱
* 組織ID
* 分析登錄公司(可與Marketing Cloud公司名稱相同)

**嘗試發佈觸發器**

按照中介紹的步驟操作 [在市場活動中建立映射觸發器](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) 以發佈觸發器。

如果發佈成功，請轉到下一步。 如果沒有，請與Adobe聯繫以重新啟動實例，然後重試。

**從網站生成觸發器**

按照中介紹的步驟操作 [編輯事務性消息模板](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) 編輯和發佈事務模板。 然後，test從網站生成觸發器。

如果Analytics接收到觸發器，請轉到下一步。 否則，檢查以下項目：

* 已為分析啟用觸發器
* 使用的網站MCID和分析在DTM中啟用
* 建立觸發器時使用正確的分析報告套件

**是市場活動接收的觸發器嗎？**

否則，檢查是否從管道接收到觸發器。

否則，接觸Adobe檢查管線端點的配置。

如果是，請遵循以下准則：

* 檢查市場活動資料源中的協調ID類型。
* CustomerId資料源是通過Customer Attributes建立的。
* 檢查資料源ID。
* 請求Adobe在資料源配置後重新啟動市場活動實例。
* 檢查觸發器報告中的觸發器分析問題。

**觸發器是否處於掛起狀態？**

否則，繼續下一步。 如果是，請遵循以下准則：

* 檢查事務模板是否已發佈。
* 檢查配置檔案是否不在denylist中。
* 檢查類型規則的應用。
* 檢查事務性消息的日誌。

**郵件是否有效？**

如果消息無效，請檢查以下項：

* 對於標籤為無效的觸發器富集個性化欄位，請從關聯的eventCusResource集合中驗證事務模板。
* 驗證消息格式
