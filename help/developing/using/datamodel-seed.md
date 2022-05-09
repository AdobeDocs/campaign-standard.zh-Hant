---
title: 資料模型種子成員
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 9b522c84-e296-47c7-9588-2e5ed08ab631
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 26%

---

# 種子成員(nms:seedMember)

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
                  <td>國家/地區</td>
                  <td>國家/地區</td>
                  <td>連結 </td>
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
                  <td>電子郵件</td>
                  <td>電子郵件</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>電子郵件呈現</td>
                  <td>電子郵件轉譯</td>
                  <td>布爾 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>傳真</td>
                  <td>傳真</td>
                  <td>字串(32)</td>
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
                  <td>上次修改時間</td>
                  <td>上次修改時間</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>位置</td>
                  <td>位置</td>
                  <td>物料 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>營銷雲ID</td>
                  <td>Marketing CloudID</td>
                  <td>字串(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>移動應用</td>
                  <td>移動應用</td>
                  <td>物料 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>手機</td>
                  <td>行動裝置</td>
                  <td>字串(32)</td>
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
                  <td>nms_recipient</td>
                  <td>設定檔</td>
                  <td>物料 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>Event</td>
                  <td>物料 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit(orgUnitBase)</td>
                  <td>組織單位</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>電話</td>
                  <td>電話</td>
                  <td>字串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>證明</td>
                  <td>證明</td>
                  <td>布爾 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification</td>
                  <td>推播通知</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>註冊令牌</td>
                  <td>註冊權杖</td>
                  <td>字串(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>示例資料</td>
                  <td>示例資料</td>
                  <td>布爾 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>簡訊</td>
                  <td>行動裝置</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink（狀態）</td>
                  <td>州</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>目標資料</td>
                  <td>擴展</td>
                  <td>字串 </td>
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
                  <td>測試設定檔</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>陷阱</td>
                  <td>補漏白</td>
                  <td>布爾 </td>
                  <td> </td>
               </tr>
            </table>

## 篩選器

按事件類型（按EventType）

<table>
        <tr>
        <th>名稱</th>
        <th>類型</th>
        </tr>
        <tr>
        <td>事件類型</td>
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

按用法（按用法）

<table>
        <tr>
        <th>名稱</th>
        <th>類型</th>
        </tr>
        <tr>
        <td>陷阱</td>
        <td>布爾</td>
        </tr>
        <tr>
        <td>電子郵件呈現</td>
        <td>布爾</td>
        </tr>
        <tr>
        <td>證明</td>
        <td>布爾</td>
        </tr>
    </table>

Test配置檔案（配置檔案）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>種子成員</td>
    <td>連結</td>
    </tr>
</table>
