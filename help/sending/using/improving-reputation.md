---
solution: Campaign Standard
product: campaign
title: 提高你在Adobe Campaign Standard的聲譽
description: 瞭解如何透過管理重複的電子郵件位址和隔離來改善您與Adobe Campaign Standard的聲譽。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 傳送能力
role: 業務從業人員
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 2%

---


# 提升您的名譽{#improving-reputation}

為避免讓收件者筋疲力盡，請從目標位置刪除重複的電子郵件地址。 此步驟可保護您的發送信譽並確保良好的隔離管理。 Adobe Campaign提供了實施這些建議的必要工具，並避免ISP加入密文清單的風險。

在下面，您將找到有關複製和隔離管理的詳細資訊。

## 複製{#duplicates}

擁有重複的電子郵件地址可能會產生多種後果：
* 相同的訊息會多次傳送。 即使Campaign在傳送之前預設會執行去重複化程式，在分割目標時，也無法停止由具有相同內容的不同動作所傳送的相同訊息。
* 未接受取消訂閱請求。 如果收件者在收到訊息後取消訂閱，則其重複的描述檔仍符合日後訊息的資格。

除了選擇加入程式的這種側步外，這種情況還可能導致用戶將郵件視為垃圾郵件，並在ISP觸發拒絕清單程式。

在資料庫上執行操作時必須特別小心。 為盡量避免重複，必須執行下列動作：
* **進口必須精心配置。** 在選擇協調密鑰時，這尤其重要。
* **修改電子郵件地址時請務必留意。** 變更的電子郵件地址也可以是重複的來源。特別是，兩個具有不同域的地址可以被路由到同一郵箱，例如，在某公司更改了名稱並在特定時間內維護了前一個域的情況下：joe.doe@amce-co.com和joe.doe@acme-rebranded.com。
* **在自動匯入時請留意。** 無論是清單還是來自其他資料庫，它們都是管理配置檔案時要考慮的元素。刪除或移動另一個分區中的配置檔案時會發生什麼情況？ 例如，在下訂單時，可通過自動導入在初始分區中重新建立。
* **應將配置檔案分類到不同的資料夾。**

同樣地，有時不同分區之間的複製是正常的。 例如，當傳送給第三方或不同的公司實體時，出於不同原因，同一個人是收件者是合乎邏輯的。 但是，在同一分區中查找重複項很少是正常的。

## 隔離{#quarantines}

Adobe Campaign 管理隔離地址清單。在傳送分析期間，預設會排除隔離地址的收件者：它們不是目標。

隔離管理在[本節](../../sending/using/understanding-quarantine-management.md)中有詳細說明。

例如，當收件箱已滿或地址不存在時，可以隔離電子郵件地址。 在所有情況下，隔離都符合[本節](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine)中的具體規則。
