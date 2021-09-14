---
title: 定義正確對象
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「當您的內容準備就緒時，請了解您如何仔細定義將接收您訊息的對象。」
feature: Deliverability
role: User
level: Intermediate
exl-id: 1e06fd9d-e850-4856-8f7b-b581dbe157df
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 11%

---

# 定義正確對象 {#define-the-right-audience}

目標人口是關鍵：請謹慎建立清單，在熱門的電子郵件用戶端和行動裝置上測試您的電子郵件，並確保您的電子郵件清單為最新狀態（沒有未知或過時的地址）。 您也可以傳送校樣，協助您設定完整的驗證週期。

在本小節](../../audiences/using/selecting-an-audience-in-a-message.md)中進一步了解目標母體[

## 鎖定正確的對象 {#target-the-right-audience}

當您的內容準備就緒時，您必須謹慎定義將接收訊息的對象。

為了讓傳遞成功，您想要將最相關的個人化內容傳送給正確的收件者。 Adobe Campaign可讓您建立最精確的目標：您可以根據收件者的年齡、當地語系化、他們購買的內容，以及他們按一下先前傳遞的連結等來選取收件者。 使用Adobe Campaign，您也可以定義測試設定檔、控制群組和種子地址，以確保目標正確無誤。

## 目標對應 {#target-mappings}

預設情況下，傳遞範本目標為&#x200B;**設定檔**。 Adobe Campaign提供您傳送的其他目標對應，您可以根據需求進行變更。

這些映射在此部分](../../automating/using/query.md#targeting-dimensions-and-resources)中顯示。[

您也可以建立和使用自訂的目標對應。 如需詳細資訊，請參閱[本章節](../../administration/using/target-mappings-in-campaign.md)。

## 外部資料 {#external-data}

您可以傳送給儲存在外部檔案中而非儲存在資料庫中的收件者。 為此，設計工作流程將從檔案將資料載入您的資料庫，並建立相關的對象。  了解更多[在此使用案例中](../../automating/using/use-case-calling-workflow.md)。 另請參閱[使用參數呼叫工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md)。

## 傳送給您的訂閱者 {#send-to-subscribers}

若要傳送訊息給電子報的訂閱者，您可以直接將訂閱者鎖定在對應的資訊服務。 了解更多[，請參閱本節](../../audiences/using/about-subscriptions.md)。

**提示**  — 您可以建立「清單」對象，透過工作流程鎖定電子報的訂閱者。然後您就可以在傳送中選取此對象。 如需詳細資訊，請參閱[建立清單對象](../../audiences/using/creating-audiences.md#creating-list-audiences)。

## 校樣、測試設定檔和控制組 {#proofs-test-control-groups}

若要測試您的傳送，請在傳送至主要目標之前使用校樣。
請確定您選取適當的校樣收件者，因為他們會驗證訊息的表單和內容。 傳送校樣的步驟在本小節](../../sending/using/sending-proofs.md)中介紹。[

了解更多有關測試設定檔[的資訊，請參閱本節](../../audiences/using/managing-test-profiles.md)。

您可以使用[控制群組](../../sending/using/control-group.md)來透過排除其閱聽眾的一部分來評估行銷活動的影響。 然後，您將能夠將接收到消息的目標人口的行為與未作為目標的聯絡人的行為進行比較。根據傳送日誌，您也可以在未來的行銷活動中定位控制群。

## 去重複地址 {#deduplicate-addresses}

請務必避免有重複的電子郵件地址，因為這可能會影響您的目標：

* 分割目標時，可以多次傳送相同的訊息。

* 如果收件者在收到訊息後取消訂閱，其重複的設定檔仍會收到未來的訊息。

重複刪除地址可保護您的發送信譽並確保良好的隔離管理。

了解更多[在此使用案例中](../../automating/using/deduplicating-data-imported-file.md)。
