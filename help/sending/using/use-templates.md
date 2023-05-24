---
title: 使用傳遞範本
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「交付模板為最常見的活動類型提供了現成的場景，從而提高了效率。」
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

交付模板通過為大多數常見活動類型提供現成的方案而提高了效率。 使用模板，營銷人員可以在較短的時間內部署具有最小定制量的新市場活動。

瞭解有關中的交付模板的詳細資訊 [此部分](../../start/using/marketing-activity-templates.md)。

## 交貨模板入門 {#gs-templates}

A [交貨模板](../../start/using/marketing-activity-templates.md#creating-a-new-template) 使您能夠一次定義一組適合您需要且可重複使用以用於將來交貨的技術和功能屬性。 然後，您可以節省時間，並在需要時使交貨標準化。

當您在Adobe Campaign管理多個品牌時，Adobe建議每個品牌有一個子域。 例如，銀行可以具有與其每個區域機構對應的多個子域。 如果銀行擁有bluebank.com域，其子域可以是@ny.bluebank.com、@ma.bluebank.com、@ca.bluebank.com等。 每個子域有一個交付模板使您始終能夠為每個品牌使用正確的預先配置的參數，這樣可避免錯誤並節省時間。

**提示**:為避免市場活動中出現配置錯誤，建議您複製本機模板並更改其屬性，而不是建立新模板。

## 配置地址

* 發件人地址是允許發送電子郵件的必需地址。

* 某些ISP（Internet服務提供商）在接受消息之前檢查發送者地址的有效性。

* 格式錯誤的地址可能導致接收伺服器拒絕它。 您必須確保提供了正確的地址。

* 地址必須明確標識發件人。 域必須由發件人擁有並註冊。

* Adobe建議建立與為遞送和回復指定的地址對應的電子郵件帳戶。 請咨詢消息系統管理員。

在 **[!UICONTROL Advanced parameters]** 的 **[!UICONTROL From (email address)]** 欄位與發件人的地址相對應。

![](assets/template-parameters.png)

地址域必須與您配置的子域相同。

的 **[!UICONTROL Reply to]** 欄位與用於回復的電子郵件地址和名稱相對應。

**提示** -Adobe建議使用現有的實際地址，如您品牌的客戶服務。 在這種情況下，如果收件人發送回復，客戶服務將能夠處理。

要更改將出現在發送郵件標題中的發件人名稱，請轉到 **[!UICONTROL Properties]**  頁籤，然後按一下 **[!UICONTROL Default sender name]** 框。

![](assets/template-content.png)

要提高交貨的開業率，Adobe建議使用易於被收件人識別的名稱，如品牌名稱。

**提示**  — 為了進一步改善接受者的體驗，您可以添加一個人的姓名，例如「Emma from Megastore」。

有關個性化發件人名稱的詳細資訊，請參閱 [電子郵件發件人](../../designing/using/subject-line.md#email-sender)。

## 個性化SMS發件人名稱

在 **高級參數** SMS模板屬性的部分， **從** 選項允許您使用字串來個性化SMS消息發送程式的名稱。 此名稱將顯示為收件者行動電話上 SMS 訊息的傳送者姓名。

如果此欄位為空，則會是使用的外部帳戶中提供的來源號碼。如果未提供來源號碼，則將使用簡短代碼。有關此項目的詳細資訊，請參閱 [SMS 設定](../../administration/using/configuring-sms-channel.md)。

**提示**  — 檢查您所在國家/地區有關修改發件人地址的法規。 您也應洽詢您的 SMS 服務提供者，以瞭解他們是否提供此功能。

## 設定控制組

發送遞送後，您可以將排除的收件人的行為與收到遞送的收件人進行比較。 然後，您可以衡量您的活動的效率。 瞭解有關控制組的詳細資訊 [此部分](../../sending/using/control-group.md)。

## 使用類型來應用篩選器或控制規則

類型包含在分析階段應用的檢查規則，然後才會發送任何消息。

在 **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** 中，根據需要更改預設類型。

例如，為了更好地控制出站通信量，可以通過為每個子域定義一個關聯和為每個關聯建立一個類型來定義可以使用哪些IP地址。 關聯在實例的配置檔案中定義。 聯繫您的Adobe Campaign管理員。

有關類型的詳細資訊，請參閱 [此部分](../../sending/using/managing-typologies.md)。

## 將品牌連結到模板

與品牌身份（如品牌標識或發件人地址）相關的已發送電子郵件的參數在Adobe Campaign集中管理。 您可以建立一個或多個品牌並將其連結到交付模板。

有關在Adobe Campaign使用和配置品牌的詳細資訊，請參閱品牌推廣。

要顯示或更改分配給交貨模板的品牌，請選擇模板的「編輯屬性」按鈕並導航至品牌的詳細資訊。

![](assets/template-brand.png)

有關將品牌連結到模板的詳細資訊，請參閱 [為電子郵件分配品牌](../../administration/using/branding.md#assigning-a-brand-to-an-email)。

瞭解如何建立和配置品牌 [此部分](../../administration/using/branding.md#creating-a-brand)。
