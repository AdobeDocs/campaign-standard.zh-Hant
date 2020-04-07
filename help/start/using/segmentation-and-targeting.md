---
title: 細分與目標定位
description: 「瞭解Campaign中的設定檔、鎖定和受眾建立：建立受眾、匯入連絡人與Experience Cloud解決方案分享受眾，並避免行銷疲勞。」
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# 細分與目標定位{#segmentation-and-targeting}

## 設定檔 {#profiles}

使用Adobe Campaign的彈性資料模型，豐富客戶個人檔案資料並新增屬性或表格。 然後，使用這些客戶個人檔案，以更精確地細分、個人化和報告。

Adobe Campaign設定檔代表儲存在資料庫中的所有連絡人。 每個描述檔都對應至資料庫中的一個項目，其中包含要定位、限定及個別追蹤的該描述檔所需資訊。 這表示描述檔可以：客戶、潛在客戶、訂閱電子報的個人、收件者、使用者或任何其他面額（視組織而定）。

客戶個人檔案功能將您所有的客戶資料整合在一個位置：

![](assets/mkt_hist_view.png)

Adobe Campaign針對個人檔案的取得提出各種機制：透過著陸頁麵線上收集資 [料](../../channels/using/getting-started-with-landing-pages.md)、手動或自動匯入機制 [、Adobe Campaign介面中的直接輸入](../../automating/using/about-data-import-and-export.md)、透過 [](../../audiences/using/creating-profiles.md)[](../../api/using/about-campaign-standard-apis.md)Campaign API進行大量建立Campaign Api。

**相關主題：**

* 在「描述檔」區段中瞭解不同的描 [述檔](../../audiences/using/about-profiles.md) 類型。
* 在此區段中存 **取組織中** 「作用中描 [述檔」數目](../../audiences/using/active-profiles.md)。
* 瞭解如何使用工作流程定位功能自訂資料、處理複雜的資料管理工作，例如計算、匯總、去重複化和 [合併](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

為了讓您傳遞相關且有效的訊息，並有效地吸引客戶，Adobe Campaign整合了進階分析和定位功能。 有了工作流程和查詢編輯器，您就可以建立受眾，這些受眾會根據不同促銷活動的資訊、活動、語言、偏好或行銷記錄來定位。 這可讓您例如篩選訂閱的描述檔，或根據不限數量的條件建立目標對象。

觀眾會呈現在 [本頁](../../audiences/using/about-audiences.md) ，並在「觀眾」區 [段中詳細說明](../../audiences/using/creating-audiences.md) 。

**相關主題：**

* 透過傳送多語言推播通知或多語言電子郵件，瞭解如何觸 [及多地區](../../channels/using/creating-a-multilingual-push-notification.md) 的多 [語言受眾](../../channels/using/creating-a-multilingual-email.md)
* 瞭解如何建 [立查詢](../../audiences/using/creating-audiences.md#creating-query-audiences) ，以建立觀眾
* 瞭解如何在工 [作流程中建立清單](../../audiences/using/creating-audiences.md#creating-list-audiences) 、觀眾群
* 瞭解如何 [從工作流程中的檔案匯入](../../audiences/using/creating-audiences.md#creating-file-audiences) 觀眾
* 瞭解如何使用Experience [Cloud解決方](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) 案來分享受眾

## 通用資料保護法規 {#general-data-protection-regulation}

GDPR 是歐盟 (EU) 最新制定的一項隱私法規，用於協調和順應時代更新資料保護需求。GDPR 適用於所持有資料的主體居住於歐盟的 Adobe Campaign 客戶。除了Adobe Campaign中已提供的隱私權功能（包括同意管理、資料保留設定和使用者角色）外，我們還將此機會作為資料處理者加入其他功能，以協助您做好準備，以做為特定GDPR要求的資料掌控者。

請參閱本指 [南](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) ，進一步瞭解Adobe Campaign為協助您符合GDPR而提供的工具和功能。

## 疲勞管理 {#fatigue-management}

疲勞規則可讓行銷人員設定全域跨通道業務規則，自動排除促銷活動中過度徵求的個人檔案。

要實施疲勞規則，請定義每個配置檔案的最大消息數，並選擇將應用該規則的期間。 在準備傳送期間，描述檔會視已傳送給描述檔的訊息數量，從傳送中排除（如果適用）。

**相關主題：**

* 瞭解如何透 [過一組樣本](../../sending/using/fatigue-rules.md#examples) ，設計疲勞規則
* 瞭解如何建立類 [型規則](../../sending/using/about-typology-rules.md)
* 使用 [篩選規則](../../sending/using/filtering-rules.md) ，以調整訊息的對象
