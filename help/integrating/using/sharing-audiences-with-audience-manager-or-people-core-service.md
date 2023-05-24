---
title: 與 Audience Manager 或 People 核心服務共用對象
description: 瞭解如何在不同的Adobe Experience Cloud解決方案中導入或導出您的受眾。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 2%

---

# 與 Audience Manager 或 People 核心服務共用對象{#sharing-audiences-with-audience-manager-or-people-core-service}

## 導入受眾 {#importing-an-audience}

人員核心服務整合允許通過技術工作流將受眾直接導入Adobe Campaign，以豐富您的資料庫。 有關「人員」核心服務中的觀眾共用的詳細資訊，請參閱此 [文檔](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

從Adobe Campaign的人員核心服務中引進受眾/部分可從 **[!UICONTROL Audiences]** 菜單僅由通過IMS(通過Adobe ID進行身份驗證)連接的用戶進行。

1. 轉到 **[!UICONTROL Audiences]** 的子菜單。
1. 在操作欄中，選擇 **[!UICONTROL Create]** 以建立觀眾。
1. 指定新受眾的標籤。
1. 設定受眾 **[!UICONTROL Type]** 至 **[!UICONTROL Experience Cloud]** 以指示所建立的受眾是從「人員」核心服務中導入的受眾。
1. 從 **[!UICONTROL Name of the shared audience]** 的子菜單。 只能導入段。 不支援包含鍵值對、特徵和規則的粒度資料。

   ![](assets/aam_import_audience.png)

1. 選擇相應 **[!UICONTROL Shared Data Source]**。

   如果將所選資料源配置為使用加密算法，則另外一個選項將提供 **[!UICONTROL Force reconciliation with a profile]**。 如果 **[!UICONTROL Channel]** 資料源的欄位設定為「電子郵件」或「移動」(SMS)，如果您想利用配置檔案資料。

   如果未選擇 **[!UICONTROL Force reconciliation with a profile]** 如果 **[!UICONTROL Channel]** 在AMC資料源中將其設定為電子郵件或移動(SMS)，然後對所有加密的聲明ID進行解密。 類型的受眾 **檔案** 建立/更新所有電子郵件地址/行動電話號碼的清單。 這樣，通過此整合導入共用受眾時，即使市場活動中不存在該配置檔案，也不會丟失電子郵件地址/行動電話號碼。 請注意，此類受眾不能直接使用，因為需要使用工作流手動對帳。

1. 確認建立受眾。

   然後通過技術工作流導入受眾。 它由ID（「訪問者ID」或「聲明的ID」）能夠與配置檔案維進行協調的記錄組成。 Adobe Campaign未識別的People核心服務段的ID不會導入。

您的受眾現在已導入到您的Adobe Campaign資料庫中。 當從人員核心服務或Audience Manager直接導入段時，導入過程需要24至36小時才能同步。 在這段時間之後，你將能夠在Adobe Campaign找到並使用你的新觀眾。

>[!NOTE]
>
>如果您要將觀眾從Adobe Analytics引入Adobe Campaign，這些觀眾首先需要在人員核心服務或Audience Manager中共用。 此過程需要12-24小時，必須添加到24-36小時與市場活動的同步中。 在這種特定情況下，觀眾共用時間最長可達60小時。 有關「人員核心服務」和「受眾經理」中Adobe Analytics受眾共用的詳細資訊，請參閱此 [文檔](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)。

## 導出受眾 {#exporting-an-audience}

可以使用工作流將受眾從Adobe Campaign導出到Audience Manager或人員核心服務， **[!UICONTROL Save audience]** 的子菜單。

它只能由通過IMS(通過Adobe ID進行認證)連接的用戶在新的工作流中執行。

1. 從方案、市場活動或市場營銷活動清單建立新工作流。
1. 使用可用的不同活動，將一組配置檔案作為目標。
1. 在目標後，拖放 **[!UICONTROL Save audience]** 活動，然後將其開啟。
1. 選取 **[!UICONTROL Share in Adobe Experience Cloud]**。

   ![](assets/aam_save_audience_activity.png)

1. 使用 **[!UICONTROL Shared audience]** 的子菜單。 在開啟的窗口中，您可以選擇選擇現有受眾或建立新受眾：

   * 如果選擇現有受眾，則只會將新記錄添加到受眾。
   * 要將個人資料清單導出到新受眾，請完成 **[!UICONTROL Segment name]** 按一下 **[!UICONTROL Create]** 選擇新建立的受眾。

   ![](assets/aam_save_audience_segment_picker.png)

   為了協調和交換，記錄必須具有Adobe Experience CloudID（「訪問者ID」或「聲明的ID」）。 在導入和導出訪問群體時忽略未協調的記錄。

1. 要完成，請按一下螢幕右上角的複選標籤。
1. 選擇相應 **[!UICONTROL Shared Data Source]**。
1. 如果你願意，查查 **[!UICONTROL Generate an outbound transition]** 框，以使用導出的配置檔案。 只導出可對帳的配置檔案。
1. 確認活動的配置並保存工作流。
1. 啟動工作流以導出受眾。 Adobe Campaign與人員核心服務之間的同步可能需要數小時

Adobe Campaign與人員核心服務之間的同步需要24-36小時。 在此期間後，您將能夠在人員核心服務中找到新的受眾，並將其重新用於其他Adobe Experience Cloud解決方案。 有關在Adobe人核心服務中使用Adobe Campaign共用受眾的詳細資訊，請參閱此 [文檔](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html)。

**相關主題：**

* [工作流程](../../automating/using/get-started-workflows.md)
* [對象](../../audiences/using/about-audiences.md)
