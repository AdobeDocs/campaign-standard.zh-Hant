---
title: SDK v4行動應用程式移轉至Adobe Experience Platform SDK
description: 瞭解如何將您的行動應用程式從SDK v4移轉至Adobe Experience Platform SDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 620ae1adc6f804e90c10daeb5fa4df42ce106885
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 1%

---

# 如何將您的行動應用程式從 SDK v4 移轉至 Adobe Experience Platform SDK {#sdkv4-migration}


自2021年8月31日起，Adobe Experience Platform Mobile第4版SDK已停止支援。 如果您仍在使用此舊版SDK，您必須在2024年6月底之前，使用Adobe Experience Platform SDK **更新實施**。 閱讀本文章以瞭解如何移轉至Adobe Experience Platform SDK。

>[!IMPORTANT]
>
> 開始將SDK V4行動應用程式移轉至Adobe Experience Platform SDK之前，請先仔細閱讀檔案。

## 關於SDK V4移轉

Adobe Campaign Standard使用SDK V4來處理行動應用程式，作為與Adobe Experience Platform SDK分開的應用程式。

將Adobe SDK版本從v4升級至Adobe Experience Platform後，行動應用程式需要繼續使用現有應用程式訂閱者資料和行銷活動：因此需要移轉。

>[!NOTE]
>
> 本頁會記錄SDK v4行動應用程式移轉至新建立的Adobe Experience Platform SDK應用程式的程式。 您的SDK v4行動應用程式將不會與具有&#x200B;**[!UICONTROL Configured]** **[!UICONTROL Property status]**&#x200B;的Adobe Experience Platform SDK行動應用程式合併。

| 移轉後不會變更的專案 |
|:-:|
| 使用移轉的SDK V4應用程式時，不會對現有的傳遞與行銷活動造成影響。 |
| 行動應用程式的名稱將維持不變。 |
| 將保留iOS和Android的平台認證。 |
| 將會保留應用程式的所有訂閱者及其資料。 |
| 現有的SDK v4行動應用程式將繼續傳送資料（PII資料、訂閱者與權杖資訊）至Adobe Campaign Standard。 |
| 行動應用程式的&#x200B;**[!UICONTROL Organizational unit]**&#x200B;將維持不變。 |

| 移轉後會有哪些變更 |
|:-:|
| 行動應用程式將可在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;中使用。 移轉前，它可在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中使用。 |
| 應用程式的&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;將會變更。 較舊的&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;將繼續運作，傳送的資料不會遺失。 |
| 應用程式將繫結至標籤&#x200B;**[!UICONTROL Mobile Property]**。 它將以新建立的行動應用程式形式處理。 |
| 移轉中使用的原始Adobe Experience Platform SDK應用程式將不會以個別應用程式的形式存在。 只有移轉的SDK v4應用程式才可使用。 |

## 將您的行動應用程式從SDK v4移轉至Adobe Experience Platform SDK {#how-to-migrate}

移轉前，您應考量下列建議：

* 移轉程式無法復原。
* 您不應同時執行多個應用程式的移轉。 您也應確定多個視窗不會同時觸發相同應用程式的移轉。
* 移轉前，請確定已為您指派要移轉的行動應用程式以及移轉所使用的Adobe Experience Platform應用程式的&#x200B;**[!UICONTROL Organizational unit]**。
* 移轉後，應用程式會變成Adobe Experience Platform SDK應用程式。 其變更將連結至其對應的標籤&#x200B;**[!UICONTROL Mobile Property]**。

1. 在資料收集UI中建立新的&#x200B;**[!UICONTROL Mobile property]**。 如需詳細資訊，請參閱[檔案](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)。

1. 在Adobe Campaign Standard中，從進階功能表選取「**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**」，然後開啟「**[!UICONTROL syncWithLaunch]**」工作流程。 檢查工作流程是否已結束且沒有錯誤。

1. 工作流程完成後，從&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;功能表，檢查行動應用程式是否可在Adobe Campaign Standard中使用並處於&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;狀態。

   ![](assets/aep_v4_2.png)

1. 在&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;中，選取您要移轉的SDK V4應用程式。

1. 選取 **[!UICONTROL Mobile application migration to AEP SDK]** 索引標籤。

   ![](assets/aep_v4_3.png)

1. 從&#x200B;**[!UICONTROL Select AEP SDK mobile application to merge current application with]**&#x200B;下拉式清單中，選取先前建立的Adobe Experience Platform SDK行動應用程式。

1. 按一下&#x200B;**[!UICONTROL Migrate]**。

   ![](assets/aep_v4_4.png)

1. 從&#x200B;**[!UICONTROL Migration application]**&#x200B;視窗，按一下&#x200B;**[!UICONTROL Ok]**。

   ![](assets/aep_v4_5.png)

1. 成功完成視窗會出現，請按一下&#x200B;**[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**。

