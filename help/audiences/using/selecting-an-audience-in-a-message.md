---
title: 在訊息中選取對象
description: "選取電子郵件對象的逐步程序：主要目標母體及測試設定檔。"
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: deliveryCreation,wizard;delivery,audience,back
feature: Audiences
role: User
level: Intermediate
exl-id: 239959ad-6386-42bf-a86a-5694cdaecd83
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 74%

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

   目標會在　**[!UICONTROL Target]**　標籤中定義，而且是由資料庫中識別的設定檔組成。您可以使用[查詢編輯器](../../automating/using/editing-queries.md#creating-queries)功能來建立主要目標。

   在此標籤中，**[!UICONTROL Shortcuts]**　浮動視窗僅包含預先定義的篩選條件，以及在已識別設定檔中定義的對象。**[!UICONTROL Explorer]** 選項可讓您存取其他設定。

   因此，您可以重複使用和結合現有的對象，對其套用其他篩選器等。

   >[!NOTE]
   >
   >當針對受眾時，請注意，未引用受眾的定義，但 **複製** 的雙曲餘切值。 如果在訪問群體成為查詢目標後對其進行了任何更改，請確保再次配置該查詢以將新定義考慮在內。

1. 定義您要用於電子郵件的　**[!UICONTROL Test profiles]**。測試設定檔會收到您之前可以傳送的校樣，以便先測試電子郵件，然後再將之傳送給主要目標。

   如需設定測試設定檔的詳細資訊，請參閱[測試設定檔](../../audiences/using/managing-test-profiles.md)區段。

1. 如果需要，可以使用相應的頁籤定義控制組。 這樣，您就可以從目標中取出一些配置檔案，這樣他們就不會收到消息。 有關此的詳細資訊，請參閱 [添加控制組](../../sending/using/control-group.md)。

1. 您還可以使用替代地址來獲取配置檔案將接收的消息的準確表示形式。  如需詳細資訊，請參閱[使用目標設定檔測試電子郵件訊息](../../sending/using/testing-messages-using-target.md)。

接著會更新對象區塊，並顯示已針對有問題的電子郵件選取目標和測試設定檔。

![](assets/delivery_audience_definition_3.png)
