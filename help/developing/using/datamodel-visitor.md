---
title: 資料模型訪問者
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 17%

---

# 訪問者（nms：訪問者）

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
        <td>注釋</td>
        <td>引用者注釋</td>
        <td>字串(255)</td>
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
        <td>交貨（交貨）</td>
        <td>傳遞</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>交貨ID</td>
        <td>上次交貨的ID</td>
        <td>整數 </td>
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
        <td>外部ID</td>
        <td>外部ID</td>
        <td>字串(64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>名字</td>
        <td>名字</td>
        <td>字串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>轉發URL</td>
        <td>轉發URL</td>
        <td>字串(255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit(geoUnitBase)</td>
        <td>地理單位</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>上次修改時間</td>
        <td>上次修改時間</td>
        <td>日期 </td>
        <td> </td>
    </tr>
    <tr>
        <td>姓氏</td>
        <td>姓氏</td>
        <td>字串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy(userBase)</td>
        <td>修改者</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit(orgUnitBase)</td>
        <td>組織單位</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>來源</td>
        <td>原點</td>
        <td>枚舉（位元組） </td>
        <td>
            <ul>
            <li>未定義 — 未定義 — 0</li>
            <li>無效值 — __Invalid_value_ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>收件人（收件人）</td>
        <td>已識別的配置檔案</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>收件人ID</td>
        <td>設定檔 ID</td>
        <td>整數 </td>
        <td> </td>
    </tr>
    <tr>
        <td>引用者電子郵件</td>
        <td>引用電子郵件</td>
        <td>字串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>引用者FirstName</td>
        <td>引用者名</td>
        <td>字串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>引用者ID</td>
        <td>引用者ID</td>
        <td>整數 </td>
        <td> </td>
    </tr>
    <tr>
        <td>引用者姓氏</td>
        <td>引用者姓</td>
        <td>字串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>引用者Rcp（收件人）</td>
        <td>引用者</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>title</td>
        <td>標籤</td>
        <td>字串(255)</td>
        <td> </td>
    </tr>
</table>

## 篩選器

按姓、名或電子郵件（按文本）</p>

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
