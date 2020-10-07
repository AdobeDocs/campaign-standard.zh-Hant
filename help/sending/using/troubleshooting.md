---
title: 疑難排解Adobe Campaign Standard中的傳遞能力問題
description: 瞭解在Adobe Campaign Standard遇到傳遞性問題時，該如何辦事。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 疑難排解{#troubleshooting}

您是否遇到交付能力問題？ 您可以在這裡找到解決方案。

## ISP的相同錯誤資訊 {#same-error-for-an-isp}

**為什麼對於特定ISP，我總是收到相同的錯誤訊息？**

如果您總是收到相同的ISP錯誤訊息，則ISP可能會偵測到您的電子郵件或IP有故障。 執行下列建議：
* 檢查您是否收到連結至不存在之電子郵件地址的大部分失敗(使&#x200B;**用者未知** 失敗)。
* 更新訂閱表單以偵測輸入的網域名稱中的任何錯誤(例如：gmaul.com或yaho.com)。
* 如果您發現錯誤，指出您的訊息已宣告為垃圾訊息，或您的訊息經常遭到封鎖，請嘗試將過去12個月中未開啟或點按其中一則訊息的收件者排除在目標位置。

如果問題持續存在，請聯絡商業或傳遞性服務，或Adobe Campaign支援。

## Denylist與隔離 {#denylist-versus-quarantine}

* **拒絕清單上的電子郵件地址與隔離的電子郵件地址之間有何區別？**

   * 狀態是 **[!UICONTROL On denylist]** 回饋迴路的結果（當某人將訊息報告為垃圾訊息時）。

   * 狀態 **[!UICONTROL Quarantined]** 是軟反彈或硬反彈的結果。
   如需詳細資訊，請參閱[本區段](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)。

* **不同的隔離錯誤原因意味著什麼？**

   以下是10個可能的原因：未定義、用戶未知、無效域、拒絕、錯誤忽略、無法訪問、帳戶禁用、郵箱已滿、未連接。

   For more on this, see [Understanding quarantine management](../../sending/using/understanding-quarantine-management.md).

## 從denylist移除 {#removing-from-denylist}

* **我的收件者中有一人被誤加入密尼列斯特。 我要如何從密文清單中移除它們，以便重新傳送訊息？**

   * 前往 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在對應記錄的詳細資訊中，將欄位的值 **[!UICONTROL Status]** 設定為 **[!UICONTROL Valid]**。
   * 保存記錄。

* **我要如何得知我的其中一個IP是否在密文清單中？ 如何從密鑰清單移除IP?**

   若要檢查您的IP位址是否在登入清單中，您可以使用各種網站來驗證，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP地址是什麼](https://whatismyipaddress.com)

   通常，IP位址檢查的結果會傳回一個清單，其中包含登入清單的詳細資訊以及封鎖IP位址的網站名稱。

   按一下對應的連結，即可存取網站詳細資訊。

   然後，您可以要求將您的網站從新增IP位址至其登入清單的網站中移除。

   >[!NOTE]
   >
   >除名程式可能因網站而異。 有些網站會要求您建立帳戶，而有些網站則只需您提供IP位址。
