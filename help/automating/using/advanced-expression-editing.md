---
title: 進階運算式編輯
seo-title: 進階運算式編輯
description: 進階運算式編輯
seo-description: 查詢版本精靈可讓您定義進階運算式。
page-status-flag: 從未啓動
uuid: a635f999-27ce-41e-a88 c-8a3882 e31 efe
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 篩選資料
discoiquuid: 4375153c-062-1d4c-bcc-66d157 f04 f6 c
context-tags: QueryFilter，概觀；觀眾，主要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Advanced expression editing{#advanced-expression-editing}

## About advanced expression editing {#about-advanced-expression-editing}

編輯運算式需要手動輸入條件以形成規則。

此模式可讓您使用進階功能。這些函數可讓您控制用於執行特定查詢(例如控制日期、字串、數值欄位、排序等)的值。

編輯運算式時也可以使用事件變數。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

您可以編輯運算式，以便：

* Define a query, via the **[!UICONTROL Advanced mode]** option which is available when a rule is added.

   ![](assets/expression_editor_2.png)

* 編輯工作流程中的運算式。例如，若要新增其他資料至活動。
* 編輯可見性條件，以定義HTML內容編輯器中的區塊如何顯示。在這種情況下，運算式是以JavaScript格式編輯，不會提供進階函數做為標準。

## Edit an expression {#edit-an-expression}

進階運算式版本可讓您手動定義符合您需求的運算式。

建立運算式時，可以在建立電子郵件或建立工作流程時，在「對象」視窗中使用「編輯」運算式。

1. Access the expression editing window via one of the methods detailed in the [About advanced expression editing](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) section. 其中包含下列元素：

   * 定義運算式的輸入欄位。
   * The list of available fields that can be used in the expression and correspond to the targeting dimension of the query (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * 可用函數清單，依類別排序。
   ![](assets/expression_editor_1.png)

1. 直接在對應欄位中輸入運算式，或使用可用欄位和函數的清單來編輯運算式。

   按兩下欄位或運算式，將其新增至放置游標的運算式。

   您可以使用工作流程變數變數來建立運算式。For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. 視需要為您的規則提供特定名稱。輸入的名稱將會顯示為查詢編輯器工作區中的規則名稱。

編輯運算式可讓您依需要個人化「對象」運算式以定位人口。

**相關主題：**

* [運算式語法](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [函數清單](../../automating/using/list-of-functions.md)

## Expression Syntax {#expression-syntax}

### Standard syntax {#standard-syntax}

標準運算式由一或數個符合下列語法元素的條件組成：

* Each condition takes the form of **&lt;value1&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; value&gt;** 為欄位或函數。For example **@created** for the date a profile was created or **Year(@created)** for the year a profile was created.
   * **&lt; compare運算子&gt;** 是 [比較運算子](../../automating/using/advanced-expression-editing.md#comparison-operators) 區段中所列的運算子之一。This operator defines the comparison method between **&lt;value1&gt;** and **&lt;value2&gt;**.
   * **&lt; value2&gt;** 是一個欄位、函數或手動輸入的值。
   >[!NOTE]
   >
   >**&lt; value&gt;** 和 **&lt; value2&gt;** 類型資料必須相同。For example, if **&lt;value1&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* 如果您想要使用多個條件，可以使用邏輯運算子結合它們。

   * **[!UICONTROL AND]**：兩個條件相交。
   * **[!UICONTROL OR]**：結合兩個條件。

例如：

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

在此範例中，建立日期為目前月份和年的描述檔會受到定位。

### JavaScript syntax {#javascript-syntax}

定義HTML內容編輯器文字類型區塊的可見性條件時，您必須使用JavaScript類型語法的運算式。

JavaScript運算式由一或多個條件組成，且它們使用下列語法元素：

* Each condition takes the form of **&lt;context&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; context&gt;** 是可讓您指定上下文的欄位或函數。**例如context. profile。@email** for a profile's email address or **context.profile.firstName.length()** for the number of characters of a profile's first name.
   * **&lt; compare運算子&gt;** 是 [比較運算子](../../automating/using/advanced-expression-editing.md#comparison-operators) 區段中所列的運算子之一。This operator defines the comparison method between **&lt;context&gt;** and **&lt;value2&gt;**.
   * **&lt; value2&gt;** 是一個欄位、函數或手動輸入的值。
   >[!NOTE]
   **&lt; context&gt;** 和 **&lt; value&gt;** type資料必須相同。For example, if **&lt;context&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* 如果您想要使用多個條件，可以使用邏輯運算子結合它們。

   * **[!UICONTROL &&]**：兩個條件相交。
   * **[!UICONTROL ||]**：結合兩個條件。

例如：

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In this example, profiles older than 21 years of age and whose first name has been provided (symbolized by the fact that the **firstName** field contains at least one character).

## Comparison operators {#comparison-operators}

對於某些規則，查詢編輯器可讓您選擇值來定義條件。

條件必須使用下列任一運算子連結至值。

<table> 
 <thead> 
  <tr> 
   <th> Operator<br /> </th> 
   <th> Standard syntax<br /> </th> 
   <th> JavaScript syntax<br /> </th> 
   <th> Description<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">等於</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> The first value must be completely identical to the second value.<br /> </td> 
   <td> <strong>@ lastName= Martin</strong> 擷取的描述檔是「Martin」，只有這些字元具有相同的字元。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">大於</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> The first value must categorically be more than the second value.<br /> </td> 
   <td> <strong>@年齡&gt;50</strong> 會擷取大於「50」的描述檔，因此'51'、'52'等。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">小於</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> The first value must categorically be less than the second value.<br /> </td> 
   <td> <strong>@ created&lt; daySago(100)</strong> 會在100天前擷取資料庫中建立的所有描述檔。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">大於或等於</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> The first value must be more than or equal to the second value.<br /> </td> 
   <td> <strong>@ age&gt;=30</strong> 擷取年齡超過30歲及以上的描述檔。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">小於或等於</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> The first value must be less than or equal to the second value.<br /> </td> 
   <td> <strong>@ age&lt;=60</strong> 擷取60或更低年齡的描述檔。<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">不同之處 </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> The first value must be different from the second value.<br /> </td> 
   <td> <strong>@ language！= English</strong> retrieves profiles that have not been defined as English speaking.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">包含</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must contain the second value.<br /> </td> 
   <td> <strong>@網域IN郵件</strong>。在此，結果中會傳回所有具有'mail'值的網域名稱。Consequently, the 'gmail.com' domain name will make up part of the returned results.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">贊</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">贊</span> 與 <span class="uicontrol">「包含</span> 」運算子非常相似。It lets you insert a <span class="uicontrol">%</span> wild card character in the value that is being searched.<br /> </td> 
   <td> <strong>@ lastName贊MART%n</strong>。Here, the substitution character <strong>%</strong> serves as a "joker" to find the name "Martin" in the hypothetical case that the spelling is not correct.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">不喜歡</span><br /> </td> 
   <td> NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> Is similar to <span class="uicontrol">Like</span>. 它可讓您無法復原輸入的值。Here too, the entered value must contain the <span class="uicontrol">%</span> wild card character.<br /> </td> 
   <td> <strong>@ lastName NOT Smi%h</strong>.在這裡，收件者對應名稱「Smi%h」(因此，are not returned as a result.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">空白</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must correspond to an empty value.<br /> </td> 
   <td> <strong>@ MobilePhone IS NULL</strong> 會擷取未提供行動電話號碼的所有描述檔。<br /> </td> 
  </tr> 
 </tbody> 
</table>

