---
title: 推播通知報告
description: 使用「推送通知開箱即用」報告，瞭解您的推送通知的成功。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# 推播通知報告{#push-notification-report}

>[!CAUTION]
>
>請注意，您必須拖放 **[!UICONTROL Message type]** 度量到表，以根據交貨類型來分割資料。

的 **推送通知** report提供了推式通知在Adobe Campaign的營銷表現的詳細資訊。 此現成報告可幫助您瞭解用戶如何與推送通知、移動應用程式和交付進行交互。

移動應用程式中需要一些配置才能實現推送跟蹤，請參閱 [頁](../../administration/using/push-tracking.md) 的上界。

![](assets/dynamic_report_push.png)

每個表都由摘要數字和圖表表示。 您可以更改詳細資訊在其各自的可視化設定中的顯示方式。

第一張表 **推送通知項目摘要** 分為三類：按天、按移動應用和按遞送。 它包含接收者對遞送反應的可用資料：

* **[!UICONTROL Processed/sent]**:發送的推送通知總數。
* **[!UICONTROL Delivered]**:成功發送的推送通知數，與已發送的推送通知總數相關。
* **[!UICONTROL Impressions]**:推送通知已傳送到設備且未在通知中心中保留的次數。 在大多數情況下，印數應與交貨數相似。 這確保設備收到消息並將該資訊中繼回伺服器。
* **[!UICONTROL Unique impressions]**:接收人印象數。
* **[!UICONTROL Click through rate]**:與推送通知交互的用戶百分比。
* **[!UICONTROL Open rate]**:開啟的推送通知百分比。

![](assets/dynamic_report_push_2.png)

第二張表 **推送通知按一下並開啟** 分為三類：按天、按移動應用和按遞送。 它包含每個傳遞的收件人行為的可用資料：

* **[!UICONTROL Impressions]**:收件人看到的推送通知總數。
* **[!UICONTROL Unique impressions]**:接收人印象數。
* **[!UICONTROL Click]**:推送通知已傳送到設備並由用戶按一下的次數。 用戶要麼想查看通知，然後將通知移到「推開開啟」跟蹤，要麼將其關閉。
* **[!UICONTROL Unique clicks]**:唯一用戶與推送通知交互的次數，例如按一下通知或按鈕。
* **[!UICONTROL Open]**:用戶通過點擊將推送通知發送到設備並開啟應用的總數。 這與「推式按一下」類似，但「推式開啟」在通知被撤消時不會觸發。
* **[!UICONTROL Unique Opens]**:開啟交貨的收件人數。
