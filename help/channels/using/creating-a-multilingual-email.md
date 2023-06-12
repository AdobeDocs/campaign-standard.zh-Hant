---
title: 建立多語言電子郵件
description: 請依照下列步驟，建立使用不同慣用語言的多語言電子郵件目標定位收件者。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
source-git-commit: d234d7fab039b602eff06c03ba0d8f7ce2a0cf3f
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# 建立多語言電子郵件{#creating-a-multilingual-email}

您可以傳送多語言電子郵件給使用不同偏好語言的設定檔：每個設定檔都會收到以其偏好語言撰寫的電子郵件變體。

若要這麼做，請檢查您是否有可用的多語言電子郵件範本。 如果沒有，請瞭解如何在中建立一個 [本節](../../channels/using/multilingual-messages-template.md).

對象是根據具有完整偏好語言資訊的個人檔案。

1. 根據建立新電子郵件 [多語言範本](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. 定義電子郵件的一般屬性與目標對象，就像標準電子郵件一樣。請參閱[建立對象](../../audiences/using/creating-audiences.md)區段。

1. 在建立精靈的第四步，定義變體選項。 如果 [多語言範本](../../channels/using/multilingual-messages-template.md) 已經包含所有正確的引數，您可以直接按一下 **[!UICONTROL Create]** 按鈕。

   ![](assets/multi_create4.png)

   如有需要，請使用 **[!UICONTROL Add an element]** 按鈕。 **[!UICONTROL Default]** 不得刪除變體。 當設定為 **[!UICONTROL default]**， [設定檔的偏好語言](../../audiences/using/creating-profiles.md) 用於選擇變體。 您也可以設定 **[!UICONTROL Default]** 變體至任何其他語言。

1. 確認電子郵件建立：接著會顯示電子郵件控制面板。
1. 定義每個變體的電子郵件內容。 根據您所選取的範本，您可以定義多個主旨、數個寄件者名稱或數個不同內容。使用下拉式功能表，在元素的不同變體之間導覽。 如需詳細資訊，請參閱[內容編輯器](../../designing/using/designing-content-in-adobe-campaign.md)區段。

   ![](assets/multi_selectcontent.png)

1. 測試及驗證您的訊息。 請參閱 [傳送證明](../../sending/using/sending-proofs.md) 區段。
1. 使用排程傳送 **[!UICONTROL Send after confirmation option]**.
1. 傳送電子郵件後，您可以存取其記錄和報告，以評估行銷活動的成功。 如需報告的詳細資訊，請參閱[本區段](../../reporting/using/about-dynamic-reports.md)。

