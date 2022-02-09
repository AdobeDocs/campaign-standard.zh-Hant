---
title: SDK v4移動應用程式遷移到Adobe Experience PlatformSDK
description: 瞭解如何將移動應用程式從SDK v4遷移到Adobe Experience PlatformSDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1200'
ht-degree: 1%

---

# 如何將您的行動應用程式從 SDK v4 移轉至 Adobe Experience Platform SDK {#sdkv4-migration}

>[!IMPORTANT]
>
> 遷移過程是不可逆的。
>
> 開始將SDK V4移動應用程式遷移到Adobe Experience PlatformSDK之前，請仔細閱讀文檔。

## 關於SDK V4遷移

Adobe Campaign Standard使用SDK V4處理移動應用程式，與使用Adobe Experience PlatformSDK的應用程式分開。
將AdobeSDK版本從v4升級到Adobe Experience Platform後，移動應用程式需要繼續使用現有應用程式訂閱者資料和活動：因此需要遷移。

>[!NOTE]
>
> 本頁記錄了SDK v4移動應用程式到新建立的Adobe Experience PlatformSDK應用程式的遷移。 您的SDK v4移動應用程式不會與Adobe Experience PlatformSDK移動應用程式合併 **[!UICONTROL Configured]** **[!UICONTROL Property status]**。

| 遷移後不會更改的內容 |
|:-:|
| 使用遷移的SDK V4應用程式對現有交付和市場活動沒有影響。 |
| 移動應用程式的名稱將保持不變。 |
| iOS和安卓的平台證書將保留。 |
| 應用程式及其資料的所有訂閱者將被保留。 |
| 現有的SDK v4移動應用程式將繼續將資料（PII資料、訂戶和令牌資訊）發送到Adobe Campaign Standard。 |
| 的 **[!UICONTROL Organizational unit]** 移動應用程式將保持不變。 |

| 遷移後將發生哪些更改 |
|:-:|
| 移動應用程式將在 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**。 遷移前，可在 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**。 |
| 的 **[!UICONTROL Collect PII Endpoint]** 的下界。 年長者 **[!UICONTROL Collect PII Endpoint]** 將繼續工作，發送的資料不會丟失。 |
| 申請將與Adobe Experience Platform Launch **[!UICONTROL Mobile Property]**。 它將作為新建立的移動應用程式處理。 |
| 遷移中使用的原始Adobe Experience PlatformSDK應用程式將不作為單獨的應用程式存在。 只有遷移的SDK v4應用程式才可用。 |

## 將移動應用程式從SDK v4遷移到Adobe Experience PlatformSDK {#how-to-migrate}

遷移之前，應考慮以下建議：

* 遷移過程是不可逆的。
* 您不應同時運行多個應用程式的遷移。 您還應確保同一應用程式的遷移不會同時被多個窗口觸發。
* 在遷移之前，請確保已為您分配 **[!UICONTROL Organizational unit]** 要遷移的移動應用程式，以及要遷移的Adobe Experience Platform應用程式。
* 遷移後，該應用程式將成為Adobe Experience PlatformSDK應用程式。 其更改將與相應的Launch連結 **[!UICONTROL Mobile Property]**。

1. 新建 **[!UICONTROL Mobile property]** 在Adobe Experience Platform Launch。 有關此項的詳細資訊，請參閱 [Adobe Experience Platform Launch文檔](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property)。

1. 在Adobe Campaign Standard，從高級菜單中，選擇 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** 開啟 **[!UICONTROL syncWithLaunch]** 工作流。 檢查工作流是否已結束且無錯誤。

1. 工作流完成後，從 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** 菜單，檢查移動應用程式是否在Adobe Campaign Standard **[!UICONTROL Ready to Configure]** 狀態。

   ![](assets/aep_v4_2.png)

1. 在 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**，選擇要遷移的SDK V4應用程式。

1. 選取 **[!UICONTROL Mobile application migration to AEP SDK]** 索引標籤。

   ![](assets/aep_v4_3.png)

1. 從 **[!UICONTROL Select AEP SDK mobile application to merge current application with]** 下拉框，選擇以前建立的Adobe Experience PlatformSDK移動應用程式。

1. 按一下&#x200B;**[!UICONTROL Migrate]**。

   ![](assets/aep_v4_4.png)

1. 從 **[!UICONTROL Migration application]** 窗口，按一下 **[!UICONTROL Ok]**。

   ![](assets/aep_v4_5.png)

1. 出現成功完成窗口，按一下 **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**。

1. 在Adobe Experience PlatformSDK通道清單頁中，檢查您以前的V4移動應用程式是否設定為 **[!UICONTROL Ready To Configure]**。

