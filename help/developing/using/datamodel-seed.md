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
ht-degree: 47%

---

# 種子成員(nms：seedMember)

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
                  <td>國家/地區</td>
                  <td>國家/地區</td>
                  <td>連結 </td>
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
                  <td>電子郵件</td>
                  <td>電子郵件</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailRendering</td>
                  <td>電子郵件轉譯</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>傳真</td>
                  <td>傳真</td>
                  <td>字串(32)</td>
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
                  <td>lastModified</td>
                  <td>上次修改時間</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>位置</td>
                  <td>位置</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marketingCloudId</td>
                  <td>MARKETING CLOUDID</td>
                  <td>字串(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>行動應用程式</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>行動電話</td>
                  <td>行動裝置</td>
                  <td>字串(32)</td>
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
                  <td>nms_recipient</td>
                  <td>設定檔</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>Event</td>
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
                  <td>電話</td>
                  <td>電話</td>
                  <td>字串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>證明</td>
                  <td>證明</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotification</td>
                  <td>推播通知</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registrationToken</td>
                  <td>註冊權杖</td>
                  <td>字串(256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampleData</td>
                  <td>樣本資料</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>簡訊</td>
                  <td>行動裝置</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
                  <td>狀態</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetdata</td>
                  <td>擴充功能</td>
                  <td>字串 </td>
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
                  <td>測試設定檔</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>補漏白</td>
                  <td>補漏白</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
            </table>

## 篩選

依事件型別(byEventType)

<table>
        <tr>
        <th>名稱</th>
        <th>類型</th>
        </tr>
        <tr>
        <td>eventtype</td>
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

依使用狀況（依使用狀況）

<table>
        <tr>
        <th>名稱</th>
        <th>類型</th>
        </tr>
        <tr>
        <td>補漏白</td>
        <td>布林值</td>
        </tr>
        <tr>
        <td>emailRendering</td>
        <td>布林值</td>
        </tr>
        <tr>
        <td>證明</td>
        <td>布林值</td>
        </tr>
    </table>

測試設定檔（設定檔）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>seedMember</td>
    <td>連結</td>
    </tr>
</table>
