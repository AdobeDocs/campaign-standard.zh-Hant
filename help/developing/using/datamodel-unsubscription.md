---
title: DataModel取消訂閱事件
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 58%

---

# 取消訂閱事件(nms：rtEvent)

## 物件說明

<table>
               <tr>
                  <th>名稱</th>
                  <th>唯讀</th>
                  <th>類型</th>
                  <th>必要</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>假</td>
                  <td>字串</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>假</td>
                  <td>項目</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>電子郵件</td>
                  <td>假</td>
                  <td>字串</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>電子郵件格式</td>
                  <td>假</td>
                  <td>分項清單</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>行動電話</td>
                  <td>假</td>
                  <td>字串</td>
                  <td>假</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>真</td>
                  <td>字串</td>
                  <td>假</td>
               </tr>
            </table>

## 篩選器

byEmail

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

byStatusOrType

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
