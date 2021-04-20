---
description: Du kan använda SEO-metataggar (sökmotoroptimering) för att anpassa vissa element på sidorna och på så sätt förbättra sökmotorplaceringen.
solution: Target
subtopic: SEO
title: Om SEO
topic: Settings,Site search and merchandising
uuid: 5c5d64f5-fe79-4489-85c6-399d1437f2c4
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 0%

---


# Om SEO{#about-seo}

Du kan använda SEO-metataggar (sökmotoroptimering) för att anpassa vissa element på sidorna och på så sätt förbättra sökmotorplaceringen.

## Använda SEO {#concept_C58BFCE720824A2B9B5F5E613CFD4C0B}

Du kan definiera varje sådant element som en del av starttexten följt av en lista med ord. Listan med ord kan innehålla följande:

* Vanliga sökfraser på din webbplats under en viss tidsperiod (till exempel&quot;sista månaden&quot;), med förbehåll för dina anpassade undantag.
* Värdeuppsättningar för ett eller flera fält från sökningen som sidan kom från.
* Statiska ord och fraser som du definierar i en lista

De vanligaste sidelementen som används för SEO är sidrubriken och metataggarna &quot;keywords&quot; och &quot;description&quot;. Du kan ange inställningar för dessa tre sidelement. Dessutom kan du definiera dessa tre inställningar för var och en av de tre sidtyperna: Sök på resultatsidor, bläddra bland sidor och objektinformationssidor.

När du sparar eller förhandsgranskar dina SEO-inställningar genereras små segment av sökmallar (transportmallar) som du kan inkludera i dina andra sökmallar med malltaggen `<search-include>`. Du kan t.ex. inkludera fältet Sökresultatsidors titel i en annan mall med följande:

```
<search-include file="seo/seo_search_title.tpl" />
```

De nio möjliga värdena för attributet `file` för taggen `<search-include>` för SEO-fält är följande:

* `seo/seo_search_title.tpl`
* `seo/seo_search_description.tpl`
* `seo/seo_search_keywords.tpl`
* `seo/seo_browse_title.tpl`
* `seo/seo_browse_description.tpl`
* `seo/seo_browse_keywords.tpl`
* `seo/seo_item_title.tpl`
* `seo/seo_item_description.tpl`
* `seo/seo_item_keywords.tpl`

Om du vill använda SEO-fält i en presentationsmall utför du flera steg.

Först använder du `<search-include>` enligt beskrivningen ovan för att inkludera de önskade fälten i en XML-sökmall i ett `<general>`-element.

Sedan omger du varje `<search-include>`-tagg med `<general-field>`- och `</general-field>`-taggar och ger fältnamnen i `name`-attributet som i följande exempel:

```
<general> 
    <general-field name="seo_search_title"><search-include file="seo/seo_search_title.tpl" /></general-field> 
    <general-field name="seo_search_description"><search-include file="seo/seo_search_description.tpl" /></general-field> 
    <general-field name="seo_search_keywords"><search-include file="seo/seo_search_keywords.tpl" /></general-field> 
</general>
```

I presentationsmallen kan du sedan använda `<guided-general-field>`-taggar för att infoga namngivna fält där du behöver dem, som i följande exempel:

```
<title><guided-general-field gsname="default" field="seo_search_title"></title> 
<meta name="description" content="<guided-general-field gsname="default" field="seo_search_description">"/> 
<meta name="keywords" content="<guided-general-field gsname="default" field="seo_search_keywords">"/>
```

Lägg märke till att attributet `gsname` används för att ange standardsökningen.

Du kan tillsammans definiera nio olika SEO-fält som du kan använda på dina webbsidor. De innehåller följande:

* Sökresultatsidor - titel, beskrivning och nyckelord
* Bläddra bland sidor - titel, beskrivning och nyckelord
* Artikeldetaljsidor - titel, beskrivning och nyckelord

Alla nio fält definieras med liknande inställningar. Namnen på de nio fälten, till exempel fältet &quot;titel&quot; i &quot;Sökresultatsidor&quot;, är bara förslag på hur du kan använda dem. Du kan använda alla fält i valfri kontext i presentationsmallar och sökmallar.

