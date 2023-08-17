---
title: DataModel訪客
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
ht-degree: 42%

---

# 訪客(nms：visitor)

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
        <td>評論</td>
        <td>推薦者評論</td>
        <td>字串(255)</td>
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
        <td>傳遞（傳遞）</td>
        <td>傳遞</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>上次傳遞的ID</td>
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
        <td>外部 ID</td>
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
        <td>forwardUrl</td>
        <td>轉寄 URL</td>
        <td>字串(255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>地理單位</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>上次修改時間</td>
        <td>date </td>
        <td> </td>
    </tr>
    <tr>
        <td>姓氏</td>
        <td>姓氏</td>
        <td>字串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>修改者</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>組織單位</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>來源</td>
        <td>來源</td>
        <td>分項清單（位元組） </td>
        <td>
            <ul>
            <li>未定義 — 未定義 — 0</li>
            <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>收件者(recipient)</td>
        <td>已識別的設定檔</td>
        <td>連結 </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>設定檔 ID</td>
        <td>整數 </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>推薦者電子郵件</td>
        <td>字串(128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>推薦者名字</td>
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
        <td>推薦者姓氏</td>
        <td>字串(50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (recipient)</td>
        <td>推薦者</td>
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

## 篩選

依姓氏、名字或電子郵件(byText)</p>

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
