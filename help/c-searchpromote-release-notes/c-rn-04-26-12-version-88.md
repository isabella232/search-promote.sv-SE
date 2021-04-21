---
description: Sök&amp;Promote 8.8 versionsinformation.
solution: Target
title: Söka&amp;Promote 8.8 Versionsinformation (04/26/2012)
topic-legacy: Release Notes,Site search and merchandising
uuid: ddb9f1af-92a4-4f85-be8f-a36f34d31add
exl-id: 3bd9b6af-99a2-4631-b7a7-0a792122c157
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Versionsinformation för Search &amp; Promote 8.8 (04/26/2012){#search-promote-release-notes}

**Nya funktioner**

* Dynamisk faceting

   Möjlighet att dynamiskt motstå en friformsuppsättning med attribut som är kopplade till varje sida med webbplatsinnehåll, som kan ändras (nya attribut läggs till, gamla tas bort eller döps om) från index till index. Dynamisk fasettering mappar automatiskt facken med de verkliga ansiktena. Lagret för guidad sökning hjälper till att underlätta den här funktionen med affärsregler.
* Adobe Search &amp; Promote användargränssnitt

   Adobe-användargränssnittet har implementerats på alla webbsidor på Adobe Search &amp; Promote.
* Bättre integrering med Adobe inloggningsportal

   Adobe Search &amp; Promote-kunder kan endast använda inloggningsportalen för Adobe. Befintliga [!DNL Adobe Publish]-, Adobe SiteSearch- och Atomz-kunder kommer att fortsätta använda den gamla inloggningen.
* Ny morfologisk analyserare som stöder kinesiska och japanska

   Morfologisk analys tillämpas på index och på söktiden för stöd av kinesiska och japanska.
* Stöd för nya dokumenttyper, som Microsoft Office 2010

   Vid sökning kan olika typer av dokument, som .doc, .docx, .pdf och .mp3, konverteras till HTML innan de matas in i indexeraren.
* Det nya onlinehjälpsystemet Adobe Search &amp; Promote

   Onlinehjälpsystemet har ett nytt användargränssnitt och är nu uppgiftsbaserat.

**Korrigeringar och förbättringar**

* Korrigerad överföring av en banderoll live med Stage Manager som resulterade i trasig Dynamic Media Classic-relaterad funktionalitet i realtid.
* Ett problem har korrigerats där redigeringen av en regel med utlösaren &quot;Frågeparametern finns inte&quot; översattes felaktigt till &quot;Nyckelordet innehåller&quot;.
* Ett problem har korrigerats där du inte kunde redigera parameter andra gången.
* Korrigerade ett problem med Index Connector där två eller flera mappningsdefinitioner inte kan peka på samma metadata/fältvärde.
* Problem med att crawla vissa PDF-dokument har åtgärdats. Uppgradering till 3.03 löser de senaste krascher.
* Lagt till möjlighet till kortare beskrivningar av affärsregler (t.ex. visning av field_table i hanteraren).
* Navigeringsmenyn Guidad sökning hade maximalt nio alternativ. Nu är maxvärdet 20.
* Prestandaförbättringar har gjorts i Index Connector.
