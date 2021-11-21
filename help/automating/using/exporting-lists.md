---
title: 匯出清單
description: 'Adobe Campaign可讓您直接從檔案的概述畫面中匯出顯示為清單的資料，以供日後使用。 '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# 匯出清單{#exporting-lists}

Adobe Campaign可讓您直接將清單匯出至檔案中，以供日後使用。 在檔案中匯出清單時，會在 **[!UICONTROL Export audits]** 功能表。 有關匯出稽核的詳細資訊，請參閱[稽核匯出](../../administration/using/auditing-export-logs.md)區段。

![](assets/do-not-localize/how-to-video.png) [探索如何在影片中設定清單](#video)

「匯出清單」選項預設會匯出最多100,000行，並由 **Nms_ExportListLimit** 選項。 此選項可由功能管理員管理，位於 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** 功能表。

所有具有 **清單** 模式視圖，適用於具有 **[!UICONTROL EXPORT (export)]** 角色。

1. 前往您選擇的 **清單** 螢幕。 例如，測試設定檔概述畫面( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** )。
1. 檢查畫面是否在 **清單** 模式。

   ![](assets/export_list_mode_switch.png)

1. 依照您要使用匯出的順序，組織清單中的欄 **[!UICONTROL Configure list]** 按鈕。 除了已設定的欄外，資源的主要索引鍵也將匯出。
1. 您也可以套用篩選。 要執行此操作，請按一下左上角的按鈕以顯示搜尋窗格。

   如果從包含不同資源的清單執行匯出，則必須套用篩選器，才能在清單中只顯示一種類型的資源。

1. 您也可以對您選取的欄進行排序。
1. 選擇導出按鈕 ![](assets/exportlistbutton.png).

   隨即出現快顯視窗以確認匯出。 確認匯出後，檔案會自動下載至您的電腦。

檔案會以CSV格式產生，副檔名為.TXT。 它會根據匯出的資源和匯出日期而命名。 例如：名稱profileBase_20150426_120253.txt將套用至2015年4月26日12:02:53。 其編碼格式為UTF-8。

數值和日期會考量執行匯出作業之使用者的當地時間（地區）。 例如：DD-MM-YYYY或MM-DD-YYYY。

若要執行大於此值的匯出，您必須建立專用的工作流程。 請參閱 [擷取檔案](../../automating/using/extract-file.md) 區段。

**範例**

以下範例是從以下定義的設定檔清單執行的匯出：

* 顯示的列（按順序）:姓氏、名字、出生日期、電子郵件地址。
* 名稱按字母順序排序。

![](assets/export_list_example1.png)

產生的檔案如下（前10條記錄）:

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

## 教學課程影片 {#video}

此影片說明如何設定清單。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

提供其他Campaign Standard作法影片 [此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant).
