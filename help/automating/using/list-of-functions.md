---
title: 函數清單
seo-title: 函數清單
description: 函數清單
seo-description: 查詢編輯工具可讓您使用進階函數進行複雜篩選。
page-status-flag: 從未啓動
uuid: fd50fc99-1e7a-479b-beb7-1f419 b419 d46
contentOwner: saviat
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: reference
topic-tags: 篩選資料
discoiquuid: cdbe962-2c59-4cd8-b29 e-36aa2562 fac6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 83be3f22f3508248f2a4666080a7207998093dc3

---


# 函數清單{#list-of-functions}

## 關於函數 {#about-functions}

查詢編輯工具可讓您使用進階函數進行複雜篩選。若要這麼做，工具浮動視窗會包含您可以在工作區中使用的 **[!UICONTROL Expression]** 元素。有關此元素的詳細資訊，請參閱特定 [章節](../../automating/using/advanced-expression-editing.md)。

此元素可讓您手動輸入條件。您可以在此處使用下列章節中定義的函數。

有幾種函數類型可供使用，視需要的結果和控制資料類型而定：

* 日期
* Geomarketing
* 數值
* 其他函數
* 整合
* 字串操縱
* 排序順序

## 日期 {#dates}

日期函數可用來控制日期或時間值。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Name</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>語法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addDays</strong><br /> </td> 
   <td> 新增日期至日期<br /> </td> 
   <td> addDays(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addStudio</strong><br /> </td> 
   <td> 新增數小時至日期<br /> </td> 
   <td> addStudio(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMin分鐘</strong><br /> </td> 
   <td> 新增數分鐘至日期<br /> </td> 
   <td> addMinds(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addMonters</strong><br /> </td> 
   <td> 新增數個月至日期<br /> </td> 
   <td> addMonters(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addSeconds</strong><br /> </td> 
   <td> 新增數秒至日期<br /> </td> 
   <td> addSeconds(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>addYear</strong><br /> </td> 
   <td> 新增數年至日期<br /> </td> 
   <td> addYear(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>dateOnly</strong><br /> </td> 
   <td> 只傳回日期(隨時間00：00)<br /> </td> 
   <td> dateOnly(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> 傳回代表日期日的數字<br /> </td> 
   <td> Day(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>天</strong><br /> </td> 
   <td> 傳回代表日期一年內的日<br /> </td> 
   <td> DayOfYear(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaySago</strong><br /> </td> 
   <td> 傳回目前日期減去n天<br /> </td> 
   <td> DaySago(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysagoInint</strong><br /> </td> 
   <td> 傳回目前日期減去n天(作為整數yyyymdd)<br /> </td> 
   <td> DaysagoInint(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> 兩個日期之間的天數<br /> </td> 
   <td> daysDiff(&lt; end date&gt;，&lt; start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayBule</strong><br /> </td> 
   <td> 傳回日期中的年齡<br /> </td> 
   <td> DayBued(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getDate</strong><br /> </td> 
   <td> 傳回伺服器的目前系統日期<br /> </td> 
   <td> getDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>小時</strong><br /> </td> 
   <td> 傳回日期的小時<br /> </td> 
   <td> 小時(&lt;日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HULSDiff</strong><br /> </td> 
   <td> 傳回兩個日期之間的小時數<br /> </td> 
   <td> HULSdiff(&lt; end date&gt;，&lt; start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>localOutC</strong><br /> </td> 
   <td> 將本機日期和時間轉換為UTC<br /> </td> 
   <td> LocalToC(&lt; date&gt;，&lt;時區&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>分鐘</strong><br /> </td> 
   <td> 傳回日期的分鐘數<br /> </td> 
   <td> 分鐘(&lt;日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>targetDiff</strong><br /> </td> 
   <td> 傳回兩個日期之間的分鐘數<br /> </td> 
   <td> targetDiff(&lt; end date&gt;，&lt; start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>月</strong><br /> </td> 
   <td> 傳回代表日期月份的數字<br /> </td> 
   <td> 月(&lt;日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthSago</strong><br /> </td> 
   <td> 傳回與目前日期減去n個月對應的日期<br /> </td> 
   <td> MonthSago(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDff</strong><br /> </td> 
   <td> 傳回兩個日期之間的月份數<br /> </td> 
   <td> monthsDff(&lt; end date&gt;，&lt; start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthBued</strong><br /> </td> 
   <td> 傳回日期中的數個月<br /> </td> 
   <td> MonthBued(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Second</strong><br /> </td> 
   <td> 傳回日期的秒數<br /> </td> 
   <td> 第二(&lt;日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最舊</strong><br /> </td> 
   <td> 傳回最舊的日期 </td> 
   <td> 最舊(&lt; Date&gt;，&lt; Date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>sightsDiff</strong><br /> </td> 
   <td> 傳回兩個日期之間的秒數<br /> </td> 
   <td> sdfs(&lt; end date&gt;，&lt; start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子日期</strong><br /> </td> 
   <td> 減去日期中的天數<br /> </td> 
   <td> 子日數(&lt;日期&gt;，&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子時數</strong><br /> </td> 
   <td> 從日期減去數小時<br /> </td> 
   <td> 子時數(&lt; date&gt;，&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子分鐘數</strong><br /> </td> 
   <td> 減去日期中的幾分鐘數<br /> </td> 
   <td> 子分鐘(&lt;日期&gt;，&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子月份</strong><br /> </td> 
   <td> 從日期中減去數個月<br /> </td> 
   <td> 子月份(&lt;日期&gt;，&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子秒數</strong><br /> </td> 
   <td> 從日期減去數秒數<br /> </td> 
   <td> subSeconds(&lt; date&gt;，&lt; number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subyear</strong><br /> </td> 
   <td> 自日期算起數年數<br /> </td> 
   <td> 子年份(&lt; date&gt;，&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> 將日期+時間轉換為日期<br /> </td> 
   <td> ToDate(&lt; date+ time&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> 將字串轉換為日期+時間<br /> </td> 
   <td> ToDateTime(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>todateTimeWithTimeZone</strong><br /> </td> 
   <td> 將字串轉換為日期+時區。<br /> 範例：TodateTimeWithTimeZone(「2019-02-1908：09：00」，「亞洲/德黑蘭」)<br /> </td> 
   <td> todateTimeWithTimeZone(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截斷日期</strong><br /> </td> 
   <td> 將日期+時間四捨五入到最近的秒數<br /> </td> 
   <td> 截斷日期(@ lastModified，&lt;秒數&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截斷資料</strong><br /> </td> 
   <td> 將日期+時間四捨五入到指定的精確度，以秒為單位<br /> </td> 
   <td> 截斷資料Z(&lt; date&gt;，&lt; number of秒&gt;，&lt;時區&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截斷1/4</strong><br /> </td> 
   <td> 將日期四捨五入到季<br /> </td> 
   <td> 截斷(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截斷時間</strong><br /> </td> 
   <td> 將時間四捨五入到最接近的秒數<br /> </td> 
   <td> cendTime(&lt; date&gt;，&lt; number of秒&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截斷周</strong><br /> </td> 
   <td> 將日期四捨五入到星期<br /> </td> 
   <td> cendWeek(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>截斷年份</strong><br /> </td> 
   <td> 將日期+時間四捨五入到每年的月日<br /> </td> 
   <td> 截斷年份(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeeDay</strong><br /> </td> 
   <td> 傳回代表日期一星期內的日<br /> </td> 
   <td> WeeDay(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>年</strong><br /> </td> 
   <td> 傳回代表日期年度的數字<br /> </td> 
   <td> 年(&lt;日期&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>每年與月</strong><br /> </td> 
   <td> 傳回代表日期和日期月份的數字<br /> </td> 
   <td> yarandMonth(&lt; date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>yarsDff</strong><br /> </td> 
   <td> 傳回兩個日期之間的年份數<br /> </td> 
   <td> yarsDiff(&lt; end date&gt;，&lt; start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>eArchell</strong><br /> </td> 
   <td> 傳回日期中的年齡<br /> </td> 
   <td> yarAsted(&lt; date&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

地域行銷功能用於控制地理值。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Name</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>語法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>距離</strong><br /> </td> 
   <td> 傳回由其經度和經緯度定義的兩點距離(以度表示)<br /> </td> 
   <td> 距離(&lt; Publisher a&gt;，&lt;緯度A&gt;，&lt; Publisher B&gt;，&lt;緯度B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 數值 {#numerical}

數值值可用來將文字轉換為數字。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Name</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>語法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> 傳回數字的絕對值<br /> </td> 
   <td> Abs(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ciil</strong><br /> </td> 
   <td> 傳回大於或等於數字的最低整數<br /> </td> 
   <td> Seil(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> 傳回大於或等於數字的最大整數<br /> </td> 
   <td> 下限(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最大</strong><br /> </td> 
   <td> 傳回兩個數字<br /> </td> 
   <td> 最大(&lt;數字1&gt;，&lt;數字2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最低</strong><br /> </td> 
   <td> 傳回兩個數字<br /> </td> 
   <td> 最低(&lt;數字1&gt;，&lt;數字2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> 傳回n除以n的整數分區<br /> </td> 
   <td> Mod(&lt;數字1&gt;，&lt;數字2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>百分比</strong><br /> </td> 
   <td> 傳回兩個數字的比例(以百分比表示)<br /> </td> 
   <td> 百分比(&lt;數字1&gt;，&lt;數字2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>隨機隨機</strong><br /> </td> 
   <td> 傳回隨機值<br /> </td> 
   <td> 隨機()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>四捨五入</strong><br /> </td> 
   <td> 將數字捨棄為n小數點<br /> </td> 
   <td> 四捨五入(&lt;數字&gt;，&lt;小數位數&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> 傳回數字的簽署<br /> </td> 
   <td> 簽署(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>toDouble</strong><br /> </td> 
   <td> 將整數轉換為浮點<br /> </td> 
   <td> TooDog(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> 將浮動字元轉換為64位元整數<br /> </td> 
   <td> Toint64(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> 將浮動字元轉換為整數<br /> </td> 
   <td> To整數(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> 將n截斷為n小數點<br /> </td> 
   <td> Trunc(&lt; n1&gt;，&lt; n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 其他人 {#others}

此表格包含其餘的函數。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Name</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>語法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>case</strong><br /> </td> 
   <td> 傳回條件時傳回值1。否則，傳回值2<br /> </td> 
   <td> 大小寫(&lt;條件&gt;，&lt; value1&gt;)，其他(&lt; value2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Clearbit</strong><br /> </td> 
   <td> 刪除值中的標幟<br /> </td> 
   <td> clearbit(&lt;識別碼&gt;，&lt;標幟&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> 傳回值2如果值為零或null，則傳回值1<br /> </td> 
   <td> CoAlesce(&lt; value1&gt;，&lt; value2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>解碼</strong><br /> </td> 
   <td> 傳回值為value= value2，否則傳回4<br /> </td> 
   <td> 解碼(&lt; value1&gt;，&lt; value2&gt;，&lt; value3&gt;，&lt; value4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>其他</strong><br /> </td> 
   <td> 傳回值1(只能用作大小寫函數的參數)<br /> </td> 
   <td> 其他(&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getTemailDomain</strong><br /> </td> 
   <td> 從電子郵件地址擷取網域<br /> </td> 
   <td> getTemailDomain(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getMirrorURL</strong><br /> </td> 
   <td> 擷取鏡像頁面伺服器的URL<br /> </td> 
   <td> getMirrorURL(&lt; value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>if</strong><br /> </td> 
   <td> 傳回值1，如果運算式為true，則傳回值2<br /> </td> 
   <td> if(&lt;條件&gt;，&lt; value1&gt;，&lt; value2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isBitSet</strong><br /> </td> 
   <td> 指出旗標是否包含在<br /> </td> 
   <td> isBitSet(&lt;識別碼&gt;，&lt;標幟&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isEmptyString</strong><br /> </td> 
   <td> 傳回值2如果字串為空，則傳回值3<br /> </td> 
   <td> isEmptyString(&lt;字串&gt;，&lt; value2&gt;，&lt; value3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nonull</strong><br /> </td> 
   <td> 如果引數為空，則傳回空白字串<br /> </td> 
   <td> 非LR(&lt;值&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rowidd</strong><br /> </td> 
   <td> 傳回行數<br /> </td> 
   <td> Rowidd<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>setBit</strong><br /> </td> 
   <td> 強制值中的旗標<br /> </td> 
   <td> setBit(&lt;識別碼&gt;，&lt;標幟&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> 將數字轉換為布林值<br /> </td> 
   <td> ToBoolean(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>當時機</strong><br /> </td> 
   <td> 傳回值時傳回值1。否則，傳回值2(只能用作大小寫函數的參數)<br /> </td> 
   <td> 時間(&lt;條件&gt;，&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NewUUID</strong><br /> </td> 
   <td> 傳回新UUID。<br /> </td> 
   <td> NewUUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 字串 {#string}

字串函數可用來控制一組字串。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Name</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>語法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> 指出所有參數為非null，而非空值<br /> </td> 
   <td> allnonNULL(&lt;字串&gt;，&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> 指出所有參數為非null，而非空值<br /> </td> 
   <td> allnonNULL(&lt;字串&gt;，&lt;字串&gt;，&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> 傳回字串中第一個字元的ASCII值<br /> </td> 
   <td> ASCII(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> 傳回對應於'n'ASCII代碼的字元<br /> </td> 
   <td> Char(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> 傳回字串中字串的位置1<br /> </td> 
   <td> Chardex(&lt;字串&gt;，&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>dataLength</strong><br /> </td> 
   <td> 傳回字串中的字元數<br /> </td> 
   <td> dataLength(&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>getLine</strong><br /> </td> 
   <td> 傳回字串的nth(從到n)行<br /> </td> 
   <td> getLine(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>iFeQals</strong><br /> </td> 
   <td> 如果前兩個參數等於最後一個參數，則傳回第三個參數<br /> </td> 
   <td> iFeQuals(&lt;字串&gt;，&lt;字串&gt;，&lt;字串&gt;，&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>isMemonull</strong><br /> </td> 
   <td> 指出傳遞作為參數的memo是否為空<br /> </td> 
   <td> isMemonull(&lt; Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JXPublish</strong><br /> </td> 
   <td> 串連作為參數的兩個字串。系統會在傳回值的每個字串之間新增空格。<br /> </td> 
   <td> JXPublish(&lt;字串&gt;，&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> 串連作為參數的三個字串。系統會在傳回值的每個字串之間新增空格。<br /> </td> 
   <td> JXPublish3(&lt;字串&gt;，&lt;字串&gt;，&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> 傳回左側的完成字串<br /> </td> 
   <td> LPad(&lt;字串&gt;，&lt;數字&gt;，&lt; cardtère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>左側</strong><br /> </td> 
   <td> 傳回字串的前n個字元<br /> </td> 
   <td> 左側(&lt;字串&gt;，&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>長度</strong><br /> </td> 
   <td> 傳回字串長度<br /> </td> 
   <td> 長度(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>小寫</strong><br /> </td> 
   <td> 傳回小寫字串<br /> </td> 
   <td> 較低(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>L修剪</strong><br /> </td> 
   <td> 移除字串左側的空格<br /> </td> 
   <td> L修剪(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> 傳回字串MD索引鍵的十六進位表示法<br /> </td> 
   <td> Md Digest(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MooOcontains</strong><br /> </td> 
   <td> 指定emo包含作為參數傳遞的字串<br /> </td> 
   <td> MooO包含(&lt; memo&gt;，&lt; string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> 傳回右側的完成字串<br /> </td> 
   <td> RPad(&lt;字串&gt;，&lt;數字&gt;，&lt;字元&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>取代</strong><br /> </td> 
   <td> 將指定字串(第一個參數)值的所有發生次數取代為字串中的另一個字串值(3d參數)(第一個參數)<br /> </td> 
   <td> 取代(&lt; String&gt;，&lt; String&gt;，&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>right</strong><br /> </td> 
   <td> 傳回字串的最後n個字元<br /> </td> 
   <td> 右側(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>R修剪</strong><br /> </td> 
   <td> 移除字串右側的空格<br /> </td> 
   <td> R修剪(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> 計算指定UTF字串的標準 <strong>SHA256</strong> 雜湊<br /> </td> 
   <td> Sha256摘要(&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> 計算指定UTF字串的標準 <strong>SHA384</strong> 雜湊<br /> </td> 
   <td> Sha384摘要(&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> 計算指定UTF字串的標準 <strong>SHA512</strong> 雜湊<br /> </td> 
   <td> Sha512摘要(&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> 傳回大寫字母中每個字詞的第一個字母<br /> </td> 
   <td> 智慧(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>子字串</strong><br /> </td> 
   <td> 從字串的字元n開始，並以n的長度擷取子字串<br /> </td> 
   <td> 子字串(&lt;字串&gt;、&lt; offset&gt;、&lt; length&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TointlString</strong><br /> </td> 
   <td> 將數字轉換為字串<br /> </td> 
   <td> TointlString(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>toString</strong><br /> </td> 
   <td> 將數字轉換為字串<br /> </td> 
   <td> toString(&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> 傳回大寫中的字串<br /> </td> 
   <td> 大寫(&lt;字串&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> 如果其他兩個參數相等，則傳回傳遞作為參數的連結外鍵<br /> </td> 
   <td> VirtualLink(&lt;數字&gt;，&lt;數字&gt;，&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualInkSTr</strong><br /> </td> 
   <td> 傳回作為參數的連結的外國(文字)索引鍵，如果其他參數等於<br /> </td> 
   <td> VirtuallInkSTR(&lt;字串&gt;，&lt;數字&gt;，&lt;數字&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>secryption_aescubC解密</strong><br /> </td> 
   <td> 使用HEX格式(2d參數)的索引鍵，以及HEX格式的初始化向量(3rd參數)，解密具有「<strong>x</strong>」首碼(第個參數)的HEX格式加密值<br /> </td> 
   <td> passworction_aescubC解密(&lt; String&gt;，&lt; String&gt;，&lt; String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>secryption_ aescBCEnrypt</strong><br /> </td> 
   <td> 使用AES演算法(CBC區塊模式)加密字元(1st參數)字串(第一個參數)和初始化向量(第3d參數)。關鍵字和初始化向量必須以十六進位表示法提供(從 <strong>\ x</strong>開始)。結果將會是十六進位，而沒有 <strong>\ x</strong>。<br /> 請注意，金鑰大小可以是128位元、192位元、256位元(16、24、32位元字元)，但建議您使用與索引鍵相同長度的256位元和randomized IV。<br /> </td> 
   <td> 加密_ aExcbCEnrypt(&lt; String&gt;，&lt; String&gt;，&lt; String&gt;)<br /> for example：加密_ aExcCEncrypt(johndoe@example.com，「<strong>\ x0123456789ABCDEF012345689ABCDEF</strong>」，「<strong>\ x0123456789ABCDEFEDCBA9867543210</strong>」))<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 整合 {#aggregates}

只有在從工作流程活動 [中新增其他資料](../../automating/using/query.md#enriching-data) 時，才可使用匯總 **[!UICONTROL Query]** 功能。

匯總函數可用來對一組值執行計算。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Name</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>語法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>平均</strong>、平均<br /> </td> 
   <td> 傳回數值欄中的平均值。<br /> </td> 
   <td> 平均值(&lt;值&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>計數</strong>、計數(NULL除外)<br /> </td> 
   <td> 計算欄中的非空值。<br /> </td> 
   <td> 計數(&lt;值&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CotTle</strong>，count all<br /> </td> 
   <td> 計算所有值(包括空值和重復值)。<br /> </td> 
   <td> CostTel()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>差異</strong>、區別計數<br /> </td> 
   <td> 計算欄中非空值、不同值。<br /> </td> 
   <td> 差異(&lt;值&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最大值</strong>、最大值<br /> </td> 
   <td> 傳回數值、字串或日期欄中的最大值。<br /> </td> 
   <td> 最大值(&lt;值&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>最小值</strong>、最小值<br /> </td> 
   <td> 傳回數值、字串或日期欄中的最小值。<br /> </td> 
   <td> 最小值(&lt;值&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>總計</strong>、總和<br /> </td> 
   <td> 傳回數值欄中值的總和。<br /> </td> 
   <td> 總計(&lt;值&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## 表示法 {#representation}

表示功能用於訂購值。

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Name</strong><br /> </td> 
   <td> <strong>說明</strong><br /> </td> 
   <td> <strong>語法</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> 套用遞減排序<br /> </td> 
   <td> desc(&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>orderBy</strong><br /> </td> 
   <td> 在分割中排序結果<br /> </td> 
   <td> orderBy(&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Partionby</strong><br /> </td> 
   <td> 剖析表格上查詢的結果<br /> </td> 
   <td> Partitionby(&lt; value1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RoWWum</strong><br /> </td> 
   <td> 根據表格劃分和排序順序產生行號。MySQL不支援此函數<br /> </td> 
   <td> RownNum(PartitionBy(&lt; value1&gt;)，orderBy(&lt; value1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

