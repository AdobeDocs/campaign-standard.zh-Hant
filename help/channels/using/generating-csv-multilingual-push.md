---
title: 為帶Campaign Standard的多語言推送通知生成CSV檔案
description: 上載CSV檔案以生成內容以供遞送是一種支援多語言推送通知的功能。
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

上載CSV檔案以生成內容以供遞送是一種支援多語言推送通知的功能。 CSV檔案的格式需要遵循某些指導原則才能成功上載檔案，從而能夠建立傳遞。 以下各節介紹了檔案格式及其注意事項。

## 檔案格式 {#file-format}

多語言推送要求CSV檔案中有14列：

1. title
1. 消息正文
1. 聲音
1. 廣告
1. deeplinkURI
1. 類別
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. 是ContentAvailable
1. 是可變內容
1. 自定義欄位
1. 區域
1. 語言
1. 靜默推送

按一下 **[!UICONTROL Download a sample file]** 的 **[!UICONTROL Manage Content Variants]** 的子菜單。 有關此內容的詳細資訊，請參閱 [節](../../channels/using/creating-a-multilingual-push-notification.md)。

* **標題， messageBody，聲音，徽章， deplinkURI，類別， iosMediaAttachmentURL, androidMediaAttachmentURL**:常規推送負載內容。 您需要以與建立推送交貨時類似的方式提供此資訊。
* **自定義欄位**:對自定義欄位使用JSON格式，例如 `{"key1":"value1","key2":"value2"}`。 有關自定義欄位的示例，請參閱上面的示例檔案。
* **是ContentAvailable**:「內容可用」檢查的標誌，值1表示true，值0表示false。 預設值為0。 如果將此列留空，則該值將視為0。
* **是可變內容**:可變內容的標誌，值1表示true，值0表示false。 預設值為0。 如果將此列留空，則該值將視為0。
* **區域**:locale是語言變體的欄位，例如「en_us」（美國 — 英語）和「fr_fr」（法國 — 法語）。
* **語言**:與區域設定關聯的語言的名稱。 例如，如果區域設定為&quot;en_us&quot;，則語言名稱應為&quot;English-United States&quot;。
* **靜默推送**:推送通知類型的標誌。 如果是常規推送通知，則值應為0。 如果是靜默推送，則值應為1。 預設值為0。 如果將此列留空，則該值將視為0。

## csv檔案建立的約束和准則 {#constraints-guideline-csv}

**每列的名稱是固定的**。
您應在CSV檔案中包括每列的名稱，如果不對內容使用任何列，請將其留空。

**「locale」和「language」列是必需的，值對於每行都是唯一的。**
此列的空值將導致檔案上載失敗。

**列順序重要**。 上載檔案中列的順序需要與示例檔案的格式相同。

**報價列內容**。 由於這是CSV（表示逗號分隔值）檔案，因此必須引用包含逗號(,)的任何列內容。 例如，&quot;你好，湯姆！&quot;

**國際字元需要UTF-8編碼。**

**如果按純文字檔案生成檔案，請按「，」分隔每列。**

**變型不匹配。** 如果您使用具有特定語言的內容塊和目標受眾，則需要列出CSV檔案中的每種目標語言，否則在發送傳遞時將出錯。

## 在csv檔案中插入個性化欄位 {#personalization-field-csv}

如果要使用個性化欄位，應包括 <span> 的下界。

要在messageBody中插入&quot;firstName&quot;個性化欄位，消息必須是：

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

&quot;firstName&quot;欄位由：

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

在跨度中有兩個必需屬性：

* 一個是靜態類。 無論您計畫使用哪個個性化欄位，它都將始終為class=&quot;nl-dce-field nl-dce-done&quot;。

* 另一個是data-nl-expr，它是個性化欄位的路徑。 例如，如果從UI插入「firstName」個性化欄位，則導航路徑將 **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** （如下圖所示）。 在這種情況下，路徑是

   ```
   /context/profile/firstName. data-nl-expr="/context/profile/firstName".
   ```

![](assets/multilingual_push_2.png)

## 區域設定和語言名稱 {#locale-language-names}

支援以下語言：

