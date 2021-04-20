---
solution: Campaign Standard
product: campaign
title: 使用傳送範本
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「提供範本可針對大多數常見活動類型提供現成的藍本，以提高效率。」
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 10%

---


# 使用範本 {#use-templates}

提供範本可針對大多數常見活動類型提供現成的藍本，以提高效率。 使用範本，行銷人員可以在較短的時間內，以最少的自訂方式部署新的促銷活動。

進一步瞭解[本節](../../start/using/marketing-activity-templates.md)中的傳送範本。

## 開始使用傳送範本{#gs-templates}

[傳送範本](../../start/using/marketing-activity-templates.md#creating-a-new-template)可讓您定義一組符合您需求且可重複使用於未來傳送的技術和功能屬性。 然後，您就可以節省時間，並視需要標準化傳送。

當您在Adobe Campaign管理多個品牌時，Adobe建議每個品牌有一個子網域。 例如，銀行可以有多個子域，對應於每個區域機構。 如果銀行擁有bluebank.com網域，其子網域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每個子網域有一個傳送範本，讓您隨時針對每個品牌使用正確的預先設定參數，以避免錯誤並節省您的時間。

**提示**:為避免Campaign中的設定錯誤，建議您複製原生範本並變更其屬性，而不要建立新範本。

## 配置地址

* 傳送者的地址是強制性的，以允許傳送電子郵件。

* 某些ISP（Internet服務提供商）在接受消息之前檢查發件人地址的有效性。

* 錯誤形成的地址可能導致接收伺服器拒絕。 您必須確定地址正確無誤。

* 地址必須明確標識發件人。 域必須由發送者擁有並註冊。

* Adobe建議建立與傳送和回覆所指定位址對應的電子郵件帳戶。 請洽詢您的訊息系統管理員。

在電子郵件模板屬性的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;部分， **[!UICONTROL From (email address)]**&#x200B;欄位與發件人地址相對應。

![](assets/template-parameters.png)

地址域必須與您配置的子域相同。

**[!UICONTROL Reply to]**&#x200B;欄位會對應回覆使用的電子郵件地址和名稱。

**提示** -Adobe建議使用現有的實際地址，例如您品牌的客戶服務。在這種情況下，如果收件者傳送回覆，客戶服務將能夠處理。

要更改將出現在發送郵件標題中的發件人名稱，請轉至「電子郵件設計器」首頁的&#x200B;**[!UICONTROL Properties]**&#x200B;頁籤（可通過首頁表徵圖訪問），然後按一下&#x200B;**[!UICONTROL Default sender name]**&#x200B;塊。

![](assets/template-content.png)

為提高交貨的開業率，Adobe建議使用收件人可輕鬆識別的名稱，例如您的品牌名稱。

**提示** -若要進一步改善收件者的體驗，您可以新增人員的姓名，例如「Emma from Megastore」。

有關個性化發件人名稱的詳細資訊，請參閱[電子郵件發件人](../../designing/using/subject-line.md#email-sender)。

## 個人化簡訊傳送者名稱

在SMS模板屬性的&#x200B;**高級參數**&#x200B;部分中，**From**&#x200B;選項允許您使用字串個性化SMS消息發送器的名稱。 此名稱將顯示為收件者行動電話上 SMS 訊息的傳送者姓名。

如果此欄位為空，則會是使用的外部帳戶中提供的來源號碼。如果未提供來源號碼，則將使用簡短代碼。有關此項目的詳細資訊，請參閱 [SMS 設定](../../administration/using/configuring-sms-channel.md)。

**提示** -檢查您所在國家／地區有關修改發件人地址的法規。您也應洽詢您的 SMS 服務提供者，以瞭解他們是否提供此功能。

## 設定控制群組

傳送傳送後，您可以比較已排除的收件者與已接收傳送的收件者的行為。 然後，您可以衡量促銷活動的效率。 進一步瞭解控制群組[本節](../../sending/using/control-group.md)。

## 使用類型套用篩選或控制規則

類型學包含分析階段期間在傳送任何訊息之前套用的檢查規則。

在範本屬性的&#x200B;**[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]**&#x200B;區段中，根據您的需求變更預設類型。

例如，為了更好地控制對外流量，您可以定義每個子網域可使用一個相似性，並為每個相似性建立一個類型，以定義哪些IP位址。 相關性在實例的配置檔案中定義。 聯繫您的Adobe Campaign管理員。

有關類型的詳細資訊，請參閱[本節](../../sending/using/managing-typologies.md)。

## 將品牌連結至範本

與品牌身分相關的已傳送電子郵件參數（例如品牌標誌或寄件者位址），在Adobe Campaign集中管理。 您可以建立一或多個品牌，並將其連結至傳送範本。

如需在Adobe Campaign使用及設定品牌的詳細資訊，請參閱品牌推廣。

若要顯示或變更指派給傳送範本的品牌，請選取範本的「編輯屬性」按鈕，並導覽至品牌的詳細資料。

![](assets/template-brand.png)

如需將品牌連結至範本的詳細資訊，請參閱[將品牌指派至電子郵件](../../administration/using/branding.md#assigning-a-brand-to-an-email)。

瞭解如何在本節](../../administration/using/branding.md#creating-a-brand)中建立品牌[。
