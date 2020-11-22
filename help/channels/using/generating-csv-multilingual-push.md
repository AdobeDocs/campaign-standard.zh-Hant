---
solution: Campaign Standard
product: campaign
title: 使用Campaign Standard產生多語言推播通知的CSV檔案
description: 上傳CSV檔案以產生內容以供傳送是一種支援多語言推播通知的功能。
audience: channels
content-type: reference
topic-tags: email-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---


# 產生多語言推播通知的 CSV 檔案{#generating-csv-multilingual-push}

上傳CSV檔案以產生內容以供傳送是一種支援多語言推播通知的功能。 CSV檔案的格式必須符合檔案上傳成功的特定准則，才能建立傳送。 以下各節將介紹檔案格式及其注意事項。

## 檔案格式 {#file-format}

多語言推播需要CSV檔案中14欄：

1. 標題
1. messageBody
1. sound
1. adge
1. deeplinkURI
1. 類別
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMutableContent
1. customFields
1. 語言
1. 語言
1. silentPush

按一下視窗中的，以檢查 **[!UICONTROL Download a sample file]** CSV范 **[!UICONTROL Manage Content Variants]** 例。 For more on this, refer to the this [section](../../channels/using/creating-a-multilingual-push-notification.md).

* **title, messageBody, sound, badge, deplinkURI, category, iosMediaAttachmentURL, androidMediaAttachmentURL**:一般推播裝載內容。 您必須以建立推播傳送時的類似方式提供此資訊。
* **自訂欄位**: 對自訂欄位使用JSON格式，例如 `{"key1":"value1","key2":"value2"}`. 如需自訂欄位的範例，請參閱上述範例檔案。
* **isContentAvailable**:標幟為「可用內容」檢查，值1表示true，值0表示false。 預設值為0。 如果將此欄留空，該值將被視為0。
* **isMutableContent**:標籤可變內容，值1表示true，值0表示false。 預設值為0。 如果將此欄留空，該值將被視為0。
* **地區**:locale是語言變體的欄位，例如「en_us」代表美國——英文，「fr_fr」代表法國——法文。
* **語言**:與語言環境關聯的語言的名稱。 例如，如果地區設定為&quot;en_us&quot;，則語言名稱應為&quot;English-United States&quot;。
* **silentPush**:推播通知類型的旗標。 如果是一般推播通知，則值應為0。 如果是無訊息推播，則值應為1。 預設值為0。 如果將此欄留空，該值將被視為0。

## 建立csv檔案的限制與准則 {#constraints-guideline-csv}

**每個列的名稱都是固定的**。
您應在CSV檔案中包含每欄的名稱，如果您未對內容使用任何欄，請將其留空。

**&quot;locale&quot;和&quot;language&quot;欄是必填欄，且值對每一列都是唯一的。**
此欄的空白值將導致檔案上傳失敗。

**欄的順序很重要**。 上傳檔案中欄的順序必須與範例檔案的格式相同。

**引號欄內容**。 由於這是CSV（代表逗號分隔值）檔案，所以任何包含逗號(,)的欄內容都必須加上引號。 例如，「Hello, Tom!」

**UTF-8編碼對於國際字元是必要的。**

**如果以純文字檔案生成檔案，請以&quot;,&quot;分隔每列。**

**變型不符。** 如果您使用內容區塊並鎖定具特定語言的對象，您必須在CSV檔案中列出每個目標語言，否則傳送傳送時會發生錯誤。

## 在csv檔案中插入個人化欄位 {#personalization-field-csv}

如果您想要使用個人化欄位，您應在檔 <span> 案中加入標籤。

若要將&quot;firstName&quot;個人化欄位插入messageBody，訊息必須是：

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

&quot;firstName&quot;欄位的代表：

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

在範圍中有兩個必備屬性：

* 一個是靜態類。 無論您打算使用哪個個人化欄位，都一律是class=&quot;nl-dce-field nl-dce-done&quot;。

* 另一個是資料nl-expr，它是個人化領域的路徑。 例如，如果您從UI插入「firstName」個人化欄位，導覽路徑將是 **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** （如下圖所示）。 在這種情況下，路徑將是

   ```
   /context/profile/firstName. data-nl-expr="/context/profile/firstName".
   ```

![](assets/multilingual_push_2.png)

## 地區和語言名稱 {#locale-language-names}

支援下列語言：

