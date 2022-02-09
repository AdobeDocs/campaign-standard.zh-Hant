---
title: 更新和維護作業
description: 關於Adobe Campaign伺服器的更新和維護操作的資訊。
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 43%

---

# 更新和維護作業{#updates-and-maintenance-operations}

為了維護目的，Adobe Campaign伺服器每天在6 AM（伺服器時區）重新啟動。 聯繫Adobe瞭解伺服器時間。 此操作是自動和透明的。 但是，我們建議您不要在重新啟動之前執行任何資料處理操作。 例如，避免在重新啟動前啟動工作流，將它們安排為在重新啟動後一分鐘啟動。

Adobe 透過新增功能、增強功能和修正不斷改進其解決方案。所有 Adobe Campaign Standard 執行個體都會隨著每個新版本升級。升級不需要任何動作。升級分兩個階段部署。首先，Stage 執行個體已升級，可讓我們的客戶測試新功能並視需要調整其配置。隨後將升級生產執行個體。咨詢 [發佈計畫](https://helpx.adobe.com/tw/campaign/kb/acs-release-planning.html) 找出下一版的時間。 另請查閱 [已棄用和已刪除的功能](../../rn/using/deprecated-features.md)。
