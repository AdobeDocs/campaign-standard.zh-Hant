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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 0%

---


# 疑難排解{#troubleshooting}

您是否遇到交付能力問題？ 您可以在這裡找到解決方案。

## ISP的相同錯誤資訊 {#same-error-for-an-isp}

**為什麼對於特定ISP，我總是收到相同的錯誤訊息？**

如果您總是收到相同的ISP錯誤訊息，則ISP可能會偵測到您的電子郵件或IP有故障。 執行下列建議：
* 檢查您是否收到連結至不存在之電子郵件地址的大部分失敗(使&#x200B;**用者未知** 失敗)。
* 更新訂閱表單以偵測輸入的網域名稱中的任何錯誤(例如： gmaul.com或yaho.com)。
* 如果您發現錯誤，指出您的訊息已宣告為垃圾訊息，或您的訊息經常遭到封鎖，請嘗試將過去12個月中未開啟或點按其中一則訊息的收件者排除在目標位置。

如果問題持續存在，請聯絡商業或傳遞性服務，或Adobe Campaign支援。

## 塊清單與隔離 {#block-list-versus-quarantine}

* **阻止清單上的電子郵件地址與隔離的電子郵件地址之間有何區別？**

   * 狀態是 **[!UICONTROL On block list]** 回饋迴路的結果（當某人將訊息報告為垃圾訊息時）。

   * 狀態 **[!UICONTROL Quarantined]** 是軟反彈或硬反彈的結果。
   有關此內容的詳細資訊，請參 [閱本節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-block-list)。

* **不同的隔離錯誤原因意味著什麼？**

   以下是10個可能的原因： 未定義、用戶未知、無效域、塊清單上的地址、拒絕、錯誤忽略、無法訪問、帳戶禁用、郵箱已滿、未連接。

   有關詳細資訊，請參閱了 [解隔離管理](../../sending/using/understanding-quarantine-management.md)。

## 從塊清單中刪除 {#removing-from-block-list}

* **我的其中一個收件者被錯誤地加入區塊清單。 如何從塊清單中刪除它們，以便我可以再次開始發送郵件？**

   * 前往 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**。
   * 在對應記錄的詳細資訊中，將欄位的值 **[!UICONTROL Status]** 設定為 **[!UICONTROL Valid]**。
   * 保存記錄。

* **我要如何得知我的其中一個IP是否在區塊清單中？ 如何從塊清單中刪除IP?**

   若要檢查您的IP位址是否在區塊清單中，您可以使用各種網站來驗證它，例如：
   * [MX工具箱](https://mxtoolbox.com/)
   * [我的IP地址是什麼](https://whatismyipaddress.com)
   通常，IP地址檢查的結果將返回一個清單，其中包含塊清單的詳細資訊以及阻止IP地址的網站的名稱。

   按一下對應的連結，即可存取網站詳細資訊。

   然後，您可以要求將您的網站從將IP位址新增至其區塊清單的網站中除名。

   >[!NOTE]
   >
   >除名程式可能因網站而異。 有些網站會要求您建立帳戶，而有些網站則只需您提供IP位址。
