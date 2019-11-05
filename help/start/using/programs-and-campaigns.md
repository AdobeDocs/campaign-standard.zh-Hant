---
title: 方案與宣傳活動
description: 在Adobe Campaign中，計畫和促銷活動可讓您對連結到它們的不同行銷活動進行分組和協調。 方案和促銷活動的報表可讓您分析其影響。
page-status-flag: 從未激活
uuid: fe2812a8-196f-4aba-a739-fbfffd754cb
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: 參考
topic-tags: 行銷計畫
discoiquuid: 21b84028-d1a7-4ad6-891a-862a94565514
context-tags: campaign,overview;campaignExplorer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 方案與宣傳活動{#programs-and-campaigns}

## 關於計畫、計畫和宣傳 {#about-plans--programs-and-campaigns}

Adobe Campaign可讓您規劃行銷宣傳，以便建立和管理不同類型的活動：電子郵件、簡訊、推播通知、工作流程、登陸頁面。 這些促銷活動及其內容可收集到程式中。

方案和促銷活動可讓您重新分組並檢視連結到它們的不同行銷活動。

* 程 **式可能** 包含其他程式，以及促銷活動、工作流程和著陸頁面。 它會出現在時間軸中，並協助您組織行銷活動：您可以依國家、品牌、單位等區隔。
* 促銷 **活動** ，可讓您在單一實體下收集您選擇的所有行銷活動。 促銷活動可能包含電子郵件、簡訊、推播通知、直接郵件、工作流程和登陸頁面。

為了更好地組織您的行銷計畫，Adobe建議使用下列階層：方案&gt;子方案&gt;促銷活動&gt;工作流程&gt;傳送。

方案和促銷活動的報表可讓您分析其影響。 例如，您可以在促銷活動層級建立報表，以匯總該促銷活動中包含之所有傳送的資料。

**相關主題：**

* [時間表](../../start/using/timeline.md)
* [關於動態報告](../../reporting/using/about-dynamic-reports.md)

## 建立程式 {#creating-a-program}

該計畫是組織的第一級。 它可包含子程式、促銷活動、工作流程或登陸頁面。

1. 從Adobe Campaign首頁，選取資 **[!UICONTROL Programs & Campaigns]** 訊卡。
1. 按一下按 **[!UICONTROL Create]** 鈕。
1. 在螢幕 **[!UICONTROL Creation mode]** 中，選擇程式類型。

   ![](assets/programs_and_campaigns_2.png)

   可用的程式類型基於「 &gt; &gt; 」部分中定 **[!UICONTROL Resources]** 義的 **[!UICONTROL Templates]** 模 **[!UICONTROL Program templates]** 板。 有關詳細資訊，請參閱「管 [理模板](../../start/using/about-templates.md) 」部分。

1. 在螢幕 **[!UICONTROL Properties]** 中，輸入程式的名稱和ID。

   ![](assets/programs_and_campaigns_3.png)

1. 選擇方案的開始和結束日期。 這些日期只適用於程式本身。

   您可以在父程式中建立程式。 要執行此操作，請從現有程式中選擇父程式。

1. 按一下 **[!UICONTROL Create]** 確認程式的建立。

程式隨即建立並顯示。 使用按 **[!UICONTROL Create]** 鈕可新增子程式、促銷活動、工作流程或著陸頁面。

>[!NOTE]
>
>您也可以從行銷活動清單中建立方案。

## 建立促銷活動 {#creating-a-campaign}

在方案和子方案中，您可以新增促銷活動。 促銷活動可包含行銷活動，例如電子郵件、簡訊、推播通知、工作流程和登陸頁面。

1. 從Adobe Campaign首頁，選取資訊卡 **[!UICONTROL Programs & Campaigns]** 並存取方案或子方案。
1. 按一下按 **[!UICONTROL Create]** 鈕並選取 **[!UICONTROL Campaign]**。
1. 在畫面 **[!UICONTROL Creation mode]** 中，選取促銷活動類型。

   ![](assets/programs_and_campaigns_7.png)

   可用的促銷活動類型是以「 &gt; &gt;」中定義的 **[!UICONTROL Resources]** 范 **[!UICONTROL Templates]** 本為基礎 **[!UICONTROL Campaign templates]**。 有關詳細資訊，請參閱「管 [理模板](../../start/using/about-templates.md) 」部分。

1. 在畫面 **[!UICONTROL Properties]** 中，輸入促銷活動的名稱和ID。
1. 選擇促銷活動的開始和結束日期。 這些日期僅適用於促銷活動本身。

   ![](assets/programs_and_campaigns_8.png)

1. 按一下 **[!UICONTROL Create]** 以確認促銷活動的建立。

促銷活動會建立並顯示。 使用按 **[!UICONTROL Create]** 鈕將行銷活動新增至促銷活動。

>[!NOTE]
>
>視您的授權合約而定，您只能存取其中部分活動。

您也可以從行銷活動清單建立促銷活動。 您可以選擇透過促銷活動的屬性視窗，將行銷活動連結至父項方案或子方案。

## 方案和促銷活動圖示和狀態 {#programs-and-campaigns-icons-and-statuses}

清單中的每個程式和每個促銷活動都有視覺符號和圖示，其顏色代表執行狀態。 此狀態取決於方案或促銷活動的有效期。

* 灰色：方案／促銷活動尚未開始——狀 **[!UICONTROL Editing]** 態。
* 藍色：方案／促銷活動正在進行中——狀 **[!UICONTROL In progress]** 態。
* 綠色：方案／促銷活動已完成——狀 **[!UICONTROL Finished]** 態。 依預設，目前日期會自動顯示為有效開始日期，而結束日期會根據開始日期(**D+186天**)計算。 您可以在方案或促銷活動屬性中變更這些日期。

![](assets/programs_and_campaigns.png)

