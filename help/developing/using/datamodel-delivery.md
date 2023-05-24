---
title: 資料模型交付
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 30%

---

# 交付（nms：交付）

## 對象描述

<table>
               <tr>
                  <th>名稱</th>
                  <th>標籤</th>
                  <th>類型（長度）</th>
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
                  <td>主資源ID</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>測試</td>
                  <td>A/B 測試</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>先進</td>
                  <td>高級交付</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>高級參數</td>
                  <td>高級參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>目錄</td>
                  <td>Adobe Experience Manager內容</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>警報消息</td>
                  <td>警告消息</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>警報模式</td>
                  <td>警告類型</td>
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
                  <td>品牌推廣（品牌推廣基礎）</td>
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
                  <td>內置</td>
                  <td>內建應用程式內物件</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>市場活動（市場活動基礎）</td>
                  <td>Campaign</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cms帳戶(extAccountAEMBase)</td>
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
                  <td>內容源</td>
                  <td>內容源</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager- aem - 1</li>
                        <li>Adobe Campaign — 活動 — 0</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>上下文資源類型</td>
                  <td>資源類型</td>
                  <td>字串 </td>
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
                  <td>交付模式</td>
                  <td>傳遞模式</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>批量交付 — 批量 — 1</li>
                        <li>中間採購 — 中間採購 — 4</li>
                        <li>說明 — 描述性 — 2</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                        <li>外部 — 外部 — 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider(extAccountBase)</td>
                  <td>路由</td>
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
                  <td>電子郵件預覽</td>
                  <td>電子郵件預覽</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>排除日誌</td>
                  <td>排除記錄檔</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>排除</td>
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
                  <td>執行類型</td>
                  <td>執行類型</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>唯一 — 一次 — 0</li>
                        <li>連續 — 連續 — 1</li>
                        <li>消息中心 — 消息中心 — 2</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>預測日誌</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit(geoUnitBase)</td>
                  <td>地理單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>有附件</td>
                  <td>新增附加的檔案</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>表徵圖</td>
                  <td>圖示</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>事務性電子郵件 — 電子郵件閃電 — 60</li>
                        <li>傳真 — 傳真 — 4</li>
                        <li>移動(SMS)- sms - 1</li>
                        <li>定期電子郵件 — 電子郵件刷新 — 30</li>
                        <li>直郵 — 紙 — 3</li>
                        <li>電話 — 電話 — 2</li>
                        <li>其他 — 其他 — 120</li>
                        <li>定期SMS - smsRefresh - 31</li>
                        <li>移動應用程式 — pushNotification - 40</li>
                        <li>事務性SMS - smsLightning - 61</li>
                        <li>電子郵件 — 電子郵件 — 0</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>為外部</td>
                  <td>是外部資源</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>為主</td>
                  <td>母版</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>是模板</td>
                  <td>範本</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>迭代</td>
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
                  <td>作業日誌</td>
                  <td>記錄</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>核</td>
                  <td>指標</td>
                  <td>項目 </td>
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
                  <td>mailParameters</td>
                  <td>電子郵件標頭參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>日期</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>映射(deliveryMapping)</td>
                  <td>目標對應</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master(deliveryBase)</td>
                  <td>主實例</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>主KPIS</td>
                  <td>主指標</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>消息類型</td>
                  <td>通道</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>傳真 — 傳真 — 4</li>
                        <li>移動(SMS)- sms - 1</li>
                        <li>電子郵件 — 電子郵件 — 0</li>
                        <li>電話 — 電話 — 2</li>
                        <li>直郵 — 紙 — 3</li>
                        <li>移動應用程式 — pushNotification - 40</li>
                        <li>其他 — 其他 — 120</li>
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
                  <td>優惠管理</td>
                  <td>服務管理</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit(orgUnitBase)</td>
                  <td>組織單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>父級(deliveryBase)</td>
                  <td>父系傳遞</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>優先順序</td>
                  <td>傳遞優先順序</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>高 — 高 — 20</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                        <li>正常 — 正常 — 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>程式（程式庫）</td>
                  <td>方案</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>證明</td>
                  <td>證明</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification預覽</td>
                  <td>推送通知預覽</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotification參數</td>
                  <td>PushNotification參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>即時報告</td>
                  <td>即時報告</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>資源版本</td>
                  <td>資源版本</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>功能區消息</td>
                  <td>功能區消息</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>場景</td>
                  <td>傳遞範本參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>調度</td>
                  <td>傳遞排程</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sms參數</td>
                  <td>簡訊參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sms預覽</td>
                  <td>SMS預覽</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>狀態</td>
                  <td>狀態</td>
                  <td>枚舉（位元組） </td>
                  <td>
                     <ul>
                        <li>開始掛起 — 開始掛起 — 51</li>
                        <li>準備交付 — 就緒 — 45</li>
                        <li>重試掛起 — 重試掛起 — 61</li>
                        <li>正在重試 — retryInProgress - 62</li>
                        <li>失敗 — 失敗 — 87</li>
                        <li>正在進行 — 已啟動 — 55</li>
                        <li>目標掛起 — targetPrepPending - 11</li>
                        <li>個性化掛起 — messagePrepPending - 21</li>
                        <li>暫停 — 暫停 — 75</li>
                        <li>編輯 — 版本 — 0</li>
                        <li>已完成 — 已完成 — 95</li>
                        <li>正在盤點 — targetSelection - 12</li>
                        <li>消息已定版 — 消息就緒 — 25</li>
                        <li>個性化或計數失敗 — preparationError - 37</li>
                        <li>已停止 — 已取消 — 85</li>
                        <li>正在個性化 — 消息準備 — 22</li>
                        <li>目標就緒 — 目標就緒 — 15</li>
                        <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
                        <li>正在進行的仲裁 — 目標</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>目標</td>
                  <td>傳遞目標母體</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>模板(deliveryTemplateSummary)</td>
                  <td>傳遞範本</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>縮略圖</td>
                  <td>遞送縮略圖</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
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
                  <td>跟蹤日誌</td>
                  <td>追蹤記錄</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>跟蹤URL</td>
                  <td>被追蹤的 URL</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>觸發器消息</td>
                  <td>異動訊息的參數</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>類型學（類型學基礎）</td>
                  <td>類型</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作流(workflowBase)</td>
                  <td>目標工作流</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>工作流狀態</td>
                  <td>工作流狀態</td>
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
            </table>

