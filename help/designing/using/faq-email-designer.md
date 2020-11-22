---
solution: Campaign Standard
product: campaign
title: '電子郵件設計人員常見問題 '
description: 電子郵件設計人員的常見問題。
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 7%

---


# 電子郵件設計人員常見問題

## 內容區塊和內容片段之間有何差異？

內容區塊和內容片段是可重複使用的內容片段，在多封電子郵件中是共通的。 這些功能可確保電子郵件的一致性，並最佳化／標準化電子郵件建立。 內容區塊和內容片段之間的差異是可自訂的層級。

* 內容區塊是純HTML，其中手動插入HTML程式碼（不方便使用的UI，它是直接原始碼）。 雖然它確實以具備HTML知識的人為導向，但卻允許內容片段無法提供個人化等級。

* 內容片段是透過電子郵件設計人員使用其使用者友好UI建立的視覺化內容片段。 但是，無法個人化內容。 如果需要個人化，則只能透過內容區塊進行。

## 如何從HTML結構新增填補至元素？

您可以使用HTML網頁導覽路徑標示來新增填補空白。

1. 在畫面左下角，按一下HTML網路導覽路徑標示。

   ![](assets/do-not-localize/breadcrumb.png)

1. 按一下要添加填充的元素。
1. 按一下HTML網站導覽路徑標示中的父標籤。
您現在可以在此元素中加上填補。

## 我可以在電子郵件設計工具中匯入HTML內容嗎？

您可以將自己的HTML內容上傳到電子郵件設計器。 如果尚未透過電子郵件設計工具建立，則會以相容模式載入，以保留原始HTML，但會限制透過UI的特定版本功能。

有關詳細資訊，請參閱「兼 [容性」模式](../../designing/using/using-existing-content.md#compatibility-mode)

## 如何建立我的第一個電子郵件內容？

首先，從首頁建立電子郵件。
然後，若要新增內容至電子郵件，您需要新增結構元件，並在其中插入內容元件。

如需詳細資訊，請參閱從頭 [開始建立電子郵件](../../designing/using/quick-start.md#from-scratch-email)

## 我為何需要更新片段？

電子郵件設計工具正在不斷改進。如果您從頭開始建立電子郵件內容、從現成可用的範本建立內容，或者如果您已建立片段，您可能需要將內容更新至最新版本，以避免發生CSS衝突等問題。

如需詳細資訊，請參閱「更 [新片段」](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## 我可以在主題中儲存樣式嗎？

樣式無法儲存為主題，以供日後重複使用。不過，CSS 樣式可以儲存在內容範本或電子郵件中。

如需詳細資訊，請參閱樣 [式](../../designing/using/styles.md)

## 哪些字型可用？

編輯樣式時，大部分電子郵件用戶端都會正式支援的網頁字型，依預設只能透過UI使用。 使用自訂字型需要更新HTML程式碼。