Se även [Om mallar](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

Se även [Presentationsmalltaggar](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

Se även [Sök efter malltaggar](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Se även [Konfigurera en sökresultatordlista](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).

## Konfigurera en sökresultatordlista {#task_A459A3734EC04042BA52C81184251DD4}

Du kan konfigurera listan med sökresultatord och fraser som ingår i sidrubriker, beskrivningar och nyckelord.

**Konfigurera en sökresultatordlista**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]** på produktmenyn.
1. På sidan [!DNL SEO Browse Pages Word List] anger du önskade alternativ i respektive [!DNL Title]-, [!DNL Description]- och [!DNL Keywords]-grupper.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Titel | Beskrivning | Nyckelord börjar med </p> </td> 
      <td colname="col2"> <p>Den text som du vill visa framför ordlistan. </p> <p>Du kanske vill att nyckelordslistan ska börja med ordet"Varumärken". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkludera populära sökningar under </p> </td> 
      <td colname="col2"> <p>Den tidsperiod för vilken sökningar ingår. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximalt antal sökningar </p> </td> 
      <td colname="col2"> <p>Maximalt antal sökningar som ingår. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkludera fältvärden </p> </td> 
      <td colname="col2"> <p>Fältvärdena som ingår i resultatordlistan. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lägg till dessa ord och fraser </p> </td> 
      <td colname="col2"> <p>Visa en lista med de ord som du vill lägga till i sökresultatsidans titel, bläddringssidans titel eller objektets informationssidtitel. </p> <p>Klicka på <b>Redigera</b> om du vill lägga till ord i listan. </p> <p>Du kan lägga till ett ord eller en fras per rad. När du är klar klickar du på <b>Spara ändringar</b> och stänger sedan sidan för att återgå till SEO-huvudsidan. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ta bort dessa ord och fraser (förutom från inkluderade fältvärden) </p> </td> 
      <td colname="col2"> <p>Visa en lista med de ord som du vill ta bort från sökresultatsidans titel, bläddringssidans titel eller objektets informationssidtitel. </p> <p>Klicka på <b>Redigera</b> om du vill lägga till ord i listan Ta bort. </p> <p>Du kan lägga till ett ord eller en fras per rad. När du är klar klickar du på <b>Spara ändringar</b> och stänger sedan sidan för att återgå till SEO-huvudsidan. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Valfritt) Klicka på **Förhandsgranska exempelutdata** om du vill förhandsgranska resultatvärdena för de SEO-fält som du anger.

   Se [Förhandsgranska SEO-metataggar som du konfigurerade](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Klicka på **Spara ändringar**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL SEO Search Results Word List]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurera en bläddringssidordlista {#task_D7A1D765A92A4D6C94E672B3A86ECB5A}

Du kan konfigurera listan med bläddringssidor, ord och fraser som ingår i sidrubriker, beskrivningar och nyckelord.

**Konfigurera en ordlista för bläddringssidor**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Browse Pages]** på produktmenyn.
1. På sidan [!DNL SEO Browse Pages Word List] anger du önskade alternativ i respektive [!DNL Title]-, [!DNL Description]- och [!DNL Keywords]-grupper.

   Se tabellen med alternativ under [Konfigurera en sökresultatordlista](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).
1. (Valfritt) Klicka på **Förhandsgranska exempelutdata** om du vill förhandsgranska resultatvärdena för de SEO-fält som du anger.

   Se [Förhandsgranska SEO-metataggar som du konfigurerade](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Klicka på **Spara ändringar**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL SEO Browse Pages Word List]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurera en ordlista för objektdetaljer {#task_761538C519B34164BE189F13C39B2495}

Du kan konfigurera listan med artikeldetaljord och fraser som ingår i sidrubriker, beskrivningar och nyckelord.

**Så här konfigurerar du en ordlista med objektdetaljer**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Item Detail Pages]** på produktmenyn.
1. På sidan [!DNL SEO Item Detail Word List] anger du önskade alternativ i respektive [!DNL Title]-, [!DNL Description]- och [!DNL Keywords]-grupper.

   Se tabellen med alternativ under [Konfigurera en sökresultatordlista](../c-about-settings-menu/c-about-seo.md#task_A459A3734EC04042BA52C81184251DD4).
1. (Valfritt) Klicka på **Förhandsgranska exempelutdata** om du vill förhandsgranska resultatvärdena för de SEO-fält som du anger.

   Se [Förhandsgranska SEO-metataggar som du konfigurerade](../c-about-settings-menu/c-about-seo.md#task_3F97949E193C4F92A104AD117FE49621).
1. Klicka på **Spara ändringar**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL SEO Item Detail Word List]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Förhandsgranska SEO-metataggar som du konfigurerade {#task_3F97949E193C4F92A104AD117FE49621}

Du kan förhandsgranska resultatvärdena för de SEO-fält som du anger för att se vad som infogas där du använder dem.

SEO-fält kan innehålla inkluderade fältvärden, så sökresultaten kan vara beroende av den sökfråga du anger.

**Så här förhandsgranskar du SEO-metataggar som du har konfigurerat**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL SEO]** > **[!UICONTROL Search Result Pages]** på produktmenyn.
1. Klicka på **Förhandsgranska exempelutdata** på SEO-sidan.
1. På sidan [!DNL SEO Preview] skriver du den frågeterm du vill söka efter i fältet [!DNL Enter sample query].
1. Klicka på **Sök**.

   I de resulterande fälten Titel, Beskrivning och Nyckelord visas innehållet som infogats på en sida baserat på den sökfråga du just angav.
1. Klicka på **Stäng** för att återgå till SEO-huvudsidan.
