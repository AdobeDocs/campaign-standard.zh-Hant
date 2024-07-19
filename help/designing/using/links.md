---
title: 新增連結
description: 探索如何使用電子郵件Designer管理連結。
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
ht-degree: 4%

---

# 新增連結 {#links}

## 插入連結 {#inserting-a-link}

編輯器可讓您將連結插入HTML內容元素中，以個人化電子郵件或登入頁面。

您可以將連結插入任何頁面元素中：影像、單字、字群組、文字區塊等。

>[!NOTE]
>
>下列影像顯示如何在電子郵件中使用[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)插入連結。

1. 選取元素，然後從內容工具列按一下&#x200B;**[!UICONTROL Insert link]**。

   ![](assets/des_insert_link.png)

1. 選擇您要建立的連結型別：

   * **外部連結**：插入外部URL的連結。

     您可以定義URL的個人化。 請參閱[個人化URL](personalization.md#personalizing-urls)。

   * **登陸頁面**：授予Adobe Campaign登陸頁面的存取權。
   * **訂閱連結**：插入連結以訂閱Adobe Campaign服務。
   * **取消訂閱連結**：插入取消訂閱Adobe Campaign服務的連結。
   * 定義動作的&#x200B;**連結**：當登陸頁面中的專案被點按時，定義動作。

     >[!NOTE]
     >
     >此型別的連結僅適用於登陸頁面。

1. 您可以修改顯示給收件者的文字。
1. 您可以設定使用者按一下連結時的瀏覽器行為（例如，開啟新視窗）。

   >[!NOTE]
   >
   >定義瀏覽器行為僅適用於登陸頁面。

1. 儲存您的變更。

建立連結後，您仍可從「設定」窗格修改連結。 按一下鉛筆圖示以編輯其引數。

![](assets/des_link_edit.png)

使用[電子郵件Designer](../../designing/using/designing-content-in-adobe-campaign.md)編輯電子郵件時，您可以從列出電子郵件中所有URL的表格輕鬆存取及修改您建立的連結。 此清單可讓您集中檢視並找出電子郵件內容中的每個URL。 若要存取它，請參閱[關於追蹤的URL](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>個人化URL （例如&#x200B;**映象頁面URL**&#x200B;或&#x200B;**取消訂閱**&#x200B;連結）無法從此清單修改。 所有其他連結皆可編輯。

**相關主題**：

* [插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)
* [新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)
* [在電子郵件中](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 關於追蹤的URL {#about-tracked-urls}

Adobe Campaign可讓您在收件者按一下電子郵件中包含的URL時，追蹤收件者的行為。 如需追蹤的詳細資訊，請參閱[本節](../../sending/using/tracking-messages.md#about-tracking)。

動作列中的&#x200B;**[!UICONTROL Links]**&#x200B;圖示會自動顯示要追蹤之內容的所有URL清單。

![](assets/des_links.png)

>[!NOTE]
>
>預設會啟用追蹤。 只有在Adobe Campaign中啟用追蹤時，此功能才可用於電子郵件。 如需追蹤引數的詳細資訊，請參閱[本節](../../administration/using/configuring-email-channel.md#tracking-parameters)。

每個連結的URL、類別、標籤和追蹤型別都可在此清單中修改。 若要編輯連結，按一下對應的鉛筆圖示。

![](assets/des_links_tracking.png)

對於每個追蹤的URL，您可將追蹤模式設定為下列其中一個值：

* **已追蹤**：啟用此URL上的追蹤。
* **映象頁面**：認為此URL是映象頁面URL。
* **從不**：從不啟用此URL的追蹤。 此資訊會儲存：如果URL再次出現在將來的訊息中，其追蹤會自動停用。
* **選擇退出**：將此網址視為選擇退出或取消訂閱URL。

![](assets/des_link_tracking_type.png)

您也可以停用或啟用每個URL的追蹤。

>[!NOTE]
>
>在Adobe Campaign中，預設會追蹤所有內容URL，但&#x200B;**映象頁面URL**&#x200B;和&#x200B;**取消訂閱**&#x200B;連結除外。

您可以根據郵件中使用的URL，編輯&#x200B;**[!UICONTROL Category]**&#x200B;欄位來重新分組您的URL。 這些類別可以顯示報表，例如在[URL和點選串流](../../reporting/using/urls-and-click-streams.md)中。

![](assets/des_link_tracking_category.png)

建立報表時，從&#x200B;**[!UICONTROL Components]**&#x200B;索引標籤中選取&#x200B;**[!UICONTROL Dimension]**，然後向下捲動清單以存取追蹤元件。 例如，將&#x200B;**[!UICONTROL Tracking URL Category]**&#x200B;拖放到工作區中，以根據每個點按URL的追蹤類別來顯示結果。

![](assets/des_link_tracking_report.png)

如需建立自訂報表的詳細資訊，請參閱[本節](../../reporting/using/about-dynamic-reports.md)。
