---
title: 在 ISP 中斷後更新跳出資格
description: 了解如何在ISP中斷後更新退信資格。
audience: delivery
content-type: reference
topic-tags: monitoring-deliveries
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# 在 ISP 中斷後更新跳出資格 {#update-bounce-qualification.md}

如果您未執行最新版的Campaign，則此區段可能適用於您。 請洽詢您的Adobe Campaign代表。

## 內容

如果ISP中斷，透過Campaign傳送的電子郵件無法成功傳送給其收件者：這些電子郵件會錯誤標示為退信。

2020年12月，Gmail的全球問題導致傳送至有效Gmail電子郵件地址的部分電子郵件訊息錯誤地硬退信，因為Gmail伺服器所提供的無效電子郵件地址，並回信如下：*&quot;550-5.1.1您嘗試訪問的電子郵件帳戶不存在。&quot;*

Google稱，造成此問題的Gmail中斷和中斷始於12月14日早上6:55，並於12月15日東部時間下午6:09結束。 我們的資料分析還顯示，美國東部標準時間12月16日凌晨2:06,Gmail彈回數出現非常短的尖峰，其中大部分發生在美國東部標準時間下午2:00至6:30之間的12月15日。

>[!NOTE]
>
>您可以在[此頁面](https://www.google.com/appsstatus#hl=en&amp;v=status)上查看Google Workspace狀態控制面板。


根據標準退信處理邏輯，Adobe Campaign會以&#x200B;**[!UICONTROL Quarantine]**&#x200B;設定，自動將這些收件者新增至隔離清單。 **[!UICONTROL Status]**&#x200B;若要修正此問題，您需要在Campaign中尋找並移除這些收件者，或將其&#x200B;**[!UICONTROL Status]**&#x200B;變更為&#x200B;**[!UICONTROL Valid]**，以便夜間清理工作流程將其移除，以更新隔離表格。

若要尋找受此Gmail問題影響的收件者，或若此情況再次發生於其他ISP，請參閱以下指示。

## 更新流程

您需要在隔離表格上執行查詢，以篩選掉所有可能受到中斷影響的Gmail（或其他ISP）收件者，以便從隔離清單中移除這些收件者，並納入未來的Campaign電子郵件傳送中。

根據事件的時間範圍，以下是此查詢的建議准則。

>[!IMPORTANT]
>
>這些日期/時間以東部標準時區(EST)為基礎。 請根據您執行個體的時區進行調整。

對於隔離清單的&#x200B;**[!UICONTROL Error text]**&#x200B;欄位中，含有SMTP退信回應資訊的Campaign執行個體：

* **錯誤文字（隔離文字）** 包含「550-5.1.1您嘗試存取的電子郵件帳戶不存在」，而「 **錯誤文字（隔離文字）** 」包含「support.google.com」**
* **12/14/2020 6 00 AM或之後** 更新狀態(@lastModified):55:
* **12/16/2020 6 00 AM或之前** 更新狀態(@lastModified):00:

在您獲得受影響的收件者清單後，您可以將其設定為&#x200B;**[!UICONTROL Valid]**&#x200B;狀態，以便讓其透過&#x200B;**[!UICONTROL Database cleanup]**&#x200B;工作流程從隔離清單中移除，或直接從表格中刪除。

**相關主題：**
* [了解傳送失敗](../../sending/using/understanding-delivery-failures.md)
* [退回郵件資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
