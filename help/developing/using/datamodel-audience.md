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
source-wordcount: '207'
ht-degree: 4%

---


# 觀眾(nms:audience)

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
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>預覽選取的人口族群</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>資料架構</td>
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
                  <td>計數預覽</td>
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
                  <td>doNotPersist</td>
                  <td>不要將此作業歷史化</td>
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
                  <td>link </td>
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
                  <td>Adobe Marketing Cloud受眾</td>
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
                  <td>系列 </td>
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
                  <td>來源ID</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>標題</td>
                  <td>閱聽眾</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>type</td>
                  <td>類型</td>
                  <td>枚舉（字串）(100)</td>
                  <td>
                     <ul>
                        <li>查詢——查詢——查詢</li>
                        <li>清單——清單——清單</li>
                        <li>檔案——檔案——檔案</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
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
                  <td>link </td>
                  <td> </td>
               </tr>
            </table>

## 濾鏡

透過篩選維度(byFilteringResource)

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

依類型（依類型）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>type</td>
    <td>枚舉</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>字串</td>
    </tr>
</table>