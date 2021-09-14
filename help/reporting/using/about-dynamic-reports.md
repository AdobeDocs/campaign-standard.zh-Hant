---
title: 開始使用動態報告
description: 透過動態報表，將變數和維度拖放至自由格式環境中，並分析促銷活動的成功。
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

動態報告提供完全可自訂的即時報告。 它新增了對設定檔資料的存取權，除了功能性電子郵件促銷活動資料（例如開啟和點按）外，還能依設定檔維度（例如性別、城市和年齡）進行人口統計分析。 透過拖放介面，您可以探索資料、判斷電子郵件促銷活動對最重要客戶細分的執行方式，並評估其對收件者的影響。

>[!NOTE]
>
>只有具有管理權限或組織單位設為&#x200B;**All**&#x200B;的使用者才能建立或儲存新報表。 如需詳細資訊，請參閱本[區段](../../administration/using/users-management.md)。

## 存取動態報表 {#accessing-dynamic-reports}

可存取報表：

* 從首頁，選取頂端列的&#x200B;**[!UICONTROL Reports]**&#x200B;標籤或&#x200B;**[!UICONTROL Reports]**&#x200B;卡片以存取所有傳送的報表。

   ![](assets/campaign_reports_access.png)

* 在每個方案、促銷活動和訊息中，按一下&#x200B;**動態報表**&#x200B;按鈕，從&#x200B;**Reports**&#x200B;按鈕僅檢視傳送的特定報表。

   ![](assets/campaign_reports_description.png)

根據收集和處理資訊所花的時間，某些報表無法在傳送後立即使用。

動態報表分為兩個類別：

* **範本**，您可以使用「儲存」選項（「專案」>「另存新檔」） **來復** 制範本，以便修改範本。**「另存新檔」。**)。
* **自訂報表** （以藍色標示），按一下報表首頁上的「建立新 **專** 案」按鈕即可直 **** 接建立。

>[!NOTE]
>
>系統會根據您的組織單位來篩選資料。

![](assets/dynamic_report_overview.png)

## 動態報告使用協定 {#dynamic-reporting-usage-agreement}

動態報告使用協定的用途是作為資料處理的快顯同意。 依預設，協定僅可見，且只能由指派有管理權限的使用者接受或拒絕。

有三個可用選項：

* **[!UICONTROL Ask me later]**:按一 **下「稍後詢問我」**，視窗會在24小時內停止顯示。在您接受或拒絕合約之前，設定檔維度不會出現在您的報表中，且不會收集或傳送客戶的個人識別資訊。
* **[!UICONTROL Accept]**:接受本合約後，您即授權Adobe Campaign收集客戶的個人識別資訊，並將其傳輸至報表或資料中心。
* **[!UICONTROL Decline]**:若拒絕合約，設定檔維度將不會顯示在您的報表中，且您的客戶個人識別資訊將不會收集或傳送。請注意，在此情況下，系統仍會收集externalID並用於識別使用者。

下表顯示接受此協定後會發生什麼，具體取決於您的地區。

|  | 動態報告 | Microsoft Dynamics 365連接器 |
|---|---|---|
| 美洲和亞太地區（亞太） | **可用功能**。<br>所有現成可用（例如，根據年齡設定的城市、國家/地區、州、性別和區段）和推送至美國報表中心的自訂設定檔資訊。如需設定檔維度的詳細資訊，請參閱此[page](../../reporting/using/list-of-components-.md) | **可用功能**。<br>所有現成可用和自訂設定檔欄位和Adobe Campaign Standard事件欄位都會在美國資料中心處理。 |
| EMEA（歐洲中東和非洲） | **可用功能**。<br>立即可用（例如，根據年齡設定的城市、國家/地區、州、性別和區段）和推入EMEA報告中心的自訂設定檔資訊。如需設定檔維度的詳細資訊，請參閱此[page](../../reporting/using/list-of-components-.md) | **功能可用。** <br>在EMEA資料中心處理的所有現成可用和自訂設定檔欄位及Adobe Campaign Standard事件欄位。<br>**[!UICONTROL Control data]**包含Adobe I/O註冊資料，以及在美國資料中心中傳送和儲存的客戶最終用戶事件ID。 |

下表顯示拒絕此協定後會發生什麼，具體取決於您的地區。 請注意，即使您拒絕此協定，仍可使用傳送和Microsoft Dynamics 365整合的報表。

| 地區 | 動態報告 | Microsoft Dynamics 365連接器 |
|---|---|---|
| 美洲和亞太地區（亞太） | **可用功能**。<br> 除了ExternalID外，沒有推送至美國報表中心的現成可用和自訂設定檔資訊。 | **可用功能**。<br>除外部ID和收件者ID外，沒有立即可用或自訂設定檔欄位傳送至美國資料中心。<br>美國資料中心處理的所有Adobe Campaign Standard事件欄位（鏡像頁面ID除外）。<br>有關Microsoft Dynamics 365整合的詳細資訊，請參 [閱本頁](../../integrating/using/d365-acs-get-started.md)。 |
| EMEA（歐洲中東和非洲） | **可用功能**。<br>除了ExternalID外，沒有推送至EMEA報表中心的現成可用和自訂設定檔資訊。 | **功能可用。** <br>除外部ID和收件者ID外，沒有立即可用或自訂設定檔欄位傳送至EMEA資料中心。<br>EMEA資料中心處理的所有Adobe Campaign Standard事件欄位（鏡像頁面ID除外）。<br>**[!UICONTROL Control data]**包含Adobe I/O註冊資料，以及在美國資料中心中傳送和儲存的客戶最終用戶事件ID。<br>有關Microsoft Dynamics 365整合的詳細資訊，請參 [閱本頁](../../integrating/using/d365-acs-get-started.md)。 |

此選項不是最終選項，您始終可以選擇&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;中的&#x200B;**[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]**&#x200B;進行更改。

值可隨時變更。 值1對應於&#x200B;**[!UICONTROL Ask me later]**、2 **[!UICONTROL Decline]**&#x200B;和3 **[!UICONTROL Accept]**。

![](assets/pii_window_2.png)
