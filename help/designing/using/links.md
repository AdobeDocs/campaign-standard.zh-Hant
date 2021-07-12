---
solution: Campaign Standard
product: campaign
title: 新增連結
description: 了解如何使用電子郵件設計工具管理連結。
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: 電子郵件設計
role: User
level: Intermediate
exl-id: d1714101-bad0-40c1-8d60-90469d033197
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 2%

---

# 新增連結 {#links}

## 插入連結 {#inserting-a-link}

編輯器可讓您將連結插入HTML內容元素，以個人化電子郵件或登錄頁面。

您可以將連結插入任何頁面元素中：影像、字、字組、文字區塊等。

>[!NOTE]
>
>下圖顯示如何使用電子郵件中的[電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)插入連結。

1. 選取元素，然後從內容工具列按一下&#x200B;**[!UICONTROL Insert link]**。

   ![](assets/des_insert_link.png)

1. 選擇要建立的連結類型：

   * **外部連結**:插入外部URL的連結。

      您可以為URL定義個人化。 請參閱[個人化URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

   * **登陸頁面**:提供Adobe Campaign登錄頁面的存取權。
   * **訂閱連結**:插入可訂閱Adobe Campaign服務的連結。
   * **取消訂閱連結**:插入連結以取消訂閱Adobe Campaign服務。
   * **定義動作的連結**:定義按一下登錄頁面中的元素時的動作。

      >[!NOTE]
      >
      >此類型的連結僅適用於登錄頁面。

1. 您可以修改向收件者顯示的文字。
1. 您可以在使用者按一下連結時設定瀏覽器行為（例如，開啟新視窗）。

   >[!NOTE]
   >
   >定義瀏覽器行為只會套用至登錄頁面。

1. 儲存您的變更。

建立連結後，您仍可從「設定」窗格修改該連結。 按一下鉛筆圖示以編輯其參數。

![](assets/des_link_edit.png)

使用[電子郵件設計工具](../../designing/using/designing-content-in-adobe-campaign.md)編輯電子郵件時，您可以輕鬆存取和修改您從清單電子郵件中所包含所有URL的表格中建立的連結。 此清單可讓您集中檢視，並找出電子郵件內容中的每個URL。 若要存取，請參閱[關於追蹤的URL](#about-tracked-urls)。

![](assets/des_link_list.png)

>[!NOTE]
>
>無法從此清單修改個人化URL，例如&#x200B;**鏡像頁面URL**&#x200B;或&#x200B;**取消訂閱**&#x200B;連結。 所有其他連結都可編輯。

**相關主題**：

* [插入個人化欄位](../../designing/using/personalization.md#inserting-a-personalization-field)
* [新增內容區塊](../../designing/using/personalization.md#adding-a-content-block)
* [定義動態內容](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## 關於追蹤的URL {#about-tracked-urls}

Adobe Campaign可讓您在收件者點按電子郵件中包含的URL時追蹤其行為。 如需追蹤的詳細資訊，請參閱[本節](../../sending/using/tracking-messages.md#about-tracking)。

動作列中的&#x200B;**[!UICONTROL Links]**&#x200B;圖示會自動顯示要追蹤之內容的所有URL清單。

![](assets/des_links.png)

>[!NOTE]
>
>預設會啟用追蹤。 若已在Adobe Campaign中啟動追蹤，則此功能僅適用於電子郵件。 如需追蹤參數的詳細資訊，請參閱[此區段](../../administration/using/configuring-email-channel.md#tracking-parameters)。

每個連結的URL、類別、標籤和追蹤類型可從此清單修改。 若要編輯連結，請按一下對應的鉛筆圖示。

![](assets/des_links_tracking.png)

對於每個追蹤的URL，您可以將追蹤模式設為下列其中一個值：

* **追蹤**:在此URL上啟用追蹤。
* **鏡像頁面**:將此URL視為鏡像頁面URL。
* **從不**:切勿啟用此URL的追蹤。此資訊已儲存：如果URL在未來的訊息中再次出現，其追蹤會自動停用。
* **退出**:將此URL視為選擇退出或取消訂閱URL。

![](assets/des_link_tracking_type.png)

您也可以停用或啟用每個URL的追蹤。

>[!NOTE]
>
>依預設，在Adobe Campaign中，除了&#x200B;**鏡像頁面URL**&#x200B;和&#x200B;**取消訂閱**&#x200B;連結之外，所有內容URL都會受到追蹤。

您可以根據訊息中使用的URL，編輯&#x200B;**[!UICONTROL Category]**&#x200B;欄位來重新分組您的URL。 這些類別可以顯示報告，例如在[URL中，然後按一下流](../../reporting/using/urls-and-click-streams.md)。

![](assets/des_link_tracking_category.png)

建立報表時，從&#x200B;**[!UICONTROL Components]**&#x200B;標籤中選取&#x200B;**[!UICONTROL Dimension]**&#x200B;並向下捲動清單以存取追蹤元件。 例如，將&#x200B;**[!UICONTROL Tracking URL Category]**&#x200B;拖放至工作區，以根據每個點按URL的追蹤類別顯示結果。

![](assets/des_link_tracking_report.png)

如需建立自訂報表的詳細資訊，請參閱[此區段](../../reporting/using/about-dynamic-reports.md)。
