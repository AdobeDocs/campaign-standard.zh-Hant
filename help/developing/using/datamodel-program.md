---
title: DataModel
description: 了解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: b05dc67a-6447-4d22-99f2-8a14a0ee46d2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 7%

---

# 程式(nms:program)

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
                  <td>集合 </td>
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
                  <td>連結 </td>
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
                  <td>geoUnit(geoUnitBase)</td>
                  <td>地理單位</td>
                  <td>連結 </td>
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
                  <td>label</td>
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
                  <td>logicalStatus</td>
                  <td>執行狀態</td>
                  <td>枚舉（字串）(255)</td>
                  <td>
                     <ul>
                        <li>進行中 — 已啟動 — 已啟動</li>
                        <li>編輯 — 版本 — 版本</li>
                        <li>已完成 — 已完成 — 已完成</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>錯誤 — 錯誤 — 錯誤</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
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
                  <td>parent(programBase)</td>
                  <td>父程式</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>即時報表</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>開始</td>
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
                        <li>已開始 — 已開始 — 1</li>
                        <li>編輯 — 版本 — 0</li>
                        <li>已完成 — 已完成 — 2</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模板（程式）</td>
                  <td>方案模板</td>
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
                  <td>title</td>
                  <td>方案</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
            </table>

## 篩選器

按邏輯狀態（按邏輯狀態）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>state</td>
    <td>分項清單</td>
    </tr>
</table>

按名稱或標籤(byText)

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

包括從異構清單（具有Continuous）進行連續傳遞

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

包括子程式（與父項）

<table>
        <tr>
        <th>名稱</th>
        <th>類型</th>
        </tr>
        <tr>
        <td>withParent</td>
        <td>布林值</td>
        </tr>
    </table>

僅限合格父母（合格父母）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>方案</td>
    <td>連結</td>
    </tr>
</table>

指定期間的計畫（按計畫）

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

在指定期間存在（按日曆）

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
