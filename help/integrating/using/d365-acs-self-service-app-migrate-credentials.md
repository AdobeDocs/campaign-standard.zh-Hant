---
title: 設定Campaign-Dynamics整合應用程式
description: 瞭解如何設定Campaign-Dynamics整合應用程式
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
source-git-commit: 736e8b7e863409779c153567f6e5fc577ac3c519
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# 將憑證從JWT移轉至OAuth伺服器對伺服器

服務帳戶(JWT)認證已遭取代，以支援新的OAuth伺服器對伺服器認證。 新的認證可讓您更輕鬆地維護Adobe應用程式。 它也能移除定期旋轉憑證的需求，並使用標準OAuth2程式庫立即運作。

雖然服務帳戶(JWT)憑證已標示為已棄用，但它們仍會繼續運作，直到2025年1月1日。 因此，您必須在2025年1月1日之前移轉整合，才能使用新的OAuth伺服器對伺服器認證。 請檢查 [淘汰時間表](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#deperecation-timelines) 以取得詳細資訊

## 將認證從JWT移轉至OAuth伺服器對伺服器的步驟

移轉至OAuth伺服器對伺服器認證是一個簡單的程式，可為您的應用程式啟用零停機移轉。 您可以依照下列步驟移轉認證。

1. 登入 [Adobe Developer Console](https://developer.adobe.com/console)
2. 從左側的篩選功能表中，選取具有服務帳戶(JWT)認證選項。 這樣會顯示所有具有服務帳戶(JWT)認證的專案。 從專案清單中，按一下您要移轉的專案。

   ![](assets/JwtToOAuthMigration1.png)

3. 從左側導覽開啟「服務帳戶(JWT)」認證標籤，並檢視移轉卡。 在移轉卡上，按一下按鈕 **新增認證** 以新增同等的OAuth伺服器對伺服器認證。 將OAuth伺服器對伺服器認證新增至您的專案將會開始移轉。
   ![](assets/JwtToOAuthMigration2.png)
4. 新認證 **OAuth伺服器對伺服器** 將會新增至左側導覽。
   * 如果您要取消移轉，請按一下取消移轉。
   * 在驗證新認證OAuth伺服器對伺服器是否正常運作之前，請勿按一下「檢閱並刪除」按鈕。
     ![](assets/JwtToOAuthMigration3.png)

5. 將Microsoft Dynamics 365中的認證更新至Adobe Campaign Standard應用程式
   * 登入整合應用程式，並導覽至「設定」頁面。
   * 選取OAuth作為驗證型別。
   * 由於新的OAuth伺服器對伺服器認證使用與舊服務帳戶(JWT)認證相同的認證，因此大部分欄位都將已填入。
   * 輸入使用者端ID和使用者端密碼。 您可以在Adobe Developer Console的專案中找到這些專案。
   * 按一下「儲存」以儲存設定。
     ![](assets/JwtToOAuthMigration4.png)

6. 驗證新認證是否有效
   * 登入整合應用程式，並導覽至工作流程頁面。
   * 停止作用中的工作流程。 等到工作流程停止為止。
   * 開始工作流程。 等到工作流程處於執行中狀態。
   * 監視工作流程幾分鐘，確保工作流程正常運作。 您也可以檢查Adobe Campaign Standard和Microsoft Dynamics 365中的資料，確保資料正確同步。

7. 刪除JWT認證以完成移轉
   * 登入 [Adobe Developer Console](https://developer.adobe.com/console)
   * 按一下專案，然後選取您移轉的專案。
   * 從左側導覽按一下「服務帳戶(JWT)」認證標籤。
   * 按一下檢閱和刪除按鈕。
     ![](assets/JwtToOAuthMigration5.png)
   * 檢閱上次存取或上次使用功能表的時間戳記，以確認整合應用程式是使用新的OAuth認證產生存取權杖，還是仍使用舊的JWT認證。
     ![](assets/JwtToOAuthMigration6.png)
   * 在確認整合應用程式使用新的OAuth憑證且不再使用JWT憑證後，按一下 **確認並繼續** 按鈕完成移轉。
     ![](assets/JwtToOAuthMigration7.png)
