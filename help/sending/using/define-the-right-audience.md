---
title: 定義正確對象
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 「準備好內容後，請瞭解如何仔細定義哪些人將會收到您的訊息。」
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

目標人口是關鍵：仔細建立您的清單，在熱門電子郵件使用者端和行動裝置上測試您的電子郵件，並確保您的電子郵件清單是最新的（沒有未知或過時的地址）。 您也可以傳送校樣來幫助設定完整的驗證週期。

進一步瞭解目標母體 [在本節中](../../audiences/using/selecting-an-audience-in-a-message.md)

## 鎖定正確的對象 {#target-the-right-audience}

內容準備就緒後，您需要仔細定義將接收訊息的人員。

若要成功傳遞，您想要將最相關的個人化內容傳送給正確的收件者。 Adobe Campaign可讓您建立最精確的目標：您可以根據收件者的年齡、本地化、購買內容、是否在上一次傳送中按一下連結等來選取收件者。 透過Adobe Campaign，您還可以定義測試設定檔、控制組和種子地址，以確保您的目標正確無誤。

## 目標對應 {#target-mappings}

依預設，傳遞範本會鎖定目標 **設定檔**. Adobe Campaign為您的傳送提供其他目標對應，您可以視需求加以變更。

下列對應會出現 [在本節中](../../automating/using/query.md#targeting-dimensions-and-resources).

您也可以建立並使用自訂的目標對應。 如需詳細資訊，請參閱[本章節](../../administration/using/target-mappings-in-campaign.md)。

## 外部資料 {#external-data}

您可以傳遞至儲存在外部檔案中而非儲存在資料庫中的收件者。 為此，設計工作流程將從檔案將資料載入您的資料庫，並建立關聯的對象。  瞭解更多 [在此使用案例中](../../automating/using/use-case-calling-workflow.md). 另請參閱 [使用引數呼叫工作流程](../../automating/using/calling-a-workflow-with-external-parameters.md).

## 傳送給您的訂閱者 {#send-to-subscribers}

若要傳送訊息給電子報的訂閱者，您可以直接將訂閱者定位到對應的資訊服務。 瞭解更多 [在本節中](../../audiences/using/about-subscriptions.md).

**秘訣**  — 您可以建立清單對象，使用工作流程鎖定您電子報的訂閱者。 然後，您便可以在傳送中選取此對象。 有關詳細資訊，請參閱 [建立清單對象](../../audiences/using/creating-audiences.md#creating-list-audiences).

## 校樣、測試設定檔和控制組 {#proofs-test-control-groups}

若要測試您的傳遞，請在傳送至主要目標之前使用證明。
請務必選取適當的校樣收件者，因為他們會驗證訊息的表單和內容。 以下說明傳送校樣的步驟 [在本節中](../../sending/using/sending-proofs.md).

進一步瞭解測試設定檔 [在本節中](../../audiences/using/managing-test-profiles.md).

您可以使用 [控制組](../../sending/using/control-group.md) 透過排除部分對象，以評估行銷活動的影響。 然後，您將能夠將接收到消息的目標人口的行為與未作為目標的聯絡人的行為進行比較。根據傳送日誌，您也可以在未來的行銷活動中定位控制群。

## 重複位址 {#deduplicate-addresses}

請務必避免電子郵件地址重複，因為這可能會對您的目標造成影響：

* 分割目標時，相同的訊息可以傳送多次。

* 如果收件者在收到訊息後取消訂閱，其重複的設定檔仍會收到未來的訊息。

對地址進行重複資料刪除可保護您的傳送信譽，並確保良好的隔離管理。

瞭解更多 [在此使用案例中](../../automating/using/deduplicating-data-imported-file.md).
