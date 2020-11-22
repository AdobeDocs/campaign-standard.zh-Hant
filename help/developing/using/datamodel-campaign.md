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
source-wordcount: '216'
ht-degree: 6%

---


# 促銷活動(nms:campaign)

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
                  <td>活動</td>
                  <td>活動</td>
                  <td>系列 </td>
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
                  <td>desc</td>
                  <td>說明</td>
                  <td>字串(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>持續時間</td>
                  <td>促銷活動持續時間</td>
                  <td>數字 </td>
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
                  <td>logicalStatus</td>
                  <td>執行狀態</td>
                  <td>枚舉（字串）(255)</td>
                  <td>
                     <ul>
                        <li>進行中——已啟動——已啟動</li>
                        <li>編輯——版本——版本</li>
                        <li>完成——完成——完成</li>
                        <li>警告——警告——警告</li>
                        <li>錯誤——錯誤——錯誤</li>
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
                  <td>方案（方案庫）</td>
                  <td>方案</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>即時報告</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>開始日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>狀態</td>
                  <td>狀態</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>開始——開始- 1</li>
                        <li>編輯——版本- 0</li>
                        <li>完成——完成- 2</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>範本（促銷活動）</td>
                  <td>促銷活動範本</td>
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
                  <td>Campaign</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
            </table>

## 濾鏡

按邏輯狀態（按邏輯狀態）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>state</td>
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

按期間（按期間）

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
    <td>timePeriod</td>
    <td>字串</td>
    </tr>
</table>

依狀態（依狀態）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>state</td>
    <td>枚舉</td>
    </tr>
</table>

從異構清單包括連續傳送（具有Continuous）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>布林值</td>
    </tr>
</table>

為指定期間計畫（按計畫）

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

在指定期間內（依日曆）

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