---
description: När webbplatsen ändras kan du köra ett skript eller program som begär att sökroboten ska köra ett index med hjälp av Fjärrstyrning.
solution: Target
title: Om Fjärrkontroll för indexering
topic: Index,Webbplatssökning och -försäljning
uuid: 20e230c6-5c1a-4bf4-bff3-b8236d14ab21
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 0%

---


# Om Fjärrkontroll för indexering{#about-remote-control-for-indexing}

När webbplatsen ändras kan du köra ett skript eller program som begär att sökroboten ska köra ett index med hjälp av Fjärrstyrning.

## Använda fjärrstyrning för indexering {#concept_C79B322190E84106A434E5C6D4A4118F}

Indexeringsbegäran för fjärrstyrning kommer vanligtvis från ett skript eller ett program som finns på servern.

Roboten utför samma indexeringssteg som om den hade startats manuellt från [!DNL Index]-menyn. Om du vill skicka en begäran om fjärrstyrning konfigurerar du de lösenord och svarssträngar som krävs.

## Göra en begäran om fjärrkontroll {#section_42FAB2BAB25A4E24BEA69566C6D1C70F}

Om du vill göra en fjärrkontrollsbegäran använder du följande formatexempel baserat på platsen för ditt datacenter:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datacenterplats </p> </th> 
   <th colname="col2" class="entry"> <p>Exempel </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>London </p> </td> 
   <td colname="col2"> <p> <code> https://center.lon5.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nordamerika </p> </td> 
   <td colname="col2"> <p> <code> https://center.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Singapore </p> </td> 
   <td colname="col2"> <p> <code> https://center.sin2.atomz.com/search/cgiindex.tk? <b>sp_a=sp99999999&amp;sp_password=xxxxxx&amp;sp_operation=op</b> </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

