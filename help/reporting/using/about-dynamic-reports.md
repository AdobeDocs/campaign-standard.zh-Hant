---
title: 開始使用動態報告
description: 使用動態報表，將變數和維度拖放至您的自由格式環境中，並分析行銷活動的成功。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 2%

---

# 開始使用動態報告 {#about-dynamic-reports}

動態報告提供完全可自訂的即時報告。 它新增對設定檔資料的存取權，除了功能性電子郵件促銷活動資料（如開啟和點按）外，還支援依設定檔維度（如性別、城市和年齡）進行人口統計分析。 透過拖放介面，您可以探索資料、判斷電子郵件行銷活動對最重要客戶細分的執行方式，並評估其對收件者的影響。

>[!NOTE]
>
>僅限具有管理許可權或組織單位設定為的使用者 **全部** 可以建立或儲存新報表。 如需詳細資訊，請參閱本[區段](../../administration/using/users-management.md)。

## 存取動態報表 {#accessing-dynamic-reports}

您可存取報告：

* 從首頁選取 **[!UICONTROL Reports]** 標籤或列中的 **[!UICONTROL Reports]** 卡片以存取所有傳遞的報告。

  ![](assets/campaign_reports_access.png)

* 在每個方案、行銷活動和訊息中，來自 **報表** 按一下按鈕 **動態報告** 以僅檢視特定於傳送的報告。

  ![](assets/campaign_reports_description.png)

某些報表在傳送後無法立即使用，視收集和處理資訊所花費的時間而定。

動態報告分為兩個類別：

* **範本**，可透過使用複製以進行修改 **另存為** 選項(**專案>另存新檔……**)。
* **自訂報表** （以藍色標示），您可以按一下 **建立新專案** 上的按鈕 **報表** 首頁。

>[!NOTE]
>
>系統會根據您的組織單位篩選資料。

![](assets/dynamic_report_overview.png)

## 動態報告使用協定 {#dynamic-reporting-usage-agreement}

動態報告使用合約的目的是當做資料處理的快顯同意。 依預設，協定僅可見，且僅能被指派管理許可權的使用者接受或拒絕。

有三個可用選項：

* **[!UICONTROL Ask me later]**：按一下 **稍後詢問我**，視窗將停止顯示24小時。 在您接受或拒絕合約之前，設定檔維度不會出現在您的報表中，也不會收集或傳送您客戶的個人識別資訊。
* **[!UICONTROL Accept]**：接受本合約即表示您授權Adobe Campaign收集客戶的個人識別資訊，並將其傳輸至報表或資料中心。
* **[!UICONTROL Decline]**：拒絕合約後，設定檔維度不會出現在您的報表中，也不會收集或傳送您客戶的個人識別資訊。 請注意，在此情況下，仍會收集externalID並使用其識別一般使用者。

下表會依據您所在的區域，顯示接受此合約後會發生什麼事。

|  | 動態報告 | Microsoft Dynamics 365聯結器 |
|---|---|---|
| 美洲和APAC （亞太） | **可用功能**. <br>所有立即可用（亦即根據年齡劃分的城市、國家/地區、州、性別和區段）與自訂設定檔資訊推送至美國報表中心。 有關設定檔維度的詳細資訊，請參閱此 [頁面](../../reporting/using/list-of-components-.md) | **可用功能**. <br>所有現成可用的和自訂設定檔欄位和Adobe Campaign Standard事件欄位都會在美國資料中心處理。 |
| EMEA （歐洲、中東及非洲） | **可用功能**. <br>所有現成可用的資訊（亦即根據年齡區分的城市、國家/地區、州、性別和區段），以及推送至EMEA報告中心的自訂設定檔資訊。 有關設定檔維度的詳細資訊，請參閱此 [頁面](../../reporting/using/list-of-components-.md) | **功能可用。** <br>所有現成可用的和自訂設定檔欄位，以及EMEA資料中心處理的Adobe Campaign Standard事件欄位。 <br>**[!UICONTROL Control data]**其中包含Adobe I/O註冊資料，以及傳送並儲存在美國資料中心的客戶一般使用者事件的ID。 |

下表顯示根據您所在的地區，拒絕此合約後會發生什麼事情。 請注意，即使您拒絕此合約，仍可提供有關傳遞與Microsoft Dynamics 365整合的報告。

| 區域 | 動態報告 | Microsoft Dynamics 365聯結器 |
|---|---|---|
| 美洲和APAC （亞太） | **可用功能**. <br> 除了ExternalID，沒有現成可用的和自訂設定檔資訊推送至美國報表中心。 | **可用功能**. <br>除了外部ID和收件者ID以外，不會有任何現成可用的或自訂的設定檔欄位傳送至美國資料中心。 <br>所有Adobe Campaign Standard事件欄位都在美國資料中心處理，但映象頁面ID除外。 <br>如需Microsoft Dynamics 365整合的詳細資訊，請參閱本節 [頁面](../../integrating/using/d365-acs-get-started.md). |
| EMEA （歐洲、中東及非洲） | **可用功能**. <br>除了ExternalID，沒有現成可用的和自訂設定檔資訊推送至EMEA報告中心。 | **功能可用。** <br>除了外部ID和收件者ID以外，不會有任何現成可用的或自訂的設定檔欄位傳送至EMEA資料中心。 <br>所有Adobe Campaign Standard事件欄位都在EMEA資料中心處理，但映象頁面ID除外。  <br>**[!UICONTROL Control data]**其中包含Adobe I/O註冊資料，以及傳送並儲存在美國資料中心的客戶一般使用者事件的ID。<br>如需Microsoft Dynamics 365整合的詳細資訊，請參閱本節 [頁面](../../integrating/using/d365-acs-get-started.md). |

此選擇不是最終選擇，您隨時都可透過選擇 **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** 在 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

此值可隨時變更。 值1對應至 **[!UICONTROL Ask me later]**， 2 **[!UICONTROL Decline]** 和3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
