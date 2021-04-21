---
description: Lär dig hur du använder olika CGI-parametrar.
solution: Target
title: CGI-parametrar
topic-legacy: Appendices,Site search and merchandising
uuid: a5f43547-bc15-44aa-ba23-6b8b573e09d2
exl-id: 9f24aebf-5fa3-433e-b66d-4129bdd3f7f6
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1938'
ht-degree: 0%

---

# CGI-parametrar{#cgi-parameters}

## CGI-parametrar {#concept_F395999090FE4926B38BC73D5E612800}

## Sök efter CGI-parametrar {#reference_DA27A8B0728246DA94994885E1353890}

Du kan kopiera och klistra in formulärkoden i webbplatsens HTML-kod ( **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]**).

Se [Kopiera HTML-koden för sökformuläret till ...](../c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Du kan också ange parametrarna som visas antingen i själva sökformuläret eller från ett skript. Förutom de parametrar som anges nedan kan du även använda backend-sökparametrarna för att styra sökningen.

Se [CGI-parametrar för backend-sökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

Sökbegäranden består av en bas-URL. Bas-URL:en anger vilket konto kunden söker och en uppsättning CGI-parametrar (nyckel-värde-par) som anger hur det önskade sökresultatet för det associerade kontot ska returneras.

Bas-URL:en är kopplad till ett specifikt konto och en staged- eller live-miljö. Du kan begära flera alias för bas-URL:en från din kontohanterare. Ett företag som heter Megacorp kan till exempel ha två bas-URL:er kopplade till sitt konto: `https://search.megacorp.com` och `https://stage.megacorp.com`. Den tidigare URL:en söker i sitt liveindex och den senare URL:en söker i sitt mellanlagrade index.

Tre format för CGI-parametrar stöds. Som standard är ditt konto konfigurerat att avgränsa CGI-parametrar med ett semikolon, som i följande exempel:

`https://search.megacorp.com?q=shoes;page=2`

Om du vill kan du låta kontohanteraren konfigurera ditt konto så att det använder et-tecken för att separera CGI-parametrarna, som i följande exempel:

`https://search.megacorp.com?q=shoes&page=2`

Ett tredje format, som kallas SEO-format, stöds också när ett snedstreck `/` används i stället för avgränsaren och likhetstecken som i följande exempel:

`https://search.megacorp.com/q/shoes/page/2`

Varje gång SEO-formatet används för att skicka en begäran returneras alla utdatalänkar i samma format.

| Parametern Guidad sökning | Exempel | Beskrivning |
|--- |--- |--- |
| q | `q=string` | Anger frågesträngen för sökningen. Den här parametern mappar till `sp_q`-parametern för backend-sökning.  Se [CGI-parametrar för backend-sökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| q# | `q#=string` | Motsökning (sökning i ett visst fält) görs med hjälp av numrerade q- och x-parametrar.  q-parametern definierar den term som du söker efter i ansiktet enligt den motsvarande numrerade x-parametern.<br>Om du t.ex. har två ansikten med namnet size och color kan du ha något som q1=small;x1=size;q2=red;x2=color.  Den här parametern mappar till `sp_q_exact_#`-parametrar för backend-sökning.  <br>Se CGI-parametrar för  [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| x# | `q#=string` | Motsökning (sökning i ett visst fält) görs med hjälp av numrerade q- och x-parametrar.  q-parametern definierar den term som du söker efter i ansiktet enligt den motsvarande numrerade x-parametern. <br>Om du t.ex. har två ansikten med namnet size och color kan du ha något som q1=small;x1=size;q2=red;x2=color.  Den här parametern mappar till `sp_x_#`-parametrar för backend-sökning.  <br>Se CGI-parametrar för  [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| samling | `collection=string` | Anger den samling som ska användas för sökningen.  Den här parametern mappar till `sp_k`-parametern för backend-sökning.  Se [CGI-parametrar för backend-sökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| antal | `count=number` | Anger det totala antalet resultat som visas.  Standardvärdet definieras i [!UICONTROL Settings ] > [!UICONTROL Searching ] > [!UICONTROL Searches ]. .  Den här parametern mappar till `sp_c`-parametern för backend-sökning.  Se [CGI-parametrar för backend-sökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| page | `page=number` | Anger sidan med resultat som returneras. |
| rankning | `rank=field` | Anger det rangordningsfält som ska användas för statisk rankning.  Fältet måste vara ett fält av typen Rank med relevans större än 0.  Den här parametern mappas till parametern `sp_sr` för serverdelen.  Se [CGI-parametrar för backend-sökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |
| sortera | `sort=number` | Anger sorteringsordningen.<br>&quot;0&quot; är standardvärdet och sorterar efter relevanspoäng, &quot;1&quot; sortera efter datum. -1 sorterar inte.  Användarna kan ange ett fältnamn för värdet för parametern `sp_s`.  `sp_s=title` sorterar till exempel resultaten enligt de värden som finns i titelfältet. När ett fältnamn används som värde för en ` sp_s `-parameter sorteras resultaten efter det fältet och subsorteras sedan efter relevans.  Om du vill aktivera den här funktionen klickar du på [!UICONTROL Settings ] > [!UICONTROL Metadata ] > [!UICONTROL Definitions ]. På sidan Definitioner klickar du på [!UICONTROL Add New Field ] eller [!UICONTROL Edit ] för ett visst fältnamn. I listrutan [!UICONTROL Sorting ] väljer du antingen [!UICONTROL Ascending ] eller [!UICONTROL Descending ]. Den här parametern mappar till `sp_s`-parametern för backend-sökning. <br>Se CGI-parametrar för  [serverdelssökning].(../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8). |

## CGI-parametrar för backend-sökning {#reference_582E85C3886740C98FE88CA9DF7918E8}

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
   <td colname="col3"> <p> <code>sp_a= string </code> </p> </td> 
   <td colname="col4"> <p>Anger kontonummersträngen. Den här parametern är obligatorisk och måste vara en giltig kontonummersträng. Du hittar kontonummersträngen under <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Kontoalternativ </span> &gt; <span class="uicontrol"> Kontoinställningar </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>sp_advanced </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_advanced= 0 or 1 </code> </p> </td> 
   <td colname="col4"> <p>Om <code>sp_advanced=1 </code> skickas med en fråga används all kod mellan <code>&lt;search-if-advanced&gt; </code>-taggen och <code>&lt;/search-if-advanced&gt; </code>-taggen i sökmallen för sökformuläret. All kod mellan taggen <code>&lt;search-if-not-advanced&gt; </code> och taggen <code>&lt;/search-if-not-advanced&gt; </code> ignoreras. Om <code>sp_advanced=0 </code> (eller något annat värde) skickas ignoreras mallblocket &lt;search-if-advanced&gt; och mallblocket &lt;search-if-not-advanced&gt; används. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>sp_c </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_c= number </code> </p> </td> 
   <td colname="col4"> <p>Anger det totala antalet resultat som ska visas. Standardvärdet är 10. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>sp_context_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_context_field= <i>field</i> </code> </p> </td> 
   <td colname="col4"> <p>Samlar in sammanhangsberoende information för det angivna fältet. Samlad information genereras i sökresultaten med hjälp av malltaggen <code>&lt;search-context&gt; </code>. Standardvärdet är <code>body </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>sp_d </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_d= type </code> </p> </td> 
   <td colname="col4"> <p>Anger vilken typ av datumintervall som ska utföras. Möjliga värden för typen är any, vilket innebär att sökning i datumintervall inte utförs, custom, vilket anger att värdet <code>sp_date_range </code> ska användas för att bestämma vilka datum som ska sökas, och specific, vilket anger att värdena i <code>sp_start_day </code>, <code>sp_start_month </code>, <code>sp_start_year </code>, <code>sp_end_day </code>, <code>sp_end_month </code> och <code>sp_end_year </code> används för att avgöra vilket datumintervall som ska sökas. <code>sp_d </code> är bara nödvändigt om sökformuläret innehåller ett alternativ för att söka antingen efter ett anpassat intervall (som  <code>sp_date_range </code>exempel) eller efter ett visst start- och slutdatumintervall. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>6 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_d_# </p> </td> 
   <td colname="col3"> <p> <code>sp_d_#= type </code> </p> </td> 
   <td colname="col4"> <p>Anger vilken typ av datumintervall som ska användas för motsvarande <code>sp_q_# </code>-fråga. "#" ersätts med ett tal mellan 1 och 16 (t.ex. <code>sp_d_8 </code> gäller för den numrerade frågan <code>sp_q_8 </code>). </p> <p>Du kan ställa in <code>type </code> på any, vilket betyder att sökning i datumintervall inte utförs, anpassad, vilket anger att värdet <code>sp_date_range_# </code> används för att bestämma vilka datum som ska sökas och specifik, vilket innebär att värdena i <code>sp_q_min_day_# </code>, <code>sp_q_min_month_# </code>, <code>sp_q_min_year_# </code>, <code>sp_q_max_day_# </code>, <code>sp_q_max_month_# </code> och <code>sp_q_max_year_# </code> ska användas för att bestämma datumintervallet. Du behöver bara använda <code>sp_d_# </code> om sökformuläret innehåller ett alternativ för att söka antingen efter ett anpassat intervall (med <code>sp_date_range_# </code>) eller efter ett visst start- och slutdatumintervall. </p> </td> 
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
   <td colname="col4"> <p>Anger ett fördefinierat datumintervall som ska användas för motsvarande <code>sp_q_# </code>-fråga. "#" ersätts med ett tal mellan 1 och 16 (t.ex. <code>sp_date_range_8 </code> gäller för den numrerade frågan <code>sp_q_8 </code>). </p> <p>Värden större än eller lika med noll anger antalet dagar som ska sökas före idag. Värdet 0 anger till exempel idag; Värdet 1 anger idag och igår. ett värde på 30 anger inom de senaste 30 dagarna o.s.v. </p> <p>Värden under noll anger ett anpassat intervall enligt följande: </p> <p>-1 = "Ingen", samma som att ange inget datumintervall. </p> <p>-2 = "Den här veckan", som söker från söndag till lördag den aktuella veckan. </p> <p>-3 = "Sista veckan", som söker från söndag till lördag i veckan före den aktuella veckan. </p> <p>-4 = "Den här månaden", som söker efter datum inom den aktuella månaden. </p> <p>-5 = "Sista månaden", som söker efter datum i månaden före den aktuella månaden. </p> <p>-6 = "Det här året", som söker efter datum under det aktuella året. </p> <p>-7 = "Sista året", som söker efter datum under året före det aktuella året. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>9 </p> </td> 
   <td colname="col2"> <p>sp_dedupe_field </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_dedupe_field= <i>fieldname</i> </code> </p> </td> 
   <td colname="col4"> <p>Anger ett enskilt fält som sökresultaten ska tas bort från. Alla dubblettresultat i det fältet tas bort från sökresultatet. Om du till exempel anger <code>sp_dedupe_field=title </code> visas bara det översta resultatet för en viss titel i sökresultatet (inga två resultat har identiskt innehåll i titelfältet). För flervärdestypfält (tillåtelselista) används hela fältinnehållet för jämförelse. Endast ett fält kan anges. Det är inte tillåtet att ange "table-qualifier" i fältnamnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>sp_e </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code>sp_e= number </code> </p> </td> 
   <td colname="col4"> <p>Anger att automatisk utökning av jokertecken ska ske för alla ord från frågesträngen med fler än siffror. Med andra ord anger <code>sp_e=5 </code> att ord med fem eller fler tecken, som "query" eller "number", ska expanderas med jokertecknet "*", vilket gör sökningen ekvivalent med en sökning efter "query*" eller "number*". Ord med färre tecken utökas inte, så om du söker efter ordet utökas inte jokertecknet automatiskt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p> </p> </td> 
   <td colname="col03"> <p> sp_e_# </p> </td> 
   <td colname="col3"> <p> <code>sp_e_#= number </code> </p> </td> 
   <td colname="col4"> <p>Anger att automatisk utökning av jokertecken sker för alla ord från den motsvarande <code>sp_q_# </code>-frågesträngen med fler än siffror. Med andra ord anger <code>sp_e_2=5 </code> att ord med fem eller fler tecken i <code>sp_q_2 </code>-frågesträngen, som "query" eller "number", ska expanderas med jokertecknet " <code>* </code>", vilket gör sökningen ekvivalent med en sökning efter "query*" eller "number*". Ord med färre tecken utökas inte, så om du söker efter ordet i <code>sp_q_2 </code> utökas inte jokertecknet automatiskt. </p> </td> 
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
   <td colname="col3"> <p> <code>sp_f= string </code> </p> </td> 
   <td colname="col4"> <p>Anger teckenuppsättningen för frågeparametersträngarna (till exempel <code>sp_q </code>). Strängen måste alltid matcha teckenuppsättningen på sidan som innehåller sökformuläret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>sp_field_table </p> </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> <code> sp_field_ table=table: field,field... </code> </p> </td> 
   <td colname="col4"> <p>Definierar en logisk datatabell som består av de angivna fälten. En tabell med namnet "items" som består av fälten "color", "size" och "price" skulle definieras så här: </p> <p> <code>sp_field_table=items:color,size,price </code> </p> <p>Logiska tabeller är mest användbara i samband med fält där Tillåtelselista har markerats (under <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>). Alla CGI-parametrar och malltaggar som får ett fältnamn som ett värde kan eventuellt ange ett tabellnamn följt av ett "." före fältnamnet (till exempel <code>sp_x_1=tablename.fieldname </code>). </p> <p>Om du till exempel vill söka efter dokument som innehåller ett eller flera "röda" objekt i storleken "large" (där objekten representeras som parallella rader med metadata), kan du använda följande: </p> <p> <code> sp_q_exact_1=red&amp;sp_x_1=items.color&amp; sp_q_exact_2=large&amp;sp_x_2=items.size&amp;sp_field_table=items:color,size,price </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>15 </p> </td> 
   <td colname="col2"> sp_i </td> 
   <td colname="col03"> <p> </p> </td> 
   <td colname="col3"> <p> </p></td><td colname="col4"><p></p><p></p><p><code>sp_i=1 </code><code>sp_i=2 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_k= string </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_l= string </code></p></td><td colname="col4"><p><code>sp_q </code><code>string </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_literal= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_literal=1 </code></p><p><code>sp_literal=0 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_m= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_n= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_not_found_page= url </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p= any/all/phrase </code></p></td><td colname="col4"><p><code>any </code><code>all </code><code>phrase </code></p><p><code>phrase </code><code>all </code><code>sp_p </code></p><p></p><p></p><p><code>sp_p </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_p_#= any/all/phrase </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>any </code><code>all </code><code>phrase </code></p><p><code>all </code><code>phrase </code><code>sp_p_# </code><code>any </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>exact </code><code>equivalent </code><code>compatible </code><code>sp_p </code><code>exact </code><code>sp_p </code><code>all </code><code>phrase </code><code>equivalent </code><code>sp_pt </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_pt_#= <i>exact/equivalent/compatible</i> </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_p_8 </code><code>sp_q_8 </code><code>exact </code><code>equivalent </code><code>exact </code><code>compatible </code><code>sp_p_# </code><code>exact </code><code>sp_p_# </code><code>equivalent </code><code>sp_pt_# </code><code>compatible </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q= string </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_#= text </code></p></td><td colname="col4"><p><code>sp_q_# </code><code>sp_q_1 </code><code>sp_q_16 </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_day= integer value </code></p><p><code>sp_q_month= integer value </code></p><p><code>sp_q_year= integer value </code></p><p><code>sp_q_day_#= integer value </code></p><p><code>sp_q_month_#= integer value </code></p><p><code>sp_q_year_#= integer value </code></p></td><td colname="col4"><p><code>sp_q_day </code><code>sp_q_month </code><code>sp_q_year </code><code>sp_q </code></p><p><code># </code><code>sp_q_day_6 </code><code>sp_q_6 </code></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt; Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;On&nbsp;:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Month &lt;input&nbsp;type="text"&nbsp;name="sp_q_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Year&nbsp; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_location=<i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p><p><code> sp_q_location_#= <i>latitude/longitude</i> OR <i>areacode</i> OR <i>zipcode</i> </code></p></td><td colname="col4"><p><code>sp_q_location </code><code>sp_q_location_# </code><code># </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_q_max_relevant_distance= <i>value</i> </code></p><p><code> sp_q_max_relevant_distance_#= <i>value</i> </code></p></td><td colname="col4"><p><code>sp_q_max_relevant_distance </code><code>sp_q_max_relevant_distance_# </code><code># </code></p><p><code>sp_q_max_relevant_distance </code></p><p><code>sp_q_max_relevant_distance_# </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p><p></p></td><td colname="col03"><p></p><p></p></td><td colname="col3"><p><code> sp_q_min_day=<i>integer value</i> </code></p><p><code> sp_q_min_month=<i>integer value</i> </code></p><p><code> sp_q_min_year=<i>integer value</i> </code></p><p><code> sp_q_max_day=<i>integer value</i> </code></p><p><code> sp_q_max_month=<i>integer value</i> </code></p><p><code> sp_q_max_year=<i>integer value</i> </code></p><p><code> sp_q_min_day_#=<i>integer value</i> </code></p><p><code> sp_q_min_month_#=<i>integer value</i> </code></p><p><code> sp_q_min_year_#=<i>integer value</i> </code></p><p><code> sp_q_max_day_#=<i>integer value</i> </code></p><p><code> sp_q_max_month_#=<i>integer value</i> </code></p><p><code> sp_q_max_year_#=<i>integer value</i> </code></p></td><td colname="col4"><p><code>sp_q_min_day </code><code>sp_q_min_month </code><code>sp_q_min_year </code><code>sp_q_max_day </code><code>sp_q_max_month </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_day_6 </code><code>sp_q_6 </code></p><p></p><p><code>PublishDate </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="PublishDate"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="orange"&gt;Between:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_day_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Day&lt;input&nbsp;type="text"&nbsp;name="sp_q_min_month_1"&nbsp;size="2"&nbsp;value="1"&gt;&nbsp;Start&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_min_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;Start&nbsp;Year 
      And:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_max_day_1"&nbsp;size="2"&nbsp;value="31"&gt;&nbsp;End&nbsp;Day 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_month_1"&nbsp;size="2"&nbsp;value="12"&gt;&nbsp;End&nbsp;Month 
      &lt;input&nbsp;type="text"&nbsp;name="sp_q_max_year_1"&nbsp;size="4"&nbsp;value="2000"&gt;&nbsp;End&nbsp;Year </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_min= value </code></p><p><code>sp_q_max= value </code></p><p><code>sp_q_min_#= value </code></p><p><code>sp_q_max_#= value </code></p><p><code>sp_q_exact_#=value </code></p></td><td colname="col4"><p><code>sp_q_min </code><code>sp_q_max </code><code>sp_q_exact </code><code>sp_q </code></p><p><code># </code><code>sp_q_min_8 </code><code>sp_q_8 </code></p><p><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>sp_q_min_# </code><code>sp_q_max_# </code></p><p><code>sp_q_min_# </code><code>sp_q_max_# </code><code>sp_q_exact_# </code><code>...&amp;sp_q_exact_1=green|red&amp;sp_x_1=color </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_nocp= 1 or 0 </code></p><p><code>sp_q_nocp_#= 1 or 0 </code></p></td><td colname="col4"><p><code>0 </code></p><p><code>1 </code></p><p><code>sp_q_nocp </code><code>sp_q </code><code># </code><code>sp_q_nocp_8 </code><code>sp_q_8 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_q_required= 1 or 0 or -1 </code></p><p><code>sp_q_required_#= 1 or 0 or -1 </code></p></td><td colname="col4"><p></p><p><code>sp_q_required </code><code>sp_q </code></p><p><code># </code><code>sp_q_required_8 </code><code>sp_q_8 </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="platform"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="calc"&gt; 
      Exclude:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="mac&nbsp;win&nbsp;all"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_q_required_1"&nbsp;value="-1"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_redirect_ 
      if_one_result= <i>0 or 1</i> </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_referrer= url </code></p></td><td colname="col4"><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>ro </code></p><p></p><p><code>sp_ro=body:10 </code></p><p></p><p><code>sp_ro=body:9|title:9 </code></p><p><p><code>sp_ro=title:10 </code><code>title </code><code>sp_ro </code><code>sp_ro </code></p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_s= number </code></p></td><td colname="col4"><p></p><p><code>sp_s </code><code>sp_s=title </code><code>sp_s </code></p><p></p><p><code>sp_s </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="artist"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="album"&gt; 
      &lt;input&nbsp;type="hidden"&nbsp;name="sp_s"&nbsp;value="track"&gt; 
      Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Music&nbsp;Search"&gt; </code></p><p><code>sp_field_table </code></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sr= field </code></p></td><td colname="col4"><p><code>sp_sr </code></p><p><code>sp_sr </code><code>&lt;input type="hidden" name="sp_sr" value=""&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_sfvl_field= string </code></p></td><td colname="col4"><p><code>search-field-value-list</code></p><p><code>sp_sfvl_field </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p></td><td colname="col4"><p><code>search-field-value-list </code></p><p><code>dynamic-facet-field-count </code><code>dynamic-facet-field-count </code></p><p><code>sp_sfvl_df_count </code><code>dynamic-facet-field-count </code><code>sp_sfvl_df_count </code><code>sp_sfvl_df_count </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p></p><p></p></td><td colname="col4"><p></p><p><p><code>sp_sfvl_df_count </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_include </code><code>sp_sfvl_df_count </code></p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_staged= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_staged=1 </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_start_day= number </code></p><p><code>sp_start_month= number </code></p><p><code>sp_start_year= number </code></p></td><td colname="col4"><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_suggest_q= number </code></p></td><td colname="col4"><p><code>sp_suggest_q </code><code>sp_q[_#] </code></p><p><code>sp_suggest_q </code><code>sp_q </code></p><p><code>sp_suggest_q=1 </code><code>sp_q_1 </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_t= string </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_trace= 0 or 1 </code></p></td><td colname="col4"><p><code>sp_stage=1 </code></p><p></p><p><p></p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code> sp_w= <i>sound-alike-enable</i> </code></p><p><code> sp_w_control=<i>sound-alike-control</i> </code></p></td><td colname="col4"><p></p><p></p><p></p><p></p><p></p><code>sp_w_control </code></p><p><code>sp_w_control=0 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="0"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="exact"&gt;No&nbsp;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control=1 </code><code>sp_w </code></p><p><code class="syntax html"> &lt;input&nbsp;type=hidden&nbsp;name="sp_w_control"&nbsp;value="1"&gt;&lt;input&nbsp;type=checkbox&nbsp;name="sp_w"&nbsp;value="alike"&gt;Sound-Alike&nbsp;matching </code></p><p><code>sp_w_control </code><code>sp_w </code></p><p></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x= field </code></p></td><td colname="col4"><p><code>sp_q </code><code>sp_x </code></p><p></p><p><code>sp_x </code></p><p></p><p><code>sp_x=any </code><code>sp_x </code></p><p><code>sp_x </code></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="title"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x"&nbsp;value="author"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="Great&nbsp;Books"&gt; </code></p></td></tr><tr><td colname="col1"><p></p></td><td colname="col2"><p></p></td><td colname="col03"><p></p></td><td colname="col3"><p><code>sp_x_#= field-name </code></p></td><td colname="col4"><p><code>sp_q_# </code><code> # </code><code>sp_x_8 </code></p><p><code>sp_x_# </code></p><p></p><p><code class="syntax html"> Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q"&nbsp;value="great"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="author"&gt;Search&nbsp;only&nbsp;documents&nbsp;written&nbsp;by:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="Fitzgerald"&gt; </code></p><p><code>sp_x </code><code>sp_x_# </code></p><p></p><p><code class="syntax html"> &lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="body"&gt;&lt;input&nbsp;type="hidden"&nbsp;name="sp_x_1"&nbsp;value="keys"&gt;Search&nbsp;for:&nbsp;&lt;input&nbsp;type="text"&nbsp;name="sp_q_1"&nbsp;value="flower"&gt; </code></p></td></tr></tbody></table>

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

Följande formulärfrågor visar `25`-resultat med början vid `10`. Sammanfattningar visas inte, sorteringsordningen är efter datum och samlingen `support` används. Endast dokument som är daterade de senaste 30 dagarna returneras.

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
