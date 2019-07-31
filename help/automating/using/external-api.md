---
title: 外部API
seo-title: 外部API
description: 外部API
seo-description: null
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 定位活動
context-tags: ExternalAPI，工作流程，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6748e59aaeafce9dc6e77dc0664a9024a53c3e35

---


# External API {#external-api}

## Description {#description}

![](assets/wf_externalAPI.png)

**[!UICONTROL External API]** 活動會透過REST API呼叫從 **外部系統** 將資料帶入 **工作流程** 。

The REST endpoints can be a customer management system, an [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) instance or an Experience Cloud REST endpoints (Data Platform, Target, Analytics, Campaign, etc).

>[!CAUTION]
>
>此功能目前仍在公開測試版中。您必須先接受使用合約，才能開始使用外部API活動。請注意，由於此公開測試版功能尚未由Adobe發佈，Adobe Client Care不支援此功能，因此可能包含錯誤且可能無法運作以及其他發行的功能。

此活動的主要特性為：

* 能夠將資料以JSON格式傳遞給第三方REST API端點
* 可接收JSON回應，將其對應至輸出表格，並傳送至其他工作流程活動。
* 透過對外特定轉場的失敗管理

已針對此活動制定下列公告：

* MB http回應資料大小限制
* 請求逾時為60秒
* 不允許HTTP重新導向
* 非HTTPS URL被拒絕
* 「接受：application/json「request header and「Content-Type」：application/json「回應標題」

>[!CAUTION]
>
>請注意，此活動用於擷取促銷活動寬資料(最新的選件集、最新分數等)。不是擷取每個描述檔的特定資訊，因為這可能導致大量傳輸資料。If the use case requires this, the recommendation is to use the [Transfer File](../../automating/using/transfer-file.md) activity.

## Configuration {#configuration}

Drag and drop an **[!UICONTROL External API]** activity into your workflow and open the activity to start the configuration.

### 傳入對應

傳入對應是由先前傳入活動產生的暫時表格，會在UI中顯示並以JSON形式傳送。
使用者可根據此暫存表格修改傳入資料。

![](assets/externalAPI-inbound.png)

**「內嵌資源** 」下拉式清單可讓您選取將建立暫存表格的查詢活動。

**「新增計數參數** 」核取方塊將會計算來自暫存表格的每一列的計數值。請注意，只有當傳入的活動產生臨時表格時，才可使用此核取方塊。

**「內嵌欄」** 區段可讓使用者從傳入的轉換表格新增任何欄位。選取的欄將是資料物件中的索引鍵。JSON中的資料物件將是包含傳入轉換表格每一列之選定欄資料的陣列清單。

**自訂參數** 文字方塊可讓您使用外部API所需的額外資料新增有效的JSON。此額外資料會新增至產生的JSON中的params物件。

### 對外對應

This tab lets you define the sample **JSON structure** returned by the API Call.

![](assets/externalAPI-outbound.png)

