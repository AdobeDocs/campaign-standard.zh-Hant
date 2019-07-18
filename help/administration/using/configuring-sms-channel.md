---
title: 設定SMS頻道
seo-title: 設定SMS頻道
description: 設定SMS頻道
seo-description: 「瞭解SMS設定步驟：路由、編碼、格式和進階屬性。"
page-status-flag: 從未啓動
uuid: 5f13dbd5-9522-419-8d9a-44c397cb2458
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: reference
topic-tags: 設定頻道
discoiquuid: 356d4d4f-3d5a-468c-bff8-96767cd8 fff6
context-tags: extAccountMobile，總覽；extAccount，main；傳送，SMSContent，back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Configuring SMS channel{#configuring-sms-channel}

To send SMS messages, one or several external accounts must be configured by an administrator under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL SMS]** &gt; **[!UICONTROL SMS accounts]** menu.

The steps for creating and modifying an external account are detailed in the [External accounts](../../administration/using/external-accounts.md) section. 您會發現傳送SMS訊息的外部帳戶參數如下。

## Defining an SMS Routing {#defining-an-sms-routing}

The external account **[!UICONTROL SMS routing via SMPP]** is provided by default, but it can be useful to add other accounts.

如果您想要使用SMPP通訊協定，也可以建立新的外部帳戶。For more information on SMS protocol and settings, refer to this [technical note](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html).

1. Create a new external account from **[!UICONTROL Administration > Application settings > External accounts]**.
1. Define the account type as **[!UICONTROL Routing]**, the channel as **[!UICONTROL Mobile (SMS)]** and the delivery mode as **[!UICONTROL Bulk delivery]**.

   Once these routing parameters have been defined, the SMS connector ( **[!UICONTROL Generic SMPP]** ) is selected automatically. 此連接器可讓Adobe Campaign透過SMPP通訊協定連接至簡短訊息服務中心(SMS-C)，直接將SMS訊息傳送至目標設定檔。

   ![](assets/sms_routing.png)

1. 定義連線設定。

   若要輸入傳送SMS訊息的特定連線設定，請連絡您的SMS服務供應商，說明如何完成不同的外部帳戶欄位。

   ![](assets/sms_connection.png)

   **[!UICONTROL Enable TLS over SMPP]** 此選項可讓您加密SMPP流量。

   **[!UICONTROL Enable verbose SMPP traces in the log file]** 可讓您在記錄檔中傾倒所有的SMPP流量。此選項必須啓用，才能疑難排解連接器，並與供應商所看到的流量進行比較。

