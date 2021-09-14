---
title: 訊息儀表板
description: 探索訊息控制面板的組成，包括動作列和各種功能區塊。
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

訊息控制面板是由不同圖示（重新分組為動作列）和各種功能區塊組成的工作區，可讓您建立訊息的參數並加以傳送。 以下將介紹這些要素。

![](assets/delivery_dashboard_2.png)

## 灰條 {#gray-bar}

灰色列會重新分組連結至訊息的各種圖示。

* **[!UICONTROL Summary]**:顯示/隱藏有關訊息的主要資訊。
* **[!UICONTROL Edit properties]**:可讓您編輯訊息的進 [階參數](../../administration/using/configuring-email-channel.md#list-of-email-properties)。
* **[!UICONTROL Reports]**:可讓您存取與訊息相關的報表。

**相關主題：**

* [設定頻道](../../administration/using/about-channel-configuration.md)
* [存取報表](../../reporting/using/about-dynamic-reports.md)

## 動作列 {#action-bar}

動作列有不同的圖示，可讓您與訊息互動。

![](assets/delivery_dashboard_4.png)

視已設定的參數和進行的進度而定，某些圖示可能無法使用。

* **[!UICONTROL Show proofs]**:顯示/隱藏已傳送的校樣清單（如果存在）。只有在您傳送校樣後，才會啟用此按鈕。

   如需校樣的詳細資訊，請參閱[傳送校樣](../../sending/using/sending-proofs.md)。

* **[!UICONTROL Send a test]**:可讓您選取要使用的核准模式： **[!UICONTROL Email rendering]** （僅限電子郵件）或 **[!UICONTROL Proof]** 兩者皆有。如需測試設定檔的詳細資訊，請參閱[傳送校樣](../../sending/using/sending-proofs.md)。 只有在您建立測試設定檔後，才會啟用此按鈕。

* **[!UICONTROL Prepare send]**:開始準備傳送。出現&#x200B;**[!UICONTROL Deployment]**&#x200B;區塊並顯示準備結果。 只有在輸入目標後，才會顯示此按鈕。 您可以隨時使用對應的按鈕停止準備。 如需訊息準備的詳細資訊，請參閱[準備傳送](../../sending/using/preparing-the-send.md)。

* **[!UICONTROL Confirm send]**:確認傳送訊息。發送統計資訊將出現在&#x200B;**[!UICONTROL Deployment]**&#x200B;塊中。 此按鈕僅在準備好傳送後才會顯示。 您可以隨時使用&#x200B;**Stop send**&#x200B;和&#x200B;**[!UICONTROL Pause]**&#x200B;按鈕來停止或暫停傳送。 如需確認傳送的詳細資訊，請參閱[傳送訊息](../../sending/using/confirming-the-send.md)。

## 區塊 {#blocks}

主螢幕由不同的區塊組成。 按一下區塊內部以存取對應的參數畫面：

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:可讓您追蹤訊息準備或傳送的進度。按一下此區塊右下角的按鈕，以存取傳送和分析記錄檔。 只有在準備好傳送後，才會顯示此區塊。 有關詳細資訊。 請參閱[確認傳送](../../sending/using/confirming-the-send.md)。
* **[!UICONTROL Audience]**:可讓您建立訊息的主要目標以及測試設定檔。請參閱[建立對象](../../audiences/using/creating-audiences.md)。
* **[!UICONTROL Schedule]**:可讓您指定傳送訊息的日期。請參閱[排程](../../sending/using/about-scheduling-messages.md)。
* **[!UICONTROL Content]**:可讓您定義訊息的內容並加以預覽。請參閱[傳送訊息的關鍵步驟](../../channels/using/key-steps-to-send-a-message.md)。

## 警告 {#warnings}

在某些情況下，訊息控制面板頂端的黃色橫幅中可能會出現警告。

![](assets/delivery_dashboard_warnings.png)

以下是可顯示的訊息清單：

* *「已為此電子郵件啟用SMTP測試模式選項：不會傳送任何訊息。」*

   如需詳細資訊，請參閱[本節](../../administration/using/configuring-email-channel.md#smtp-test-mode)。

* *&quot;已禁用路由外部帳戶。&quot;*

   有關詳細資訊，請參閱[外部帳戶](../../administration/using/external-accounts.md)。

* *&quot;無法傳送訊息，因為目前的IP相關性未由任何傳送程式處理。&quot;*

   如果您看到此訊息，在IP相關性定義層級或傳送程式層級會發生問題。 請連絡您的Adobe管理員。

* *「這是現成可用的交易式訊息範本。如果要修改它，必須複製它並處理副本。&quot;*

   其中有些現成可用的交易式訊息範本是內建的登錄頁面範本。 如需詳細資訊，請參閱[本節](../../channels/using/landing-page-templates.md)。

* *「此訊息是技術交易式訊息範本。您無法修改或發佈它。&quot;*

   此警告會顯示在無法編輯的空白交易式訊息範本中。 如需交易式訊息的詳細資訊，請參閱[此區段](../../channels/using/getting-started-with-transactional-msg.md)。
