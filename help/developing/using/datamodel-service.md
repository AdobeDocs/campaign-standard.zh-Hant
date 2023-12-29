---
title: DataModel服務
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 35%

---

# 服務(nms：service)

## 物件說明

<table>
               <tr>
                  <th>名稱</th>
                  <th>標籤</th>
                  <th>型別（長度）</th>
                  <th>分項清單值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主要資源ID</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>buildIn</td>
                  <td>內建應用程式內物件</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>已建立</td>
                  <td>建立時間</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>建立者</td>
                  <td>連結 </td>
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
                  <td>結束</td>
                  <td>結束日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>地理單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>history</td>
                  <td>訂閱歷史記錄</td>
                  <td>集合 </td>
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
                  <td>上次修改時間</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>limitedDuration</td>
                  <td>限定期間</td>
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
                  <td>管道</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>行動裝置（簡訊） — 簡訊 — 1</li>
                        <li>電子郵件 — 電子郵件 — 0</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模式</td>
                  <td>模式</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>病毒式 — 病毒式 — 1</li>
                        <li>電子報 — 電子報 — 0</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>修改者</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>名稱</td>
                  <td>ID</td>
                  <td>字串(64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>組織單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>公用標籤</td>
                  <td>服務標籤</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>開始</td>
                  <td>開始日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>訂閱專案登陸頁面</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>訂閱確認</td>
                  <td>連結 </td>
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
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetresource</td>
                  <td>目標定位維度</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>範本（服務）</td>
                  <td>服務範本</td>
                  <td>連結 </td>
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
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>取消訂閱登陸頁面</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>取消訂閱確認</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>有效期間</td>
                  <td>數字 </td>
                  <td> </td>
               </tr>
            </table>

## 篩選

在指定期間內可用（由Planning）

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

依管道型別(byChannel)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>頻道</td>
<td>分項清單</td>
</tr>
</table>

依名稱或標籤(byText)

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

透過目標資源(byTargetResource)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>targetresource</td>
<td>字串</td>
</tr>
</table>
