---
title: 以電子郵件傳送Designer常見問答
description: 關於電子郵件Designer的常見問題集。
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
ht-degree: 3%

---

# 以電子郵件傳送Designer常見問答

## 內容區塊與內容片段之間有何差異？

內容區塊和內容片段是可重複使用的內容片段，在多個電子郵件中很常見。 這些用於確保電子郵件的一致性，也用於最佳化/標準化電子郵件建立。 內容區塊與內容片段之間的差異在於可能的自訂層級。

* 內容區塊是手動插入HTML程式碼的純HTML（不方便使用的UI，它是直接原始程式碼）。 雖然它的目標客戶是具有HTML知識的人，但此產品可讓內容片段不提供個人化等級。

* 內容片段是使用使用者易記的UI，透過電子郵件Designer建立的視覺內容片段。 但是，無法個人化內容。 如果需要個人化，則只能透過內容區塊完成。

## 如何從HTML結構將邊框間距新增至元素？

您可以使用HTML階層連結來新增邊框間距。

1. 在畫面左下方，按一下HTML階層連結。

   ![](assets/do-not-localize/breadcrumb.png)

1. 按一下您要新增邊框間距的元素。
1. 按一下HTML階層連結中的父標籤。
您現在可以新增邊框間距至此元素。

## 我可以在電子郵件Designer中匯入HTML內容嗎？

您可以將自己的HTML內容上傳到電子郵件Designer。 如果尚未透過電子郵件Designer建立，則會以相容性模式載入，這種模式旨在保留您的原始HTML，但限制透過UI的某些版本功能。

如需詳細資訊，請參閱[相容性模式](../../designing/using/using-existing-content.md#compatibility-mode)

## 如何建立我的第一封電子郵件內容？

首先，從首頁建立電子郵件。
然後，若要將內容新增至電子郵件，您需要新增結構元件，並在其中插入內容元件。

如需詳細資訊，請參閱[從頭開始建立電子郵件](../../designing/using/quick-start.md#from-scratch-email)

## 為什麼我需要更新片段？

電子郵件設計工具正在不斷改進。如果您從草稿開始、從現成可用的範本建立電子郵件內容，或是如果您建立了片段，您可能需要將內容更新至最新版本，以避免CSS衝突問題之類的問題。

如需詳細資訊，請參閱[更新片段](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## 我可以在佈景主題中儲存樣式嗎？

樣式無法儲存為主題，以供日後重複使用。不過，CSS樣式可以儲存在內容範本或電子郵件中。

如需詳細資訊，請參閱[樣式](../../designing/using/styles.md)

## 有哪些字型可用？

在編輯樣式時，根據預設，只有大多數電子郵件使用者端正式支援的網頁字型才能透過UI使用。 使用自訂字型需要更新HTML程式碼。
