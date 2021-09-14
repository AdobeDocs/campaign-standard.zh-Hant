---
title: DataModel
description: 了解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%

---

# 對象(nms:audience)

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
                  <td>aamMappingId</td>
                  <td>Audience Manager對應ID</td>
                  <td>字串(100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource(amcDataSourceBase)</td>
                  <td>AMC資料來源</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>預覽所選母體</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>資料結構</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>使用行號作為ID</td>
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
                  <td>countDate</td>
                  <td>計數日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>項目 </td>
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
                  <td>doNotPersist</td>
                  <td>不要將此作業過史化</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>中止前出錯</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>過期時間</td>
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
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Adobe Marketing Cloud對象</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部資源</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>記錄檔</td>
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
                  <td>lastModified</td>
                  <td>上次修改時間</td>
                  <td>日期 </td>
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
                  <td>rejectFilename</td>
                  <td>拒絕檔案</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>共用對象的名稱</td>
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
                  <td>sourceId</td>
                  <td>來源Id</td>
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
                  <td>type</td>
                  <td>類型</td>
                  <td>枚舉（字串）(100)</td>
                  <td>
                     <ul>
                        <li>查詢 — 查詢 — 查詢</li>
                        <li>清單 — 清單 — 清單</li>
                        <li>檔案 — 檔案 — 檔案</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>where</td>
                  <td>查詢定義</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作流程（工作流程）</td>
                  <td>工作流程</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
            </table>

## 篩選器

通過篩選維(byFilteringResource)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>filteringResource</td>
    <td>字串</td>
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

按類型(byType)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>type</td>
    <td>分項清單</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>字串</td>
    </tr>
</table>
