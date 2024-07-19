---
title: 資料模型行銷記錄
description: 瞭解資料模型
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 7f2a3139-57eb-48ff-9b1a-ac2caad2f691
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1347'
ht-degree: 9%

---

# 行銷歷史記錄(nms：history)

## 物件說明

<table>
               <tr>
                  <th>名稱</th>
                  <th>標籤</th>
                  <th>型別（長度）</th>
                  <th>分項清單值</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>主要資源ID</td>
                  <td>字串 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>年齡</td>
                  <td>年齡</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>出生日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>黑名單</td>
                  <td>不再連絡 (透過任何管道)</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>不再透過電子郵件聯絡</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>不再透過傳真聯絡</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>不再透過簡訊聯絡</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>不再透過電話聯絡</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostMail</td>
                  <td>不再透過直接郵件聯絡</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>不再透過推播通知聯絡</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countBroadLogEvents</td>
                  <td>CountBroadLogEvents</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countSubHistoEvents</td>
                  <td>CountSubHistoEvents</td>
                  <td>整數 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>國家/地區</td>
                  <td>國家/地區</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countryIsoA2</td>
                  <td>ISO A2 代碼</td>
                  <td>字串(2)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>已建立</td>
                  <td>已建立</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>建立者：</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>上次交易日期</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>交易數</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>電子郵件</td>
                  <td>電子郵件</td>
                  <td>字串(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>事件</td>
                  <td>異質資源</td>
                  <td>集合 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>傳真</td>
                  <td>傳真</td>
                  <td>字串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>名字</td>
                  <td>名字</td>
                  <td>字串(30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>性別</td>
                  <td>性別</td>
                  <td>分項清單（位元組） </td>
                  <td>
                     <ul>
                        <li>未指定 — 未知 — 0</li>
                        <li>男性 — 男性 — 1</li>
                        <li>女性 — 女性 — 2</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>是外部資源</td>
                  <td>布林值 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpisAndChart</td>
                  <td>KpiAndChart</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>上次修改時間</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>姓氏</td>
                  <td>姓氏</td>
                  <td>字串(50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>位置</td>
                  <td>位置</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>中間名</td>
                  <td>中間名</td>
                  <td>字串(30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minBroadLogEvents</td>
                  <td>MinBroadLogEvents</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minSubHistoEvents</td>
                  <td>MinSubHistoEvents</td>
                  <td>日期 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>行動電話</td>
                  <td>行動</td>
                  <td>字串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>修改者</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>電話</td>
                  <td>電話</td>
                  <td>字串(32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>salutation</td>
                  <td>標題</td>
                  <td>字串(20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
                  <td>狀態</td>
                  <td>連結 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>縮圖</td>
                  <td>縮圖</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>時區</td>
                  <td>時區</td>
                  <td>分項清單（字串） (64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02:00)中大西洋 — 大西洋_南喬治亞 — 大西洋/南喬治亞</li>
                        <li>(GMT+02:00)安曼 — 亞洲_安曼 — 亞洲/安曼</li>
                        <li>(GMT-03:00)布拉西 — 美洲_聖保羅 — 美洲/聖保羅</li>
                        <li>(GMT+06:00)阿斯塔納、達卡 — 亞洲_達卡 — 亞洲/達卡</li>
                        <li>(GMT+06:00)新西伯利亞 — 亞洲_新西伯利亞 — 亞洲/新西伯利亞</li>
                        <li>(GMT+02:00)溫得和克 — 非洲_溫得和克 — 非洲/溫得和克</li>
                        <li>(GMT+04:00)高加索、葉里溫 — 亞洲_葉里溫 — 亞洲/葉里溫</li>
                        <li>(GMT-04:00)馬瑙斯 — 美洲_馬瑙斯 — 美洲/馬瑙斯</li>
                        <li>(GMT+03:30)德黑蘭市 — 亞洲_德黑蘭 — 亞洲/德黑蘭</li>
                        <li>(GMT+12:00)奧克蘭、惠靈頓 — 太平洋_奧克蘭 — 太平洋/奧克蘭</li>
                        <li>(GMT+02:00)耶路撒冷 — 亞洲_耶路撒冷 — 亞洲/耶路撒冷</li>
                        <li>(GMT+03:00)莫斯科、聖彼得堡、伏爾加 — 歐洲_莫斯科 — 歐洲/莫斯科</li>
                        <li>(GMT+09:30)阿德萊德 — 澳洲_阿德萊德 — 澳洲/阿德萊德</li>
                        <li>(GMT+10:00)坎培拉、墨爾本、雪梨 — 澳洲_坎培拉 — 澳洲/坎培拉</li>
                        <li>(GMT+08:00)珀斯 — 澳洲_珀斯 — 澳洲/珀斯</li>
                        <li>(GMT+09:00)亞庫次克 — 亞洲_亞庫次克 — 亞洲/亞庫次克</li>
                        <li>(GMT-10:00)夏威夷 — 太平洋_檀香山 — 太平洋/檀香山</li>
                        <li>(GMT+04:00)巴庫 — 亞洲_巴庫 — 亞洲/巴庫</li>
                        <li>(GMT+10:00)海參威 — 亞洲_海參威 — 亞洲/海參威</li>
                        <li>(GMT+09:00)首爾 — 亞洲_首爾 — 亞洲/首爾</li>
                        <li>(GMT+01:00)塞拉耶佛、斯科普列、索菲亞、華沙、薩格勒布 — 歐洲_塞拉耶佛 — 歐洲/塞拉耶佛</li>
                        <li>(GMT+04:00)阿布達比、馬斯喀特 — 亞洲_馬斯喀特 — 亞洲/馬斯喀特</li>
                        <li>(GMT+08:00)吉隆坡、新加坡 — 亞洲_吉隆坡 — 亞洲/吉隆坡</li>
                        <li>(GMT+09:00)大阪、札幌、東京 — 亞洲_東京 — 亞洲/東京</li>
                        <li>(GMT+10:00)布里斯本 — 澳洲_布里斯本 — 澳洲/布里斯本</li>
                        <li>(GMT+05:30)斯里加亞華登尼普拉 — 亞洲_可倫坡 — 亞洲/可倫坡</li>
                        <li>(GMT+02:00)哈拉雷、普利托里亞 — 非洲_哈拉雷 — 非洲/哈拉雷</li>
                        <li>(GMT+08:00)烏蘭巴托 — 亞洲_烏蘭巴托 — 亞洲/烏蘭巴托</li>
                        <li>(GMT-02:00)格林威治標準時間減2小時 — Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03:00)格林威治標準時間減3小時 — Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-01:00)格林威治標準時間減1小時 — Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06:00)格林威治標準時間減6小時 — Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07:00)格林威治標準時間減7小時 — Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04:00)格林威治標準時間減4小時 — Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT)卡薩布蘭卡 — 非洲_卡薩布蘭卡 — 非洲/卡薩布蘭卡</li>
                        <li>(GMT+05:30)加爾各答、金奈、孟買、新德里 — 亞洲_加爾各答 — 亞洲/加爾各答</li>
                        <li>(GMT-11:00)格林威治標準時間減11小時 — Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09:00)格林威治標準時間減9小時 — Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03:30)紐芬蘭 — 美洲_聖約翰 — 美洲/聖約翰</li>
                        <li>(GMT+03:00)格林威治標準時間加3小時 — Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04:30)加拉加斯 — 美洲_加拉加斯 — 美洲/加拉加斯</li>
                        <li>(GMT+01:00)阿姆斯特丹、柏林、伯恩、羅馬、斯德哥爾摩、維也納 — 歐洲_柏林 — 歐洲/柏林</li>
                        <li>(GMT-07:00)奇瓦瓦，拉巴斯，馬薩特蘭 — 美洲_奇瓦瓦 — 美洲/奇瓦瓦</li>
                        <li>(GMT+03:00)奈洛比 — 非洲_奈洛比 — 非洲/奈洛比</li>
                        <li>(GMT-04:00)亞松森 — 美洲_亞松森 — 美洲/亞松森</li>
                        <li>(GMT+03:00)巴格達 — 亞洲_巴格達 — 亞洲/巴格達</li>
                        <li>(GMT-10:00)格林威治標準時間減10小時 — Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03:00)格陵蘭 — 美洲_哥特哈布 — 美洲/哥特哈布</li>
                        <li>(GMT+02:00)達馬斯 — 亞洲_大馬士革 — 亞洲/大馬士革</li>
                        <li>(GMT-11:00)薩摩亞 — 太平洋薩摩亞 — 太平洋/薩摩亞</li>
                        <li>(GMT-05:00)波哥大、利馬、基多 — 美洲_波哥大 — 美洲/波哥大</li>
                        <li>(GMT+01:00)布魯塞爾、哥本哈根、馬德里、巴黎 — 歐洲_巴黎 — 歐洲/巴黎</li>
                        <li>(GMT+08:00)北京、重慶、香港、烏魯木齊 — 亞洲_上海 — 亞洲/上海</li>
                        <li>(GMT+12:00)斐濟 — 太平洋_斐濟 — 太平洋/斐濟</li>
                        <li>(GMT+02:00)雅典、伊斯坦堡、明斯克 — 歐洲_雅典 — 歐洲/雅典</li>
                        <li>(GMT+04:00)第比利斯 — 亞洲_第比利斯 — 亞洲/第比利斯</li>
                        <li>無效值 — __Invalid_value__ - __Invalid_value__</li>
                        <li>(GMT+05:45)加德滿都 — 亞洲_加德滿都 — 亞洲/加德滿都</li>
                        <li>(GMT-05:00)印地安納州（東部） — 美洲_印地安納波利斯 — 美洲/印地安納波利斯</li>
                        <li>(GMT-01:00)維德角群島 — 大西洋_維德角 — 大西洋/維德角</li>
                        <li>(GMT+04:00)路易港 — 印度模里西斯 — 印度洋/模里西斯</li>
                        <li>(GMT+08:00)台北 — 亞洲_台北 — 亞洲/台北</li>
                        <li>(GMT+06:30)仰光 — 亞洲_仰光 — 亞洲/仰光</li>
                        <li>(GMT+11:00)馬加丹、索羅門群島、新喀里多尼亞 — 太平洋_瓜達爾卡納島 — 太平洋/瓜達爾卡納島</li>
                        <li>(GMT+02:00)開羅 — 非洲_開羅 — 非洲/開羅</li>
                        <li>(GMT+05:00)葉卡捷琳堡 — 亞洲_葉卡捷琳堡 — 亞洲/葉卡捷琳堡</li>
                        <li>(GMT+08:00)伊爾庫茨克 — 亞洲_伊爾庫茨克 — 亞洲/伊爾庫茨克</li>
                        <li>(GMT+10:00)關島、莫爾斯比港 — 太平洋關島 — 太平洋/關島</li>
                        <li>(GMT-04:00)大西洋標準時間（加拿大） — 美洲_哈利法克斯 — 美洲/哈利法克斯</li>
                        <li>(GMT)格林威治標準時間 — GMT - GMT</li>
                        <li>預設 — 無 — 無</li>
                        <li>(GMT-04:00)拉巴斯 — 美洲_拉巴斯 — 美洲/拉巴斯</li>
                        <li>(GMT-06:00)瓜達拉哈拉，墨西哥，蒙特雷 — 美洲_墨西哥城 — 美洲/墨西哥城</li>
                        <li>(GMT+09:30)達爾文 — 澳洲_達爾文 — 澳洲/達爾文</li>
                        <li>(GMT-05:00)東部時間（美國和加拿大） — 美洲/紐約 — 美洲/紐約</li>
                        <li>(GMT-05:00)格林威治標準時間減5小時 — Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05:00)伊斯蘭堡、喀拉蚩、塔肯特 — 亞洲_喀拉蚩 — 亞洲/喀拉蚩</li>
                        <li>(GMT+03:00)科韋特、利雅德 — 亞洲_利雅德 — 亞洲/利雅德</li>
                        <li>(GMT-08:00)格林威治標準時間減8小時 — Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01:00)亞速爾群島 — 大西洋_亞速爾群島 — 大西洋/亞速爾群島</li>
                        <li>(GMT+07:00)曼谷、河內、雅加達 — 亞洲_曼谷 — 亞洲/曼谷</li>
                        <li>(GMT)蒙羅維亞 — 非洲_蒙羅維亞 — 非洲/蒙羅維亞</li>
                        <li>(GMT-09:00)阿拉斯加 — 美洲_安克拉治 — 美洲/安克拉治</li>
                        <li>(GMT+01:00)貝爾格萊德、布拉提斯拉瓦、布達佩斯、盧比安納、布拉格 — 歐洲_貝爾格萊德 — 歐洲/貝爾格萊德</li>
                        <li>(GMT)雷克雅未克 — 大西洋_雷克雅未克 — 大西洋/雷克雅未克</li>
                        <li>(GMT+02:00)布加勒斯特 — 歐洲_布加勒斯特 — 歐洲/布加勒斯特</li>
                        <li>(GMT+05:00)格林威治標準時間加5小時 — Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04:00)格林威治標準時間加4小時 — Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07:00)格林威治標準時間加7小時 — Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06:00)格林威治標準時間加6小時 — Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01:00)格林威治標準時間加1小時 — Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08:00)太平洋（美國和加拿大） — 美洲_洛杉磯 — 美洲/洛杉磯</li>
                        <li>(GMT+02:00)格林威治標準時間加2小時 — Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07:00)克拉史諾亞爾斯克 — 亞洲_克拉史諾亞爾斯克 — 亞洲/克拉史諾亞爾斯克</li>
                        <li>(GMT+09:00)格林威治標準時間加9小時 — Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08:00)格林威治標準時間加8小時 — Gmt_p8 - Etc/GMT-8</li>
                        <li>(GMT+10:00)荷巴特 — 澳洲_荷巴特 — 澳洲/荷巴特</li>
                        <li>(GMT+13:00)努庫阿洛法 — 太平洋_東加塔布 — 太平洋/東加塔布</li>
                        <li>(GMT-06:00)中美洲 — 美洲_雷吉納 — 美洲/雷吉納</li>
                        <li>(GMT-03:00)布宜諾斯艾利斯、卡宴、福塔雷薩 — 美洲_布宜諾斯艾利斯 — 美洲/布宜諾斯艾利斯</li>
                        <li>(GMT-07:00)落基山脈（美國和加拿大） — 美洲_丹佛 — 美洲/丹佛</li>
                        <li>(GMT+01:00)中非 — 西部 — 非洲_羅安達 — 非洲/羅安達</li>
                        <li>(GMT+02:00)赫爾辛基、基輔、里加、索菲亞、塔林、維爾紐斯 — 歐洲_赫爾辛基 — 歐洲/赫爾辛基</li>
                        <li>(GMT)格林威治標準時間：都柏林、愛丁堡、里斯本、倫敦 — 歐洲_倫敦 — 歐洲/倫敦</li>
                        <li>(GMT-07:00)亞利桑那 — 美洲_鳳凰城 — 美洲/鳳凰城</li>
                        <li>(GMT+02:00)貝魯特 — 亞洲_貝魯特 — 亞洲/貝魯特</li>
                        <li>(GMT+04:30)喀布林 — 亞洲_喀布林 — 亞洲/喀布林</li>
                        <li>(GMT-06:00)中心（美國和加拿大） — 美洲_芝加哥 — 美洲/芝加哥</li>
                        <li>(GMT+11:00)格林威治標準時間加11小時 — Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10:00)格林威治標準時間加10小時 — Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13:00)格林威治標準時間加13小時 — Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12:00)格林威治標準時間加12小時 — Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04:00)聖地亞哥 — 美洲_聖地亞哥 — 美洲/聖地亞哥</li>
                        <li>(GMT-03:00)蒙特維多 — 美洲_蒙特維多 — 美洲/蒙特維多</li>
                        <li>(GMT-04:00)庫亞巴 — 美洲_庫亞巴 — 美洲/庫亞巴</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>標題</td>
                  <td>設定檔</td>
                  <td>字串(255)</td>
                  <td> </td>
               </tr>
            </table>

