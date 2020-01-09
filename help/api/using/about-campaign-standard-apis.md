---
title: 關於 Campaign Standard API
description: 進一步瞭解Campaing Standard API。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea78c0d4bc338eed81a4e0cd39dfdd76837aeb2c

---


# 關於 Campaign Standard API {#about-campaign-standard-apis}

Campaign Standard API的目的是讓您 **建立Adobe Campaign** Standard的整合，並將Adobe Campaign Standard與您使用的技術面板結合，以建立 **您自己的生態系統** 。

透過Adobe Campaign Standard API，您可以存取下列各節所述的各種功能：

<table>
<tr>
    <td valign="top">
        <a href="../../api/using/retrieving-profiles.md"><img alt="條件" src="assets/icon_profile.png"/></a>
        <div><a href="../../api/using/retrieving-profiles.md"><strong>設定檔</strong></a></div>
        <em>瞭解如何從資料庫與描述檔互動。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img alt="條件" src="assets/icon_services.png"/></a>
        <div><a href="../../api/using/creating-a-service.md"><strong>服務與訂閱</strong></a></div>
        <em>瞭解如何從資料庫與服務互動並管理訂閱。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img alt="條件" src="assets/icon_customresources.png"/></a>
        <div><a href="../../api/using/interacting-with-custom-resources.md"><strong>自訂資源</strong></a></div>
        <em>瞭解如何從資料庫與自訂資源互動。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img alt="條件" src="assets/icon_marketinghistory.png"/></a>
        <div><a href="../../api/using/interacting-with-marketing-history.md"><strong>行銷歷史</strong></a></div>
        <em>瞭解如何與個人檔案的行銷記錄互動。</em>
    </td>
</tr>
<tr>
    <td valign="top">
        <a href="../../api/using/creating-a-privacy-request.md"><img alt="條件" src="assets/icon_privacy.png"/></a>
        <div><a href="../../api/using/creating-a-privacy-request.md"><strong>隱私權</strong></a></div>
        <em>進一步瞭解隱私權管理。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/managing-transactional-messages.md"><img alt="條件" src="assets/icon_transactionalmessage.png"/></a>
        <div><a href="../../api/using/managing-transactional-messages.md"><strong>交易式訊息</strong></a></div>
        <em>瞭解如何傳送交易事件。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/controlling-a-workflow.md"><img alt="條件" src="assets/icon_workflows.png"/></a>
        <div><a href="../../api/using/controlling-a-workflow.md"><strong>工作流程</strong></a></div>
        <em>瞭解如何控制和觸發工作流程。</em>
    </td>
    <td valign="top">
        <a href="../../api/using/retrieving-an-organizational-unit.md"><img alt="條件" src="assets/icon_units.png"/></a>
        <div><a href="../../api/using/retrieving-an-organizational-unit.md"><strong>組織和地理單位</strong></a></div>
        <em>瞭解如何與組織單位和地理單位互動。</em>
    </td>
</tr>
</table>

若要使用Campaign Standard API，您需要Adobe I/O帳戶。 這是前進並探索API功能的必備第一步。
如需詳細資訊，請參閱[本小節](../../api/using/setting-up-api-access.md)。

我們提供的API使用 **標準概念** ，以及REST介面和JSON負載。

本檔案中詳盡說明了所有端點，其中包含您應瞭解的控制API的一般概念、程式碼範例和快速入門手冊。 所有範例都可與Postman搭配使用，但您可以自由使用您最愛的REST用戶端。

>[!CAUTION]
>
>在執行API呼叫前，請檢查與您的授權合約相應的比例限制。 有關詳細資訊，請參見[此頁面](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)。
