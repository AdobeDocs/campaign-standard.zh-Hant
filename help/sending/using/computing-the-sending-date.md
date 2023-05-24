---
title: 計算傳送日期
description: 瞭解如何在特定日期和時間發送消息。
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7a0cd10a-24e6-44d1-842c-2067bfbac838
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 1%

---

# 計算傳送日期{#computing-the-sending-date}

您可以定義一個公式，以在特定日期和時間將消息發送給每個收件人。

## 自定義日期公式 {#customizing-date-formula}

例如，在升級過程中可以使用發送時間優化。

當使用新平台發送電子郵件時，Internet服務提供商(ISP)對無法識別的IP地址表示懷疑。 如果突然發送了大量電子郵件， ISP通常會將其標籤為垃圾郵件。

為避免被標籤為垃圾郵件，您可以通過在不同時間分發大量電子郵件來逐步增加發送量。 這應確保啟動階段的順利開發，並使您能夠降低無效地址的總體速率。

例如，您可以隨機分段目標受眾，以將交貨分為五批。 您將在6月1日上午10點發送第一批代表目標受眾的10% ，在24小時後發送第二批代表15%的受眾，依此類推。

您可以使用工作流計畫此項。

![](assets/send-time_opt_workflow1.png)

1. 訪問市場營銷活動清單並建立新工作流。 請參閱 [建立工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 拖放 **查詢** 活動並將其開啟。 查看 [查詢](../../automating/using/query.md) 的子菜單。
1. 選擇一個受眾，例如所有金牌客戶，然後按一下 **[!UICONTROL Confirm]** 的子菜單。
1. 拖放 **分段** 活動並將其開啟。 查看 [分段](../../automating/using/segmentation.md) 的子菜單。
1. 定義五個段。 對於每個段：

   * 填寫 **[!UICONTROL Segment code]** 欄位：手動輸入發送消息所需的日期和時間。

      例如，您希望在6月1日上午10點(GMT+1)發送第一批批。 使用以下格式： **YYYY-MM-DD hh:mm:ss+tz**。

      ![](assets/send-time_opt_segment_configuration.png)

      要在次日發送下一批，請輸入 **2017-06-02 10:00:00+01** 的下界。

      對於其餘段，按以下方式定義下一批：

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * 確保您選擇 **[!UICONTROL Limit the population of this segment]** 的雙曲餘切值。

      在 **[!UICONTROL Limitation]** 頁籤 **[!UICONTROL Random sampling]** 並輸入每個段的所需百分比：第一批10，第二批15，依此類推。

      ![](assets/send-time_opt_segment_limitation.png)


1. 定義所有段後，選擇 **[!UICONTROL Generate all segments in the same transition]** 按一下 **[!UICONTROL Confirm]**。

   ![](assets/send-time_opt_segment_dates.png)

1. 拖放 **電子郵件傳遞** 活動並將其開啟。 查看 [電子郵件傳遞](../../automating/using/email-delivery.md) 的子菜單。
1. 按一下 **[!UICONTROL Schedule]** 選擇 **[!UICONTROL Messages to be sent automatically on the date specified below]**。
1. 在 **[!UICONTROL Start sending from]** 欄位中定義聯繫日期。
1. 從「發送時間優化」下拉菜單中，選擇 **[!UICONTROL Send at a custom date defined by a formula]**。
1. 按一下 **[!UICONTROL Edit an expression]** 按鈕 **[!UICONTROL Custom date formula]** 的子菜單。

   ![](assets/send-time_opt_formula_define.png)

1. 使用 **[!UICONTROL ToDateTime]** 函式和 **[!UICONTROL Segment code]** 的子菜單。 您也可以直接鍵入表達式，但確保使用正確的語法和拼寫。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   的 **[!UICONTROL ToDateTime]** 函式將段代碼從文本字串轉換為日期和時間值。

   確認表達式以返回上一個螢幕。

   ![](assets/send-time_opt_formula_define_segment.png)

   在 **[!UICONTROL Schedule]** 的子菜單。

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. 確認計畫、保存交貨並執行工作流。

將在五天內逐步向所有目標收件人發送遞送。

>[!NOTE]
>
>確認發送時，確保所有日期都在將來。 否則，在確認發送後立即發送消息。

## 使用運算式 {#using-an-expression}

發送時間優化對於涉及呼叫中心的活動也很有用。 您可以確保不同時接收所有消息。 這樣，您的組織就可以根據其能力處理呼叫數。

例如，您希望發送電子郵件，邀請客戶與呼叫中心聯繫以獲得促銷優惠。 為避免呼叫中心不堪重負，您決定隨機將目標受眾分成四批發送電子郵件。

您可以使用工作流計畫此項。

![](assets/send-time_opt_workflow2.png)

1. 訪問市場營銷活動清單並建立新工作流。 請參閱 [建立工作流](../../automating/using/building-a-workflow.md#creating-a-workflow)。
1. 拖放 **查詢** 活動並將其開啟。 查看 [查詢](../../automating/using/query.md) 的子菜單。
1. 選擇一個受眾，例如超過35個配置檔案，然後按一下 **[!UICONTROL Confirm]** 的子菜單。
1. 拖放 **分段** 活動並將其開啟。 查看 [分段](../../automating/using/segmentation.md) 的子菜單。
1. 定義四個段。 對於每個段：

   * 定義段代碼如下：

      * 上午8:00 — 上午10:00: **0**。 消息將在上午8:00（聯繫日期）發送到目標人口的第一季度。
      * 上午10:00 — 中午12:00 : **2**。 消息將在上午10:00（聯繫日期+ 2小時）發送到目標人口的第二季度。
      * 下午2:00 — 下午4:00 : **6**。 呼叫中心在中午12:00至下午2:00之間關閉，消息將在下午2:00（聯繫日期+ 6小時）發送到目標人口的第三季度。
      * 下午4:00 — 下午6:00 : **8**。 消息將在下午4:00（聯繫日期+ 8小時）發送到目標人口的最後一個季度。

      >[!NOTE]
      >
      >聯繫日期將在工作流稍後的「電子郵件傳遞」活動中定義。

   * 確保您選擇 **[!UICONTROL Limit the population of this segment]** 的雙曲餘切值。
   * 在 **[!UICONTROL Limitation]** 頁籤 **[!UICONTROL Random sampling]** 並輸入每個段的所需百分比： **25**。


1. 定義所有段後，選擇 **[!UICONTROL Generate all segments in the same transition]** 按一下 **[!UICONTROL Confirm]**。

   ![](assets/send-time_opt_segment.png)

1. 拖放 **電子郵件傳遞** 活動並將其開啟。 查看 [電子郵件傳遞](../../automating/using/email-delivery.md) 的子菜單。
1. 按一下 **[!UICONTROL Schedule]** 中。
1. 選取 **[!UICONTROL Messages to be sent automatically on the date specified below]**。
1. 在 **[!UICONTROL Start sending from]** 欄位中定義聯繫日期。

   在此示例中，選擇5月25日上午8:00。

1. 從「發送時間優化」下拉菜單中，選擇 **[!UICONTROL Send at a custom date defined by a formula]** 並按一下 **[!UICONTROL Edit an expression]** 按鈕

   ![](assets/send-time_opt_formula_expression.png)

1. 在 **[!UICONTROL Expression editor]**，設定日期和段代碼以計算每個客戶的資料。

   在函式清單中，選擇 **[!UICONTROL AddHours]**。

   ![](assets/send-time_opt_formula_expression_addhours.png)

   在可用欄位中，選擇 **[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**。

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   這使您能夠檢索在 **[!UICONTROL Start sending from]** 的子菜單。

   在函式清單中，選擇 **[!UICONTROL ToInteger]**。 在可用欄位中，選擇 **[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**。

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   這使您能夠檢索在段代碼中指定的數字。

   您應得到以下公式：

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. 確認保存表達式。 確認計畫、保存交貨並執行工作流。

* 第一段將在聯繫日（5月25日上午8點）收到消息。
* 第二段將在兩小時後（5月25日上午10點）收到消息。
* 第三段將在六小時後（5月25日下午2:00）收到消息。
* 第四段將在八小時後（5月25日下午4點）收到消息。
