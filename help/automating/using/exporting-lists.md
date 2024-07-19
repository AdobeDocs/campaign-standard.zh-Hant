---
title: 匯出清單
description: Adobe Campaign可讓您直接從概述畫面將顯示為清單的資料匯出到檔案中，以供日後使用。
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# 匯出清單{#exporting-lists}

Adobe Campaign可讓您直接將清單匯出至檔案中，以供日後使用。 匯出檔案中的清單會在&#x200B;**[!UICONTROL Export audits]**&#x200B;功能表中產生記錄專案。 有關匯出稽核的詳細資訊，請參閱[稽核匯出](../../administration/using/auditing-export-logs.md)區段。

![](assets/do-not-localize/how-to-video.png) [探索如何在視訊中設定清單](#video)

匯出清單選項預設會匯出最多100,000行，並由&#x200B;**Nms_ExportListLimit**&#x200B;選項定義。 此選項可由功能管理員在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;功能表下管理。

擁有&#x200B;**[!UICONTROL EXPORT (export)]**&#x200B;角色的使用者，可在所有具有&#x200B;**清單**&#x200B;模式檢視的畫面中使用匯出清單。

1. 移至您選擇的&#x200B;**清單**&#x200B;畫面。 例如，測試設定檔總覽畫面( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** )。
1. 檢查熒幕是否處於&#x200B;**清單**&#x200B;模式。

   ![](assets/export_list_mode_switch.png)

1. 使用右上角的&#x200B;**[!UICONTROL Configure list]**&#x200B;按鈕，以您要匯出的順序來組織清單中的欄。 除了已設定的欄外，也會匯出資源的主索引鍵。
1. 您也可以套用篩選器。 若要這麼做，請按一下左上角的按鈕以顯示搜尋窗格。

   如果您從包含不同資源的清單執行匯出，則必須套用篩選器，如此清單中只會顯示一種型別的資源。

1. 您也可以將所選的欄排序。
1. 選取匯出按鈕![](assets/exportlistbutton.png)。

   將會出現快顯視窗以確認匯出。 在您確認匯出後，檔案會自動下載到您的電腦。

檔案會以CSV格式產生，副檔名為.TXT。 根據匯出的資源和匯出日期來命名。 例如：名稱profileBase_20150426_120253.txt將套用至2015年4月26日12:02:53執行的設定檔匯出。 它以UTF-8格式編碼。

數值和日期會考量執行匯出之使用者的當地時間（地區設定）。 例如： DD-MM-YYYY或MM-DD-YYYY。

若要執行大於此值的匯出，您必須建立專用工作流程。 請參閱[擷取檔案](../../automating/using/extract-file.md)區段。

**範例**

以下範例是從以下定義的設定檔清單執行的匯出：

* 顯示的欄（依順序）：姓氏、名字、出生日期、電子郵件地址。
* 名稱會依字母順序排序。

![](assets/export_list_example1.png)

產生的檔案顯示如下（前10筆記錄）：

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

本影片說明如何設定清單。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

[此處](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)提供其他Campaign Standard操作說明影片。