1. 從Adobe Experience Platform SDK頻道清單頁面，檢查您先前的V4行動應用程式是否設為&#x200B;**[!UICONTROL Ready To Configure]**。

1. 選取您的行動應用程式並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以完成移轉。

此移轉後，移轉的應用程式將可提供V4版本行動應用程式收集的訂閱者以及AEP版本行動應用程式收集的新訂閱者。

若要區分兩種不同型別的訂閱者，您可以在擴充自訂資源&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;時新增&#x200B;**[!UICONTROL Text]**&#x200B;型別的自訂欄位，例如`sdkversion`或`appVersion`。 如需如何擴充自訂資源的詳細資訊，請參閱此[頁面](../../developing/using/creating-or-extending-the-resource.md)。
然後，您需要設定關聯的標籤**[!UICONTROL Mobile property]**，以在「收集PII」呼叫中傳送此自訂欄位值，並相應地變更您的行動應用程式設定。

## 常見問答集 {#faq}

### 問：在SDK v4行動應用程式中，移轉至Adobe Experience Platform SDK的行動應用程式標籤不可見。 {#tab-not-visible}

答：從進階功能表&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**，檢查&#x200B;**[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**&#x200B;選項的值。 預設應將它設為1並啟用。 管理員可能已經手動停用。

![](assets/aep_v4_1.png)

### 問：從行動應用程式移轉至Adobe Experience Platform SDK索引標籤中，訊息無資料出現。 {#no-data}

答：清單中只會顯示您&#x200B;**[!UICONTROL Organizational unit]**&#x200B;的合格應用程式。 請確定您有正確的移轉Adobe Experience Platform應用程式。 您的Adobe Experience Platform應用程式的&#x200B;**[!UICONTROL Property Status]**&#x200B;應設為&#x200B;**[!UICONTROL Ready to Configure]**，**[!UICONTROL Mobile app migration status]**&#x200B;應設為&#x200B;**[!UICONTROL Not Migrated]**。

![](assets/aep_v4_6.png)

### 問：為何具有已設定屬性狀態的Adobe Experience Platform SDK應用程式無法用於移轉？ {#property-status}

答：移轉程式會保留SDK v4訂閱者和屬性。 它只會保留Adobe Experience Platform SDK應用程式中的標籤相關資訊。 Adobe Experience Platform SDK應用程式的訂閱者和其他資料將會遺失。 為避免任何資料遺失，只有具有&#x200B;**[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]**&#x200B;的Adobe Experience Platform SDK應用程式符合移轉資格。

### 問：移轉之後，我可以在哪裡找到先前的SDK v4行動應用程式？ {#v4-app-not-visible}

答：移轉後的行動應用程式將顯示於進階功能表&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**。

### 問：移轉之後，我可以在哪裡找到新建立的Adobe Experience Platform SDK應用程式？ {#aep-not-visible}

答：用於移轉的新建立Adobe Experience Platform SDK應用程式將不會以獨立應用程式存在。 只有移轉的SDK v4應用程式才可使用。

### 問：如果SDK v4行動應用程式組織單位已設為「A」（組織單位ALL的子項），且Adobe Experience Platform SDK已設為「ALL」。 如何移轉行動應用程式？ {#v4-org-unit}

答： **[!UICONTROL Organizational unit]** ALL的管理員將有權管理這兩個行動應用程式，並將負責移轉。

### 問：如果SDK v4行動應用程式組織單位設為A，而Adobe Experience Platform SDK應用程式設為B （組織單位A的同胞）。 如何移轉行動應用程式？ {#aep-org-unit}

答： Adobe Experience Platform SDK應用程式是同層級&#x200B;**[!UICONTROL Organizational unit]**&#x200B;的資產，行動應用程式將不會顯示給&#x200B;**[!UICONTROL Organizational unit]** A的使用者。**[!UICONTROL Organizational unit]** ALL的系統管理員可以使用行動應用程式，但我們不建議這些系統管理員移轉行動應用程式。
在此情況下，您應在相同的**[!UICONTROL Organizational unit]**&#x200B;或具有父連結的&#x200B;**[!UICONTROL Organizational unit]**中移動行動應用程式。
如需**[!UICONTROL Organizational unit]**&#x200B;的詳細資訊，請參閱此[區段](../../administration/using/organizational-units.md)。

### 問：在您的Adobe Experience Platform SDK行動應用程式（從v4行動應用程式移轉）頁面的「推播通道設定」下拉式清單下，不會顯示Android金鑰或iOS憑證的已上傳日期/名稱等資訊 {#no-information-v5}

答：建立SDK V4行動應用程式時，系統不會儲存此資訊。 將您的SDK V4行動應用程式移轉至Adobe Experience Platform SDK行動應用程式時，移轉後的行動應用程式也不會有這類資訊。 使用者一旦上傳新的iOS憑證或Android金鑰，金鑰或憑證的不同詳細資料就會儲存起來，並正確地顯示在&#x200B;**[!UICONTROL Push channel settings]**&#x200B;下拉式清單中。
