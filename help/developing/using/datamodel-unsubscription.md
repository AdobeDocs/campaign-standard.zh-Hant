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

# 取消訂閱事件(nms:rtEvent)

## 對象描述

<table>
               <tr>
                  <th>名稱</th>
                  <th>只讀</th>
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
                  <td>電子郵件格式</td>
                  <td>False</td>
                  <td>枚舉</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>手機</td>
                  <td>False</td>
                  <td>字串</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>伺服器URL</td>
                  <td>True</td>
                  <td>字串</td>
                  <td>False</td>
               </tr>
            </table>

## 篩選

按電子郵件

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

按狀態或類型

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
        <td>類型</td>
        <td>字串</td>
        </tr>
    </table>
