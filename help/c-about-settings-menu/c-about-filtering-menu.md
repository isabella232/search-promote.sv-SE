---
description: Använd filtermenyn för att använda skript som ändrar innehållet i ett webbdokument innan det indexeras.
solution: Target
subtopic: Filtering
title: Om menyn Filtrera
topic: Inställningar,Webbplatssökning och -försäljning
uuid: ebb08fa8-4e17-417d-868b-11fc2af9f284
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '4008'
ht-degree: 0%

---


# Om filtermenyn{#about-the-filtering-menu}

Använd filtermenyn för att använda skript som ändrar innehållet i ett webbdokument innan det indexeras.

## Om att filtrera skript {#concept_E56B73D625854AB2A899EF2D56CFCB47}

Du kan använda [!DNL Filtering Script] för att ändra innehållet i ett webbdokument innan det indexeras.

Du kan infoga HTML-taggar, ta bort irrelevant innehåll och till och med skapa nya HTML-metadata baserat på dokumentets URL, MIME-typ och befintligt innehåll. Filtreringsskriptet är ett Perl-skript som ger kraftfull stränghantering och flexibilitet vid matchning av reguljära uttryck. Du använder filtreringsskriptet med ett initieringsskript, ett avslutningsskript, ett URL-maskskript och en test-URL.

Filtreringsskriptet körs varje gång ett dokument läses från webbplatsen. Skriptet körs som ett standardfilter, d.v.s. läser data från STDIN, omformar data på något sätt och skriver resultaten till STDOUT. Du kan använda filtreringsskriptet för att skriva ut statusmeddelanden från filtreringsskriptet till indexloggen. Du skriver antingen ut meddelandena till STDERR eller via underrutinen `_search_debug_log()`.

En del alternativ för GNU-differenser som du kan använda i läget **[!UICONTROL Expert (diff)]** på sidan Skript för mellanfiltrering inkluderar följande:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU-differensalternativ </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar i mängden tomt utrymme. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar som infogar eller tar bort tomma rader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> Använder kontextutdataformatet, som visar tre kontextrader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C rader  </span> </p> </td> 
   <td colname="col2"> <p> Använder kontextutdataformatet, visar kontextrader (heltal) eller tre om rader inte anges. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar i fallet, motsvarar gemener och versaler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Skapar utdata som ser ut som ett skript med ände men som har ändringar i den ordning de visas i filen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> Ger RCS-formatsskillnader, som <span class="codeph"> -f </span> förutom att varje kommando anger antalet rader som påverkas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Använder det enhetliga utdataformatet, som visar tre kontextrader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U rader  </span> </p> </td> 
   <td colname="col2"> <p> Använder det enhetliga utdataformatet, visar rader (ett heltal) i kontexten eller tre om rader inte anges. </p> </td> 
  </tr> 
 </tbody> 
</table>

Du kan använda lokala variabler, globala variabler eller båda i dessa skript. Alla globala variabler förskrivs med namnutrymmet&quot;main::&quot;. När filtreringsskriptet startas innehåller dess miljö följande standardfilreferenser:

* STDIN - ingenting (returnerar omedelbart EOF vid läsning)
* STDOUT - ersättnings-HTML (om data skrivs ut till STDOUT används den i stället för det ursprungliga dokumentet)
* STDERR - data som skrivs ut till STDERR skrivs ut till indexloggen som ett fel

Dessutom kan du skriva egna meddelanden i indexloggen med hjälp av underrutinen `_search_debug_log()`, som i följande exempel:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Dessa meddelanden visas med ordet `DEBUG` som preface och loggas inte som fel.

Följande är ett exempel på filtrering. Webbsidesfält `<title>` börjar ofta med företagsnamnet. Även om den här informationen är användbar för webbplatsnavigering är den inte relevant vid sökning. Om rubrikerna för alla MegaCorp-webbsidor börjar med en gemensam sträng, till exempel följande:

```
<title>MegaCorp -- meaningful title 
here</title>
```

