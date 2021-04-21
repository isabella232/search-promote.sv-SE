---
description: Search&amp;Promote 8.14.0 Release Notes.
solution: Target
title: Sökning&stämpel;amp;Promote 8.14.0 Versionsinformation (05/22/2014)
topic-legacy: Release Notes,Site search and merchandising
uuid: 308d84a9-ec38-4fec-b146-e8a353e65be4
exl-id: fcc00d85-128e-4015-aa82-7d31606cb076
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 0%

---

# Versionsinformation för Search &amp; Promote 8.14.0 (05/22/2014){#search-promote-release-notes}

**Korrigeringar**

* Om [!DNL sqlite_open] misslyckas flyttas den gamla SQL-databasfilen bort från vägen och en ny skapas från grunden.
* De viktigaste sökresultaten var inkonsekventa när samma sökning upprepades.
* Prestandaförbättring av mallbearbetning när det finns många fält som genereras per sökresultat.
* Anteckningar har lagts till i **[!UICONTROL Business Rule History]**.
* Prestanda för de resultatbaserade utlösarna och åtgärderna i omgenereringsfasen för förhandsgranskningsindex, under indexeringsåtgärder, försämras stadigt över tiden.
* Alternativet **[!UICONTROL Reset SPIN cache]** har ändrats från booleskt nej/nästa körning till ett trimläge: no/always/next-run.
