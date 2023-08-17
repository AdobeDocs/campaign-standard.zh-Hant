---
title: 資料模型程式
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: b05dc67a-6447-4d22-99f2-8a14a0ee46d2
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 36%

---

# 程式(nms：program)

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
                  <td>活動</td>
                  <td>活動</td>
                  <td>集合 </td>
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
                  <td>已建立</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
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
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
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
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logicalStatus</td>
                  <td>執行狀態</td>
                  <td>分項清單（字串） (255)</td>
                  <td>
                     <ul>
                        <li>進行中 — 已開始 — 已開始</li>
                        <li>編輯 — 版本 — 版本</li>
                        <li>已完成 — 已完成 — 已完成</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>錯誤 — 錯誤 — 錯誤</li>
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
                  <td>父級(programBase)</td>
                  <td>父級方案</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>即時報告</td>
                  <td>即時報表</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>開始</td>
                  <td>開始日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>狀態</td>
                  <td>狀態</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>開始 — 開始 — 1</li>
                        <li>編輯 — 版本 — 0</li>
                        <li>已完成 — 已完成 — 2</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>範本（方案）</td>
                  <td>計畫範本</td>
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

## 篩選

依邏輯狀態(byLogicalStatus)

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

按期間（按期間）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>時間週期</td>
    <td>字串</td>
    </tr>
</table>

包含來自異質性清單的持續傳遞（使用Continuous）

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

包含子程式(withParent)

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

僅限合格的父項（合格父項）

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

為指定期間計畫（由Planning）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

在指定期間顯示(byCalendar)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>
