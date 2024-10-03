---
title: 開始使用 Campaign Standard API
description: 將 Campaign 與一組技術結合，以建立整合並建置您自己的生態系統。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: 3e6afc55581a24f1fc2b26ac35b801ce38cce905
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 100%

---

# 開始使用 Campaign Standard API {#get-started-apis}

Campaign Standard API 的目的是讓您&#x200B;**建立 Adobe Campaign Standard 的整合**，並將 Adobe Campaign Standard 與您使用的技術面板結合，以建立&#x200B;**專屬的生態系統**。

透過 Adobe Campaign Standard API，您可以存取下列功能：

<table style="table-layout:auto"><tr style="border: 0;">
 <td valign="top"><a href="../../api/using/retrieving-profiles.md"><img width="50px" alt="條件" src="assets/icon_profile.svg"/></a><p><a href="../../api/using/retrieving-profiles.md">輪廓</a></p></td>
<td valign="top"><a href="../../api/using/creating-a-service.md"><img width="50px" alt="條件" src="assets/icon_services.svg"/></a><p><a href="../../api/using/creating-a-service.md">服務與訂閱</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-custom-resources.md"><img width="50px" alt="條件" src="assets/icon_customresources.svg"/></a><p><a href="../../api/using/interacting-with-custom-resources.md">自訂資源</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-marketing-history.md"><img width="50px" alt="條件" src="assets/icon_marketinghistory.svg"/></a><p><a href="../../api/using/interacting-with-marketing-history.md">行銷歷史記錄</a></p></td>
</tr>
<tr style="border: 0;">
<td valign="top"><a href="../../api/using/creating-a-privacy-request.md"><img width="50px" alt="條件" src="assets/icon_privacy.svg"/></a><p><a href="../../api/using/creating-a-privacy-request.md">隱私權管理</a></p></td>
<td valign="top"><a href="../../api/using/managing-transactional-messages.md"><img width="50px" alt="條件" src="assets/icon_transactionalmessage.svg"/></a><p><a href="../../api/using/managing-transactional-messages.md">交易式訊息</a></p></td>
<td valign="top"><a href="../../api/using/controlling-a-workflow.md"><img width="50px" alt="條件" src="assets/icon_workflows.svg"/></a><p><a href="../../api/using/controlling-a-workflow.md">工作流程</a></p></td>
<td valign="top"><a href="../../api/using/retrieving-an-organizational-unit.md"><img width="50px" alt="條件" src="assets/icon_units.svg"/></a><p><a href="../../api/using/retrieving-an-organizational-unit.md">組織單位</a></p></td>
</tr></table>

>[!NOTE]
>
>在執行 API 呼叫之前，請檢查與您的授權合約相應的比例限制。有關詳細資訊，請參見[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。

若要使用 Campaign Standard API，您需要 Adobe I/O 帳戶。這是前進並探索 API 功能的必備第一步。如需詳細資訊，請參閱[本章節](../../api/using/setting-up-api-access.md)。

我們提供的 API 使用&#x200B;**標準概念**，以及 REST 介面和 JSON 負載。

>[!NOTE]
>
>所有範例都可以與 Postman 搭配使用，但您可以自由使用您最愛的 REST 用戶端。

本文件中詳細說明了所有端點，其中包括您應瞭解的控制 API 的一般概念、完整的 API 參考、代碼範例和快速入門手冊。

如果有任何遺漏或看起來不正確，請詢問[社群](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)。
