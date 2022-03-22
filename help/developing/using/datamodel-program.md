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
ht-degree: 21%

---

# 程式(nms:program)

## 對象描述

<table>
               <tr>
                  <th>名稱</th>
                  <th>標籤</th>
                  <th>類型（長度）</th>
                  <th>枚舉值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主資源ID</td>
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
                  <td>內置</td>
                  <td>內置應用程式對象</td>
                  <td>布爾 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>建立</td>
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
                  <td>des</td>
                  <td>說明</td>
                  <td>字串(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>端</td>
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
                  <td>為外部</td>
                  <td>是外部資源</td>
                  <td>布爾 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>是模板</td>
                  <td>範本</td>
                  <td>布爾 </td>
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
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>邏輯狀態</td>
                  <td>執行狀態</td>
                  <td>枚舉（字串）(255)</td>
                  <td>
                     <ul>
                        <li>正在進行 — 已啟動 — 已啟動</li>
                        <li>編輯 — 版本 — 版本</li>
                        <li>完成 — 完成 — 完成</li>
                        <li>警告 — 警告 — 警告</li>
                        <li>錯誤 — 錯誤 — 錯誤</li>
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
                  <td>父級(programBase)</td>
                  <td>父程式</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>即時報告</td>
                  <td>即時報告</td>
                  <td>物料 </td>
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
                        <li>已啟動 — 已啟動 — 1</li>
                        <li>編輯 — 版本 — 0</li>
                        <li>完成 — 完成 — 2</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>模板（程式）</td>
                  <td>程式模板</td>
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
                  <td>方案</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
            </table>

## 篩選器

按邏輯狀態（按LogicalStatus）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>狀態</td>
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

按期間（按期間）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>開始日期</td>
    <td>日期</td>
    </tr>
    <tr>
    <td>時段</td>
    <td>字串</td>
    </tr>
</table>

包括來自異構清單(withContinuous)的連續交付

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>與連續</td>
    <td>布爾</td>
    </tr>
</table>

包括子程式(withParent)

<table>
        <tr>
        <th>名稱</th>
        <th>類型</th>
        </tr>
        <tr>
        <td>帶父項</td>
        <td>布爾</td>
        </tr>
    </table>

僅合格父母（合格父母）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>程式</td>
    <td>連結</td>
    </tr>
</table>

為給定期間計畫（按Planning）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>開始日期</td>
    <td>日期</td>
    </tr>
    <tr>
    <td>結束日期</td>
    <td>日期</td>
    </tr>
</table>

在指定期間（按日曆）存在

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>開始日期</td>
    <td>日期</td>
    </tr>
    <tr>
    <td>結束日期</td>
    <td>日期</td>
    </tr>
</table>
