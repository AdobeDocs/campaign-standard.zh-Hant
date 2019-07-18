---
title: 建立多語言電子郵件
seo-title: 建立多語言電子郵件
description: 建立多語言電子郵件
seo-description: 請依照下列步驟，針對使用不同慣用語言的收件者建立多語言電子郵件目標。
page-status-flag: 從未啓動
uuid: e90f4ec8-14e3-4304-b5 fc-bce0 ba08 a4 ef
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 頻道
content-type: reference
topic-tags: 電子郵件訊息
discoiquuid: 79231445-1d51-499a-adcf-3c0 f6 db1 cfa3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Creating a multilingual email{#creating-a-multilingual-email}

您可以將多語言電子郵件傳送至使用不同慣用語言的個人檔案：每個描述檔都會以他慣用的語言收到電子郵件變體。

若要這麼做，請檢查您是否有多語言電子郵件範本。If not, learn how to create one in [this section](../../start/using/creating-a-multilingual-template.md).

觀眾是以具有已完成慣用語言資訊的個人檔案為基礎。

1. Create a new email based on a [multilingual template](../../start/using/creating-a-multilingual-template.md).

   ![](assets/multi_create1.png)

1. 定義一般屬性和電子郵件的目標對象，就像標準電子郵件一樣。Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. 在建立精靈的第四個步驟中，定義變體選項。If the [multilingual template](../../start/using/creating-a-multilingual-template.md) already contains all the right parameters, you can directly click on the **[!UICONTROL Create]** button.

   ![](assets/multi_create4.png)

   If needed, add variants using the **[!UICONTROL Add an element]** button. **[!UICONTROL Default]** 變數不能刪除。When set to **[!UICONTROL default]**, [the profile's preferred language](../../audiences/using/creating-profiles.md) is used to choose the variant. You can also set the **[!UICONTROL Default]** variant to any other language.

1. 確認電子郵件建立：隨即顯示電子郵件控制面板。
1. 定義每個變體的電子郵件內容。視您選擇的範本而定，您可以定義數個主題、數個傳送者名稱或數個不同的內容。使用下拉式選單可在元素的不同變體之間導覽。For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/multi_selectcontent.png)

1. 測試並驗證您的訊息。Refer to the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. Schedule the send with the **[!UICONTROL Send after confirmation option]**.
1. 傳送電子郵件後，您可以存取其記錄檔和報告以測量促銷活動的成功。For more on reporting, refer to [this section](../../reporting/using/about-dynamic-reports.md).

