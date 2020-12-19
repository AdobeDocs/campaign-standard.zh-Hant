---
solution: Campaign Standard
product: campaign
title: 管理 Adobe Experience Platform 閱聽眾
description: 瞭解如何在Campaign Standard中管理Adobe Experience Platform。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---


# 管理 Adobe Experience Platform 閱聽眾 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Service目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

## 存取Adobe Experience Platform受眾

若要存取Adobe Experience Platform區段產生器，請導覽至Campaign Standard首頁上的&#x200B;**[!UICONTROL Audiences]**&#x200B;資訊卡（或標題中的&#x200B;**[!UICONTROL Audiences]**&#x200B;連結），然後選取&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;環境。

![](assets/aep_audiences_access.png)

您會先被導向至Adobe Experience Platform區段清單頁面，您可在該頁面存取現有的Adobe Experience Platform區段以進一步編輯。

搜尋列和篩選器可協助您尋找所需的Adobe Experience Platform區段。

![](assets/aep_audiences_list.png)

## 建立Adobe Experience Platform受眾

若要直接在Campaign Standard中建立Adobe Experience Platform觀眾，請遵循下列步驟：

1. 從Adobe Experience Platform區段清單頁面，按一下位於右角的&#x200B;**[!UICONTROL New audience]**&#x200B;按鈕。

   ![](assets/aep_audiences_creation_create.png)

1. 「區段產生器」現在應會顯示在您的工作區中。 它可讓您使用Adobe Experience Platform中的資料來建立細分，這些資料最終將用來建立您的觀眾。

1. 在右窗格中為區段命名，並輸入說明（選用）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 若要成功建立區段，您必須選擇符合此區段行銷目的的&#x200B;**合併原則**。

   在設定窗格中，會選取「平台」預設合併原則。 有關合併策略的詳細資訊，請參閱[區段產生器使用手冊](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)中的專用部分。

   ![](assets/aep_audiences_mergepolicy.png)

1. 定義規則，以識別要在觀眾中擷取的個人檔案。

   若要這麼做，請從左窗格拖曳所要的屬性和／或事件至工作區，定義對應的規則，然後按一下&#x200B;**[!UICONTROL Create segment]**&#x200B;按鈕以儲存區段（請參閱[使用區段產生器](../../audiences/using/aep-using-segment-builder.md)）。

   ![](assets/aep_audiences_creation_query.png)

觀眾現在已準備好要啟動，您可將其用作促銷活動的目標（請參閱[定位Adobe Experience Platform觀眾](../../automating/using/aep-targeting-audiences.md)）。

## 編輯對象

若要編輯對象，請視需要在「區段產生器」介面中開啟並修改規則（請參閱「使用區段產生器」[）。](../../audiences/using/aep-using-segment-builder.md)

變更完成後，按一下&#x200B;**[!UICONTROL Save segment]**&#x200B;按鈕以更新您的觀眾。

![](assets/aep_audiences_editing.png)
