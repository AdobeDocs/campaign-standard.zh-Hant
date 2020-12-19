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
source-wordcount: '144'
ht-degree: 5%

---


# 訪客(nms:visitor)

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
        <td>評論</td>
        <td>反向連結注釋</td>
        <td>字串(255)</td>
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
        <td>傳送（傳送）</td>
        <td>傳送</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>上次傳送的ID</td>
        <td>整數 </td>
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
        <td>externalId</td>
        <td>外部ID</td>
        <td>字串(64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>名字</td>
        <td>字串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>轉發URL</td>
        <td>字串(255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit(geoUnitBase)</td>
        <td>地理單位</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>上次修改日期</td>
        <td>日期 </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>姓氏</td>
        <td>字串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy(userBase)</td>
        <td>修改者</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit(orgUnitBase)</td>
        <td>組織單位</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>來源</td>
        <td>原點</td>
        <td>枚舉（位元組） </td>
        <td>
            <ul>
            <li>未定義——未定義- 0</li>
            <li>無效值- __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>收件者（收件者）</td>
        <td>已識別的個人檔案</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>描述檔ID</td>
        <td>整數 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>反向連結電子郵件</td>
        <td>字串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>反向連結名稱</td>
        <td>字串(30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>反向連結ID</td>
        <td>整數 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>反向連結姓氏</td>
        <td>字串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp（收件者）</td>
        <td>反向連結</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>title</td>
        <td>標籤</td>
        <td>字串(255)</td>
        <td> </td>
    </tr>
</table>

## 濾鏡

依姓氏、名字或電子郵件（依文字）</p>

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