eller

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Sträng och värde </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_a= sp99999999  </span> </p> </td> 
   <td colname="col2"> <p> Ditt kontonummer. </p> <p>Du hittar ditt kontonummer under <span class="uicontrol"> <b>Inställningar</b> </span> &gt; <span class="uicontrol"> <b>Kontoalternativ</b> </span> &gt; <span class="uicontrol"> <b>Kontoinställningar</b> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_lines= N  </span> </p> </td> 
   <td colname="col2"> <p>Här kan du kontrollera status för en crawl som körs. </p> <p> <span class="codeph">  N  </span> är antingen ett positivt heltal eller  <span class="codeph"> alla  </span>. Om det här är ett numeriskt värde inkluderas de sista <span class="codeph"> N </span> raderna i motsvarande indexloggfil i JSON-svaret. </p> <p>Om värdet är <span class="codeph"> alla </span> returneras hela filen. </p> <p>Om värdet är <span class="codeph"> 0 </span> returneras ingen logginformation. Det här värdet är standardvärdet för en fråga om indexstatus som körs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= op  </span> </p> </td> 
   <td colname="col2"> <p>Här kan du ange en av följande indexeringsåtgärder som du vill köra: </p> <p> 
     <ul id="ul_6CA190AC41694BC293FC7C6BABA629FE"> 
      <li id="li_EFC76E31D47E473F9A56B2EBA8A97CA1"> <span class="codeph"> full_index  </span> <p>Sökroboten kör ett fullständigt index för din webbplats. </p> </li> 
      <li id="li_A9ACE21718804A21B3DA7B84AB6729D3"> <span class="codeph"> incremental_index  </span> <p>Sökroboten kör ett inkrementellt index med den konfiguration som anges under <span class="uicontrol"> <b>Index</b> </span> &gt; <span class="uicontrol"> <b>Inkrementellt index</b> </span> &gt; <span class="uicontrol"> <b>Konfiguration</b></span>. </p> </li> 
      <li id="li_722FE409AE454AD48ACE95C4CDC7A00B"> <span class="codeph"> vertical_index  </span> <p>Sökroboten kör en lodrät uppdatering med den konfiguration som anges under <span class="uicontrol"> <b>Index</b> </span> &gt; <span class="uicontrol"> <b>Lodrät uppdatering</b> </span> &gt; <span class="uicontrol"> <b>Konfiguration</b></span>. </p> <p>Se <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Om lodrät uppdatering</a>. </p> </li> 
      <li id="li_A40B513CE17043A4925CE3D4DE0B48A4"> <span class="codeph"> script_index  </span> <p>Sökroboten kör ett inkrementellt index med hjälp av textfilen som anges under <span class="uicontrol"> <b>Index</b> </span> &gt; <span class="uicontrol"> <b>Skriptade index</b> </span> &gt; <span class="uicontrol"> <b>Konfiguration</b></span>. </p> </li> 
      <li id="li_A0BC7F1373B14393997BAB7690FD3EF7"> <span class="codeph"> full_staged_index  </span> <p>Sökroboten kör ett komplett mellanlagrat index för din webbplats. </p> </li> 
      <li id="li_47753E358457443A95B384A278FACA83"> <span class="codeph"> incremental_staged_index  </span> <p>Sökroboten kör ett inkrementellt mellanlagrat index med den konfiguration som anges under <span class="uicontrol"> <b>Index</b> </span> &gt; <span class="uicontrol"> <b>Inkrementellt index</b> </span> &gt; <span class="uicontrol"> <b>Konfiguration</b></span>. </p> </li> 
      <li id="li_C8B5F8F1208E438ABEFDF9129A6B14A3"> <span class="codeph"> vertical_staged_index  </span> <p>Sökroboten kör en lodrät mellanlagrad uppdatering med den konfiguration som anges under <span class="uicontrol"> <b>Index</b> </span> &gt; <span class="uicontrol"> <b>Lodrät uppdatering</b> </span> &gt; <span class="uicontrol"> <b>Konfiguration</b></span>. </p> </li> 
     </ul> </p> <p>Obs!  Om du vill använda vertikala uppdateringar kan du behöva aktivera det på ditt konto av din Adobe-kontorepresentant eller Adobe Support. </p> <p>Se <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Om lodrät uppdatering </a>. </p> <p>Du kan lägga till <span class="codeph"> _saved </span> till något av ovanstående <span class="codeph"> sp_operation </span>-värden om du vill att sökroboten ska försöka använda sparat innehåll. Du kan till exempel ange följande: </p> <p> <code class="syntax html"> sp_operation=full_index_saved </code> </p> <p>eller </p> <p> <code class="syntax html"> sp_operation=full_staged_index_saved </code> </p> <p>Du kan också lägga till <span class="codeph"> _status </span> till något av ovanstående <span class="codeph"> sp_operation </span>-värden för att begära en statusrapport för den aktuella eller senaste åtgärden. Du kan till exempel ange följande: </p> <p> <code class="syntax html"> sp_operation=full_index_status </code> </p> <p>eller </p> <p> <code class="syntax html"> sp_operation=full_staged_index_status </code> </p> <p>och resultaten returneras som ett JSON-objekt. Inkludera <span class="codeph"> sp_lines=N </span> om du vill inkludera N rader i den associerade loggfilen. Om N är negativt inkluderas de sista N-raderna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_operation= push  </span> </p> </td> 
   <td colname="col2"> <p> Används för att fjärröverföra ett mellanlagrat index. </p> <p>Alla försök att lägga till <span class="codeph"> _saved </span> i push-åtgärden ignoreras. </p> <p>När du kör en <span class="codeph"> pushLive </span>-åtgärd returneras textsträngen OK, Prioritet eller Fel till servern. Du anger de här svarssträngarna på <span class="wintitle">-sidan för fjärrstyrning </span>. </p> <p>Se <a href="../c-about-index-menu/c-about-remote-control-for-indexing.md#task_57C296258404448DA7A5ADC9B7232391" format="dita" scope="local"> Konfigurera fjärrstyrning för indexering</a>. </p> <p>Om du skickar live när det inte finns något mellanlagrat index händer ingenting och OK-svarssträngen returneras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sp_password= xxxx  </span> </p> </td> 
   <td colname="col2"> <p>Lösenordet för fjärrkontrollen. </p> </td> 
  </tr> 
 </tbody> 
</table>

Sökningen returnerar data i form av ett korrekt HTTP-svar. Det fullständiga svaret består av en HTTP-status, HTTP-svarshuvuden, en tom rad och svarssträngen.

Anta till exempel att du utför följande fjärrkontrollbegäran:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index
```

Följande är svaret från servern:

```
Status: 200 OK 
Content-type: text/plain 
OK
```

Eller anta att du utför följande fjärrstyrningsstatusbegäran:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status
```

Serverns svar kan se ut så här:

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:58:58-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "status": 1, 
    "message": "ok" 
}
```

Följande fråga används för att hämta de tio första raderna i logglistan som är associerad med den här indexåtgärden, tillsammans med dess status:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=10
```

