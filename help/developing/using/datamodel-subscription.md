---
title: DataModel訂閱事件
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 32%

---

# 訂閱事件(nms：rtEvent)

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
        <td>電子郵件格式</td>
        <td>電子郵件格式</td>
        <td>分項清單（位元組） </td>
        <td>
            <ul>
            <li>文字 — 文字 — 1</li>
            <li>HTML- html - 2</li>
            <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
            <li>未知 — 未知 — 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>已封存的事件ID</td>
        <td>整數 </td>
        <td> </td>
    </tr>
    <tr>
        <td>行動電話</td>
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

## 篩選器

依電子郵件（依電子郵件）

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

依狀態或型別(byStatusOrType)

<table>
        <tr>
        <th>名稱</th>
        <th>類型</th>
        </tr>
        <tr>
        <td>狀態</td>
        <td>分項清單</td>
        </tr>
        <tr>
        <td>類型</td>
        <td>字串</td>
        </tr>
    </table>
