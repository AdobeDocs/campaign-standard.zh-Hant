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
source-wordcount: '687'
ht-degree: 6%

---


# 傳送（nms：傳送）

## 物件說明

<table>
               <tr>
                  <th>名稱</th>
                  <th>標籤</th>
                  <th>類型（長度）</th>
                  <th>枚舉值</th>
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
                  <td>advanced</td>
                  <td>進階傳送</td>
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
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>警告訊息</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>警告類型</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>附件</td>
                  <td>附加的檔案</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>品牌推廣（品牌推廣基礎）</td>
                  <td>品牌</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>傳送記錄檔</td>
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
                  <td>campaign(campaignBase)</td>
                  <td>Campaign</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount(extAccountAEMBase)</td>
                  <td>Adobe Experience Manager帳戶</td>
                  <td>link </td>
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
                  <td>contentSource</td>
                  <td>內容來源</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campaign - 0</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
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
                  <td>deliveryMode</td>
                  <td>傳送模式</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>批量傳送——批量- 1</li>
                        <li>中部採購——中部採購- 4</li>
                        <li>說明——說明性- 2</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
                        <li>外部——外部- 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider(extAccountBase)</td>
                  <td>路由</td>
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
                  <td>emailPreview</td>
                  <td>電子郵件預覽</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>排除記錄檔</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>排除</td>
                  <td>排除原因</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>執行</td>
                  <td>傳送執行參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>執行類型</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>唯一——一次- 0</li>
                        <li>連續——連續- 1</li>
                        <li>消息中心- messageCenter - 2</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>ForecastLog</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit(geoUnitBase)</td>
                  <td>地理單位</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>添加附加檔案</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>表徵圖</td>
                  <td>圖示</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>交易電子郵件- emailLightning - 60</li>
                        <li>傳真——傳真- 4</li>
                        <li>行動(SMS)- sms - 1</li>
                        <li>循環電子郵件- emailRefresh - 30</li>
                        <li>直接郵件——紙張- 3</li>
                        <li>電話——電話- 2</li>
                        <li>其他——其他- 120</li>
                        <li>經常性SMS - smsRefresh - 31</li>
                        <li>行動應用程式- pushNotification - 40</li>
                        <li>交易型SMS - smsLightning - 61</li>
                        <li>電子郵件——電子郵件- 0</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
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
                  <td>主</td>
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
                  <td>迭代</td>
                  <td>傳遞</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作</td>
                  <td>工作</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>記錄檔</td>
                  <td>系列 </td>
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
                  <td>mailParameters</td>
                  <td>電子郵件標題參數</td>
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
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master(deliveryBase)</td>
                  <td>主實例</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>主指標</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>通道</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>傳真——傳真- 4</li>
                        <li>行動(SMS)- sms - 1</li>
                        <li>電子郵件——電子郵件- 0</li>
                        <li>電話——電話- 2</li>
                        <li>直接郵件——紙張- 3</li>
                        <li>行動應用程式- pushNotification - 40</li>
                        <li>其他——其他- 120</li>
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
                  <td>offerManagement</td>
                  <td>選件管理</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit(orgUnitBase)</td>
                  <td>組織單位</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent(deliveryBase)</td>
                  <td>父傳送</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>優先順序</td>
                  <td>傳送優先順序</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>高——高- 20</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
                        <li>正常——正常- 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>方案（方案庫）</td>
                  <td>方案</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>校樣</td>
                  <td>校樣</td>
                  <td>系列 </td>
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
                  <td>PushNotification參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>即時報告</td>
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
                  <td>ribbonMessage</td>
                  <td>功能區訊息</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>藍本</td>
                  <td>傳送範本參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>調度</td>
                  <td>傳送排程</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>SMS參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>SMS預覽</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>狀態</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>開始擱置中- startPending - 51</li>
                        <li>準備交付——準備- 45</li>
                        <li>重試擱置中- retryPending - 61</li>
                        <li>重試進行中- retryInProgress - 62</li>
                        <li>失敗——失敗- 87</li>
                        <li>進行中——已啟動- 55</li>
                        <li>定位待定- targetPrepPending - 11</li>
                        <li>個人化擱置中- messagePrepPending - 21</li>
                        <li>暫停——暫停- 75</li>
                        <li>編輯——版本- 0</li>
                        <li>完成——完成- 95</li>
                        <li>計數進行中- targetSelection - 12</li>
                        <li>消息已完成- messageReady - 25</li>
                        <li>個人化或計數失敗- preparationError - 37</li>
                        <li>已停止——已取消- 85</li>
                        <li>個人化進行中——訊息準備- 22</li>
                        <li>目標就緒——目標就緒- 15</li>
                        <li>無效值- __Invalid_value__ - __Invalid_value__</li>
                        <li>進行中仲裁——目標仲裁- 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>目標</td>
                  <td>傳送目標人口</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>範本(deliveryTemplateSummary)</td>
                  <td>傳送範本</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>縮圖</td>
                  <td>傳送縮圖</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>傳送</td>
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
                  <td>追蹤記錄檔</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrl</td>
                  <td>追蹤的URL</td>
                  <td>系列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>事務性消息的參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>類型學（類型學基礎）</td>
                  <td>類型學</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow(workflowBase)</td>
                  <td>定位工作流程</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>工作流程狀態</td>
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
            </table>

## 濾鏡

依頻道類型（依頻道）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>頻道</td>
    <td>枚舉</td>
    </tr>
</table>

按執行類型(byExecutionType)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>枚舉</td>
    </tr>
</table>

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
    <td>timePeriod</td>
    <td>字串</td>
    </tr>
</table>

By period(byStartPeriod)

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

依出版物狀態(byPublicationStatus)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>枚舉</td>
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

後續訊息(showFolloup)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>追蹤</td>
    <td>布林值</td>
    </tr>
</table>

包含進階傳送(withAdvanced)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>advanced</td>
    <td>布林值</td>
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

包含校樣（使用FCP）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>具有FCP</td>
    <td>布林值</td>
    </tr>
</table>

在指定期間內計畫（按計畫）

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

立即顯示(showOob)

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