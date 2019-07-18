---
title: 管理測試設定檔並傳送校樣
seo-title: 管理測試設定檔並傳送校樣
description: 管理測試設定檔並傳送校樣
seo-description: 瞭解如何管理測試設定檔和校樣。
page-status-flag: 從未啓動
uuid: eb4d893b-3724-4b15-9312-1ec7478468d
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 傳送
content-type: reference
topic-tags: 準備與測試訊息
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: Exce會員，概觀
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Managing test profiles and sending proofs{#managing-test-profiles-and-sending-proofs}

## About test profiles {#about-test-profiles}

測試設定檔可讓您定位其他不符合定義目標條件的收件者。會將它們新增至訊息的對象，以偵測您的收件者資料庫有詐用，或確保電子郵件送達收件匣。

You can manage your test profiles from the advanced menu **[!UICONTROL Profiles & audiences > Test profiles]**.

測試設定檔包含虛構的連絡人資訊或傳送者控制的聯絡資訊，然後在下列上下文中用於訊息：

* For sending **Proofs**: the Proof is a specific message used to check the message before sending the finalized delivery to recipients. 校樣測試設定檔負責檢查傳送的內容和格式。See [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).
* **電子郵件演算**：電子郵件演算測試設定檔可用來檢查訊息收件匣的顯示方式。例如，網路郵件、訊息服務、行動裝置等等。See [Email rendering](../../sending/using/email-rendering.md).

   **電子郵件演算** 使用是唯讀的。使用此使用的測試描述檔僅適用於Adobe Campaign。

* **設為陷阱**：訊息會傳送至測試描述檔，就像傳送到主要目標一樣，用以識別您的客戶檔案是否被惡意使用。
* **若要預覽** 訊息：預覽訊息時，可以選取測試設定檔來測試個人化元素。

![](assets/test_profile.png)

## Managing test profiles {#managing-test-profiles}

### Creating test profiles {#creating-test-profiles}

1. From the advanced menu, via the Adobe Campaign logo, select **Profiles &amp; audiences &gt; Test profiles** to access the list of test profiles.

   ![](assets/test_profile_creation_1.png)

1. From the **[!UICONTROL Test profiles]** dashboard, click **Create**.

   ![](assets/test_profile_creation_2.png)

1. 輸入此設定檔的資料。

   ![](assets/test_profile_creation_3.png)

1. 選擇您要用於測試設定檔的用途。

   ![](assets/test_profile_creation_4.png)

1. Enter the contact channels **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, as well as the test profile address if necessary.

   >[!NOTE]
   >
   >You can define a preferred email format: **[!UICONTROL Text]** or **[!UICONTROL HTML]**.

1. 如果您要使用此測試設定檔來測試交易訊息的個人化，請指定事件類型和此事件的資料。
1. Click **[!UICONTROL Create]** to save the test profile.

然後會將測試設定檔新增至描述檔清單中。

**相關主題：**

[建立測試描述檔](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) 影片

### Editing test profiles {#editing-test-profiles}

若要編輯測試描述檔並參考連結至其的資料，或加以修改：

1. 按一下影像，選擇要編輯的測試設定檔。
1. 請參閱或修改欄位。

   ![](assets/test_profile_edit.png)

1. Click **[!UICONTROL Save]** if you have entered your changes, or select the name of the test profile then **[!UICONTROL Test profiles]** in the section at the top of the screen to go back to the test profiles dashboard.

## Sending proofs {#sending-proofs}

校樣是一個特定訊息，可讓您先測試訊息，然後再傳送至主要目標。

校方的收件者負責核准該訊息(其內容和表格)。They are defined in the **Test profiles**. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

若要傳送校樣，您的訊息對象必須包含測試設定檔。

在訊息中：

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. 選擇您要使用的校樣類型：

   * **[!UICONTROL Email rendering]**：選取此選項可測試根據收件匣接收訊息的方式。For more information, refer to [Email rendering](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**：選取此選項，可在傳送訊息至主要目標之前測試訊息。校訂收件者可檢查其內容及其格式，以核准傳送內容。
   * **[!UICONTROL Proof + Email rendering]**：此選項結合了兩個先前選項。
   ![](assets/bat_select1.png)

1. 確認您的選擇。

   校樣會傳送至測試描述檔。

   ![](assets/bat_select2.png)

1. You can view your proofs using the **[!UICONTROL Proofs]** drop-down list.

   ![](assets/bat_view.png)

1. 選取存取摘要的校樣。For an email, if you have selected the **Email rendering** option as the proof type, the **[!UICONTROL Access email rendering]** icon is displayed on the right of the proof label. See [Email rendering](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

根據接收校樣之人員的意見，您可能會被要求修改傳送內容。修改完成後，您必須重新啓動電子郵件準備，然後重新傳送校樣。Each new proof can be accessed using the **[!UICONTROL Show proofs]** button.

您必須視需要傳送盡可能多的校樣，直到完成交付內容為止。完成後，您可以傳送傳送至主要目標，並關閉核准週期。

**相關主題：**

[傳送測試、準備和傳送電子郵件](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) 視訊
