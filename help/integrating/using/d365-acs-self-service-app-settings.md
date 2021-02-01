---
title: 設定Campaign-Dynamics整合應用程式
description: 瞭解如何設定Campaign-Dynamics整合應用程式
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 2%

---


# 將系統與整合應用程式連接

## 新增認證至整合應用程式

**[!UICONTROL Settings]**&#x200B;螢幕可讓您指定Microsoft Dynamics 365和Adobe API憑證。 您也可以設定與Adobe Campaign SFTP例項相關的設定。

### Microsoft Dynamics 365認證

Microsoft Dynamics 365憑證可授予整合應用程式從Microsoft Dynamics 365提取資料的權限。  您必須先依照畫面[「設定Microsoft Dynamics 365 for Campaign整合](../../integrating/using/d365-acs-configure-d365.md)」中的步驟進行，才能產生將貼至此畫面的值。 以下說明的輸入將參照此畫面。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:在本節中瞭解如何參考您的用 [戶端ID](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:在本節中瞭解如何產生您的用戶 [端密碼](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:瞭解如何在本節中尋找您的租 [用戶ID](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:網址的格式為「https://&lt;servername>.api.crm.dynamics.com/」

### Adobe API認證

Adobe Campaign認證是使用[Adobe I/O](https://www.adobe.io/)產生。 您必須造訪畫面[「設定Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)」，然後依照指示進行，才能填寫本節的輸入。

下圖將詳細說明Adobe I/O與設定畫面輸入之間的對應。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *私密金鑰*:定義此項的程式會從按一下「產生公用／私用鑰匙對」按鈕開始。這將建立您必須下載的zip檔案。 下載後，請解壓縮檔案，以產生兩個名為certificate_pub.crt和private.key的檔案。 請務必將private.key放在安全的位置，而不要共用它。 在文本編輯器中開啟private.key檔案。 在文字編輯器中複製整個值（在PC上為ctrl-A然後為ctrl-C，在Mac上為cmd-A然後為cmd-C）。 這應包括完整的「BEGIN PRIVATE KEY」和「END PRIVATE KEY」行。 將此整個多行文字貼入「設定」畫面的「私密金鑰」輸入。

* *URL*:此值將符合模式https\://mc.adobe.io/&lt;campaign-instance-name>。整合應用程式的頁首包含「組織」和「例項」。 URL的「campaign-instance-name」部分只是在此例項值中找到的名稱。

## Adobe Campaign SFTP設定{#ac-smtp-settings}

這些設定是選擇性的。 如果您打算使用Adobe Campaign SFTP例項從連接器輸出記錄檔，則需要定義它們。 如果您在整合執行時遇到問題，而且需要除錯輸出為何不符合您的期望，這將很有幫助。

設定SFTP伺服器的另一個原因是，如果您打算執行選擇加入／退出工作流程，而且有資料從Adobe Campaign流向Microsoft Dynamics 365（**[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**&#x200B;或&#x200B;**[!UICONTROL Bidirectional]**）。

>[!IMPORTANT]
>
>您需負責從SFTP資料夾存取和下載的資訊。 如果資訊包含個人資料，您有責任遵守任何適用的隱私權法律和法規。 [進一步瞭解](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。


若要定義Microsoft Dynamics 365整合的促銷活動SFTP設定，請存取下列區段：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您需要指定：

* **SFTP主機**:此欄位將包 &lt;campaign-instance-name>含。campaign.adobe.com。整合應用程式的標題同時包含&#x200B;**Org**&#x200B;和&#x200B;**Instance**。 URL的「campaign-instance-name」部分只是在此例項值中找到的名稱。

* **SFTP使用者**:如果您有SFTP使用者，請將其新增至此處。否則，請參閱[本節](#ac-control-panel-settings)。 在程式中，將顯示用戶名。

* **SFTP金鑰**:如果您有SSH密鑰，請將其添加到此處。否則，請參閱[本節](#ac-control-panel-settings)。

* 您的Adobe Campaign SFTP設定中需要包含&#x200B;**IP範圍**。 必須允許列出這些項目，以便整合使用SFTP端點。

* **您要將記錄檔匯出至您的Adobe Campaign SFTP嗎？** 允許您確定整合是否將日誌資訊輸出到SFTP端點。如果Adobe Campaign或Microsoft Dynamics 365未顯示您預期的資訊，此功能可用於協助除錯。

## Adobe Campaign {#ac-control-panel-settings}中的SFTP設定

在下列區段中探索使用[促銷活動控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant)進行SFTP管理：

* [關於 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [SFTP 儲存空間管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [新增IP範圍](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [管理金鑰](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [登入您的SFTP伺服器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

完成配置後，使用私鑰登錄到SFTP伺服器並建立目錄&quot;d365_loads/exports&quot;。

[請造訪本](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) 頁，以取得有關Adobe Campaign Standard SFTP伺服器的資訊。
