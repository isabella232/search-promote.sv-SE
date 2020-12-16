---
description: Du kan använda Lodrät uppdatering för att snabbt uppdatera delar av indexet utan att behöva bearbeta stora mängder data.
seo-description: Du kan använda Lodrät uppdatering för att snabbt uppdatera delar av indexet utan att behöva bearbeta stora mängder data.
seo-title: Om Lodrät uppdatering
solution: Target
subtopic: Vertical Update
title: Om Lodrät uppdatering
topic: Index,Site search and merchandising
uuid: ded09e89-5a52-4e8c-a6f7-3e25b4191183
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 0%

---


# Om lodrät uppdatering{#about-vertical-update}

Du kan använda Lodrät uppdatering för att snabbt uppdatera delar av indexet utan att behöva bearbeta stora mängder data.

## Använda lodrät uppdatering {#concept_E65A70C9C2E04804BF24FBE1B3CAD899}

Ett lodrätt index tar bara några sekunder att utföra och är användbart på e-handelswebbplatser med stor kapacitet som kan ta många timmar att antingen indexera helt eller stegvis.

När du genererar ett lodrätt index visas statusinformation, t.ex. starttid, förfluten tid och fel under indexeringsprocessen.

Du kan när som helst stoppa eller starta om den lodräta indexeringsprocessen.

Medan det nya lodräta indexet uppdaterar din aktiva webbplats kan kunderna fortsätta att söka på din webbplats med ditt nuvarande index.

>[!NOTE]
>
>Den här funktionen är inte aktiverad i [!DNL Adobe Search&Promote] som standard. Kontakta teknisk support för att aktivera funktionen.

Lodräta uppdateringar är särskilt avsedda att användas på e-handelskonton i [!DNL Adobe Search&Promote] som använder IndexConnector för att tillhandahålla innehållet för sökindexet. Det typiska användningsfallet är ett fall där indexet [!DNL Adobe Search&Promote] representerar en sökbar produktkatalog och behovet finns att snabbt kunna uppdatera värden som ändras ofta, till exempel lagerbehållning, tillgänglighet och/eller pris. En lodrät uppdatering liknar ett inkrementellt index, förutom att delar av varje dokument endast uppdateras, medan ett inkrementellt index ersätter hela dokument med nya versioner.

Termen&quot;Lodrät uppdatering&quot; avser begreppet att ett [!DNL Adobe Search&Promote]-index kan anges som en kolumntabell, där varje kolumn motsvarar en metadatafältdefinition för [!DNL Adobe Search&Promote] och varje rad motsvarar ett dokument. Processen Lodrät uppdatering ersätter en eller flera kolumner utan att något av de andra kolumnernas innehåll behöver ändras.

Där huvudkällan för innehåll, en IndexConnector-feed, innehåller alla nödvändiga dataelement som behövs för att skapa indexet, är den lodräta uppdateringsmatningen en delmängd av huvudmatningen, en som använder samma IndexConnector-schema för att definiera dataelementen, men som bara innehåller ** de dataobjekt som behöver uppdateras.

Som minimum måste flödet för lodrät uppdatering innehålla elementet&quot;primärnyckel&quot; (som identifieras med kryssrutan **primärnyckel** i konfigurationen för IndexConnector) och minst ett dataelement som ska uppdateras.

En primär IndexConnector-feed kan till exempel se ut så här (men oftast med många fler dataobjekt):

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <title><![CDATA[Title for product 123]]></title>
  <description><![CDATA[Description for product 123.]]></description>
  <price>3.99</price>
  <link><![CDATA[https://www.somewhere.com/products/123]]></link>
  <image><![CDATA[https://www.somewher.com/images/products/123.jpg]]></image>
  <label><![CDATA[PROD123]]></label>
  <inventory>100</inventory>
  <brand><![CDATA[brand123]]></brand>
  ...
</product>
<product>
...
</product>
</products>
```

Ett krav är att snabbt kunna uppdatera endast `<price>`- och `<inventory>`-värdena, eftersom dessa värden kan ändras snabbt på kundens webbplats. En lodrät uppdateringsfeed kan då se ut så här:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<products>
<product>
  <id><![CDATA[123]]></id>
  <price>3.50</price>
  <inventory>90</inventory>
</product>
<product>
...
</product>
</products>
```

Den här informationen lagras vanligtvis i en separat fil på kundens server och konfigurationsinställningen IndexConnector &quot;Vertical File Path&quot; pekar på den här filen. Den lodräta uppdateringsprocessen läser det nya innehållet och uppdaterar det befintliga [!DNL Adobe Search&Promote]-indexet, och uppdaterar bara värdena för `<price>` och `<inventory>`, i det här fallet. Efterföljande sökningar returnerar det nya uppdaterade innehållet.

>[!NOTE]
I det här exemplet måste metadatafälten `<price>` och `<inventory>` ha definierats med alternativet **Lodrätt uppdateringsfält** markerat.

Se även [Om fjärrstyrning för indexering](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F) och [Lägga till ett nytt metataggsfält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Konfigurera en lodrät uppdatering för en mellanlagrad webbplats {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

Du kan konfigurera vilka indexanslutningskällor du vill ta med i den lodräta uppdateringen genom att ange URL:er.

**Konfigurera en lodrät uppdatering av en mellanlagrad webbplats**

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Configuration]** på produktmenyn.
1. På sidan **[!UICONTROL Vertical Update Configuration]** anger du URL-adresserna för sidorna som du vill indexera i fältet Uppdatera URL-adresser.

   Sökroboten uppdaterar bara de dokument som identifieras i de angivna indexanslutningskällorna.

   Det här fältet får endast innehålla URL:er för indexkoppling enligt följande exempel:

   `index:product_catalog`.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Visa lodrät uppdateringslogg för en aktiv eller mellanlagrad webbplats {#task_E668E1F1240C476DAA1CA783DC728232}

När en live-vertikal uppdatering eller en mellanlagrad vertikal uppdatering är klar kan du visa tillhörande logg för att felsöka eventuella fel som kan ha inträffat.

Du kan inte exportera lodräta uppdateringsloggfiler och inte heller spara dem. Loggfilen är fortfarande tillgänglig för visning tills nästa index inträffar.

**Så här visar du lodrät uppdateringslogg för en aktiv eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Live Log]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Vertical Update]** > **[!UICONTROL Staged Log]**.

1. Gör något av följande på loggsidan, längst upp eller längst ned:

   * Använd navigeringsalternativen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** eller **[!UICONTROL Go to line]** för att gå igenom loggen.

   * Använd visningsalternativen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** eller **[!UICONTROL Show]** för att förfina det du ser.

