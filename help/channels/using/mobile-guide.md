---
title: Campaign Standard　行動指南
description: 瞭解有關Adobe Campaign Standard移動交付的一般准則的更多資訊，例如如何配置移動應用程式或建立推送通知和應用內消息。
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 24%

---

# 開始使用行動頻道 {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>瞭解如何配置移動應用程式以進行推送通知 </br><a href="#configuration-push">按一下這裡</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>瞭解如何為In-App消息配置移動應用程式 </br><a href="#configuring-mobile-app">按一下這裡</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>瞭解有關如何建立推送通知的詳細資訊 </br><a href="#create-push">按一下這裡</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>瞭解如何建立In-App消息</br><a href="#create-inapp">按一下這裡</a></p></td></tr>
</table>

## 關於移動交付 {#about-mobile}

Adobe Campaign允許您通過各種渠道建立和發送個性化消息，並通過專用報告衡量其有效性。

使用Adobe Campaign Standard，您可以通過三個不同渠道發送移動交付：

* SMS，在「關於SMS消息」部分中顯示。
* 推送通知，顯示在「關於推送通知」部分。
* In-App消息，顯示在About In-App消息部分。

## 配置移動應用程式以進行推送通知 {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>使用Adobe Experience PlatformSDK配置移動應用程式</strong></p>
    </div>
    <p>要發送In-App消息和推送通知，您的移動應用程式需要利用Adobe Experience PlatformSDK在Adobe Campaign設定。</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>瞭解Campaign Standard推送通知負載結構</strong></p>
    </div>
    <p>瞭解在成功將推送通知發送到來自Adobe Campaign Standard的應用程式時在移動應用程式中接收的負載結構的詳細資訊。</br><a href="../../administration/using/push-payload.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>實施本機通知追蹤</strong></p>
    </div>
    <p>在此處瞭解如何確保正確實施本地通知跟蹤。 </br><a href="../../administration/using/local-tracking.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>實現推式跟蹤</strong></p>
    </div>
    <p>瞭解如何確保推送通知跟蹤已在iOS和Android上正確實施。</br><a href="../../administration/using/push-tracking.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
</table>

## 為In-App消息配置移動應用程式 {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>使用Adobe Experience PlatformSDK配置移動應用程式</strong></p>
    </div>
    <p>要發送In-App消息和推送通知，您的移動應用程式需要利用Adobe Experience PlatformSDK在Adobe Campaign設定。</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>使用Adobe Experience PlatformSDK支援的移動使用案例</strong></p>
    </div>
    <p>瞭解有關使用Adobe Experience PlatformSDK在Adobe Campaign Standard支援的移動使用案例的更多資訊。</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>配置標籤規則以支援Adobe Campaign Standard使用案例</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>按一下這裡</strong></a> 開始在資料收集UI中建立資料元素和規則，以將PII和其他資料從移動應用程式發送到Adobe Campaign Standard。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>實施本機通知追蹤</strong></p>
    </div>
    <p>在此處瞭解如何確保正確實施本地通知跟蹤。 </br><a href="../../administration/using/local-tracking.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
</table>

## 自訂推播通知 {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>準備和傳送推送通知</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>在此處瞭解</strong></a> 如何準備推送通知，以及如何將其發送給目標受眾。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自訂推送通知</strong></p>
    </div>
    <p>為了優化您的交付，Adobe Campaign允許您在設計推送通知時訪問一組選項。</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>建立多語言推送通知</strong></p>
    </div>
    <p>通過根據用戶首選的語言和區域發送消息來個性化推送通知內容。</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>從 Adobe Campaign Standard 推播通知顯示影像</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>在此處瞭解</strong></a> 如何在iOS設備上顯示來自Adobe Campaign推送通知的影像。</p>
    <br>
  </td>
</tr>
</table>

## 建立應用內消息 {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>準備和傳送應用程式內訊息</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>在此處瞭解</strong></a> 如何準備In-App消息，以及如何將其發送給目標受眾。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自定義應用內消息</strong></p>
    </div>
    <p>為了優化您的交付，Adobe Campaign允許您在設計In-App時訪問一組高級選項。</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>自訂本機通知訊息類型</strong></p>
    </div>
    <p>本機通知只能由應用程式在特定時間內觸發，且會視事件而定。</br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>應用程式內報告</strong></p>
    </div>
    <p>In-App報告提供了與In-App交付相關的詳細資訊。</br><a href="../../reporting/using/in-app-report.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
</table>

## 建立SMS消息 {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>建立簡訊訊息</strong></p>
    </div>
    <p>建立簡訊傳送與建立一般電子郵件非常類似。</br>步驟 <a href="../../channels/using/creating-an-sms-message.md"><strong>詳細</strong></a> 描述特定於此通道的配置。</br></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自定義SMS消息
</strong></p>
    </div>
    <p>為了優化您的傳送，Adobe Campaign允許您在設計簡訊時訪問一組高級選項。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>按一下這裡以獲得更多資訊。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong></p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>管理傳入的簡訊</strong></p>
    </div>
    <p>當配置檔案答復通過市場活動發送的SMS消息時，您可以配置自動發回給它們的消息以及要執行的操作。自定義本地通知消息類型</br><a href="../../channels/using/managing-incoming-sms.md"><strong>按一下這裡瞭解詳細資訊。</br><a href="../../channels/using/managing-incoming-sms.md"><strong></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>簡訊報告</strong></p>
    </div>
    <p>SMS報告提供有關SMS交付的詳細資訊，如交付和彈跳率。</br><a href="../../reporting/using/sms-report.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
</table>

## 移動故障排除 {#mobile-troubleshooting}

以下頁面將幫助您解決在Adobe Campaign Classic使用移動交付時遇到的最常見問題。

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>推送通知常見問題</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>按一下這裡以獲得更多資訊。</p>
  </td>
  <td>
    <div>
    <p><strong>Adobe Launch Synchronization 常見問答集</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>按一下這裡以獲得更多資訊。</p>
  </td>
  <td>
    <div>
    <p><strong>應用程式內常見問題集</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>按一下這裡以獲得更多資訊。</p>
  </td>
</tr>
</table>
