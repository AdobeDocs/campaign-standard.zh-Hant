---
solution: Campaign Standard
product: campaign
title: 定義正確受眾
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 11%

---


# 定義正確受眾 {#define-the-right-audience}

目標人口是關鍵：仔細建立您的清單、在熱門的電子郵件用戶端和行動裝置上測試您的電子郵件，並確保您的電子郵件清單是最新的（沒有未知或過時的位址）。 您也可以傳送校樣，協助設定完整的驗證週期。

在本節中進一步瞭解目 [標人口族群](../../audiences/using/selecting-an-audience-in-a-message.md)

## 鎖定適當的受眾 {#target-the-right-audience}

當您的內容準備好時，您需要仔細定義將收到訊息的對象。

為了讓傳遞成功，您想要將最相關的個人化內容傳送給適當的收件者。 Adobe Campaign可讓您建立最精確的目標：您可以根據收件者的年齡、當地語系、他們購買的商品，如果他們點選先前遞送的連結，等等。 有了Adobe Campaign，您也可以定義測試設定檔、控制群組和種子位址，以確定您的目標正確無誤。

## 目標映射 {#target-mappings}

依預設，傳送範本以「描述檔」 **為目標**。 Adobe Campaign會為您的傳送提供其他目標對應，您可以根據需要進行變更。

這些映射將在 [本節中顯示](../../automating/using/query.md#targeting-dimensions-and-resources)。

您也可以建立和使用自訂的目標對應。 如需詳細資訊，請參閱[本章節](../../administration/using/target-mappings-in-campaign.md)。

## 外部資料 {#external-data}

您可以將內容傳送給儲存在外部檔案而非儲存在資料庫中的收件者。 為此，設計工作流程會從檔案將資料載入您的資料庫並建立相關對象。  在此使用 [案例中進一步瞭解](../../automating/using/use-case-calling-workflow.md)。 另請參閱 [使用參數調用工作流](../../automating/using/calling-a-workflow-with-external-parameters.md)。

## 傳送給您的訂閱者 {#send-to-subscribers}

若要傳送訊息給電子報的訂閱者，您可以直接將訂閱者鎖定在對應的資訊服務。 在本節 [中進一步瞭解](../../audiences/using/about-subscriptions.md)。

**提示** -您可以建立「清單」對象，透過工作流程鎖定電子報的訂閱者。 然後，您可以在傳送中選取此對象。 如需詳細資訊，請參閱「建 [立清單對象」](../../audiences/using/creating-audiences.md#creating-list-audiences)。

## 校樣、測試設定檔和控制群組 {#proofs-test-control-groups}

若要測試傳送內容，請在傳送至主要目標之前先使用校樣。
請確定您選取了適當的校樣收件者，因為他們會驗證訊息的表單和內容。 傳送校樣的步驟將在本節 [中介紹](../../sending/using/sending-proofs.md)。

在本節中進一步瞭解 [測試設定檔](../../audiences/using/managing-test-profiles.md)。

You can use [Control groups](../../sending/using/control-group.md) to measure the impact of your campaigns by excluding a portion of their audience. 然後，您將能夠將接收到消息的目標人口的行為與未作為目標的連絡人的行為進行比較。根據傳送日誌，您也可以在未來的行銷活動中定位控制群。

## 消除重複地址 {#deduplicate-addresses}

請務必避免使用重複的電子郵件位址，因為這會對您的目標產生影響：

* 分割目標時，可多次傳送相同的訊息。

* 如果收件者在收到訊息後取消訂閱，其重複的描述檔仍會收到未來的訊息。

刪除重複地址可保護您的發送信譽並確保良好的隔離管理。

在此使用 [案例中進一步瞭解](../../automating/using/deduplicating-data-imported-file.md)。