Du bör ta bort &quot; `MegaCorp --`&quot; från början av varje dokumenttitel och räkna alla dokument som bearbetas med filtreringsskriptet. Om du vill göra det kan du använda följande skript:

```
# Make sure this is an HTML document. 
if ($main::ws_content_type =~ /^text\/html/) { 
    # Read the entire document into a local scalar variable. 
    my @docarray = <>; 
    my $doc = join("", @docarray); 
 
    # Remove "MegaCorp -- " from the title. 
    $doc =~ s/(<TITLE>)MegaCorp -- /$1/gis; 
 
    # Print the resulting document. 
    print $doc; 
 
    # Count that we've filtered one more document. 
    $main::doc_count++; 
}
```

## Globala variabler {#global-variables}

Du kan använda följande variabler i alla filtreringsskript:

| Variabel | Beskrivning |
|--- |--- |
| `$main::search_crawl_type` | Värdet `$main::search_crawl_type` anger vilken typ av indexåtgärd som pågår.  Föråldrat formulär: `$main::ws_crawl_type` Indexåtgärderna och tillhörande värden omfattar följande: <ul><li>Fullständigt index: Manuell - `manual`</li><li>Fullständigt index: Schemalagd - `auto`</li><li>Fullständigt index: Fjärrkontroll - `CGI`</li><li>Inkrementellt index: Manuell - `manual-incremental`</li><li>Inkrementellt index: Schemalagd - `auto-incremental` </li><li>Inkrementellt index: Fjärrkontroll - `CGI-incremental`</li><li>Skriptade index: Manuell - `manual-indexlist.txt` </li><li>Skriptade index: Schemalagd - `auto-indexlist.txt`</li><li>Skriptade index: Fjärrkontroll - `CGI-indexlist.txt`</li><li>Återskapa - `manual-upgrade`</li></ul> |
| `$main::search_clear_cache` | Värdet anger om indexeringsalternativet &quot;Rensa indexcache&quot; begärdes för den aktuella indexåtgärden. Om &quot;Rensa indexcache&quot; begärdes är värdet `$main::search_clear_cache` &quot; `1`&quot;.  Föråldrat formulär: `$main::ws_clear_cache` |
| `$main::search_fields` | Värdet innehåller en tabbavgränsad lista med metadatafält som är definierade i kontot. Som standard är värdet:   `url title desc keys target body alt date charset language` Föråldrat format: `$main::ws_fields` |
| `$main::search_collections` | Värdet innehåller en tabbavgränsad lista med de samlingar som är definierade i kontot.  Föråldrat formulär: `$main::ws_collections` |
| `$main::search_url` | Värdet är dokumentets fullständiga URL.  Föråldrat formulär: `$main::ws_url` |
| `$main::search_content_type` | Värdet är dokumentets innehållstyp som hämtats från meta-taggen http-equiv. Ett typiskt värde är &quot;text/html; charset=iso-8859-1&quot;.  Föråldrat formulär: `$main::ws_content_type` |
| `$main::search_content_class` | Värdet är dokumentets innehållsklass som härleds från innehållstypfältet.  Föråldrat formulär: `$main::ws_content_class` |
| `$main::search_syntax_check` | Värdet återspeglar användningen av knappen Kontrollera syntax. Om du klickar på det är värdet 1 (ett); i annat fall är dess värde 0 (noll).  Föråldrat formulär: `$main::ws_syntax_check` |
| `$main::search_last_mod_date` | Om det anges av webbservern innehåller det här värdet Epoch-representationen (sekunder sedan 1 januari 1970) av dokumentets senaste ändringsdatum.  Du kan formatera det här värdet med biblioteksanropet Perl localtime(). |

### Snabbtips {#section_89A5C16911744AF98E232DF608C6A1F5}

* Alla globala variabler är förinställda med namnutrymmet&quot;main::&quot;: `$main::doc_count = 0;`
* Alla lokala variabler deklareras med &quot;my&quot;: `my $i = 0;`
* Underrutiner definieras i initieringsskriptet. De behöver inte ett explicit &quot;main:::&quot;-namnutrymme: `sub my_sub {` `...`

   `}`

