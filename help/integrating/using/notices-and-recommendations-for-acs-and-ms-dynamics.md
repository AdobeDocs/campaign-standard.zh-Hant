---
title: 關於Microsoft Dynamics 365整合
description: 瞭解如何使用Campaign Standard和Microsoft Dynamics 365的注意事項和建議
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 277663c4cf0e810f691eeebfade17bf8dd73698e

---


# 關於Microsoft Dynamics 365整合

## 地區支援

此項整合適用於北美、歐洲、中東和非洲及亞太地區。

如果您位於EMEA或APAC地區，部分資料將會在美國處理，做為此項整合的一部分。 有關更多資訊，請參見[本節](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。

## 單向連絡人同步的真相來源

對於Contact和自訂實體同步，此整合會將Dynamics 365視為真實來源。對同步化屬性所做的任何變更都應在Microsoft Dynamics 365中完成，而非在Adobe Campaign Standard中完成。如果在促銷活動中進行變更，則在同步期間，這些變更最終會在促銷活動中被覆寫，因為同步是單向的。  此外，Contacts Synchronization旨在提取所有Contact記錄，無論這些記錄在Microsoft Dynamics 365中標籤為活動或非活動。

## 管理隱私權要求

此整合旨在在Microsoft Dynamics 365和Adobe Campaign Standard之間傳輸使用者資料（包括但不限於個人資訊，如果它包含在您的使用者資料中）。  身為資料掌控者，貴公司有責任遵守任何適用於您收集和使用個人資料的隱私權法律和法規。

在此整合中，您必須獨立處理每個系統中的每個資料主體要求，才能將變更反映在兩個資料庫中。 變更應先在Microsoft Dynamics 365中執行，然後在Adobe Campaign Standard中執行。 唯一的例外是，當Dynamics 365中的連絡人刪除時，隱私權相關的刪除要求會新增至「促銷活動標準」的「隱私權工具」佇列。

以下連結可協助您在每個系統中實作存取和／或刪除隱私權相關要求：

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)

## 刪除連絡人

由於Dynamics 365是真相的來源，因此Dynamics 365中的連絡人刪除將反映在Campaign中。

在Dynamics 365中刪除連絡人時，整合會在「促銷活動隱私權要求／工具」畫面中佇列隱私權相關的刪除要求。  如果您已停用隱私權相關刪除要求的2步驟程式，Campaign會為您處理刪除。

不過，如果啟用了2步驟的程式，您將需要在隱私權技術工作流程執行後進入「隱私權要求／工具」畫面，並確認記錄是否可以刪除。  只有到那時，Campaign才會處理刪除。

如需詳細資訊，請參閱 [Adobe Campaign Standard中如何執行隱私權相關的刪除要求](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/execute-privacy-requests.html)

>[!CAUTION]
>
>如果您在促銷活動中針對隱私權要求啟用了2步驟的程式，Dynamics 365中的刪除將不會自動反映在促銷活動中。  您必須進入「促銷活動隱私權要求」畫面，以確認刪除。

>[!NOTE]
>
>此整合會使用外部Id（即Dynamics 365連絡人Id）建立請求，作為記錄／描述檔識別碼。

## 選擇退出

由於Dynamics 365和Campaign之間的退出屬性不同，以及每個客戶的業務需求不同，因此選擇退出對應仍留作客戶完成的練習。請務必確保系統之間正確對應退出選項，以便維持使用者退出偏好設定，而且使用者不會透過已選擇退出的通道取得通訊。

請注意，只有具有「blackList」首碼（例如blackListEmail）或CCPA選擇退出的特定屬性的促銷活動屬性，才能用於選擇退出映射。  在Dynamics 365中，大部分的退出欄位都有「doNot」字首；不過，如果資料類型相容，您也可以利用您為選擇退出而建立的自訂屬性。

在布建整合時，您將有機會指定您的企業需要何種退出設定：

* Dynamics 365是退出的真相來源：退出屬性將會在從Dynamics 365到Campaign Standard的一個方向上同步
* 「促銷活動標準」是退出的真相來源：退出屬性將會在從促銷活動標準到動態365的一個方向上同步
* Dynamics 365 AND Campaign Standard是真相的來源：退出屬性將在Campaign Standard和Dynamics 365之間雙向同步

請依照 [Unifi使用指南中的布建後指示](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn) ，正確映射這些值。

雙向選擇退出配置使用邏輯確定要寫入兩個系統的值。  邏輯會比較兩個系統之間的時間戳記（Dynamics 365中的記錄層級變更、Campaign中的屬性層級變更），以判斷哪個系統佔上風。  如果「促銷活動」包含較新的時間戳記，則會優先使用「促銷活動」值。  如果Dynamics 365包含較新的時間戳記，或者等於，則opt-out=TRUE將會成功（假設其中一個值為TRUE）。

**加州消費者保護法(CCPA)及類似法案的退出規定。**

雙向選擇退出配置功能目前無法支援符合CCPA和／或其他立即可用的資料隱私權法規的特定法定要求。 必須符合CCPA或與退出相關之類似法律規定的客戶，有責任實作自己的第三方解決方案以執行雙向同步。

>[!NOTE]
>
>建議您選擇單向退出選項，如果您的公司不需要雙向退出支援。

>[!NOTE]
>
>請檢閱並視需要更新Adobe Campaign中的預設和特定類型規則，然後再在此處進行變更，以確保這些變更正確套用至所有傳出的通訊。 例如，請確定任何對應至選擇退出偏好設定的對應，都能準確反映收件者的意圖／通訊選擇，且不會不慎中斷傳送關係或交易訊息，例如客戶訂單確認。

## 現有促銷活動資料

此整合將同步Dynamics 365與Campaign的連絡人和自訂實體。 整合不會觸及在整合以外建立的促銷活動記錄（亦即，不是由同步工作建立），包括整合設定時現有的促銷活動記錄。

由於此整合使用「促銷活動 **[!UICONTROL externalId]** 標準」中的欄位，將促銷活動描述檔記錄與Dynamics 365連絡人記錄同步，因此，您必須在此「促銷活動」欄位中填入Dynamics 365 **[!UICONTROL externalId]****[!UICONTROL contactId]** ，才能將您想要從Dynamics 365同步的記錄。  自訂實體也需要有此欄位，並正確填入，才能維持同步。  但請記住，Dynamics 365仍將是真相的來源，而且當整合偵測到Dynamics 365端的更新時，促銷活動描述檔資料可能會被覆寫。  視您現有的部署而定，也可能需要其他步驟來啟用整合；因此，建議您與Adobe技術聯絡人密切合作。

>[!NOTE]
>
>由於現有客戶部署的複雜性，建議您在規劃和設定整合時與Adobe技術聯絡人合作。
