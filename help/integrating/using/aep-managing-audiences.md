---
solution: Campaign Standard
product: campaign
title: 管理 Adobe Experience Platform 閱聽眾
description: 了解如何透過Campaign Standard管理Adobe Experience Platform。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM整合
role: Data Architect
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---

# 管理 Adobe Experience Platform 閱聽眾 {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations服務目前為測試版，可能會經常更新，恕不另行通知。 客戶必須在Azure上托管（目前測試版僅供北美使用），才能存取這些功能。 如果您想要存取權限，請聯絡Adobe客戶服務。

## 存取Adobe Experience Platform對象

若要存取Adobe Experience Platform區段產生器，請導覽至Campaign Standard首頁的&#x200B;**[!UICONTROL Audiences]**&#x200B;卡片（或標題中的&#x200B;**[!UICONTROL Audiences]**&#x200B;連結），然後選取&#x200B;**[!UICONTROL Adobe Experience Platform]**&#x200B;環境。

![](assets/aep_audiences_access.png)

系統會先將您導向至Adobe Experience Platform區段清單頁面，您可在其中存取現有的Adobe Experience Platform區段以進行進一步編輯。

搜尋列和篩選器可協助您尋找所需的Adobe Experience Platform區段。

![](assets/aep_audiences_list.png)

## 建立Adobe Experience Platform對象

若要直接在Campaign Standard中建立Adobe Experience Platform對象，請執行下列步驟：

1. 從Adobe Experience Platform區段清單頁面，按一下右角的&#x200B;**[!UICONTROL New audience]**&#x200B;按鈕。

   ![](assets/aep_audiences_creation_create.png)

1. 「區段產生器」現在應會顯示在您的工作區中。 它可讓您使用Adobe Experience Platform中的資料來建立區段，這些資料最終將用來建立您的對象。

1. 在右窗格中為區段命名，並輸入說明（選用）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 若要成功建立區段，您必須選取符合您對此區段之行銷目的的&#x200B;**合併原則**。

   在設定窗格中，選取平台預設合併原則。 如需合併原則的詳細資訊，請參閱[區段產生器使用手冊](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)中的專屬區段。

   ![](assets/aep_audiences_mergepolicy.png)

1. 定義規則以識別要在您的對象中擷取的設定檔。

   若要這麼做，請從左窗格將所需的屬性和/或事件拖曳至工作區中，定義對應的規則，然後按一下&#x200B;**[!UICONTROL Create segment]**&#x200B;按鈕以儲存區段（請參閱[使用區段產生器](../../integrating/using/aep-using-segment-builder.md)）。

   ![](assets/aep_audiences_creation_query.png)

對象現在已可供啟用，您可以將其用作行銷活動的目標(請參閱[鎖定Adobe Experience Platform對象](../../integrating/using/aep-targeting-audiences.md))。

## 編輯對象

若要編輯對象，請視需要在「區段產生器」介面中開啟對象並修改規則（請參閱[使用區段產生器](../../integrating/using/aep-using-segment-builder.md)）。

變更完成後，按一下&#x200B;**[!UICONTROL Save segment]**&#x200B;按鈕以更新您的對象。

![](assets/aep_audiences_editing.png)
