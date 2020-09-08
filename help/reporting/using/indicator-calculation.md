---
title: 指示器計算
description: 透過每個量度公式的清單，瞭解報表的結果。
page-status-flag: never-activated
uuid: dfbc9d7e-62db-4e77-bb8e-0ac826ec7333
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 45b11631-6b32-4074-8c8d-affd06407810
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 2%

---


# 指示器計算{#indicator-calculation}

>[!NOTE]
>
>為了更好地處理及管理大量資料和即時分析，動態報告會使用概略匯整來進行不同的計數估計。 近似聚合提供有界的記憶體使用，而且通常比精確計算更快。

下表提供不同報表中使用的指標清單及其計算公式，視傳送類型而定。

## 電子郵件傳送 {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>標籤</strong> <br /> </th> 
   <th> <strong>欄位名稱</strong> <br /> </th> 
   <th> <strong>指標計算公式</strong> <br /> </th> 
   <th> <strong>注釋</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 帳戶已停用<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 拒絕列出<br /> </td> 
   <td> @黑名單<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 登記率<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> 比率計算的分母是以「已傳送」計數（「已傳送」+「彈回數」）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 彈回數+錯誤<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 反彈+錯誤率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count（@trackingUrlType=1或10或11）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delived<br /> </td> 
   <td> 比率計算的分母僅基於「已傳送」。<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> 比率計算的分母是以「已傳送」計數（「已傳送」+「彈回數」）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬彈回數<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 硬彈回數率<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> 比率計算的分母是以「已傳送」計數（「已傳送」+「彈回數」）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 無效的域<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 郵箱已滿<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> 比率計算的分母僅基於「已傳送」。<br /> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁面速率<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 未連接<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11)- unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 開放率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> 比率計算的分母僅基於「已傳送」。<br /> </td> 
  </tr> 
  <tr> 
   <td> 隔離<br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 隔離率<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantine/@sent<br /> </td> 
   <td> 比率計算的分母是以「已傳送」計數（「已傳送」+「彈回數」）為基礎。<br /> </td> 
  </tr>
  <tr> 
   <td> 已拒絕<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 拒絕率<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> 比率計算的分母是以「已傳送」計數（「已傳送」+「彈回數」）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理／已傳送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 軟彈跳<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 軟反彈率<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> 比率計算的分母是以「已傳送」計數（「已傳送」+「彈回數」）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特點按<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 獨特點按次數是使用ThetaSketch概念計算的。 For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 唯一開啟<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 無法訪問 <br /> </td> 
   <td> @unreachable<br /> </td> 
   <td> count(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱率<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> 比率計算的分母僅基於「已傳送」。<br /> </td> 
  </tr> 
  <tr> 
   <td> 用戶未知<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## 推播通知傳送 {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>標籤</strong> <br /> </th> 
   <th> <strong>欄位名稱</strong> <br /> </th> 
   <th> <strong>指標計算公式</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已處理／已傳送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 反彈+錯誤率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> 開放率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 唯一開啟<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 唯一開啟是使用唯一RecipientId的ThetaSketch概念計算。 For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 印象<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特印象<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> 獨特點按<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 獨特點按次數是使用ThetaSketch概念計算的。 For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 應用程式內傳送 {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>標籤</strong> <br /> </th> 
   <th> <strong>欄位名稱</strong> <br /> </th> 
   <th> <strong>指標計算公式</strong> <br /> </th> 
   <th> <strong>注釋</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已處理／已傳送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivered<br /> </td> 
  </tr> 
  <tr> 
   <td> 交付<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delived)<br /> </td> 
   <td> delivered=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> 印象<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view)或@count（status=button 1按一下+按鈕2按一下+免除）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 獨特印象<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> 針對 <span class="uicontrol">根據其促銷活動設定檔(inAppProfile)範本的Target使用者</span> ，使用者=收件者Id。<br /> 針對 <span class="uicontrol">Target行動應用程式(inAppBroadcast)</span> 和 <span class="uicontrol"></span> Target使用者根據其行動設定檔(inApp)範本的所有使用者，使用者= MC Id或相當等級，代表使用者、行動應用程式和裝置的獨特組合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點按次數 <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count(status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 獨特的應用程式內點按次數<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count(status=clicks))<br /> </td> 
   <td> 針對 <span class="uicontrol">根據其促銷活動設定檔(inAppProfile)範本的Target使用者</span> ，使用者=收件者Id。<br /> 針對 <span class="uicontrol">Target行動應用程式(inAppBroadcast)</span> 和 <span class="uicontrol"></span> Target使用者根據其行動設定檔(inApp)範本的所有使用者，使用者= MC Id或相當等級，代表使用者、行動應用程式和裝置的獨特組合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點進率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> 按鈕1或按鈕2的點按總次數／印象總數*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解雇<br /> </td> 
   <td> @compicent<br /> </td> 
   <td> @count(status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 獨特的應用程式內解雇<br /> </td> 
   <td> @uniquecciption<br /> </td> 
   <td> @unique(@count(status=close))<br /> </td> 
   <td> 針對 <span class="uicontrol">根據其促銷活動設定檔(inAppProfile)範本的Target使用者</span> ，使用者=收件者Id。<br /> 針對 <span class="uicontrol">Target行動應用程式(inAppBroadcast)</span> 和 <span class="uicontrol"></span> Target使用者根據其行動設定檔(inApp)範本的所有使用者，使用者= MC Id或相當等級，代表使用者、行動應用程式和裝置的獨特組合。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解雇率<br /> </td> 
   <td> @unitsalrate<br /> </td> 
   <td> 關閉總次數／曝光總次數*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

