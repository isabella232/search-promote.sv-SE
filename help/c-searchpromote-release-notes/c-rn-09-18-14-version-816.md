---
description: Sök&amp;Promote 8.16.0 versionsinformation.
solution: Target
title: Sökning&stämpel;amp;Promote 8.16.0 Versionsinformation (9/18/2014)
topic: Versionsinformation,Webbplatssökning och -försäljning
uuid: 0a59858b-213b-40d6-aea1-d085c4d6d2fa
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# Versionsinformation för Search &amp; Promote 8.16.0 (9/18/2014){#search-promote-release-notes}

## Versionsinformation om Search &amp; Promote 8.16.0 (9/18/2014) {#topic_5BECD3F66C684987828F6AE65E62DA29}

## Nya funktioner {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Cachelagring av sökresultat i den guidade sökningen 3 (GS3) - Om du vill att den här anpassade funktionen ska vara konfigurerad för dig så att du kan använda den i ditt konto kontaktar du den tekniska kontohanteraren för Adobe.
* Lodräta uppdateringar för fält som ändrats ofta - Nu kan du snabbt uppdatera alla värden för en uppsättning metadatafält utan att du behöver indexera om innehållet helt.

   Se alternativet Lodrätt uppdateringsfält i tabellen i [Lägga till ett nytt meta tag-fält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5) och [Om lodrät uppdatering](../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899).

   Den här funktionen kan bara användas på [!DNL Adobe Search&Promote]-konton som använder Index Connector. Om du vill att den här anpassade funktionen ska vara konfigurerad för dig så att du kan använda den i ditt konto kontaktar du den tekniska kontohanteraren för Adobe.

## Korrigeringar och förbättringar {#section_22D1AFC99F394D569898828A0D3C419D}

* Tolkningen av XML-feeds som innehöll `?>`-strängen har korrigerats.
* Fast indexanslutnings-SFTP-feeds när minsta antal dokument användes.
* Rapportexport till Microsoft Excel har nu stöd för UTF8.
* Guidad sökning: kompileringen av ansikten var långsam.
* Attributinläsare: sammanställningsdata hade dubblettnycklar.
* Felaktig körningsordning för affärsregel har korrigerats när en enskild regel aktiverades.
* Felaktiga Ångra-länkar genererades av guidad sökning.
* En ny fjärrkontrollsåtgärd har lagts till ( `sp_lines=N`) som gör att du kan kontrollera förloppet och statusen för en crawl som körs för tillfället.

   Se [Om fjärrstyrning för indexering](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

* Du måste skicka autentiseringsinformation när du hämtar tar bort information vid inkrementell indexkoppling.
* [!DNL Change Log]-rapporten identifierar nu den användare som initierar en manuell indexåtgärd.

   Se [Visa ändringsloggen](../c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

* När du exporterar en [!DNL Terms Report] är du inte längre begränsad till 500 eller färre objekt i rapporten.

   Se [Visa termrapporten eller Null Search Terms Report...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* Inställningen för indexkoppling **[!UICONTROL Strip HTML]** visades alltid som markerad.
* Inkonsekventa sökresultat har uppnåtts med funktionen **[!UICONTROL Common Phrases]**.
* Visning av attributnamn trunkerades i sammanfattningar av regellistan.
* Att publicera en regel för enskilda företag innebar att alla affärsregler blev verklighet.

