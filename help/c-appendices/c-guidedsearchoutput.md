---
description: Lär dig hur du anpassar utdata i alla textbaserade format, inklusive XML och JSON.
solution: Target
title: Guidade sökresultat
topic: bilagor,Webbplatssökning och -försäljning
uuid: 234fd563-f249-42b0-88ca-c89b44f8df77
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '6289'
ht-degree: 0%

---


# Utdata från guidad sökning{#guided-search-output}

Du kan anpassa utdata i alla textbaserade format, inklusive XML och JSON.

## Använda utdata från guidad sökning {#concept_2A1BA3AD413848A1AC2A3ABC4FFE481F}

Utdataformatet är anpassbart för att stödja fasettering, sortering och andra implementeringsspecifika beslut som fattas under designprocessen. Ni kan anpassa själva formatet för att vid behov förenkla utvecklingen av kundens gränssnitt.

Hela utdata finns i `<result>`-taggar, och de flesta dynamiska data finns i `<![CDATA[ ]]>`-taggar. Sådan organisation tillåter att resultaten innehåller HTML och andra icke-XML-enheter.

Där det finns länkar till andra sidor visas de i form av en relativ URL-adress. Resultatet innehåller också frågesträngsparametrar som skickas för att generera det önskade resultatet.

## Om en guidad sökimplementering {#section_95483980930C4325BAB50A40BD47245A}

När du påbörjar en implementering av en guidad sökning måste du komma ihåg att [!DNL Adobe Search&Promote] är ansvarig för affärslagret. Det är logiken som omger vilka resultat och aspekter som visas för kunden vid varje givet tillfälle.

När du implementerar webbprogrammets frontdel som tolkar och visar resultatet som HTML, ska du begränsa funktionen så att den bara visas. Det innebär att all logik på serversidan som du använder för att skapa presentationslagret inte avgör vad som ska visas för en kund, såvida det inte är nödvändigt. Affärsreglerna fungerar inte som du förväntar dig om frontendskriptet ändrar sökresultaten.

[!DNL Adobe Search&Promote] behåller användartillståndet för de valda alternativen för sökförfining via URL-parametrarna. Alla `<link>`-noder innehåller de relevanta parametrarna för kundens val. Parametrarna kan vara vägbeskrivningar, sidnumrering, sortering och ansiktsval. I tillämpliga fall returneras `<undolink>`-noder så att kunden kan&quot;hoppa ut&quot; från ett urval. Ansikten och vägbeskrivningar innehåller den här typen av länkar.

## Arbeta med sökservern {#section_8DBEACDECD714E59BDED6315E6041B8D}

Ett REST-liknande API används som du kan interagera med för att utföra sökningar och ta emot resultat. De vanligaste formaten som används för resultaten är XML eller JSON.

Bas-URI är associerad med ett specifikt konto och en staged- eller live-miljö. Du kan begära flera alias för bas-URI:n från din kontohanterare. Ett fiktivt företag som heter Megacorp har till exempel följande två bas-URL:er som är kopplade till deras konto:

* `https://search.megacorp.com `
* `https://stage.megacorp.com`

Den tidigare URI:n utför sökningar mot sitt liveindex och den senare URI:n mot sitt mellanlagrade index.

Sökbegäranden består av bas-URI och en uppsättning CGI-parametrar eller nyckelvärdepar som anger den önskade sökningen för kontot som är associerat med bas-URI:n.

Tre format för CGI-parametrar stöds. Som standard är ditt konto konfigurerat att avgränsa CGI-parametrar med semikolon ( `;`), som i följande exempel:

* `https://search.megacorp.com?q=shoes ;page=2`

Om du vill kan du låta kontohanteraren konfigurera ditt konto så att det använder et-tecken ( `&`) för att separera CGI-parametrarna, som i följande exempel:

* `https://search.megacorp.com?q=shoes &page=2`

Ett tredje format, som kallas SEO-format, stöds också där ett snedstreck ( `/`) används i stället för avgränsaren och likhetstecken för att generera&quot;rena&quot; länkar, som i följande exempel:

* `https://search.megacorp.com/q/shoes/page/2`

Varje gång SEO-formatet används för att skicka en begäran returneras alla utdatalänkar i samma format.

## Sökfrågeparametrar {#section_7ADA5E130E3040C9BE85D0D68EDD3223}

I följande tabell beskrivs standardparametrarna för sökfrågor som du kan använda. Bearbetningsregler och affärsregler kan byggas utifrån användardefinierade frågeparametrar för att implementera anpassad affärslogik som är relevant för ditt företag. Du kan arbeta med konsultteamet för att få dokumentation om de parametrarna.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Sökfrågeparameter </p> </th> 
   <th colname="col2" class="entry"> <p>Exempel </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q= sträng  </span> </p> </td> 
   <td colname="col3"> <p> Anger frågesträngen för sökningen. Den här parametern mappar till <span class="codeph"> sp_q </span>-parametern för backend-sökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> q#  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> q#= sträng  </span> </p> </td> 
   <td colname="col3"> <p>Numrerade <span class="codeph"> q </span>- och <span class="codeph"> x </span>-parametrar ger fasettering eller sökning i ett givet fält. </p> <p>Parametern <span class="codeph"> q </span> definierar den term som du söker efter i ansiktet som motsvarande numrerade <span class="codeph"> x </span>-parameter anger. Om du t.ex. har två ansikten med namnet size och color, kan du ha något av följande: </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color  </span> </p> <p>Den här parametern mappar till <span class="codeph"> sp_q_exact_# </span>-parametrar för backend-sökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> x#  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> x#= sträng  </span> </p> </td> 
   <td colname="col3"> <p> Numrerade <span class="codeph"> q </span>- och <span class="codeph"> x </span>-parametrar ger fasettering eller sökning i ett givet fält. </p> <p>Parametern <span class="codeph"> q </span> definierar den term som du söker efter i ansiktet som motsvarande numrerade <span class="codeph"> x </span>-parameter anger. Om du t.ex. har två ansikten med namnet size och color, kan du ha något av följande: </p> <p> <span class="codeph"> q1=small;x1=size;q2=red;x2=color  </span> </p> <p>Den här parametern mappar till <span class="codeph"> sp_x_# </span>-parametrar för backend-sökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> samling  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> collection= string  </span> </p> </td> 
   <td colname="col3"> <p> Anger den samling som ska användas för sökningen. Den här parametern mappar till <span class="codeph"> sp_k </span>-parametern för backend-sökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> antal  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> count= number  </span> </p> </td> 
   <td colname="col3"> <p> Anger det totala antalet resultat som visas. Standardvärdet definieras i <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Söka </span> &gt; <span class="uicontrol"> Söka </span>. Den här parametern mappar till <span class="codeph"> sp_c </span>-parametern för backend-sökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> page  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> page= number  </span> </p> </td> 
   <td colname="col3"> <p> Anger sidan med resultat som returneras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> rankning  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> rank= field  </span> </p> </td> 
   <td colname="col3"> <p> Anger det rangordningsfält som ska användas för statisk rankning. Fältet måste vara ett fält av typen Rank med relevans större än 0. Den här parametern mappar till parametern <span class="codeph"> sp_sr </span> backend. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> gs_store  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> gs_store= sträng  </span> </p> </td> 
   <td colname="col3"> <p> Anger vilket arkiv som ska sökas igenom. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> sortera  </span> </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> sort= number  </span> </p> </td> 
   <td colname="col3"> <p> Anger sorteringsordningen. "0" är standardvärdet och sorterar efter relevanspoäng, "1" sortera efter datum. -1 sorterar inte. </p> <p>Användare kan ange ett fältnamn för värdet för parametern <span class="codeph"> sp_s </span>. Till exempel sorterar <span class="codeph"> sp_s=title </span> resultaten enligt värdena som finns i titelfältet. När ett fältnamn används för värdet för en <span class="codeph"> sp_s </span>-parameter sorteras resultaten efter det fältet och subsorteras sedan efter relevans. </p> <p>Så här aktiverar du den här funktionen: </p> 
    <ol id="ol_3894F81EA7BF4827A84DE8662111ABEF"> 
     <li id="li_C040C0B88F174A4885E1A8E721FD032A">På produktmenyn klickar du på <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>. </li> 
     <li id="li_2E83C3A46D1B4BF991EABAD9D3E52B7D">Gör något av följande på sidan <span class="wintitle"> Mellanlagrade definitioner </span>: 
      <ul id="ul_8018FEE10E0A4C96A74F84A897080580"> 
       <li id="li_E9A7CE43E2734F4D9522A1283CA111FB">Klicka på <span class="uicontrol"> Lägg till nytt fält </span>. </li> 
       <li id="li_9D2434A321924FBD874569CA9AD2EEF7">Klicka på <span class="uicontrol"> Redigera </span> för ett visst fältnamn. </li> 
      </ul> </li> 
     <li id="li_90D5E3F4AC0A4A6189934A5589F69903">I listrutan <span class="wintitle"> Sortering </span> klickar du antingen på <span class="uicontrol"> Stigande </span> eller <span class="uicontrol"> Fallande </span>. <p>Den här parametern mappar till <span class="codeph"> sp_s </span>-parametern för backend-sökning. </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## Integrera med ditt system {#section_91261B19A44A4E579B3FC9FAB9AD3665}

Nedan följer några rekommendationer för integrering med ditt system.

* Kommunicera med sökservern.

   Du kan kommunicera med [!DNL Adobe Search&Promote]-webbservrarna med http GET-begäranden. Dina servrar genererar dessa förfrågningar eller på klientsidan som gör en Ajax-förfrågan.
* Sparar sökhistoriken.

[!DNL Adobe Search&Promote] är tillståndslös där hela läget överförs i http-begäran.
* Analyserar returnerade resultat.

   Vi rekommenderar att du använder en SAX-baserad XML-tolk för att tolka XML-svaret. Om du genererar en Ajax-begäran kan du konfigurera [!DNL Adobe Search&Promote] så att JSON-svar returneras för dessa begäranden, så att det blir enklare att tolka svaret.

## Guidad sökning - JSON-utdata {#reference_EB8182A564DE4374BB84158F2AABEF74}

Tabeller som beskriver JSON-standardsvarans utdata.