* Testa `$main::search_content_type` innan du gör ändringar i en fil. Testerna kan hjälpa dig att undvika slarviga ändringar i binära filer, som SWF-filer eller PDF-filer:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type` är den fullständiga Content-Type-rubriken som levereras av servern. Den kan ibland innehålla en enkel MIME-typ, till exempel&quot;text/html&quot;. Eller så kan den innehålla en MIME-typ följt av annan information, som dokumentets teckenuppsättningskodning, t.ex. &quot;text/html; charset=iso-8859-1&quot;.
* För varje typ av dokument som inte är HTML kan `$main::search_content_type` ha olika värden. Testning av varje värde i skriptet blir krångligt. Vissa Word-dokument har till exempel innehållstypsvärdena &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot; eller &quot;application/x-msword&quot;. I sådana fall kan `$main::search_content_class` anta följande värden:

   * html
   * pdf
   * ord
   * excel
   * powerpoint
   * mp3
   * text

* I exemplet skulle testning av `$main::search_content_class` för &quot;word&quot; matcha något av de tre möjliga innehållstypsvärdena.
* Om inget skrivs ut till STDOUT från filtreringsskriptet används dokumentet exakt som det hämtades. Det innebär att om du inte behöver ändra något i ett dokument behöver du inte kopiera STDIN till STDOUT för det dokumentet.
* Om du vill ta bort all text från ett dokument skriver du ut en giltig STDOUT-fil. Om du till exempel vill ta bort all text helt från ett HTML-dokument gör du följande: `print "<html></html>";`

## Lägga till ett filtreringsskript {#task_0AB84FD1133F47F9AA069A79BEA13A22}

Filtreringsskriptet är ett Perl-skript som körs för varje dokument som hämtas från din webbplats.

Du använder filtreringsskriptet tillsammans med ett initieringsskript, ett avslutningsskript och ett URL-maskskript.

Se till att du återskapar webbplatsindexet så att resultaten av filtreringsskriptet blir synliga för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Lägga till ett filtreringsskript**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Filtering Script]** på produktmenyn.
1. (Valfritt) På sidan [!DNL Filtering Script] anger du URL:en för ett dokument på webbplatsen i fältet [!DNL Test URL].

   Klicka på ett testalternativ om du vill se ändringar i den oformaterade HTML-texten.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Test URL field </p> </td> 
      <td colname="col2"> <p>Här kan du ange URL-adressen till ett dokument på webbplatsen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Testa </p> </td> 
      <td colname="col2"> <p>Testar URL:en mot filtreringsskript och URL-masker. </p> <p>Test-URL-dokumentet laddas ned, som sedan används som STDIN-indata till filtreringsskriptet. Initierings-, filtrerings- och avslutningsskripten körs sedan. Om det finns några STDOUT-utdata från filtreringsskriptet visas utdata i ett nytt webbläsarfönster. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Endast test </p> </td> 
      <td colname="col2"> <p>Testar endast skriptets åtgärd. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Förhandsgranska </p> </td> 
      <td colname="col2"> <p>Här kan du visa sidan. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Full visuell </p> </td> 
      <td colname="col2"> <p>Skapar en fullständig före och efter-tabellvy av dokumenten. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kort visuell </p> </td> 
      <td colname="col2"> <p>Visar endast skillnaderna mellan vyerna före och efter. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Expert (diff) </p> </td> 
      <td colname="col2"> <p>Visar rå utdata för det GNU-differenskommando som används för att jämföra filerna, med de angivna kommandoradsalternativen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Filtrera skript </p> </td> 
      <td colname="col2"> <p>Gör att du kan klistra in filtreringsskriptet i fältet som visas. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Spara ändringar </p> </td> 
      <td colname="col2"> <p>Sparar filtreringsskriptet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kontrollera syntax </p> </td> 
      <td colname="col2"> <p>Gör att du snabbt kan kontrollera skriptet genom att köra initierings-, filtrerings- och avslutningsskript. Skriptet uppdateras inte och sparas. </p> <p>Alla Perl-kompileringsfel och -varningar och alla STDERR-utdata skrivs ut. </p> <p>Innan skriptets effekter syns för kunderna måste du återskapa webbplatsindexet. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   **alternativ för GNU-differens på kommandorad**

   En del alternativ för GNU-differenser som du kan använda i läget **[!UICONTROL Expert (diff)]** på sidan Skript för mellanfiltrering inkluderar följande:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>GNU diff-kommandoradsalternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
      <td colname="col2"> <p> Ignorerar ändringar i mängden tomt utrymme. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
      <td colname="col2"> <p> Ignorerar ändringar som infogar eller tar bort tomma rader. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
      <td colname="col2"> <p> Använder kontextutdataformatet, som visar tre kontextrader. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -C rader  </span> </p> </td> 
      <td colname="col2"> <p> Använder kontextutdataformatet, visar kontextrader (heltal) eller tre om rader inte anges. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
      <td colname="col2"> <p> Ignorerar ändringar i fallet, motsvarar gemener och versaler. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
      <td colname="col2"> <p> Skapar utdata som ser ut som ett skript med ände men som har ändringar i den ordning de visas i filen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
      <td colname="col2"> <p> Ger RCS-formatsskillnader, som <span class="codeph"> -f </span> förutom att varje kommando anger antalet rader som påverkas. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>-u </p> </td> 
      <td colname="col2"> <p> Använder det enhetliga utdataformatet, som visar tre kontextrader. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <span class="codeph"> -U rader  </span> </p> </td> 
      <td colname="col2"> <p> Använder det enhetliga utdataformatet, visar rader (ett heltal) i kontexten eller tre om rader inte anges. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Test]** för att testa mot filtreringsskript och URL-masker.

   Om du klickar på **[!UICONTROL Test]** uppdateras inte och du sparar ditt filtreringsskript.
1. Klistra in skriptet i fältet [!DNL Filtering Script].
1. (Valfritt) Klicka på **[!UICONTROL Check Syntax]** för att utföra en snabb syntaxkontroll av skriptet genom att köra skripten för filtrering, initiering och avslutning.

   **[!UICONTROL Check Syntax]** uppdaterar inte och sparar skriptet.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Filtering Script]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om initieringsskript {#concept_048B4C8BC9F74BE8BB6162C490C201A3}

Du kan använda [!DNL Initialization Script] för att ändra innehållet i ett webbdokument innan det indexeras.

Du kan infoga HTML-taggar, ta bort irrelevant innehåll och till och med skapa nya HTML-metadata baserat på dokumentets URL, MIME-typ och befintligt innehåll. Initieringsskriptet är ett Perl-skript som ger kraftfull stränghantering och flexibilitet vid matchning av reguljära uttryck. Du använder initieringsskriptet med ett filtreringsskript, ett avslutningsskript, ett URL-maskskript och en test-URL.

Initieringsskriptet körs en gång innan indexeringen börjar. Använd det här skriptet för att initiera globala variabler och underrutiner som används av ditt filtreringsskript. Du kan använda initieringsskriptet för att skriva ut statusmeddelanden från filtreringsskriptet till indexloggen. Du skriver antingen ut meddelandena till STDERR eller via underrutinen `_search_debug_log()`.

En del alternativ för GNU-differens som du kan använda i **[!UICONTROL Expert (diff)]**-läge på sidan Staged Initialization Script inkluderar följande:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU-differensalternativ </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar i mängden tomt utrymme. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar som infogar eller tar bort tomma rader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> Använder kontextutdataformatet, som visar tre kontextrader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C rader  </span> </p> </td> 
   <td colname="col2"> <p> Använder kontextutdataformatet, visar kontextrader (heltal) eller tre om rader inte anges. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar i fallet, motsvarar gemener och versaler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Skapar utdata som ser ut som ett skript med ände men som har ändringar i den ordning de visas i filen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> Ger RCS-formatsskillnader, som <span class="codeph"> -f </span> förutom att varje kommando anger antalet rader som påverkas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Använder det enhetliga utdataformatet, som visar tre kontextrader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U rader  </span> </p> </td> 
   <td colname="col2"> <p> Använder det enhetliga utdataformatet, visar rader (ett heltal) i kontexten eller tre om rader inte anges. </p> </td> 
  </tr> 
 </tbody> 
</table>

Du kan använda lokala variabler, globala variabler eller båda i dessa skript. Alla globala variabler förskrivs med namnutrymmet&quot;main::&quot;. När initieringsskriptet startas innehåller dess miljö följande standardfilreferenser:

* STDIN - ingenting (returnerar omedelbart EOF vid läsning)
* STDOUT - ingenting (om data skrivs ut till STDOUT, ignoreras det)
* STDERR - data som skrivs ut till STDERR skrivs ut till indexloggen som ett fel

Dessutom kan du skriva egna meddelanden i indexloggen med hjälp av underrutinen `_search_debug_log()`, som i följande exempel:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Dessa meddelanden visas med ordet `DEBUG` som preface och loggas inte som fel.

Ett exempel på ett initieringsskript är följande:

```
# My subroutine to do something. 
sub my_sub_for_the_filtering_script { 
    my ($param1, $param2) = @_; 
    ... 
} 
 
