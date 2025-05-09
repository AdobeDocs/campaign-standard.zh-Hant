---
title: 使用傳遞範本
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「傳遞範本提供最常見活動型別的現成案例，有助於提升效率。」
feature: Deliverability
role: User
level: Intermediate
exl-id: ca134a7f-9035-4885-b4cb-1170b6ec10cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 10%

---

# 使用範本 {#use-templates}

傳遞範本提供最常見活動型別的現成案例，有助於提高效率。 透過範本，行銷人員可以在較短的時間內以最小的自訂部署新行銷活動。

在[本節](../../start/using/marketing-activity-templates.md)中進一步瞭解傳遞範本。

## 開始使用傳遞範本 {#gs-templates}

[傳遞範本](../../start/using/marketing-activity-templates.md#creating-a-new-template)可讓您定義一次符合您需求且可重複用於未來傳遞的一組技術和功能屬性。 然後您可以節省時間，並在需要時標準化傳遞。

當您在Adobe Campaign中管理多個品牌時，Adobe建議每個品牌使用一個子網域。 例如，銀行可以有數個子網域對應至其各個地區機構。 如果銀行擁有bluebank.com網域，其子網域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每個子網域擁有一個傳遞範本，可讓您針對每個品牌一律使用正確的預先設定引數，以避免錯誤並節省您的時間。

**提示**：若要避免Campaign發生設定錯誤，建議您複製原生範本並變更其屬性，而非建立新的範本。

## 設定地址

* 寄件者的地址為必要項，才能傳送電子郵件。

* 有些ISP （網際網路服務提供者）在接受訊息之前，會先檢查寄件者地址的有效性。

* 格式錯誤的位址可能會導致接收伺服器拒絕該位址。 您必須確定已提供正確的地址。

* 地址必須明確識別寄件者。 網域必須屬於寄件者且已註冊給寄件者。

* Adobe建議建立對應至傳送和回覆所指定地址的電子郵件帳戶。 請洽詢您的傳訊系統管理員。

在電子郵件範本屬性的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;區段中，**[!UICONTROL From (email address)]**&#x200B;欄位對應到寄件者的地址。

![](assets/template-parameters.png)

位址網域必須與您設定的子網域相同。

**[!UICONTROL Reply to]**&#x200B;欄位對應到用於回覆的電子郵件地址和名稱。

**秘訣** -Adobe建議使用現有的實際地址，例如您品牌的客戶服務。 在此情況下，如果收件者傳送回覆，客戶服務將能夠處理。

若要變更將顯示在已傳送訊息標題中的寄件者名稱，請移至[電子郵件Designer]首頁的&#x200B;**[!UICONTROL Properties]**&#x200B;標籤（可透過首頁圖示存取），然後按一下&#x200B;**[!UICONTROL Default sender name]**&#x200B;區塊。

![](assets/template-content.png)

為了提高傳遞的開頭率，Adobe建議使用讓收件者輕鬆辨識的名稱，例如您的品牌名稱。

**提示** — 若要進一步改善收件者的體驗，您可以新增個人名稱，例如「Emma from Megastore」。

如需個人化寄件者名稱的詳細資訊，請參閱[電子郵件寄件者](../../designing/using/subject-line.md#email-sender)。

## 個人化SMS寄件者名稱

在SMS範本屬性的&#x200B;**進階引數**&#x200B;區段中，**從**&#x200B;選項可讓您使用字串個人化SMS訊息寄件者的名稱。 此名稱將顯示為收件者行動電話上簡訊訊息的傳送者姓名。

如果此欄位為空，則會是使用的外部帳戶中提供的來源號碼。如果未提供來源號碼，則將使用簡短代碼。有關此項目的詳細資訊，請參閱[簡訊設定](../../administration/using/configuring-sms-channel.md)。

**提示** — 檢查您所在國家/地區有關修改寄件者地址的法規。 您也應洽詢您的簡訊服務提供者，以瞭解他們是否提供此功能。

## 設定控制組

傳送傳遞後，您可以將排除的收件者與收到傳遞的收件者之行為進行比較。 接著，您就可以評估行銷活動的效率。 深入瞭解控制群組[本節](../../sending/using/control-group.md)。

## 使用型別來套用篩選器或控制規則

型別包含在傳送任何訊息之前，在分析階段套用的檢查規則。

在範本屬性的&#x200B;**[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]**&#x200B;區段中，根據您的需求變更預設型別。

例如，為了更能控制傳出流量，您可以定義要使用的IP位址，方法為為每個子網域定義一個相似性，並為每個相似性建立一種型別。 相似性是在執行個體的組態檔案中定義。 請連絡您的Adobe Campaign管理員。

如需型別的詳細資訊，請參閱[本節](../../sending/using/managing-typologies.md)。

## 將品牌連結至範本

與品牌身分相關的已傳送電子郵件引數（例如品牌標誌或寄件者地址）會在Adobe Campaign中集中管理。 您可以建立一或多個品牌，並將其連結至傳遞範本。

如需在Adobe Campaign中使用和設定品牌的詳細資訊，請參閱品牌。

若要顯示或變更指派給傳遞範本的品牌，請選取範本的「編輯屬性」按鈕，並導覽至品牌的詳細資料。

![](assets/template-brand.png)

如需將品牌連結至範本的詳細資訊，請參閱[將品牌指派至電子郵件](../../administration/using/branding.md#assigning-a-brand-to-an-email)。

在本節[&#128279;](../../administration/using/branding.md#creating-a-brand)中瞭解如何建立設定品牌。
