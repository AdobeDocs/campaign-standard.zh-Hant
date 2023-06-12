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
source-wordcount: '791'
ht-degree: 5%

---

# 開始使用動態報告 {#about-dynamic-reports}

動態報告提供完全可自訂的即時報告。 它新增對設定檔資料的存取權，除了功能性電子郵件促銷活動資料（如開啟和點按）外，還能夠依設定檔維度（如性別、城市和年齡）進行人口統計分析。 透過拖放介面，您可以探索資料、判斷電子郵件促銷活動對最重要客戶細分的執行方式，並評估其對收件者的影響。

>[!NOTE]
>
>僅限具有管理許可權或組織單位設定為的使用者 **全部** 可以建立或儲存新報表。 如需詳細資訊，請參閱本[區段](../../administration/using/users-management.md)。

## 存取動態報告 {#accessing-dynamic-reports}

報表可以存取：

* 從首頁選取 **[!UICONTROL Reports]** 標籤或上方列的 **[!UICONTROL Reports]** 卡片以存取所有傳遞的報告。

   ![](assets/campaign_reports_access.png)

* 在每個方案、行銷活動和訊息中，來自 **報表** 按一下「 」按鈕 **動態報告** 以僅檢視特定於傳遞的報告。

   ![](assets/campaign_reports_description.png)

視收集和處理資訊所花的時間而定，某些報表在傳送後無法立即使用。

動態報告分為兩個類別：

* **範本**，您可使用來複製以進行修改 **另存為** 選項(**專案>另存新檔……**)。
* **自訂報表** （以藍色標示），您可以按一下 **建立新專案** 上的按鈕 **報表** 首頁。

>[!NOTE]
>
>資料會根據您的組織單位進行篩選。

![](assets/dynamic_report_overview.png)

## 動態報告使用協定 {#dynamic-reporting-usage-agreement}

動態報告使用協定的目的是作為資料處理的快顯同意。 依預設，協定僅可見，且只能由指派有管理許可權的使用者接受或拒絕。

有三個可用選項：

* **[!UICONTROL Ask me later]**：按一下 **稍後詢問我**，視窗將停止顯示24小時。 在您接受或拒絕合約之前，設定檔維度不會出現在您的報表中，且不會收集或傳送您客戶的個人識別資訊。
* **[!UICONTROL Accept]**：接受本合約即表示您授權Adobe Campaign收集客戶的個人識別資訊，並將其傳輸至報表或資料中心。
* **[!UICONTROL Decline]**：拒絕合約後，設定檔維度不會出現在您的報表中，也不會收集或傳送您客戶的個人識別資訊。 請注意，在此情況下，系統仍會收集externalID並用來識別一般使用者。

下表根據您的地區顯示接受此合約後會發生什麼事。

|  | 動態報告 | Microsoft Dynamics 365聯結器 |
|---|---|---|
| 美洲和亞太地區（亞太） | **可用功能**. <br>所有現成可用的資訊（例如城市、國家/地區、州、性別和年齡區段），以及推送至美國報告中心的自訂設定檔資訊。 如需設定檔維度的詳細資訊，請參閱此 [頁面](../../reporting/using/list-of-components-.md) | **可用功能**. <br>所有現成可用的和自訂設定檔欄位和Adobe Campaign Standard事件欄位都會在美國資料中心處理。 |
| EMEA （歐洲、中東和非洲） | **可用功能**. <br>所有現成可用的資訊（即根據年齡區分的城市、國家/地區、州、性別和區段），以及推送至EMEA報告中心的自訂設定檔資訊。 如需設定檔維度的詳細資訊，請參閱此 [頁面](../../reporting/using/list-of-components-.md) | **可用功能。** <br>在EMEA資料中心處理的所有現成可用和自訂設定檔欄位，以及Adobe Campaign Standard事件欄位。 <br>**[!UICONTROL Control data]**其中包含Adobe I/O註冊資料，以及傳送並儲存在美國資料中心的客戶使用者事件ID。 |

下表顯示根據您所在的地區，拒絕此合約後會發生什麼情況。 請注意，即使您拒絕此合約，仍可使用傳遞與Microsoft Dynamics 365整合的相關報告。

| 區域 | 動態報告 | Microsoft Dynamics 365聯結器 |
|---|---|---|
| 美洲和亞太地區（亞太） | **可用功能**. <br> 除了ExternalID以外，沒有現成可用的和自訂設定檔資訊推送至美國報表中心。 | **可用功能**. <br>除了外部ID和收件者ID以外，不會傳送任何現成可用的或自訂的設定檔欄位給美國的資料中心。 <br>所有Adobe Campaign Standard事件欄位都在美國資料中心處理，但映象頁面ID除外。 <br>如需Microsoft Dynamics 365整合的詳細資訊，請參閱此 [頁面](../../integrating/using/d365-acs-get-started.md). |
| EMEA （歐洲、中東和非洲） | **可用功能**. <br>除了ExternalID以外，沒有現成可用的與自訂設定檔資訊推送至EMEA報告中心。 | **可用功能。** <br>除了外部ID和收件者ID以外，不會傳送任何現成可用的或自訂的設定檔欄位至EMEA資料中心。 <br>所有Adobe Campaign Standard事件欄位都在EMEA資料中心處理，但映象頁面ID除外。  <br>**[!UICONTROL Control data]**其中包含Adobe I/O註冊資料，以及傳送並儲存在美國資料中心的客戶使用者事件ID。<br>如需Microsoft Dynamics 365整合的詳細資訊，請參閱此 [頁面](../../integrating/using/d365-acs-get-started.md). |

此選擇不是最終選擇，您一律可以選取 **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** 在 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

此值可隨時變更。 值1對應至 **[!UICONTROL Ask me later]**， 2 **[!UICONTROL Decline]** 和3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
