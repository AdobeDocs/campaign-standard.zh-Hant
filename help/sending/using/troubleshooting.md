---
title: 疑難排解Adobe Campaign Standard中的傳遞問題
description: 瞭解在使用Adobe Campaign Standard時遇到傳遞能力問題時該怎麼做。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# 疑難排解{#troubleshooting}

您是否遇到傳遞能力問題？ 您可以在這裡找到解決方案。

## ISP的相同錯誤訊息 {#same-error-for-an-isp}

**為什麼我總是收到特定ISP的相同錯誤訊息？**

如果您一律收到ISP的相同錯誤訊息，則ISP可能會偵測到您的電子郵件或IP有錯誤。 請遵循下列建議：

* 檢查您是否收到大量連結到不存在電子郵件地址的失敗百分比（**使用者未知**&#x200B;個失敗）。
* 更新您的訂閱表單，以偵測所輸入網域名稱中的任何錯誤(例如：gmaul.com或yaho.com)。
* 如果您發現錯誤，指出您的訊息被宣告為垃圾訊息，或您的訊息被持續封鎖，請嘗試排除過去12個月內未開啟或點按您訊息之一的收件者，使其離開目標。

如果問題仍然存在，請聯絡商業或傳遞服務或Adobe Campaign支援。

## 封鎖清單與隔離 {#denylist-versus-quarantine}

* **封鎖清單上的電子郵件地址與隔離的電子郵件地址有何不同？**

   * 狀態&#x200B;**[!UICONTROL On denylist]**&#x200B;是[回饋迴路](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=zh-Hant#feedback-loops) （當某人回報訊息為垃圾訊息時）的結果。

   * 狀態&#x200B;**[!UICONTROL Quarantined]**&#x200B;是軟退信或硬退信的結果。

  如需詳細資訊，請參閱[本章節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔離錯誤原因代表什麼意思？**

  可能的原因有10個：未定義、使用者不明、網域無效、封鎖清單上的地址、已拒絕、已忽略錯誤、無法連線、帳戶已停用、信箱已滿、未連線。

  如需詳細資訊，請參閱[瞭解隔離管理](../../sending/using/understanding-quarantine-management.md)。

## 從封鎖清單移除 {#removing-from-denylist}

* **我的其中一個收件者被誤新增至封鎖清單。 如何將他們從封鎖清單中移除，以便可以開始再次傳送訊息？**

   * 移至&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在對應的記錄的詳細資訊中，將&#x200B;**[!UICONTROL Status]**&#x200B;欄位的值設定為&#x200B;**[!UICONTROL Valid]**。
   * 儲存記錄。

* **如何找出我的IP是否位於封鎖清單中？ 如何從封鎖清單移除我的IP？**

  若要檢查您的IP位址是否在封鎖清單中，您可以使用各種網站來驗證它，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP位址是什麼](https://whatismyipaddress.com)

  一般而言，IP位址檢查的結果會傳回包含封鎖清單詳細資訊以及封鎖IP位址之網站名稱的清單。

  按一下對應的連結，即可存取網站詳細資訊。

  接著，您可以要求將您的網站從新增IP位址至封鎖清單的網站中除名。

  >[!NOTE]
  >
  >除名程式可能會因網站而異。 有些網站會要求您建立帳戶，有些則只需要您提供IP位址。