The JSON structure pattern is: `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

The sample JSON definition must have the **following characteristics**:

* **資料** 是JSON中的強制屬性名稱，「資料」的內容是JSON陣列。
* **陣列元素** 必須包含第一級屬性(不支援更深層次)。
   **屬性名稱** 最後會變成輸出暫存表格輸出結構的欄名稱。
* **欄名稱** 定義是以「資料」陣列的第一個元素為基礎。
Columns definition (add/remove) and the type value of the property can be edited in the **Column definition** tab.

If the **parsing is validated** a message appears and invite you to customize the data mapping in the "Column definition" tab. 在其他情況下，會顯示錯誤訊息。

### 執行執行

This tab lets you define the **HTTPS Endpoint** that will send data to ACS. If needed, you can enter authentication information in the fields below.
![](assets/externalAPI-execution.png)

### 屬性

This tab lets you control **general properties** on the external API activity like the displayed label in the UI. 內部ID無法自訂。

![](assets/externalAPI-properties.png)

### 欄定義

>[!NOTE]
>
>**當回應資料格式** 已完成並在「對外對應」標籤中驗證時，就會顯示此標籤。

**「欄定義** 」標籤可讓您精確指定每個欄的資料結構，以便匯入不包含任何錯誤的資料，並使它符合Adobe Campaign資料庫中已存在的類型，以便日後操作。

![](assets/externalAPI-column.png)

例如，您可以變更欄的標籤，選取其類型(字串、整數、日期等)。甚至指定錯誤處理。

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### 轉場效果

This tab lets you activate the **outbound transition** and its label. This specific transition is useful in case of **timeout** or if the payload exceed the **data size limit**.

![](assets/externalAPI-transition.png)

### 執行選項

大部分工作流程活動都有此標籤。For more information, consult the [Activity properties](../../automating/using/executing-a-workflow.md#activity-properties) section.

![](assets/externalAPI-options.png)

## 疑難排解

此新工作流程活動中新增了兩種記錄訊息：資訊和錯誤。它們可協助您疑難排解潛在問題。

### 資訊

這些記錄訊息可用來記錄執行工作流程活動期間有用查核點的相關資訊。尤其是，使用下列記錄訊息來記錄第一次嘗試嘗試存取API的嘗試嘗試(以及首次嘗試失敗的原因)。

<table> 
 <thead> 
  <tr> 
   <th> Message format<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 叫用API URL'%s'。</td> 
   <td> <p>叫用API URL'https://example.com/api/v1/web-coupon?count=2'。</p></td> 
  </tr> 
  <tr> 
   <td> 重試API URL'%s'時，先前嘗試失敗('%s')。</td> 
   <td> <p>重新嘗試API URL'https://example.com/api/v1/web-coupon?count=2'，先前嘗試失敗('HTTP-401')。</p></td>
  </tr> 
  <tr> 
   <td> 從'%s'傳輸內容(%s/%s)。</td> 
   <td> <p>從'https://example.com/api/v1/web-coupon?count=2'(1234/1234)傳輸內容。</p></td> 
  </tr>
 </tbody> 
</table>

### 錯誤

這些記錄訊息可用來記錄未預期錯誤條件的資訊，這會最終導致工作流程活動失敗。

<table> 
 <thead> 
  <tr> 
   <th> Code - Message format<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250- API要求主體超出限制(限制：'% d')。</td> 
   <td> <p>API請求主體超出限制(限制：'5242880')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239- API回應超出限制(限制：'% d')。</td> 
   <td> <p>API回應超出限制(限制：5242880」)。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245- API URL無法解析(錯誤：'% d')。</td> 
   <td> <p>API URL無法解析(錯誤：'-2010')。</p>
   <p> 注意：當API URL失敗驗證規則時，會記錄此錯誤。</p></td>
  </tr> 
  <tr>
   <td> WKF-560244- API URL主機不得為'localhost'或IP位址常值(URL主機：'% s')。</td> 
   <td> <p>API URL主機不得為'localhost'或IP位址常值(URL主機：'localhost')。</p>
    <p>API URL主機不得為'localhost'或IP位址常值(URL主機：'192.168.0.5')。</p>
    <p>API URL主機不得為'localhost'或IP位址常值(URL主機：'[2001]')。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238- API URL必須是安全的URL(https)(要求的URL：'% s')。</td> 
   <td> <p>API URL必須是安全的URL(https)(要求的URL：https://example.com/api/v1/web-coupon?count=2')。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249-無法建立請求主體JSON。新增'%s'時發生錯誤。</td> 
   <td> <p>無法建立請求主體JSON。新增「params」時發生錯誤。</p>
    <p>無法建立請求主體JSON。新增「資料」時發生錯誤。</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246- HTTP標題索引鍵不好(標題金鑰：'% s')。</td> 
   <td> <p>HTTP標題金鑰不好(標題索引鍵：'% s')。</p>
   <p> Note: This error is logged when the custom header key fails validation according to <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr>
 <tr> 
   <td> 無法使用WKF-560248- HTTP標題金鑰(標題金鑰：'% s')。</td> 
   <td> <p>不允許HTTP標題金鑰(標題索引鍵：「接受」)。</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247- AHTTP標題值不佳(標題值：'% s')。</td> 
   <td> <p>HTTP標題值不好(標題值：'% s')。 </p>
    <p>Note: This error is logged when the custom header value fails validation according to <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240- JSON裝載有不良屬性'%s'。</td> 
   <td> <p>JSON裝載有不良的屬性'vish'。</p></td>
  </tr> 
  <tr>
   <td> WKF-560241-格式不正確或無法接受的格式。</td> 
   <td> <p>格式錯誤或格式不可接受。</p>
   <p>注意：此訊息僅適用於外部API的剖析回應主體，並在嘗試驗證回應主體是否符合本活動所規定的JSON格式時記錄。</p></td>
  </tr>
  <tr> 
   <td> WKF-560246-活動失敗(原因：'% s')。</td> 
   <td> <p>當活動因HTTP401錯誤回應而失敗時-活動失敗(原因：'HTTP-401')</p>
        <p>當活動因內部呼叫失敗而失敗時-活動失敗(原因：'IRC- n')。</p>
        <p>由於無效的Content-Type標題，活動失敗。- 活動失敗(原因：「Content-Type- application/html」)。</p></td> 
  </tr>
 </tbody> 
</table>

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