# Initialize the document counter. 
$main::doc_count = 0;
```

Se [Globala variabler](#global-variables)

### Snabbtips {#section_A2CC0302CAF14135BF8EF6171FB184F1}

* Alla globala variabler är förinställda med namnutrymmet&quot;main::&quot;: `$main::doc_count = 0;`
* Alla lokala variabler deklareras med &quot;my&quot;: `my $i = 0;`
* Underrutiner definieras i initieringsskriptet. De behöver inte ett explicit &quot;main:::&quot;-namnutrymme: `sub my_sub {` `...`

   `}`

* Testa `$main::search_content_type` innan du gör ändringar i en fil. Testerna kan hjälpa dig att undvika slarviga ändringar i binära filer, som SWF-filer eller PDF-filer:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type` är den fullständiga Content-Type-rubriken som levereras av servern. Den kan ibland innehålla en enkel MIME-typ, till exempel&quot;text/html&quot;. Eller så kan den innehålla en MIME-typ följt av annan information, som dokumentets teckenuppsättningskodning, t.ex. &quot;text/html; charset=iso-8859-1&quot;.
* För varje typ av dokument som inte är HTML kan `$main::search_content_type` ha olika värden. Testning av varje värde i skriptet blir krångligt. Vissa Word-dokument har till exempel innehållstypsvärdena &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot; eller &quot;application/x-msword&quot;. I sådana fall kan `$main::search_content_class` anta följande värden:

   * html
   * pdf
   * ord
   * excel
   * powerpoint
   * mp3
   * text

