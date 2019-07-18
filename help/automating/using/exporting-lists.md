---
title: 匯出清單
seo-title: 匯出清單
description: 匯出清單
seo-description: 'Adobe Campaign可讓您將顯示為概述畫面中清單的資料直接匯出為檔案，以便日後使用。 '
page-status-flag: 從未啓動
uuid: c64Fe706-bd6 e-4746-958e-f97226 f4 e2 cb
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 匯入-匯出資料
discoiquuid: 12c874da-435f-44b6-a3 c8-873301e177 cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting lists{#exporting-lists}

Adobe Campaign可讓您將清單直接匯出至檔案，以便日後使用。Exporting a list in a file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit** option. This option can be managed by the functional administrator, under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

Export list is available in all the screens that have a **List** mode view, for users with the **[!UICONTROL EXPORT (export)]** role.

1. Go to your chosen **List** screen. For example, the test profile overview screen ( **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]** ).
1. Check that the screen is in **List** mode.

   ![](assets/export_list_mode_switch.png)

1. Organize the columns in the list in the order that you want to export them using the **[!UICONTROL Configure list]** button, in the top right corner. 除了設定的欄外，還將匯出資源的主要金鑰。
1. 您可以視需要套用篩選。若要這麼做，請按一下左上角的按鈕以顯示搜尋窗格。

   如果您從包含不同資源的清單進行匯出，您必須套用篩選器，如此才能在清單中只顯示一種資源類型。

1. 如果您喜歡，請對選擇的欄進行排序。
1. Select the export button ![](assets/exportlistbutton.png).

   此時會出現彈出式視窗來確認匯出。在確認匯出後，檔案會自動下載至您的電腦。

檔案是以CSV格式產生，除非匯出在iOS中執行，否則產生的檔案是採用TXT格式。它是根據匯出的資源和匯出日期命名。例如：名稱ProfileBase_20150426_120253.csv將會套用至2015年月26日下午12：02：53的描述檔匯出。它以UTF-8格式編碼。

數值和日期會考量執行匯出之使用者的當地時間(地區設定)。例如：DD-MM-YYYY或MM-DD-YYYY。

若要執行比這更大的匯出作業，您必須建立專屬的工作流程。Refer to the [Extract file](../../automating/using/extract-file.md) section.

**範例**

下列範例是從下列描述檔清單中進行的匯出：

* 顯示欄(依順序排列)：姓氏、名字、生日日期、電子郵件地址。
* 名稱依字母順序排序。

![](assets/export_list_example1.png)

產生的檔案會顯示如下(對於前10個記錄)：

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
* [設定清單視訊](https://helpx.adobe.com/campaign/kt/acs/using/acs-configuring-a-list-feature-video-setup.html)

