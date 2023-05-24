---
title: 開始使用動態報告
description: 使用動態報告，將變數和維拖放到自由形式環境中，並分析市場活動的成功。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 5%

---

# 開始使用動態報告 {#about-dynamic-reports}

動態報告提供完全可定製的即時報告。 它增加了對個人資料資料的訪問，使用戶能夠按個人資料維度（如性別、城市和年齡）以及功能性電子郵件活動資料（如開啟和點擊）進行人口分析。 透過拖放介面，您可以探索資料、判斷電子郵件促銷活動對最重要客戶細分的執行方式，並評估其對收件者的影響。

>[!NOTE]
>
>僅具有管理權限或組織單位設定為的用戶 **全部** 可以建立或保存新報告。 如需詳細資訊，請參閱本[區段](../../administration/using/users-management.md)。

## 訪問動態報告 {#accessing-dynamic-reports}

可以訪問報告：

* 通過選擇 **[!UICONTROL Reports]** 的上界 **[!UICONTROL Reports]** 訪問所有交貨的報表的卡。

   ![](assets/campaign_reports_access.png)

* 在每個計畫、活動和消息中， **報告** 按鈕 **動態報告** 只查看特定於交貨的報表。

   ![](assets/campaign_reports_description.png)

某些報告在交付後無法立即可用，具體取決於收集和處理資訊所花的時間。

動態報告分為兩類：

* **模板**，可通過使用 **另存為** 選項&#x200B;**項目>另存為……**)。
* **自定義報告** （以藍色標識），可通過按一下 **建立新項目** 按鈕 **報告** 的子菜單。

>[!NOTE]
>
>根據組織單位篩選資料。

![](assets/dynamic_report_overview.png)

## 動態報告使用協定 {#dynamic-reporting-usage-agreement}

動態報告使用協定的目的是作為資料處理的彈出式同意。 預設情況下，協定僅可見，只能被分配有管理權限的用戶接受或拒絕。

有三種選擇：

* **[!UICONTROL Ask me later]**:按一下 **晚點問我**&#x200B;窗口將在24小時內停止顯示。 在您接受或拒絕協定之前，配置檔案維不會顯示在您的報表中，也不會收集或發送客戶的個人標識資訊。
* **[!UICONTROL Accept]**:通過接受此協定，您授權Adobe Campaign收集客戶的個人標識資訊，並將其傳輸到報告或資料中心。
* **[!UICONTROL Decline]**:拒絕協定後，配置檔案維將不會顯示在您的報表中，並且不會收集或發送客戶的個人標識資訊。 請注意，在這種情況下，仍將收集外部ID並用於標識最終用戶。

下表顯示接受此協定後將發生的情況，具體取決於您所在的區域。

|  | 動態報告 | Microsoft動力365連接器 |
|---|---|---|
| 美洲和APAC（亞太） | **功能可用**。 <br>所有現成功能（即城市、國家/地區、州、性別和年齡段）和客戶簡介資訊都推送到美國報告中心。 有關配置檔案維的詳細資訊，請參閱此 [頁](../../reporting/using/list-of-components-.md) | **功能可用**。 <br>所有出廠設定和自定義配置檔案欄位以及Adobe Campaign Standard事件欄位都在美國資料中心進行處理。 |
| EMEA（歐洲中東和非洲） | **功能可用**。 <br>所有現成功能（如城市、國家/地區、州、性別和年齡段）和定制簡檔資訊，已推送到EMEA報告中心。 有關配置檔案維的詳細資訊，請參閱此 [頁](../../reporting/using/list-of-components-.md) | **功能可用。** <br>在EMEA資料中心處理的所有現成配置檔案和自定義配置檔案欄位以及Adobe Campaign Standard事件欄位。 <br>**[!UICONTROL Control data]**它包含Adobe I/O註冊資料和在美國資料中心發送和儲存的客戶最終用戶事件的ID。 |

下表顯示拒絕此協定後將發生的情況，具體取決於您所在的區域。 請注意，即使您拒絕此協定，仍可以報告交付和MicrosoftDynamics 365整合。

| 區域 | 動態報告 | Microsoft動力365連接器 |
|---|---|---|
| 美洲和APAC（亞太） | **功能可用**。 <br> 除ExternalID外，沒有將出廠設定和自定義配置檔案資訊推送到美國報告中心。 | **功能可用**。 <br>除外部ID和收件人ID外，沒有將出廠設定或自定義配置檔案欄位發送到美國資料中心。 <br>除鏡像頁ID外，美國資料中心中處理的所有Adobe Campaign Standard事件欄位。 <br>有關MicrosoftDynamics 365整合的詳細資訊，請參閱 [頁](../../integrating/using/d365-acs-get-started.md)。 |
| EMEA（歐洲中東和非洲） | **功能可用**。 <br>除ExternalID外，沒有將現成和自定義配置檔案資訊推送到EMEA報告中心。 | **功能可用。** <br>除外部ID和收件人ID外，沒有發送到EMEA資料中心的現成或自定義配置檔案欄位。 <br>EMEA資料中心中處理的所有Adobe Campaign Standard事件欄位（鏡像頁ID除外）。  <br>**[!UICONTROL Control data]**它包含Adobe I/O註冊資料和在美國資料中心發送和儲存的客戶最終用戶事件的ID。<br>有關MicrosoftDynamics 365整合的詳細資訊，請參閱 [頁](../../integrating/using/d365-acs-get-started.md)。 |

此選項不是最終選項，您始終可以通過選擇 **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** 在 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**。

值可以隨時更改。 值1對應於 **[!UICONTROL Ask me later]**。 **[!UICONTROL Decline]** 和3 **[!UICONTROL Accept]**。

![](assets/pii_window_2.png)