Se även [JSON-utdata för guidad sökning](../c-appendices/c-guidedsearchoutput.md#reference_EB8182A564DE4374BB84158F2AABEF74).

Du kan granska JSON-svar för följande:

* [Banderoller](../c-appendices/c-guidedsearchoutput.md#section_88519CAAD25F4BD49D5E517077745B0E)
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_A7DB0F1DA9ED4CBCAE18395122F3E01E)
* [Fasetter](../c-appendices/c-guidedsearchoutput.md#section_65932C95931743A1BFAF1DF16D7E6D92)
* [Sidhuvud och fråga](../c-appendices/c-guidedsearchoutput.md#section_1D57062259CA46E0B4F598FA4EB37065)
* [Sidnumrering](../c-appendices/c-guidedsearchoutput.md#section_504E7AB570BD49AF9839530DC438EE96)
* [Senaste sökningar](../c-appendices/c-guidedsearchoutput.md#section_525816A0355C48F8970D89B8FC3F1FFF)
* [Resultat](../c-appendices/c-guidedsearchoutput.md#section_41AC56BB0A084BF59379B06C8BEF2157)
* [Sökformulär](../c-appendices/c-guidedsearchoutput.md#section_434DA13EA295474C99FFE9F14801CD0E)
* [Sortera](../c-appendices/c-guidedsearchoutput.md#section_558853CD376F4D71BACF211D53085D55)
* [Förslag](../c-appendices/c-guidedsearchoutput.md#section_6EC104E1DDD94AC799B65E6E61A2FB3C)
* [Zoner](../c-appendices/c-guidedsearchoutput.md#section_AE53A498B440465EAF2286F2AE87D548)

## Banderoller {#section_88519CAAD25F4BD49D5E517077745B0E}

Exempel:

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i banners </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> En enskild bannernod. Du kan ha flera banderollnoder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> Det område på webbsidan där banderollen visas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;content&gt; </span> </p> </td> 
   <td colname="col2"> <p> HTML-innehållet för banderollområdet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_A7DB0F1DA9ED4CBCAE18395122F3E01E}

I följande exempel läggs markeringen till i vägbeskrivningen varje gång kunden drar längre ned genom ansiktena. Varje objekt representeras som en `<breadcrumb-item>`.

Exempel:

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i vägbeskrivningar </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> En relativ länk till sökresultat som visar önskad vy. Om du klickar på en vägbeskrivningslänk visas en vy där alla finjusteringar tas bort. Andra alternativ är också tillgängliga. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundmotsatt text för det synliga objektet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ansikten {#section_65932C95931743A1BFAF1DF16D7E6D92}

Ansikten är förfiningsalternativ som ger kunderna möjlighet att filtrera utifrån resultaten. Ansikten används ofta för kategorisering, prisintervall, färgval och annan attributförfining. Metadata i indexet är vad som driver ansiktsuttryck.

Det är vanligt att dölja eller visa kategoriseringsfacets när kunden rör sig nedåt genom kategoriseringen. Den högsta kategoriseringsnivån (kategori) kallas nivå 1. När en kund klickar på ett alternativ för nivå 1 visas förfiningsalternativen för nivå 2 (underkategori) och alternativen för nivå 1 försvinner. När en kund klickar på ett alternativ för nivå 2 visas förfiningsalternativen för nivå 3 (underkategori) och alternativen för nivå 2 försvinner. Som vi nämnt ovan är dessa alternativ dolda och visas-webbprogrammet påverkas inte av dem.

Varje aspekt finns i `<facet-item>`-taggar. I följande exempel visas en aspekt som gör att kunden kan förfina sökresultaten med&quot;semester&quot;.

Exempel:

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item> 
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i ansikten </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Faktorns kundorienterade titel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Etikett som riktar sig mot kunden för ansiktsalternativet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Relativ länk till resultat som alternativet förfinar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> Antalet resultat i den förfinade resultatmängden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> När ett facet-värde har valts returnerar noden en ångra-länk som gör att kunden kan gå tillbaka från resultatet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header and Query {#section_1D57062259CA46E0B4F598FA4EB37065}

Exempel:

```xml
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

Tillsammans visar dessa taggar ett meddelande som följande: &quot;Visar resultat 1-16 av 621 för &#39;nytt år&#39;.&quot;

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i rubrik och fråga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> Nyckelordsfrågan som skickas med begäran. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Artikelnumret för det första resultatet på den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Artikelnumret för det sista resultatet på den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Det totala antalet resultat som matchar användarfrågan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ett valfritt fält som tillämpas globalt på sökresultaten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sidnumrering {#section_504E7AB570BD49AF9839530DC438EE96}

Exempel:

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i sidnumrering </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> Totalt antal resultatsidor, baserat på antalet resultat delat med antalet resultat per sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till den första sidan i resultatuppsättningen, såvida inte kunden redan visar sidan 1. I så fall är det tomt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till den sista sidan i resultatuppsättningen, såvida inte kunden visar den sista sidan. I så fall är det tomt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till föregående sida i resultatuppsättningen, såvida inte kunden visar sidan 1, i så fall är den tom. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till den sista sidan i resultatuppsättningen, såvida inte kunden visar den sista sidan. I så fall är det tomt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till ett visst sidnummer. Tio intilliggande sidnummer visas. På sidan 1 är det sidorna 1-10. I slutet av resultatmängden (i det här fallet 39) blir det sidorna 30-39. I mitten av resultatuppsättningen, sidan 15, blir det sidorna 11-20. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> Används som ett attribut på den markerade sidan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Senaste sökningar {#section_525816A0355C48F8970D89B8FC3F1FFF}

Senaste sökningar är en cookie-baserad funktion som bara fungerar om du skickar cookie-informationen till servrarna.

Exempel:

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i de senaste sökningarna </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> En enskild nod för senaste sökning. Du kan ha flera noder för senaste sökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> Termen som kunden sökte efter tidigare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Länkar till föregående sökning. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resultat {#section_41AC56BB0A084BF59379B06C8BEF2157}

Resultatuppsättningen är en anpassningsbar del av JSON-svaret. Varje index är unikt i metadatas namngivningsmekanismer. Det finns gemensamma fält som returneras för varje resultat, till exempel rubrik, beskrivning och URL. Alla metadata som är definierade för en sida i indexet kan dock bli tillgängliga för varje resultatnod. Kategorisering, priser, färger och miniatyrbilder är bara några av de alternativ som du kan använda för att få mer övertygande sökresultat.

Resultatformatet anpassas baserat på de metadata som är specifika för implementeringen. Alla data per resultat som ska visas i resultatet, inklusive URL:er för miniatyrbilder, finns här.

Dessutom kan du konfigurera flera resultatzoner på sidan, till exempel&quot;Aktuella resultat&quot; eller separata avsnitten&quot;Produkter&quot; och&quot;Innehåll&quot;. I dessa fall finns det flera resultatzoner i HTML-koden, även om facets bara är kopplade till den primära resultatmängden.

Exempel:

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i resultat </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> Serienumret för resultatet i den här resultatmängden. I det här exemplet, där tio resultat visas per sida, på sidan 2 i resultatet, skulle det första objektet ha indexvärdet 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundens titel för den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> Den här sidans URL. Den används för att skapa en hyperlänk som gör att kunden kan klicka sig igenom resultatet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sökformulär {#section_434DA13EA295474C99FFE9F14801CD0E}

Exempel:

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i sökformulär </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> Valfritt. I JSON anger värdet 1 att ditt konto är länkat till <span class="keyword"> Test&amp;Target </span> och har minst en affärsregel som ingår i ett A:B-test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> Valfritt. När du använder Komplettera automatiskt visas den här noden för att ange att CSS och JavaScript finns på sidan tillsammans med innehållet som finns i formuläret. Dessa fält ändras vanligtvis inte om ingen har ändrat inställningen för automatisk komplettering. I sådana fall ökas fältet xxx_cache_ver så att det cachelagrade innehållet blir ogiltigt i kundens webbläsare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> CSS som är associerad med automatisk komplettering. Vi rekommenderar att du placerar den här taggen högt på sidan för att förbättra sidåtergivningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåll som krävs i din sökning för verktyget Komplettera automatiskt för att ansluta till rätt kontroll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> Anpassat JavaScript som krävs för att slutföra automatiskt. Vi rekommenderar att du placerar den här taggen lågt på sidan för att förbättra sidåtergivningen. JavaScript-koden för YUI krävs också för automatisk komplettering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller alla dolda parametrar (namn och värde) som ska tas med i sökformuläret. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sortera {#section_558853CD376F4D71BACF211D53085D55}

I följande exempel visas data för en sorteringsmeny med tre alternativ. Menyn låter kunden sortera efter relevans, titel eller gradering. Det markerade objektet innehåller attributet &quot;selected=true&quot;. &quot;. Erbjud alltid ett relevant alternativ för att låta en kund återgå till de standardsökresultat som ursprungligen visades.

Exempel:

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar på menyn Sortera </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundmotsatt text för alternativet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Representerar värdet för frågesträngsparametern "sort" för det här alternativet. Den här taggen behövs inte om <span class="codeph"> &lt;link&gt; </span>-värdet används. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> För de alternativ som inte är markerade innehåller parametern <span class="codeph"> &lt;link&gt; </span> den relativa länken som returnerar samma resultatuppsättning, sorterad efter den nya sorteringsparametern. Det här fältet är tomt för det valda sorteringsalternativet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Förslag {#section_6EC104E1DDD94AC799B65E6E61A2FB3C}

Förslag returneras när det bara finns ett fåtal resultat eller inga resultat. Den här noden innehåller termer som ger upphov till slutförda frågor och kan visas på sidan &quot;Inga resultat&quot;. Länken returneras också så att kunden kan hoppa till den nya frågan.

Exempel:

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i förslag </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>En relativ länk som används för att skapa en hyperlänk för att söka efter resultat för förslagstermen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den föreslagna termen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zoner {#section_AE53A498B440465EAF2286F2AE87D548}

Exempel:

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i zoner </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> En enskild zonnod. Du kan ha flera zonnoder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> Zonens namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1 eller 0 för att ange om zonen visas eller inte. Det faktiska zoninnehållet kan vara ett statiskt område på webbsidan eller i sökresultaten, till exempel bästsäljare eller relaterade produkter. </p> </td> 
  </tr> 
 </tbody> 
</table>

## XML-utdata för guidad sökning {#reference_D93E859A277643068B10AE7A61C973EA}

Tabeller som beskriver standard-XML-svar.

Du kan granska XML-svar för följande:

* [Banderoller](../c-appendices/c-guidedsearchoutput.md#section_6A19EC26DD3B494194AAA788151B78B5)
* [Breadcrumb](../c-appendices/c-guidedsearchoutput.md#section_E48A71B0EBDB4EDDA7587009AD865488)
* [Fasetter](../c-appendices/c-guidedsearchoutput.md#section_5CEB1F966C004FFEA3CF675638966E25)
* [Sidhuvud och fråga](../c-appendices/c-guidedsearchoutput.md#section_802835E19BCB48239C6770A1B72DFFF8)
* [Sidnumrering](../c-appendices/c-guidedsearchoutput.md#section_72DB86DDE1284B1EA295CFFBC16A3150)
* [Senaste sökningar](../c-appendices/c-guidedsearchoutput.md#section_BCA2DDD17F264CF6BA11634E1A514E28)
* [Resultat](../c-appendices/c-guidedsearchoutput.md#section_EC496F5CA2634158891455E2F6DF6833)
* [Sökformulär](../c-appendices/c-guidedsearchoutput.md#section_F92D8C3D37174A10A4E26CAFF3F3DF89)
* [Sortera](../c-appendices/c-guidedsearchoutput.md#section_32DC50A103BF491BA3665A5CADCCAADE)
* [Förslag](../c-appendices/c-guidedsearchoutput.md#section_D81BCE46F0AF443695DF9C4BA084B716)
* [Zoner](../c-appendices/c-guidedsearchoutput.md#section_15D8AA585F3246799968BA88EE2C9FC2)

## Banderoller {#section_6A19EC26DD3B494194AAA788151B78B5}

Exempel:

```xml
<banners> 
 <banner> 
  <area><![CDATA[top-left]]></area> 
  <content><![CDATA[<img src="https://www.megacorp.com/discount.gif"/>]]></content> 
 </banner> 
</banners>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i banners </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;banner&gt; </span> </p> </td> 
   <td colname="col2"> <p> En enskild bannernod. Du kan ha flera banderollnoder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;area&gt; </span> </p> </td> 
   <td colname="col2"> <p> Det område på webbsidan där banderollen visas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;content&gt; </span> </p> </td> 
   <td colname="col2"> <p> HTML-innehållet för banderollområdet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_E48A71B0EBDB4EDDA7587009AD865488}

I följande exempel läggs markeringen till i vägbeskrivningen varje gång kunden drar längre ned genom ansiktena. Varje objekt representeras som en `<breadcrumb-item>`.

Exempel:

```xml
 <breadcrumb> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year]]></link> 
   <value><![CDATA[new year]]></value> 
  </breadcrumb-item> 
  <breadcrumb-item> 
   <link><![CDATA[?q=new+year;q1=Articles;x1=content-type]]></link> 
   <value><![CDATA[Articles]]></value> 
  </breadcrumb-item> 
 </breadcrumb> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i vägbeskrivningar </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> En relativ länk till sökresultat som visar önskad vy. Om du klickar på en vägbeskrivningslänk visas en vy där alla finjusteringar tas bort. Andra alternativ är också tillgängliga. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundmotsatt text för det synliga objektet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ansikten {#section_5CEB1F966C004FFEA3CF675638966E25}

Ansikten är förfiningsalternativ som ger kunderna möjlighet att filtrera utifrån resultaten. Ansikten används ofta för kategorisering, prisintervall, färgval och annan attributförfining. Metadata i indexet är vad som driver ansiktsuttryck.

Det är vanligt att dölja eller visa kategoriseringsfacets när kunden rör sig nedåt genom kategoriseringen. Den högsta kategoriseringsnivån (kategori) kallas nivå 1. När en kund klickar på ett alternativ för nivå 1 visas förfiningsalternativen för nivå 2 (underkategori) och alternativen för nivå 1 försvinner. När en kund klickar på ett alternativ för nivå 2 visas förfiningsalternativen för nivå 3 (underkategori) och alternativen för nivå 2 försvinner. Som vi nämnt ovan är dessa alternativ dolda och visas-webbprogrammet påverkas inte av dem.

Varje aspekt finns i `<facet-item>`-taggar. I följande exempel visas en aspekt som gör att kunden kan förfina sökresultaten med&quot;semester&quot;.

Exempel:

```xml
 <facets> 
  <facet-item> 
   <facet-title><![CDATA[Holidays]]></facet-title> 
   <facet-value> 
    <label><![CDATA[New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[11]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Christmas]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Christmas;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Chinese New Year]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Chinese+New+Year;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Thanksgiving]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Thanksgiving;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[4th of July]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=4th+of+July;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Father&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Father's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Hanukkah]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Hanukkah;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Mother&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Mother's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Valentine&#39;s Day]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Valentine's+Day;x1=content-type;x2=holidays]]></link> 
    <count><![CDATA[1]]></count> 
   </facet-value> 
  </facet-item> 
  <facet-item> 
   <facet-title><![CDATA[Seasons]]></facet-title> 
   <facet-value> 
    <label><![CDATA[Winter]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Winter;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[20]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Summer]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Summer;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[7]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Autumn]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Autumn;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[4]]></count> 
   </facet-value> 
   <facet-value> 
    <label><![CDATA[Spring]]></label> 
    <link><![CDATA[?q=new+year;q1=Articles;q2=Spring;x1=content-type;x2=seasons]]></link> 
    <count><![CDATA[2]]></count> 
   </facet-value> 
  </facet-item>  
 </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i ansikten </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Faktorns kundorienterade titel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Etikett som riktar sig mot kunden för ansiktsalternativet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Relativ länk till resultat som alternativet förfinar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;count&gt; </span> </p> </td> 
   <td colname="col2"> <p> Antalet resultat i den förfinade resultatmängden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;undolink&gt; </span> </p> </td> 
   <td colname="col2"> <p> När ett facet-värde har valts returnerar noden en ångra-länk som gör att kunden kan gå tillbaka från resultatet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header and Query {#section_802835E19BCB48239C6770A1B72DFFF8}

Exempel:

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<result> 
 <query> 
  <user-query><![CDATA[new year]]></user-query> 
  <lower-results><![CDATA[1]]></lower-results> 
  <upper-results><![CDATA[16]]></upper-results> 
  <total-results><![CDATA[621]]></total-results> 
 </query> 
```

Tillsammans visar dessa taggar ett meddelande som följande: &quot;Visar resultat 1-16 av 621 för &#39;nytt år&#39;.&quot;

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i sidhuvud och fråga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;user-query&gt; </span> </p> </td> 
   <td colname="col2"> <p> Nyckelordsfrågan som skickas med begäran. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;lower-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Artikelnumret för det första resultatet på den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;upper-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Artikelnumret för det sista resultatet på den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-results&gt; </span> </p> </td> 
   <td colname="col2"> <p> Det totala antalet resultat som matchar användarfrågan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;custom-field&gt; </span> </p> </td> 
   <td colname="col2"> <p> Ett valfritt fält som tillämpas globalt på sökresultaten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sidnumrering {#section_72DB86DDE1284B1EA295CFFBC16A3150}

Exempel:

```xml
<pagination> 
 <total-pages><39></total-pages> 
 <pages> 
   <page position="first"></page> 
   <page position="last">?i=1;page=39;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="previous"></page> 
   <page position="next">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="1" selected="true">?i=1;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="2">?i=1;page=2;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="3">?i=1;page=3;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="4">?i=1;page=4;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="5">?i=1;page=5;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="6">?i=1;page=6;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="7">?i=1;page=7;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="8">?i=1;page=8;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="9">?i=1;page=9;q=new+year;q1=Articles;x1=content-type]]></page> 
   <page position="10">?i=1;page=10;q=new+year;q1=Articles;x1=content-type]]></page> 
 </pages> 
</pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i sidnumrering </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;total-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p> Totalt antal resultatsidor, baserat på antalet resultat delat med antalet resultat per sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="first"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till den första sidan i resultatuppsättningen, såvida inte kunden redan visar sidan 1. I så fall är det tomt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="last"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till den sista sidan i resultatuppsättningen, såvida inte kunden visar den sista sidan. I så fall är det tomt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="previous"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till föregående sida i resultatuppsättningen, såvida inte kunden visar sidan 1, i så fall är den tom. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="next"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till den sista sidan i resultatuppsättningen, såvida inte kunden visar den sista sidan. I så fall är det tomt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;page position="x"&gt;</span> </p> </td> 
   <td colname="col2"> <p> Innehåller en relativ länk till ett visst sidnummer. Tio intilliggande sidnummer visas. På sidan 1 är det sidorna 1-10. I slutet av resultatmängden (i det här fallet 39) blir det sidorna 30-39. I mitten av resultatuppsättningen, sidan 15, blir det sidorna 11-20. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> selected="true"&gt;  </span> </p> </td> 
   <td colname="col2"> <p> Används som ett attribut på den markerade sidan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Senaste sökningar {#section_BCA2DDD17F264CF6BA11634E1A514E28}

Senaste sökningar är en cookie-baserad funktion som bara fungerar om du skickar cookie-informationen till servrarna.

Exempel:

```xml
<recent-searches> 
 <recent-search> 
  <search-term><![CDATA[shoes]]></search-term> 
  <link><![CDATA[?q=shoes]]></link> 
 </recent-search> 
</recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i de senaste sökningarna </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;recent-search&gt; </span> </p> </td> 
   <td colname="col2"> <p> En enskild nod för senaste sökning. Du kan ha flera noder för senaste sökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-term&gt; </span> </p> </td> 
   <td colname="col2"> <p> Termen som kunden sökte efter tidigare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> Länkar till föregående sökning. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resultat {#section_EC496F5CA2634158891455E2F6DF6833}

Resultatuppsättningen är en anpassningsbar del av XML-svaret. Varje index är unikt i metadatas namngivningsmekanismer. Det finns gemensamma fält som returneras för varje resultat, till exempel rubrik, beskrivning och URL. Alla metadata som är definierade för en sida i indexet kan dock bli tillgängliga för varje resultatnod. Kategorisering, priser, färger och miniatyrbilder är bara några av de alternativ som du kan använda för att få mer övertygande sökresultat.

Resultatformatet anpassas baserat på de metadata som är specifika för implementeringen. Alla data per resultat som ska visas i resultatet, inklusive URL:er för miniatyrbilder, finns här.

Dessutom kan du konfigurera flera resultatzoner på sidan, till exempel&quot;Aktuella resultat&quot; eller separata avsnitten&quot;Produkter&quot; och&quot;Innehåll&quot;. I dessa fall finns det flera resultatzoner i HTML-koden, även om facets bara är kopplade till den primära resultatmängden.

Exempel:

```xml
 <results> 
  <result> 
    <index><![CDATA[1]]></index> 
    <result-title><![CDATA[New Year's Eve Slumber Party]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-eve-slumber-party-705199/]]></url> 
    <meta-description><![CDATA[Fun New Year's celebration ideas for your kids]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve-

slumber-party-parties-photo-80-FF1200SLEEPA18.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/new-years-eve- 
slumber-party-parties-photo-160-FF1200SLEEPA18.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Nancy Mades]]></byline> 
    <blurb><![CDATA[Fun New Year's celebration ideas for your kids]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[2]]></index> 
    <result-title><![CDATA[10 Holiday Traditions to Start This Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/10-holiday-traditions-to-start-this-year-704781/]]></url> 
    <meta-description><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <small-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-80-FF1107HOLIA01.jpg]]></small-thumbnail-img> 
    <large-thumbnail-img><![CDATA[https://mysite.com/assets/cms/parties/10-holiday- 
traditions-to-start-this-year-parties-photo-160-FF1107HOLIA01.jpg]]></large-thumbnail-img> 
    <byline><![CDATA[Julie Taylor]]></byline> 
    <blurb><![CDATA[Reader ideas to make Thanksgiving, Christmas, and New Year's even more magical]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[3]]></index> 
    <result-title><![CDATA[A Perfect New Year's Eve]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/a-perfect-new-years-eve-705258/]]></url> 
    <meta-description><![CDATA[You can turn New Year's into a celebration for the whole family.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Teri Keough]]></byline> 
    <blurb><![CDATA[You can turn New Year's into a celebration for the whole family.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[4]]></index> 
    <result-title><![CDATA[New Year's Fun and Games]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/new-years-fun-and-games-705220/]]></url> 
    <meta-description><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Charlotte Meryman]]></byline> 
    <blurb><![CDATA[Craft, game and food ideas for a New Year's celebration with kids.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[5]]></index> 
    <result-title><![CDATA[11 Great Ways to Start the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/11-great-ways-to-start-the-new-year-705552/]]></url> 
    <meta-description><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <byline><![CDATA[Emily Block]]></byline> 
    <blurb><![CDATA[11 New Family Traditions to Start This Year from My Magazine]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[6]]></index> 
    <result-title><![CDATA[Celebrating Chinese New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/parties/celebrating-chinese-new-year-705260/]]></url> 
    <meta-description><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></meta-description> 
    <category><![CDATA[parties]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Crafts, food, and games to help you celebrate Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[7]]></index> 
    <result-title><![CDATA[New Year's Eve, Family Style]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/new-years-eve-family-style-701283/]]></url> 
    <meta-description><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Start a family New Year's Eve tradition by having an evening of kid-focused fun at home]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[8]]></index> 
    <result-title><![CDATA[Chinese New Year Activities]]></result-title> 
    <url><![CDATA[https://mysite.com/crafts/chinese-new-year-activities-710345/]]></url> 
    <meta-description><![CDATA[Activities for celebrating Chinese New Year.]]></meta-description> 
    <category><![CDATA[crafts]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Activities for celebrating Chinese New Year.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[9]]></index> 
    <result-title><![CDATA[More Organized in the New Year]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/more-organized-in-the-new-year-701284/]]></url> 
    <meta-description><![CDATA[Tips for getting your household more organized--and getting the kids to help.]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Tips for getting your household more organized--and getting your kids to help out.]]></blurb> 
  </result>   
  <result> 
    <index><![CDATA[10]]></index> 
    <result-title><![CDATA[Checklists: Year-End Safety Checklist]]></result-title> 
    <url><![CDATA[https://mysite.com/holidays/checklists-year-end-safety-checklist-701352/]]></url> 
    <meta-description><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></meta-description> 
    <category><![CDATA[holidays]]></category> 
    <content-type><![CDATA[Articles]]></content-type> 
    <blurb><![CDATA[Make sure that your home is safe with our year-end safety checklist!]]></blurb> 
  </result>   
 </results> 
</customer-result> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i resultat </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;index&gt; </span> </p> </td> 
   <td colname="col2"> <p> Serienumret för resultatet i den här resultatmängden. I det här exemplet, där tio resultat visas per sida, på sidan 2 i resultatet, skulle det första objektet ha indexvärdet 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result-title&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundens titel för den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;url&gt; </span> </p> </td> 
   <td colname="col2"> <p> Den här sidans URL. Den används för att skapa en hyperlänk som gör att kunden kan klicka sig igenom resultatet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sökformulär {#section_F92D8C3D37174A10A4E26CAFF3F3DF89}

Exempel:

```xml
<search-form> 
 <include-tnt-mbox>1 </included-tnt-mbox> 
 <autocomplete> 
  <css><![CDATA[<!--link rel="stylesheet" type="te 
        xt/css"href="//content.atomz.com/sp000000a8/publish/autoc 
        omplete_styles.css?sp_css_cache_ver=2" /-->]]> 
  </css> 
  <form-content><![CDATA[<div id="autocomplete"></div>]]> 
  </form-content> 
  <js><![CDATA[<script type="text/javascript" 
   src="//content.atomz.com/sp100491de/publish/autoc 
   omplete_data.js?sp_js_cache_ver=3"></script>]]> 
  </js> 
 </autcomplete> 
 <hidden-parameters> 
  <parameter> 
   <name><![CDATA[store]]></name> 
   <value><![CDATA[mens]]></value> 
  </parameter> 
 </hidden-parameters> 
</search-form>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i sökformulär </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;include-tnt-mbox&gt; </span> </p> </td> 
   <td colname="col2"> <p> Valfritt. I XML anger värdet 1 att ditt konto är länkat till <span class="keyword"> Test&amp;Target </span> och har minst en affärsregel som ingår i ett A:B-test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p> Valfritt. När du använder Komplettera automatiskt visas den här noden för att ange att CSS och JavaScript finns på sidan tillsammans med innehållet som finns i formuläret. Dessa fält ändras vanligtvis inte om ingen har ändrat inställningen för automatisk komplettering. I sådana fall ökas fältet xxx_cache_ver så att det cachelagrade innehållet blir ogiltigt i kundens webbläsare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;css&gt; </span> </p> </td> 
   <td colname="col2"> <p> CSS som är associerad med automatisk komplettering. Vi rekommenderar att du placerar den här taggen högt på sidan för att förbättra sidåtergivningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;form-content&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåll som krävs i din sökning för verktyget Komplettera automatiskt för att ansluta till rätt kontroll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;js&gt; </span> </p> </td> 
   <td colname="col2"> <p> Anpassat JavaScript som krävs för att slutföra automatiskt. Vi rekommenderar att du placerar den här taggen lågt på sidan för att förbättra sidåtergivningen. JavaScript-koden för YUI krävs också för automatisk komplettering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;hidden-parameters&gt; </span> </p> </td> 
   <td colname="col2"> <p> Innehåller alla dolda parametrar (namn och värde) som ska tas med i sökformuläret. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sortera {#section_32DC50A103BF491BA3665A5CADCCAADE}

I följande exempel visas data för en sorteringsmeny med tre alternativ. Menyn låter kunden sortera efter relevans, titel eller gradering. Det markerade objektet innehåller attributet &quot;selected=true&quot;. &quot;. Erbjud alltid ett relevant alternativ för att låta en kund återgå till de standardsökresultat som ursprungligen visades.

Exempel:

```xml
 <sort> 
  <sort-item selected="true"> 
   <label><![CDATA[Relevance]]></label> 
   <value><![CDATA[relevance]]></value> 
   <link><![CDATA[]]></link> 
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Title]]></label> 
   <value><![CDATA[title]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=title;x1=content-type]]></link>     
  </sort-item> 
  <sort-item> 
   <label><![CDATA[Rating]]></label> 
   <value><![CDATA[user-rating]]></value> 
   <link><![CDATA[?q=new+year;q1=Articles;sort=user-rating;x1=content-type]]></link>     
  </sort-item> 
 </sort>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar på menyn Sortera </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;label&gt; </span> </p> </td> 
   <td colname="col2"> <p> Kundmotsatt text för alternativet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;value&gt; </span> </p> </td> 
   <td colname="col2"> <p> Representerar värdet för frågesträngsparametern "sort" för det här alternativet. Den här taggen behövs inte om <span class="codeph"> &lt;link&gt; </span>-värdet används. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p> För de alternativ som inte är markerade innehåller parametern <span class="codeph"> &lt;link&gt; </span> den relativa länken som returnerar samma resultatuppsättning, sorterad efter den nya sorteringsparametern. Det här fältet är tomt för det valda sorteringsalternativet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Förslag {#section_D81BCE46F0AF443695DF9C4BA084B716}

Förslag returneras när det bara finns ett fåtal resultat eller inga resultat. Den här noden innehåller termer som ger upphov till slutförda frågor och kan visas på sidan &quot;Inga resultat&quot;. Länken returneras också så att kunden kan hoppa till den nya frågan.

Exempel:

```xml
 <suggestions> 
  <suggestion-item> 
   <link><![CDATA[?q=video]]></link> 
   <word><![CDATA[video]]> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i förslag </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;link&gt; </span> </p> </td> 
   <td colname="col2"> <p>En relativ länk som används för att skapa en hyperlänk för att söka efter resultat för förslagstermen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;word&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den föreslagna termen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zoner {#section_15D8AA585F3246799968BA88EE2C9FC2}

Exempel:

```xml
<zones> 
 <zone> 
  <name><![CDATA[best-sellers]]></name> 
  <display><![CDATA[1]]></display> 
 </zone> 
</zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Taggar i zoner </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;zone&gt; </span> </p> </td> 
   <td colname="col2"> <p> En enskild zonnod. Du kan ha flera zonnoder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;name&gt; </span> </p> </td> 
   <td colname="col2"> <p> Zonens namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;display&gt; </span> </p> </td> 
   <td colname="col2"> <p> 1 eller 0 för att ange om zonen visas eller inte. Det faktiska zoninnehållet kan vara ett statiskt område på webbsidan eller i sökresultaten, till exempel bästsäljare eller relaterade produkter. </p> </td> 
  </tr> 
 </tbody> 
</table>

## XML-utdata för guidad sökning för Adobe Experience Manager {#reference_DBE13C606C3A4BB185DE53F88D0D3048}

Tabeller som beskriver standardutdata för XML-svar för AEM (Adobe Experience Manager).

Se även . [XML-utdata för guidad sökning](../c-appendices/c-guidedsearchoutput.md#reference_D93E859A277643068B10AE7A61C973EA)

Du kan granska XML-svar för följande:

* [Banderoller](../c-appendices/c-guidedsearchoutput.md#section_B16EDC5533FA4494AC9983AA7357CBE3)
* [Breadcrumbs](../c-appendices/c-guidedsearchoutput.md#section_49EA7043FBE44315A79A4E738BE30114)
* [Anpassade fält](../c-appendices/c-guidedsearchoutput.md#section_38DD31AFE5DD4263A63644AFF484E0F4)
* [Fasetter](../c-appendices/c-guidedsearchoutput.md#section_BE98990E3DD748A1BD4E0CA322314B79)
* [Sidhuvud](../c-appendices/c-guidedsearchoutput.md#section_5305B1DC5774439485CA0665DB683F9C)
* [Menyer och sortering](../c-appendices/c-guidedsearchoutput.md#section_A34CBB645DBF4C70A12A5B7E81211295)
* [Sidnumrering](../c-appendices/c-guidedsearchoutput.md#section_E52F81C6A6EB4B8F996157B657EC540F)
* [Fråga](../c-appendices/c-guidedsearchoutput.md#section_3DAA1013F09742869B80F6A361816E6C)
* [Senaste sökningar](../c-appendices/c-guidedsearchoutput.md#section_17F942F6EC07456DABED7A483AC08446)
* [Resultat](../c-appendices/c-guidedsearchoutput.md#section_155A80B8C4F641678DD9C8F257108412)
* [Sökformulär](../c-appendices/c-guidedsearchoutput.md#section_9E4B99D4FEDC49629F6C7E866F3A7493)
* [Förslag](../c-appendices/c-guidedsearchoutput.md#section_2899FACB9AD84F60B3687C1B4EF09E15)
* [Mall](../c-appendices/c-guidedsearchoutput.md#section_1E2BB2F274B04F5491A4CCCC38F507BD)
* [Zoner](../c-appendices/c-guidedsearchoutput.md#section_26C4A947E7B1474A8E37D86D9579B93E)

## Banderoller {#section_B16EDC5533FA4494AC9983AA7357CBE3}

Sökning/försäljning av webbplatser kan hantera en kunds banners och koppla in banners i olika delar på en webbsida.

Exempelbanderoll:

Följande är ett exempel på en banderoll som placeras i området på sidorna &quot;top&quot;.

```xml
   <banners> 
       <banner> 
           <area><![CDATA[top]]></area> 
           <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
       </banner> 
    </banners> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>banners </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p>Innehåller 0-n banderollnoder som anger varje banderollområde och innehållet som är kopplat till det området. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>banner </p> </td> 
   <td colname="col2"> <p>banners </p> </td> 
   <td colname="col3"> <p>En enskild bannernod. Du kan ha flera banderollnoder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>area </p> </td> 
   <td colname="col2"> <p>banner </p> </td> 
   <td colname="col3"> <p>Det område på webbsidan där banderollen visas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>innehåll </p> </td> 
   <td colname="col2"> <p>banner </p> </td> 
   <td colname="col3"> <p>Banderollinnehållet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumbs {#section_49EA7043FBE44315A79A4E738BE30114}

Flera vägbeskrivningar stöds. Du kan definiera vägbeskrivningar och deras motsvarande beteende i **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]**. Du måste också tilldela ett unikt namn för varje vägbeskrivningsfil som du definierar. XML-noden för vägbeskrivningar itererar över alla definierade vägbeskrivningar. Vi rekommenderar att du bara visar en vägbeskrivare i sökresultaten.

I följande exempel läggs markeringen till i vägbeskrivningen varje gång kunden drar längre ned genom ansiktena. Varje objekt representeras som en `<breadcrumb-item>`.

Exempelnod för breadcrumb:

```xml
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;sp_cs=UTF-8;view=xml]]></link> 
   <value><![CDATA[mens]]></value> 
                <label><![CDATA[]]></label> 
      </breadcrumb-item> 
     <breadcrumb-item> 
   <link><![CDATA[?i=1;q=mens;q1=Channel;sp_cs=UTF-8;view=xml;x1=brand]]></link> 
   <value><![CDATA[Channel]]></value> 
                <label><![CDATA[brand]]></label> 
      </breadcrumb-item> 
   </breadcrumb> 
    </breadcrumbs> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>breadcrumbs </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p> Innehåller 0-n breadcrumb-noder som definierar varje breadcrumb. De flesta kunder har bara ett spår. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrumb </p> </td> 
   <td colname="col2"> <p>breadcrumbs </p> </td> 
   <td colname="col3"> <p> Innehåller de underordnade noder som definierar definitionen för ett vägbeskrivningsmönster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>breadcrumb </p> </td> 
   <td colname="col3"> <p> Breadcrumb-namnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>breadcrumb-item </p> </td> 
   <td colname="col2"> <p>Ett enskilt objekt i vägbeskrivningsfilen. Varje objekt anger ett steg i spåret när användaren minskar resultatmängden. </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> En relativ länk till sökresultat som visar önskad vy. Om du klickar på en vägbeskrivningslänk visas en vy där alla finjusteringar tas bort. Det finns även andra alternativ, till exempel ta bort och släppa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Kundmotsatt text för det synliga objektet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>breadcrumb-item </p> </td> 
   <td colname="col3"> <p> Etikettaggen genererar en etikett för ett vägbeskrivningsvärde som anger vilken aspekt som valdes för att generera det vägbeskrivande objektet. Det används bara i ett vägstyrt block. Detta är tomt för frågeterbetssteget. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Anpassade fält {#section_38DD31AFE5DD4263A63644AFF484E0F4}

Anpassade fält är en annan samling variabler med global kontext. Den används vanligtvis för att skicka över variabler för SEO-syften som anges i sökresultatsidans metadata.

Exempel på anpassad fältnod:

```xml
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>anpassade fält </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p> Kan innehålla noder med 0-n underordnade noder som definierar anpassade fält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>anpassat fält </p> </td> 
   <td colname="col2"> <p>anpassade fält </p> </td> 
   <td colname="col3"> <p> Valfritt. Innehåller ett värde för ett angivet anpassat fält som anges av namnattributet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ansikten {#section_BE98990E3DD748A1BD4E0CA322314B79}

Ansikten är förfiningsalternativ som ger kunderna möjlighet att filtrera utifrån resultaten. Ansikten används ofta för kategorisering, prisintervall, färgval och annan attributförfining. Ansikten byggs ovanpå metadata i indexet.

Det är vanligt att dölja eller visa kategoriseringsfacets när kunden rör sig nedåt genom kategoriseringen. Den högsta kategoriseringsnivån (kategori) kallas nivå 1. När en kund klickar på ett alternativ för nivå 1 visas förfiningsalternativen för nivå 2 (underkategori) och alternativen för nivå 1 försvinner. När en kund klickar på ett alternativ för nivå 2 visas förfiningsalternativen för nivå 3 (underunderkategori) och alternativen för nivå 2 försvinner. Som nämnts ovan är dessa alternativ dolda och visade. ditt webbprogram påverkar inte dem.

Varje aspekt finns i `<facet-item>`-taggar. I följande exempel visas en aspekt där kunden kan finjustera sökresultaten med&quot;semester&quot;.

Exempel på facet-block:

```xml
<facets>          
     <facet> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undo-link> 
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;q2=Mens;sp_staged=1;view=xml;x1=brand;x2=leveli]]></link> 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Armora+Jeans;sp_staged=1;view=xml;x1=brand]]></undolink> 
      </facet-value> 
      </facet> 
     <facet> 
         <facet-title><![CDATA[Sub-Category]]></facet-title> 
                <behavior><![CDATA[sticky]]></behavior> 
                <selected>0</selected> 
      <facet-value>           
              <label><![CDATA[Apparel]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans;q3=Apparel;sp_staged=1;view=xml;x1=leveli;x2=brand;x3=levelii]]></link> 
       <count><![CDATA[3]]></count>                         
      </facet-value>   
      </facet>         
     <facet> 
         <facet-title><![CDATA[Brand]]></facet-title> 
                <behavior><![CDATA[multi-select]]></behavior> 
                <selected>1</selected> 
                <undo-link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undo-link> 
      <facet-value>        
              <label><![CDATA[Amoura]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Amoura;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[9]]></count>                         
      </facet-value>   
      <facet-value>         
              <label><![CDATA[Armora]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[12]]></count>                        
      </facet-value>   
      <facet-value> 
          <selected><![CDATA[true]]></selected> 
              <label><![CDATA[Armora Jeans]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Armora+Jeans;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
 
       <count><![CDATA[3]]></count> 
                        <undolink><![CDATA[?i=1;lang=enus;q=*;q1=Mens;sp_staged=1;view=xml;x1=leveli]]></undolink> 
      </facet-value>   
      <facet-value>           
              <label><![CDATA[Art of Grooming]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Art+of+Grooming;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count>                         
      </facet-value>   
      <facet-value>          
              <label><![CDATA[Bear Co.]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Bear+Co.;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[1]]></count> 
      </facet-value> 
      <facet-value>      
              <label><![CDATA[Citizens]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|Citizens;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[4]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[D&amp;B]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|D%26B;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[17]]></count> 
      </facet-value> 
      <facet-value> 
              <label><![CDATA[David Yuri]]></label> 
       <link><![CDATA[?i=1;lang=enus;q=*;q1=Mens;q2=Armora+Jeans|David+Yuri;sp_staged=1;view=xml;x1=leveli;x2=brand]]></link> 
       <count><![CDATA[2]]></count>    
      </facet-value>   
      </facet> 
    </facets> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>facets </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p>Behållarfacets-noden med 0-n underordnade noder som representerar varje aspekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet </p> </td> 
   <td colname="col2"> <p>facets </p> </td> 
   <td colname="col3"> <p> En enda facet-instans. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-title </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Faktorns kundorienterade titel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>beteende </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Faktorns beteende. Exempel: normal, klisterlapp eller flerval. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>markerad </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>1 om begränsningen har ett valt värde som inte är 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ångra länk </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p> Endast tillgänglig när ansiktet har valts. Ångra länk återställer hela aspekten. Om det till exempel är en flervalsaspekt avmarkeras alla valda alternativ för ansiktet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>facet-value </p> </td> 
   <td colname="col2"> <p>facet </p> </td> 
   <td colname="col3"> <p>Innehåller alla enskilda fasettobjekt som tillhör ansiktet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>markerad </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Om det aktuella objektet med aspekten är markerat finns den här noden med värdet "true". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Etikett som riktar sig mot kunden för ansiktsalternativet. Som standard bör detta redan vara av HTML-escape. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p> Relativ länk till resultat som alternativet förfinar ytterligare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>antal </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>Antalet resultat i den förfinade resultatmängden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ångra länk </p> </td> 
   <td colname="col2"> <p>facet-value </p> </td> 
   <td colname="col3"> <p>När ett facet-värde är valt returnerar noden en ångra-länk som gör att kunden kan välja det enskilda facet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Rubrik {#section_5305B1DC5774439485CA0665DB683F9C}

Exempel:

```xml
xml version="1.0" encoding="utf-8" standalone="yes" 
```

## Menyer och sortering {#section_A34CBB645DBF4C70A12A5B7E81211295}

Menyer för sortering av resultat stöds och ändringar av antalet resultat som ska returneras per sida. Den har även stöd för en navigeringsmeny som är användbar om du vill använda &quot;sök som navigering&quot;. Ett konto kan definiera flera menyer av samma typ och använda någon av menyerna för att visa dem.

Exempelmenynod:

I följande exempel visas data för en sorteringsmeny med tre alternativ och en navigeringsmeny. På sorteringsmenyn kan kunden sortera efter relevans, titel eller klassificering. Det markerade objektet innehåller attributet &quot;selected=true&quot;. &quot;. Erbjud alltid ett relevant alternativ för att låta en kund återgå till de standardsökresultat som ursprungligen visades.

```xml
<menus> 
        <menu> 
           <name><![CDATA[sort]]></name>         
             <item selected="true"> 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=mens;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>   
                    <item> 
                        <label><![CDATA[WOMEN'S]]></label> 
          <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[MEN'S]]></label> 
          <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
          <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
          <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
          <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
          <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[GIFTS & HOME]]></label> 
          <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[CHILDREN & TOYS]]></label> 
          <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link> 
                    </item> 
                    <item> 
                        <label><![CDATA[ELECTRONICS]]></label> 
          <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
          <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link> 
                    </item> 
        </menu> 
    </menus> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>menyer </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p>Innehåller 0-n underordnade noder som definierar varje meny. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>meny </p> </td> 
   <td colname="col2"> <p>menyer </p> </td> 
   <td colname="col3"> <p>En instans av en meny (motsvarar en meny som är definierad i <span class="uicontrol"> Design </span> &gt; <span class="uicontrol"> Navigering </span> &gt; <span class="uicontrol"> menyer </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>meny </p> </td> 
   <td colname="col3"> <p>Menyns namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>artikel </p> </td> 
   <td colname="col2"> <p>meny </p> </td> 
   <td colname="col3"> <p>Definierar varje alternativ på menyn. Det valfria attributet som valts är true om det angivna menyalternativet är markerat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>artikel </p> </td> 
   <td colname="col3"> <p>Kundmotsatt text för menyalternativet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>value </p> </td> 
   <td colname="col2"> <p>artikel </p> </td> 
   <td colname="col3"> <p>Representerar värdet för menyalternativet (frågeparametervärdet som menyn är inställd på också). Den här taggen behövs inte om &lt;link&gt;-värdet används. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>artikel </p> </td> 
   <td colname="col3"> <p>För de alternativ som inte är markerade innehåller parametern &lt;link&gt; den relativa länken som returnerar samma resultatuppsättning, men med menyalternativet tillämpat. Det här fältet är tomt för det valda sorteringsalternativet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sidnumrering {#section_E52F81C6A6EB4B8F996157B657EC540F}

Resultatuppsättningar delas över flera sidor. Normalt visas 10-20 resultat på en sida. Efterföljande resultat visas på nästa sida. Med hjälp av XML-sidnumreringen kan du skapa en uppsättning navigeringslänkar så att dina kunder kan bläddra, sida för sida, genom resultatuppsättningarna. Det finns fyra tillgängliga navigeringslänkar: först, sist, nästa och föregående. Med varje typ av länk kan kunderna snabbt gå igenom sidorna för att enkelt kunna granska och förfina det de letar efter.

I följande exempel visas sidnumreringen för en sökning som finns på den första sidan med sidnumreringen konfigurerad att visa länkar till fem sidor.

Exempelsidnumrering:

```xml
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
            <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
        </pages> 
    </pagination> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>sidnumrering </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p> Totalt antal resultatsidor, baserat på antalet resultat delat med antalet resultat per sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>totalt antal sidor </p> </td> 
   <td colname="col2"> <p>sidnumrering </p> </td> 
   <td colname="col3"> <p>Det totala antalet sidor som sökresultaten är spridda över. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sidor </p> </td> 
   <td colname="col2"> <p>sidnumrering </p> </td> 
   <td colname="col3"> <p>Innehåller 0-n sidnoder som definierar varje sida i sidnumreringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>page </p> </td> 
   <td colname="col2"> <p>sidor </p> </td> 
   <td colname="col3"> <p>Det finns fyra specialsidnoder: först, sista, föregående och nästa. Dessa fyra sidor är valfria och visas bara i resultatuppsättningen om de passar. Om du t.ex. befinner dig på sidan 1 finns det ingen "föregående" länk. Alla andra sidor anger en position. Hur många sidor som visas beror på antalet länkar till sidor som är konfigurerat i sidnumreringsgränssnittet. Attributet"selected" anger den sida som kunden för närvarande är på. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Fråga {#section_3DAA1013F09742869B80F6A361816E6C}

Exempelfrågenod:

```xml
    <query> 
        <user-query><![CDATA[mens]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[265]]></total-results> 
    </query> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>fråga </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p> En global nod som ger en översikt över frågan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>användarfråga </p> </td> 
   <td colname="col2"> <p>fråga </p> </td> 
   <td colname="col3"> <p> Nyckelordet som du sökte efter. Om <span class="uicontrol"> du menar </span> automatiskt sökte efter en föreslagen term på grund av att den ursprungliga termen inte gav några resultat, återspeglas det i det nya nyckelordet som du sökte efter (se förslagsnoden för att få det ursprungliga nyckelordet). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>lägre resultat </p> </td> 
   <td colname="col2"> <p>fråga </p> </td> 
   <td colname="col3"> <p> Artikelnumret för det första resultatet på den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>övre resultat </p> </td> 
   <td colname="col2"> <p>fråga </p> </td> 
   <td colname="col3"> <p> Artikelnumret för det sista resultatet på den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total-results </p> </td> 
   <td colname="col2"> <p>fråga </p> </td> 
   <td colname="col3"> <p> Det totala antalet resultat som matchar användarfrågan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Senaste sökningar {#section_17F942F6EC07456DABED7A483AC08446}

Senaste sökningar är en cookie-baserad funktion som bara fungerar om du vidarebefordrar cookie-informationen till webbplatsens sök-/försäljningsservrar.

Exempel på senaste sökningar:

```xml
    <recent-searches> 
        <clear-link><![?q=womens&gscr=clear]]></clear-link> 
        <recent-search> 
            <link><![?q=mens]]></link> 
            <label><![CDATA[mens]]></label> 
        <recent-search> 
    </recent-searches> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>senaste sökningar </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p>Noden finns bara om sökningen innehåller nyligen gjorda sökningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clear-link </p> </td> 
   <td colname="col2"> <p>senaste sökningar </p> </td> 
   <td colname="col3"> <p>Den relativa sökvägen som rensar alla kundens senaste sökningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>senaste sökningen </p> </td> 
   <td colname="col2"> <p>senaste sökningar </p> </td> 
   <td colname="col3"> <p>Definierar senaste sökningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>senaste sökningen </p> </td> 
   <td colname="col3"> <p>Sökvägen till att skapa en länk som utför en sökning som användaren nyligen har utfört. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>label </p> </td> 
   <td colname="col2"> <p>senaste sökningen </p> </td> 
   <td colname="col3"> <p>Kundexempel för den senaste sökningen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resultat {#section_155A80B8C4F641678DD9C8F257108412}

Resultatuppsättningen är en anpassningsbar del av XML-svaret. Varje index är unikt i metadatas namngivningsmekanismer. Det finns gemensamma fält som returneras för varje resultat, till exempel rubrik, beskrivning och URL. Alla metadata som är definierade för en sida i indexet kan dock bli tillgängliga för varje resultatnod. Kategorisering, priser, färger och miniatyrbilder är bara några av de alternativ som du kan använda för att få mer övertygande sökresultat.

Resultatformatet anpassas baserat på de metadata som är specifika för implementeringen. Alla data per resultat som ska visas i resultatet, inklusive URL:er för miniatyrbilder, finns här.

Dessutom kan du konfigurera flera resultatzoner på sidan, till exempel&quot;Aktuella resultat&quot; eller separata avsnitten&quot;Produkter&quot; och&quot;Innehåll&quot;. I dessa fall finns det flera resultatzoner i HTML-koden, även om facets bara är kopplade till den primära resultatmängden.

Exempelresultatnod:

```xml
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
                    <field name="sku"><![CDATA[200190]]></field> 
                    <field name="pagename"><![CDATA[Relaxed Paint Splattered]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>   
         <result> 
                    <field name="index"><![CDATA[2]]></field> 
                    <field name="sku"><![CDATA[200195]]></field> 
                    <field name="pagename"><![CDATA[Tumbled Jeans]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[235]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>    
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
                    <field name="sku"><![CDATA[200196]]></field> 
                    <field name="pagename"><![CDATA[Montana Relaxed]]></field> 
 
                    <field name="img_sm_url"><![CDATA[https://geometrixx.com/images/08_geometrixx_icon_men.jpg]]></field> 
      <field name="brand"><![CDATA[Armora Jeans]]></field> 
      <field name="price"><![CDATA[220]]></field> 
      <field name="foundIn"><![CDATA[Mens,  
            Apparel,  
          Denim]]></field> 
         </result>         
        </result-set>   
    </results> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>resultat </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p>Behållarnoden för resultatuppsättningar 0-n. Nollresultatuppsättningar innebär att du är på en särskild landningssida utan resultat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>result-set </p> </td> 
   <td colname="col2"> <p>resultat </p> </td> 
   <td colname="col3"> <p>En inkommande sökning kan utlösa flera sökningar. Varje resultatuppsättning innehåller resultaten för en specifik namngiven sökning som utfördes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>result-set </p> </td> 
   <td colname="col3"> <p>Namnet på den sökning som resultatuppsättningen tillhör. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>resultat </p> </td> 
   <td colname="col2"> <p>result-set </p> </td> 
   <td colname="col3"> <p>Innehåller alla fält som är associerade med ett enskilt resultat för resultatuppsättningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>fält </p> </td> 
   <td colname="col2"> <p>resultat </p> </td> 
   <td colname="col3"> <p>Attributet name definierar namnet på fältet i indexet som visas. Värdet är det faktiska värdet för det fältet. Vissa resultat kan ha saknade fält som inte är relevanta för det enskilda resultatet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sökformulär {#section_9E4B99D4FEDC49629F6C7E866F3A7493}

Sökformuläret ingår i resultatuppsättningen så att kunderna kan skapa sina sökformulär dynamiskt. Det här steget är valfritt. De flesta kunder har ett fast sökformulär. Men det gör det möjligt för kunderna att avgöra om sökformuläret behöver en Test&amp;Target-mbox, baserat på att de har minst en affärsregel som utför ett A:B-test. På samma sätt kan kunderna automatiskt hämta den senaste automatiska kompletteringen av CSS och JavaScript.

Exempel på XML för sökformulär:

```xml
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>sökformulär </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p>Innehåller data för att köra sökformuläret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>include-tnt-mbox </p> </td> 
   <td colname="col2"> <p> sökformulär </p> </td> 
   <td colname="col3"> <p>Tekniskt sett behöver du bara en mbox i sökformuläret när du har minst en affärsregel som gör ett A:B-test för Test&amp;Target. Den här noden anger om du behöver en mbox eller inte tillåter dig att minska antalet träffar på Test&amp;Target-servrarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>autocomplete </p> </td> 
   <td colname="col2"> <p>sökformulär </p> </td> 
   <td colname="col3"> <p>Placerar underordnade noder som är relaterade till automatisk komplettering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>aktiverad </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>Ange 1 när sökkontot använder Komplettera automatiskt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>css </p> </td> 
   <td colname="col2"> <p> autocomplete </p> </td> 
   <td colname="col3"> <p> CSS för automatisk komplettering. Placera den här noden så högt upp på sidan som möjligt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> form-content </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>Innehåll som matas in i sökformuläret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>javascript </p> </td> 
   <td colname="col2"> <p>autocomplete </p> </td> 
   <td colname="col3"> <p>JavaScript för automatisk komplettering. Placera den här noden så lågt som möjligt på sidan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Förslag {#section_2899FACB9AD84F60B3687C1B4EF09E15}

Kunder kan konfigurera **[!UICONTROL Did You Mean]**-funktionalitet på tre sätt: kan du lägga till förslag på grund av att det inte finns några resultat, automatiskt söka efter det första förslaget när vi inte har några resultat eller ge förslag på grund av låga resultat (där förslagen har ett högre resultatantal). Alla förslag ger resultat.

Den här förslagsnoden innehåller termer som ger lyckade frågor. Länken returneras också så att kunden kan hoppa till den nya frågan.

Exempelutdata för förslag på grund av 0 resultat:

```xml
    <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>0</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=arcade;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[arcade]]></word> 
 </suggestion-item>    
    </suggestions>
```

Exempelutdata för automatisk sökning mot ett förslag:

```xml
    <suggestions> 
        <auto-searched>1</auto-searched> 
        <orig-query><![CDATA[arcace]]></orig-query> 
        <suggestions-low-results>0</suggestions-low-results>         
    </suggestions> 
```

Exempelutdata för förslag på grund av låga resultat:

```xml
   <suggestions> 
        <auto-searched>0</auto-searched> 
        <suggestions-low-results>1</suggestions-low-results> 
 <suggestion-item> 
     <link><![CDATA[?i=1;q=coffee;sp_cs=UTF-8;view=xml]]></link> 
     <word><![CDATA[coffee]]></word> 
 </suggestion-item>  
    </suggestions> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>förslag </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p> Innehåller underordnade noder som definierar förslag, om sådana finns. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>automatisk sökning </p> </td> 
   <td colname="col2"> <p>förslag </p> </td> 
   <td colname="col3"> <p> Anger om webbplatssökning/försäljning automatiskt har sökts mot en ny term på grund av att inga resultat har hittats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>orig-query </p> </td> 
   <td colname="col2"> <p>förslag </p> </td> 
   <td colname="col3"> <p> När webbplatssökning/försäljning automatiskt söker efter det första förslaget, visar användarfrågan i frågenoden nyckelordet som söks mot. Den här noden visar den ursprungliga frågetermen. Genom att kombinera de två kan kunderna skapa strukturer som"Söka efter arcade istället för arcade". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>exempel-få-resultat </p> </td> 
   <td colname="col2"> <p>förslag </p> </td> 
   <td colname="col3"> <p>Anger om webbplatssökning/försäljning ger förslag på grund av den aktuella söktermen, vilket ger låga resultat och ett förslag som ger betydligt högre resultat. De två tröskelvärdena kan konfigureras i <span class="uicontrol"> Menade du </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>förslag-objekt </p> </td> 
   <td colname="col2"> <p>förslag </p> </td> 
   <td colname="col3"> <p>Innehåller 0-n-noder som betecknar de olika förslagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>link </p> </td> 
   <td colname="col2"> <p>förslag-objekt </p> </td> 
   <td colname="col3"> <p>Innehåller sökvägen för att skapa en länk till den föreslagna termen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ord </p> </td> 
   <td colname="col2"> <p>förslag-objekt </p> </td> 
   <td colname="col3"> <p> Innehåller det föreslagna ordet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mall {#section_1E2BB2F274B04F5491A4CCCC38F507BD}

Det finns stöd för möjligheten att byta ut en kunds sökupplevelse baserat på resultatet. En del av detta är att växla mellan olika mallar med olika layout för sökresultaten. Du kan till exempel ha en mall med en stödrastervy över produkter när du har många produkter. Du kan också ha en spotlight-mall när du visar ett resultat som innehåller mer information. Du kan också ha en mall utan resultat när en sökning inte ger några resultat. Mallnoden anger vilken mall som används för att visa sökresultaten.

Exempelmall:

```xml
<template><![CDATA[grid]]></template>
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>mall </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p>Anger namnet på mallen som används för att visa sökresultaten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zoner {#section_26C4A947E7B1474A8E37D86D9579B93E}

Zoner är avsnitt på sidorna som kan aktiveras och inaktiveras av affärsregler. En zon kan innehålla allt innehåll, inklusive, men inte begränsat till, ansikten, sökningar, vägbeskrivningar och statiskt innehåll. Zonerna på kundens webbsida ska mappas till samma områden som webbplatssökning/försäljning.

Exempel på zonnoder:

```xml
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nod </p> </th> 
   <th colname="col2" class="entry"> <p>Överordnad nod </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>zoner </p> </td> 
   <td colname="col2"> <p>kundresultat </p> </td> 
   <td colname="col3"> <p>Innehåller 0-n zoner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>zon </p> </td> 
   <td colname="col2"> <p>zoner </p> </td> 
   <td colname="col3"> <p> En enskild zonnod. Du kan ha flera zonnoder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>name </p> </td> 
   <td colname="col2"> <p>zon </p> </td> 
   <td colname="col3"> <p>Zonens namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visa </p> </td> 
   <td colname="col2"> <p>1 eller 0, vilket anger om zonen som motsvarar zonnamnet visas eller döljs. </p> </td> 
   <td colname="col3"> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel {#reference_64B7D8D228AF4B8D90EDF4DE507B0F84}

Exempelutdata för en *-sökning på en fiktiv webbplats som kallas Geometrixx och en exempelpresentationsmall som används för att skapa exempelutdata.

* [Exempelutdata](../c-appendices/c-guidedsearchoutput.md#section_515C000A18B847D59097D0A9CCC02636)
* [Exempel på presentationsmall](../c-appendices/c-guidedsearchoutput.md#section_AD42571DFB88491AA7F0FDF0929EBE97)

## Exempelutdata {#section_515C000A18B847D59097D0A9CCC02636}

Exempelutdata för en *-sökning på en fiktiv webbplats som kallas Geometrixx.

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[*]]></user-query> 
 <lower-results><![CDATA[1]]></lower-results> 
 <upper-results><![CDATA[12]]></upper-results> 
 <total-results><![CDATA[1337]]></total-results> 
    </query> 
 
    <custom-fields> 
 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name>

             <item selected="true"> 
 
          <label><![CDATA[Relevance]]></label> 
          <value><![CDATA[relevance]]></value> 
          <link><![CDATA[ ]]></link> 
             </item>

             <item> 
          <label><![CDATA[Lowest Price]]></label> 
          <value><![CDATA[Price]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Highest Price]]></label> 
          <value><![CDATA[Price_r]]></value> 
          <link><![CDATA[?i=1;q=*;sort=Price_r;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

             <item> 
          <label><![CDATA[Brand]]></label> 
          <value><![CDATA[brand]]></value> 
          <link><![CDATA[?i=1;q=*;sort=brand;sp_cs=UTF-8;sp_staged=1;view=xml]]></link>     
             </item>

        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name>

                    <label><![CDATA[WOMEN'S]]></label> 
      <value><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Womens;sp_sfvl_field=levelii|leveli|brand|leveliii;x=0;x1=leveli;y=0;view=nav;top=1;i=1;m_ss_head_nav=WOMEN'S]]></link>

                    <label><![CDATA[MEN'S]]></label> 
      <value><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></value> 
      <link><![CDATA[/q1/Mens/x1/leveli/view/nav/top/1/]]></link>

                    <label><![CDATA[JEWELRY & ACCESSORIES]]></label> 
      <value><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1]]></value> 
      <link><![CDATA[?q1=Jewelry+%26+Accessories&sp_sfvl_field=levelii|leveli|brand|leveliii&x1=leveli&view=nav&top=1;i=1;m_ss_head_nav=JEWELRY+%26+ACCESSORIES]]></link>

                    <label><![CDATA[BEAUTY & FRAGRANCE]]></label> 
      <value><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Beauty+%26+Fragrance;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=BEAUTY+%26+FRAGRANCE]]></link>

                    <label><![CDATA[GIFTS & HOME]]></label> 
      <value><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Gifts+%26+Home;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=GIFTS+%26+HOME]]></link>

                    <label><![CDATA[CHILDREN & TOYS]]></label> 
      <value><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Children+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=CHILDREN+%26+TOYS]]></link>

                    <label><![CDATA[ELECTRONICS]]></label> 
      <value><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1]]></value> 
      <link><![CDATA[?q1=Electronics+%26+Toys;sp_sfvl_field=levelii|leveli|brand|leveliii;x1=leveli;view=nav;top=1;i=1;m_ss_head_nav=ELECTRONICS]]></link>

        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
       
  <breadcrumb-item> 
    <link><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></link> 
    <value><![CDATA[*]]></value> 
                        <label><![CDATA[]]></label> 
   </breadcrumb-item> 
          
   </breadcrumb> 
 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched>0</auto-searched> 
         
        <suggestions-low-results>0</suggestions-low-results> 
         
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[112]]></total-pages> 
 
        <pages> 
     <page position="first"><![CDATA[]]></page> 
     <page position="last"><![CDATA[?i=1;page=112;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page> 
      
     <page position="next"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="1" selected="true"><![CDATA[?i=1;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="2"><![CDATA[?i=1;page=2;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="3"><![CDATA[?i=1;page=3;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="4"><![CDATA[?i=1;page=4;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

                <page position="5"><![CDATA[?i=1;page=5;q=*;sp_cs=UTF-8;sp_staged=1;view=xml]]></page>

        </pages> 
    </pagination> 
 
    <facets>  
         
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected>0</selected>

      <facet-value> 
           
              <label><![CDATA[Womens]]></label> 
 
       <link><![CDATA[?i=1;q=*;q1=Womens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[219]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Mens]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Mens;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[202]]></count> 
                         
      </facet-value> 
   
      <facet-value>

              <label><![CDATA[Beauty &amp; Fragrance]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Beauty+%26+Fragrance;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[169]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Children &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Children+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[209]]></count> 
                         
      </facet-value>

      <facet-value> 
           
              <label><![CDATA[Electronics &amp; Toys]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Electronics+%26+Toys;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[200]]></count> 
                         
      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Gifts &amp; Home]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Gifts+%26+Home;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[156]]></count>

      </facet-value> 
   
      <facet-value> 
           
              <label><![CDATA[Jewelry &amp; Accessories]]></label> 
       <link><![CDATA[?i=1;q=*;q1=Jewelry+%26+Accessories;sp_cs=UTF-8;sp_staged=1;view=xml;x1=leveli]]></link> 
       <count><![CDATA[182]]></count> 
                         
      </facet-value> 
   
      </facet-item> 
  
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
               
         <result> 
                    <field name="index"><![CDATA[1]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[2]]></field> 
      <field name="brand"><![CDATA[One For All]]></field> 
      <field name="price"><![CDATA[145]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[3]]></field> 
      <field name="brand"><![CDATA[Citizens]]></field> 
      <field name="price"><![CDATA[208]]></field> 
 
      <field name="foundIn"><![CDATA[Womens,  
            Apparel,  
          Denim]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[4]]></field> 
      <field name="brand"><![CDATA[Vera Watson]]></field> 
      <field name="price"><![CDATA[850]]></field> 
      <field name="foundIn"><![CDATA[Womens,  
            Dresses,  
          Day]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[5]]></field> 
 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[195]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[6]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[80]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[7]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[85]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[8]]></field> 
      <field name="brand"><![CDATA[Woolberry]]></field> 
 
      <field name="price"><![CDATA[280]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[9]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[149]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
 
                    <field name="index"><![CDATA[10]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[55]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[11]]></field> 
      <field name="brand"><![CDATA[Petrol]]></field> 
      <field name="price"><![CDATA[45]]></field> 
 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
        
         <result> 
                    <field name="index"><![CDATA[12]]></field> 
      <field name="brand"><![CDATA[Ray Laredo]]></field> 
      <field name="price"><![CDATA[47]]></field> 
      <field name="foundIn"><![CDATA[Children &amp; Toys,  
            Apparel,  
          Boys Toddler (2T-4T)]]></field> 
         </result>   
      
        </result-set>   
    </results>

    <banners> 
         
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<div style="color:#70A100">We have custom shipping</div>]]></content> 
            </banner>

    </banners> 
 
    <zones> 
        <zone> 
 
            <name><![CDATA[brand-facet]]></name> 
            <display>1</display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox>1</include-tnt-mbox> 
        <autocomplete> 
 
            <enabled>1</enabled> 
            <css><![CDATA[<link rel="stylesheet" type="text/css" href="https://content.t1.atomz.com/sp10043554/stage/autocomplete_styles.css?sp_js_param=2" /> 
]]></css> 
            <form-content><![CDATA[<div id="autocomplete"></div> 
<input type="hidden" name="sp_staged" id="sp_staged" value="1" /> 
]]></form-content> 
            <javascript><![CDATA[<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/utilities/utilities.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/datasource/datasource-min.js"></script> 
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/yui/2.6.0/build/autocomplete/autocomplete-min.js"></script> 
<script type="text/javascript" src="https://content.t1.atomz.com/sp10043554/stage/autocomplete_data.js?sp_js_param=3"></script>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

## Exempel på presentationsmall {#section_AD42571DFB88491AA7F0FDF0929EBE97}

Följande är ett exempel på en presentationsmall som används för att skapa exempelutdata ovan.

```xml
<?xml version="1.0" encoding="utf-8" standalone="yes" ?> 
<customer-results> 
    <query> 
        <user-query><![CDATA[<guided-query-param gsname="q" />]]></user-query> 
 <lower-results><![CDATA[<guided-results-lower>]]></lower-results> 
 <upper-results><![CDATA[<guided-results-upper>]]></upper-results> 
 <total-results><![CDATA[<guided-results-total>]]></total-results> 
    </query> 
 
    <custom-fields> 
        <custom-field name="seo-search-title"><![CDATA[Geometrixx Search Results]]></custom-field> 
        <custom-field name="seo-search-keywords"><![CDATA[<guided-general-field gsname="default" field="seo_search_keywords"/>]]></custom-field> 
    </custom-fields> 
 
    <menus> 
 
        <menu> 
           <name>sort</name> 
     <guided-menu gsname="sort"> 
         <guided-if-menu-item-selected> 
             <item selected="true"> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[ ]]></link> 
             </item> 
        <guided-else-menu-item-selected> 
             <item> 
          <label><![CDATA[<guided-menu-item-label />]]></label> 
          <value><![CDATA[<guided-menu-item-value />]]></value> 
          <link><![CDATA[<guided-menu-item-path />]]></link>     
             </item> 
        </guided-if-menu-item-selected> 
    </guided-menu> 
        </menu> 
        <menu> 
            <name><![CDATA[ss_head_nav]]></name> 
            <guided-menu gsname="ss_head_nav"> 
                <guided-if-menu-item-selected> 
                    <item selected="true"> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                <guided-else-menu-item-selected> 
                    <label><![CDATA[<guided-menu-item-label />]]></label> 
      <value><![CDATA[<guided-menu-item-value />]]></value> 
      <link><![CDATA[<guided-menu-item-path />]]></link> 
                </guided-if-menu-item-selected> 
            </guided-menu>  
        </menu> 
    </menus> 
 
    <breadcrumbs> 
  <breadcrumb> 
            <name><![CDATA[default]]></name> 
      <guided-breadcrumb gsname="default"> 
  <breadcrumb-item> 
    <link><![CDATA[<guided-breadcrumb-path gsname="goto">]]></link> 
    <value><![CDATA[<guided-breadcrumb-value />]]></value> 
                        <label><![CDATA[<guided-breadcrumb-label>]]></label> 
   </breadcrumb-item> 
         </guided-breadcrumb> 
   </breadcrumb> 
    </breadcrumbs> 
 
    <suggestions> 
        <auto-searched><guided-if-suggestion-autosearch>1<guided-else-suggestion-autosearch>0</guided-if-suggestion-autosearch></auto-searched> 
        <guided-if-suggestion-autosearch><orig-query><![CDATA[<guided-suggestion-original-query/>]]></orig-query></guided-if-suggestion-autosearch> 
        <suggestions-low-results><guided-if-suggestion-low-results>1<guided-else-suggestion-low-results>0</guided-if-suggestion-low-results></suggestions-low-results> 
        <guided-suggestions> 
     <suggestion-item> 
         <link><![CDATA[<guided-suggestion-path />]]></link> 
  <word><![CDATA[<guided-suggestion />]]></word> 
     </suggestion-item> 
 </guided-suggestions> 
    </suggestions> 
 
    <pagination> 
        <total-pages><![CDATA[<guided-page-total />]]></total-pages> 
        <pages> 
     <page position="first"><![CDATA[<guided-page-path gsname="first" />]]></page> 
     <page position="last"><![CDATA[<guided-page-path gsname="last" />]]></page> 
     <guided-if-page-prev><page position="prev"><![CDATA[<guided-page-path gsname="prev" />]]></page></guided-if-page-prev> 
     <guided-if-page-next><page position="next"><![CDATA[<guided-page-path gsname="next" />]]></page></guided-if-page-next> 
     <guided-if-page-viewall><page position="viewall"><![CDATA[<guided-page-path gsname="viewall" />]]></page></guided-if-page-viewall> 
     <guided-if-page-viewpages><page position="viewall"><![CDATA[<guided-page-path gsname="viewpages" />]]></page></guided-if-page-viewpages> 
 
     <guided-pages> 
                <guided-if-page-selected><page position="<guided-page-number />" selected="true"><![CDATA[<guided-page-path />]]></page> 
  <guided-else-page-selected><page position="<guided-page-number />"><![CDATA[<guided-page-path />]]></page> 
  </guided-if-page-selected> 
     </guided-pages> 
        </pages> 
    </pagination> 
 
    <facets>  
        <guided-facet gsname="leveli"> 
     <facet-item> 
         <facet-title><![CDATA[Department]]></facet-title> 
                <selected><guided-if-facet-selected>1<guided-else-facet-selected>0</guided-if-facet-selected></selected> 
                <guided-if-facet-selected><undo-link><![CDATA[<guided-facet-undo-path gsname="leveli">]]></undo-link></guided-if-facet-selected> 
  <guided-facet-values> 
      <facet-value> 
          <guided-if-facet-value-selected><selected><![CDATA[true]]></selected></guided-if-facet-value-selected> 
              <label><![CDATA[<guided-facet-value>]]></label> 
       <link><![CDATA[<guided-facet-value-path />]]></link> 
       <count><![CDATA[<guided-facet-count>]]></count> 
                        <guided-if-facet-value-selected><undolink><![CDATA[<guided-facet-value-undo-path />]]></undolink></guided-if-facet-value-selected> 
      </facet-value> 
  </guided-facet-values> 
      </facet-item> 
 </guided-facet> 
    </facets> 
 
    <results> 
        <result-set> 
            <name><![CDATA[default]]></name> 
            <guided-results gsname="default">   
         <result> 
                    <field name="index"><![CDATA[<guided-result-index />]]></field> 
      <field name="brand"><![CDATA[<guided-result-field gsname="brand" />]]></field> 
      <field name="price"><![CDATA[<guided-result-field gsname="price" />]]></field> 
      <field name="foundIn"><![CDATA[<guided-if-result-field gsname="leveli"><!--tmpl_var name='leveli'-->, </guided-if-result-field> 
            <guided-if-result-field gsname="levelii"><!--tmpl_var name='levelii'-->, </guided-if-result-field> 
          <guided-if-result-field gsname="leveliii"><!--tmpl_var name='leveliii'--></guided-if-result-field>]]></field> 
         </result>   
     </guided-results> 
        </result-set>   
    </results> 
 
    <guided-if-recent-searches> 
    <recent-searches> 
        <clear-link><guided-recent-searches-clear-path/></clear-link> 
        <guided-recent-searches> 
            <recent-search> 
                <link><guided-recent-searches-path></link> 
                <label><guided-recent-searches-value></label> 
            <recent-search> 
        </guided-recent-searches> 
    </recent-searches> 
    </guided-if-recent-searches> 
 
    <banners> 
        <guided-if-banner-set gsname="top"> 
            <banner> 
                <area><![CDATA[top]]></area> 
                <content><![CDATA[<guided-banner gsname="top">]]></content> 
            </banner> 
        </guided-if-banner-set> 
        <guided-if-banner-set gsname="bottom"> 
            <banner> 
                <area><![CDATA[bottom]]></area> 
                <content><![CDATA[<guided-banner gsname="bottom">]]></content> 
            </banner> 
        </guided-if-banner-set> 
    </banners> 
 
    <zones> 
        <zone> 
            <name><![CDATA[brand-facet]]></name> 
            <display><guided-if-zone gsname="brand-facet">1<guided-else-zone>0</guided-if-zone></display> 
        </zone> 
    </zones> 
 
    <search-form> 
        <include-tnt-mbox><guided-if-tnt-business-rules>1<guided-else-tnt-business-rules>0</guided-if-tnt-business-rules></include-tnt-mbox> 
        <autocomplete> 
            <enabled><guided-if-autocomplete>1<guided-else-autocomplete>0</guided-if-autocomplete></enabled> 
            <css><![CDATA[<guided-ac-css/>]]></css> 
            <form-content><![CDATA[<guided-ac-form-content/>]]></form-content> 
            <javascript><![CDATA[<guided-ac-javascript/>]]></javascript> 
        </autocomplete> 
    </search-form> 
 
</customer-results> 
```

