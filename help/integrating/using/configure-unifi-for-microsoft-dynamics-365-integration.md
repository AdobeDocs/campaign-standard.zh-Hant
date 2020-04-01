---
title: 針對Microsoft Dynamics 365整合設定Unifi
description: 瞭解如何設定Unifi for Microsoft Dynamics 365整合
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---



# 針對Microsoft Dynamics 365整合設定Unifi

設定Unifi以設定並啟動Microsoft Dynamics 365 - Adobe Campaign整合。

## 必要條件

在執行本文中的布建後步驟之前，我們假設您已成功完成Campaign [和Dynamics 365的布建](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) 後步驟 [](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。  如果未發生此情況，則您需要依照這些步驟完成Campaign Standard和Dynamics 365後置備。

您也假設您已與Unifi連絡，已為您建立Unifi帳戶，並已成功登入。  如果未發生此情況，請依照本文所述的 [步驟](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。

>[!CAUTION]
>
>強烈建議您在設定Unifi時與Unifi和／或Adobe諮詢（請連絡您的Adobe CSM）合作。

## 設定促銷活動整合

在您的第一個連線中，按一下 **[!UICONTROL Adobe Campaign Standard]** 以輸入您的促銷活動認證。

這些認證大多來自您在Campaign Standard設定步驟期間在Adobe I/O Console中建立 [的整合](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)。

>[!NOTE]
>
>為確保安全性和隱私性，在重新造訪這些設定畫面時，敏感性認證欄位會顯示為空白。

1. 若為Adobe驗證URL，請輸入 `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. 輸入您 **[!UICONTROL Adobe IO Organization ID]** 和您的 **[!UICONTROL Adobe IO Integration ID]**。

若要取得您的Adobe IO組織與整合ID，請導覽至「Adobe I/O Console Integration Over」畫面並記下網頁URL。

它應該看起來像這樣： `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`中，組織ID和Int ID是數字。

1. 輸入您的 **[!UICONTROL Tenant ID]**

若要取得您的租用戶ID，請依照下列步驟進行：

1. 導覽至 [Adobe Admin Console](https://adminconsole.adobe.com/) ，然後從右上角下拉式選單中選取您的IMS組織。
1. 選擇您的Adobe Campaign Standard產品，然後選擇您的Campaign Standard例項（如果您有多個例項）。  這會顯示產品設定檔清單。

   產品描述檔說明通常會以下列其中一種格式顯示，其 `<tenantID>` 中是您例項的租用戶ID。

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>如果您在識別您的租用戶ID時遇到問題，請聯絡您> Adobe技術聯絡人或Adobe客戶服務。
>
>合作夥伴執行個體租用戶ID通常會遵循 `https://<tenantId>`模式，其 `tenantId` 中 `tbd.campaign-sandbox.adobe.com`為。

1. 輸入您的 **[!UICONTROL Campaign Instance ID]**。

若要取得您的例項ID，請遵循下列步驟：

    1. 在Web瀏覽器中輸入「https://&lt;acs-instance-url>/r/test」，將「&lt;acs-instance-url>」取代為Campaign Standard例項的URL。
    1. 回應將包含「instance=」，後面接著執行個體ID。

1. 選取促銷活動例項的地區。

1. 您可以留空 **[!UICONTROL Base Directory]** 白。

1. 選擇選 **[!UICONTROL Allow as Output Destination]** 項。

在設定參數後，按一下並 **[!UICONTROL CONNECT]** 檢查連線是否成功。

否則，按一下並 **[!UICONTROL CLOSE]** 檢查參數。

>[!NOTE]
>
>如果您無法完成此步驟，請聯絡 [Unifi客戶服務](mailto:support@unifisoftware.atlassian.net)。

## 設定Dynamics 365整合

按一下「Microsoft Dynamics CRM」以設定Dynamics 365憑證。 這些認證大多來自您在Microsoft Dynamics 365設定步驟期間在Microsoft Dynamics 365中建立的整合。

>[!NOTE]
>
>為確保安全性和隱私性，在重新造訪這些設定畫面時，敏感性認證欄位會顯示為空白。

1. 對 **[!UICONTROL URL]**&#x200B;於，請輸入Dynamics 365例項的URL，小心在&quot;。crm&quot;之前插入&quot;。api&quot;(例如 `https://mydynamicsinstance.api.crm.dynamics.com`)

1. 對於 **[!UICONTROL clientid]**，您將使用建立應用程式註冊時產生的應用程式ID來設 [定Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

1. 對於 **[!UICONTROL clientsecret]**，您將在設定Dynamics 365時，將用戶端密碼新增至應用程式註冊時產生的 [用戶端密碼](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

1. 對於 **[!UICONTROL callbackurl]**，添加 `http://localhost:33333`。

1. 留 **[!UICONTROL refresh token]**&#x200B;空。

1. 對 **[!UICONTROL於租用戶ID]**，請使用您從portal.azure.com取得的租用戶ID來設定 [Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

1. 最後，請勾選方塊 **[!UICONTROL Allow as Output Destination]**。

輸入參數後，按一下並檢 **[!UICONTROL CONNECT]** 查連接是否成功。

否則，按一下並 **[!UICONTROL CLOSE]** 檢查參數。

>[!NOTE]
>
>如果您無法完成此步驟，請聯絡 [Unifi客戶服務](mailto:support@unifisoftware.atlassian.net)。

## 完成Unifi設定

設定認證後，您必須通知Unifi，因為您必須先執行一些其他步驟，才能完成整合設定。  請連絡提供給您的Unifi連絡資訊，以指出您已設定認證。

您必須選取選擇退出選項，並在完成時通知Unifi（指出正在選取選擇退出選項的Unifi）。  如需退出選項的說明，請參閱 [Unifi使用指南](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn)。

Unifi完成工作後，他們會通知您並提供進一步資訊，協助您設定Unifi例項、執行一次資料入口，然後在成功完成後，您就可以啟用排程。

針對各種使用案例，建議使用下列頻率：

* 入口：每15分鐘
* 出口：每15分鐘
* 刪除：每天
* 退出：每天

>[!NOTE]
>
>依預設，會從匯出工作中篩選出SEND行銷事件。  如果您想在Dynamics 365中查看SEND行銷事件，則需要修改Unifi中出口工作的篩選（步驟5）。

Unifi中有兩個不同的角色，一個所有者用戶和一個只讀分析用戶。 擁有者使用者可修改工作和排程，唯讀分析師則不能。  給定客戶實例只能有一個擁有者用戶。  如果客戶需要變更指派為擁有者使用者的個人，他們可以傳送電子郵件至 [adobe-support@unifisoftware.com](mailto:adobe-support@unifisoftware.com)，並加入要求的變更。

Unifi組態、工作詳細資訊、設定和監控會顯示在以下影片中。

## Unifi Jobs

### Unifi工作概觀

>[!VIDEO](https://video.tv.adobe.com/v/27392)

此影片說明Adobe Campaign Standard與Microsoft Dynamics 365整合所需的不同Unifi工作（02:10分鐘）

### Unifi工作詳細資訊：入口與出口

>[!VIDEO](https://video.tv.adobe.com/v/27396)

此視訊說明Unifi中的入口和出口作業（04:27分鐘）

### 操作化和監控

>[!VIDEO](https://video.tv.adobe.com/v/27391)

此影片說明工作流程和排程（03:03分鐘）

更像這樣
* [使用Adobe Campaign Standard - Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [設定Microsoft Dynamics 365以進行促銷活動整合](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [設定Adobe IO for Microsoft Dynamics 365 - Campaign Standard整合](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Microsoft Dynamics 365整合功能頁面](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)