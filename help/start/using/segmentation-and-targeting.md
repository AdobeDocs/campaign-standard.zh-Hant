---
title: 細分與鎖定
seo-title: 細分與鎖定
description: 細分與鎖定
seo-description: 「瞭解促銷活動中的設定檔、定位和對象建立：建立受眾、匯入聯絡人與Experience Cloud解決方案共用受眾，避免行銷疲勞」。
page-status-flag: 從未啓動
uuid: 71f53808-0309-49f6-a4 ee-3446eac9758 a
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9443-4aec-b378-fd0 Beb50 e9 fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Segmentation and targeting{#segmentation-and-targeting}

## Profiles {#profiles}

使用Adobe Campaign的靈活資料模型豐富客戶個人檔案資料，並新增新屬性或表格。然後，使用這些客戶個人檔案進行更精確的細分、個人化和報告。

Adobe Campaign設定檔代表儲存在資料庫中的所有聯絡人。每個描述檔對應至資料庫中的一個項目，其中包含該描述檔要被定位、符合資格及個別追蹤的必要資訊。這表示設定檔可以是：客戶、潛在客戶、個別訂閱給電子報、收件者、使用者或任何其他依組織而定的分母。

客戶個人檔案功能可整合所有客戶資料：

![](assets/mkt_hist_view.png)

Adobe Campaign proposes various mechanisms for profile acquisition: collecting data online via [landing pages](../../channels/using/about-landing-pages.md), manual or [automated import mechanisms](../../automating/using/about-data-import-and-export.md), [direct input](../../audiences/using/creating-profiles.md) in the Adobe Campaign interface, bulk creation through [Campaign APIs](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

**相關主題：**

* Learn about different types of profiles in the [Profiles](../../audiences/using/about-profiles.md) section.
* Access the number of **Active Profiles** in your organization in [this section](../../audiences/using/active-profiles.md).
* Learn how to customize your data, handle complex data management tasks, such as calculations, aggregates, de-dupes, and merges, using [workflow targeting capabilities](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

Adobe Campaign整合了進階分析與鎖定功能，讓您能夠提供切實有用且有效的訊息，並有效吸引客戶。由於工作流程和查詢編輯器，您可以建立將由不同促銷活動鎖定的受眾，視您擁有的資訊、其活動、語言、偏好或行銷歷史記錄而定。這可讓您篩選訂閱設定檔，或以不限數量的標準建立目標受眾。

Audiences are presented [in this page](../../audiences/using/about-audiences.md) and detailed in the [Audiences](../../audiences/using/creating-audiences.md) section.

**相關主題：**

* Learn how to reach multilingual audiences across multiple regions by sending [multilingual push notifications](../../channels/using/creating-a-multilingual-push-notification.md) or [multilingual emails](../../channels/using/creating-a-multilingual-email.md)
* Learn how to [create queries](../../audiences/using/creating-audiences.md#creating-query-audiences) to build audiences
* Learn how to [create list audiences](../../audiences/using/creating-audiences.md#creating-list-audiences) in a workflow
* Learn how to [import an audience from a file](../../audiences/using/creating-audiences.md#creating-file-audiences) in a workflow
* Learn how to [share audiences](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) with Experience Cloud solutions

## General Data Protection Regulation {#general-data-protection-regulation}

GDPR是歐盟(EU)新的隱私權法律，用於協調資料保護要求並現代規範資料保護要求。GDPR適用於持有位於歐盟之資料主體之資料的Adobe Campaign客戶。除了Adobe Campaign中已提供的隱私權功能(包括同意管理、資料保留設定及使用者角色)，我們也將此機會納入資料處理方的角色中，以納入額外的功能，以協助您為特定GDPR要求的資料掌控者做好準備。

Refer to this [guide](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) to learn more about the tools and functionalities that Adobe Campaign provides to help you become GDPR compliant.

## Fatigue management {#fatigue-management}

疲勞規則可讓行銷人員設定全域跨通道業務規則，自動排除促銷活動中過度詢問的個人檔案。

若要實施疲勞規則，您可以定義每個描述檔的訊息數目上限，並選取規則適用的時段。在傳送準備期間，會根據已傳送給他們的訊息數目，從傳送中排除描述檔。

**相關主題：**

* Learn how to [design fatigue rules](../../administration/using/fatigue-rules.md#examples) through a set of samples
* Learn how to create [typology rules](../../administration/using/about-typology-rules.md)
* Use [filter rules](../../administration/using/filtering-rules.md) to refine the audience of your messages
