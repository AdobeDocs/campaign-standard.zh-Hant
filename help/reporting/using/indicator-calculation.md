---
title: 指標計算
description: 使用每個度量公式的清單瞭解報告的結果。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 7%

---

# 指標計算{#indicator-calculation}

>[!NOTE]
>
>為了更好地處理和管理高卷和即時分析，動態報告使用近似聚合來進行不同的計數估計。 近似聚合提供有界的記憶體使用，並且通常比精確計算快。

下表根據交貨類型為您提供了不同報表中使用的指標清單及其計算公式。

## 電子郵件傳遞 {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>標籤</strong> <br /> </th> 
   <th> <strong>欄位名稱</strong> <br /> </th> 
   <th> <strong>指標計算公式</strong> <br /> </th> 
   <th> <strong>評論</strong><br /> </th> 
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
   <td> 登錄<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 登錄率<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> 速率計算的分母基於「已發送」計數（「已交付」+「邊界」）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 邊界+錯誤<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 彈出+錯誤率<br /> </td> 
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
   <td> 費率計算的分母基於「僅交付」。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 交貨率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> 速率計算的分母基於「已發送」計數（「已交付」+「邊界」）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 硬退件<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2和@failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 硬邊界率<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> 速率計算的分母基於「已發送」計數（「已交付」+「邊界」）。<br /> </td> 
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
   <td> 計數(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁面<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> 費率計算的分母基於「僅交付」。<br /> </td> 
  </tr> 
  <tr> 
   <td> 鏡像頁速率<br /> </td> 
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
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11)- unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 開啟率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> 費率計算的分母基於「僅交付」。<br /> </td> 
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
   <td> 速率計算的分母基於「已發送」計數（「已交付」+「邊界」）。<br /> </td> 
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
   <td> 速率計算的分母基於「已發送」計數（「已交付」+「邊界」）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 已處理/已發送<br /> </td> 
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
   <td> 軟彈跳率<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> 速率計算的分母基於「已發送」計數（「已交付」+「邊界」）。<br /> </td> 
  </tr> 
  <tr> 
   <td> 按一下<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 使用ThetaSketch概念計算唯一按一下。 有關此的詳細資訊，請參閱此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>。<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟次數<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 唯一(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 無法聯繫 <br /> </td> 
   <td> @unreachable<br /> </td> 
   <td> 計數(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> 計數(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 取消訂閱率<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> 費率計算的分母基於「僅交付」。<br /> </td> 
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
   <td> 已處理/已發送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count（狀態=發送）<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count（狀態=已交付）<br /> </td> 
  </tr> 
  <tr> 
   <td> 交貨率<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 彈出+錯誤率<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟<br /> </td> 
   <td> @開啟次數<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> 開啟率<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> 不重複開啟次數<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> 使用唯一RecipientId的ThetaSketch概念計算唯一開啟。 有關此的詳細資訊，請參閱此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>。<br /> </td> 
  </tr> 
  <tr> 
   <td> 印象<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count（狀態=已交付）<br /> </td> 
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
   <td> 按一下<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> 使用ThetaSketch概念計算唯一按一下。 有關此的詳細資訊，請參閱此 <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">示例</a>。<br /> </td> 
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
   <th> <strong>評論</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 已處理/已發送<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count（狀態=發送）<br /> </td> 
   <td> 發送=已送達<br /> </td> 
  </tr> 
  <tr> 
   <td> 已傳遞<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count（狀態=已交付）<br /> </td> 
   <td> 已送達=已發送<br /> </td> 
  </tr> 
  <tr> 
   <td> 印象<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view)或@count（status=button 1按一下+按鈕2按一下+解除）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 獨特印象<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> 對於 <span class="uicontrol">根據其市場活動配置檔案(inAppProfile)目標用戶</span> 模板，用戶=收件人ID。<br /> 對於 <span class="uicontrol">針對移動應用(inAppBroadcast)的所有用戶</span> 和 <span class="uicontrol">根據其Mobile配置檔案(inApp)確定目標用戶</span> 模板， user =表示用戶、移動應用和設備的唯一組合的MC Id或等效項。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內按一下 <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count（狀態=按一下）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 應用內唯一按一下<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count（狀態=按一下）)<br /> </td> 
   <td> 對於 <span class="uicontrol">根據其市場活動配置檔案(inAppProfile)目標用戶</span> 模板，用戶=收件人ID。<br /> 對於 <span class="uicontrol">針對移動應用(inAppBroadcast)的所有用戶</span> 和 <span class="uicontrol">根據其Mobile配置檔案(inApp)確定目標用戶</span> 模板， user =表示用戶、移動應用和設備的唯一組合的MC Id或等效項。<br /> </td> 
  </tr> 
  <tr> 
   <td> In-App按一下率<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> 按鈕1或按鈕2的總點擊量/總印數*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 應用內解除<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count（狀態=關閉）<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> 應用程式中的唯一解雇<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count（狀態=關閉）<br /> </td> 
   <td> 對於 <span class="uicontrol">根據其市場活動配置檔案(inAppProfile)目標用戶</span> 模板，用戶=收件人ID。<br /> 對於 <span class="uicontrol">針對移動應用(inAppBroadcast)的所有用戶</span> 和 <span class="uicontrol">根據其Mobile配置檔案(inApp)確定目標用戶</span> 模板， user =表示用戶、移動應用和設備的唯一組合的MC Id或等效項。<br /> </td> 
  </tr> 
  <tr> 
   <td> 應用程式內解雇率<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> 總結/總印象* 100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
