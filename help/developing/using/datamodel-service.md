---
title: 資料模型服務
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 40%

---

# 服務(nms:service)

## 對象描述

<table>
               <tr>
                  <th>名稱</th>
                  <th>標籤</th>
                  <th>類型（長度）</th>
                  <th>分項清單值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主資源ID</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>內置</td>
                  <td>內建應用程式內物件</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>建立</td>
                  <td>建立時間</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy(userBase)</td>
                  <td>建立者</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>固定價格</td>
                  <td>價格</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>des</td>
                  <td>說明</td>
                  <td>字串(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>端</td>
                  <td>結束日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit(geoUnitBase)</td>
                  <td>地理單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>歷史</td>
                  <td>訂閱歷史記錄</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>為外部</td>
                  <td>是外部資源</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>是模板</td>
                  <td>範本</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>標籤</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>上次修改時間</td>
                  <td>上次修改時間</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>有限持續時間</td>
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
                  <td>消息類型</td>
                  <td>通道</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>移動(SMS)- sms - 1</li>
                        <li>電子郵件 — 電子郵件 — 0</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模式</td>
                  <td>模式</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>病毒 — 病毒 — 1</li>
                        <li>新聞稿 — 新聞稿 — 0</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy(userBase)</td>
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
                  <td>orgUnit(orgUnitBase)</td>
                  <td>組織單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>公共標籤</td>
                  <td>服務標籤</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>開始</td>
                  <td>開始日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage(landingPageSubscriptionBase)</td>
                  <td>訂閱登錄頁</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario(deliveryMCTemplateBase)</td>
                  <td>訂閱確認</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>子方案事件類型</td>
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
                  <td>目標資源</td>
                  <td>定位維度</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>模板（服務）</td>
                  <td>服務範本</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>縮略圖</td>
                  <td>縮圖</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>服務</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>不明嫌犯登錄頁（登錄頁取消訂閱基）</td>
                  <td>取消訂閱登錄頁</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>不明嫌犯場景(deliveryMCTemplateBase)</td>
                  <td>取消訂閱確認</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>不明嫌犯ScenarioEventType</td>
                  <td>不明嫌犯場景事件類型</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>有效性持續時間</td>
                  <td>有效期間</td>
                  <td>數字 </td>
                  <td> </td>
               </tr>
            </table>

## 篩選

在指定期間可用（按Planning）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>開始日期</td>
    <td>date</td>
    </tr>
    <tr>
    <td>結束日期</td>
    <td>date</td>
    </tr>
</table>

按通道類型（按通道）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>通道</td>
<td>枚舉</td>
</tr>
</table>

按名稱或標籤（按文本）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>文本</td>
<td>字串</td>
</tr>
</table>

按目標資源（按TargetResource）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>目標資源</td>
<td>字串</td>
</tr>
</table>
