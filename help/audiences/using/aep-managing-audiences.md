---
title: 管理閱聽眾
description: 瞭解如何在Campaign standard中管理Adobe Experience Platform。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 19b22fa0780a0bf7c4b7a559270d7c8b32d89e38

---


# 管理閱聽眾 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations service目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上代管（目前僅限北美地區測試版）才能存取這些功能。 如果您想要存取，請聯絡Adobe客戶服務。

## 存取觀眾

若要存取Adobe Experience platform觀眾，請選取Campaign standard首 **[!UICONTROL Audiences]**頁上的資訊卡或連結，**[!UICONTROL Audiences]** 然後選取 **[!UICONTROL Adobe Experience Platform]**。

![](assets/aep_audiences_access.png)

所有建立的Adobe Experience platform觀眾都會顯示。 搜尋列和篩選器可協助您找到所需的對象。

![](assets/aep_audiences_list.png)

## 建立閱聽眾

觀眾是直接從Adobe Experience platform觀眾清單中建立的。 若要這麼做，請依照下列步驟進行：

1. 前往對象清單，然後按一下 **[!UICONTROL New audience]**按鈕。

   ![](assets/aep_audiences_creation_create.png)

1. 「統一區段產生器」現在應會顯示在您的工作區中。 它可讓您使用Adobe Experience platform中的資料來建立細分，這些資料最終將用來建立您的觀眾。

1. 在右窗格中為區段命名，並輸入說明（選用）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 若要成功建立區段，您必須選取符合 **此區段行銷目的的合** 並原則。

   在設定窗格中，會選取「平台」預設合併原則。 如需合併原則的詳細資訊，請參閱「區段產生器」使用指南中 [的專屬章節](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)

   ![](assets/aep_audiences_mergepolicy.png)

1. 定義規則，以識別要在觀眾中擷取的個人檔案。

   若要這麼做，請從左窗格拖曳所要的屬性和／或事件至工作區，定義對應的規則，然後按一下按鈕以儲存區段(請參 **[!UICONTROL Create segment]**閱[使用統一區段產生器](../../audiences/using/aep-using-segment-builder.md))。

   ![](assets/aep_audiences_creation_query.png)

觀眾現在已準備好要啟動，您可將其用作促銷活動的目標(請參閱「定 [位Adobe Experience platform觀眾](../../automating/using/aep-targeting-audiences.md)」)。

## 編輯觀眾

若要編輯對象，請視需要在「統一區段產生器」介面中開啟並修改規則(請 [參閱使用統一區段產生器](../../audiences/using/aep-using-segment-builder.md))。

變更完成後，按一下按鈕 **[!UICONTROL Save segment]**以更新您的觀眾。

![](assets/aep_audiences_editing.png)
