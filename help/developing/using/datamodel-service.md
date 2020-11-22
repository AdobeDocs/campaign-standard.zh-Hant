---
solution: Campaign Standard
product: campaign
title: DataModel
description: 瞭解資料模型
audience: developing
content-type: reference
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 5%

---


# 服務(nms:service)

## 物件說明

<table>
               <tr>
                  <th>名稱</th>
                  <th>標籤</th>
                  <th>類型（長度）</th>
                  <th>枚舉值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主要資源ID</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>內建應用程式物件</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>已建立</td>
                  <td>已建立</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy(userBase)</td>
                  <td>建立者</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusPrice</td>
                  <td>價格</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>說明</td>
                  <td>字串(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>end</td>
                  <td>結束日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit(geoUnitBase)</td>
                  <td>地理單位</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>歷史</td>
                  <td>訂閱歷史記錄</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部資源</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>範本</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>標籤</td>
                  <td>標籤</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>上次修改日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>limitedDuration</td>
                  <td>有限期</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日期</td>
                  <td>日期(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>通道</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>行動(SMS)- sms - 1</li>
                        <li>電子郵件——電子郵件- 0</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模式</td>
                  <td>模式</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>病毒式營銷- 1</li>
                        <li>電子報——電子報- 0</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy(userBase)</td>
                  <td>修改者</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>名稱</td>
                  <td>ID</td>
                  <td>字串(64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit(orgUnitBase)</td>
                  <td>組織單位</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>服務標籤</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>開始日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage(landingPageSubscriptionBase)</td>
                  <td>訂閱登陸頁面</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario(deliveryMCTemplateBase)</td>
                  <td>訂閱確認</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>訂閱</td>
                  <td>訂閱</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetResource</td>
                  <td>定位維度</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>範本（服務）</td>
                  <td>服務模板</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>縮圖</td>
                  <td>縮圖</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>標題</td>
                  <td>服務</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nimsLandingPage(landingPageUnsubscriptionBase)</td>
                  <td>取消訂閱登陸頁面</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nimsScenario(deliveryMCTemplateBase)</td>
                  <td>取消訂閱確認</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minsumScenarioEventType</td>
                  <td>NimmessScenarioEventType</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>有效期</td>
                  <td>數字 </td>
                  <td> </td>
               </tr>
            </table>

## 濾鏡

在指定時段內可用（由Planning提供）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日期</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>日期</td>
    </tr>
</table>

依頻道類型（依頻道）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>頻道</td>
<td>枚舉</td>
</tr>
</table>

依名稱或標籤（依Text）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>文字</td>
<td>字串</td>
</tr>
</table>

透過定位資源(byTargetResource)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>targetResource</td>
<td>字串</td>
</tr>
</table>