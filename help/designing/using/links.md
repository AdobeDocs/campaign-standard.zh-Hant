---
title: 添加連結
description: 瞭解如何管理與電子郵件設計器的連結。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d1714101-bad0-40c1-8d60-90469d033197
source-git-commit: 146dfea38bd456a5d9200b0632d4aa279b10a7b9
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---

# 添加連結 {#links}

## 插入連結 {#inserting-a-link}

編輯器允許您通過將連結插入HTML內容元素來個性化電子郵件或登錄頁。

可以將連結插入任何頁元素：影像、單詞、單片語、文本塊等。

>[!NOTE]
>
>下圖顯示了如何使用 [電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md) 郵件里。

1. 選擇元素並按一下 **[!UICONTROL Insert link]** 的子菜單。

   ![](assets/des_insert_link.png)

1. 選擇要建立的連結類型：

   * **外部連結**:插入指向外部URL的連結。

      您可以為URL定義個性化。 請參閱 [個性化URL](personalization.md#personalizing-urls)。

   * **登錄頁**:訪問Adobe Campaign登錄頁。
   * **訂閱連結**:插入連結以訂閱Adobe Campaign服務。
   * **取消訂閱連結**:插入連結以取消訂閱Adobe Campaign服務。
   * **定義操作的連結**:按一下登錄頁中的元素時定義操作。

      >[!NOTE]
      >
      >此類連結僅可用於登錄頁。

1. 您可以修改顯示給收件人的文本。
1. 當用戶按一下連結（例如，開啟新窗口）時，可設定瀏覽器行為。

   >[!NOTE]
   >
   >定義瀏覽器行為僅適用於登錄頁。

1. 儲存您的變更。

建立連結後，您仍可以從「設定」窗格中修改該連結。 按一下鉛筆表徵圖可編輯其參數。

![](assets/des_link_edit.png)

使用 [電子郵件設計器](../../designing/using/designing-content-in-adobe-campaign.md)，您可以輕鬆訪問和修改從表中建立的連結，該表中列出了電子郵件中包含的所有URL。 此清單使您能夠有一個集中的視圖並查找電子郵件內容中的每個URL。 要訪問它，請參閱 [關於跟蹤的URL](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>個性化URL，如 **鏡像頁URL** 或 **取消訂閱** 無法從此清單修改連結。 所有其他連結都是可編輯的。

**相關主題**：

* [插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)
* [添加內容塊](../../designing/using/personalization.md#adding-a-content-block)
* [定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 關於跟蹤的URL {#about-tracked-urls}

Adobe Campaign允許您在收件人按一下電子郵件中包含的URL時跟蹤其行為。 如需追蹤的詳細資訊，請參閱[本節](../../sending/using/tracking-messages.md#about-tracking)。

的 **[!UICONTROL Links]** 表徵圖自動顯示要跟蹤的內容的所有URL的清單。

![](assets/des_links.png)

>[!NOTE]
>
>預設情況下，跟蹤被激活。 此功能僅在Adobe Campaign激活跟蹤後才可用於電子郵件。 有關跟蹤參數的詳細資訊，請參閱 [此部分](../../administration/using/configuring-email-channel.md#tracking-parameters)。

每個連結的URL、類別、標籤和跟蹤類型都可以從此清單中修改。 要編輯連結，請按一下相應的鉛筆表徵圖。

![](assets/des_links_tracking.png)

對於每個跟蹤的URL，可以將跟蹤模式設定為以下值之一：

* **跟蹤**:在此URL上激活跟蹤。
* **「鏡像」頁**:認為此URL是鏡像頁URL。
* **從不**:從不激活此URL的跟蹤。 此資訊已保存：如果URL在將來的消息中再次出現，則其跟蹤將自動停用。
* **選擇退出**:將此URL視為選擇退出或取消訂閱URL。

![](assets/des_link_tracking_type.png)

您還可以停用或激活每個URL的跟蹤。

>[!NOTE]
>
>預設情況下，在Adobe Campaign，將跟蹤除 **鏡像頁URL** 和 **取消訂閱** 的子菜單。

可以通過編輯 **[!UICONTROL Category]** 欄位，具體取決於消息中使用的URL。 這些類別可以顯示報告，例如 [URL並按一下流](../../reporting/using/urls-and-click-streams.md)。

![](assets/des_link_tracking_category.png)

生成報告時， **[!UICONTROL Components]** 頁籤 **[!UICONTROL Dimension]** 並向下滾動清單以訪問跟蹤元件。 例如，拖放 **[!UICONTROL Tracking URL Category]** 按照每個按一下的URL的跟蹤類別顯示結果。

![](assets/des_link_tracking_report.png)

有關構建自定義報告的詳細資訊，請參見 [此部分](../../reporting/using/about-dynamic-reports.md)。
