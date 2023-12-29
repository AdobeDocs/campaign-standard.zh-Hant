---
title: 稽核軌跡
description: 使用Campaign稽核軌跡監視動作和事件
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: bda6f8d5-3bcf-498c-a7c4-d3c2c79b9510
source-git-commit: 64da7ac09e1b0fbf13ba1e563b6dc7be995b1640
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 3%

---

# 稽核軌跡 {#audit}

此 **[!UICONTROL Audit trail]** 可讓您存取執行個體中所做變更的完整歷史記錄。

**[!UICONTROL Audit trail]** 即時擷取在Adobe Campaign Standard例項中發生之動作和事件的完整清單。 功能包括自助式存取歷史資料記錄，以協助回答下列問題：工作流程狀況、自訂資源與選項、上次更新者或使用者在執行個體中的行為。

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** 包含三個元件：

* **自訂資源稽核軌跡**：檢查活動和上次對自訂資源進行的修改。

  如需詳細資訊，請參閱 **[!UICONTROL Custom resources]**，請參閱此 [頁面](../../developing/using/key-steps-to-add-a-resource.md).

* **工作流程稽核軌跡**：檢查活動和上次對工作流程進行的修改，以及工作流程的狀態，例如：

   * 建立時間
   * 已修改
   * 已刪除
   * 工作流程開始
   * 工作流程暫停
   * 工作流程停止
   * 工作流程重新啟動
   * 工作流程清理
   * 工作流程模擬
   * 工作流程喚醒
   * 工作流程立即停止
   * 相同使用者重新啟動工作流程
   * 工作流程重新啟動不明的命令

  如需詳細資訊，請參閱 **[!UICONTROL Workflows]**，請參閱此 [頁面](../../automating/using/get-started-workflows.md).

* **選項稽核軌跡**：檢查活動和上次修改選項。

  如需詳細資訊，請參閱 **[!UICONTROL Options]**，請參閱此 [頁面](../../administration/using/about-campaign-standard-settings.md).

請注意，保留期間預設為30天。

## 存取稽核軌跡 {#audit-access}

若要存取執行個體的稽核軌跡：

1. 在Adobe Campaign Standard中，從進階功能表選取 **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**.

   ![](assets/audit-trail.png)

1. 此 **[!UICONTROL Audit trail]** 視窗會開啟，其中含有您的實體清單。 Adobe Campaign Standard將稽核工作流程、選項和自訂資源的建立、編輯和刪除動作。

   從 **[!UICONTROL Search]** 選單中，您可以依據以下條件篩選實體：

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**：介於全部、工作流程、自訂資源和選項之間的實體型別。
   * **[!UICONTROL Entity name]**：工作流程、選項或自訂資源的ID

   ![](assets/audit-trail_2.png)

1. 選取其中一個實體以深入瞭解最後的修改。

1. 「稽核實體」視窗會提供所選實體的詳細資訊，例如：

   * **[!UICONTROL Entity]**：工作流程、選項或自訂資源的ID。
   * **[!UICONTROL Action]**：此實體上執行的最後一個動作。
   * **[!UICONTROL Changed by]**：上次修改此實體之人員的使用者名稱。
   * **[!UICONTROL Changed date]**：此實體上個動作執行的日期。
   * **[!UICONTROL Content]**：程式碼區塊，可提供實體中確切變更專案的詳細資訊。

   在此範例中，我們可以看到工作流程WKF110已由此執行個體的企業管理員於8月26日啟動。

   ![](assets/audit-trail_3.png)

## 啟用/停用稽核軌跡 {#enable-disable-audit}

>[!NOTE]
>
> 只有功能管理員可以啟用或停用稽核軌跡。 如需關於此項目的詳細資訊，請參閱此[頁面](../../administration/using/users-management.md#functional-administrators)。

稽核軌跡可以針對特定活動輕鬆啟用或停用。

若要這麼做：

1. 在Adobe Campaign Standard中，從進階功能表選取 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

   ![](assets/audit-trail_4.png)

1. 根據要停用的實體，選取下列選項之一：

   * **[!UICONTROL XtkAudit_Workflows]** 管理工作流程的稽核軌跡選項。
   * **[!UICONTROL XtkAudit_Option]** 用於管理「選項」之「稽核軌跡」的選項。
   * **[!UICONTROL XtkAudit_CusResource]** 用於管理自訂資源之稽核軌跡的選項。
   * **[!UICONTROL XtkAudit_Enable_All]** 用於管理每個實體的稽核軌跡的選項。

     >[!NOTE]
     >
     >如果 **[!UICONTROL XtkAudit_Enable_All]** 選項設為0，則 **[!UICONTROL Audit trail]** 功能將完全停用，無論其他個別選項值為何。

   ![](assets/audit-trail_5.png)

1. 從您的 **[!UICONTROL Options]** 頁面，設定 **[!UICONTROL Value (integer)]** 設為0 (如果您要停用 **[!UICONTROL Audit trail]** 或變成1以啟用它。

   ![](assets/audit-trail_6.png)

1. 按一下&#x200B;**[!UICONTROL Save]**。
