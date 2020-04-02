---
title: 請求並設定Microsoft Dynamics 365與Campaign Standard整合
description: 瞭解如何透過Campaign Standard整合來請求及設定Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4dd1ada05b6681a4e2f7676b177747bdfb0e9bff

---


# 請求整合Campaign Standard的Microsoft Dynamics 365

若要布建此整合，您必須遵循下列步驟。

請注意，此整合使用協力廠商供應商Unifi。  若您要求支援協助，Adobe可能必須與Unifi分享您的Adobe Campaign實例資訊。

請依照下面的流程圖和流程圖詳細資訊要求並設定整合。

![](assets/provisioning-wf.png)

流程圖詳細資訊（映射至上述步驟）:

1. 您必須已布建Campaign Standard和Microsoft Dynamics 365，並擁有管理員存取權，才能開始實施此整合。

1. 閱讀本文章，檢查注意事項和設定步驟。

1. 傳送帳戶要求至adobe-support@unifisoftware.com;Unifi在您要求帳戶時，將需要下列資訊：
   * 用戶名
   * 用戶姓氏
   * 使用者電子郵件
   * 公司名稱
   * 地區（北美、歐洲、中東和非洲或亞太地區）
   * 使用類型： 客戶類型（在此整合中使用其生產資料的客戶使用者）或合作夥伴類型（測試整合以取得更深入的瞭解，以協助其Campaign客戶的合作夥伴顧問）或內部類型（測試整合以深入瞭解解決方案的Adobe內部使用者）
   * Campaign Standard資料狀態（從乾淨的資料庫開始或將現有資料整合）
   * 促銷活動租用戶ID（請參閱「設定促銷活動整合」步驟3以取得您的租用戶ID）
   * 促銷活動例項URL
   Unifi預期回應時間：在美國正常營業時間（太平洋時間週一至週五上午9點至下午5點，節假日除外）內需要1小時。

1. 針對Microsoft Dynamics 365和Campaign Standard的完整布建後步驟。
此外，請提交票證給Adobe客戶服務（直接或透過您的Adobe聯絡人），以便在您的Campaign實例中啟用單一登入功能標幟。 合作夥伴應聯絡其Adobe合作夥伴沙盒代表，而不是聯絡Adobe客戶服務，以啟用功能標幟。
如果您計畫將Campaign中的現有資料併入整合中，請遵循「現有促銷活動資料」中的指引，並在繼續之前與Adobe技術聯絡人密切諮詢。

1. 在Unifi中，導覽至Unifi、按一下登入畫面、填寫Dynamics 365和Campaign Standard帳戶認證，並在完成時通知Unifi，以完成初始登入步驟。

1. Unifi會要求客戶進行所需的退出設定和退出屬性對應。

1. 客戶會指出選取的退出設定和退出屬性對應。
Unifi預期回應時間：1個工作日（週一至週五，節假日除外）

1. 配置Unifi涉及查看OOTB映射、篩選器、作業等。 如有需要，進行修改。  如需詳細資訊，請參閱Unifi使用指南。
此步驟涉及設定Unifi調度的運行頻率
* 在Unifi的調度螢幕中設定調度的運行頻率；但是，對於「入口」和「出口」計畫，請在設定計畫頻率之前手動運行一次
* 建議使用下列排程頻率：入口（15分鐘）、出口（15分鐘）、刪除（一天一次）、退出（一天一次）

**在設定Unifi時，建議您與Unifi和／或Adobe諮詢（連絡您的Adobe客戶團隊）合作。**

若要啟用Adobe Campaign Standard和Microsoft Dynamics 365之間的整合，客戶必須如本檔案所述，與協力廠商供應商Unifi建立使用者帳戶。   作為Unifi系統的最終用戶，對於客戶在Unifi系統內發起的與資料請求相關的任何查詢，客戶應與Unifi聯繫。

## 設定此整合

需要為此整合配置三個系統：Adobe Campaign Standard、Microsoft Dynamics 365 for Sales和Unifi。 設定文章會連結在下方。

>[!CAUTION]
>
>對於每個系統，這些步驟都需由管理員執行。
>
>下列文章中的步驟將引導您建立整合／註冊，其中涉及指派權限和／或管理存取權。  您有責任確保這些步驟在執行前符合您的公司政策，並謹慎執行。

在ADOBE CAMPAIGN中，您必須設定API存取權，並設定Unifi的新整合。 若要達成此目的，請參 [閱本文](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)。

在MICROSOFT DYNAMICS 365中，您需要建立新的應用程式註冊，並讓應用程式使用者能夠使用整合。  若要針對此整合設定Microsoft Dynamics 365，請參閱 [本文](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)。

在UNIFI中，您需要設定整合併設定對應或新增自訂屬性。 若要為此整合設定Unifi，請參 [閱本文](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)。

## 要求支援

如果您遇到問題，請聯絡Unifi客戶支援： [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net)。

Unifi預期回應時間：在美國正常營業時間（太平洋時間週一至週五上午9點至下午5點，節假日除外）內工作4小時。

>[!CAUTION]
>
>若您要求支援協助，Adobe可能必須與Unifi分享您的Adobe Campaign實例資訊。