* I exemplet skulle testning av `$main::search_content_class` för &quot;word&quot; matcha något av de tre möjliga innehållstypsvärdena.
* Om inget skrivs ut till STDOUT från filtreringsskriptet används dokumentet exakt som det hämtades. Det innebär att om du inte behöver ändra något i ett dokument behöver du inte kopiera STDIN till STDOUT för det dokumentet.
* Om du vill ta bort all text från ett dokument skriver du ut en giltig STDOUT-fil. Om du till exempel vill ta bort all text helt från ett HTML-dokument gör du följande: `print "<html></html>";`

## Lägga till ett initieringsskript {#task_5A03B8D0C46E4674B7CE88203515803B}

Initieringsskriptet är ett Perl-skript som körs en gång innan något dokument indexeras.

Du använder initieringsskriptet tillsammans med ett filtreringsskript, ett avslutningsskript och ett URL-maskskript.

Se till att du återskapar platsindexet så att resultaten av initieringsskriptet blir synliga för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Lägga till ett initieringsskript**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Initialization Script]** på produktmenyn.
1. (Valfritt) På sidan [!DNL Initialization Script] anger du URL:en för ett dokument på webbplatsen i fältet [!DNL Test URL].

   Klicka på ett testalternativ om du vill se ändringar i den oformaterade HTML-texten.

   Se tabellen med filtreringsalternativ under **Lägga till ett filtreringsskript**.

   Klicka på **[!UICONTROL Test]** för att testa mot filtreringsskript och URL-masker.

   När du klickar på **[!UICONTROL Test]** uppdateras inte initieringsskriptet och sparas.
