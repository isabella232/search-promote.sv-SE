---
description: 'null'
seo-description: 'null'
seo-title: Sök&stämpel;amp;Promote 15.3.1 Versionsinformation (03/24/2015)
solution: Target
title: Sök&stämpel;amp;Promote 15.3.1 Versionsinformation (03/24/2015)
topic: Release Notes,Site search and merchandising
uuid: f02da5a4-2207-4603-aa05-5cff7be16dd5
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 15.3.1 Versionsinformation (03/24/2015){#search-promote-release-notes}

## Nya funktioner och förbättringar {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Söker efter produktmodellnummer - En ny inställning för språk som gör att du kan dela tokens i alfabetiska siffror. Med den här funktionen kan du göra mer flexibla fritextmatchningar på delar- eller produktliknande tokens.

   Se **[!UICONTROL Partial Alphanumeric Matching]** i [Konfigurera hur söktermer matchas med ditt webbinnehåll..](../c-about-linguistics-menu/c-about-words-and-language.md#task_351A9144A51F4B41923BDBACDEF3B616).

* Lagt till möjlighet att exportera datavyresultat.

   Se [Datavyer](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3).

* Dynamiskt genererade intervall för intervallattribut med autofacet-value-låsningsfunktioner.

   Adobe Systems kräver för närvarande att du tillhandahåller innehåll som identifierar intervallvärden för att göra detta. Om du till exempel anger priset 10 genererar du en intervallsträng (&quot;Mellan $10 och $20&quot;). Eller så kräver Adobe Systems att du använder skriptad filtrering. Nya attribut har lagts till i en metadatafältdefinition, endast för `Type=Number` fält. De nya alternativen associerar det numeriska fältet med ett `Type=Text` fält och anger konfigurationsinformation som beskriver hur intervallbeskrivningen skapas.

   Se [Lägga till ett nytt fält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)för metataggar.

## Korrigeringar {#section_22D1AFC99F394D569898828A0D3C419D}

* Dialogrutan för redigering av Fasetterad rälskarta ska innehålla mellanliggande fasetter.
* Tomma kärnsökresultat för inbäddat sökläge, för en sökning som innehåller japanska tecken.
* Tikakonverteringen av Word.docx-filer fyller nu i `title` attributet.
* Felaktiga dubblettbanderollmeddelanden i **[!UICONTROL Banner]** hanteraren har korrigerats.
* [!DNL Dynamic Media Classic] banners är nu protokollagnostiska.
* Fältattributet var ibland dolt när användardefinierade fält redigerades i användargränssnittet för metadata, även när det **[!UICONTROL Table Name]** **[!UICONTROL Dynamic Facets]** aktiverades för kontot.
* **[!UICONTROL Recent Searches]** inte längre multiplicera icke-ASCII-tecken.
* MDI-fält kan fyllas i utan att använda skriptbaserad filtrering.
* Fel kodning i förslag.
* utlösaren &quot;other facet selected&quot; fungerar nu korrekt med komplexa affärsregler.

