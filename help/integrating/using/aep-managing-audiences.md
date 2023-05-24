---
title: 管理 Adobe Experience Platform 對象
description: 瞭解如何在Campaign Standard中管理Adobe Experience Platform。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 3%

---

# 管理 Adobe Experience Platform 對象 {#about-audiences}

>[!IMPORTANT]
>
>受眾目標服務當前處於測試版，可能需要頻繁更新，恕不另行通知。 客戶需要在Azure上托管（目前僅在北美試用版）才能訪問這些功能。 如果您想訪問，請聯繫Adobe客戶服務。

## 訪問Adobe Experience Platform觀眾

要訪問Adobe Experience Platform段生成器，請導航到 **[!UICONTROL Audiences]** Campaign Standard首頁上的卡(或 **[!UICONTROL Audiences]** 連結)，然後選擇 **[!UICONTROL Adobe Experience Platform]** 環境。

![](assets/aep_audiences_access.png)

您將首先轉到Adobe Experience Platform段清單頁，在該頁可以訪問現有的Adobe Experience Platform段以進行進一步編輯。

搜索欄和過濾器可幫助您找到所需的Adobe Experience Platform段。

![](assets/aep_audiences_list.png)

## 建立Adobe Experience Platform觀眾

要直接以Campaign Standard建立Adobe Experience Platform受眾，請執行以下步驟：

1. 在「Adobe Experience Platform段」清單頁中，按一下 **[!UICONTROL New audience]** 按鈕。

   ![](assets/aep_audiences_creation_create.png)

1. 現在，段生成器應顯示在工作區中。 它允許您使用來自Adobe Experience Platform的資料構建一個段，該段最終將用於建立您的受眾。

1. 在右窗格中命名段並輸入說明（可選）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 要成功建立段，必須選擇 **合併策略** 與您的營銷目的相符。

   在設定窗格中，選擇了平台預設合併策略。 有關合併策略的詳細資訊，請參閱 [段生成器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)。

   ![](assets/aep_audiences_mergepolicy.png)

1. 定義將標識要在受眾中檢索的配置檔案的規則。

   為此，請將所需的屬性和/或事件從左窗格拖到工作區中，定義相應的規則，然後按一下 **[!UICONTROL Create segment]** 按鈕保存段(請參閱 [使用段生成器](../../integrating/using/aep-using-segment-builder.md))。

   ![](assets/aep_audiences_creation_query.png)

現在，受眾已準備好被激活，您可以將其用作您的活動的目標(請參閱 [瞄準Adobe Experience Platform觀眾](../../integrating/using/aep-targeting-audiences.md))。

## 編輯對象

要編輯受眾，請在段生成器介面中根據需要開啟並修改規則(請參閱 [使用段生成器](../../integrating/using/aep-using-segment-builder.md))。

完成更改後，按一下 **[!UICONTROL Save segment]** 按鈕來更新受眾。

![](assets/aep_audiences_editing.png)
