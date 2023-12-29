---
title: DataModel傳遞
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 26%

---

# 傳遞(nms：delivery)

## 物件說明

<table>
               <tr>
                  <th>名稱</th>
                  <th>標籤</th>
                  <th>型別（長度）</th>
                  <th>分項清單值</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>證明</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主要資源ID</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>A/B 測試</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>進階</td>
                  <td>進階傳遞</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>高級參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Adobe Experience Manager內容</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertmessage</td>
                  <td>警告訊息</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>警示模式</td>
                  <td>警告型別</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>附件</td>
                  <td>附加的檔案</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>品牌推廣（品牌基礎）</td>
                  <td>品牌</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>傳遞記錄</td>
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
                  <td>行銷活動(campaignBase)</td>
                  <td>Campaign</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Adobe Experience Manager帳戶</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>命令</td>
                  <td>命令</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>內容</td>
                  <td>內容</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentsource</td>
                  <td>內容來源</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign — 行銷活動 — 0</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>資源類型</td>
                  <td>字串 </td>
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
                  <td>deliverymode</td>
                  <td>傳遞模式</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>大量傳送 — 大量傳送 — 1</li>
                        <li>中間來源 — midSourcing - 4</li>
                        <li>說明 — 描述性 — 2</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>外部 — 外部 — 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>路由</td>
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
                  <td>emailPreview</td>
                  <td>電子郵件預覽</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>排除記錄</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>排除專案</td>
                  <td>排除原因</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>執行</td>
                  <td>傳遞執行參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>執行類型</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>唯一 — 一次 — 0</li>
                        <li>連續 — 連續 — 1</li>
                        <li>訊息中心 — messageCenter - 2</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>預測記錄</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>地理單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>新增附加的檔案</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>圖示</td>
                  <td>圖示</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>異動電子郵件 — emailLightning - 60</li>
                        <li>傳真 — 傳真 — 4</li>
                        <li>行動裝置（簡訊） — 簡訊 — 1</li>
                        <li>週期性電子郵件 — emailRefresh - 30</li>
                        <li>直接郵件 — 紙張 — 3</li>
                        <li>電話 — 電話 — 2</li>
                        <li>其他 — 其他 — 120</li>
                        <li>循環SMS - smsRefresh - 31</li>
                        <li>行動應用程式 — pushNotification - 40</li>
                        <li>異動SMS - smsLightning - 61</li>
                        <li>電子郵件 — 電子郵件 — 0</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部資源</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>主版</td>
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
                  <td>反複專案</td>
                  <td>傳遞</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作</td>
                  <td>工作</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>記錄</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpi</td>
                  <td>指標</td>
                  <td>項目 </td>
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
                  <td>mailParameters</td>
                  <td>電子郵件標頭參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>對應(deliveryMapping)</td>
                  <td>目標對應</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>主要(deliveryBase)</td>
                  <td>主要執行個體</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpi</td>
                  <td>主要指標</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>管道</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>傳真 — 傳真 — 4</li>
                        <li>行動裝置（簡訊） — 簡訊 — 1</li>
                        <li>電子郵件 — 電子郵件 — 0</li>
                        <li>電話 — 電話 — 2</li>
                        <li>直接郵件 — 紙張 — 3</li>
                        <li>行動應用程式 — pushNotification - 40</li>
                        <li>其他 — 其他 — 120</li>
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
                  <td>offerManagement</td>
                  <td>Offer Management</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>組織單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>上層(deliveryBase)</td>
                  <td>父系傳遞</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>優先順序</td>
                  <td>傳遞優先順序</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>高 — 高 — 20</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>一般 — 一般 — 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>方案(programBase)</td>
                  <td>方案</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>校樣</td>
                  <td>證明</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>推播通知預覽</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>PushNotification引數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>即時報告</td>
                  <td>即時報表</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>資源版本</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>功能區訊息</td>
                  <td>功能區訊息</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>情境</td>
                  <td>傳遞範本參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>排程</td>
                  <td>傳遞排程</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>簡訊引數</td>
                  <td>簡訊參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>簡訊預覽</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>狀態</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>開始擱置 — startPending - 51</li>
                        <li>準備送貨 — 準備 — 45</li>
                        <li>重試擱置 — 重試擱置 — 61</li>
                        <li>正在重試 — retryInProgress - 62</li>
                        <li>失敗 — 失敗 — 87</li>
                        <li>進行中 — 已開始 — 55</li>
                        <li>鎖定目標擱置中 — targetPrepPending - 11</li>
                        <li>個人化擱置中 — messagePrepPending - 21</li>
                        <li>已暫停 — 已暫停 — 75</li>
                        <li>編輯 — 版本 — 0</li>
                        <li>已完成 — 已完成 — 95</li>
                        <li>計算中 — targetSelection - 12</li>
                        <li>已完成訊息 — messageReady - 25</li>
                        <li>個人化或計數失敗 — preparationError - 37</li>
                        <li>已停止 — 已取消 — 85</li>
                        <li>正在進行個人化 — messagePreparation - 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>仲裁進行中 — targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>目標</td>
                  <td>傳遞目標族群</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>範本(deliveryTemplateSummary)</td>
                  <td>傳遞範本</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>縮圖</td>
                  <td>傳遞縮圖</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>標題</td>
                  <td>傳遞</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>追蹤</td>
                  <td>追蹤參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>追蹤記錄</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>被追蹤的 URL</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>交易型訊息的參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>型別(typologyBase)</td>
                  <td>類型</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作流程(workflowBase)</td>
                  <td>目標定位工作流程</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowstatus</td>
                  <td>工作流程狀態</td>
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
            </table>

## 篩選

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

依執行型別(byExecutionType)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>分項清單</td>
    </tr>
</table>

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
    <tr>
    <td>mc</td>
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
    <td>時間週期</td>
    <td>字串</td>
    </tr>
</table>

按期間(byStartPeriod)

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
    <td>時間週期</td>
    <td>字串</td>
    </tr>
</table>

依發佈狀態(byPublicationStatus)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>分項清單</td>
    </tr>
</table>

依狀態(byState)

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

後續追蹤訊息(showFollowup)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>後續追蹤</td>
    <td>布林值</td>
    </tr>
</table>

包含進階傳遞（含進階）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>進階</td>
    <td>布林值</td>
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

包含校樣(withFCP)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>withFCP</td>
    <td>布林值</td>
    </tr>
</table>

在指定期間內計畫（由Planning）

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

在指定期間顯示(byCalendar)

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

顯示立即可用(showOob)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>oob</td>
    <td>布林值</td>
    </tr>
</table>
