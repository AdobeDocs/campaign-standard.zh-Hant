---
solution: Campaign Standard
product: campaign
title: 與 Audience Manager 或 People 核心服務共用閱聽眾
description: 瞭解如何在不同的Adobe Experience Cloud解決方案中匯入或匯出您的觀眾。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: 人員核心服務整合
role: 資料架構師
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 2%

---


# 與 Audience Manager 或 People 核心服務共用閱聽眾{#sharing-audiences-with-audience-manager-or-people-core-service}

## 匯入對象{#importing-an-audience}

人員核心服務整合可讓受眾透過技術工作流程直接匯入Adobe Campaign，以豐富您的資料庫。 有關「人員」核心服務中觀眾分享的詳細資訊，請參閱本[檔案](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

只有透過IMS(透過Adobe ID驗證)連線的使用者才能從&#x200B;**[!UICONTROL Audiences]**&#x200B;功能表匯入Adobe Campaign地區「人物」核心服務的觀眾／區段。

1. 前往&#x200B;**[!UICONTROL Audiences]**&#x200B;功能表。
1. 在動作列中，選取&#x200B;**[!UICONTROL Create]**，以前往畫面建立觀眾。
1. 指定新對象的標籤。
1. 將對象&#x200B;**[!UICONTROL Type]**&#x200B;設為&#x200B;**[!UICONTROL Experience Cloud]**，以指出所建立的對象是從People核心服務匯入的對象。
1. 從&#x200B;**[!UICONTROL Name of the shared audience]**&#x200B;欄位中，選取要匯入的對象。 只能匯入區段。 不支援精細資料，包括索引鍵值配對、特徵和規則。

   ![](assets/aam_import_audience.png)

1. 選擇相應的&#x200B;**[!UICONTROL Shared Data Source]**。

   如果選定的資料源配置為使用加密算法，則附加選項可能提供&#x200B;**[!UICONTROL Force reconciliation with a profile]**。 如果資料來源的&#x200B;**[!UICONTROL Channel]**&#x200B;欄位設為「電子郵件」或「行動(SMS)」，而且您想要運用描述檔資料，請勾選此選項。

   如果您未選取&#x200B;**[!UICONTROL Force reconciliation with a profile]**，而且在AMC資料來源中設定&#x200B;**[!UICONTROL Channel]**&#x200B;為「電子郵件」或「行動」(SMS)，則所有加密的已宣告ID都會解密。 建立／更新類型&#x200B;**File**&#x200B;的觀眾，其中列出所有電子郵件地址／行動電話號碼。 如此，透過此整合匯入共用對象時，不會遺失電子郵件地址／行動電話號碼，即使該描述檔不存在於Campaign中亦然。 請注意，此類型的觀眾無法直接使用，因為需要使用工作流程手動調節觀眾。

1. 確認建立觀眾。

   然後，觀眾會透過技術工作流程匯入。 它由記錄組成，其中ID（&#39;訪客ID&#39;或&#39;Declared ID&#39;）可與描述檔維度協調。 不會匯入「人員」核心服務區段中未被Adobe Campaign識別的ID。

您的觀眾現在已匯入至您的Adobe Campaign資料庫。 從People核心服務或Audience Manager直接匯入區段時，匯入程式需要24-36小時才能同步。 在這段期間之後，您將能夠在Adobe Campaign找到並使用您的新受眾。

>[!NOTE]
>
>如果您要將觀眾從Adobe Analytics匯入Adobe Campaign，這些觀眾必須先在People Core Service或Audience Manager中共用。 此程式需要12-24小時，這必須新增至與Campaign同步的24-36小時。 在此特定情況下，觀眾分享的時間最長可達60小時。 有關「People Core」服務和「Audience Manager」中Adobe Analytics觀眾分享的詳細資訊，請參閱此[檔案](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

## 匯出對象{#exporting-an-audience}

使用工作流程和&#x200B;**[!UICONTROL Save audience]**&#x200B;活動，觀眾可從Adobe Campaign匯出至Audience Manager或人員核心服務。

它可以在新的工作流程中執行，而且只能由經由IMS(通過Adobe ID驗證)連接的用戶執行。

1. 從方案、促銷活動或行銷活動清單建立新的工作流程。
1. 使用可用的不同活動，鎖定一組描述檔。
1. 定位後，將&#x200B;**[!UICONTROL Save audience]**&#x200B;活動拖放至工作流程中，然後開啟。
1. 選取 **[!UICONTROL Share in Adobe Experience Cloud]**。

   ![](assets/aam_save_audience_activity.png)

1. 使用&#x200B;**[!UICONTROL Shared audience]**&#x200B;欄位指定對象。 在開啟的視窗中，您可以選擇選取現有對象或建立新對象：

   * 如果您選取現有對象，則只會將新記錄新增至對象。
   * 若要將您的個人檔案清單匯出至新對象，請填妥&#x200B;**[!UICONTROL Segment name]**&#x200B;欄位，然後按一下&#x200B;**[!UICONTROL Create]**，再選取新建立的對象。

   ![](assets/aam_save_audience_segment_picker.png)

   為了進行協調和交換，記錄必須有Adobe Experience CloudID（&#39;訪客ID&#39;或&#39;Declared ID&#39;）。 匯入和匯出對象時，不協調的記錄會被忽略。

1. 若要完成，請按一下位於螢幕右上角的核取標籤。
1. 選擇相應的&#x200B;**[!UICONTROL Shared Data Source]**。
1. 如果您喜歡，請選中&#x200B;**[!UICONTROL Generate an outbound transition]**&#x200B;框以使用導出的配置檔案。 僅導出可調節的配置檔案。
1. 確認活動的設定並儲存您的工作流程。
1. 啟動您的工作流程以匯出您的觀眾。 Adobe Campaign與人員核心服務的同步可能需要數小時

Adobe Campaign與人員核心服務的同步需要24-36小時。 在這段期間後，您將能夠在People核心服務中找到新的受眾，並在其他Adobe Experience Cloud解決方案中重複使用。 有關在Adobe人核心服務中使用Adobe Campaign共用觀眾的更多資訊，請參閱本[文檔](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-audience-create.html)。

**相關主題：**

* [工作流程](../../automating/using/get-started-workflows.md)
* [受眾](../../audiences/using/about-audiences.md)

