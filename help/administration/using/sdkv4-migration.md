---
solution: Campaign Standard
product: campaign
title: SDK v4行動應用程式移轉至Adobe Experience Platform SDK
description: 本檔案可讓您將行動應用程式從SDK v4移轉至Adobe Experience Platform SDK
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 6c171d45d655e4055d4a3c7927f1dd8e0913eeaa
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 0%

---


# 如何將您的行動應用程式從SDK v4移轉至Adobe Experience Platform SDK {#sdkv4-migration}

>[!IMPORTANT]
>
> 遷移過程是不可逆的。
>
> 開始將SDK V4行動應用程式移轉至Adobe Experience Platform SDK之前，請仔細閱讀檔案。

## 關於SDK V4移轉

Adobe Campaign Standard使用SDK V4處理行動應用程式，將其與使用Adobe Experience Platform SDK的應用程式分開處理。
將Adobe SDK版本從v4升級至Adobe Experience Platform後，行動應用程式需要繼續使用現有的應用程式訂閱者資料和促銷活動：因此需要移轉。

>[!NOTE]
>
> 本頁記錄SDK v4行動應用程式移轉至新建立的Adobe Experience Platform SDK應用程式的情況。 您的SDK v4行動應用程式不會與Adobe Experience Platform SDK行動應用程式與&#x200B;**[!UICONTROL Configured]** **[!UICONTROL Property status]**&#x200B;合併。

| 移轉後不會變更的項目 |
|:-:|
| 使用移轉的SDK V4應用程式，將不會對現有的傳送和促銷活動造成任何影響。 |
| 行動應用程式的名稱將維持不變。 |
| iOS和Android的平台認證將會保留。 |
| 應用程式的所有訂閱者及其資料將會保留。 |
| 現有的SDK v4行動應用程式將繼續傳送資料（PII資料、訂閱者與Token資訊）至Adobe Campaign Standard。 |
| 行動應用程式的&#x200B;**[!UICONTROL Organizational unit]**&#x200B;將維持不變。 |

| 移轉後會有哪些改變 |
|:-:|
| 行動應用程式將可在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中使用。 在移轉之前，它可在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中使用。 |
| 應用程式的&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;將會變更。 舊版&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;將繼續運作，傳送的資料不會遺失。 |
| 應用程式將系結至Adobe Experience Platform Launch **[!UICONTROL Mobile Property]**。 它會處理為新建立的行動應用程式。 |
| 移轉中使用的原始Adobe Experience Platform SDK應用程式將不會單獨存在。 只有已移轉的SDK v4應用程式才可用。 |

## 將您的行動應用程式從SDK v4移轉至Adobe Experience Platform SDK {#how-to-migrate}

在移轉之前，您應考量下列建議：

* 遷移過程是不可逆的。
* 您不應同時執行多個應用程式的移轉。 您也應確保同一應用程式的移轉不會同時由多個視窗觸發。
* 在移轉之前，請確定您已獲得要移轉之行動應用程式的&#x200B;**[!UICONTROL Organizational unit]**，以及您用於移轉的Adobe Experience Platform應用程式的。
* 移轉後，應用程式將會變成Adobe Experience Platform SDK應用程式。 其更改將連結至其相應的啟動&#x200B;**[!UICONTROL Mobile Property]**。

1. 在Adobe Experience Platform Launch中建立新的&#x200B;**[!UICONTROL Mobile property]**。 如需詳細資訊，請參閱[Adobe Experience Platform Launch檔案](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property)。

1. 在Adobe Campaign Standard的進階功能表中，選取&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;並開啟&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;工作流程。 檢查工作流程是否已結束且無錯誤。

1. 工作流程完成後，從&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;功能表，檢查行動應用程式是否可在Adobe Campaign Standard中使用且處於&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;狀態。

   ![](assets/aep_v4_2.png)

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中，選取您要移轉的SDK V4應用程式。

1. 選取 **[!UICONTROL Mobile application migration to AEP SDK]** 索引標籤。

   ![](assets/aep_v4_3.png)

1. 從&#x200B;**[!UICONTROL Select AEP SDK mobile application to merge current application with]**&#x200B;下拉式清單中，選取先前建立的Adobe Experience Platform SDK行動應用程式。

1. 按一下 **[!UICONTROL Migrate]**。

   ![](assets/aep_v4_4.png)

1. 在&#x200B;**[!UICONTROL Migration application]**&#x200B;窗口中，按一下&#x200B;**[!UICONTROL Ok]**。

   ![](assets/aep_v4_5.png)

1. 出現成功完成窗口，按一下&#x200B;**[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**。

1. 從Adobe Experience Platform SDK頻道清單頁面，檢查您先前的V4行動應用程式是否已設為&#x200B;**[!UICONTROL Ready To Configure]**。