| 區域 | 語言 |
|:-:|:-:|
| af_za | 阿非利卡語 — 南非 |
| sq_al | 阿爾巴尼亞語 — 阿爾巴尼亞 |
| ar_dz | 阿拉伯語 — 阿爾及利亞 |
| ar_bh | 阿拉伯語 — 巴林 |
| ar_iq | 阿拉伯語 — 伊拉克 |
| ar_il | 阿拉伯語 — 以色列 |
| ar_jo | 阿拉伯語 — 約旦 |
| ar_kw | 阿拉伯語 — 科威特 |
| ar_lb | 阿拉伯語 — 黎巴嫩 |
| ar_ma | 阿拉伯語 — 摩洛哥 |
| ar_om | 阿拉伯語 — 阿曼 |
| ar_qa | 阿拉伯語 — 卡達 |
| ar_sa | 阿拉伯語 — 沙烏地阿拉伯 |
| ar_sy | 阿拉伯語 — 敘利亞 |
| ar_tn | 阿拉伯語 — 突尼西亞 |
| ar_ae | 阿拉伯語 — 阿拉伯聯合大公國 |
| ar_ye | 阿拉伯語 — 葉門 |
| hy_am | 亞美尼亞語 — 亞美尼亞 |
| az_az | 亞塞拜然語 — 亞塞拜然 |
| 是 | 白俄羅斯 — 白俄羅斯 |
| bs_ba | 波斯尼亞 — 波斯尼亞 |
| bg_bg | 保加利亞語 — 保加利亞 |
| ca_es | 加泰羅尼亞語 — 西班牙 |
| zh_cn | 中文（簡體） — 中國 |
| zh_sg | 中文（簡體） — 新加坡 |
| zh_hk | 中文（繁體） — 香港 |
| zh_tw | 中文（繁體） — 台灣地區 |
| hr_hr | 克羅埃西亞語 — 克羅埃西亞 |
| cs_cz | 捷克語 — 切希亞語 |
| da_dk | 丹麥語 — 丹麥 |
| nl_be | 荷蘭語 — 比利時 |
| nl_nl | 荷蘭語 — 荷蘭 |
| en_au | 英語 — 澳大利亞 |
| 根據 | 英語 — 貝里斯 |
| en_ca | 英語 — 加拿大 |
| en-in | 英語 — 印度 |
| en_ie | 英語 — 愛爾蘭 |
| en_jm | 英語 — 牙買加 |
| en_nz | 英語 — 紐西蘭 |
| en_ph | 英語 — 菲律賓 |
| en_za | 英語 — 南非 |
| en_tt | 英語 — 千里達和多巴哥 |
| en_gb | 英語 — 英國 |
| en_us | 英語 — 美國 |
| en_zw | 英語 — 辛巴威 |
| 集 | 愛沙尼亞語 — 愛沙尼亞 |
| fi_fi | 芬蘭語 — 芬蘭 |
| fr_be | 法語 — 比利時 |
| fr_ca | 法語 — 加拿大 |
| fr_fr | 法語 — 法國 |
| fr_lu | 法語 — 盧森堡 |
| fr_ch | 法語 — 瑞士 |
| 取消 | 德語 — 奧地利 |
| 取消 | 德語 — 德國 |
| de_lu | 德語 — 盧森堡 |
| 取消 | 德語 — 瑞士 |
| el_cy | 希臘語 — 塞普勒斯 |
| el_gr | 希臘語 — 希臘 |
| gu_in | 古吉拉特語 — 印度 |
| he_il | 希伯來語 — 以色列 |
| hi_in | 印地語 — 印度 |
| hu_hu | 匈牙利語 — 匈牙利 |
| 是 | 冰島語 — 冰島 |
| id_id | 印度尼西亞 — 印度尼西亞 |
| it | 義大利語 — 義大利 |
| it_ch | 義大利語 — 瑞士 |
| ja_jp | 日語 — 日本 |
| kn_in | 卡納達 — 印度 |
| kk_kz | 哈薩克語 — 哈薩克 |
| ko_kr | 韓國 — 韓國 |
| lv_lv | 拉脫維亞語 — 拉脫維亞 |
| lt_lt | 立陶宛語 — 立陶宛 |
| mk_mk | 馬其頓語 — 馬其頓 |
| ms_my | 馬來語 — 馬來西亞 |
| mr_in | 馬拉地語 — 印度 |
| 否 | 挪威語 — 挪威 |
| pl_pl | 波蘭 — 波蘭 |
| pt_br | 葡萄牙語 — 巴西 |
| pt_pt | 葡萄牙語 — 葡萄牙 |
| pa_in | 旁遮普語 — 印度 |
| ro_md | 羅馬尼亞語 — 摩爾多瓦 |
| ro_ro | 羅馬尼亞語 — 羅馬尼亞 |
| ru_kz | 俄語 — 哈薩克 |
| ru_ru | 俄語 — 俄羅斯 |
| ru_ua | 俄語 — 烏克蘭 |
| 插入 | 梵語 — 印度 |
| sr_ba | 塞爾維亞語 — 波斯尼亞 |
| sr_rs | 塞爾維亞語 — 塞爾維亞 |
| sk_sk | 斯洛伐克語 — 斯洛伐克 |
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
| sv_fi | 瑞典語 — 芬蘭 |
| sv_se | 瑞典語 — 瑞典 |
| ta_in | 泰米爾語 — 印度 |
| t_ru | 塔塔爾語 — 俄語 |
| 插入 | 泰盧古語 — 印度 |
| 第 | 泰語 — 泰國 |
| tr_cy | 土耳其語 — 塞普勒斯 |
| tr_tr | 土耳其語 — 土耳其 |
| uk_ua | 烏克蘭語 — 烏克蘭 |
| ur_in | 烏爾都語 — 印度 |
| ur_pk | 烏爾都語 — 巴基斯坦 |
| vi_vn | 越南語 — 越南 |
