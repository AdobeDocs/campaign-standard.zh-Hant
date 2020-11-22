---
solution: Campaign Standard
product: campaign
title: 方案與行銷活動
description: 在 Adobe Campaign 中，計畫和行銷活動可讓您對連結到它們的不同行銷活動進行分組和協調。方案和行銷活動的報表可讓您分析其影響。
audience: start
content-type: reference
topic-tags: marketing-plans
context-tags: campaign,overview;campaignExplorer,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 100%

---


# 方案與行銷活動{#programs-and-campaigns}

## 關於計畫、方案和行銷活動 {#about-plans--programs-and-campaigns}

Adobe Campaign 可讓您規劃行銷活動，以便建立和管理不同類型的活動：電子郵件、簡訊、推播通知、工作流程、登錄頁面。可將這些行銷活動及其內容收集到方案中。

方案和行銷活動可讓您重新分組並檢視連結到它們的不同行銷活動。

* **方案**&#x200B;可能包含其他方案，以及行銷活動、工作流程和登錄頁面。它會出現在時間表中，並協助您組織行銷活動：您可以依國家、品牌、單位等進行區隔。
* **行銷活動**&#x200B;可讓您在單一實體下收集您選取的所有行銷活動。行銷活動可能包含電子郵件、簡訊、推播通知、直接郵件、工作流程和登錄頁面。

為了更妥善地組織您的行銷計畫，Adobe 建議使用下列階層：方案 > 子方案 > 行銷活動 > 工作流程 > 傳送。

方案和行銷活動的報表可讓您分析其影響。例如，您可以在行銷活動層級建立報表，以彙總該行銷活動中包含之所有傳送的資料。

**相關主題：**

* [時間表](../../start/using/timeline.md)
* [關於動態報告](../../reporting/using/about-dynamic-reports.md)

## 建立方案 {#creating-a-program}

該方案是組織的第一級。它可包含子方案、行銷活動、工作流程或登錄頁面。

1. 從 Adobe Campaign 首頁，選取 **[!UICONTROL Programs & Campaigns]** 資訊卡。
1. 按一下 **[!UICONTROL Create]** 按鈕。
1. 在 **[!UICONTROL Creation mode]** 畫面中，選取方案類型。

   ![](assets/programs_and_campaigns_2.png)

   可用的方案類型是以 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Program templates]** 區段中定義的範本為基礎而提供。如需詳細資訊，請參閱[管理範](../../start/using/marketing-activity-templates.md)本區段。

1. 在 **[!UICONTROL Properties]** 畫面中，輸入方案的名稱和 ID。

   ![](assets/programs_and_campaigns_3.png)

1. 選取方案的開始和結束日期。這些日期只適用於方範本身。

   您可以在父方案中建立方案。要執行此操作，請從現有方案中選取父方案。

1. 按一下 **[!UICONTROL Create]** 以確認建立方案。

方案隨即建立並顯示。使用 **[!UICONTROL Create]** 按鈕可新增子方案、行銷活動、工作流程或登錄頁面。

>[!NOTE]
>
>您也可以從行銷活動清單中建立方案。

## 建立行銷活動 {#creating-a-campaign}

在方案和子方案中，您可以新增行銷活動。行銷活動可包含行銷活動，例如電子郵件、簡訊、推播通知、工作流程和登錄頁面。

1. 從Adobe Campaign首頁，選取資訊卡 **[!UICONTROL Programs & Campaigns]** 並存取方案或子方案。
1. 按一下 **[!UICONTROL Create]** 按鈕並選取 **[!UICONTROL Campaign]**。
1. 在 **[!UICONTROL Creation mode]** 畫面中，選取行銷活動類型。

   ![](assets/programs_and_campaigns_7.png)

   可用的行銷活動類型是以 **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Campaign templates]** 中定義的範本為基礎而提供。如需詳細資訊，請參閱[管理範](../../start/using/marketing-activity-templates.md)本區段。

1. 在 **[!UICONTROL Properties]** 畫面中，輸入行銷活動的名稱和ID。
1. 選取行銷活動的開始和結束日期。這些日期僅適用於行銷活動本身。

   ![](assets/programs_and_campaigns_8.png)

1. 按一下 **[!UICONTROL Create]** 以確認行銷活動的建立。

行銷活動會建立並顯示。使用 **[!UICONTROL Create]** 按鈕，將行銷活動新增至行銷活動。

>[!NOTE]
>
>根據您的授權合約，您只能存取其中的部分活動。

您也可以從行銷活動清單建立行銷活動。您可以選取透過行銷活動的屬性視窗，將行銷活動連結至父方案或子方案。

## 方案和行銷活動圖示和狀態 {#programs-and-campaigns-icons-and-statuses}

清單中的每個方案和每個行銷活動都有視覺符號和圖示，其顏色代表執行狀態。此狀態會視方案或行銷活動的有效期而定。

* 灰色：方案/行銷活動尚未開始 – **[!UICONTROL Editing]** 狀態。
* 藍色：方案/行銷活動正在進行中 – **[!UICONTROL In progress]** 狀態。
* 綠色：方案/行銷活動已完成 – **[!UICONTROL Finished]** 狀態。依預設，目前日期會自動顯示為有效開始日期，而結束日期會根據開始日期（**D+186 天**）計算。您可以在方案或行銷活動屬性中變更這些日期。

![](assets/programs_and_campaigns.png)

