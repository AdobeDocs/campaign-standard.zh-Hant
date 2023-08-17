---
title: 在 ISP 中斷後更新跳出資格
description: 瞭解如何在ISP中斷後更新跳出資格。
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: f81b8a3b076a6e29b697f21ea4d99fa7d5b6788c
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 4%

---

# 在 ISP 中斷後更新跳出資格 {#update-bounce-qualification.md}

## 內容

如果ISP發生中斷，透過Campaign傳送的電子郵件無法成功傳送給其收件者：這些電子郵件將錯誤標示為跳出。

2020年12月，Gmail發生全域問題，導致傳送至有效Gmail電子郵件地址的某些電子郵件訊息被Gmail伺服器錯誤地硬退為無效的電子郵件地址，並出現以下回應： *「550-5.1.1您嘗試存取的電子郵件帳戶不存在。」*

Google表示，造成Gmail中斷和作業中斷的問題始於12月14日早上6:55，結束於12月15日晚上6:09 EST。 我們的資料分析也顯示Gmail在12月16日凌晨2:06點（東部標準時間）跳出數出現非常短暫的尖峰，其中大多數發生在12月15日下午2:00 （東部標準時間）至下午6:30 （東部標準時間）之間。

>[!NOTE]
>
>您可以檢查Google工作區狀態控制面板，於 [此頁面](https://www.google.com/appsstatus#hl=en&amp;v=status).


根據標準退信處理邏輯，Adobe Campaign會使用自動將這些收件者新增至隔離清單 **[!UICONTROL Status]** 設定 **[!UICONTROL Quarantine]**. 若要修正此問題，您需要找到並移除這些收件者，或變更其收件者，以更新Campaign中的隔離表。 **[!UICONTROL Status]** 至 **[!UICONTROL Valid]** 以便「夜間清理」工作流程會將其移除。

若要尋找受此Gmail問題影響的收件者，或當此問題再次發生在任何其他ISP身上時，請參閱下列指示。

## 更新流程

您將需要在隔離表上執行查詢，以篩選出所有可能受到中斷影響的Gmail （或其他ISP）收件者，以便將其從隔離清單中移除，並包含在將來的Campaign電子郵件傳送中。

根據事件的時間範圍，以下是此查詢的建議准則。

>[!IMPORTANT]
>
>這些日期/時間以東部標準時區(EST)為基礎。 請根據您執行個體的時區進行調整。

對於含有SMTP退回回應資訊的Campaign執行個體， **[!UICONTROL Error text]** 隔離清單的欄位：

* **錯誤文字（隔離文字）** 包含「550-5.1.1您嘗試存取的電子郵件帳戶不存在」且 **錯誤文字（隔離文字）** 包含「support.google.com」**
* **更新狀態(@lastModified)** 2020年12月14日或之後6:55:上午0
* **更新狀態(@lastModified)** 2020年12月16日或之前6:00:上午0

取得受影響的收件者清單後，您就可以將清單設定為 **[!UICONTROL Valid]** 因此它們會由從隔離清單中移除 **[!UICONTROL Database cleanup]** 工作流程，或從表格中刪除這些專案。

**相關主題：**
* [瞭解傳遞失敗](../../sending/using/understanding-delivery-failures.md)
* [退回郵件資格](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
