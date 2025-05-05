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

**[!UICONTROL Settings]**&#x200B;畫面可讓您指定Microsoft Dynamics 365和AdobeAPI認證。 您也可以設定與Adobe Campaign SFTP執行個體相關的設定。

### Microsoft Dynamics 365認證

Microsoft Dynamics 365憑證會授予整合應用程式許可權，讓您從Microsoft Dynamics 365提取資料。  您必須先依照熒幕[設定Microsoft Dynamics 365以進行Campaign整合](../../integrating/using/d365-acs-configure-d365.md)上的步驟操作，才能產生將貼至此熒幕的值。 以下說明的輸入將參考此畫面。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**：在[本節](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)中瞭解如何參考您的使用者端識別碼

* **[!UICONTROL Client Secret]**：在[本節](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)中瞭解如何產生您的使用者端密碼

* **[!UICONTROL Tenant]**：瞭解如何在[本節](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)中找到您的租使用者ID

* **[!UICONTROL URL]**： URL的格式將為`https://&lt;servername&gt;.api.crm.dynamics.com/`

### AdobeAPI認證

使用[Adobe I/O](https://www.adobe.io/)產生Adobe Campaign認證。 您必須造訪畫面[設定Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)，並依照指示操作，才能填寫本節中的輸入內容。

* 選取「驗證型別」作為Oauth，因為不建議使用JWT型驗證。
* 下圖將詳細說明Adobe I/O與設定畫面輸入之間的對應。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *URL*：此值將符合https\：//mc.adobe.io/&lt;campaign-instance-name>模式。 整合應用程式的標頭同時包含「組織」和「例項」。 URL的「campaign-instance-name」部分只是此執行個體值中的名稱。

## Adobe Campaign SFTP設定 {#ac-smtp-settings}

這些設定是選用的。 如果您打算使用Adobe Campaign SFTP執行個體從聯結器輸出記錄檔，則需要定義記錄檔。 如果您在整合執行時遇到問題，而您需要針對輸出不符合您期望的原因進行偵錯，這會很有幫助。

設定SFTP伺服器的另一個原因是您打算執行選擇加入/退出工作流程，且有資料從Adobe Campaign流入Microsoft Dynamics 365 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;或&#x200B;**[!UICONTROL Bidirectional]**。

>[!IMPORTANT]
>
>您需負責存取和下載SFTP資料夾中的資訊。 如果資訊包含個人資料，您有責任遵守任何適用的隱私權法規。 [了解更多](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。
>

若要為Microsoft Dynamics 365整合定義Campaign SFTP設定，請存取下列章節：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您必須指定：

* **SFTP主機**：此欄位將包含&lt;campaign-instance-name>.campaign.adobe.com。 整合應用程式的標頭同時包含&#x200B;**組織**&#x200B;和&#x200B;**執行個體**。 URL的「campaign-instance-name」部分只是此執行個體值中的名稱。

* **SFTP使用者**：如果您有SFTP使用者，請在這裡新增該使用者。 否則，請參考[本節](#ac-control-panel-settings)。 在程式中，您將會看到使用者名稱。

* **SFTP金鑰**：如果您有SSH金鑰，請在此處新增。 否則，請參考[本節](#ac-control-panel-settings)。

* **IP範圍**&#x200B;必須包含在您的Adobe Campaign SFTP設定中。 這些需要加入允許清單，整合才能使用SFTP端點。

* **您要將記錄檔匯出至Adobe Campaign SFTP嗎？**&#x200B;可讓您判斷整合是否會將記錄資訊輸出至SFTP端點。 如果Adobe Campaign或Microsoft Dynamics 365未顯示您預期的資訊，可使用此協助進行偵錯。

## Adobe Campaign中的SFTP設定 {#ac-control-panel-settings}

在以下章節中探索使用[Campaign控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)進行SFTP管理：

* [關於 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=zh-Hant#sftp-management)

* [SFTP 儲存空間管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=zh-Hant#installing-ssh-key)

* [新增IP範圍](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=zh-Hant#sftp-management)

* [管理金鑰](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=zh-Hant#sftp-management)

* [登入您的SFTP伺服器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=zh-Hant#sftp-management)

完成設定後，請使用私密金鑰登入SFTP伺服器並建立「d365_loads/exports」目錄。

[請造訪此頁面](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=zh-Hant)，瞭解Adobe Campaign Standard SFTP伺服器的相關資訊。
