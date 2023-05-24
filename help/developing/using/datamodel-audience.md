---
title: 資料模型受眾
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 40%

---

# 受眾（nms：受眾）

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
                  <td>aamMappingId</td>
                  <td>Audience Manager映射ID</td>
                  <td>字串(100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource(amcDataSourceBase)</td>
                  <td>AMC資料源</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>受眾資料</td>
                  <td>預覽所選人口</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>資料架構</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>受眾元資料</td>
                  <td>受眾元資料</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>將行號用作ID</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>計數</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>計數日期</td>
                  <td>計數日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>計數預覽</td>
                  <td>計數預覽</td>
                  <td>項目 </td>
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
                  <td>des</td>
                  <td>說明</td>
                  <td>字串(512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>不持續</td>
                  <td>不要將此工作歷史化</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>錯誤限制</td>
                  <td>中止前的錯誤</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>到期日期</td>
                  <td>到期時間</td>
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
                  <td>具有架構</td>
                  <td>HasSchema</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>是AMC</td>
                  <td>Adobe Marketing Cloud觀眾</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>為外部</td>
                  <td>是外部資源</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>作業日誌</td>
                  <td>記錄</td>
                  <td>集合 </td>
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
                  <td>拒絕檔案名</td>
                  <td>拒絕檔案</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>共用受眾</td>
                  <td>共用受眾的名稱</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>來源</td>
                  <td>來源</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>源ID</td>
                  <td>來源 ID</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>對象</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>類型</td>
                  <td>類型</td>
                  <td>枚舉（字串）(100)</td>
                  <td>
                     <ul>
                        <li>查詢 — 查詢 — 查詢</li>
                        <li>清單 — 清單 — 清單</li>
                        <li>檔案 — 檔案 — 檔案</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>何處</td>
                  <td>查詢定義</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作流（工作流）</td>
                  <td>工作流程</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
            </table>

## 篩選

通過篩選維(byFilteringResource)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>篩選資源</td>
    <td>字串</td>
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

按類型（按類型）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>類型</td>
    <td>枚舉</td>
    </tr>
    <tr>
    <td>是AMC</td>
    <td>字串</td>
    </tr>
</table>