## 篩選

按通道類型（按通道）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>通道</td>
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
    <td>執行類型</td>
    <td>枚舉</td>
    </tr>
</table>

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
    <tr>
    <td>麥克</td>
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
    <td>時段</td>
    <td>字串</td>
    </tr>
</table>

按期間（按StartPeriod）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>開始日期</td>
    <td>date</td>
    </tr>
    <tr>
    <td>時段</td>
    <td>字串</td>
    </tr>
</table>

按發佈狀態（按PublicationStatus）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>p狀態</td>
    <td>枚舉</td>
    </tr>
</table>

按狀態（按狀態）

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

後續消息（show跟進）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>跟蹤</td>
    <td>布林值</td>
    </tr>
</table>

包括高級交貨(withAdvanced)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>先進</td>
    <td>布林值</td>
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
    <td>布林值</td>
    </tr>
</table>

包括證明（使用FCP）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>使用FCP</td>
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
    <td>開始日期</td>
    <td>date</td>
    </tr>
    <tr>
    <td>結束日期</td>
    <td>date</td>
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
    <td>date</td>
    </tr>
    <tr>
    <td>結束日期</td>
    <td>date</td>
    </tr>
</table>

現成顯示(showOob)

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>肥</td>
    <td>布林值</td>
    </tr>
</table>
