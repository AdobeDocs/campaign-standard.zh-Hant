---
title: 疑難排解Adobe Campaign Standard中的傳遞能力問題
description: 了解發生Adobe Campaign Standard的傳遞能力問題時該做什麼。
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

您是否遇到傳遞能力問題？ 你可以在這裡找到解決方案。

## ISP的相同錯誤訊息 {#same-error-for-an-isp}

**為何對特定ISP一律會收到相同的錯誤訊息？**

如果您一律收到ISP的相同錯誤訊息，則ISP可能已偵測到您的電子郵件或IP有問題。 執行下列建議：
* 檢查您是否收到連結到不存在的電子郵件地址的大百分比故障（**用戶未知**&#x200B;故障）。
* 更新訂閱表單以偵測輸入的網域名稱中的任何錯誤(例如：gmaul.com或yaho.com)。
* 如果您發現錯誤，指出您的郵件被宣告為垃圾郵件，或您的郵件被持續阻止，請嘗試排除在目標前12個月內未開啟或點擊您其中一條郵件的收件人。

如果問題仍然存在，請聯絡商業或傳遞服務，或Adobe Campaign支援。

## 封鎖清單與隔離 {#denylist-versus-quarantine}

* **封鎖清單上的電子郵件地址與隔離的電子郵件地址之間有何差異？**

   * 狀態&#x200B;**[!UICONTROL On denylist]**&#x200B;是[反饋循環](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)的結果（當某人報告郵件為垃圾郵件時）。

   * 狀態&#x200B;**[!UICONTROL Quarantined]**&#x200B;是軟退信或硬退信的結果。
   如需詳細資訊，請參閱[本區段](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔離錯誤原因代表什麼？**

   原因有10個：未定義，用戶未知，無效域，封鎖清單上的地址，拒絕，錯誤被忽略，無法訪問，帳戶已禁用，郵箱已滿，未連接。

   有關詳細資訊，請參閱[了解隔離管理](../../sending/using/understanding-quarantine-management.md)。

## 從封鎖清單中移除 {#removing-from-denylist}

* **我的一個收件者被錯誤地加入封鎖名單。如何從封鎖清單中移除這些訊息，以便開始再次傳送訊息？**

   * 前往&#x200B;**[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在相應記錄的詳細資訊中，將&#x200B;**[!UICONTROL Status]**&#x200B;欄位的值設定為&#x200B;**[!UICONTROL Valid]**。
   * 保存記錄。

* **如何找出我的IP是否列在封鎖清單中？如何從封鎖清單中移除我的IP?**

   若要檢查您的IP位址是否列在封鎖清單中，您可以使用各種網站來驗證，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP地址是什麼](https://whatismyipaddress.com)

   一般而言，IP位址檢查的結果會傳回包含封鎖清單詳細資訊以及封鎖IP位址之網站名稱的清單。

   按一下對應的連結，即可存取網站詳細資訊。

   然後，您可以請求將您的網站從將IP位址新增至封鎖清單的網站中除名。

   >[!NOTE]
   >
   >除名程式可能會因網站而異。 有些網站會要求您建立帳戶，有些網站則只需要您提供IP位址。
