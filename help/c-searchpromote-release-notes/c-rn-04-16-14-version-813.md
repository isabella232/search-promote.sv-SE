---
description: 'null'
seo-description: 'null'
seo-title: Sökning&stämpel;amp;Promote 8.13.0 versionsinformation (04/16/2014)
solution: Target
title: Sökning&stämpel;amp;Promote 8.13.0 versionsinformation (04/16/2014)
topic: Release Notes,Site search and merchandising
uuid: b3524992-ff00-4a7c-a404-078242456734
translation-type: tm+mt
source-git-commit: 9d5ac055d665b39d09b28063179d74a389d7f830

---


# Search&amp;Promote 8.13.0 Release Notes (04/16/2014){#search-promote-release-notes}

| Nya funktioner och förbättringar | Beskrivning |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dynamiska ansikten med fullt stöd för tabellmatchning | Vissa kunder hade många&quot;SKU-nivåattribut&quot; som de ville välja och visa via Dynamic Facets. Du kan nu välja att associera varje dynamiskt facet-fält med upp till ett tabellnamn i en statisk kontokonfiguration. Dessa tabellrelationer kan sedan tillämpas vid sökningen för alla dynamiska facettsfält som ingår i sökningen. Se [Om dynamiska fakta](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899). |

**Korrigeringar**

* Beskrivningsfältet för datavyn har ändrats så att taggen används `<search-display-field>` i stället för `<search-description>`.
* En funktion har lagts till i Index Connector för att göra primärnyckeln till en sammanfogning av två eller flera fält.
* Ändrade skriptet AttributeLoader-Regen-Enabled `attributeloader-regen.pl` till att inte använda HTML-kodvärden.
* Matchad indextid och blankstegsbehandling vid sökning för&quot;intervallsökning&quot;-frågor.
* Om du lägger till en affärsregel kan det ibland leda till ett fel när Dynamic Facets har aktiverats.

   Se [Affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Ett JavaScript-fel förhindrade att en definition lades till eller redigerades i **Inställningar** > **SPIN** > **IndexConnector**.
* När en affärsregel har sparats verkade det som om tiden som valdes när affärsregeln skapades var standardvärdet för GMT-tidszonen. Efter att tidszonen för kontot sparats verkade det som om tidszonen för kontot användes.

   Se [Affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Sorteringen av affärsregler på scenen fungerade inte korrekt.

   Se [Affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Prestandarapporteringen har förbättrats genom att du kan schemalägga rapporter för e-postleverans.
* Det fasta affärsregelschemat ändrades automatiskt till sommartid.

   Se [Affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Om ett stort antal dynamiska facettsfält har definierats, har användarna fått långsamma svarstider för grundsökningar.
* Felaktiga indexfel för intervall inträffade.
* Dynamic Media Classic-åtkomst i datacentraler utanför Nordamerika bröts.
* SPIN XPath-valideringsfunktionen returnerade ett falskt positivt fel.

* Efter en SPIN-aktiverings-/inaktiveringsåtgärd omdirigerades användaren till inloggningssidan för medlemscentret.

