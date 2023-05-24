---
title: 使用 Adobe Experience Manager 整合建立多語言電子郵件.
description: 通過Adobe Experience Manager整合，您可以直接在中創AEM建內容，稍後在Adobe Campaign使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 5%

---

# 使用 Adobe Experience Manager 整合建立多語言電子郵件 {#creating-multilingual-email-aem}

使用此文檔，您將學習如何使用Adobe Experience Manager內容和語言副本建立多語言電子郵件。

先決條件為：

* 對為集AEM成配置的實例的訪問。
* 訪問為整合配置的Adobe Campaign實例。
* 配置為接收內容的Adobe Campaign多語言電AEM子郵件模板。

## 在Adobe Experience Manager建立新電子郵件內容 {#creating-email-content-aem}

1. 從Adobe Experience Manager首頁，選擇 **[!UICONTROL Site]**。

   ![](assets/aem_acs_1.png)

1. 選擇要在其中建立頁面的資料夾，然後按一下 **[!UICONTROL Create]** 然後 **[!UICONTROL Page]**。 在此，我們將在en_us資料夾中建立我們的頁面，該資料夾將是我們的預設語言。

   ![](assets/aem_acs_2.png)

1. 選擇 **[!UICONTROL Adobe Campaign Email (ACS)]** 的下界。

1. 填寫電子郵件的屬性，然後按一下 **[!UICONTROL Create]**。

   ![](assets/aem_acs_3.png)

1. 開啟新電子郵件內容並根據需要對其進行個性化設定。 如需關於此項目的詳細資訊，請參閱此[頁面](../../integrating/using/creating-email-experience-manager.md#editing-email-aem)。

   ![](assets/aem_acs_4.png)

1. 從 **[!UICONTROL Workflow]** 頁籤 **[!UICONTROL Approve for Adobe Campaign]** 驗證工作流。 如果Adobe Campaign使用的內容未經批准，您將無法在該地區發送電子郵件。

   ![](assets/aem_acs_7.png)

1. 按一下 **[!UICONTROL Complete]** 然後 **[!UICONTROL Newsletter review]** 從 **[!UICONTROL Complete work item]** 的子菜單。

1. 按一下 **[!UICONTROL Complete]**，之後 **[!UICONTROL Newsletter approval]**。定義內容和發送參數後，您可以在Adobe Campaign Standard繼續批准、準備和發送電子郵件。

   ![](assets/aem_acs_8.png)

## 建立語言副本 {#creating-language-copies}

設計完電子郵件內容後，您現在需要建立語言副本，這些副本將作為變體與Adobe Campaign Standard同步。

1. 選擇以前建立的頁面，按一下 **[!UICONTROL Create]** 然後 **[!UICONTROL Language Copy]**。

   ![](assets/aem_acs_5.png)

1. 選擇以前建立的電子郵件內容，這些內容將以所選語言翻譯，然後按一下 **[!UICONTROL Next]**。

   ![](assets/aem_acs_6.png)

1. 在 **[!UICONTROL Target language(s)]** 下拉框，選擇翻譯內容的語言，然後按一下 **[!UICONTROL Next]**。

   ![](assets/aem_acs_9.png)

1. 按一下&#x200B;**[!UICONTROL Create]**。

您的語言副本現在已建立，您現在可以根據所選語言編輯您的內容。

>[!CAUTION]
>
>每個語言副本都需要通過 **[!UICONTROL Approve for Adobe Campaign]** 驗證工作流。 如果Adobe Campaign使用的內容未經批准，您將無法在該地區發送電子郵件。

![](assets/aem_acs_11.png)

## 在Adobe Campaign Standard建立您的多語言內容 {#multilingual-acs}

1. 從Adobe Campaign Standard首頁，按一下 **[!UICONTROL Create an email]**。

   ![](assets/aem_acs_12.png)

1. 選擇配置為接收Adobe Campaign內容的Adobe Experience Manager多語言電子郵件模板。 有關如何建立連結到您的Adobe Experience Manager實例的模板的詳細資訊，請參閱此 [頁](../../integrating/using/configure-experience-manager.md#config-acs)。

   >[!NOTE]
   >
   >在這種情況下，您需要複製內置模板 **[!UICONTROL Multilingual email (mailMultiLang)]** 能夠發送您的多語言電子郵件。

   ![](assets/aem_acs_13.png)

1. 填寫 **[!UICONTROL Properties]** 和 **[!UICONTROL Audience]** 的 **[!UICONTROL Create]**。

1. 在 **[!UICONTROL Edit properties]**，確保在中正確設定了您的Adobe Experience Manager帳戶 **[!UICONTROL Content]** 下拉。

   ![](assets/aem_acs_20.png)

1. 按一下&#x200B;**[!UICONTROL Language copy creation]**。

   ![](assets/aem_acs_16.png)

1. 選擇您以前建立的Adobe Experience Manager內容並按一下 **[!UICONTROL Confirm]**。 此處顯示的Adobe Experience Manager內容僅是已驗證的內容，可在其上篩選 **[!UICONTROL Label]** 和 **[!UICONTROL Path]**。

   >[!NOTE]
   >
   >所選語言副本將設定為預設，您稍後可以在 **[!UICONTROL Content variant]** 框。

   ![](assets/aem_acs_17.png)

1. 按一下 **[!UICONTROL Create variants]** 連結您的多語言內容。 Adobe Campaign Standard將自動將其他語言副本連結到此內容。 建立的變型的標籤和代碼語言與在Adobe Experience Manager選擇的變型相同。

   ![](assets/aem_acs_18.png)

1. 按一下 **[!UICONTROL Content variant]** 阻止更改預設變型（如果需要），然後按一下 **[!UICONTROL Confirm]**。

   ![](assets/aem_acs_19.png)

1. 如果您的內容或變型在Adobe Experience Manager更新，您可以直接在Adobe Campaign Standard與 **[!UICONTROL Refresh AEM contents]** 按鈕

1. 您的電子郵件現在可以發送。 有關此的詳細資訊，請參閱此 [頁](../../sending/using/get-started-sending-messages.md)。

   >[!NOTE]
   >
   >如果Adobe Campaign使用的內容未經批准，則您將無AEM法在其中發送電子郵件。

您的受眾將根據 **[!UICONTROL Preferred languages]** 在他們 **[!UICONTROL Profiles]**。 有關如何編輯配置檔案和首選語言的詳細資訊，請參閱此 [頁](../../audiences/using/editing-profiles.md)。
