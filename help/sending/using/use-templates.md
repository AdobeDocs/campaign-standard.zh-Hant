---
solution: Campaign Standard
product: campaign
title: 使用傳遞範本
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「傳遞範本可為最常見的活動類型提供現成的案例，借此提高效率。」
feature: 達成能力
role: User
level: Intermediate
exl-id: ca134a7f-9035-4885-b4cb-1170b6ec10cc
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 10%

---

# 使用範本 {#use-templates}

傳遞範本可為最常見的活動類型提供現成的案例，借此提高效率。 透過範本，行銷人員可以在較短的時間內以最少的自訂方式部署新的行銷活動。

在[此小節](../../start/using/marketing-activity-templates.md)中深入了解傳遞範本。

## 開始使用傳遞範本 {#gs-templates}

[傳遞範本](../../start/using/marketing-activity-templates.md#creating-a-new-template)可讓您一次定義一組符合您需求且可重複使用的技術和功能屬性。 然後，您就可以視需要節省時間並標準化傳送。

當您在Adobe Campaign中管理多個品牌時，Adobe建議每個品牌有一個子網域。 例如，銀行可以有與其每個地區機構對應的數個子網域。 如果銀行擁有bluebank.com域，其子域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每個子網域有一個傳送範本可讓您一律為每個品牌使用正確的預先設定參數，以避免錯誤並節省時間。

**提示**:為避免在Campaign中發生設定錯誤，建議您複製原生範本並變更其屬性，而非建立新範本。

## 配置地址

* 寄件者的地址是必填欄位，以允許傳送電子郵件。

* 某些ISP（網際網路服務提供者）在接受訊息之前，會檢查寄件者地址的有效性。

* 錯誤形成的地址可能導致接收伺服器拒絕該地址。 您必須確保提供正確的地址。

* 地址必須明確標識發件人。 域必須由發件人擁有並註冊。

* Adobe建議建立與為傳送和回覆指定的地址對應的電子郵件帳戶。 請咨詢您的消息系統管理員。

在電子郵件範本屬性的&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;區段中， **[!UICONTROL From (email address)]**&#x200B;欄位與寄件者的地址對應。

![](assets/template-parameters.png)

地址域必須與您配置的子域相同。

**[!UICONTROL Reply to]**&#x200B;欄位對應於用於回覆的電子郵件地址和名稱。

**提示**  -Adobe建議使用現有的實際地址，例如您品牌的客戶服務。在此情況下，如果收件者傳送回覆，客戶服務將能處理。

要更改將出現在已發送郵件標題中的發件人名稱，請轉至電子郵件設計器首頁的&#x200B;**[!UICONTROL Properties]**&#x200B;頁簽（可通過首頁表徵圖訪問），然後按一下&#x200B;**[!UICONTROL Default sender name]**&#x200B;塊。

![](assets/template-content.png)

若要提高傳送的開啟率，Adobe建議使用可供收件者輕鬆識別的名稱，例如您的品牌名稱。

**提示**  — 若要進一步改善收件者的體驗，您可以新增人員名稱，例如「Emma from Megastore」。

有關個人化發件人名稱的詳細資訊，請參閱[電子郵件發件人](../../designing/using/subject-line.md#email-sender)。

## 個人化SMS寄件者名稱

在SMS範本屬性的&#x200B;**進階參數**&#x200B;區段中，**From**&#x200B;選項可讓您使用字串個人化SMS訊息寄件者的名稱。 此名稱將顯示為收件者行動電話上 SMS 訊息的傳送者姓名。

如果此欄位為空，則會是使用的外部帳戶中提供的來源號碼。如果未提供來源號碼，則將使用簡短代碼。有關此項目的詳細資訊，請參閱 [SMS 設定](../../administration/using/configuring-sms-channel.md)。

**提示**  — 檢查您所在國家/地區有關修改寄件者地址的法規。您也應洽詢您的 SMS 服務提供者，以瞭解他們是否提供此功能。

## 設定控制組

傳送後，您可以比較已排除收件者的行為與已接收傳送的收件者。 然後，您可以測量行銷活動的效率。 進一步了解控制組[此部分](../../sending/using/control-group.md)。

## 使用類型來套用篩選器或控制規則

類型包含在分析階段期間套用的檢查規則，然後再傳送任何訊息。

在範本屬性的&#x200B;**[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]**&#x200B;區段中，根據您的需求變更預設類型。

例如，為了更妥善地控制傳出流量，您可以定義可使用的IP位址，方法是為每個子網域定義一個相關性，並為每個相關性建立一個類型。 相關性會在執行個體的設定檔案中定義。 請連絡您的Adobe Campaign管理員。

有關類型的詳細資訊，請參閱[此區段](../../sending/using/managing-typologies.md)。

## 將品牌連結至範本

與品牌身分相關的已傳送電子郵件參數（例如品牌標誌或寄件者地址）會在Adobe Campaign中央管理。 您可以建立一或多個品牌，並將其連結至傳遞範本。

如需在Adobe Campaign中使用和設定品牌的詳細資訊，請參閱品牌推廣。

若要顯示或變更指派給傳遞範本的品牌，請選取範本的「編輯屬性」按鈕，並導覽至品牌的詳細資料。

![](assets/template-brand.png)

如需將品牌連結至範本的詳細資訊，請參閱[將品牌指派至電子郵件](../../administration/using/branding.md#assigning-a-brand-to-an-email)。

了解如何在本小節](../../administration/using/branding.md#creating-a-brand)中建立設定品牌[。
