---
title: 更新和維護作業
description: 有關Adobe Campaign伺服器更新和維護作業的資訊。
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
TQID: https://experienceleague.adobe.com/aWpRR9r5jK3vVHxO9-xFPrVSyTI9Cg2rIBJ6AzvEONQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 169
ht-degree: 33%

---

# 更新和維護作業{#updates-and-maintenance-operations}

為了進行維護，Adobe Campaign伺服器每天早上6:00重新啟動（伺服器時區）。 請聯絡Adobe以瞭解伺服器時間。 此作業是自動且透明的。 不過，我們建議您不要在重新啟動之前執行任何資料處理作業。 例如，請避免在重新啟動前啟動工作流程，請將工作流程排程在重新啟動後一分鐘開始。

Adobe透過新增新功能、增強功能和修正不斷改進其解決方案。 所有 Adobe Campaign Standard 執行個體都會隨著每個新版本升級。 升級不需要任何動作。 升級分兩個階段部署。 首先，Stage 執行個體已升級，可讓我們的客戶測試新功能並視需要調整其配置。 隨後將升級生產執行個體。 請參閱[發行計畫](https://helpx.adobe.com/tw/campaign/kb/acs-release-planning.html)，瞭解下一個發行將於何時發生。 另請參閱[已棄用和已移除的功能](../../rn/using/deprecated-features.md)清單。
