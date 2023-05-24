---
title: 電子郵件設計人員常見問題
description: 有關電子郵件設計器的常見問題。
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Email Design
role: User
level: Intermediate
exl-id: f3208380-a4cf-4944-aa24-883995d1075d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 7%

---

# 電子郵件設計人員常見問題

## 內容塊和內容片段之間有何區別？

內容塊和內容片段是可重複使用的內容片段，這些內容在多個電子郵件中很常見。 這些功能用於確保電子郵件的一致性，還用於優化/標準化電子郵件建立。 內容塊和內容片段之間的差異是可能的定製級別。

* 內容塊是純HTML，其中手動插入HTML代碼（不是用戶友好的UI，而是直接原始碼）。 雖然它確實面向具有HTML知識的人，但它允許內容片段中不具備個性化級別。

* 內容片段是通過電子郵件設計器使用其用戶友好的UI建立的可視內容。 但是，無法個性化內容。 如果需要個性化，則只能通過內容塊進行。

## 如何將填充添加到HTML結構中的元素？

可以使用HTMLbreadcrumb添加填充。

1. 在螢幕左下角，按一下HTMLbreadcrumb。

   ![](assets/do-not-localize/breadcrumb.png)

1. 按一下要添加填充的元素。
1. 按一下HTMLbreadcrumb中的父標籤。
現在可以向此元素添加填充。

## 是否可以在電子郵件設計器中導入HTML內容？

您可以將自己的HTML內容上載到電子郵件設計器。 如果尚未通過電子郵件設計器建立它，它將以相容模式載入，該模式旨在保持原始HTML，但通過UI限制某些版本功能。

有關詳細資訊，請參閱 [相容模式](../../designing/using/using-existing-content.md#compatibility-mode)

## 如何建立我的第一個電子郵件內容？

首先，從首頁建立電子郵件。
然後，要向電子郵件中添加內容，您需要添加結構元件，並在其中插入內容元件。

有關詳細資訊，請參閱 [從頭建立電子郵件](../../designing/using/quick-start.md#from-scratch-email)

## 為什麼需要更新片段？

電子郵件設計工具正在不斷改進。如果您從頭開始建立電子郵件內容、從現成模板建立電子郵件內容或建立片段，則可能需要將內容更新為最新版本以避免出現CSS衝突問題等問題。

有關詳細資訊，請參閱 [更新片段](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## 是否可以保存主題中的樣式？

樣式無法儲存為主題，以供日後重複使用。不過，CSS 樣式可以儲存在內容範本或電子郵件中。

有關詳細資訊，請參閱 [樣式](../../designing/using/styles.md)

## 哪些字型可用？

編輯樣式時，預設情況下，只有大多數電子郵件客戶端正式支援的Web字型才能通過UI使用。 使用自定義字型需要更新HTML代碼。
