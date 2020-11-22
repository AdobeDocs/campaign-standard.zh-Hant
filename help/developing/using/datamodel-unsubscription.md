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
source-wordcount: '53'
ht-degree: 5%

---


# 取消訂閱事件(nms:rtEvent)

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
                  <td>False</td>
                  <td>字串</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>False</td>
                  <td>項目</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>電子郵件</td>
                  <td>False</td>
                  <td>字串</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>False</td>
                  <td>枚舉</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>False</td>
                  <td>字串</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>True</td>
                  <td>字串</td>
                  <td>False</td>
               </tr>
            </table>

## 濾鏡

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
        <td>枚舉</td>
        </tr>
        <tr>
        <td>type</td>
        <td>字串</td>
        </tr>
    </table>