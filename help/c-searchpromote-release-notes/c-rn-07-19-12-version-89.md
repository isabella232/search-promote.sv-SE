---
description: Sök&amp;Promote 8.9 versionsinformation.
solution: Target
title: Sökning&stämpel;amp;Promote 8.9 Versionsinformation (07/19/2012)
topic: Versionsinformation,Webbplatssökning och -försäljning
uuid: 3853c75d-19ed-4e36-9e81-dcbffe5f5b0c
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 0%

---


# Versionsinformation för Search &amp; Promote 8.9 (07/19/2012){#search-promote-release-notes}

**Nya funktioner**

* Förbättrad metadatahantering - dynamisk metadatadefinition från kundflöden

   Skapa ett schema för att dynamiskt konfigurera om ditt Search &amp; Promote-konto baserat på metadatadefinitioner som kunden tillhandahållit.
* Förbättrade indexeringsprestanda - Index Loader

   Index Loader är ett nytt sätt att importera XML-innehåll direkt till ett Search &amp; Promote-index. Det är en delmängd av den befintliga funktionen för Index Connector som är utformad för att snabbt importera våra standardfiler för XML-flöden.

**Korrigeringar och förbättringar**

* Stöd för att ändra sorteringsalternativet med hjälp av en affärsregel har lagts till.
* I hjälpsystemets `<search-description>`-tagg visas brödtexten i stället när metataggen för beskrivningen har tomt innehåll.
* Lagt till möjlighet att spåra tillämpliga tabellträffar för resultat som lagts till med hjälp av resultatbaserade åtgärder.
* Stöd för att skicka frågeparametrar via POST har lagts till
* Vid crawlning kan i vissa fall en slutgiltig mirror_account-åtgärd hoppas över.
* Adobe Analytics URL:er innehåller inte CGI-argument och den Search &amp; Promote som Adobe Analytics-sökningar behöver för att på liknande sätt ta bort CGI-argument från URL-nycklar.
* Regler för att skriva om försvinner då och då från användargränssnittet när de har publicerats.
* Search &amp; Promote med Menade du inställningar som var inställda på att ge förslag på grund av låga resultat kan få återkommande resultat.
* Det gick inte att skriva om regeltestutdata med radbrytningar.
* Sidan URL-regler för sökning och sidan URL-regler för crawllistearkiv pekar på fel historiksida.
* Om du klickar på Redigera på vissa banderoller visas inte sidan Redigera.
* Det kan ibland ta lång tid att rangordna uppdateringskoden.
* Det gick inte att ta bort eller flytta ett ansiktsobjekt om ansiktsnamnet har blandat skiftläge.

