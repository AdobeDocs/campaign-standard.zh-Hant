---
solution: Campaign Standard
product: campaign
title: Campaign和Microsoft Dynamics 365資料管理
description: 瞭解Campaign Standard和Microsoft Dynamics 365如何管理常見資料
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 1%

---


# 管理Campaign和Microsoft Dynamics 365之間的資料

## 單向同步的真相來源

對於連絡人和自訂實體同步，此整合會將Dynamics 365視為真實來源。  對同步化屬性所做的任何變更都應在Dynamics 365中進行，而非在Campaign中進行。  如果在促銷活動中進行變更，則在同步期間，這些變更最終會在促銷活動中被覆寫，因為同步是單向的。

## 刪除連絡人

視需要，整合可設定為在Dynamics 365中刪除連絡人時，向Campaign發出描述檔刪除呼叫，以協助維持資料的完整性。

不過，描述檔刪除與隱私權刪除不同。 促銷活動中的隱私權刪除會移除促銷活動描述檔記錄和相關記錄項目；但是，定期刪除描述檔只會刪除ACS描述檔記錄，而保留在促銷活動記錄中。

如果整合中啟用了描述檔刪除功能，則需要執行其他步驟，才能正確處理資料主體的隱私權要求。 請參閱](#manage-privacy-requests)下方[一節中的步驟。

## 隱私權

### 管理隱私權要求{#manage-privacy-requests}

此整合旨在在Microsoft Dynamics 365和Adobe Campaign Standard之間傳輸使用者資料(包括但不限於個人資訊（若您的使用者資料中包含）。 身為資料掌控者，貴公司有責任遵守任何適用於您收集和使用個人資料的隱私權法律和法規。

此整合不會發佈任何資料主體隱私權（例如GDPR），刪除或處理任何其他隱私權要求（選擇退出除外）。 在處理隱私權要求時，您應該在Dynamics 365和Campaign（透過Adobe Experience Platform Privacy Service）中單獨執行。

如果您已設定整合，在Dynamics 365中刪除連絡人時，對促銷活動發出定期的描述檔刪除呼叫，請遵循下列步驟。 確保在此過程中未對相關記錄進行更新。

1. 向[Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)發出隱私權刪除要求

1. 監控請求，直到成功完成

1. 確認記錄不再在您的促銷活動例項中

1. （不久之後）在Dynamics中發出隱私權刪除365

1. 驗證是否已從兩個系統中刪除記錄

以下連結可協助您在每個系統中實作存取和／或刪除隱私權相關要求：

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### 隱私權和連結資源{#privacy-linked-resources}

如果任何促銷活動自訂資源記錄包含客戶使用促銷活動時適用的個人資訊，該記錄應連結至對應的促銷活動描述檔記錄（直接或透過其他自訂資源），如此，描述檔記錄上的隱私權相關刪除也可以刪除包含個人資訊的連結自訂資源記錄；必須配置實體之間的連結和刪除選項，以啟用連結記錄的類級聯刪除。 個人資訊不應輸入至未連結至描述檔的自訂資源。

瞭解如何在本節](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md)中映射促銷活動資源和Dynamics 365實體[。

## 選擇退出

由於Dynamics 365和Campaign之間的退出屬性不同，以及每個客戶的業務需求不同，因此選擇退出對應仍留作客戶完成的練習。  請務必確保退出選項在系統之間正確映射，以便維護最終用戶退出首選項，並且他們不會通過他們選擇退出的通道接收通信。

請注意，只有首碼為「不再透過電子郵件聯絡」的促銷活動屬性或CCPA選擇退出的特定屬性才能用於選擇退出映射。 [進一步瞭解](../../developing/using/datamodel-profile.md)。在Dynamics 365中，大多數選擇退出欄位都有「donot」字首；但是，如果資料類型相容，您也可以利用其他屬性來選擇退出。

在布建整合時，您將有機會指定您的企業需要何種退出設定：

* Dynamics 365是退出的真相來源：退出屬性將會在從Dynamics 365到Campaign的一個方向上同步
* 促銷活動是退出的真相來源：選擇退出屬性將在從促銷活動到動態365的一個方向上同步
* Dynamics 365 AND Campaign是真相的來源：選擇退出屬性將在Campaign和Dynamics 365之間雙向同步

或者，如果您有個別的程式來管理系統之間的退出同步，則可停用整合的退出資料流。

雙向選擇退出配置使用邏輯確定要寫入兩個系統的值。 邏輯會比較兩個系統之間的時間戳記（Dynamics 365中的記錄層級變更、Campaign中的屬性層級變更），以判斷哪個系統佔上風。 如果「促銷活動」包含較新的時間戳記，則會優先使用「促銷活動」值。 如果Dynamics 365包含較新的時間戳記，或者等於，則opt-out=TRUE將會成功（假設其中一個值為TRUE）。

>[!NOTE]
>
>請檢閱並視需要更新Adobe Campaign中的預設和特定類型規則，然後再在此處進行變更，以確保這些變更正確套用至所有傳出的通訊。 例如，請確定任何對應至選擇退出偏好設定的對應，都能準確反映收件者的意圖／通訊選擇，且不會不慎中斷傳送關係或交易訊息，例如客戶訂單確認。

如果您選取雙向或「促銷活動至Dynamics 365選擇退出」設定，「促銷活動選擇退出」資料將會透過工作流程定期匯出至您的「促銷活動SFTP」儲存區（請參閱下方的「促銷活動SFTP使用情形」）。 如果您的促銷活動選擇退出工作流程停止執行，您需要盡快手動重新啟動，以降低錯過選擇退出同步的可能性。

## 促銷活動SFTP使用

您的促銷活動SFTP儲存空間需要透過以下使用案例的整合來使用。  您需要確保您的SFTP帳戶有足夠的儲存容量來容納這些使用案例。  超過授權的SFTP儲存容量可能會嚴重削弱Campaign、整合和／或SFTP帳戶的功能使用。

| 使用案例 | 說明 |
|---|---|
| 初始資料載入 | 超過500k記錄的Dynamics 365表格必須匯出至促銷活動SFTP儲存，才能透過工作流程匯入。 此後，整合將使用API進行增量更新。 |
| 雙向選擇退出與Dynamics 365單向選擇退出的促銷活動 | 雙向選擇退出和促銷活動至Dynamics 365單向選擇退出資料流將運用促銷活動SFTP儲存空間。 ACS工作流將增量更改導出到SFTP資料夾。 從那裡，整合將會擷取記錄和程式。 |
| 災難恢復 | 萬一發生系統災難，將會遵循「初始資料載入」使用案例，以傳送遺失之促銷活動的增量更新。 |

## 現有促銷活動資料

此整合將同步從Dynamics 365到Campaign的連絡人和自訂實體。 整合不會修改在整合以外建立的促銷活動記錄（亦即，不是由同步工作建立），包括整合設定時現有的促銷活動記錄。

由於此整合使用促銷活動中的&#x200B;**[!UICONTROL externalId]**&#x200B;欄位，將促銷活動描述檔記錄與Dynamics 365連絡人記錄同步，因此，您必須在此促銷活動欄位(**[!UICONTROL externalId]**)中填入Dynamics 365 **[!UICONTROL contactId]**，以取得您要從Dynamics 365同步的記錄。  自訂實體也會使用Dynamics 365唯一ID同步化。 「促銷活動」自訂實體需要將此ID屬性包含為表格欄。 externalId欄可用來儲存此屬性值，但促銷活動自訂實體不需要它。

請記住，Dynamics 365仍是真相的來源，而且當整合偵測到Dynamics 365端的更新時，促銷活動描述檔資料可以覆寫。  視您現有的部署而定，也可能需要其他步驟來啟用整合；因此，建議您與Adobe技術聯絡人密切合作。

>[!NOTE]
>
>由於現有客戶部署的複雜性，建議您在規劃和設定整合時與Adobe技術聯絡人合作。

## 資料同步頻率

整合採用一種架構，可讓更新在Dynamics 365中發生後不久（即串流，而非批次處理）便可偵測並新增至處理「佇列」。 因此，不需要指定資料流執行頻率或排程。

這個例外是雙向和Campaign to Dynamics 365選擇退出資料流。 對於這些選擇退出配置，更新的ACS記錄每天通過ACS工作流導出一次至SFTP，然後整合工具讀取檔案並處理記錄。

## 資料使用協定

如果您位於EMEA或APAC地區，部分資料將會在美國處理，做為此項整合的一部分。 如需詳細資訊，請參閱[本區段](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)。
