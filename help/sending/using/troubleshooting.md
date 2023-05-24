---
title: 診斷Adobe Campaign Standard的可交付性問題
description: 瞭解在遇到Adobe Campaign Standard的可交付性問題時應做什麼。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 1%

---

# 疑難排解{#troubleshooting}

您是否遇到交付能力問題？ 你可以在這裡找到解決辦法。

## ISP的相同錯誤資訊 {#same-error-for-an-isp}

**為什麼對於特定的ISP，我總是收到相同的錯誤消息？**

如果您總是收到ISP的相同錯誤消息，則ISP可能已檢測到您的電子郵件或IP有故障。 執行以下建議：
* 檢查您是否收到連結到不存在的電子郵件地址的大比例失敗(**用戶未知** 失敗)。
* 更新訂閱表單以檢測輸入的域名中的任何錯誤(例如：gmaul.com或yaho.com)。
* 如果您注意到錯誤，指出您的郵件被聲明為垃圾郵件，或者您的郵件經常被阻止，請嘗試從目標端排除在過去12個月中未開啟或按一下您其中一條郵件的收件人。

如果問題仍然存在，請與商業或交付服務或Adobe Campaign支援聯繫。

## 德尼列斯特與隔離 {#denylist-versus-quarantine}

* **denylist上的電子郵件地址與隔離的電子郵件地址之間有何區別？**

   * 狀態 **[!UICONTROL On denylist]** 是 [反饋環](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops) （當某人將郵件報告為垃圾郵件時）。

   * 狀態 **[!UICONTROL Quarantined]** 是軟的或硬的反彈的結果。
   如需詳細資訊，請參閱[本章節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔離錯誤原因意味著什麼？**

   以下是10個可能的原因：未定義、用戶未知、無效域、denylist上的地址、拒絕、錯誤忽略、無法訪問、帳戶禁用、郵箱已滿、未連接。

   有關此的詳細資訊，請參閱 [瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)。

## 從密文清單刪除 {#removing-from-denylist}

* **我的一個收件人被錯誤地添加到密尼清單。 如何從密碼清單中刪除它們，以便我可以再次開始發送郵件？**

   * 轉到 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在相應記錄的詳細資訊中，設定 **[!UICONTROL Status]** 欄位 **[!UICONTROL Valid]**。
   * 保存記錄。

* **如何查明我的IP是否在密碼清單中？ 如何從密碼清單中刪除我的IP?**

   要檢查您的IP地址是否在denylist上，您可以使用各種網站來驗證它，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP地址是什麼](https://whatismyipaddress.com)

   通常， IP地址檢查的結果將返回一個清單，其中包含denylist的詳細資訊以及阻止IP地址的網站的名稱。

   通過按一下相應的連結，可以訪問網站詳細資訊。

   然後，您可以請求從將IP地址添加到其denylist的網站中刪除您的網站。

   >[!NOTE]
   >
   >除名過程可能因網站而異。 有些站點要求您建立帳戶，而另一些站點則只需要您提供IP地址。
