---
title: 指標計算
description: 使用每個量度的公式清單瞭解報表的結果。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 1%

---

# 指標計算{#indicator-calculation}

>[!NOTE]
>
>為了更好地處理和管理高容量和即時分析，動態報告使用近似彙總來得出不同的計數預估。 近似彙總提供有限的記憶體使用量，通常比精確計算更快。

下表提供不同報表中使用的指標清單，及其計算公式（視傳遞型別而定）。

## 電子郵件傳遞 {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>標籤</strong> <br /> </th> 
   <th> <strong>欄位名稱</strong> <br /> </th> 
   <th> <strong>指標計算公式</strong> <br /> </th> 
   <th> <strong>個註解</strong><br /> </th> 
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
   <td> 在封鎖清單<br />上 </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8， @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 封鎖清單速率<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> 費率計算的分母是以「已傳送」計數（已傳遞+退回）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+錯誤<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 退回+錯誤率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1或10或11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> 費率計算的分母僅以傳遞為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 傳遞率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> 費率計算的分母是以「已傳送」計數（已傳遞+退回）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬退信<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2且@failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 硬跳出率<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> 費率計算的分母是以「已傳送」計數（已傳遞+退回）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 無效的網域<br /> </td> 
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
   <td> 映象頁面<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> 費率計算的分母僅以傳遞為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 映象頁面速率<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 未連線<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2，3,6，10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 開啟率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> 費率計算的分母僅以傳遞為基礎。<br /> </td> 
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
   <td> 費率計算的分母是以「已傳送」計數（已傳遞+退回）為基礎。<br /> </td> 
  </tr>
  <tr> 
   <td> 已拒絕<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20， @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 拒絕率<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> 費率計算的分母是以「已傳送」計數（已傳遞+退回）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/傳送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 軟退信<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 軟跳出率<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> 費率計算的分母是以「已傳送」計數（已傳遞+退回）為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 不重複點按次數是使用ThetaSketch概念計算的。 如需詳細資訊，請參閱此<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html?lang=zh-Hant#unique-open-clicks-no-match">範例</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 唯一(@trackingUrlType=1,2，3,6，10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 無法連線<br /> </td> 
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
   <td> 費率計算的分母僅以傳遞為基礎。<br /> </td> 
  </tr> 
  <tr> 
   <td> 使用者不明<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## 推播通知傳遞 {#push-notification-delivery}

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
   <td> 已處理/傳送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 傳遞率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 退回+錯誤率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 不重複開啟的計算方式是使用不重複RecipientId的ThetaSketch概念。 如需詳細資訊，請參閱此<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html?lang=zh-Hant#unique-open-clicks-no-match">範例</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 曝光次數<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複曝光次數<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複點按<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 不重複點按次數是使用ThetaSketch概念計算的。 如需詳細資訊，請參閱此<a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html?lang=zh-Hant#unique-open-clicks-no-match">範例</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> 點進率<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 應用程式內傳遞 {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>標籤</strong> <br /> </th> 
   <th> <strong>欄位名稱</strong> <br /> </th> 
   <th> <strong>指標計算公式</strong> <br /> </th> 
   <th> <strong>個註解</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已處理/傳送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivered<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
   <td> delivered=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> 曝光次數<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view)或@count（status=button 1按一下+按鈕2按一下+解除）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 不重複曝光次數<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> 針對<span class="uicontrol">根據促銷活動設定檔(inAppProfile)</span>範本鎖定使用者，使用者=收件者ID。<br />對於<span class="uicontrol">，根據行動設定檔(inAppBroadcast)定位行動應用程式的所有使用者</span>和<span class="uicontrol">根據行動設定檔(inApp)定位使用者</span>範本，使用者= MC ID或代表使用者、行動應用程式和裝置獨特組合的對等專案。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點按<br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 不重複的應用程式內點按<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=clicks))<br /> </td> 
   <td> 針對<span class="uicontrol">根據促銷活動設定檔(inAppProfile)</span>範本鎖定使用者，使用者=收件者ID。<br />對於<span class="uicontrol">，根據行動設定檔(inAppBroadcast)定位行動應用程式的所有使用者</span>和<span class="uicontrol">根據行動設定檔(inApp)定位使用者</span>範本，使用者= MC ID或代表使用者、行動應用程式和裝置獨特組合的對等專案。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內點進率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> 按下Button 1或Button 2的總次數/曝光總數*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解除<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 不重複應用程式內解除服務<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> 針對<span class="uicontrol">根據促銷活動設定檔(inAppProfile)</span>範本鎖定使用者，使用者=收件者ID。<br />對於<span class="uicontrol">，根據行動設定檔(inAppBroadcast)定位行動應用程式的所有使用者</span>和<span class="uicontrol">根據行動設定檔(inApp)定位使用者</span>範本，使用者= MC ID或代表使用者、行動應用程式和裝置獨特組合的對等專案。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解僱率<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> 關閉總數/曝光總數*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