1. Contact Adobe who will give you the value to enter into the **[!UICONTROL SMS-C implementation name]** field, depending on the provider chosen.
1. 定義SMPP頻道設定。You can learn more in the [SMS encoding and formats](../../administration/using/configuring-sms-channel.md#sms-encoding-and-formats) section.

   Enable the **[!UICONTROL Store incoming MO in the database]** if you want all incoming SMS to be stored in the inSMS table. For more information on how to retrieve your incoming SMS, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   **[!UICONTROL Enable Real-time KPI updates during SR processing]** 此選項可讓 **[!UICONTROL Delivered]** 您在傳送傳送後即時更新或 **[!UICONTROL Bounces + Errors]** KPI。These KPIs can be found in the **[!UICONTROL Deployment]** window and are directly recalculated from the SR (Status Report) received from the provider.

   ![](assets/sms_connection_1.png)

1. Define the **[!UICONTROL Throughput and timeouts]** parameters.

   您可以指定每秒MT的傳出訊息(「MT」、「行動終止」)的最大總處理能力。如果您在對應欄位中輸入「0」，總處理能力將會無限制。

   所有對應至期間的欄位值都必須在秒內完成。

1. 定義SMS-C特定參數，以防您需要定義特定編碼對應。For more information, refer to the [SMSC specifics](../../administration/using/configuring-sms-channel.md#smsc-specifics) section.

   Enable the **[!UICONTROL Send full phone number (send characters other than digits)]** option if you don't want to respect the SMPP protocol and transfer the **[!UICONTROL +]** prefix to the server of the SMS provider (SMS-C).

   However, given that certain providers require the use of the **[!UICONTROL +]** prefix, it is advised that you check with your provider and they will suggest that you enable this option if necessary.

1. 視需要定義自動回覆，根據回覆內容觸發動作。For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. 儲存SMS路由外部帳戶的設定。

您現在可以使用Adobe Campaign傳送SMS訊息來傳送SMS訊息。

## SMS encoding and formats {#sms-encoding-and-formats}

### SMS encoding, length and transliteration {#sms-encoding--length-and-transliteration}

根據預設，SMS中的字元數符合GSM(全球行動通訊通訊標準)標準。

使用GSM編碼的SMS訊息僅限160個字元，而多個部分傳送的訊息每SMS則有153個字元。

>[!NOTE]
>
>某些字元會計算為兩個(括號、方形括號、歐元符號等)。The list of available GSM characters is presented in the [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard) section.

您可以按一下對應方塊來授權字元翻譯。

![](assets/sms_transliteration.png)

轉譯是由GSM標準不會將SMS的一個字元取代為另一個字元。

* **如果已授權**&#x200B;翻譯，則傳送訊息時，每個未納入考量的字元都會被GSM字元取代。例如，字母「if」會被「e」取代。因此訊息會稍微變更，但字元限制會維持不變。
* When transliteration is **not authorized**, each message that contains characters that are not taken into account is sent in binary format (Unicode): all of the characters are therefore sent as they are. 但是，使用Unicode的SMS訊息僅限70個字元(以多個組件傳送的訊息為每SMS的67個字元)。如果超出字元數目上限，則會傳送數個訊息，以產生額外的成本。

>[!CAUTION]
>
>將個人化欄位插入SMS訊息內容中，可能會引入GSM編碼未考量的字元。[「個人化SMS訊息](../../channels/using/personalizing-sms-messages.md) 」區段提供內容範例。

依預設，字元翻譯會停用。如果您希望SMS訊息中的所有字元保持原樣，例如不更改適當的名稱，建議您不要啓用此選項。

不過，如果SMS訊息包含許多產生Unicode訊息的字元，您可以選擇啓用此選項來限制傳送訊息的成本。

### Table of characters - GSM Standard {#table-of-characters---gsm-standard}

本節將說明採用GSM標準的字元。在訊息內文中插入的所有字元，除了以下提及的字元外，將整個訊息轉換為二進位格式(Unicode)，因此將其限制為70個字元。For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

**基本字元**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> P<br /> </td> 
   <td> ¿<br /> </td> 
   <td> P<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> A<br /> </td> 
   <td> Q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> B<br /> </td> 
   <td> R<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> C<br /> </td> 
   <td> S<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> F<br /> </td> 
   <td> V<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> G<br /> </td> 
   <td> W<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> H<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> Ç<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> I<br /> </td> 
   <td> Y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> J<br /> </td> 
   <td> Z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> K<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> Æ<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> Ñ<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP：Space

ESC：逸出

LF：行摘要

CR：歸位退貨

**進階字元(計數次)**

^ { } [ ~ ] | €

### SMSC specifics {#smsc-specifics}

>[!NOTE]
>
>這些選項可讓您調整連接器以搭配非標準SMSC運作(亦即不符合SMPP3.4規格)或特定編碼要求，而且僅能由進階使用者設定。

傳送SMS訊息時，Adobe Campaign可以使用一或多個文字編碼。每個編碼都有自己的特定字元集，並決定適合SMS訊息的字元數目。

**[!UICONTROL DATA_CODING]** 此欄位可讓Adobe Campaign與SMS-C通訊，以進行編碼。

>[!NOTE]
>
>**data_ code** 值與實際使用的編碼之間的映射是標準化的。Nevertheless, certain SMS-C have their own specific mapping: in this case, your **Adobe Campaign** administrator needs to declare this mapping. 請洽詢您的供應商以瞭解更多資訊。

**[!UICONTROL Define a specific mapping of encodings]** 此功能可讓您宣告 **data_ cotts** 並強制進行編碼：若要這麼做，請在表格中指定單一編碼。

**組態配置**

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is not checked, the connector takes on a generic behavior:

   * It will try to use GSM encoding to which it assigns the value **data_coding = 0**.
   * If GSM encoding fails, it will use **UCS2** encoding to which it assigns the value **data_coding = 8**.
   ![](assets/sms_data_coding.png)

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is checked, you can define the encodings that you would like to use as well as the linked **[!UICONTROL data_coding]** field values. 如果第一個編碼可行，Adobe Campaign會嘗試使用清單中的第一個編碼，然後再使用下列編碼。

   The order of declaration is important: it is recommended that you put the list in ascending order **of cost** in order to favor the encodings allowing you to fit as many characters as possible in each SMS message.

   僅宣告您要使用的編碼。如果SMS-C所提供的某些編碼不符合您的使用目的，請勿在清單中宣告。

   ![](assets/sms_data_coding1.png)

### Automatic reply sent to the MO {#automatic-reply-sent-to-the-mo}

當描述檔回覆是透過促銷活動傳送的SMS訊息時，您可以設定自動傳回給他的訊息，以及執行的動作。

For more information, refer to [this section](../../channels/using/managing-incoming-sms.md).

## Configuring SMS properties {#configuring-sms-properties}

本節詳細說明SMS傳送或SMS範本屬性畫面中SMS獨有的參數清單。

The specific parameters for sending SMS messages are regrouped in the **[!UICONTROL Send]** and in the **[!UICONTROL Advanced parameters]** sections.

![](assets/sms_options.png)

* **[!UICONTROL From]** 此選項可讓您使用字元字串個人化SMS訊息傳送者的名稱。此名稱會在收件者的行動電話上顯示為SMS訊息的傳送者名稱。

   如果此欄位空白，則會為將使用的外部帳戶中提供的來源號碼。如果沒有提供來源號碼，則會是將使用的簡短代碼。The external account specific to SMS delivery is presented in the [External SMS account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.

   ![](assets/sms_smpp.png)

   >[!CAUTION]
   >
   >請檢查您所在國家/地區是否修改傳送者地址。您也應與SMS服務供應商核對，以瞭解他們是否提供此功能。

* **[!UICONTROL Maximum number of SMS per message]** 此選項可讓您定義要用來傳送訊息的SMS訊息數目。如果超過此數目，則不會傳送訊息。

   >[!CAUTION]
   >
   >如果您在SMS訊息的內容中插入個人化欄位或條件文字，則訊息長度，因此傳送的SMS訊息數量可能會有所不同。For more on this, refer to the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

* **[!UICONTROL Transmission mode]** 此欄位可讓您判斷SMS訊息的傳送方式：

   * **[!UICONTROL Saved on SIM card]**：訊息會儲存在收件者的電話SIM卡上。
   * **[!UICONTROL Saved on mobile]**：訊息會儲存在手機的內部記憶體上。
   * **[!UICONTROL Flash]**：訊息會在收件者的行動電話上顯示為通知，然後就會消失而不會儲存。

