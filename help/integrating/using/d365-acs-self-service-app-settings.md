---
title: 設定Campaign-Dynamics整合應用程式
description: 瞭解如何設定Campaign-Dynamics整合應用程式
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# 連結系統與整合應用程式

## 將認證新增至整合應用程式

此 **[!UICONTROL Settings]** 畫面可讓您指定Microsoft Dynamics 365和Adobe API認證。 您也可以設定與Adobe Campaign SFTP執行個體相關的設定。

### Microsoft Dynamics 365認證

Microsoft Dynamics 365憑證會授予整合應用程式許可權，讓您從Microsoft Dynamics 365提取資料。  您必須先依照畫面上的步驟操作 [設定Microsoft Dynamics 365以進行Campaign整合](../../integrating/using/d365-acs-configure-d365.md) 以產生將貼入此熒幕的值。 以下說明的輸入將參考此畫面。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**：瞭解如何在中參照您的使用者端ID [本節](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**：瞭解如何在中產生您的使用者端密碼 [本節](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**：瞭解如何在中尋找您的租使用者ID [本節](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**：URL的格式將為 `https://&lt;servername&gt;.api.crm.dynamics.com/`

### AdobeAPI認證

Adobe Campaign認證產生方式： [Adobe I/O](https://www.adobe.io/). 您必須造訪畫面 [設定Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) 並依照這裡的指示操作，您才能填寫本節中的輸入內容。

* 選取「驗證型別」作為Oauth，因為不建議使用JWT型驗證。
* 下圖將詳細說明Adobe I/O與設定畫面輸入之間的對應。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *URL*：此值將符合模式https\：//mc.adobe.io/&lt;campaign-instance-name>. 整合應用程式的標頭同時包含「組織」和「例項」。 URL的「campaign-instance-name」部分只是此執行個體值中的名稱。

## Adobe Campaign SFTP設定 {#ac-smtp-settings}

這些設定是選用的。 如果您打算使用Adobe Campaign SFTP執行個體從聯結器輸出記錄檔，則需要定義記錄檔。 如果您在整合執行時遇到問題，而您需要針對輸出不符合您期望的原因進行偵錯，這會很有幫助。

設定SFTP伺服器的另一個原因是如果您打算執行選擇加入/退出工作流程，而且有資料從Adobe Campaign流入Microsoft Dynamics 365，可能是 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** 或 **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>您需負責存取和下載SFTP資料夾中的資訊。 如果資訊包含個人資料，您有責任遵守任何適用的隱私權法規。 [了解更多](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。
>

若要為Microsoft Dynamics 365整合定義Campaign SFTP設定，請存取下列章節：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您必須指定：

* **SFTP主機**：此欄位將包含 &lt;campaign-instance-name>.campaign.adobe.com. 整合應用程式的標頭同時包含 **組織** 和 **例項**. URL的「campaign-instance-name」部分只是此執行個體值中的名稱。

* **SFTP使用者**：如果您有SFTP使用者，請在這裡新增該使用者。 否則，請參閱 [本節](#ac-control-panel-settings). 在程式中，您將會看到使用者名稱。

* **sftp金鑰**：如果您有SSH金鑰，請在此處新增。 否則，請參閱 [本節](#ac-control-panel-settings).

* 此 **IP範圍** 需要包含在您的Adobe Campaign SFTP設定中。 這些需要加入允許清單，整合才能使用SFTP端點。

* 此 **您是否要將記錄檔匯出至Adobe Campaign SFTP？** 可讓您確定整合是否會將記錄資訊輸出至SFTP端點。 如果Adobe Campaign或Microsoft Dynamics 365未顯示您預期的資訊，可使用此協助進行偵錯。

## Adobe Campaign中的SFTP設定 {#ac-control-panel-settings}

透過探索SFTP管理 [Campaign控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant) 在以下小節中：

* [關於 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=zh-Hant#sftp-management)

* [SFTP 儲存空間管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [新增IP範圍](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management)

* [管理金鑰](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [登入您的SFTP伺服器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

完成設定後，請使用私密金鑰登入SFTP伺服器並建立「d365_loads/exports」目錄。

[造訪此頁面](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=zh-Hant) 以取得Adobe Campaign Standard SFTP伺服器的相關資訊。
