---
solution: Campaign Standard
product: campaign
title: 匯出清單
description: 'Adobe Campaign可讓您直接從檔案中匯出顯示為清單的資料，以供日後使用。 '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 6%

---


# 匯出清單{#exporting-lists}

Adobe Campaign可讓您直接將清單匯出至檔案中，以供日後使用。 導出檔案中的清單會在&#x200B;**[!UICONTROL Export audits]**&#x200B;菜單中生成日誌條目。 有關匯出稽核的詳細資訊，請參閱[稽核匯出](../../administration/using/auditing-export-logs.md)區段。

![](assets/do-not-localize/how-to-video.png) [探索如何在視訊中設定清單](#video)

導出清單選項允許預設導出最多100,000行，並且由&#x200B;**Nms_ExportListLimit**&#x200B;選項定義。 此選項可由功能管理員管理，位於&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**&#x200B;功能表下。

對於具有&#x200B;**[!UICONTROL EXPORT (export)]**&#x200B;角色的用戶，所有具有&#x200B;**List**&#x200B;模式視圖的螢幕都提供導出清單。

1. 前往您選擇的&#x200B;**清單**&#x200B;畫面。 例如，測試設定檔概述畫面(**[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**)。
1. 檢查螢幕是否處於&#x200B;**List**&#x200B;模式。

   ![](assets/export_list_mode_switch.png)

1. 使用右上角的&#x200B;**[!UICONTROL Configure list]**&#x200B;按鈕，依您要匯出的順序組織清單中的欄。 除了配置的列外，還將導出資源的主鍵。
1. 如果您喜歡，可以套用篩選。 若要這麼做，請按一下左上角的按鈕以顯示搜尋窗格。

   如果您從包含不同資源的清單進行匯出，則必須套用篩選，如此清單中才會顯示一種資源類型。

1. 如果您喜歡，請對所選欄進行排序。
1. 選擇導出按鈕![](assets/exportlistbutton.png)。

   隨即出現快顯視窗以確認匯出。 確認匯出後，檔案會自動下載至您的電腦。

檔案是以CSV格式產生，副檔名為。TXT。 它根據導出的資源和導出日期命名。 例如：名稱profileBase_20150426_120253.txt將應用於2015年4月26日12:02:53進行的配置檔案導出。 它以UTF-8格式編碼。

數值和日期會考慮執行匯出的使用者的當地時間（地區）。 例如：DD-MM-YYYY或MM-DD-YYYY。

要執行大於此值的導出，必須建立專用的工作流。 請參閱[Extract file](../../automating/using/extract-file.md)一節。

**範例**

以下示例是從以下定義的配置檔案清單中執行的導出：

* 顯示的列（按順序）:姓氏、名字、出生日期、電子郵件地址。
* 名稱按字母順序排序。

![](assets/export_list_example1.png)

生成的檔案如下（前10條記錄）:

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

## 教學課程影片{#video}

此影片說明如何設定清單。

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

其他Campaign Standard操作說明影片可在[這裡](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=zh-Hant)取得。
