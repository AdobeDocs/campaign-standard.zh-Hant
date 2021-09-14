---
title: SDK v4行動應用程式移轉至Adobe Experience Platform SDK
description: 本檔案可讓您將行動應用程式從SDK v4移轉至Adobe Experience Platform SDK
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 1%

---

# 如何將您的行動應用程式從 SDK v4 移轉至 Adobe Experience Platform SDK {#sdkv4-migration}

>[!IMPORTANT]
>
> 遷移過程是不可逆的。
>
> 開始將SDK V4行動應用程式移轉至Adobe Experience Platform SDK之前，請仔細閱讀檔案。

## 關於SDK V4移轉

Adobe Campaign Standard使用SDK V4處理行動應用程式，將其與使用Adobe Experience Platform SDK的應用程式分開。
將AdobeSDK版本從v4升級至Adobe Experience Platform後，行動應用程式需要繼續使用現有的應用程式訂閱者資料和促銷活動：因此，需要遷移。

>[!NOTE]
>
> 本頁記錄SDK v4行動應用程式移轉至新建立的Adobe Experience Platform SDK應用程式的程式。 您的SDK v4行動應用程式不會與&#x200B;**[!UICONTROL Configured]** **[!UICONTROL Property status]**&#x200B;的Adobe Experience Platform SDK行動應用程式合併。

| 移轉後不會變更的項目 |
|:-:|
| 使用移轉的SDK V4應用程式的現有傳送和行銷活動將沒有影響。 |
| 行動應用程式的名稱將保持相同。 |
| iOS和Android的平台憑證將會保留。 |
| 應用程式的所有訂閱者及其資料將會保留。 |
| 現有的SDK v4行動應用程式會繼續將資料（PII資料、訂閱者與代號資訊）傳送至Adobe Campaign Standard。 |
| 行動應用程式的&#x200B;**[!UICONTROL Organizational unit]**&#x200B;將保持相同。 |

| 移轉後會有何變更 |
|:-:|
| 行動應用程式將可在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中使用。 移轉前，可在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中使用。 |
| 應用程式的&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;將更改。 舊的&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;將繼續運作，傳送的資料不會遺失。 |
| 應用程式將系結至Adobe Experience Platform Launch **[!UICONTROL Mobile Property]**。 會以新建立的行動應用程式處理。 |
| 移轉中使用的原始Adobe Experience Platform SDK應用程式將不會作為個別應用程式存在。 只有移轉的SDK v4應用程式才可供使用。 |

## 將行動應用程式從SDK v4移轉至Adobe Experience Platform SDK {#how-to-migrate}

移轉前，您應考量下列建議：

* 遷移過程是不可逆的。
* 不應同時運行多個應用程式的遷移。 您也應確保同一個應用程式的移轉不會同時由多個視窗觸發。
* 移轉前，請確定已為您指派您要移轉的行動應用程式的&#x200B;**[!UICONTROL Organizational unit]**，以及您用於移轉的Adobe Experience Platform應用程式。
* 移轉後，應用程式將會變成Adobe Experience Platform SDK應用程式。 其變更將連結至其對應的Launch **[!UICONTROL Mobile Property]**。

1. 在Adobe Experience Platform Launch中建立新的&#x200B;**[!UICONTROL Mobile property]**。 如需詳細資訊，請參閱[Adobe Experience Platform Launch檔案](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property)。

1. 在Adobe Campaign Standard中，從進階功能表中選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;並開啟&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流程。 檢查工作流程是否已結束，且無錯誤。

1. 工作流程完成後，從&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;功能表檢查行動應用程式是否可在Adobe Campaign Standard中使用且處於&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;狀態。

   ![](assets/aep_v4_2.png)

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中，選取您要移轉的SDK V4應用程式。

1. 選取 **[!UICONTROL Mobile application migration to AEP SDK]** 索引標籤。

   ![](assets/aep_v4_3.png)

1. 從&#x200B;**[!UICONTROL Select AEP SDK mobile application to merge current application with]**&#x200B;下拉式清單中，選取先前建立的Adobe Experience Platform SDK行動應用程式。

1. 按一下&#x200B;**[!UICONTROL Migrate]**。

   ![](assets/aep_v4_4.png)

1. 在&#x200B;**[!UICONTROL Migration application]**&#x200B;窗口中，按一下&#x200B;**[!UICONTROL Ok]**。

   ![](assets/aep_v4_5.png)

1. 出現成功完成窗口，按一下&#x200B;**[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**。

1. 在Adobe Experience Platform SDK通道清單頁面中，檢查您先前的V4行動應用程式是否已設為&#x200B;**[!UICONTROL Ready To Configure]**。

1. 選取您的行動應用程式，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以完成移轉。