1. Klistra in skriptet i fältet [!DNL Initialization Script].
1. (Valfritt) Klicka på **[!UICONTROL Check Syntax]** för att utföra en snabb syntaxkontroll av skriptet genom att köra skripten för filtrering, initiering och avslutning.

   **[!UICONTROL Check Syntax]** uppdaterar inte och sparar skriptet.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Initialization Script]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om avslutningsskript {#concept_AAD6B3B0E7124874AD0947096FC42F47}

Du kan använda [!DNL Termination Script] för att ändra innehållet i ett webbdokument innan det indexeras.

Du kan infoga HTML-taggar, ta bort irrelevant innehåll och till och med skapa nya HTML-metadata baserat på dokumentets URL, MIME-typ och befintligt innehåll. Initieringsskriptet är ett Perl-skript som ger kraftfull stränghantering och flexibilitet vid matchning av reguljära uttryck. Du använder avslutningsskriptet med ett initieringsskript, filtreringsskript, avslutningsskript, URL-maskskript och test-URL.

Skriptet för avslutning körs en gång efter att alla dokument har indexerats. Du kan använda avslutningsskriptet för att skriva ut statusmeddelanden från filtreringsskriptet till indexloggen. Du skriver antingen ut meddelandena till STDERR eller via underrutinen `_search_debug_log()`.

Vissa kommandoradsalternativ för GNU diff som du kan använda i **[!UICONTROL Expert (diff)]**-läge på sidan Skript för mellanlagrad avslutning inkluderar följande:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>GNU diff-kommandoradsalternativ </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -b  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar i mängden tomt utrymme. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -B  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar som infogar eller tar bort tomma rader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -c  </span> </p> </td> 
   <td colname="col2"> <p> Använder kontextutdataformatet, som visar tre kontextrader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -C rader  </span> </p> </td> 
   <td colname="col2"> <p> Använder kontextutdataformatet, visar kontextrader (heltal) eller tre om rader inte anges. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -i  </span> </p> </td> 
   <td colname="col2"> <p> Ignorerar ändringar i fallet, motsvarar gemener och versaler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -f  </span> </p> </td> 
   <td colname="col2"> <p> Skapar utdata som ser ut som ett skript med ände men som har ändringar i den ordning de visas i filen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -n  </span> </p> </td> 
   <td colname="col2"> <p> Ger RCS-formatsskillnader, som <span class="codeph"> -f </span> förutom att varje kommando anger antalet rader som påverkas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>-u </p> </td> 
   <td colname="col2"> <p> Använder det enhetliga utdataformatet, som visar tre kontextrader. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> -U rader  </span> </p> </td> 
   <td colname="col2"> <p> Använder det enhetliga utdataformatet, visar rader (ett heltal) i kontexten eller tre om rader inte anges. </p> </td> 
  </tr> 
 </tbody> 
</table>

Du kan använda lokala variabler, globala variabler eller båda i dessa skript. Alla globala variabler förskrivs med namnutrymmet&quot;main::&quot;. När avslutningsskriptet startas innehåller dess miljö följande standardfilreferenser:

* STDIN - ingenting (returnerar omedelbart EOF vid läsning)
* STDOUT - ingenting (om data skrivs ut till STDOUT, ignoreras det)
* STDERR - data som skrivs ut till STDERR skrivs ut till indexloggen som ett fel

Dessutom kan du skriva egna meddelanden i indexloggen med hjälp av underrutinen `_search_debug_log()`, som i följande exempel:

```
# Log information to the Index Log 
_search_debug_log("Done processing document: " . $main::search_url);
```

Dessa meddelanden visas med ordet `DEBUG` som preface och loggas inte som fel.

Om du vill visa antalet dokument som har bearbetats av ditt filtreringsskript som en felrad i indexloggen kan du använda följande avslutningsskript:

```
# Print the value of the document counter. 
print STDERR "Total docs: $main::doc_count\n"; 
# Or, using the log subroutine: 
_search_debug_log("Total docs: " . $main::doc_count);
```

Se [Globala variabler](#global-variables)

### Snabbtips {#section_5790EA7ACAC046CBA01F759F88E2460F}

* Alla globala variabler är förinställda med namnutrymmet&quot;main::&quot;: `$main::doc_count = 0;`
* Alla lokala variabler deklareras med &quot;my&quot;: `my $i = 0;`
* Underrutiner definieras i initieringsskriptet. De behöver inte ett explicit &quot;main:::&quot;-namnutrymme: `sub my_sub {` `...`

   `}`

* Testa `$main::search_content_type` innan du gör ändringar i en fil. Testerna kan hjälpa dig att undvika slarviga ändringar i binära filer, som SWF-filer eller PDF-filer:

   `if ($main::search_content_type =~ /^text\/html/) { ...`

* `$main::search_content_type` är den fullständiga Content-Type-rubriken som levereras av servern. Den kan ibland innehålla en enkel MIME-typ, till exempel&quot;text/html&quot;. Eller så kan den innehålla en MIME-typ följt av annan information, som dokumentets teckenuppsättningskodning, t.ex. &quot;text/html; charset=iso-8859-1&quot;.
* För varje typ av dokument som inte är HTML kan `$main::search_content_type` ha olika värden. Testning av varje värde i skriptet blir krångligt. Vissa Word-dokument har till exempel innehållstypsvärdena &quot;application/msword&quot;, &quot;application/vnd.ms-word&quot; eller &quot;application/x-msword&quot;. I sådana fall kan `$main::search_content_class` anta följande värden:

   * html
   * pdf
   * ord
   * excel
   * powerpoint
   * mp3
   * text

* I exemplet skulle testning av `$main::search_content_class` för &quot;word&quot; matcha något av de tre möjliga innehållstypsvärdena.
* Om inget skrivs ut till STDOUT från filtreringsskriptet används dokumentet exakt som det hämtades. Det innebär att om du inte behöver ändra något i ett dokument behöver du inte kopiera STDIN till STDOUT för det dokumentet.
* Om du vill ta bort all text från ett dokument skriver du ut en giltig STDOUT-fil. Om du till exempel vill ta bort all text helt från ett HTML-dokument gör du följande: `print "<html></html>";`

## Lägger till ett avslutningsskript {#task_F0CFB412871642CFBC88132889C5B6F9}

Skriptet för avslutande är ett Perl-skript som körs en gång efter att alla dokument har indexerats.

Du använder avslutningsskriptet tillsammans med ett filterskript, avslutningsskript och URL-maskskript.

Se till att du återskapar platsindexet så att resultaten av initieringsskriptet blir synliga för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Lägga till ett avslutningsskript**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Termination Script]** på produktmenyn.
1. (Valfritt) På sidan [!DNL Termination Script] anger du URL:en för ett dokument på webbplatsen i fältet [!DNL Test URL].

   Klicka på ett testalternativ om du vill se ändringar i den oformaterade HTML-texten.

   Se tabellen med filtreringsalternativ under **Lägga till ett filtreringsskript**.

   Klicka på **[!UICONTROL Test]** för att testa mot filtreringsskript och URL-masker.

   Om du klickar på **[!UICONTROL Test]** uppdateras inte och ditt avslutningsskript sparas.
1. Klistra in skriptet i fältet [!DNL Termination Script].
1. (Valfritt) Klicka på **[!UICONTROL Check Syntax]** om du vill utföra en snabb syntaxkontroll av skriptet genom att köra initierings-, filtrerings- och avslutningsskripten.

   **[!UICONTROL Check Syntax]** uppdaterar inte och sparar skriptet.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Termination Script]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om URL Masks-skript {#concept_384F32EA18F84853A7BA99A04009330B}

Med filtrering kan du ändra innehållet i ett webbdokument innan det indexeras. Du kan infoga HTML-taggar, ta bort irrelevant innehåll och till och med skapa nya HTML-metadata baserat på dokumentets URL, MIME-typ och befintligt innehåll. Skriptet för URL-masker är ett Perl-skript som ger kraftfull stränghantering och flexibilitet vid matchning av reguljära uttryck.

Om du vill ändra innehållet i dokument som bara finns på en viss del av webbplatsen kan du ange att URL-masker ska inkluderas, att URL-masker ska exkluderas eller båda, för att definiera lämpliga sidor.

Om du bara vill ändra dokumenten under `"https://www.mysite.com/faqs/"` kan du använda följande maskuppsättning:

```
include https://www.mysite.com/faqs/ 
exclude *
```

Du kan också använda reguljära uttryck i ett URL-maskskript som i följande exempel:

```
include regexp ^https://www\.mysite\.com.*/faqs/.*$ 
exclude *
```

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Skriptade URL-masker beaktas i den ordning som du angav dem i fältet [!DNL URL Masks]. När en dokument-URL matchar en mask inkluderas eller exkluderas det dokumentet baserat på masktypen. Om ett dokuments URL inte matchar någon URL-mask inkluderas dokumentet bara om dess MIME-typ är &quot;text/html&quot;. Alla andra MIME-typer exkluderas.

## Lägga till ett URL-maskskript {#task_D18F2A496C1C45C997B5DA650AAF5D59}

Ange URL-adresser som innehåller masker och exkluderingsmasker för att ändra innehållet i dokument som bara finns på en viss del av webbplatsen.

Innan effekten av inställningarna för URL-masker är synlig för besökarna, ska du återskapa platsindexet.

**Lägga till ett URL-maskskript**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL URL Masks]** på produktmenyn.
1. (Valfritt) På sidan [!DNL URL Masks] anger du en URL för ett dokument på webbplatsen i fältet [!DNL Test URL] och klickar sedan på **[!UICONTROL Test]** för att testa URL:en mot filtreringsskript och masker.

   Test URL-dokumentet laddas ned, som används som STDIN-indata till filtreringsskriptet. Filtrerings-, initierings- och avslutningsskripten körs sedan. Om det finns STDOUT-utdata från filtreringsskriptet visas utdata i ett nytt webbläsarfönster.

   Skriptet uppdateras inte när du klickar på **[!UICONTROL Test]**.
