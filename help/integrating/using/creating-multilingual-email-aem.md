---
title: 使用Adobe Experience Manager整合建立多語言電子郵件。
description: 透過Adobe Experience Manager整合，您可以直接在AEM中建立內容，並稍後在Adobe Campaign中使用。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 3%

---

# 使用 Adobe Experience Manager 整合建立多語言電子郵件 {#creating-multilingual-email-aem}

透過此檔案，您將瞭解如何使用Adobe Experience Manager內容和語言副本建立多語言電子郵件。

先決條件為：

* 存取為整合設定的AEM執行個體。
* 存取為整合設定的Adobe Campaign執行個體。
* 設定為可接收AEM內容的Adobe Campaign多語言電子郵件範本。

## 在Adobe Experience Manager中建立新的電子郵件內容 {#creating-email-content-aem}

1. 從Adobe Experience Manager首頁選取&#x200B;**[!UICONTROL Site]**。

   ![](assets/aem_acs_1.png)

1. 選取您要建立頁面的資料夾，然後按一下&#x200B;**[!UICONTROL Create]**、**[!UICONTROL Page]**。 在此，我們在en_us資料夾中建立頁面，此資料夾將是我們的預設語言。

   ![](assets/aem_acs_2.png)

1. 選取&#x200B;**[!UICONTROL Adobe Campaign Email (ACS)]**&#x200B;範本。

1. 填寫電子郵件的內容，然後按一下&#x200B;**[!UICONTROL Create]**。

   ![](assets/aem_acs_3.png)

1. 開啟您的新電子郵件內容，並視需要加以個人化。 如需關於此項目的詳細資訊，請參閱此[頁面](../../integrating/using/creating-email-experience-manager.md#editing-email-aem)。

   ![](assets/aem_acs_4.png)

1. 從&#x200B;**[!UICONTROL Workflow]**&#x200B;索引標籤中，選取&#x200B;**[!UICONTROL Approve for Adobe Campaign]**&#x200B;驗證工作流程。 如果您使用Adobe Campaign中尚未核准的內容，將無法傳送電子郵件。

   ![](assets/aem_acs_7.png)

1. 從&#x200B;**[!UICONTROL Complete work item]**&#x200B;視窗按一下&#x200B;**[!UICONTROL Complete]**，然後按一下&#x200B;**[!UICONTROL Newsletter review]**。

1. 按一下&#x200B;**[!UICONTROL Complete]**，然後再按&#x200B;**[!UICONTROL Newsletter approval]**。 定義內容和傳送引數後，您可以在Adobe Campaign Standard中繼續核准、準備和傳送電子郵件。

   ![](assets/aem_acs_8.png)

## 建立語言副本 {#creating-language-copies}

設計電子郵件內容後，您現在需要建立語言副本，並以變體形式與Adobe Campaign Standard同步。

1. 選取您先前建立的頁面，按一下&#x200B;**[!UICONTROL Create]**、**[!UICONTROL Language Copy]**。

   ![](assets/aem_acs_5.png)

1. 選取您先前建立的電子郵件內容，這些內容將以選擇的語言翻譯，然後按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/aem_acs_6.png)

1. 在&#x200B;**[!UICONTROL Target language(s)]**&#x200B;下拉式清單中，選取將翻譯內容的語言，然後按一下&#x200B;**[!UICONTROL Next]**。

   ![](assets/aem_acs_9.png)

1. 按一下&#x200B;**[!UICONTROL Create]**。

您的語言副本現已建立，您現在可以根據所選的語言編輯內容。

>[!CAUTION]
>
>每個語言副本都必須透過&#x200B;**[!UICONTROL Approve for Adobe Campaign]**&#x200B;驗證工作流程核准。 如果您使用Adobe Campaign中尚未核准的內容，將無法傳送電子郵件。

![](assets/aem_acs_11.png)

## 在Adobe Campaign Standard中建立您的多語言內容 {#multilingual-acs}

1. 從Adobe Campaign Standard首頁，按一下&#x200B;**[!UICONTROL Create an email]**。

   ![](assets/aem_acs_12.png)

1. 選取您設定為接收Adobe Experience Manager內容的Adobe Campaign多語言電子郵件範本。 若要深入瞭解如何建立連結至您Adobe Experience Manager執行個體的範本，請參閱此[頁面](../../integrating/using/configure-experience-manager.md#config-acs)。

   >[!NOTE]
   >
   >在此情況下，您需要複製內建範本&#x200B;**[!UICONTROL Multilingual email (mailMultiLang)]**&#x200B;才能傳送您的多語言電子郵件。

   ![](assets/aem_acs_13.png)

1. 填寫您電子郵件的&#x200B;**[!UICONTROL Properties]**&#x200B;和&#x200B;**[!UICONTROL Audience]**，然後按一下&#x200B;**[!UICONTROL Create]**。

1. 在&#x200B;**[!UICONTROL Edit properties]**&#x200B;中，確定已在&#x200B;**[!UICONTROL Content]**&#x200B;下拉式清單中正確設定您的Adobe Experience Manager帳戶。

   ![](assets/aem_acs_20.png)

1. 按一下&#x200B;**[!UICONTROL Language copy creation]**。

   ![](assets/aem_acs_16.png)

1. 選取您先前建立的Adobe Experience Manager內容，然後按一下&#x200B;**[!UICONTROL Confirm]**。 此處顯示的Adobe Experience Manager內容僅為已驗證的內容，且可在其&#x200B;**[!UICONTROL Label]**&#x200B;和&#x200B;**[!UICONTROL Path]**&#x200B;上篩選。

   >[!NOTE]
   >
   >所選的語言副本將設定為預設值，您稍後可以在&#x200B;**[!UICONTROL Content variant]**&#x200B;區塊中加以變更。

   ![](assets/aem_acs_17.png)

1. 按一下&#x200B;**[!UICONTROL Create variants]**&#x200B;以連結您的多語言內容。 Adobe Campaign Standard會自動將其他語言副本連結至此內容。 建立的變體將與Adobe Experience Manager中選擇的變體具有相同的標籤和程式碼語言。

   ![](assets/aem_acs_18.png)

1. 視需要按一下&#x200B;**[!UICONTROL Content variant]**&#x200B;區塊以變更您的預設變體，然後按一下&#x200B;**[!UICONTROL Confirm]**。

   ![](assets/aem_acs_19.png)

1. 若您的內容或變體已在Adobe Experience Manager中更新，您可以使用&#x200B;**[!UICONTROL Refresh AEM contents]**&#x200B;按鈕直接在Adobe Campaign Standard中同步化。

1. 您的電子郵件現在已可供傳送。 如需詳細資訊，請參閱此[頁面](../../sending/using/get-started-sending-messages.md)。

   >[!NOTE]
   >
   >如果電子郵件使用Adobe Campaign中尚未核准的AEM內容，您將無法在AEM中傳送電子郵件。

您的對象將依據其&#x200B;**[!UICONTROL Profiles]**&#x200B;中設定的&#x200B;**[!UICONTROL Preferred languages]**&#x200B;收到您的電子郵件。 若要進一步瞭解如何編輯設定檔和慣用語言，請參閱此[頁面](../../audiences/using/editing-profiles.md)。