1. 選擇您的行動應用程式，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以完成移轉。

此移轉後，由V4版行動應用程式收集的訂閱者和由AEP版行動應用程式收集的新訂閱者，將可在移轉的應用程式中使用。

要區分兩種不同的訂閱者類型，例如，將自訂資源&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;擴展為`sdkversion`或`appVersion`時，可以添加&#x200B;**[!UICONTROL Text]**&#x200B;類型的新自訂欄位。 有關如何擴展自定義資源的詳細資訊，請參閱此[頁](../../developing/using/creating-or-extending-the-resource.md)。
然後，您需要設定相關的啟動**[!UICONTROL Mobile property]**，以傳送Collect PII呼叫中的此自訂欄位值，並據以變更行動應用程式設定。

## 常見問答集{#faq}

### 問：在SDK v4行動應用程式中，無法看到移動應用程式移轉至Adobe Experience Platform SDK標籤。{#tab-not-visible}

答：從高級菜單&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;中，檢查&#x200B;**[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**&#x200B;選項的值。 它應設為1，並依預設啟用。 管理員可能已手動禁用它。

![](assets/aep_v4_1.png)

### 問：從「行動應用程式」移轉至Adobe Experience Platform SDK標籤，訊息會顯示「無資料」。{#no-data}

答：清單中只會顯示您&#x200B;**[!UICONTROL Organizational unit]**&#x200B;的合格應用程式。 請確定您有正確的Adobe Experience Platform應用程式進行移轉。 Adobe Experience Platform應用程式的&#x200B;**[!UICONTROL Property Status]**&#x200B;應設為&#x200B;**[!UICONTROL Ready to Configure]**，而&#x200B;**[!UICONTROL Mobile app migration status]**&#x200B;應設為&#x200B;**[!UICONTROL Not Migrated]**。

![](assets/aep_v4_6.png)

### 問：為什麼無法使用具有「已設定屬性狀態」的Adobe Experience Platform SDK應用程式進行移轉？{#property-status}

答：移轉程式會保留SDK v4訂閱者和屬性。 它只會保留Adobe Experience Platform SDK應用程式中的Launch相關資訊。 來自Adobe Experience Platform SDK應用程式的訂閱者和其他資料將會遺失。 為避免資料遺失，只有&#x200B;**[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]**&#x200B;的Adobe Experience Platform SDK應用程式才符合移轉的資格。

### 問：在移轉後，我可以在哪裡找到我先前的SDK v4行動應用程式？{#v4-app-not-visible}

答：移轉後的行動應用程式將可從進階功能表&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中看到。

### 問：在移轉後，我可以在哪裡找到我新建立的Adobe Experience Platform SDK應用程式？{#aep-not-visible}

答：用於移轉的新建Adobe Experience Platform SDK應用程式不會以個別應用程式的形式存在。 只有已移轉的SDK v4應用程式才可用。

### 問：如果SDK v4行動應用程式組織單位設為A（組織單位ALL的子系），而Adobe Experience Platform SDK則設為ALL。 如何移轉行動應用程式？{#v4-org-unit}

答：**[!UICONTROL Organizational unit]** ALL的管理員將擁有管理行動應用程式的權限，並負責移轉。

### 問：如果SDK v4行動應用程式組織單位設為A，而Adobe Experience Platform SDK應用程式則設為B（組織單位A的同級）。 如何移轉行動應用程式？{#aep-org-unit}

答：Adobe Experience Platform SDK應用程式是同級&#x200B;**[!UICONTROL Organizational unit]**&#x200B;的資產，而行動應用程式對於&#x200B;**[!UICONTROL Organizational unit]** A的使用者將看不到。**[!UICONTROL Organizational unit]** ALL的管理員可使用行動應用程式，但我們不建議這些管理員移轉行動應用程式。
在這種情況下，您應將行動應用程式移至相同的**[!UICONTROL Organizational unit]**&#x200B;或具有父連結的&#x200B;**[!UICONTROL Organizational unit]**中。
有關**[!UICONTROL Organizational unit]**&#x200B;的更多資訊，請參閱[部分](../../administration/using/organizational-units.md)。

### 問：從您的Adobe Experience Platform SDK行動應用程式（從v4行動應用程式移轉）頁面，在「推播頻道設定」下拉式清單下，不會顯示Android金鑰或iOS憑證{#no-information-v5}的上傳日期／名稱等資訊

答：當建立SDK V4行動應用程式時，系統不會儲存此資訊。 將SDK V4行動應用程式移轉至Adobe Experience Platform SDK行動應用程式時，您移轉的行動應用程式也不會有此類資訊。 當使用者上傳新的iOS憑證或Android金鑰時，就會儲存和正確顯示金鑰或憑證的不同詳細資訊至&#x200B;**[!UICONTROL Push channel settings]**&#x200B;下拉式清單。