## 篩選器

生日（生日）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>includeStart</td>
<td>布林值</td>
</tr>
<tr>
<td>previousUnitsValue</td>
<td>整數</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>整數</td>
</tr>
<tr>
<td>endDay</td>
<td>日期</td>
</tr>
<tr>
<td>精確度</td>
<td>分項清單</td>
</tr>
<tr>
<td>相對值</td>
<td>字串</td>
</tr>
<tr>
<td>月</td>
<td>日期</td>
</tr>
<tr>
<td>運運算元</td>
<td>分項清單</td>
</tr>
<tr>
<td>includeEnd</td>
<td>布林值</td>
</tr>
<tr>
<td>endMonth</td>
<td>日期</td>
</tr>
<tr>
<td>類型</td>
<td>分項清單</td>
</tr>
<tr>
<td>天</td>
<td>日期</td>
</tr>
</table>

依電子郵件（依電子郵件）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>電子郵件</td>
<td>字串</td>
</tr>
</table>

按索引鍵(byKeysProfile)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>電子郵件</td>
<td>字串</td>
</tr>
</table>

依名稱或電子郵件(byText)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>文字</td>
<td>字串</td>
</tr>
</table>

依靜態對象(byStaticAudience)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>客群</td>
<td>連結</td>
</tr>
</table>

Clicked (hasClickedDelivery)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>傳遞</td>
<td>連結</td>
</tr>
</table>

已開啟(hasOpenedDelivery)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>傳遞</td>
<td>連結</td>
</tr>
</table>

設定檔（設定檔）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>設定檔</td>
<td>連結</td>
</tr>
</table>

已接收(hasReceivedDelivery)

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>傳遞</td>
<td>連結</td>
</tr>
</table>

訂閱者（訂閱者）

<table>
<tr>
<th>名稱</th>
<th>類型</th>
</tr>
<tr>
<td>服務</td>
<td>連結</td>
</tr>
</table>
