---
title: Campaign Standard Mobile指南
description: 進一步瞭解Adobe Campaign Standard中行動傳送的一般准則，例如如何設定行動應用程式或建立推播通知和應用程式內訊息。
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
source-git-commit: afb988281f00dc17b484872259d44f51864d55f1
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 22%

---

# 開始使用行動頻道 {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>瞭解如何設定推播通知的行動應用程式</br><a href="#configuration-push">按一下這裡</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>瞭解如何設定行動應用程式的應用程式內訊息</br><a href="#configuring-mobile-app">按一下這裡</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>進一步瞭解如何建立推播通知</br><a href="#create-push">按一下這裡</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>瞭解如何建立應用程式內訊息</br><a href="#create-inapp">按一下這裡</a></p></td></tr>
</table>

## 關於行動傳送 {#about-mobile}

Adobe Campaign可讓您在不同通道上建立和傳送個人化訊息，並透過專用報告衡量其成效。

有了Adobe Campaign Standard，您可以透過三個不同通道傳送行動傳遞：

* SMS，顯示在「關於SMS訊息」區段。
* 推播通知，顯示在關於推播通知區段。
* 應用程式內訊息，顯示在關於應用程式內訊息區段。

## 設定推播通知的行動應用程式 {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>使用Adobe Experience Platform SDK設定行動應用程式</strong></p>
    </div>
    <p>若要傳送應用程式內訊息和推播通知，您必須運用Adobe Experience Platform SDK，在Adobe Campaign中設定您的行動應用程式。</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>瞭解Campaign Standard推播通知裝載結構</strong></p>
    </div>
    <p>進一步瞭解當推播通知成功從Adobe Campaign Standard傳送至應用程式時，行動應用程式中接收的裝載結構。</br><a href="../../administration/using/push-payload.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>實施本機通知追蹤</strong></p>
    </div>
    <p>在此處瞭解如何確保本機通知追蹤已正確實作。 </br><a href="../../administration/using/local-tracking.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>實施推播追蹤</strong></p>
    </div>
    <p>瞭解如何確保在iOS和Android上正確實作推播通知追蹤。</br><a href="../../administration/using/push-tracking.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
</table>

## 設定應用程式內訊息的行動應用程式 {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>使用Adobe Experience Platform SDK設定行動應用程式</strong></p>
    </div>
    <p>若要傳送應用程式內訊息和推播通知，您必須運用Adobe Experience Platform SDK，在Adobe Campaign中設定您的行動應用程式。</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>使用Adobe Experience Platform SDK支援的行動使用案例</strong></p>
    </div>
    <p>深入瞭解Adobe Campaign Standard支援的行動使用案例，透過使用Adobe Experience Platform SDK。</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>設定標籤規則以支援 Adobe Campaign Standard 使用案例</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>按一下這裡</strong></a>，開始在資料收集UI中建立資料元素和規則，以便將PII和其他資料從行動應用程式傳送至Adobe Campaign Standard。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>實施本機通知追蹤</strong></p>
    </div>
    <p>在此處瞭解如何確保本機通知追蹤已正確實作。 </br><a href="../../administration/using/local-tracking.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
</table>

## 建立推播通知 {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>準備和傳送推送通知</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>在這裡瞭解</strong></a>如何準備推播通知，以及如何傳送給您的目標對象。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自訂推送通知</strong></p>
    </div>
    <p>為了微調您的傳送，Adobe Campaign可讓您在設計推播通知時存取一組選項。</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>建立多語言推送通知</strong></p>
    </div>
    <p>根據使用者偏好的語言和區域來傳送訊息，以個人化推播通知內容。</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>從Adobe Campaign Standard推播通知顯示影像</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>在這裡瞭解</strong></a>如何在iOS裝置上顯示Adobe Campaign推播通知的影像。</p>
    <br>
  </td>
</tr>
</table>

## 建立應用程式內訊息 {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>準備和傳送應用程式內訊息</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>在這裡瞭解</strong></a>如何準備您的應用程式內訊息，然後如何將其傳送給您的目標對象。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自訂您的應用程式內訊息</strong></p>
    </div>
    <p>為了微調您的傳送，Adobe Campaign可讓您在設計應用程式內時，存取一組進階選項。</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>自訂本機通知訊息型別</strong></p>
    </div>
    <p>本機通知只能由應用程式在特定時間內觸發，且會視事件而定。</br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>應用程式內報告</strong></p>
    </div>
    <p>應用程式內報表提供與應用程式內傳遞相關的詳細資訊。</br><a href="../../reporting/using/in-app-report.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
</table>

## 建立簡訊訊息 {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>建立簡訊訊息</strong></p>
    </div>
    <p>建立簡訊傳送與建立一般電子郵件非常類似。</br>步驟<a href="../../channels/using/creating-an-sms-message.md"><strong>在此詳細說明</strong></a>說明此管道的特定設定。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>自訂簡訊
</strong></p>
    </div>
    <p>為了微調您的傳送，Adobe Campaign可讓您在設計SMS訊息時存取一組進階選項。</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>按一下這裡以取得詳細資訊。</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>管理傳入的簡訊</strong></p>
    </div>
    <p>當設定檔回覆透過Campaign傳送的SMS訊息時，您可以設定自動傳回給他們的訊息，以及要執行的動作。自訂本機通知訊息型別</br><a href="../../channels/using/managing-incoming-sms.md"><strong>按一下這裡以取得詳細資訊。</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>簡訊報告</strong></p>
    </div>
    <p>SMS報表提供SMS傳送的詳細資訊，例如傳送率和跳出率。</br><a href="../../reporting/using/sms-report.md"><strong>按一下這裡</strong></a>以獲得更多資訊。</p>
    <br>
  </td>
</tr>
</table>

## 行動裝置疑難排解 {#mobile-troubleshooting}

下列頁面將協助您解決在Adobe Campaign Standard中使用行動傳送時最常見的問題。

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>推播通知常見問題集</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>如需詳細資訊，請按一下此處。</p>
  </td>
  <td>
    <div>
    <p><strong>Adobe Launch Synchronization 常見問答集</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>如需詳細資訊，請按一下此處。</p>
  </td>
  <td>
    <div>
    <p><strong>應用程式內常見問題集</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>如需詳細資訊，請按一下此處。</p>
  </td>
</tr>
</table>
