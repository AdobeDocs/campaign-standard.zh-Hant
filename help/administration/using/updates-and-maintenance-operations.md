---
title: 更新和維護作業
description: 有關Adobe Campaign伺服器更新和維護作業的資訊。
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 27%

---

# 更新和維護作業{#updates-and-maintenance-operations}

為了進行維護，Adobe Campaign伺服器每天早上6:00重新啟動（伺服器時區）。 請連絡Adobe以瞭解伺服器時間。 此作業是自動且透明的。 不過，我們建議您不要在重新啟動之前執行任何資料處理作業。 例如，請避免在重新啟動前啟動工作流程，請將工作流程排程在重新啟動後一分鐘開始。

Adobe透過新增新功能、增強功能和修正不斷改進其解決方案。 所有 Adobe Campaign Standard 執行個體都會隨著每個新版本升級。升級不需要任何動作。 升級分兩個階段部署。首先，Stage 執行個體已升級，可讓我們的客戶測試新功能並視需要調整其配置。隨後將升級生產執行個體。 請參閱 [發行計畫](https://helpx.adobe.com/tw/campaign/kb/acs-release-planning.html) 以瞭解下一個版本何時推出。 另請參閱 [已棄用及已移除的功能](../../rn/using/deprecated-features.md).