1. 選擇您的移動應用程式，然後按一下 **[!UICONTROL Save]** 完成遷移。

在此遷移之後，由移動應用程式的V4版本收集的訂戶和由移動應用程式的AEP版本收集的新訂戶將在遷移的應用程式中可用。

要區分兩種不同類型的訂閱伺服器，可以添加一個新的自定義欄位 **[!UICONTROL Text]** 擴展自定義資源時鍵入 **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** 如 `sdkversion` 或 `appVersion` 例如。 有關如何擴展自定義資源的詳細資訊，請參閱此 [頁](../../developing/using/creating-or-extending-the-resource.md)。
然後，您需要配置關聯的啟動 **[!UICONTROL Mobile property]** 在「收集PII呼叫」中發送此自定義欄位值，並相應更改您的移動應用程式配置。

## 常見問答集 {#faq}

### 問：在SDK v4移動應用程式中，移動應用程式遷移到Adobe Experience PlatformSDK頁籤不可見。 {#tab-not-visible}

答：從高級菜單 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**，檢查 **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]** 的雙曲餘切值。 它應設定為1，並預設啟用。 管理員可能已手動禁用它。

![](assets/aep_v4_1.png)

### 問：從「移動應用程式」遷移到「Adobe Experience PlatformSDK」頁籤，將顯示「無資料」消息。 {#no-data}

答：僅適用於您 **[!UICONTROL Organizational unit]** 清單中。 請確保您有正確的Adobe Experience Platform應用程式進行遷移。 的 **[!UICONTROL Property Status]** 你Adobe Experience Platform的申請書 **[!UICONTROL Ready to Configure]**  和 **[!UICONTROL Mobile app migration status]** 設定為 **[!UICONTROL Not Migrated]**。

![](assets/aep_v4_6.png)

### 問：為什麼不能使用配置屬性狀態的Adobe Experience PlatformSDK應用程式進行遷移？ {#property-status}

答：遷移過程將保留SDK v4訂閱者和屬性。 它只保留Adobe Experience PlatformSDK應用程式中的「啟動」相關資訊。 來自Adobe Experience PlatformSDK應用程式的訂閱者和其他資料將丟失。 為避免任何資料丟失，僅Adobe Experience PlatformSDK應用程式 **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** 符合遷移條件。

### 問：遷移後，我在哪裡可以找到以前的SDK v4移動應用程式？ {#v4-app-not-visible}

答：遷移後的移動應用程式將從高級菜單中可見 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**。

### 問：遷移後，在何處可以找到新建立的Adobe Experience PlatformSDK應用程式？ {#aep-not-visible}

答：新建立的用於遷移的Adobe Experience PlatformSDK應用程式將不作為單獨的應用程式存在。 只有遷移的SDK v4應用程式才可用。

### 問：如果SDK v4移動應用程式組織單元設定為A（組織單元ALL的子項），而Adobe Experience PlatformSDK設定為ALL。 如何遷移移動應用程式？ {#v4-org-unit}

答：管理員 **[!UICONTROL Organizational unit]** ALL將擁有管理兩個移動應用程式的權限，並負責遷移。

### 問：如果SDK v4移動應用程式組織單元設定為A，而Adobe Experience PlatformSDK應用程式設定為B（組織單元A的同級）。 如何遷移移動應用程式？ {#aep-org-unit}

答：Adobe Experience PlatformSDK應用程式是同級的資產 **[!UICONTROL Organizational unit]**，移動應用程式對用戶不可見 **[!UICONTROL Organizational unit]** 答：移動應用程式將可供 **[!UICONTROL Organizational unit]** 但我們不建議這些管理員遷移移動應用程式。
在這種情況下，您應將移動應用程式移動到同一位置 **[!UICONTROL Organizational unit]** 或 **[!UICONTROL Organizational unit]** 父連結。
有關 **[!UICONTROL Organizational unit]**，請參閱 [節](../../administration/using/organizational-units.md)。

### 問：從您的Adobe Experience PlatformSDK移動應用程式（從v4移動應用程式遷移）頁面，在「推送通道設定」下拉清單中，不顯示Android密鑰或iOS證書的上載日期/名稱等資訊 {#no-information-v5}

答：建立SDK V4移動應用程式時，系統不儲存此資訊。 將SDK V4移動應用程式遷移到Adobe Experience PlatformSDK移動應用程式時，遷移的移動應用程式也將沒有此類資訊。 一旦用戶將上傳新的iOS證書或Android密鑰，密鑰或證書的不同詳細資訊將儲存並正確顯示在 **[!UICONTROL Push channel settings]** 下拉。
