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
source-wordcount: '77'
ht-degree: 6%

---


# 訂閱事件(nms:rtEvent)

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
        <td>ctx</td>
        <td>事件內容</td>
        <td>項目 </td>
        <td> </td>
    </tr>
    <tr>
        <td>電子郵件</td>
        <td>電子郵件</td>
        <td>字串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>電子郵件格式</td>
        <td>枚舉（位元組） </td>
        <td>
            <ul>
            <li>文字——文字- 1</li>
            <li>HTML - html - 2</li>
            <li>無效值- __Invalid_value__ - __Invalid_value__</li>
            <li>未知——未知- 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>封存事件ID</td>
        <td>整數 </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>行動電話號碼</td>
        <td>字串(32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>字串 </td>
        <td> </td>
    </tr>
</table>

## 濾鏡

透過電子郵件（透過電子郵件）

<table>
    <tr>
    <th>名稱</th>
    <th>類型</th>
    </tr>
    <tr>
    <td>電子郵件</td>
    <td>字串</td>
    </tr>
</table>

按狀態或類型(byStatusOrType)

<table>
        <tr>
        <th>名稱</th>
        <th>類型</th>
        </tr>
        <tr>
        <td>狀態</td>
        <td>枚舉</td>
        </tr>
        <tr>
        <td>type</td>
        <td>字串</td>
        </tr>
    </table>