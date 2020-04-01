---
title: Adobe Campaign Standard的可傳遞性技術建議
description: 閱讀有關使用Adobe Campaign Standard改善傳遞能力的一些技術建議。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 41502fb6574879d3e69440f49a20fbc1c76ff26c

---


# 技術建議{#technical-recommendations}

以下列出幾種可用來改善傳遞率的技術、組態和工具。 以下是一些主要技術術語的定義。

**反向DNS**:Adobe Campaign會檢查是否提供反向DNS以取得IP位址，且這會正確指向IP。

**MX規則** ，用來控制促銷活動MTA（訊息傳送代理）傳送電子郵件至每個個別電子郵件網域或ISP（例如hotmail.com、comcast.net）的速度。 這些規則通常基於ISP發佈的限制（例如每個SMTP連接不包含超過20條消息）。

**TLS** （傳輸層安全性）是一種加密協定，可用來保護兩個電子郵件伺服器之間的連線，並保護電子郵件內容不受預定收件者以外的任何人讀取。

**SPF** （發件人策略框架）是一種電子郵件驗證標準，允許域的所有者指定允許代表該域發送電子郵件的電子郵件伺服器。 此標準使用電子郵件「回傳路徑」標題（也稱為「封套寄件者」位址）中的網域。

**DKIM** （域密鑰標識的郵件）驗證是SPF的繼承者，使用公鑰加密技術，允許接收電子郵件伺服器確認消息實際上是由其聲稱發送的個人或實體發送的，以及消息內容是否在最初發送時（和DKIM「簽名」）和接收時間之間發生了更改。 此標準通常使用「寄件者」或「寄件者」標題中的網域。

**DMARC** （基於域的消息驗證、報告和符合性）是最新的電子郵件驗證形式，它依賴SPF和DKIM驗證來確定電子郵件是否通過或失敗。 DMARC在兩個非常重要的方面是獨特而強大的：
* 符合性——允許發送方指示ISP如何處理任何未通過驗證的消息（例如不接受）。
* 報告——它為發送者提供詳細報告，顯示所有未通過DMARC驗證的消息，以及每個消息所使用的「發件人」域和IP地址。 這可讓公司識別驗證失敗且需要某些類型「修正」（例如，在其SPF記錄中新增IP位址）的合法電子郵件，以及其電子郵件網域上網路釣魚企圖的來源和普遍性。

DMARC可運用250ok產生的報表。

**SMTP** （簡單郵件傳輸協定）是電子郵件傳輸的Internet標準。

**專用IP**:Adobe為每位客戶提供專屬的IP策略，以提升IP，以建立聲譽並最佳化傳送效能。