| 語言 | 語言 |
|:-:|:-:|
| af_za | 南非荷蘭文——南非 |
| sq_al | 阿爾巴尼亞——阿爾巴尼亞 |
| ar_dz | 阿拉伯文——阿爾及利亞 |
| ar_bh | 阿拉伯文——巴林 |
| ar_iq | 阿拉伯文——伊拉克 |
| ar_il | 阿拉伯文——以色列 |
| ar_jo | 阿拉伯文——約旦 |
| ar_kw | 阿拉伯文——科威特 |
| ar_lb | 阿拉伯文——黎巴嫩 |
| ar_ma | 阿拉伯文——摩洛哥 |
| ar_om | 阿拉伯文——阿曼 |
| ar_qa | 阿拉伯文——卡達 |
| ar_sa | 阿拉伯文——沙烏地阿拉伯 |
| ar_sy | 阿拉伯文——敘利亞 |
| ar_tn | 阿拉伯文——突尼西亞 |
| ar_ae | 阿拉伯文——阿拉伯聯合大公國 |
| ar_ye | 阿拉伯文——葉門 |
| hy_am | 亞美尼亞——亞美尼亞 |
| az_az | 亞塞拜然——亞塞拜然 |
| be_by | 白俄羅斯——白俄羅斯 |
| bs_ba | 波斯尼亞——波士尼亞 |
| bg_bg | 保加利亞——保加利亞 |
| ca_es | 加泰羅尼亞語——西班牙 |
| zh_cn | 簡體中文——中文 |
| zh_sg | 簡體中文——新加坡 |
| zh_hk | 中文（繁體）-香港 |
| zh_tw | 繁體中文——台灣地區 |
| hr_hr | 克羅埃西亞——克羅埃西亞 |
| cs_cz | 捷克文——切奇亞文 |
| da_dk | 丹麥文——丹麥 |
| nl_be | 荷蘭文——比利時 |
| nl_nl | 荷蘭文——荷蘭文 |
| en_au | 英文——澳洲 |
| en_bz | 英文——貝里斯 |
| en_ca | 英文——加拿大 |
| en_in | 英文——印度 |
| en_ie | 英文——愛爾蘭 |
| en_jm | 英文——牙買加 |
| en_nz | 英文——紐西蘭 |
| en_ph | 英文——菲律賓 |
| en_za | 英文——南非 |
| en_tt | 英文——千里達和多巴哥 |
| en_gb | 英文——英國 |
| en_us | 英文——美國 |
| en_zw | 英文——辛巴威 |
| et_ee | 愛沙尼亞——愛沙尼亞 |
| fi_fi | 芬蘭文——芬蘭 |
| fr_be | 法文——比利時 |
| fr_ca | 法文——加拿大 |
| fr_fr | 法文——法國 |
| fr_lu | 法文——盧森堡 |
| fr_ch | 法文——瑞士 |
| de_at | 德文——奧地利 |
| de_de | 德文——德國 |
| de_lu | 德文——盧森堡 |
| de_ch | 德文——瑞士 |
| el_cy | 希臘文——塞普勒斯 |
| el_gr | 希臘文——希臘 |
| gu_in | 古吉拉特文——印度 |
| he_il | 希伯來文——以色列 |
| hi_in | 印度文——印度 |
| hu_hu | 匈牙利文——匈牙利 |
| is_is | 冰島——冰島 |
| id_id | 印尼——印尼 |
| it_it | 義大利文——義大利文 |
| it_ch | 義大利文——瑞士 |
| ja_jp | 日文——日本 |
| kn_in | 坎納達——印度 |
| kk_kz | 哈薩克——哈薩克 |
| ko_kr | 韓文——韓國 |
| lv_lv | 拉脫維亞——拉脫維亞 |
| lt_lt | 立陶宛——立陶宛 |
| mk_mk | 馬其頓——馬其頓 |
| ms_my | 馬來文——馬來西亞 |
| mr_in | 馬拉地——印度 |
| no_no | 挪威文——挪威 |
| pl_pl | 波蘭——波蘭 |
| pt_br | 葡萄牙文——巴西 |
| pt_pt | 葡萄牙文——葡萄牙文 |
| pa_in | 旁遮普——印度 |
| ro_md | 羅馬尼亞文——摩爾多瓦 |
| ro_ro | 羅馬尼亞文——羅馬尼亞文 |
| ru_kz | 俄文——哈薩克 |
| ru_ru | 俄文——俄羅斯 |
| ru_ua | 俄文——烏克蘭 |
| a_in | 梵文——印度 |
| sr_ba | 塞爾維亞——波斯尼亞 |
| sr_rs | 塞爾維亞——塞爾維亞 |
| sk_sk | 斯洛伐克——斯洛伐克 |
| sl_si | 斯洛維尼亞——斯洛維尼亞 |
| es_ar | 西班牙文——阿根廷 |
| es_bo | 西班牙文——玻利維亞 |
| es_cl | 西班牙文——智利 |
| es_co | 西班牙文——哥倫比亞 |
| es_cr | 西班牙文——哥斯大黎加 |
| es_do | 西班牙文——多明尼加共和國 |
| es_ec | 西班牙文——厄瓜多 |
| es_sv | 西班牙文——薩爾瓦多 |
| es_gt | 西班牙文——瓜地馬拉 |
| es_hn | 西班牙文——宏都拉斯 |
| es_mx | 西班牙文——墨西哥 |
| es_ni | 西班牙文——尼加拉瓜 |
| es_pa | 西班牙文——巴拿馬 |
| es_py | 西班牙文——巴拉圭 |
| es_pe | 西班牙文——秘魯 |
| es_pr | 西班牙文——波多黎各 |
| es_es | 西班牙文——西班牙 |
| es_uy | 西班牙文——烏拉圭 |
| es_ve | 西班牙文——委內瑞拉 |
| sw_ke | 斯瓦希里語——肯亞 |
| sv_fi | 瑞典文——芬蘭 |
| sv_se | 瑞典文——瑞典 |
| ta_in | 坦米爾——印度 |
| tt_ru | 塔塔爾——俄文 |
| te_in | 泰盧古——印度 |
| th_th | 泰文——泰國 |
| tr_cy | 土耳其文——塞普勒斯 |
| tr_tr | 土耳其文——土耳其 |
| uk_ua | 烏克蘭文——烏克蘭文 |
| ur_in | 烏爾都——印度 |
| ur_pk | 烏爾都——巴基斯坦 |
| vi_vn | 越南——越南 |
