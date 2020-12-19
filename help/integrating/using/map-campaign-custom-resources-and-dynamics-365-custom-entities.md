---
solution: Campaign Standard
product: campaign
title: 對應 Campaign 自訂資源和 Dynamics 365 自訂實體
description: 瞭解如何在Adobe Campaign Standard和Microsoft Dynamics 365整合的背景下，對應資源和實體。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 9%

---


# 對應促銷活動資源和Dynamics 365實體

瞭解如何在Adobe Campaign Standard和Microsoft Dynamics 365整合的背景下，對應自訂資源和自訂實體。

>[!CAUTION]
>
>這項功能無法立即在產品中使用。此實作需要 Adobe Consulting 參與。請洽詢您的 Adobe 代表以瞭解更多資訊。

## 必要條件

[Microsoft Dynamics 365-Adobe Campaign Standard整合](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)支援自訂實體，讓Dynamics 365中的自訂實體與Campaign中的對應自訂資源同步。

自訂資源中的新資料可用於數種用途，包括分段和個人化。

整合支援連結和非連結的表格。 連結最多支援三個級別（即級別1->級別2->級別3）。

>[!CAUTION]
>
>如果任何促銷活動自訂資源記錄包含個人資訊，則會套用特定建議。 瞭解本節[的更多資訊。](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources)

## 通知

設定自訂實體資料流時，請務必注意下列事項：

* 建立和修改促銷活動自訂資源是敏感作業，必須由專業使用者執行。
* 對於自訂實體資料流，必須在Dynamics 365中為同步化的自訂實體啟用變更追蹤。
* 如果在Dynamics 365中建立父記錄和連結的子記錄時，由於並行處理整合，因此在其父記錄之前，可能會將新的子記錄寫入Campaign。

* 如果父記錄和子記錄使用&#x200B;**1基數簡單連結**&#x200B;選項在促銷活動方面連結，子記錄將保持隱藏且無法存取（透過UI或API），直到父記錄到達Campaign。

* （假設促銷活動中&#x200B;**1基數簡單連結**）如果子記錄在Dynamics 365中更新或刪除，且該變更在父記錄顯示於促銷活動之前已寫入促銷活動（不可能，但是遠端可能），該更新或刪除不會在促銷活動中處理，且會擲回錯誤。 在更新時，相關記錄需要在Dynamics 365中再次更新，才能同步更新的記錄。 若是刪除，相關記錄需要在促銷活動端個別處理，因為Dynamics 365中不再有要刪除或更新的記錄。

* 如果您遇到您認為有隱藏的子記錄而無法訪問這些記錄的情況，可以暫時將基數連結類型更改為&#x200B;**0或1基數簡單連結**&#x200B;以訪問這些記錄。

有關促銷活動自訂資源的更完整概觀，請參閱本節[。](../../developing/using/key-steps-to-add-a-resource.md)
