---
title: 設定Campaign-Dynamics整合應用程式
description: 了解如何設定Campaign-Dynamics整合應用程式
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: f75df49e7957437df72c814aa9055d34770f22d6
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 4%

---

# 連結系統與整合應用程式

## 將憑證新增至整合應用程式

此 **[!UICONTROL Settings]** 螢幕可讓您指定Microsoft Dynamics 365和AdobeAPI憑證。 您也可以配置與Adobe Campaign SFTP例項相關的設定。

### Microsoft Dynamics 365憑證

Microsoft Dynamics 365憑證提供整合應用程式權限，可從Microsoft Dynamics 365中提取資料。  您必須先依照畫面上的步驟操作 [設定Microsoft Dynamics 365以進行Campaign整合](../../integrating/using/d365-acs-configure-d365.md) 來產生要貼上至此畫面的值。 下面描述的輸入將參考此螢幕。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:了解如何在 [本節](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:了解如何在 [本節](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:了解如何在 [本節](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:URL會有格式 `https://&lt;servername&gt;.api.crm.dynamics.com/`

### AdobeAPI憑證

Adobe Campaign憑證是使用 [Adobe I/O](https://www.adobe.io/). 您需要瀏覽畫面 [配置Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) 並先依照這些指示操作，您才能填寫本節中的輸入內容。

下圖將詳細說明Adobe I/O與設定畫面輸入之間的對應。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *私密金鑰*:定義此項的程式會從按一下「產生公開/私用金鑰組」按鈕開始。 這會建立您必須下載的zip檔案。 下載後，將檔案解壓縮，這會產生兩個檔案，名為certificate_pub.crt和private.key。 請務必將private.key放在安全位置，但請勿共用。 在文字編輯器中開啟private.key檔案。 在文字編輯器中複製整個值(在PC上按住ctrl-A然後按住ctrl-C，在Mac上按住cmd-A然後按住cmd-C)。 這應包括整個包含「BEGIN PRIVATE KEY」和「END PRIVATE KEY」的行。 將此整份多行文字貼入「設定」畫面的「私密金鑰」輸入。

* *URL*:此值將符合以下模式： https\://mc.adobe.io/&lt;campaign-instance-name>. 整合應用程式的標題同時包含「組織」和「例項」。 url的「campaign-instance-name」部分將只是此執行個體值中找到的名稱。

## Adobe Campaign SFTP設定 {#ac-smtp-settings}

這些設定為選用。 如果您打算使用Adobe Campaign SFTP例項從連接器輸出記錄檔，則需要定義這些記錄檔。 如果您在整合執行時遇到問題，且需要針對輸出不符合您期望的原因進行除錯，此功能將有所幫助。

設定SFTP伺服器的另一個原因是，如果您打算執行選擇加入/退出工作流程，且有資料從Adobe Campaign流向Microsoft Dynamics 365，可能 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** 或 **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>您需負責從SFTP資料夾存取和下載的資訊。 如果資訊包含個人資料，您需負責遵守任何適用的隱私權法律和法規。 [深入瞭解](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。

若要定義Microsoft Dynamics 365整合的Campaign SFTP設定，請存取下列區段：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您需要指定：

* **SFTP主機**:此欄位將包含 &lt;campaign-instance-name>.campaign.adobe.com。 整合應用程式的標題包含 **組織** 和 **例項**. url的「campaign-instance-name」部分將只是此執行個體值中找到的名稱。

* **SFTP使用者**:如果您有SFTP使用者，請在此處新增。 否則，請參閱 [本節](#ac-control-panel-settings). 在程式中，會顯示使用者名稱。

* **SFTP金鑰**:如果您有SSH金鑰，請在此處新增。 否則，請參閱 [本節](#ac-control-panel-settings).

* 此 **IP範圍** 需要包含在您的Adobe Campaign SFTP設定中。 必須允許列出這些項目，整合才能使用SFTP端點。

* 此 **是否要將記錄檔匯出至您的Adobe Campaign SFTP?** 可讓您判斷整合是否會將記錄資訊輸出至SFTP端點。 如果Adobe Campaign或Microsoft Dynamics 365未顯示您預期的資訊，此功能可協助進行除錯。

## Adobe Campaign中的SFTP設定 {#ac-control-panel-settings}

探索SFTP管理，使用 [Campaign控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant) 在以下幾節中：

* [關於 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=zh-Hant#sftp-management)

* [SFTP 儲存空間管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [新增IP範圍](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [管理金鑰](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [登入您的SFTP伺服器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

完成設定後，使用私密金鑰登入SFTP伺服器並建立「d365_loads/exports」目錄。

[請造訪此頁面](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) 以取得Adobe Campaign Standard SFTP伺服器的相關資訊。
