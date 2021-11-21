---
title: 產生多語言推播通知的CSV檔案並附上Campaign Standard
description: 上傳CSV檔案以產生要傳送的內容是支援多語言推播通知的功能。
audience: channels
content-type: reference
topic-tags: email-messages
feature: Push
role: User
level: Intermediate
exl-id: bd9ec3f9-e047-42dc-ab64-9fb274cb4656
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# 產生多語言推送通知的 CSV 檔案{#generating-csv-multilingual-push}

上傳CSV檔案以產生要傳送的內容是支援多語言推播通知的功能。 CSV檔案格式必須符合檔案上傳成功的特定准則，才能建立傳送。 以下幾節將說明檔案格式及其注意事項。

## 檔案格式 {#file-format}

多語言推播需要CSV檔案中的14欄：

1. title
1. messageBody
1. 聲音
1. 廣告
1. deeplinkURI
1. 類別
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMutableContent
1. customFields
1. 地區
1. 語言
1. silentPush

按一下 **[!UICONTROL Download a sample file]** 在 **[!UICONTROL Manage Content Variants]** 窗口。 有關詳細資訊，請參閱 [節](../../channels/using/creating-a-multilingual-push-notification.md).

* **title, messageBody，音效，徽章， deeplinkURI，類別， iosMediaAttachmentURL, androidMediaAttachmentURL**:一般推播裝載內容。 您需要以與建立推送傳送時類似的方式提供此資訊。
* **自訂欄位**:對自訂欄位使用JSON格式，例如 `{"key1":"value1","key2":"value2"}`. 如需自訂欄位的範例，請參閱上述範例檔案。
* **isContentAvailable**:「可用內容」檢查的標幟，值1表示true，值0表示false。 預設值為0。 如果此欄留空，則值會視為0。
* **isMutableContent**:可變內容的標幟，值1表示true，值0表示false。 預設值為0。 如果此欄留空，則值會視為0。
* **地區**:locale是語言變體的欄位，例如「en_us」代表美文 — 英文，「fr_fr」代表法文 — 法文。
* **語言**:與地區關聯的語言的名稱。 例如，如果地區設定為&quot;en_us&quot;，則語言的名稱應為&quot;English-United States&quot;。
* **silentPush**:推播通知類型的標幟。 如果是一般推播通知，則值應為0。 如果是靜默推送，則值應為1。 預設值為0。 如果此欄留空，則值會視為0。

## csv檔案建立的限制和准則 {#constraints-guideline-csv}

**每欄的名稱是固定的**.
您應在CSV檔案中加入各欄的名稱，如果您未對內容使用任何欄，請將其留空。

**&quot;locale&quot;和&quot;language&quot;列是必填欄，且值對每行都是唯一的。**
此欄的空白值會導致檔案上傳失敗。

**欄的順序很重要**. 上傳檔案中的欄順序必須遵循與範例檔案相同的格式。

**報價欄內容**. 由於這是CSV（代表逗號分隔值）檔案，因此任何包含逗號(,)的欄內容都必須加上引號。 例如，「你好，湯姆！」

**UTF-8編碼對於國際字元是必要的。**

**如果您以純文字產生檔案，請以「，」分隔每欄。**

**變體不匹配。** 如果您使用內容區塊和目標對象搭配特定語言，您必須在CSV檔案中列出每個目標語言，否則在傳送傳遞時會出現錯誤。

## 在csv檔案中插入個人化欄位 {#personalization-field-csv}

如果您想使用個人化欄位，應包含 <span> 標籤。

若要在messageBody中插入「firstName」個人化欄位，訊息必須是：

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

&quot;firstName&quot;欄位由：

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

在範圍中有兩個必要屬性：

* 一個是靜態的類。 無論您打算使用哪個個人化欄位，都一律為class=&quot;nl-dce-field nl-dce-done&quot;。

* 另一個是data-nl-expr，這是個人化欄位的路徑。 例如，如果您從UI插入「firstName」個人化欄位，則導覽路徑將是 **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** （如下圖所示）。 在此情況下，路徑將是

   ```
   /context/profile/firstName. data-nl-expr="/context/profile/firstName".
   ```

![](assets/multilingual_push_2.png)

## 地區和語言名稱 {#locale-language-names}

支援下列語言：

