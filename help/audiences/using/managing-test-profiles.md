---
title: 管理測試設定檔
description: 瞭解如何管理測試設定檔。
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# 管理測試設定檔 {#managing-test-profiles}

## 關於測試設定檔 {#about-test-profiles}

測試設定檔可讓您定位不符合已定義定位准則的其他收件者。 它們會新增至訊息的讀者群，以偵測任何詐用收件者資料庫的行為，或確保電子郵件送達收件匣。

您可以從進階功能表管理您的測試設定檔 **[!UICONTROL Profiles & audiences > Test profiles]**。

測試配置檔案包含虛構的聯繫資訊或由發送者控制的聯繫資訊，這些資訊隨後可用於以下上下文中的消息：

* 傳送校 **樣**:校對是特定訊息，用來在傳送已完成的傳送給收件者之前檢查訊息。 Proof測試設定檔負責檢查傳送的內容和格式。 請參閱 [傳送校樣](../../sending/using/sending-proofs.md)。
* 對於電 **子郵件轉譯**:電子郵件轉換測試配置檔案用於檢查根據接收郵件收件箱顯示郵件的方式。 例如，webmail、message service、mobile等。 請參閱 [電子郵件轉譯](../../sending/using/email-rendering.md)。

   「電 **子郵件** 」轉譯使用為唯讀。 使用此功能的測試設定檔僅能在Adobe Campaign中立即使用。

* 作為陷 **阱**:訊息會傳送至測試描述檔，就像傳送至主要目標一樣。 請參 [閱使用陷阱](../../sending/using/using-traps.md)。
* 要預 **覽消息** :在預覽訊息以測試個人化元素時，可選取測試描述檔。 請參閱 [預覽訊息](/help/sending/using/previewing-messages.md)。

![](assets/test_profile.png)

## 建立測試設定檔 {#creating-test-profiles}

1. 從進階功能表，透過Adobe Campaign標誌，選取「設定檔與觀眾 **>測試設定檔** 」以存取測試設定檔清單。

   ![](assets/test_profile_creation_1.png)

1. 在控制面 **[!UICONTROL Test profiles]** 板中，按一下 **建立**。

   ![](assets/test_profile_creation_2.png)

1. 輸入此配置式的資料。

   ![](assets/test_profile_creation_3.png)

1. 選擇您要用於測試設定檔的用途。

   ![](assets/test_profile_creation_4.png)

1. 輸入聯絡人 **[!UICONTROL Email, Telephone, Mobile, Mobile app]**&#x200B;渠道，以及測試描述檔位址（如有必要）。

   >[!NOTE]
   >
   >您可以定義偏好的電子郵件格式：或 **[!UICONTROL Text]** 者 **[!UICONTROL HTML]**。

1. 如果要使用此測試設定檔來測試交易式訊息的個人化，請指定事件類型和此事件的資料。
1. 按一 **[!UICONTROL Create]** 下以儲存測試設定檔。

然後，測試描述檔會新增至描述檔清單。

**相關主題：**

[建立測試設定檔](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html) 影片

## 編輯測試設定檔 {#editing-test-profiles}

若要編輯測試描述檔並參考其連結的資料，或加以修改：

1. 按一下您要編輯的測試描述檔，以選取它。
1. 請參考或修改欄位。

   ![](assets/test_profile_edit.png)

1. 如果 **[!UICONTROL Save]** 您已輸入變更，請按一下，或選取測試描述檔名稱，然後 **[!UICONTROL Test profiles]** 在畫面頂端的區段中，返回測試描述檔控制面板。
