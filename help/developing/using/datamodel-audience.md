---
title: DataModel對象
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 36%

---

# 對象(nms：audience)

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
                  <td>aamMappingId</td>
                  <td>Audience Manager對應ID</td>
                  <td>字串(100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>AMC資料來源</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>預覽選取的母體</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>資料結構描述</td>
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
                  <td>使用行號作為識別碼</td>
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
                  <td>createdBy (userBase)</td>
                  <td>建立者：</td>
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
                  <td>不要將此工作歷史化</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>中止前的錯誤</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationdate</td>
                  <td>到期時間</td>
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
                  <td>記錄</td>
                  <td>集合 </td>
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
                  <td>rejectFilename</td>
                  <td>拒絕檔案</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedaudience</td>
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
                  <td>來源 ID</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>標題</td>
                  <td>對象</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>類型</td>
                  <td>類型</td>
                  <td>分項清單（字串） (100)</td>
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
                  <td>位置</td>
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

依篩選維度(byFilteringResource)

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

依型別(byType)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>類型</td>
    <td>分項清單</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>字串</td>
    </tr>
</table>
