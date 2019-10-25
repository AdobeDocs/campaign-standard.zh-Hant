---
title: 設定SMS頻道
seo-title: 設定SMS頻道
description: 設定SMS頻道
seo-description: 「瞭解SMS設定步驟：路由、編碼、格式和進階屬性。 "
page-status-flag: 從未激活
uuid: 5f13dbd5-9522-4199-8d9a-44c397cb2458
contentOwner: 紹維亞
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 參考
topic-tags: 配置通道
discoiquuid: 356d4d4f-3d5a-468c-bff8-96767cd8ff6
context-tags: extAccountMobile,overview;extAccount,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0c455e965d21996ffbadeddf336c6709ce8ee8f3

---


# 設定SMS頻道{#configuring-sms-channel}

若要傳送SMS訊息，管理員必須在&gt; &gt; &gt; &gt;功能表下設定一或多個 **[!UICONTROL Administration]** 外 **[!UICONTROL Channels]** 部 **[!UICONTROL SMS]** 帳戶 **[!UICONTROL SMS accounts]** 。

建立和修改外部帳戶的步驟在「外部帳戶」部分 [中詳細說](../../administration/using/external-accounts.md) 明。 您將在下方找到傳送SMS訊息之外部帳戶的特定參數。

## 定義SMS路由 {#defining-an-sms-routing}

外部帳戶 **[!UICONTROL SMS routing via SMPP]** 預設是提供的，但可用於添加其他帳戶。

如果您想使用SMPP通訊協定，也可以建立新的外部帳戶。 有關SMS通訊協定和設定的詳細資訊，請參閱此 [技術說明](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html)。

1. 從建立新的外部帳戶 **[!UICONTROL Administration > Application settings > External accounts]**。
1. 將帳戶類型定 **[!UICONTROL Routing]**&#x200B;義為，渠道 **[!UICONTROL Mobile (SMS)]** 定義為，傳送模式為 **[!UICONTROL Bulk delivery]**。

   在定義了這些路由參數後，會自動選擇SMS連接器( **[!UICONTROL Generic SMPP]** )。 此連接器可讓Adobe Campaign透過SMPP通訊協定連線至簡訊服務中心(SMS-C)，將簡訊訊息直接傳送至目標描述檔。

   ![](assets/sms_routing.png)

1. 定義連接設定。

   若要輸入傳送SMS訊息的特定連線設定，請連絡您的SMS服務提供者，該服務提供者將向您說明如何填寫不同的外部帳戶欄位。

   ![](assets/sms_connection.png)

   此選 **[!UICONTROL Enable TLS over SMPP]** 項允許您加密SMPP通信。

   **[!UICONTROL Enable verbose SMPP traces in the log file]** 允許您將所有SMPP通信轉儲到日誌檔案中。 必須啟用此選項，才能排除連接器故障，並與提供者所看到的流量進行比較。

