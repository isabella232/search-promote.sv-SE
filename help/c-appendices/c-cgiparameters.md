---
description: 'null'
seo-description: 'null'
seo-title: CGI-parametrar
solution: Target
title: CGI-parametrar
topic: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# CGI-parametrar{#cgi-parameters}

## CGI-parametrar {#concept_F395999090FE4926B38BC73D5E612800}

## Sök i CGI-parametrar {#reference_DA27A8B0728246DA94994885E1353890}

Du kan kopiera och klistra in formulärkoden i webbplatsens HTML-kod ( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**).

Se [Kopiera HTML-koden för sökformuläret till ...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Du kan också ange parametrarna som visas antingen i själva sökformuläret eller från ett skript. Förutom de parametrar som anges nedan kan du även använda backend-sökparametrarna för att styra sökningen.

Se CGI-parametrar för [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

Sökbegäranden består av en bas-URL. Bas-URL:en anger vilket konto kunden söker och en uppsättning CGI-parametrar (nyckel-värde-par) som anger hur det önskade sökresultatet för det associerade kontot ska returneras.

Bas-URL:en är kopplad till ett specifikt konto och en staged- eller live-miljö. Du kan begära flera alias för bas-URL:en från din kontohanterare. Ett företag med namnet Megacorp kan till exempel ha två bas-URL:er kopplade till sitt konto: `https://search.megacorp.com` och `https://stage.megacorp.com`. Den tidigare URL:en söker i sitt liveindex och den senare URL:en söker i sitt mellanlagrade index.

Tre format för CGI-parametrar stöds. Som standard är ditt konto konfigurerat att avgränsa CGI-parametrar med ett semikolon, som i följande exempel:

`https://search.megacorp.com?q=shoes;page=2`

Om du vill kan du låta kontohanteraren konfigurera ditt konto så att det använder et-tecken för att separera CGI-parametrarna, som i följande exempel:

`https://search.megacorp.com?q=shoes&page=2`

Ett tredje format, som kallas SEO-format, stöds också när ett snedstreck `/` används i stället för avgränsaren och likhetstecken, som i följande exempel:

`https://search.megacorp.com/q/shoes/page/2`

Varje gång SEO-formatet används för att skicka en begäran returneras alla utdatalänkar i samma format.

| Parametern Guidad sökning | Exempel | Beskrivning |
|--- |--- |--- |
| q | `q=string` | Anger frågesträngen för sökningen. Den här parametern mappas till parametern för `sp_q` backend-sökning.  Se CGI-parametrar för [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| q# | `q#=string` | Motsökning (sökning i ett visst fält) görs med hjälp av numrerade q- och x-parametrar.  q-parametern definierar den term som du söker efter i ansiktet enligt den motsvarande numrerade x-parametern.<br>Om du t.ex. har två ansikten med namnet size och color kan du ha något som q1=small;x1=size;q2=red;x2=color.  Den här parametern mappar till `sp_q_exact_#` backend-sökparametrarna.  <br>Se CGI-parametrar för [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| x# | `q#=string` | Motsökning (sökning i ett visst fält) görs med hjälp av numrerade q- och x-parametrar.  q-parametern definierar den term som du söker efter i ansiktet enligt den motsvarande numrerade x-parametern. <br>Om du t.ex. har två ansikten med namnet size och color kan du ha något som q1=small;x1=size;q2=red;x2=color.  Den här parametern mappar till `sp_x_#` backend-sökparametrarna.  <br>Se CGI-parametrar för [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| samling | `collection=string` | Anger den samling som ska användas för sökningen.  Den här parametern mappas till parametern för `sp_k` backend-sökning.  Se CGI-parametrar för [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| antal | `count=number` | Anger det totala antalet resultat som visas.  Standardvärdet definieras i [!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]. .  Den här parametern mappas till parametern för `sp_c` backend-sökning.  Se CGI-parametrar för [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| page | `page=number` | Anger sidan med resultat som returneras. |
| rankning | `rank=field` | Anger det rangordningsfält som ska användas för statisk rankning.  Fältet måste vara ett fält av typen Rank med relevans större än 0.  Den här parametern mappas till parametern `sp_sr` backend.  Se CGI-parametrar för [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| sortera | `sort=number` | Anger sorteringsordningen.<br>&quot;0&quot; är standardvärdet och sorterar efter relevanspoäng, &quot;1&quot; sortera efter datum. -1 sorterar inte.  Användare kan ange ett fältnamn för värdet på `sp_s` parametern.  Du kan t.ex. `sp_s=title` sortera resultaten efter de värden som finns i titelfältet. När ett fältnamn används som värde för en ` sp_s ` parameter sorteras resultaten efter det fältet och sorteras sedan efter relevans.  Om du vill aktivera den här funktionen klickar du på [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. På sidan Definitioner klickar du på [!UICONTROL Add New Field ] eller klickar [!UICONTROL Edit ] för ett specifikt fältnamn. I den [!UICONTROL Sorting ] nedrullningsbara listan väljer du antingen [!UICONTROL Ascending ] eller [!UICONTROL Descending ]. Den här parametern mappas till parametern för `sp_s` backend-sökning. <br>Se CGI-parametrar för [serverdelssökning].(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |

## CGI-parametrar för serversökning {#reference_582E85C3886740C98FE88CA9DF7918E8}

Normalt interagerar kunderna med ett presentationslager som kallas guidad sökning. Det är dock teoretiskt möjligt att hoppa över lagret Guidad sökning och interagera med backend-kärnsökningen direkt med CGI-parametrarna som beskrivs på den här sidan.

Du kan välja CGI-parametrar för serverdelssökning i följande tabell:
<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Stöd för enstaka frågor </p> </th> 
   <th colname="col03" class="entry"> <p>Stöd för flera frågor </p> </th> 
   <th colname="col3" class="entry"> <p>Exempel </p> </th> 
   <th colname="col4" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>sp_a </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_a= sträng </span> </p> </td> 
   <td colname="col4"> <p>Anger kontonummersträngen. Den här parametern är obligatorisk och måste vara en giltig kontonummersträng. Du hittar kontonummersträngen under <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Kontoalternativ </span> &gt; <span class="uicontrol"> Kontoinställningar </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_advanced= 0 eller 1 </span> </p> </td> 
   <td colname="col4"> <p>Om <span class="codeph"> sp_advanced=1 </span> skickas med en fråga används all kod mellan <span class="codeph"> &lt;search-if-advanced&gt;- </span> -taggen och <span class="codeph"> &lt;/search-if-advanced&gt;- </span> -taggen i sökmallen för sökformuläret. All kod mellan <span class="codeph"> &lt;search-if-not-advanced&gt;- </span> taggen och <span class="codeph"> &lt;/search-if-not-advanced&gt;- </span> taggen ignoreras. Om <span class="codeph"> sp_advanced=0 </span> (eller något annat värde) skickas ignoreras mallblocket &lt;search-if-advanced&gt; och mallblocket &lt;search-if-not-advanced&gt; används. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_c= tal </span> </p> </td> 
   <td colname="col4"> <p>Anger det totala antalet resultat som ska visas. Standardvärdet är 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>Samlar in sammanhangsberoende information för det angivna fältet. Den insamlade informationen genereras i sökresultaten med hjälp av malltaggen <span class="codeph"> &lt;search-context&gt; </span> . Standardvärdet är <span class="codeph"> body </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d= type </span> </p> </td> 
   <td colname="col4"> <p>Anger vilken typ av datumintervall som ska utföras. Möjliga värden för typen är any, vilket innebär att ingen sökning efter datumintervall utförs, custom, vilket anger att värdet för <span class="codeph"> sp_date_range </span> ska användas för att bestämma vilka datum som ska sökas och specific, vilket anger att värdena i <span class="codeph"> sp_start_day </span>, <span class="codeph"> sp_start_month </span>, <span class="codeph"> sp_start_year </span>, <span class="codeph"> sp_end_day </span><span class="codeph"> </span><span class="codeph"> </span> ,¥_end_month¥, och String och StruString. p_end_year¥ används för att bestämma vilket datumintervall som ska sökas. <span class="codeph"> sp_d </span> krävs bara om sökformuläret innehåller ett alternativ för att söka antingen efter ett anpassat intervall (med hjälp av <span class="codeph"> sp_date_range </span>) eller efter ett visst start- och slutdatumintervall. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_d_#= typ </span> </p> </td> 
   <td colname="col4"> <p>Anger vilken typ av datumintervall som ska användas för motsvarande <span class="codeph"> sp_q_#- </span> fråga. "#" ersätts med ett tal mellan 1 och 16 (t.ex. <span class="codeph"> sp_d_8 </span>gäller den numrerade frågan <span class="codeph"> sp_q_8 </span>). </p> <p>Du kan ställa in <span class="codeph"> typen </span> till any, vilket innebär att inte utföra sökning i datumintervall, anpassad, vilket anger att värdet för <span class="codeph"> sp_date_range_# </span> används för att bestämma vilka datum som ska sökas, och specifik, vilket anger att värdena i <span class="codeph"> sp_q_min_day_# </span>, <span class="codeph"> sp_q_min_month_# </span>, <span class="codeph"> sp_q_min_year_# </span><span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span> , ✔ sp_q_q_q_max __day_# ,¥ sp_q_max_month_#¥, och¥ sp_q_max_year_# Du bör använda för att bestämma datumintervallet. Användning av <span class="codeph"> sp_d_# </span> krävs bara om sökformuläret innehåller ett alternativ för att söka antingen efter ett anpassat intervall (med hjälp av <span class="codeph"> sp_date_range_# </span>) eller efter ett visst start- och slutdatumintervall. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>7 </p> </td> 
   <td colname="col2"> <p>sp_date_range </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Anger ett fördefinierat datumintervall som ska användas i sökningen. Värden som är större än eller lika med noll anger antalet dagar som ska genomsökas före idag - till exempel anger värdet "0" "idag", värdet "1" anger "idag och igår", värdet "30" anger "inom de senaste 30 dagarna" och så vidare. </p> <p>Värden under noll anger ett anpassat intervall enligt följande: </p> <p>-1 = "Ingen", samma som att ange inget datumintervall. </p> <p>-2 = "Den här veckan", som söker från söndag till lördag den aktuella veckan. </p> <p>-3 = "Sista veckan", som söker från söndag till lördag i veckan före den aktuella veckan. </p> <p>-4 = "Den här månaden", som söker efter datum inom den aktuella månaden. </p> <p>-5 = "Sista månaden", som söker efter datum i månaden före den aktuella månaden. </p> <p>-6 = "Det här året", som söker efter datum under det aktuella året. </p> <p>-7 = "Sista året", som söker efter datum under året före det aktuella året. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>8 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_date_range_# </p> </td> 
   <td colname="col3"> <p> <code> sp_date_range_#= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Anger ett fördefinierat datumintervall som ska användas för motsvarande <span class="codeph"> sp_q_#- </span> fråga. "#" ersätts med ett tal mellan 1 och 16 (t.ex. <span class="codeph"> sp_date_range_8 </span>gäller den numrerade frågan <span class="codeph"> sp_q_8 </span>). </p> <p>Värden större än eller lika med noll anger antalet dagar som ska sökas före idag. Värdet 0 anger till exempel idag; Värdet 1 anger idag och igår. ett värde på 30 anger inom de senaste 30 dagarna o.s.v. </p> <p>Värden under noll anger ett anpassat intervall enligt följande: </p> <p>-1 = "Ingen", samma som att ange inget datumintervall. </p> <p>-2 = "Den här veckan", som söker från söndag till lördag den aktuella veckan. </p> <p>-3 = "Sista veckan", som söker från söndag till lördag i veckan före den aktuella veckan. </p> <p>-4 = "Den här månaden", som söker efter datum inom den aktuella månaden. </p> <p>-5 = "Sista månaden", som söker efter datum i månaden före den aktuella månaden. </p> <p>-6 = "Det här året", som söker efter datum under det aktuella året. </p> <p>-7 = "Sista året", som söker efter datum under året före det aktuella året. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>Anger ett enskilt fält som sökresultaten ska tas bort från. Alla dubblettresultat i det fältet tas bort från sökresultatet. Om t.ex. <span class="codeph"> sp_dedupe_field=title </span>visas endast det översta resultatet för en viss titel i sökresultatet (inga två resultat har identiskt textfältsinnehåll). För typfält med flera värden (Tillåt lista) används hela fältinnehållet för jämförelse. Endast ett fält kan anges. Det är inte tillåtet att ange "table-qualifier" i fältnamnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e= tal </span> </p> </td> 
   <td colname="col4"> <p>Anger att automatisk utökning av jokertecken ska ske för alla ord från frågesträngen med fler än siffror. Med andra ord <span class="codeph"> anger </span> sp_e=5 att ord med 5 eller fler tecken, som "query" eller "number", ska expanderas med jokertecknet "*", vilket gör sökningen ekvivalent med en sökning efter "query*" eller "number*". Ord med färre tecken utökas inte, så om du söker efter ordet utökas inte jokertecknet automatiskt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_e_#= tal </span> </p> </td> 
   <td colname="col4"> <p>Anger att automatisk utökning av jokertecken sker för alla ord från motsvarande <span class="codeph"> sp_q_#- </span> frågesträng med fler än siffror. Med andra ord <span class="codeph"> anger </span> sp_e_2=5 att ord med fem eller fler tecken i <span class="codeph"> sp_q_2- </span> frågesträngen, som "query" eller "number", ska expanderas med jokertecknet " <span class="codeph"> * </span>", vilket gör sökningen ekvivalent med en sökning efter "query*" eller "number*". Ord med färre tecken utökas inte, så om du söker efter ordet i <span class="codeph"> sp_q_2 </span> utökas inte jokertecknet automatiskt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>sp_end_day, sp_end_month, sp_end_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_end_day= <i>number</i>,sp_end_month= <i>number</i>, sp_end_year= <i>number</i> </code> </p> </td> 
   <td colname="col4"> <p>Den här trippeln med värden anger slutdatumintervallet för sökningen och måste anges som en uppsättning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>sp_f </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_f= sträng </span> </p> </td> 
   <td colname="col4"> <p>Anger teckenuppsättningen för frågeparametersträngarna (till exempel <span class="codeph"> sp_q </span>). Strängen måste alltid matcha teckenuppsättningen på sidan som innehåller sökformuläret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>Definierar en logisk datatabell som består av de angivna fälten. En tabell med namnet "items" som består av fälten "color", "size" och "price" skulle definieras så här: </p> <p> <span class="codeph"> sp_field_table=items:color,size,price </span> </p> <p>Logiska tabeller är mest användbara i samband med fält där Tillåt listor är markerat (under <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>). Alla CGI-parametrar och malltaggar som får ett fältnamn som ett värde kan eventuellt ange ett tabellnamn följt av ett "." före fältnamnet (t.ex. <span class="codeph"> sp_x_1=tabellename.fältnamn </span>). </p> <p>Om du till exempel vill söka efter dokument som innehåller ett eller flera "röda" objekt i storleken "large" (där objekten representeras som parallella rader med metadata), kan du använda följande: </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_i= <span class="varname"> värde </span></span> </p> </td> 
   <td colname="col4"> <p>Sökningen ignoreras när du genererar rapporter. </p> <p>Använd den här frågan för att maskera vissa backend-sökningar, t.ex. sökningar som du menar genererar, eller sökningar som en administratör genererar i medlemscentret. Eftersom slutanvändaren inte genererar den här typen av sökningar visas de inte i olika Adobe Search&amp;Promote-rapporter. </p> <p>Giltiga värden är <span class="codeph"> sp_i=1 </span> och <span class="codeph"> sp_i=2 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>16 </p> </td> 
   <td colname="col2"> <p>sp_k </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_k= sträng </span> </p> </td> 
   <td colname="col4"> <p> Anger den samling som ska användas för sökningen. Standardvärdet är ingen samling, vilket innebär att sökningen ska omfatta hela webbplatsen. </p> <p>Se <a href="../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3" type="reference" format="dita" scope="local"> Använda samlingar i sökformulär </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>17 </p> </td> 
   <td colname="col2"> <p>sp_l </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_l= sträng </span> </p> </td> 
   <td colname="col4"> <p>Anger språket för frågeparametersträngarna (till exempel <span class="codeph"> sp_q </span>). Strängen <i> <span class="codeph"> </span></i> ska vara ett standardspråk-ID som innehåller en ISO-639-språkkod som kan följas av en ISO-3166-landskod. Till exempel "en" eller "en_US" för engelska eller "ja" eller "ja_JP" för japanska. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>18 </p> </td> 
   <td colname="col2"> <p>sp_literal </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_literal= 0 eller 1 </span> </p> </td> 
   <td colname="col4"> <p> Om du anger <span class="codeph"> sp_literal=1 inaktiveras </span> tillfälligt alla funktioner som kan tolka orden i frågan. Med den här parametern matchar bara de litterala orden i frågan dokument, oavsett synonymer, alternativa ordformer och ljudliknande matchningar. </p> <p>Observera att <span class="codeph"> sp_literal=0 inte </span> har någon betydelse och ignoreras om det används. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> Om ordlistor </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>19 </p> </td> 
   <td colname="col2"> <p>sp_m </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_m= tal </span> </p> </td> 
   <td colname="col4"> <p> Anger om sammanfattningar visas. 1 är ja, 0 är nej. Standardvärdet är 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>20 </p> </td> 
   <td colname="col2"> <p>sp_n </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_n= tal </span> </p> </td> 
   <td colname="col4"> <p> Anger antalet resultat som startar sökresultaten. Standardvärdet är 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>21 </p> </td> 
   <td colname="col2"> <p>sp_not_found_page </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_not_found_page= url </span> </p> </td> 
   <td colname="col4"> <p> Anger om omdirigering ska ske till den angivna URL:en om det inte finns några sökresultat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>22 </p> </td> 
   <td colname="col2"> <p>sp_p </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p> Anger standardtypen av sökning som ska utföras. Om du använder <span class="codeph"> något </span> innebär det att du söker efter dokument som innehåller valfritt ord från frågesträngen. Om du använder <span class="codeph"> alla </span> innebär det att du söker efter dokument som innehåller alla ord i frågesträngen. Användningen av <span class="codeph"> fras </span> innebär att frågesträngen behandlas som om den vore en fras inom citattecken och alla citattecken som skrivs av användaren ignoreras. </p> <p>För <span class="codeph"> fras </span> och <span class="codeph"> alla </span>är specifikationen för "+" och "-" före sökord inaktiverad och dessa tecken ignoreras. Om <span class="codeph"> sp_p inte </span> finns, eller om det är inställt på en tom sträng eller någon annan, tillåts standardprefix för "+" och "-". </p> <p>Mer information om hur du använder plustecken ("+") och minustecken ("-") i sökningar finns i beskrivningen av söktips. </p> <p>Se <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> Om sökningar </a>. </p> <p>Se exemplet på avancerat sökformulär för exempel på hur du använder <span class="codeph"> parametern sp_p </span> . </p> <p>Se <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Exempel på avancerat sökformulär </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>23 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_p_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_p_#= any/all/phrase </span> </p> </td> 
   <td colname="col4"> <p>Anger standardtypen för sökning som ska utföras med motsvarande <span class="codeph"> sp_q_#- </span> fråga. "#" ersätts med ett tal mellan 1 och 16 ( <span class="codeph"> sp_p_8 </span> gäller t.ex. för den numrerade frågan <span class="codeph"> sp_q_8 </span>). Om du använder <span class="codeph"> någon av dem </span> returneras dokument som innehåller valfritt ord från frågesträngen. Om du använder <span class="codeph"> alla </span> innebär det att returdokument som innehåller alla ord i frågesträngen returneras. Användningen av <span class="codeph"> fras </span> innebär att frågesträngen behandlas som om den vore en fullständig fras (och alla användartypade citattecken ignoreras). </p> <p>Om du anger antingen <span class="codeph"> alla </span> eller <span class="codeph"> fraser </span>ignoreras alla plus- och minustecken före sökorden. Om <span class="codeph"> sp_p_# </span> utelämnas, eller om det är inställt på en tom sträng eller någon annan <span class="codeph"> </span>, tillåts standardprefix "+" och "-". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>24 </p> </td> 
   <td colname="col2"> <p>sp_pt </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_pt= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p> Anger vilken typ av målmatchning som ska användas. Om du använder <span class="codeph"> exact </span> innebär det att målavkastningen endast matchar i dokument som exakt matchar frågesträngen i målinnehållet. Användningen av <span class="codeph"> motsvarigheter </span> är som exakt, förutom att ordens ordning inte är viktig. Om du använder <span class="codeph"> kompatibel </span> ställs målmatchningstypen in automatiskt baserat på värdet för <span class="codeph"> sp_p- </span> parametern. Användning av <span class="codeph"> exact </span> används om <span class="codeph"> sp_p </span> är <span class="codeph"> all </span> eller <span class="codeph"> phrase </span>, annars <span class="codeph"> equivalent </span> används. Standardvärdet för <span class="codeph"> sp_pt </span> är <span class="codeph"> kompatibelt </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>25 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_pt_# </p> </td> 
   <td colname="col3"> <p> <code> sp_pt_#= <i>exact/equivalent/compatible</i> </code> </p> </td> 
   <td colname="col4"> <p>Anger vilken typ av målmatchning som ska användas med motsvarande <span class="codeph"> sp_q_#- </span> fråga. "#" ersätts med ett tal mellan 1 och 16 ( <span class="codeph"> sp_p_8 </span> gäller t.ex. för den numrerade frågan <span class="codeph"> sp_q_8 </span>). Om du använder <span class="codeph"> exact </span> innebär det att målavkastningen endast matchar i dokument som exakt matchar frågesträngen i målinnehållet. Användningen av <span class="codeph"> motsvarigheten </span> är som <span class="codeph"> exakt </span>, förutom att ordens ordning inte är viktig. Användning av <span class="codeph"> kompatibel </span> ställer automatiskt in målmatchningstypen baserat på värdet för motsvarande <span class="codeph"> sp_p_#- </span> parameter: <span class="codeph"> exact </span> används om <span class="codeph"> sp_p_# </span> är all eller phrase, annars <span class="codeph"> används motsvarande </span> värde. Standardvärdet för <span class="codeph"> sp_pt_# </span> är <span class="codeph"> kompatibelt </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>26 </p> </td> 
   <td colname="col2"> <p>sp_q </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q= sträng </span> </p> </td> 
   <td colname="col4"> <p> Anger frågesträngen för sökningen. En tom sträng leder till att inga resultat visas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>27 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_q_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_#= text </span> </p> </td> 
   <td colname="col4"> <p>Med den här parametern kan du skapa flera frågor i sökformulär. Parametern <span class="codeph"> sp_q_# </span> innehåller frågesträngen som ska användas i den angivna numrerade frågan. En sökbegäran kan referera till upp till 16 olika numrerade frågor ( <span class="codeph"> sp_q_1 </span> till <span class="codeph"> sp_q_16 </span>). </p> <p>Om du t.ex. skickar in följande formulär returneras alla dokument som innehåller orden "bra" och "böcker". </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>28 </p> </td> 
   <td colname="col2"> <p>sp_q_day, sp_q_month, sp_q_year </p> </td> 
   <td colname="col03"> <p> sp_q_day_#, sp_q _month_#, sp_q _year_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_day= heltalsvärde </span> </p> <p> <span class="codeph"> sp_q_month= heltalsvärde </span> </p> <p> <span class="codeph"> sp_q_year= heltalsvärde </span> </p> <p> <span class="codeph"> sp_q_day_#= heltalsvärde </span> </p> <p> <span class="codeph"> sp_q_month_#= heltalsvärde </span> </p> <p> <span class="codeph"> sp_q_year_#= heltalsvärde </span> </p> </td> 
   <td colname="col4"> <p>De här parametrarna används för att ange ett exakt datum för en viss fråga. Parametrarna <span class="codeph"> sp_q_day </span>, <span class="codeph"> sp_q_month </span>och <span class="codeph"> sp_q_year </span> gäller för huvudfrågan ( <span class="codeph"> sp_q </span>). </p> <p>Parametern <span class="codeph"> # </span>ersätts med ett tal mellan 1 och 16 (t.ex. <span class="codeph"> sp_q_day_6 </span>som gäller för den numrerade frågan <span class="codeph"> sp_q_6 </span>). Som standard genomsöks alla datum i förhållande till Greenwich Mean Time. </p> <p>I följande kodavsnitt kan användaren söka efter ordet "orange" i dokument som är daterade "Jan. 1st, 2000" i ett användardefinierat fält med namnet <span class="codeph"> PublishDate </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>29 </p> </td> 
   <td colname="col2"> <p>sp_q_location </p> </td> 
   <td colname="col03"> <p>sp_q_location_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> <p> <code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code> </p> </td> 
   <td colname="col4"> <p>De här parametrarna associerar en plats med den huvudsakliga eller numrerade frågan. Användningen av <span class="codeph"> sp_q_location </span> påverkar huvudfrågan, <span class="codeph"> sp_q_location_# </span> (där <span class="codeph"> # </span> ersätts med ett tal mellan 1 och 16), påverkar den numrerade frågan. Parametrarna används för att utföra sökningar efter minsta och/eller största avstånd från platsdata som indexerats för varje webbplatssida. Värdets format avgör dess tolkning. </p> <p>Ett värde i formatet DDD (tre siffror) tolkas som ett amerikanskt telefonnummer. ett värde i formatet DDDDD eller DDDDD-DDDD tolkas som ett amerikanskt postnummer, och ett värde i formen ±DD.DDDD±DDD.DDDD tolkas som ett latitud-/longitudpar. Tecknen krävs för varje värde. Exempel: +38.6317+120.5509 anger latitud 38.6317, longitud 120.5509. </p> <p>Se <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Om närhetssökning </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>30 </p> </td> 
   <td colname="col2"> <p>sp_q_max_relevant_distance </p> </td> 
   <td colname="col03"> <p>sp_q_max_relevant _distans _# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_max_relevant_distance= <i>value</i> </code> </p> <p> <code> sp_q_max_relevant_distance_#= <i>value</i> </code> </p> </td> 
   <td colname="col4"> <p>Dessa parametrar styr den relevanta beräkning som används för närhetssökningar. Användningen av <span class="codeph"> sp_q_max_relevant_distance </span> påverkar huvudfrågan, <span class="codeph"> sp_q_max_relevant_distance_# </span> (där <span class="codeph"> # </span> ersätts med ett tal mellan 1 och 16), påverkar den numrerade frågan. </p> <p>Standardvärdet för <span class="codeph"> sp_q_max_relevant_distance </span> är 100. </p> <p>Ett perfekt relevansresultat för närhetskomponenten skulle representera avståndet 0. Ett minsta relevansvärde för proximity-komponenten skulle representera ett avstånd precis över det angivna <span class="codeph"> sp_q_max_relevant_distance_# </span> -värdet. </p> <p>Se <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Om närhetssökning </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>31 </p> </td> 
   <td colname="col2"> <p>sp_q_min_day, sp_q_min_month, sp_q_min_year </p> <p>sp_q_max_day, sp_q_max_month, sp_q_max_year </p> </td> 
   <td colname="col03"> <p>sp_q_min_day_#, sp_q_min_month_#, sp_q_min_year_# </p> <p> sp_q_max_day_#, sp_q_max_month_#, sp_q_max_year_# </p> </td> 
   <td colname="col3"> <p> <code> sp_q_min_day=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year=<i>integer value</i> </code> </p> <p> <code> sp_q_min_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_min_year_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_day_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_month_#=<i>integer value</i> </code> </p> <p> <code> sp_q_max_year_#=<i>integer value</i> </code> </p> </td> 
   <td colname="col4"> <p>Parametrarna används för att ange minsta och högsta datumintervall för en viss fråga. Parametrarna <span class="codeph"> sp_q_min_day </span>, <span class="codeph"> sp_q_min_month </span>, <span class="codeph"> sp_q_min_year </span>, <span class="codeph"> sp_q_max_day </span>, <span class="codeph"> sp_q_max_month </span><i></i> <span class="codeph"> </span>och¥sp_q_max_year¥ gäller för huvudfrågan (¥ sp_q¥). </p> <p>Numret <span class="codeph"> # </span>i parameternamnet ersätts med ett tal mellan 1 och 16 (t.ex. <span class="codeph"> sp_q_min_day_6 </span> gäller för den numrerade frågan <span class="codeph"> sp_q_6 </span>). </p> <p>Det är tillåtet att endast ange ett minimidatum, endast ett maximidatum eller både minimi- och maximidatum. För en given minsta eller högsta uppsättning måste dock alla tre datumparametrar anges (dag, månad och år). Som standard genomsöks alla datum i förhållande till Greenwich Mean Time. </p> <p>I följande kodavsnitt kan en användare söka efter ordet "orange" i dokument med ett datum mellan 1 januari 2000 och 31 december 2000 i ett användardefinierat fält med namnet <span class="codeph"> PublishDate </span>: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>32 </p> </td> 
   <td colname="col2"> <p>sp_q_min, sp_q_max </p> </td> 
   <td colname="col03"> <p>sp_q_min_#, sp_q _max_#, sp_q _exact_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_min= värde </span> </p> <p> <span class="codeph"> sp_q_max= värde </span> </p> <p> <span class="codeph"> sp_q_min_#= värde </span> </p> <p> <span class="codeph"> sp_q_max_#= värde </span> </p> <p> <span class="codeph"> sp_q_exact_#=värde </span> </p> </td> 
   <td colname="col4"> <p>De här parametrarna anger ett lägsta (och/eller högsta) värde som ska tillämpas på den numrerade eller den huvudsakliga frågan. Användningen av <span class="codeph"> sp_q_min </span>, <span class="codeph"> sp_q_max </span>och <span class="codeph"> sp_q_exact </span> påverkar huvudfrågan ( <span class="codeph"> sp_q </span>). </p> <p>Ersätt <span class="codeph"> # </span>i parameternamnet med en siffra mellan 1 och 16 (t.ex. <span class="codeph"> sp_q_min_8 </span> gäller för den numrerade frågan <span class="codeph"> sp_q_8 </span>). </p> <p>Användningen av <span class="codeph"> sp_q_exact_# </span> är snabb för att ange både <span class="codeph"> sp_q_min_# </span> och <span class="codeph"> sp_q_max_# </span> med samma värde. Om <span class="codeph"> sp_q_exact_# </span> anges ignoreras alla motsvarande <span class="codeph"> sp_q_min_# </span> - eller <span class="codeph"> sp_q_max_#- </span> parametrar. </p> <p>Parametrarna <span class="codeph"> sp_q_min_# </span>, <span class="codeph"> sp_q_max_# </span> och <span class="codeph"> sp_q_exact_# </span> kan ange flera separerade värden med "|". Om du till exempel vill söka efter dokument som innehåller värdet grönt eller rött i fältet "color": <span class="codeph"> ...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>33 </p> </td> 
   <td colname="col2"> <p>sp_q_nocp </p> </td> 
   <td colname="col03"> <p>sp_q_nocp _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_nocp= 1 eller 0 </span> </p> <p> <span class="codeph"> sp_q_nocp_#= 1 eller 0 </span> </p> </td> 
   <td colname="col4"> <p>Standardparametervärdet är <span class="codeph"> 0, vilket innebär </span> att Common Phrase-tillägg utförs. </p> <p>Om värdet är <span class="codeph"> 1 </span> för den motsvarande sökfrågan utförs inte Common Phrases-tillägg. </p> <p>Om du använder <span class="codeph"> sp_q_nocp </span> påverkas huvudsökfrågeparametern <span class="codeph"> sp_q </span>. Om du vill använda den här parametern på en numrerad sökfråga ersätter du <span class="codeph"> # </span> i parameternamnet med motsvarande nummer. Exempel: <span class="codeph"> sp_q_nocp_8 </span> gäller den numrerade sökfrågan <span class="codeph"> sp_q_8 </span>. </p> <p> 
     <!--See also <xref href="c_about_common_phrases.xml#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local">About Common Phrases</xref>--> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>34 </p> </td> 
   <td colname="col2"> <p>sp_q_required </p> </td> 
   <td colname="col03"> <p>sp_q krävs _# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_q_required= 1 eller 0 eller -1 </span> </p> <p> <span class="codeph"> sp_q_required_#= 1 eller 0 eller -1 </span> </p> </td> 
   <td colname="col4"> <p>Den här parametern avgör om en matchning måste (1), kan (0) eller inte får (-1) förekomma i motsvarande fråga för att ett dokument ska returneras på resultatsidan. </p> <p>Användning av <span class="codeph"> sp_q_required </span> påverkar huvudfrågan ( <span class="codeph"> sp_q </span>). </p> <p>Om du vill tillämpa på en numrerad fråga ersätter du <span class="codeph"> # </span> i parameternamnet med motsvarande nummer (t.ex. <span class="codeph"> sp_q_required_8 </span> gäller för den numrerade frågan <span class="codeph"> sp_q_8 </span>). Standardvärdet för parametern är 1 (måste matcha). </p> <p>Om du vill söka efter dokument som innehåller ordet "calc" men inte innehåller "mac", "win" eller "all" i det användardefinierade fältet "platform", kan ditt HTML-sökformulär innehålla följande rader: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>35 </p> </td> 
   <td colname="col2"> <p>sp_redirect_if_one_result </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code> </p> </td> 
   <td colname="col4"> <p>Anger om omdirigering ska ske till URL:en för sökresultat om det bara finns ett sökresultat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>36 </p> </td> 
   <td colname="col2"> <p>sp_reference </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_reference= url </span> </p> </td> 
   <td colname="col4"> <p>Anger referenswebbadressen för sökningen. Användbar för omskrivningsregler för sökning där sökresultaten länkar tillbaka till samma webbplats som sökformuläret. </p> <p>Standardvärdet är CGI HTTP_REFERRER-standardvärdet som levereras av webbläsaren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>37 </p> </td> 
   <td colname="col2"> <p>sp_ro </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_ro= <span class="varname"> fält </span>: <span class="varname"> Relevans </span></span> </p> </td> 
   <td colname="col4"> <p>Tillåter valfri söktid, per fältnamn, relevanskontroll. Värdet <span class="codeph"> eller </span> i parameternamnet står för"relevansåsidosättning". Parametern accepterar ett eller flera fältnamn följt av ett kolon följt av ett relevansvärde mellan 0 och 10. </p> <p>Om du till exempel vill ange relevansvärdet för fältnamnet "body" till 10, visas parametern så här när en kund utför en sökning: </p> <p> <span class="codeph"> sp_ro=body:10 </span> </p> <p>Om du vill ange flera åsidosättningar av fältrelevans i parametersträngen kan du använda en pipe-avgränsare. Om du till exempel vill ange relevansvärdet för fältnamnen"body" och"title" till 9, visas parametern så här när en kund gör en sökning: </p> <p> <span class="codeph"> sp_ro=body:9|title:9 </span> </p> <p> <p>Obs!  Att ange ett fält som inte ingår i den associerade sökningen har ingen effekt. Om du t.ex. anger <span class="codeph"> sp_ro=title:10 </span>men inte söker efter namnet på <span class="codeph"> titelfältet </span> , har <span class="codeph"> parametern sp_ro ingen effekt </span> . Att ange ett fältnamn med <span class="codeph"> parametern sp_ro </span> söker alltså inte automatiskt i det fältet. i stället åsidosätter den bara fältets relevanta inställning. </p> </p> <p>Se <a href="../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3" type="task" format="dita" scope="local"> Redigera fördefinierade eller användardefinierade meta tag-fält </a>. </p> <p>Se <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" type="concept" format="dita" scope="local"> Om regler för Frågerengöring </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>38 </p> </td> 
   <td colname="col2"> <p>sp_s </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_s= tal </span> </p> </td> 
   <td colname="col4"> <p>Anger sorteringsordningen. Noll (0) är standardvärdet och innebär att sortera efter relevans. Ett (1) betyder att sortera efter datum och -1 betyder att inte sortera. </p> <p>Du kan ange ett fältnamn för värdet på <span class="codeph"> parametern sp_s </span> . Exempel: <span class="codeph"> sp_s=title </span> sorterar resultaten enligt värdena i titelfältet. När ett fältnamn används för värdet av en <span class="codeph"> sp_s- </span> parameter sorteras resultaten efter det fältet och subsorteras sedan efter relevans. </p> <p>Aktivera den här funktionen genom att ange Sortering för det refererade fältet till antingen <span class="uicontrol"> Stigande </span> eller <span class="uicontrol"> Fallande </span> i <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span> . </p> <p>Du kan också tilldela flera sorteringsfält till en enskild fråga genom att ställa in <span class="codeph"> parametern sp_s </span> flera gånger i sökformuläret. Följande mallrader anger att sökresultaten ska sorteras först efter artistnamn, sedan efter albumnamn och sedan efter spårnamn. </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code> </p> <p>Det går också att sortera tabellmatchade fältdata genom att ange en tabellnamnskvalificerare före fältnamnet, till exempel items.price. Mer information om tabellmatchning finns i parametern <span class="codeph"> sp_field_table </span> . </p> <p>Om du söker efter närhet kan du sortera resultaten efter närhet genom att ange ett "närhetsutdatafält". </p> <p>Se <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Om närhetssökning </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>39 </p> </td> 
   <td colname="col2"> <p>sp_sr </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sr= fält </span> </p> </td> 
   <td colname="col4"> <p>Anger det rangordningsfält som ska användas för statisk rankning. Fältet måste vara ett fält av typen Rank med relevans större än 0. Om ingen <span class="codeph"> sp_sr- </span> parameter anges för frågan, markeras ett fält av typen Rank automatiskt. </p> <p>Om du vill inaktivera statisk rankning för en viss fråga tar du med ett NULL-värde för <span class="codeph"> sp_sr </span> (till exempel <span class="codeph"> &lt;input type="hidden" name="sp_sr" value=""&gt; </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>40 </p> </td> 
   <td colname="col2"> <p>sp_sfvl_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_field= sträng </span> </p> </td> 
   <td colname="col4"> <p>Anger namnet på ett fält som ska användas tillsammans med <span class="codeph"> &lt;search-field-value-list&gt;- </span> taggen i sökmallen. </p> <p>Du kan ange flera <span class="codeph"> sp_sfvl_field- </span> parametrar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>41 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_count </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_sfvl_df_count= <span class="varname"> &lt;heltalsvärde&gt; </span></span> </p> </td> 
   <td colname="col4"> <p> 
     <!--NEW 2/2/2014-->Begäranden upp till <span class="codeph"> <span class="varname"> &lt;integer_value&gt; </span> </span><span class="codeph"> dynamiska fält av typen search-field-value-list </span> för den här sökningen. </p> <p>Standardvärdet är 0. Det högsta tillåtna värdet är det aktuella antalet dynamiska facet, dynamiskt facet-field-count som har definierats för ett givet index. Heltalsvärden under 0 behandlas som 0. Heltalsvärden som anges ovan <span class="codeph"> dynamisk-facet-field-count </span> begränsas till <span class="codeph"> dynamic-facet-field-count </span>. Värden som inte är heltal ignoreras. behandlas som standardvärde. </p> <p>Sökningen för ett givet segment har ett maximalt tillåtet <span class="codeph"> sp_sfvl_df_count- </span> värde för det här segmentets <span class="codeph"> dynamiska facet-field-count- </span> värde. När du sammanfogar segmentresultat <span class="codeph"> är det maximala effektiva värdet för </span> sp_sfvl_df_count det maximala faktiska <span class="codeph"> sp_sfvl_df_count </span> för alla segment. </p> <p>Se <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Konfigurera dynamiska aspekter </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>42 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_exclude </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_exclude= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span> </span>&gt;|.. </p> </td> 
   <td colname="col4"> <p> Anger en lista med specifika dynamiska facettsfält som ska uteslutas vid sökning. </p> <p>Som standard beaktas alla dynamiska fasettsfält. </p> <p>Se <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Konfigurera dynamiska aspekter </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>43 </p> </td> 
   <td colname="col2"> <p> sp_sfvl_df_include </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> <span class="codeph"> sp_sfvl_df_include= &lt; <span class="varname"> field_name </span>&gt;[|&lt; <span class="varname"> field_name </span> </span>&gt;|.. </p> </td> 
   <td colname="col4"> <p> Anger en lista med specifika dynamiska facettfält som ska inkluderas i sökresultaten. </p> <p> <p>Obs!  Parametern <span class="codeph"> sp_sfvl_df_count </span> bestämmer det totala antalet dynamiska facet-fält som ska returneras, inklusive de som anges med <span class="codeph"> sp_sfvl_df_include </span>. Det innebär att <span class="codeph"> sp_sfvl_df_include </span> inte tillåter att det totala antalet returnerade dynamiska facet överskrider <span class="codeph"> sp_sfvl_df_count </span>. </p> </p> <p>Se <a href="../c-about-design-menu/c-about-dynamic-facets.md#task_D17F484130E448258100BAC1EEC53F39" format="dita" scope="local"> Konfigurera dynamiska aspekter </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>44 </p> </td> 
   <td colname="col2"> <p>sp_staged </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_staged= 0 eller 1 </span> </p> </td> 
   <td colname="col4"> <p>Om <span class="codeph"> sp_staged=1 </span> skickas med en fråga är frågan som körs en mellanlagrad sökning. </p> <p>I en mellanlagrad sökning används alla komponenter som för närvarande är mellanlagrade, inklusive index och mallar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>45 </p> </td> 
   <td colname="col2"> <p>sp_start_day, sp_start_month, sp_start_year </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_start_day= tal </span> </p> <p> <span class="codeph"> sp_start_month= number </span> </p> <p> <span class="codeph"> sp_start_year= number </span> </p> </td> 
   <td colname="col4"> <p>Den här trippeln med värden anger startdatumintervallet för sökningen och du anger det som en uppsättning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>46 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_ föreslår _q </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_PI_q= tal </span> </p> </td> 
   <td colname="col4"> <p>Parametern <span class="codeph"> sp_iss_q </span> avgör vilken <span class="codeph"> sp_q[_#]- </span> parameter som ska användas med tjänsten Föreslå. </p> <p>Standardvärdet för <span class="codeph"> sp_iss_q </span> är 0, vilket innebär att sökmotorn använder värdet för <span class="codeph"> sp_q </span> för att fastställa förslagen. </p> <p>Ange <span class="codeph"> sp_iss_q=1 </span> om du vill använda värdet för <span class="codeph"> sp_q_1 </span> för att fastställa förslagen osv. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>47 </p> </td> 
   <td colname="col2"> <p>sp_t </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_t= sträng </span> </p> </td> 
   <td colname="col4"> <p>Anger transportmallen som ska användas. </p> <p>Den här parametern är användbar om du vill styra utseendet på de viktigaste sökresultaten på webbplatsen genom att använda olika söktransportmallar för varje område i sökkontot. </p> <p>Standardtransportmallen är "search". </p> <p>Se <a href="../c-appendices/c-templates.md#reference_12AAB3B9F4C74C11956F1DBA95714C2F" type="reference" format="dita" scope="local"> Hantera flera transportmallar för din webbplats </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>48 </p> </td> 
   <td colname="col2"> <p>sp_trace </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_trace= 0 eller 1 </span> </p> </td> 
   <td colname="col4"> <p>När det anges som <span class="codeph"> sp_stage=1 </span>aktiveras huvudfunktionen för sökspårning i simulatorn. </p> <p>Se <a href="../c-about-simulator.md#concept_020AA6751E32421A96A3455508364C7E" format="dita" scope="local"> Om simulator </a>. </p> <p> <p>Obs!  Om den här parametern inte anges samlar huvudsökningen inte in kalkeringsinformationen och de relaterade taggarna för grundsökmallen har inga utdata. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>49 </p> </td> 
   <td colname="col2"> <p>sp_w, sp_w_control </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_w= <i>sound-alike-enable</i> </code> </p> <p> <code> sp_w_control=<i>sound-alike-control</i> </code> </p> </td> 
   <td colname="col4"> <p>Anger att ljudmatchning ska vara aktiverad eller inaktiverad för den här frågan. </p> <p>sp_w_control for "Exact" ignoreras. Ljudliknande matchning är inaktiverad. </p><p>sp_w_control for "Alike" ignoreras. Ljudliknande matchning är aktiverad</p><p>sp_w_control för Any else är 1. Ljudliknande matchning är inaktiverad. </p><p>sp_w_control för Allt annat är vad som helst. Ljudliknande matchning är aktiverad. </p>Med <span class="codeph"> parametern sp_w_control kan </span> du skapa en kryssruta med negativ eller positiv ordalydelse för slutanvändarkontroll av ljudmatchning. </p> <p>Om <span class="codeph"> sp_w_control=0 </span> används en negativt formulerad kryssruta för att ställa in <span class="codeph"> sp_w- </span> parametern som i följande exempel: </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code> </p> <p>Om <span class="codeph"> sp_w_control=1 </span> används en kryssruta med ett positivt ord för att ange <span class="codeph"> parametern </span> sp_w enligt följande: </p> <p> <code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code> </p> <p>Se exemplet på avancerat sökformulär för fler exempel på hur du använder <span class="codeph"> parametrarna </span> sp_w_control <span class="codeph"> och </span> sp_w. </p> <p>Se <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Exempel på avancerat sökformulär </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>50 </p> </td> 
   <td colname="col2"> <p>sp_x </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x= fält </span> </p> </td> 
   <td colname="col4"> <p>Anger vilka fält som ska genomsökas efter frågesträngen. innebär att söka i alla fält. titel innebär att endast söka efter titelfält. desc betyder att du bara söker i dokumentbeskrivningsfält. tangenter betyder att endast söka efter dokumentnyckelord. brödtext innebär att endast söka i brödtext. alt betyder att du bara söker efter alternativ text. url betyder att du bara söker efter URL-värden. mål innebär att endast söka efter målnyckelord. I alla dessa fall ignoreras användarspecifikationen för fälten "text:", "desc:", "keys:", "body:", "alt:", "url:" och "target:" i motsvarande <span class="codeph"> sp_q- </span> parameter. Om <span class="codeph"> sp_x inte </span> finns, eller om det är inställt på en tom sträng eller någon annan, tillåts standardprefixen för användarfält. Mer information om fältprefix finns i beskrivningen av söktips. </p> <p>Se <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> Om sökningar </a>. </p> <p>Se exemplet med den avancerade formulärbeskrivningen för sökning för exempel med <span class="codeph"> parametern sp_x </span> . </p> <p>Se <a href="../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A" type="reference" format="dita" scope="local"> Exempel på avancerat sökformulär </a>. </p> <p>Du kan skapa frågor som söker i alla fält som är inställda på <span class="uicontrol"> Sök som standard </span> under <span class="uicontrol"> Alternativ </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span> genom att ange <span class="codeph"> sp_x=any </span>. Både för- och användardefinierade fält kan användas som värde för <span class="codeph"> parametern sp_x </span> . </p> <p>Du kan också tilldela flera fält till en enskild fråga genom att ställa in <span class="codeph"> parametern sp_x flera gånger </span> . Med följande mallrader kan användare fråga både "title" och "author" om "Great Books". </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>51 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p>sp_x_# </p> </td> 
   <td colname="col3"> <p> <span class="codeph"> sp_x_#= field-name </span> </p> </td> 
   <td colname="col4"> <p>Den här parametern anger vilket fält som ska sökas i motsvarande <span class="codeph"> sp_q_# </span> -fråga. Värdet <span class="codeph"> <span class="codeph"> # </span> </span> ersätts med ett tal mellan 1 och 16 (till exempel <span class="codeph"> sp_x_8 </span>). Fältnamnet är ett för- eller användardefinierat fält. </p> <p>Om ingen <span class="codeph"> sp_x_#- </span> parameter anges för en viss numrerad fråga genomsöks alla fält som definieras som <span class="uicontrol"> Sök efter standard </span> enligt inställningen <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span> . </p> <p>Om du till exempel skickar följande formulär returneras alla dokument som innehåller ordet "Great" som även innehåller ordet "Fitzgerald" i fältet "author": </p> <p> <code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code> </p> <p>Du kan associera flera fältnamn med en viss fråga eller numrerad fråga genom att ange mer än en instans av samma <span class="codeph"> sp_x- </span> eller <span class="codeph"> sp_x_#- </span> parameter i en enda sökbegäran. </p> <p>Om du till exempel vill söka efter ordet "blomma" i både "brödtext" och "tangenter" kan du skapa ett sökformulär med följande information: </p> <p> <code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ett typiskt exempel på hur CGI-parametrar för backend-sökning används {#section_260012BBC2514CC9A8E02E53DE8B41EE}

Följande länkfrågor startar en sökning med &quot;Musik&quot; som sökfråga och använder alla standardparametrar. Observera att URL:en delas upp på två rader för läsbarhet. I din HTML-kod ska den här länken finnas på en rad.

```
<a href="https://search.atomz.com/search/?sp_q=Music&sp_a=sp99999999"> 
Testing...</a>
```

Samma funktioner definieras vanligtvis i ett formulär:

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q" value="Music"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
</form>
```

Du bör vanligtvis använda standardparametrar när du startar en sökning. På så sätt visas den första sidan, sorterad efter relevans, så att kunden kan välja andra sidor och andra alternativ. Om sökformuläret på din webbplats innehåller alternativ för samlingar anger du samlingens namn som en parameter.

## Ett detaljerat exempel på hur CGI-parametrar för backend-sökning används {#section_5FA3C620D5124FB2AB28857F8D8473F6}

Följande formulärfrågor visar `25` resultat med början på resultatet `10`. Sammanfattningar visas inte, sorteringsordningen är efter datum och samlingen med namnet `support` används. Endast dokument som är daterade de senaste 30 dagarna returneras.

```
<form action="https://search.atomz.com/search/"> 
<input size=12 name="sp_q"><br> 
<input type=hidden name="sp_a" value="sp99999999"> 
<input type=submit value="Search"><br> 
<input type=hidden name=sp_n value=10> 
<input type=hidden name=sp_c value=25> 
<input type=hidden name=sp_m value=0> 
<input type=hidden name=sp_s value=1> 
<input type=hidden name=sp_k value="support"> 
<input type=hidden name=sp_date_range value=30> 
</form>
```

