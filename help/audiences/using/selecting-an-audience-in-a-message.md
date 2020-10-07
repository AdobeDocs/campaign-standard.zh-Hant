---
title: 在訊息中選取對象
description: '"選取電子郵件對象的逐步程序：主要目標母體及測試設定檔。"'
page-status-flag: never-activated
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 在訊息中選取對象{#selecting-an-audience-in-a-message}

Adobe Campaign　可讓您在訊息的對象中設定數個設定檔類型。

可透過建立精靈或是從訊息控制面板（若已建立訊息）定義對象。

>[!NOTE]
>
>如果對象是在工作流程中建立並且富含其他資料，您將無法使用這些資料來個人化獨立傳送。它們只能從在工作流程中執行的傳送中使用。

1. 從控制面板，移至對象區塊以開始。

   ![](assets/delivery_audience_definition_1.png)

   定義對象的畫面隨即開啟。它有兩個標籤，可讓您分別定義將收到訊息的每個對象類型：

   * 目標
   * 測試設定檔

   ![](assets/delivery_audience_definition_2.png)

1. 定義電子郵件的主要　**[!UICONTROL Target]**　功能。這是電子郵件的一般目標對象。

   目標會在　**[!UICONTROL Target]**　標籤中定義，而且是由資料庫中識別的設定檔組成。

   您可以使用[查詢編輯器](../../automating/using/editing-queries.md#creating-queries)功能來建立主要目標。

   在此標籤中，**[!UICONTROL Shortcuts]**　浮動視窗僅包含預先定義的篩選條件，以及在已識別設定檔中定義的對象。**[!UICONTROL Explorer]** 選項可讓您存取其他設定。

   因此，您可以重複使用和結合現有的對象，對其套用其他篩選器等。

1. 定義您要用於電子郵件的　**[!UICONTROL Test profiles]**。測試設定檔會收到您之前可以傳送的校樣，以便先測試電子郵件，然後再將之傳送給主要目標。

   如需設定測試設定檔的詳細資訊，請參閱[測試設定檔](../../audiences/using/managing-test-profiles.md)區段。

1. 如有需要，您可以使用對應的標籤定義控制組。 這可讓您從目標中取出一些描述檔，以免他們收到訊息。 For more on this, see [Adding a control group](../../sending/using/control-group.md).

1. 您也可以使用替代地址獲得描述檔將收到的消息的精確表示。  如需詳細資訊，請參閱[使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)。

接著會更新對象區塊，並顯示已針對有問題的電子郵件選取目標和測試設定檔。

![](assets/delivery_audience_definition_3.png)

