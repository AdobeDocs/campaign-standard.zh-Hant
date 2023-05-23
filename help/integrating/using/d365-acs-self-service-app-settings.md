---
title: 配置Campaign-Dynamics整合應用
description: 瞭解如何配置Campaign-Dynamics整合應用
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 3%

---

# 連結系統與整合應用程式

## 向整合應用添加憑據

的 **[!UICONTROL Settings]** 螢幕允許您指定MicrosoftDynamics 365和AdobeAPI憑據。 您還可以配置與Adobe CampaignSFTP實例相關的設定。

### MicrosoftDynamics 365憑據

MicrosoftDynamics 365憑據授予整合應用程式從MicrosoftDynamics 365中提取資料的權限。  必須首先執行螢幕上的步驟 [配置MicrosoftDynamics 365以進行市場活動整合](../../integrating/using/d365-acs-configure-d365.md) 以生成將貼上到此螢幕中的值。 下面描述的輸入將引用此螢幕。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:瞭解如何在中引用您的客戶端ID [此部分](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:瞭解如何在中生成客戶端密鑰 [此部分](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:瞭解如何在中查找您的租戶ID [此部分](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:URL將具有格式 `https://&lt;servername&gt;.api.crm.dynamics.com/`

### AdobeAPI憑據

Adobe Campaign憑據使用 [Adobe I/O](https://www.adobe.io/)。 您需要訪問螢幕 [配置Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) 並按照此處的說明進行操作，然後才能填寫本部分的輸入。

下圖將詳細說明Adobe I/O和設定螢幕輸入之間的映射。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *私鑰*:要定義此項，請按一下「生成公共/專用密鑰對」按鈕。 這將建立必須下載的zip檔案。 下載後，將解壓檔案，這將導致兩個名為certificate_pub.crt和private.key的檔案。 確保將private.key放在安全位置，不要共用它。 在文本編輯器中開啟private.key檔案。 在文本編輯器中複製整個值(在PC上按ctrl-A然後按ctrl-C，或在Mac上按cmd-A再按cmd-C)。 這應包括整個「BEGIN PRIVATE KEY」和「END PRIVATE KEY」的行。 將此整行多行文本貼上到「設定」螢幕的「私鑰」輸入中。

* *URL*:此值將適合模式https\://mc.adobe.io/&lt;campaign-instance-name>。 整合應用的標題包括「組織」和「實例」。 URL的「campaign-instance-name」部分將只是在此實例值中找到的名稱。

## Adobe CampaignSFTP設定 {#ac-smtp-settings}

這些設定是可選的。 如果計畫使用Adobe CampaignSFTP實例從連接器輸出日誌，則需要定義它們。 如果您在整合運行時遇到問題，並且需要調試為什麼輸出不符合您的期望值，則此操作將非常有用。

設定SFTP伺服器的另一個原因是，如果您計畫運行選擇加入/退出工作流，並且有從Adobe Campaign到MicrosoftDynamics 365的資料流 **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** 或 **[!UICONTROL Bidirectional]**。

>[!IMPORTANT]
>
>您負責從SFTP資料夾訪問和下載的資訊。 如果資訊包含個人資料，您應負責遵守任何適用的隱私法律和法規。 [了解更多](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)。

要為MicrosoftDynamics 365整合定義市場活動SFTP設定，請訪問以下部分：

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

您需要指定：

* **SFTP主機**:此欄位包含 &lt;campaign-instance-name>.campaigment.adobe.com。 整合應用的標題包括 **組織** 和 **實例**。 URL的「campaign-instance-name」部分將只是在此實例值中找到的名稱。

* **SFTP用戶**:如果您有SFTP用戶，請將其添加到此處。 否則，請參閱 [此部分](#ac-control-panel-settings)。 在此過程中，將顯示用戶名。

* **SFTP密鑰**:如果您有SSH密鑰，請在此處添加。 否則，請參閱 [此部分](#ac-control-panel-settings)。

* 的 **IP範圍** 需要包含在您的Adobe CampaignSFTP配置中。 需要列出這些內容，以便整合能夠利用SFTP端點。

* 的 **是否要將日誌導出到您的Adobe CampaignSFTP?** 允許您確定整合是否將日誌資訊輸出到SFTP端點。 如果Adobe Campaign或MicrosoftDynamics 365未顯示您期望的資訊，則此選項可用於幫助調試。

## SFTP在Adobe Campaign的設定 {#ac-control-panel-settings}

使用 [市場活動控制面板](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=zh-Hant) 在以下各節中：

* [關於 SFTP 管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html#sftp-management)

* [SFTP 儲存空間管理](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [添加IP範圍](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management)

* [管理密鑰](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [登錄到SFTP伺服器](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

完成配置後，使用私鑰登錄到SFTP伺服器並建立目錄「d365_loads/exports」。

[訪問此頁](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=zh-Hant) 有關Adobe Campaign StandardSFTP伺服器的資訊。
