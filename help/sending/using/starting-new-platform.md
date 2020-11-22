---
solution: Campaign Standard
product: campaign
title: 使用Adobe Campaign Standard啟動新平台
description: 瞭解如何使用Adobe Campaign Standard來設定新平台，同時維持您的網域和IP位址信譽。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---


# 啟動新平台{#starting-new-platform}

維護您的網域和IP位址信譽至關重要。 以下是建立新平台的一些建議。

開始在新平台上傳送電子郵件是一個敏感的步驟，因為該平台沒有任何使用記錄，也沒有信譽（當傳送的IP從未用於此目的時）。 ISP自然會懷疑從未用於傳送電子郵件的IP位址，而且會突然開始傳送大量電子郵件流量。 實際上，垃圾郵件發送者通常會使用「未知」的IP位址（從未新增至密鑰清單的位址），在偵測前傳送最多的訊息。

在生產階段開始時，您無法期望在產出方面達到操作速度。 此外，您不應嘗試以此速率發送消息，因為這可能導致ISP阻塞發送地址，並嚴重危害啟動階段的其他階段。

首次使用地址清單且可能無法完全限定的平台時，通常會啟動平台。 如果您傳送至無效的位址或蜜罐位址，這將會降低平台的聲譽。
* 如果您有無效地址清單，在首次發送前將其導入隔離表(**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**)符合您的最大利益。 如需詳細資訊，請參閱[本區段](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)。
* 但是，如果您希望重新命名無效地址，則最好在平台信譽建立後再逐個逐個地執行此操作，以便隨著時間的推移「稀釋」不良地址的使用。

總結啟動時應遵循的原則：
* **設定專用的子網域** ，以搭配Adobe傳送之電子郵件促銷活動專用的Campaign運作。
* **將無效／非活動地址導入隔離表** （如果您有此資訊）。
* **限制傳送總處理量** (技術設定：限制匹配項數)。
* **逐漸增加發送的卷**:從一開始就不要將整個資料庫作為目標，而是每次傳送時新增清單的一小部分。 這應可讓您在每個步驟增加音量，同時降低無效地址的總體速率。
* **定期傳送訊息**:從某種程度上講，最好定期發送小照片，而不是偶爾發送大宣傳。
* **密切監控傳送報表**:高錯誤指示燈可能表示技術設定配置不當。
