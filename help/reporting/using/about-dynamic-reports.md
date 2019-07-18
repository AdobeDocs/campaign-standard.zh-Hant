---
title: 關於動態報表
seo-title: 關於動態報表
description: 關於動態報表
seo-description: 使用動態報表，將變數和維度拖放到自由環境中，並分析促銷活動的成功與否。
page-status-flag: 從未啓動
uuid: a84a18bd-4e33-466e-a6 ce-d7008 fe12746
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 報告功能
content-type: reference
topic-tags: 關於報表
discoiquuid: bbb41c38-10c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 08b2363076adcc101b741ab66b85285e7a510baa

---


# About dynamic reports{#about-dynamic-reports}

>[!NOTE]
>
>Only users with administration rights or with organizational units set to **All** can create or save a new report. For more on this, refer to this [section](../../administration/using/types-of-users.md).

![](assets/dynamic_report_intro.png)

動態報告提供可完全自訂和即時報告。它新增個人資料資料存取權，讓人口統計分析依據個人資料維度(如性別、城市和年齡)，以及功能電子郵件促銷活動資料(例如開啓和點擊)進行人口統計分析。透過拖放介面，您可以探索資料，決定電子郵件促銷活動對您最重要客戶細分的執行方式，並衡量他們對收件者的影響。

動態報表功能由於拖放功能表和可自訂的視覺化功能，可讓您在任何組合中結合維度、度量和時間範圍，以及無限制的劃分和比較。


**相關主題：**

* [報表清單](../../reporting/using/defining-the-report-period.md)
* [組織單位](../../administration/using/organizational-units.md)
* [動態報表](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-dynamic-report-feature-video-use.html) 視訊

## Accessing dynamic reports {#accessing-dynamic-reports}

可存取報表：

* From the home page by selecting **[!UICONTROL Reports]** tab in the top bar or the **[!UICONTROL Reports]** card to access reports for all deliveries.

   ![](assets/campaign_reports_access.png)

* In each program, campaign, and message, from the **Reports** button by clicking **Dynamic Reports** to only view the reports specific to the delivery.

   ![](assets/campaign_reports_description.png)

某些報表無法在傳送後立即可用，視收集和處理資訊所花的時間而定。

動態報表分為兩類：

* **範本**，可借由使用 **「另存新檔** 」選項(**「專案&gt;另存新檔」)複製這些範本，以進行修改。**) 範本中。
* **自訂報表** (以藍色表示)，可透過按一下「報表」首頁上的「 **建立新專案」** 按鈕 **直接** 建立。

>[!NOTE]
>
>根據組織單位篩選資料。

![](assets/dynamic_report_overview.png)


## Dynamic reporting usage agreement {#dynamic-reporting-usage-agreement}

動態報表可讓您根據描述檔維度來篩選報表資料。

您只能在接受動態報告使用合約後，在報表中顯示和使用描述檔維度。根據預設，合約僅顯示出來，且僅供指派給管理權限的使用者接受或拒絕。

本協議允許在美國境內的下列個人檔案資料傳輸和儲存：城市、國家/地區、州、性別和區段。

凡接受本合約，歐洲及非歐洲資料均將傳輸至美國。

![](assets/pii_window.png)

有三個選項：

* **[!UICONTROL Ask me later]**：按一下稍後再按一下，視窗會停止顯示24小時。
* **[!UICONTROL Accept]**：接受本合約即表示您授權Adobe Campaign收集客戶的個人識別資訊，並將其轉移至美國。
* **[!UICONTROL Decline]**：透過減少合約，描述檔維度將不會出現在您的報表中，而客戶的個人識別資訊將不會收集或傳送。

This choice is not final, you can always change it by selecting **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Options]**.

值可隨時變更。The value -1 corresponds to **[!UICONTROL Ask me later]**, 1 **[!UICONTROL Accept]** and 0 **[!UICONTROL Decline]**.

![](assets/pii_window_2.png)

