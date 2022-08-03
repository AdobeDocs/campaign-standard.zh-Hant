---
title: 開始使用設定檔和對象
description: 定義目標人口、選取對象、篩選收件者、收集資料及更新設定檔。
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: Profiles
role: User
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 開始使用設定檔和對象{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">分段和定向</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">許可和同意</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">隱私合規性</a></p></td></tr>
</table>

Campaign Integrated Customer Profile 可讓您透過單一檢視追蹤所有通道上與客戶的每一次互動，讓您向客戶傳遞相關的個人化訊息。

將您的資料庫細分為受眾，以最佳化行銷活動的目標。

使用服務和登陸頁面，管理客戶權限和同意，以便設定簡單的選擇加入和選擇退出機制。

## 分段和定向 {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

在建立市場活動或消息時，您可以通過從市場活動資料庫中的聯繫人中選擇、使用簡單或高級標準或選擇受眾來指定交貨的目標。

使用 **整合客戶配置檔案**。 **自定義段** 和 **控制組**。 當您瞭解客戶、興趣、人口結構和渠道偏好時，建立個性化體驗就更容易被人注意。

Adobe Campaign即時構建豐富的客戶配置檔案，使您能夠隨著客戶偏好的變化提供更相關和個性化的服務。 此外，Adobe Campaign整合了高級分析、資料管理和目標功能，以建立受眾。

**配置檔案** 是儲存在資料庫中的單個聯繫人。 每個配置檔案對應於資料庫中的一個條目，該條目包含要針對、限定和單獨跟蹤該配置檔案的必要資訊：Adobe Campaign可以跟蹤線上和線下渠道的每次交互，並將其合併到單個配置檔案中。

**觀眾** 是基於特定條件或一組條件構建的配置檔案清單。 使用工作流和查詢編輯器，您可以構建市場營銷活動將針對的受眾，具體取決於您對這些受眾的資訊、其活動以及其市場營銷歷史記錄。 這樣，您就可以按無限數量的標準篩選訂閱的配置檔案、示例或建立目標受眾。

閱讀全文:

* [關於設定檔](../../audiences/using/about-profiles.md)
* [使用中的設定檔案](../../audiences/using/active-profiles.md)
* [管理測試設定檔](../../audiences/using/managing-test-profiles.md)
* [充實 Campaign 資料庫](../../audiences/using/enriching-campaign-database.md)
* [關於對象](../../audiences/using/about-audiences.md)
* [在訊息中選取對象](../../audiences/using/selecting-an-audience-in-a-message.md)
* [新增控制組](../../sending/using/control-group.md)

## 許可和同意 {#permission}

<img src="assets/do-not-localize/icon_permission.svg"  width="60px">

在開始向聯繫人發送消息之前，您需要確保您獲得他們的權限。 否則，您的電子郵件可能會被標籤為垃圾郵件，這將影響您的平台交付能力。 要確保構建健康的配置檔案資料庫，請首先保護此權限。

對於活動，我們建議您使用 **易於選擇加入和選擇退出機制** 通 [服務](../../audiences/using/creating-a-service.md), [登錄頁](../../channels/using/getting-started-with-landing-pages.md) 更新您的聯繫資訊並增大資料庫。

提供 **取消訂閱連結** 在您的郵件中，配置檔案將在需要時添加到denylist中，從而提高您的平台交付能力。 有關denylist管理的詳細資訊，請參閱 [關於選擇加入和選擇退出活動](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)。

>[!IMPORTANT]
>
>你必須尊重 [Adobe Campaign可接受使用政策](https://www.adobe.com/legal/terms/aup.html)。

閱讀全文:

* [關於訂閱](../../audiences/using/about-subscriptions.md)
* [關於 Campaign 中的選擇加入和選擇退出](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## 隱私合規性 {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaign提供一套工具，幫助您 **隱私合規性** GDPR 、 CCPA和其他隱私法。

瞭解更多資訊 [這篇文章](https://helpx.adobe.com/tw/campaign/kb/campaign-privacy.html) 關於隱私管理以及我們為管理訪問權、忘記權、同意權、資料保留和用戶角色而提供的功能。

活動中的隱私和同意以及如何管理這些隱私和同意 [此部分](../../start/using/privacy.md)。 您還將找到最佳實踐，幫助您在使用我們的服務時遵守隱私保護法規。

## 額外資源

* [將 Adobe Experience Platform 對象內嵌至 Campaign](../../integrating/using/ingest-aep-data.md)
* [使用Microsoft動力365](../../integrating/using/d365-acs-get-started.md)
* [Adobe共用受眾](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [使用工作流導入配置檔案](../../automating/using/creating-import-workflow-templates.md)
* [個人資料和觀眾視頻](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html)
