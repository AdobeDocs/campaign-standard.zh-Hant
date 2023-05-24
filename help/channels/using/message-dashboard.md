---
title: 訊息儀表板
description: 瞭解消息儀表板由什麼組成，包括操作欄和各種功能塊。
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Overview
role: User
level: Beginner
exl-id: 886aae39-2029-471c-b4d1-c6ca57d0e568
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---

# 訊息儀表板{#message-dashboard}

消息儀表板是由不同表徵圖（重新分組到操作欄）和各種功能塊組成的工作區，這些功能塊允許您建立消息的參數併發送消息。 這些要素在下文中介紹。

![](assets/delivery_dashboard_2.png)

## 灰條 {#gray-bar}

灰色欄重組連結到消息的各種表徵圖。

* **[!UICONTROL Summary]**:顯示/隱藏有關消息的主要資訊。
* **[!UICONTROL Edit properties]**:允許您編輯郵件 [高級參數](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**:允許您訪問與消息相關的報告。

**相關主題：**

* [設定頻道](../../administration/using/about-channel-configuration.md)
* [訪問報告](../../reporting/using/about-dynamic-reports.md)

## 動作列 {#action-bar}

操作欄具有不同的表徵圖，允許您與消息交互。

![](assets/delivery_dashboard_4.png)

根據已設定的參數和已完成的進度，某些表徵圖可能不可用。

* **[!UICONTROL Show proofs]**:顯示/隱藏已發送的校樣清單（如果存在）。 僅當您發送校樣後，才啟用此按鈕。

   有關校樣的詳細資訊，請參見 [發送校樣](../../sending/using/sending-proofs.md)。

* **[!UICONTROL Send a test]**:允許您選擇要使用的審批模式： **[!UICONTROL Email rendering]** （僅限電子郵件）, **[!UICONTROL Proof]** 或兩者兼有。 有關test配置檔案的詳細資訊，請參閱 [發送校樣](../../sending/using/sending-proofs.md)。 只有建立test配置檔案後，才啟用此按鈕。

* **[!UICONTROL Prepare send]**:開始準備發送。 的 **[!UICONTROL Deployment]** 塊出現並顯示準備結果。 只有輸入目標後，此按鈕才顯示。 您可以隨時使用相應的按鈕停止準備。 有關消息準備的詳細資訊，請參閱 [準備發送](../../sending/using/preparing-the-send.md)。

* **[!UICONTROL Confirm send]**:確認發送消息。 發送統計資訊顯示在 **[!UICONTROL Deployment]** 框。 此按鈕僅在準備發送後顯示。 您可以使用 **停止發送** 和 **[!UICONTROL Pause]** 按鈕。 有關確認發送的詳細資訊，請參閱 [發送消息](../../sending/using/confirming-the-send.md)。

## 塊 {#blocks}

主螢幕由不同的塊組成。 在塊內按一下以訪問相應的參數螢幕：

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:允許您跟蹤消息準備或發送的進度。 按一下此塊右下部分中找到的按鈕以訪問發送和分析日誌。 此塊僅在準備發送後出現。 更多關於這個的。 請參閱 [確認發送](../../sending/using/confirming-the-send.md)。
* **[!UICONTROL Audience]**:允許您建立消息的主要目標以及test配置檔案。 請參閱[建立對象](../../audiences/using/creating-audiences.md)。
* **[!UICONTROL Schedule]**:允許您指定消息的發送日期。 請參閱 [計畫](../../sending/using/about-scheduling-messages.md)。
* **[!UICONTROL Content]**:允許您定義郵件的內容並預覽它。 請參閱 [發送消息的關鍵步驟](../../channels/using/key-steps-to-send-a-message.md)。

## 警告 {#warnings}

在某些情況下，消息儀表板頂部的黃色橫幅中可能會出現警告。

![](assets/delivery_dashboard_warnings.png)

以下是可顯示的消息清單：

* *&quot;已為此電子郵件啟用SMTPtest模式選項：不會發送任何消息。」*

   如需詳細資訊，請參閱[本節](../../administration/using/configuring-email-channel.md#smtp-test-mode)。

* *&quot;已禁用路由外部帳戶。&quot;*

   有關此的詳細資訊，請參閱 [外部帳戶](../../administration/using/external-accounts.md)。

* *&quot;無法發送消息，因為任何發送進程都未處理當前IP關聯。&quot;*

   如果您看到此消息，則在IP關聯定義級別或發送進程級別存在問題。 請與Adobe管理員聯繫。

* *「這是一個現成的事務性消息模板。 如果要修改它，必須複製它並處理副本。」*

   其中一些現成的事務性消息模板是內置登錄頁模板。 如需詳細資訊，請參閱[本節](../../channels/using/landing-page-templates.md)。

* *&quot;此消息是技術事務性消息模板。 您不能修改或發佈它。」*

   此警告顯示在不可編輯的空事務性消息模板中。 有關事務性消息的詳細資訊，請參見 [此部分](../../channels/using/getting-started-with-transactional-msg.md)。