1. I fältet [!DNL URL Masks] anger du en URL-mask per rad.
1. (Valfritt) Klicka på **[!UICONTROL Check Syntax]** för att utföra en snabb syntaxkontroll av dina URL-masker genom att köra skripten för filtrering, initiering och avslutning.

   **[!UICONTROL Check Syntax]** uppdaterar inte och sparar skriptet.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL URL Masks]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om innehållstyper i filtrering {#concept_E3EFF4A148EA4D21AFD0A5453A00427E}

Här kan du välja vilka innehållstyper som du vill filtrera för det här kontot.

Texten som hittas i de valda innehållstyperna konverteras till HTML och bearbetas sedan med skriptet som anges i Filtreringsskript.

Se [Om att filtrera skript](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

De innehållstyper du kan välja bland är bland annat följande:

* PDF-dokument
* Textdokument
* Adobe Flash filmer
* Microsoft Word-filer
* Microsoft Office-filer (OpenXML)
* Microsoft Excel-filer
* Microsoft PowerPoint-filer
* Text i MP3-musikfiler

Innan effekterna av inställningarna för innehållstyper eller ändringar av inställningarna är synliga för kunderna måste du återskapa platsindexet.

## Markera de innehållstyper som har filtrerats {#task_C46081FA425A43EC8FDE6EA4A52A170A}

Markera de innehållstyper som du vill skicka till skriptet som anges i Filtrera skript.

Se [Om att filtrera skript](../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47).

**Välj de innehållstyper som har filtrerats**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Filtering]** > **[!UICONTROL Content Types]** på produktmenyn.
1. På sidan [!DNL Content Types] kontrollerar du de innehållstyper som du vill skicka till filterskriptet.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Content Types]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
