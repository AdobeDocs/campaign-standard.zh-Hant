---
title: 定義正確對象
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「當您的內容準備好後，瞭解您如何仔細定義接收您的消息的人。」
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

目標人口是關鍵：精心構建您的清單，在常用電子郵件客戶端和移動設備上test電子郵件，並確保您的電子郵件清單是最新的（沒有未知或過時的地址）。 您還可以發送校樣，以幫助設定完整的驗證週期。

瞭解有關目標群體的詳細資訊 [此部分](../../audiences/using/selecting-an-audience-in-a-message.md)

## 瞄準正確的受眾 {#target-the-right-audience}

當您的內容準備好後，您需要仔細定義接收您的消息的人。

要使交付成功，您希望將最相關的個性化內容發送到正確的收件人。 Adobe Campaign使您能夠構建最準確的目標：您可以根據收件人的年齡、本地化、他們購買的內容，如果他們按一下了先前遞送中的連結，等等來選擇收件人。 使用Adobe Campaign，您還可以定義test配置檔案、控制組和種子地址，以確保目標正確。

## 目標對應 {#target-mappings}

預設情況下，交貨模板目標 **配置檔案**。 Adobe Campaign為您的交貨提供了其他目標映射，您可以根據需要進行更改。

這些映射被顯示 [此部分](../../automating/using/query.md#targeting-dimensions-and-resources)。

您還可以建立和使用自定義的目標映射。 如需詳細資訊，請參閱[本章節](../../administration/using/target-mappings-in-campaign.md)。

## 外部資料 {#external-data}

您可以傳遞給儲存在外部檔案中而不是保存在資料庫中的收件人。 為此，設計工作流將從檔案將資料載入到資料庫中並建立關聯的訪問群體。  瞭解更多資訊 [在本案中](../../automating/using/use-case-calling-workflow.md)。 另請參閱 [使用參數調用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)。

## 發送給您的訂閱者 {#send-to-subscribers}

要向新聞簡報的訂閱者發送消息，您可以直接將訂閱者定位到相應的資訊服務。 瞭解更多資訊 [此部分](../../audiences/using/about-subscriptions.md)。

**提示**  — 您可以建立「清單」受眾，該受眾使用工作流針對新聞稿的訂閱者。 然後，您可以在遞送中選擇此受眾。 有關此的詳細資訊，請參閱 [建立清單訪問群](../../audiences/using/creating-audiences.md#creating-list-audiences)。

## 校樣、test配置檔案和控制組 {#proofs-test-control-groups}

要test交貨，請在發送到主目標之前使用校樣。
確保您選擇適當的證明收件人，因為他們會驗證表單和郵件內容。 給出了校樣的發送步驟 [此部分](../../sending/using/sending-proofs.md)。

瞭解有關test配置檔案的詳細資訊 [此部分](../../audiences/using/managing-test-profiles.md)。

您可以使用 [控制組](../../sending/using/control-group.md) 通過排除部分受眾來衡量您的活動的影響。 然後，您將能夠將接收到消息的目標人口的行為與未作為目標的聯絡人的行為進行比較。根據傳送日誌，您也可以在未來的行銷活動中定位控制群。

## 消除重複地址 {#deduplicate-addresses}

避免使用重複的電子郵件地址非常重要，因為這樣會對您的目標產生影響：

* 當目標被拆分時，可以多次發送同一消息。

* 如果收件人在收到消息後取消訂閱，則其重複的配置檔案仍將接收將來的消息。

消除重複地址可保護您的發送信譽並確保良好的隔離管理。

瞭解更多資訊 [在本案中](../../automating/using/deduplicating-data-imported-file.md)。