此移轉後，行動應用程式的V4版所收集的訂閱者，以及行動應用程式的AEP版所收集的新訂閱者，將可在已移轉的應用程式中使用。

若要區分兩種不同的訂閱者，您可以在將自訂資源&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;擴充為`sdkversion`或`appVersion`時，新增&#x200B;**[!UICONTROL Text]**&#x200B;類型的自訂欄位。 有關如何擴展自定義資源的詳細資訊，請參閱此[page](../../developing/using/creating-or-extending-the-resource.md)。
然後，您需要設定相關聯的Launch **[!UICONTROL Mobile property]**&#x200B;以傳送Collect PII呼叫中的此自訂欄位值，並據此變更行動應用程式設定。

## 常見問答集 {#faq}

### 問：在SDK v4行動應用程式中，看不到移動應用程式移轉至Adobe Experience Platform SDK標籤。 {#tab-not-visible}

答：從進階功能表&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;中，檢查&#x200B;**[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**&#x200B;選項的值。 此值應設為1，並預設為啟用。 管理員可能已手動禁用它。

![](assets/aep_v4_1.png)

### 問：從「行動應用程式移轉至Adobe Experience Platform SDK」標籤，出現「無資料」訊息。 {#no-data}

答：清單中只顯示符合條件的&#x200B;**[!UICONTROL Organizational unit]**&#x200B;應用程式。 請確定您有正確的Adobe Experience Platform移轉應用程式。 Adobe Experience Platform應用程式的&#x200B;**[!UICONTROL Property Status]**&#x200B;應設為&#x200B;**[!UICONTROL Ready to Configure]**，而&#x200B;**[!UICONTROL Mobile app migration status]**&#x200B;應設為&#x200B;**[!UICONTROL Not Migrated]**。

![](assets/aep_v4_6.png)

### 問：為何無法使用已設定屬性狀態的Adobe Experience Platform SDK應用程式進行移轉？ {#property-status}

答：移轉程式會保留SDK v4訂閱者和屬性。 它只會從Adobe Experience Platform SDK應用程式中保留Launch的相關資訊。 來自Adobe Experience Platform SDK應用程式的訂閱者和其他資料將會遺失。 為避免資料遺失，只有具有&#x200B;**[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]**&#x200B;的Adobe Experience Platform SDK應用程式才符合移轉資格。

### 問：移轉後，我可在何處找到先前的SDK v4行動應用程式？ {#v4-app-not-visible}

答：移轉後的行動應用程式會顯示在進階功能表&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中。

### 問：移轉後，我可在何處找到新建立的Adobe Experience Platform SDK應用程式？ {#aep-not-visible}

答：用於移轉的新建立Adobe Experience Platform SDK應用程式將不作為個別應用程式存在。 只有移轉的SDK v4應用程式才可供使用。

### 問：如果SDK v4行動應用程式組織單位設為A（組織單位ALL的子項），而Adobe Experience Platform SDK設為ALL。 如何移轉行動應用程式？ {#v4-org-unit}

答：**[!UICONTROL Organizational unit]** ALL的管理員將有權管理兩個行動應用程式，並負責移轉。

### 問：如果SDK v4行動應用程式組織單位設為A，而Adobe Experience Platform SDK應用程式設為B（組織單位A的同層級）。 如何移轉行動應用程式？ {#aep-org-unit}

答：Adobe Experience Platform SDK應用程式是同層級&#x200B;**[!UICONTROL Organizational unit]**&#x200B;的資產，**[!UICONTROL Organizational unit]** A的使用者將看不到行動應用程式。**[!UICONTROL Organizational unit]** ALL的管理員將可使用行動應用程式，但我們不建議這些管理員移轉行動應用程式。
在此情況下，您應將行動應用程式移至相同的**[!UICONTROL Organizational unit]**&#x200B;或具有父連結的&#x200B;**[!UICONTROL Organizational unit]**中。
有關**[!UICONTROL Organizational unit]**&#x200B;的詳細資訊，請參閱此[部分](../../administration/using/organizational-units.md)。

### 問：從您的Adobe Experience Platform SDK行動應用程式（從v4行動應用程式移轉）頁面，在「推播通道設定」下拉式清單下，不會顯示Android金鑰或iOS憑證的上傳日期/名稱等資訊 {#no-information-v5}

答：建立SDK V4行動應用程式時，系統不會儲存此資訊。 將SDK V4行動應用程式移轉至Adobe Experience Platform SDK行動應用程式時，您移轉的行動應用程式也不會有這類資訊。 一旦使用者上傳新的iOS憑證或Android金鑰，金鑰或憑證的不同詳細資料就會儲存並正確顯示在&#x200B;**[!UICONTROL Push channel settings]**&#x200B;下拉式清單下。
