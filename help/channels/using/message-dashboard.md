---
title: 訊息儀表板
description: 探索訊息控制面板的組成部分，包括動作列和各種功能區塊。
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

訊息控制面板是由不同圖示（重新分組為動作列）和各種功能區塊組成的工作區，可讓您建立訊息引數並傳送。 這些元素將於下文介紹。

![](assets/delivery_dashboard_2.png)

## 灰色列 {#gray-bar}

灰色列會重新分組連結至訊息的各種圖示。

* **[!UICONTROL Summary]**：顯示/隱藏訊息的主要相關資訊。
* **[!UICONTROL Edit properties]**：可讓您編輯訊息的 [進階引數](../../administration/using/configuring-email-channel.md#list-of-email-properties).
* **[!UICONTROL Reports]**：可讓您存取與訊息相關的報表。

**相關主題：**

* [設定頻道](../../administration/using/about-channel-configuration.md)
* [存取報告](../../reporting/using/about-dynamic-reports.md)

## 動作列 {#action-bar}

動作列有不同的圖示，可讓您與訊息互動。

![](assets/delivery_dashboard_4.png)

根據已設定的引數和進度，某些圖示可能無法使用。

* **[!UICONTROL Show proofs]**：顯示/隱藏已傳送的校樣清單（如果存在）。 只有在您已傳送校樣後，才會啟用此按鈕。

  如需校訂的詳細資訊，請參閱 [傳送校樣](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**：可讓您選取要使用的核准模式： **[!UICONTROL Email rendering]** （僅限電子郵件）， **[!UICONTROL Proof]** 或兩者。 如需測試設定檔的詳細資訊，請參閱 [傳送校樣](../../sending/using/sending-proofs.md). 只有在您已建立測試設定檔後，才會啟用此按鈕。

* **[!UICONTROL Prepare send]**：開始準備傳送。 此 **[!UICONTROL Deployment]** 區塊隨即出現，並顯示準備的結果。 此按鈕只會在輸入目標後顯示。 您可以使用對應的按鈕隨時停止準備。 如需訊息準備的詳細資訊，請參閱 [準備傳送](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**：確認傳送訊息。 傳送的統計資料會顯示在 **[!UICONTROL Deployment]** 區塊。 此按鈕只會在傳送準備就緒後顯示。 您可以使用來隨時停止或暫停傳送 **停止傳送** 和 **[!UICONTROL Pause]** 按鈕。 如需確認傳送的詳細資訊，請參閱 [傳送訊息](../../sending/using/confirming-the-send.md).

## 個區塊 {#blocks}

主畫面由不同區塊組成。 按一下區塊內部以存取對應的引數畫面：

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**：可讓您追蹤訊息準備或傳送的進度。 按一下在此區塊右下角找到的按鈕，以存取傳送和分析記錄。 此區塊只會在傳送準備就緒後顯示。 有關詳細資訊。 另請參閱 [確認傳送](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**：可讓您建立訊息的主要目標以及測試設定檔。 請參閱[建立對象](../../audiences/using/creating-audiences.md)。
* **[!UICONTROL Schedule]**：可讓您指定傳送訊息的日期。 另請參閱 [正在排程](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**：可讓您定義訊息的內容並加以預覽。 另請參閱 [傳送訊息的關鍵步驟](../../channels/using/key-steps-to-send-a-message.md).

## 警告 {#warnings}

在某些情況下，警告可能會顯示在訊息控制面板上方的黃色橫幅中。

![](assets/delivery_dashboard_warnings.png)

以下是可以顯示的訊息清單：

* *「此電子郵件已啟用SMTP測試模式選項：不會傳送任何郵件。」*

  如需詳細資訊，請參閱[本節](../../administration/using/configuring-email-channel.md#smtp-test-mode)。

* *「路由外部帳戶已停用。」*

  有關詳細資訊，請參閱 [外部帳戶](../../administration/using/external-accounts.md).

* *「無法傳送訊息，因為任何傳送程式都不會處理目前的IP相似性。」*

  如果您看到此訊息，則表示IP相似性定義層級或傳送程式層級有問題。 請連絡您的Adobe管理員。

* *「這是立即可用的交易式訊息範本。 如果要修改它，您必須複製它並製作副本。」*

  這些立即可用的交易式訊息範本中，有些是內建登入頁面範本。 如需詳細資訊，請參閱[本節](../../channels/using/landing-page-templates.md)。

* *「此訊息為技術交易式訊息範本。 您無法修改或發佈。」*

  此警告會顯示在無法編輯的空白交易式訊息範本中。 如需異動訊息的詳細資訊，請參閱 [本節](../../channels/using/getting-started-with-transactional-msg.md).
