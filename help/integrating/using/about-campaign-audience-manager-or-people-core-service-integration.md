---
title: 關於 Campaign-Audience Manager 或 People 核心服務整合
description: 通過Audience Manager/人員核心服務整合，您可以在不同的Adobe Experience Cloud解決方案中共用受眾或細分市場。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 22%

---

# 關於 Campaign-Audience Manager 或 People 核心服務整合{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>根據交換的資料，在Adobe Campaign進口受眾可能受到法律限制。

Adobe Campaign允許您與不同的Adobe Experience Cloud應用程式交換和共用受眾/網段。 整合 **Adobe Campaign** 與 **人員核心服務** (也稱為 **簡介和受眾核心服務**)或Adobe Audience Manager允許您：

* 將不同Adobe Experience Cloud解決方案的受眾/分區導入Adobe Campaign。 可以從 **[!UICONTROL Audiences]** 菜單。
* 將受眾導出為共用的受眾/段。 這些對象可用於您所使用的不同 Adobe Experience Cloud 解決方案。 在將工作流中的活動作為目標後，可以使用 **[!UICONTROL Save audience]** 的子菜單。

整合支援兩種類型的Adobe Experience CloudID:

* **訪問者ID**:此類型的ID允許您調節Adobe Experience Cloud訪問者與Adobe Campaign配置檔案。 一旦通過Adobe IMS啟用連接，Marketing Cloud訪問者ID服務即被激活，這將取代Adobe Campaign使用的永久cookie。 這允許您識別訪問者，然後將其連結到配置檔案。
   <br>訪問者ID在通過Adobe Campaign發送的電子郵件中按一下後立即連結到配置檔案：
   * 如果配置檔案已具有訪問者ID，則配置檔案的瀏覽器資料允許Adobe Campaign恢復並自動將配置檔案連結到訪問者ID。
   * 如果找不到訪問者ID，則會建立新ID。 此訪問者ID儲存在配置檔案跟蹤日誌中。

   ID隨後將由具有相同CNAME的其他Adobe Marketing Cloud應用程式識別。

* **聲明的ID**:此類型的ID允許您將任何類型的資料與Adobe Campaign資料庫中的元素進行協調。 在 Adobe Campaign 中以預先定義的調解金鑰呈現。交換資料時，對Adobe Campaign資料庫標識符進行散列處理。 然後，將這些散列ID與參與進口或出口的Adobe Marketing Cloud受眾的散列ID進行比較。
   <br>此整合支援常規聲明的ID、散列聲明的ID和加密聲明的ID。

   >[!NOTE]
   >
   >已宣告的 ID 資料來源現在也可搭配 People 核心服務整合使用。
   >
   >如果您使用 People 核心服務整合，且想要新增 Audience Manager 整合，則需要 Adobe Audience Manager 顧問的協助，以避免在 Adobe Audience Manager 內容中轉換為使用此宣告 ID 資料來源時，所收集的 ID 同步全部遺失。


   加密允許您通過指定加密算法使用聲明的ID在資料源（例如PII）中共用加密資料。

   例如，通過解密加密的電子郵件地址或SMS號碼，您還可以向用戶發送觸發消息，即使其配置檔案在Adobe Campaign資料庫中不存在。

下圖詳細說明此整合的運作方式。這裡，AAM代表Adobe Audience Manager和Adobe Campaign Standard。

![](assets/aam_diagram.png)
