---
title: 匯出清單
description: Adobe Campaign允許您將顯示為清單的資料從概述螢幕直接導出到檔案中，以供將來使用。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 6%

---

# 匯出清單{#exporting-lists}

Adobe Campaign允許您將清單直接導出到檔案中，以備將來使用。 導出檔案中的清單將生成 **[!UICONTROL Export audits]** 的子菜單。 有關匯出稽核的詳細資訊，請參閱[稽核匯出](../../administration/using/auditing-export-logs.md)區段。

![](assets/do-not-localize/how-to-video.png) [瞭解如何在視頻中配置清單](#video)

「導出清單」(export list)選項允許您預設導出最多100,000行，並且由 **Nms_ExportListLimit** 的雙曲餘切值。 此選項可由功能管理員管理，位於 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 的子菜單。

導出清單在具有 **清單** 模式視圖，對於具有 **[!UICONTROL EXPORT (export)]** 角色。

1. 轉到您選擇的 **清單** 的上界。 例如，test概要檔案概述螢幕( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** )。
1. 檢查螢幕是否在 **清單** 的子菜單。

   ![](assets/export_list_mode_switch.png)

1. 按要使用 **[!UICONTROL Configure list]** 按鈕。 除配置列外，還將導出資源的主鍵。
1. 如果您願意，可以應用篩選器。 要執行此操作，請按一下左上角的按鈕以顯示搜索窗格。

   如果從包含不同資源的清單執行導出，則必須應用篩選器，以便清單中只顯示一種類型的資源。

1. 如果您願意，請對所選列進行排序。
1. 選擇導出按鈕 ![](assets/exportlistbutton.png)。

   將出現一個彈出窗口來確認導出。 確認導出後，檔案將自動下載到您的電腦。

檔案以CSV格式生成，副檔名為.TXT。 它根據導出的資源和導出日期命名。 例如：名稱profileBase_20150426_120253.txt將應用於2015年4月26日在12時執行的配置檔案導出:02:53. 它以UTF-8格式編碼。

數字值和日期考慮執行導出的用戶的本地時間（區域設定）。 例如：DD-MM-YYYY或MM-DD-YYYY。

要執行大於此值的導出，必須建立專用工作流。 請參閱 [提取檔案](../../automating/using/extract-file.md) 的子菜單。

**範例**

以下示例是從下面定義的配置檔案清單中執行的導出：

* 顯示的列（按順序）:姓、名、出生日期、電子郵件地址。
* 名稱按字母順序排序。

![](assets/export_list_example1.png)

生成的檔案如下所示（前十條記錄）:

```
Last name;First name;Birth date;Email;Zip code
Abalo;Patrick;11/11/1941 02:00:00;patrick.a@testmail.com;29200
Abasq;Joel;21/08/1977 02:00:00;abasq.joel@testmail.com;92160
Abernot;John;12/07/1963 01:00:00;john.abernot@testmail.com;78510
Abiven;Christian;16/03/1975 01:00:00;chris.a@mailtest.com;35000
Abouvier;Peter;02/07/1975 01:00:00;pabouvier@mailtest.com;94560
Accardi;Mike;22/06/1948 01:00:00;mike.accardi@mail.com;76400
Accremont;Frank;27/04/1947 01:00:00;accr.frank@mailtest.com;13500
Adam;Daniel;17/09/1953 01:00:00;danieladam@mail.com;17000
Adama;Pascal;22/01/1990 01:00:00;adapascal@mailtest.com;75012
Adama;Henry;22/09/1992 02:00:00;henry.adama@mail.com;64120
```

**相關主題：**

* [角色](../../administration/using/list-of-roles.md)
* [自訂清單](../../start/using/customizing-lists.md)

## 教程視頻 {#video}

此視頻顯示如何配置清單。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

可提供其他Campaign Standard操作視頻 [這裡](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)。