| 地區 | 語言 |
|:-:|:-:|
| af_za | 阿非利卡語 — 南非 |
| sq_al | 阿爾巴尼亞 — 阿爾巴尼亞 |
| ar_dz | 阿拉伯語 — 阿爾及利亞 |
| ar_bh | 阿拉伯文 — 巴林 |
| ar_iq | 阿拉伯語 — 伊拉克 |
| ar_il | 阿拉伯語 — 以色列 |
| ar_jo | 阿拉伯語 — 約旦 |
| ar_kw | 阿拉伯語 — 科威特 |
| ar_lb | 阿拉伯語 — 黎巴嫩 |
| ar_ma | 阿拉伯語 — 摩洛哥 |
| ar_om | 阿拉伯文 — 阿曼 |
| ar_qa | 阿拉伯語 — 卡達 |
| ar_sa | 阿拉伯語 — 沙烏地阿拉伯 |
| ar_sy | 阿拉伯語 — 敘利亞 |
| ar_tn | 阿拉伯語 — 突尼西亞 |
| ar_ae | 阿拉伯語 — 阿拉伯聯合大公國 |
| ar_ye | 阿拉伯文 — 葉門 |
| hy_am | 亞美尼亞 — 亞美尼亞 |
| az_az | 亞塞拜然 — 亞塞拜然 |
| be_by | 白俄羅斯 — 白俄羅斯 |
| bs_ba | 波斯尼亞 — 波斯尼亞 |
| bg_bg | 保加利亞語 — 保加利亞 |
| ca_es | 加泰羅尼亞語 — 西班牙 |
| zh_cn | 簡體中文 — 中國 |
| zh_sg | 簡體中文 — 新加坡 |
| zh_hk | 中文（繁體） — 香港 |
| zh_tw | 繁體中文 — 台灣地區 |
| hr_hr | 克羅埃西亞 — 克羅埃西亞 |
| cs_cz | 捷克語 — 切希亞 |
| da_dk | 丹麥語 — 丹麥 |
| nl_be | 荷蘭語 — 比利時 |
| nl_nl | 荷蘭語 — 荷蘭 |
| en_au | 英語 — 澳大利亞 |
| en_bz | 英語 — 貝里斯 |
| en_ca | 英語 — 加拿大 |
| en_in | 英語 — 印度 |
| en_ie | 英語 — 愛爾蘭 |
| en_jm | 英語 — 牙買加 |
| en_nz | 英語 — 紐西蘭 |
| en_ph | 英語 — 菲律賓 |
| en_za | 英語 — 南非 |
| en_tt | 英語 — 千里達和多巴哥 |
| en_gb | 英語 — 英國 |
| en_us | 英語 — 美國 |
| en_zw | 英語 — 辛巴威 |
| et_ee | 愛沙尼亞語 — 愛沙尼亞 |
| fi_fi | 芬蘭語 — 芬蘭 |
| fr_be | 法語 — 比利時 |
| fr_ca | 法語 — 加拿大 |
| fr_fr | 法語 — 法國 |
| fr_lu | 法語 — 盧森堡 |
| fr_ch | 法語 — 瑞士 |
| de_at | 德文 — 奧地利 |
| de_de | 德文 — 德國 |
| de_lu | 德語 — 盧森堡 |
| de_ch | 德文 — 瑞士 |
| el_cy | 希臘語 — 塞普勒斯 |
| el_gr | 希臘語 — 希臘 |
| gu_in | 古吉拉特語 — 印度 |
| he_il | 希伯來語 — 以色列 |
| hi_in | 印地語 — 印度 |
| hu_hu | 匈牙利語 — 匈牙利 |
| is_is | 冰島語 — 冰島 |
| id_id | 印度尼西亞 — 印度尼西亞 |
| it_it | 義大利語 — 義大利 |
| it_ch | 義大利語 — 瑞士 |
| ja_jp | 日文 — 日本 |
| kn_in | 坎納達 — 印度 |
| kk_kz | 哈薩克 — 哈薩克 |
| ko_kr | 韓語 — 韓國 |
| lv_lv | 拉脫維亞語 — 拉脫維亞 |
| lt_lt | 立陶宛語 — 立陶宛 |
| mk_mk | 馬其頓 — 馬其頓 |
| ms_my | 馬來語 — 馬來西亞 |
| mr_in | 馬拉地語 — 印度 |
| no_no | 挪威語 — 挪威 |
| pl_pl | 波蘭語 — 波蘭 |
| pt_br | 葡萄牙語 — 巴西 |
| pt_pt | 葡萄牙語 — 葡萄牙 |
| pa_in | 旁遮普語 — 印度 |
| ro_md | 羅馬尼亞語 — 摩爾多瓦 |
| ro_ro | 羅馬尼亞文 — 羅馬尼亞 |
| ru_kz | 俄文 — 哈薩克 |
| ru_ru | 俄文 — 俄羅斯 |
| ru_ua | 俄文 — 烏克蘭 |
| a_in | 梵語 — 印度 |
| sr_ba | 塞爾維亞語 — 波斯尼亞 |
| sr_rs | 塞爾維亞語 — 塞爾維亞 |
| sk_sk | 斯洛伐克文 — 斯洛伐克文 |
| sl_si | 斯洛維尼亞 — 斯洛維尼亞 |
| es_ar | 西班牙語 — 阿根廷 |
| es_bo | 西班牙語 — 玻利維亞 |
| es_cl | 西班牙語 — 智利 |
| es_co | 西班牙語 — 哥倫比亞 |
| es_cr | 西班牙語 — 哥斯大黎加 |
| es_do | 西班牙語 — 多明尼加共和國 |
| es_ec | 西班牙語 — 厄瓜多 |
| es_sv | 西班牙語 — 薩爾瓦多 |
| es_gt | 西班牙語 — 瓜地馬拉 |
| es_hn | 西班牙語 — 宏都拉斯 |
| es_mx | 西班牙語 — 墨西哥 |
| es_ni | 西班牙語 — 尼加拉瓜 |
| es_pa | 西班牙語 — 巴拿馬 |
| es_py | 西班牙語 — 巴拉圭 |
| es_pe | 西班牙語 — 秘魯 |
| es_pr | 西班牙語 — 波多黎各 |
| es_es | 西班牙語 — 西班牙 |
| es_uy | 西班牙語 — 烏拉圭 |
| es_ve | 西班牙語 — 委內瑞拉 |
| sw_ke | 斯瓦希里語 — 肯亞 |
| sv_fi | 瑞典文 — 芬蘭 |
| sv_se | 瑞典文 — 瑞典 |
| ta_in | 泰米爾語 — 印度 |
| tt_ru | 塔塔爾語 — 俄語 |
| te_in | 泰盧古 — 印度 |
| th_th | 泰語 — 泰國 |
| tr_cy | 土耳其語 — 塞普勒斯 |
| tr_tr | 土耳其語 — 土耳其 |
| uk_ua | 烏克蘭語 — 烏克蘭 |
| ur_in | 烏爾都語 — 印度 |
| ur_pk | 烏爾都語 — 巴基斯坦 |
| vi_vn | 越南 — 越南 |
