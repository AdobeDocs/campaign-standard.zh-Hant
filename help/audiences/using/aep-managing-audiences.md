---
title: 管理 Adobe Experience Platform 閱聽眾
description: 瞭解如何在Campaign Standard中管理Adobe Experience Platform。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 管理 Adobe Experience Platform 閱聽眾 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Service目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

## 存取Adobe Experience Platform受眾

若要存取Adobe Experience Platform區段產生器，請導覽至Campaign Standard首頁上的資訊卡（或頁首中的連結），然後選取 **[!UICONTROL Audiences]****[!UICONTROL Audiences]****[!UICONTROL Adobe Experience Platform]** 環境。

![](assets/aep_audiences_access.png)

您會先被導向至Adobe Experience Platform區段清單頁面，您可在該頁面存取現有的Adobe Experience Platform區段以進一步編輯。

搜尋列和篩選器可協助您尋找所需的Adobe Experience Platform區段。

![](assets/aep_audiences_list.png)

## 建立Adobe Experience Platform受眾

若要直接在Campaign Standard中建立Adobe Experience Platform觀眾，請遵循下列步驟：

1. 從Adobe Experience Platform區段清單頁面，按一 **[!UICONTROL New audience]** 下位於右角的按鈕。

   ![](assets/aep_audiences_creation_create.png)

1. 「區段產生器」現在應會顯示在您的工作區中。 它可讓您使用Adobe Experience Platform中的資料來建立細分，這些資料最終將用來建立您的觀眾。

1. 在右窗格中為區段命名，並輸入說明（選用）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 若要成功建立區段，您必須選取符合 **此區段行銷目的的合** 並原則。

   在設定窗格中，會選取「平台」預設合併原則。 如需合併原則的詳細資訊，請參閱「區段產生器」使用指 [南中的專屬章節](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)。

   ![](assets/aep_audiences_mergepolicy.png)

1. 定義規則，以識別要在觀眾中擷取的個人檔案。

   若要這麼做，請從左窗格拖曳所要的屬性和／或事件至工作區，定義對應的規則，然後按一下按鈕以儲存區段(請 **[!UICONTROL Create segment]** 參閱 [使用區段產生器](../../audiences/using/aep-using-segment-builder.md))。

   ![](assets/aep_audiences_creation_query.png)

觀眾現在已準備好要啟動，您可將其用作促銷活動的目標(請參閱「定 [位Adobe Experience Platform觀眾](../../automating/using/aep-targeting-audiences.md)」)。

## 編輯對象

若要編輯對象，請視需要在「區段產生器」介面中開啟並修改規則(請 [參閱使用區段產生器](../../audiences/using/aep-using-segment-builder.md))。

變更完成後，按一下按鈕 **[!UICONTROL Save segment]** 以更新您的觀眾。

![](assets/aep_audiences_editing.png)
