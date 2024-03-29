---
title: Adobe Campaign Standard 中的協助工具
description: 瞭解 Adobe Campaign Standard 工作區中的協助工具支援。
audience: designing
content-type: reference
topic-tags: accessibility
feature: Campaigns
role: User
level: Intermediate
exl-id: 958f7beb-ab41-4492-bc0a-e9e342e3c12e
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 100%

---

# Adobe Campaign Standard 中的協助工具 {#accessibility-acs}

瞭解 Adobe Campaign Standard 工作區中的協助工具支援。

協助工具是指讓產品適用於視覺、聽覺、認知、運動和其他殘疾人士。軟體產品的協助功能範例包括語義結構化內容、螢幕閱讀器支援、圖形的文字等效功能、鍵盤快速鍵等。

Adobe Campaign Standard 提供多種功能，讓您能更輕鬆使用對比、標籤、結構化內容、鍵盤導覽和內容相關說明等內容。

## 協助工具功能 {#accessibility-features}

### 對比和顏色 {#contrast}

Adobe Campaign Standard 使用者介面致力於在應用程式中提供足夠的對比功能，以確保為視力不足或色彩缺乏的使用者提供可存取的檢視體驗。

* 大型文字和標題已增強，以符合 3:1 的對比。

  ![](assets/accessibility_2.png)

* 應用程式中的說明內容和內文已更新，以符合 4.5:1 的對比。

* 工作流程的暫停和取消圖示已更新為改善背景和前景顏色之間的對比。

  ![](assets/accessibility_1.png)

* 顏色、形狀和位置並非在應用程式中傳達資訊或階層的唯一方法。

### 使用者介面 {#user-interface}

Adobe Campaign Standard 使用者介面可讓所有使用者更輕鬆地與內容互動，方法是在視覺元素中加入替代文字，並使用語義結構以視覺化和程式設計方式傳達資訊。

* 當使用者將必要的 ID 欄位留空時，圖形會以視覺化方式指出哪個欄位有錯誤訊息文字，並以程式設計方式將相同的資訊傳送給使用者，例如螢幕閱讀器等輔助技術。

  ![](assets/accessibility_3.png)

* 顯示在暫留或焦點上的內容可由使用者關閉，而不會遮蔽其他內容。

  ![](assets/accessibility_4.png)

* 已新增影像的替代文字和按鈕的可存取名稱，並可使用輔助技術朗讀，而非僅依賴視覺提示來識別元素。

<!--
### Create responsive resize for multiple devices {#resize-devices}

When designing for multiple devices and platforms, it's important to create a seamless experience for screen sizes across mobile and desktop resolutions.

Adobe Campaign Standard allows you to design and test emails and push notifications on different devices such as: iPhone, Android devices, iPad, Android tablet and desktop.

![](assets/accessibility_6.png)
-->

## 內容說明 {#contextual-help}

內容說明可協助您更清楚瞭解可用的不同請求欄位和功能。它也會引導您閱讀產品文件，以進一步瞭解所選功能的資訊。

在設計電子郵件時，您可以存取工具提示，其中提供功能說明和產品檔案的連結。

![](assets/accessibility_7.png)

## 支援協助技術 {#screen-magnifiers}

我們致力於讓 Adobe Campaign Standard 應用程式能透過各種輔助技術而徹底發揮效用，包含但不限於修改過鍵盤、螢幕放大軟體、螢幕閱讀器、語音辨識軟體和其他輔助裝置。

## 使用您的偏好語言 {#languages}

Adobe Campaign Standard 提供不同的語言版本：英文、法文和德文。

請注意，語言是在安裝時已設定好的，之後無法變更。

## 鍵盤快速鍵 {#shortcuts}

### 首頁 {#homepage-shortcuts}

| 動作 | 快速鍵 |
| --- | --- |
| 介紹使用者介面的個別元件 | 標籤 |
| 啟用選取的項目 | 輸入或空格鍵 |

### 電子郵件設計工具 {#email-designer-shortcuts}

| 動作 | Windows 捷徑 | macOS 捷徑 |
| --- | --- | --- |
| 還原 | Ctrl + Z | Command + Z |
| 取消還原 | Ctrl + Y | Shift + Command + Z |

### 動態報告 {#report-shortcuts}

| 動作 | Windows 捷徑 | macOS 捷徑 |
| --- | --- | --- |
| 開啟專案 | Ctrl + O | Command + O |
| 儲存 | Ctrl + S | Command + S |
| 儲存為 | Shift + Ctrl + S | Shift + Command + S |
| 重新整理專案 | Alt + R | Command + R |
| 下載 CSV 檔案 | Shift + Ctrl + V | Shift + Command + V |
| 列印 | Alt + P | Command + P |
| 還原 | Ctrl + Z | Command + Z |
| 取消還原 | Ctrl + Y | Shift + Command + Z |
| 新的空白面板 | Alt + B | Option + B |
| 新的創意筆 | Alt + A | Option + A |
| 新的創意筆表格 | Alt + 1 | Option + 1 |
| 新行 | Alt + 2 | Option + 2 |
| 新列 | Alt + 3 | Option + 3 |
| 立即傳送報告 | Alt + S | Option + S |
| 依排程傳送報告 | Shift + Alt + S | Shift + Option + S |
| 已排程報告 | Shift + Alt + L | <!-- Should be 'Shift + Option + L ' but does not work on Mac --> |

## 進一步閱讀 {#further-reading}

Adobe Campaign Standard 致力於提供日益提升功能的協助工具，讓產品更易於每個人使用。

建議您使用 [Adobe 協助工具意見回饋格式](https://www.adobe.com/accessibility/feedback.html)來傳送您遇到的改善建議和協助工具的問題。

您也可以參閱 [Adobe Campaign Standard 發行說明](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=zh-Hant#release-notes)，以遵循最新的改善與功能。