1. 請洽詢Adobe,Adobe會根據所選的提供者，為您提供 **[!UICONTROL SMS-C implementation name]** 進入欄位的值。
1. 定義SMPP頻道設定。 您可以從 [SMS編碼和格式一節瞭解更多](#sms-encoding-and-formats) 。

   如果 **[!UICONTROL Store incoming MO in the database]** 您希望將所有傳入的SMS儲存在inSMS表格中，請啟用。 有關如何檢索傳入SMS的詳細資訊，請參閱本 [節](../../channels/using/managing-incoming-sms.md#storing-incoming-sms)。

   此選 **[!UICONTROL Enable Real-time KPI updates during SR processing]** 項可讓您 **[!UICONTROL Delivered]** 在傳送 **[!UICONTROL Bounces + Errors]** 傳送後即時更新或KPI。 這些KPI可在窗口中找 **[!UICONTROL Deployment]** 到，並直接從從提供商接收的SR（狀態報告）重新計算。

   ![](assets/sms_connection_1.png)

1. 定義參 **[!UICONTROL Throughput and timeouts]** 數。

   您可以指定每秒MT的出站消息（「MT」,「已終止移動」）的最大吞吐量。 如果您在對應欄位中輸入"0"，則吞吐量將無限制。

   與持續時間對應的所有欄位的值需要以秒為單位完成。

1. 定義SMS-C特定參數，以備您需要定義特定編碼對應時使用。 有關詳細資訊，請參閱 [SMSC詳細資訊](#smsc-specifics) 。

   如果 **[!UICONTROL Send full phone number (send characters other than digits)]** 您不想遵守SMPP協定，並將首碼傳輸 **[!UICONTROL +]** 到SMS提供者(SMS-C)的伺服器，請啟用此選項。

   但是，由於某些提供者需要使用首碼，因此建議您向您的提供者 **[!UICONTROL +]** 查詢，並建議您視需要啟用此選項。

1. 如有需要，請根據回覆的內容定義自動回覆以觸發動作。 如需詳細資訊，請參閱[本小節](../../channels/using/managing-incoming-sms.md#managing-stop-sms)。
1. 保存SMS路由外部帳戶的配置。

您現在可以使用新的路由，透過Adobe Campaign傳送SMS訊息。

## SMS編碼和格式 {#sms-encoding-and-formats}

### SMS編碼、長度和音譯 {#sms-encoding--length-and-transliteration}

根據預設，SMS中的字元數量符合GSM（行動通訊全球系統）標準。

使用GSM編碼的SMS訊息最多只能有160個字元，若是以多個部分傳送的訊息，則每個SMS的SMS訊息最多只能有153個字元。

>[!NOTE]
>
>某些字元會計為兩個字元（括弧、方括弧、歐元符號等）。 可用GSM字元的清單顯示在「字元表- [GSM標準」部分](#table-of-characters---gsm-standard) 。

如果您喜歡，可以勾選對應方塊，以授權字母音譯。

![](assets/sms_transliteration.png)

音譯包括當GSM標準未考慮到SMS的一個字元時，用另一個字元取代該字元。

* 如果音譯是 **授權的**，則在傳送訊息時，未考慮的每個字元會由GSM字元取代。 例如，字母"ë"被"e"取代。 因此，訊息會稍微變更，但字元限制將維持不變。
* 當音譯未 **授權時**，每個包含未納入考量之字元的訊息都會以二進位格式(Unicode)傳送：因此，所有字元都將按原樣發送。 不過，使用Unicode的SMS訊息最多只能有70個字元（若是以多個部分傳送的訊息，則每個SMS有67個字元）。 如果超出字元數上限，則會傳送數則訊息，這可能會造成額外成本。

>[!CAUTION]
>
>將個人化欄位插入您的SMS訊息內容，可能會引入GSM編碼未考慮的字元。 「個人化SMS訊息」區 [段提供內容範例](../../channels/using/personalizing-sms-messages.md) 。

依預設，字母音譯會停用。 如果您希望SMS訊息中的所有字元都保持原樣，不要變更正確名稱（例如），建議您不要啟用此選項。

不過，如果您的SMS訊息包含許多產生Unicode訊息的字元，您可以選擇啟用此選項，以限制傳送訊息的成本。

### 字元表- GSM Standard {#table-of-characters---gsm-standard}

本節介紹GSM標準所考慮的字元。 除下面提及的字元外，所有插入訊息內文的字元都會將整個訊息轉換為二進位格式(Unicode)，因此限制為70個字元。 如需詳細資訊，請參閱 [SMS編碼、長度和音譯](#sms-encoding--length-and-transliteration) 。

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
   <td> 埃<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> 烏<br /> </td> 
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
   <td> ww<br /> </td> 
  </tr> 
  <tr> 
   <td> 奧<br /> </td> 
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
   <td> 島<br /> </td> 
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
   <td> AE<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> 厄<br /> </td> 
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
   <td> 奧<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> 女<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> 埃<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> a<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP:空間

ESC:Escape

LF:行動態消息

CR:歸位

**進階字元（計算兩次）**

^ { } [ ~ ] | €

### SMSC細節 {#smsc-specifics}

>[!NOTE]
>
>這些選項允許您調整連接器以使用非標準SMSC（即不完全遵循SMPP 3.4規範）或特定編碼要求，並且僅應由高級用戶配置。

傳送SMS訊息時，Adobe Campaign可以使用一或多種文字編碼。 每個編碼都有其專屬的字元集，並決定符合SMS訊息的字元數。

此欄 **[!UICONTROL DATA_CODING]** 位可讓Adobe Campaign與使用編碼的SMS-C通訊。

>[!NOTE]
>
>標準化 **data_coding值與實際使用的編碼** 之間的映射。 然而，某些SMS-C有其獨特的映射：在這種情況下，您的 **** Adobe Campaign管理員需要宣告此對應。 請洽詢您的供應商以瞭解更多資訊。

此功 **[!UICONTROL Define a specific mapping of encodings]** 能可讓您宣告 **data_codings** ，並視需要強制進行編碼：若要這麼做，請在表格中指定單一編碼。

**配置**

* 未檢 **[!UICONTROL Define a specific mapping of encodings]** 查該功能時，連接器會採取一般行為：

   * 它會嘗試使用GSM編碼，將 **data_coding = 0的值指派給它**。
   * 如果GSM編碼失敗，則會使 **用UCS2** 編碼，將值 **data_coding = 8**。
   ![](assets/sms_data_coding.png)

* 勾選功 **[!UICONTROL Define a specific mapping of encodings]** 能後，您可以定義要使用的編碼以及連結的欄位 **[!UICONTROL data_coding]** 值。 Adobe Campaign會嘗試使用清單中的第一個編碼，如果第一個編碼不可能，則請執行下列操作。

   聲明的順序非常重要：建議您將清單以成本的遞增 **順序** ，以利使用編碼，讓您在每則SMS訊息中盡可能多地顯示字元。

   僅聲明您要使用的編碼。 如果SMS-C提供的某些編碼不符合您的使用目的，請勿在清單中宣告。

   ![](assets/sms_data_coding1.png)

### 自動回覆傳送至MO {#automatic-reply-sent-to-the-mo}

當描述檔回覆透過「促銷活動」傳送的SMS訊息時，您可以設定自動傳回給他的訊息，以及要執行的動作。

有關更多資訊，請參見[本節](../../channels/using/managing-incoming-sms.md)。

## 配置SMS屬性 {#configuring-sms-properties}

本節詳細說明SMS傳送或SMS範本屬性畫面中SMS專屬的參數清單。

用於發送SMS消息的特定參數在和節中 **[!UICONTROL Send]** 重新分組 **[!UICONTROL Advanced parameters]** 。

![](assets/sms_options.png)

* 該 **[!UICONTROL From]** 選項允許您使用字串個性化SMS消息發送器的名稱。 此名稱將顯示為收件者行動電話上SMS訊息的傳送者名稱。

   如果此欄位為空，則會是使用的外部帳戶中提供的來源號碼。 如果未提供來源號碼，則將使用簡短代碼。 特定於SMS傳送的外部帳戶會顯示在「外部 [SMS帳戶」區段](#defining-an-sms-routing) 。

   ![](assets/sms_smpp.png)

   >[!CAUTION]
   >
   >請查看您所在國家／地區有關修改發件人地址的法規。 您也應洽詢您的SMS服務供應商，以瞭解他們是否提供此功能。

* 選 **[!UICONTROL Maximum number of SMS per message]** 項允許您定義用於發送消息的SMS消息數。 如果超過此數目，則不會傳送訊息。

   >[!CAUTION]
   >
   >如果您已將個人化欄位或條件文字插入SMS訊息的內容，訊息的長度，以及因此要傳送的SMS訊息數量，可能會因收件者而異。 有關詳細資訊，請參閱「個 [人化SMS消息](../../channels/using/personalizing-sms-messages.md) 」部分。

* 此 **[!UICONTROL Transmission mode]** 欄位可讓您判斷SMS訊息的傳送方式：

   * **[!UICONTROL Saved on SIM card]**:該消息儲存在接收者的電話SIM卡上。
   * **[!UICONTROL Saved on mobile]**:該消息儲存在電話的內部儲存器上。
   * **[!UICONTROL Flash]**:該消息作為通知在收件人的行動電話上顯示，然後消息消失而不被保存。