Serverns svar:

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T10:59:30-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "offset": 672, 
    "lines": [ 
        "07/25 16:40:07 PST   ======== Starting manual crawl of account sp99999999. ========", 
        "07/25 16:40:08 PST   Loading existing data", 
        "07/25 16:40:08 PST   Downloading entrypoint https://www.atomz.com/", 
        "07/25 16:40:08 PST   Robots.txt exclude mask: https://www.atomz.com/snap", 
        "07/25 16:40:08 PST   Exclude mask: regexp ^https://www.atomz.com/$", 
        "07/25 16:40:08 PST   Include mask: https://www.atomz.com/", 
        "07/25 16:40:08 PST   Downloading https://www.atomz.com/style.css", 
        "07/25 16:40:09 PST   Ignoring https://www.atomz.com/style.css, document type 'text/css'.", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/privacy.html", 
        "07/25 16:40:09 PST   Downloading https://www.atomz.com/terms.html" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

Observera `offset`-värdet. Det här värdet identifierar filförskjutningspositionen i loggfilen där läsningen avbröts. Om du vill läsa *nästa* tio rader i filen tar du med `&sp_offset=672` i den begäran som skickas till servern i det här exemplet.

Med `sp_offset` kan du effektivt bläddra genom en loggfil.

Om du vill hämta de *sista* tio raderna i loggen, tillsammans med statusen, anger du antalet som ett negativt tal. Ange till exempel `sp_lines=` med värdet `-10` enligt följande:

```
https://center.atomz.com/search/cgiindex.tk?sp_a=sp99999999&sp_password=my-password&sp_operation=full_index_status&sp_lines=-10
```

Serverns svar:

```
Status: 200 OK 
Content-type: application/json; charset=utf-8 
{ 
    "current_time": "2017-08-27T11:01:14-0700", 
    "start_time": "2017-07-25T16:40:07-0800", 
    "end_time": "2017-07-25T16:40:20-0800", 
    "elapsed_seconds": 13, 
    "elapsed_seconds_fmt": "13s", 
    "state": "finished", 
    "docs_indexed": 3, 
    "depth": 0, 
    "errors": 0, 
    "lines": [ 
        "07/25 16:40:20 PST   End Time: 07/25/2017 16:40:20 PST", 
        "07/25 16:40:20 PST   Elapsed Time: 13 seconds", 
        "07/25 16:40:20 PST   Pages Crawled: 3 pages", 
        "07/25 16:40:20 PST   Pages Indexed: 3 pages", 
        "07/25 16:40:20 PST   Words/Bytes Indexed: 2373 words/ 20618 bytes", 
        "07/25 16:40:20 PST   Errors: 0", 
        "07/25 16:40:20 PST   *** Index Summary ***", 
        "07/25 16:40:20 PST   Total Pages: 3", 
        "07/25 16:40:20 PST   --------------------------------------------------------------------", 
        "07/25 16:40:20 PST   ======== Finish manual crawl of account sp99999999: Done. ========" 
    ], 
    "status": 1, 
    "message": "ok" 
}
```

Observera att inget `offset`-värde returneras här, eftersom den här åtgärden slutfördes i slutet av filen och det inte finns några fler rader att läsa.

## Konfigurerar fjärrstyrning för indexering av {#task_57C296258404448DA7A5ADC9B7232391}

När webbplatsen ändras kan du använda Fjärrstyrning för att köra ett skript eller program från servern och begära att sökroboten kör ett index.

**Konfigurera fjärrstyrning för indexering**

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Remote Control]** på produktmenyn.
1. På sidan [!DNL Remote Control] anger du att varje konfigurationsfältalternativ ska kunna skicka en indexeringsbegäran från servern automatiskt för att indexera webbplatsen.

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
    <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Fjärrstyrningslösenord </p> </td> 
    <td colname="col2"> <p>Ange lösenordet för fjärrkontrollen. </p> <p> Lösenord är skiftlägeskänsliga, minst sex tecken långa och måste innehålla minst en bokstav. Vi rekommenderar att du även tar med minst en siffra. </p> <p>Använd inte ditt lösenord för webbplatssökning/försäljning. </p> <p>Lösenordet används i varje fjärrkontrollsbegäran. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>OK-svarssträng </p> </td> 
    <td colname="col2"> <p>Gör att du kan ange en OK-svarstextsträng om den begärda indexåtgärden börjar fungera. I sådana fall returnerar sökroboten din OK-svarssträng till servern. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Prioritetssvarssträng </p> </td> 
    <td colname="col2"> <p>Om en annan indexeringsåtgärd pågår när fjärrbegäran görs kan sökroboten inte utföra det begärda indexet. I sådana fall returneras textsträngen Priority-svar till servern. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Felsvarssträng </p> </td> 
    <td colname="col2"> <p>Gör att du kan ange en textsträng för felsvar Om lösenordet är felaktigt eller om ett annat fel inträffar. I sådana fall returnerar sökroboten din felsvarssträng till servern. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.
