---
description: Använd menyn Skriv om regler om du vill ange regler för crawlning och sökning av URL:er och titlar.
solution: Target
subtopic: Rewrite Rules
title: Om menyn Skriv om regler
topic: Settings,Site search and merchandising
uuid: 77ee84dd-fdba-4d34-ae8e-2fe786599800
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '10202'
ht-degree: 0%

---


# Om menyn Skriv om regler {#about-the-rewrite-rules-menu}

Använd menyn Skriv om regler om du vill ange regler för crawlning och sökning av URL:er och titlar.

## Om URL-regler för crawllistans lager {#concept_B71CF4C8030A4A74A22C3BFE4DE3B865}

URL-regler för crawlning anger hur de URL:er som upptäcks i webbinnehållet skrivs om. Du kan ange ett obegränsat antal regler och villkor, och du kan ändra vilken del som helst av de URL-adresser som påträffas.

<!-- 

c_about_crawl_list_store_url_rules.xml

 -->

Crawlningsregler är mest användbara när du vill skriva om dynamiska delar av en URL, till exempel en sessionsidentifierare som är unik för varje kund som besöker webbplatsen. Du kan också använda omskrivningsregler för att dölja delar av en URL, t.ex. frågeparametrar, från sökroboten. Som standard har inga regler angetts och ingen URL-omskrivning utförs.

När en webbplats crawlas lagras inbäddade innehålls-URL:er i en tillfällig lista över ytterligare webbsidor som ska crawlas. Innan en URL läggs till i den här listan används reglerna för omskrivning av arkiv på den. Normalt används regler för att ta bort ett sessions-ID från en URL eller för att framtvinga ett särskilt sessions-ID för crawlning. När sökroboten hämtar en URL från listan används reglerna för att hämta omskrivning för att manipulera delar av den URL:en igen. Hämtningsreglerna används vanligtvis för att infoga tidskänsliga data i URL:en. Det är den slutliga URL-adressen som används för att hämta sidan från din webbplats.

Se [Om Hämta URL-regler för crawllista](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA).

Vanligtvis använder du enbart Lagra URL-regler. Hämta URL-regler är bara nödvändigt om URL-adresser innehåller dynamiska data, som ett sessions-ID, och om dessa dynamiska data ändras över tid för att förbli giltiga. I det här fallet använder du Lagra URL-regler för att hämta det senaste tillståndet för data från de URL:er som påträffas. Sedan använder du Hämta URL-regler för att lägga till data till varje URL när sökroboten försöker hämta sidan.

Varje regel anges med ett omskrivningsregeldirektiv (RewriteRule) och ett eller flera valfria omskrivningsvillkor (RewriteCond). Ordningen på reglerna är viktig. Regeluppsättningen upprepas regel för regel. När en regel matchar, körs en slinga genom alla motsvarande omskrivningsvillkor. En crawlnings-URL-regel anges på följande sätt:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

När en inbäddad URL påträffas försöker sökroboten matcha URL:en med mönstret för varje crawlningsregel. Om mönstret matchar söker omskrivningsmotorn efter motsvarande RewriteCond-direktiv. Om det inte finns några villkor ersätts URL-adressen med ett nytt värde som skapas från ersättningssträngen och fortsätter med nästa regel i regeluppsättningen. Om det finns villkor bearbetas de i den ordning som de listas. Omskrivningsmotorn försöker matcha ett villkorsmönster (CondPattern) mot en teststräng (TestString). Om de två matchar varandra behandlas nästa villkor tills inga fler villkor är tillgängliga. Om alla villkor matchar ersätts URL:en med det ersättningsalternativ som anges i regeln. Om villkoret inte uppfylls misslyckas hela uppsättningen villkor och motsvarande regel.

## Om RewriteRule-direktiv {#section_162122340BB34F12BB9A36DC9349092B}

Ett RewriteRule-direktiv har följande format:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` kan vara ett reguljärt POSIX-uttryck som används på den aktuella URL:en. Aktuell URL kan skilja sig från den ursprungliga begärda URL-adressen eftersom tidigare regler redan har matchat och ändrat URL-adressen.

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Du kan inte använda tecknet &quot;not&quot; (&#39;!&#39;) för att prefix till mönstret. Med tecknet&quot;inte&quot; kan du negera ett mönster, d.v.s. bara vara sant om den aktuella URL:en INTE matchar det här mönstret. Tecknet&quot;inte&quot; kan användas när det är bättre att matcha ett negativt mönster eller som en slutlig standardregel.

>[!NOTE]
>
>Du kan inte använda både&quot;inte&quot;-tecknet och grupperade jokertecken i ett mönster. Du kan inte heller använda ett negerat mönster när ersättningssträngen innehåller $N.

Du kan använda parenteser för att skapa en bakåtreferens i mönstret, som du kan referera till av Substitution och CondPattern.

**** SubstitutionURL:en ersätts av ersättningssträngen som innehåller följande:

Oformaterad text: Text som skickas oförändrad.

Med bakåtreferenser får du tillgång till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Följande två typer av bakåtreferenser:

* **RewriteRule** BackreferencesDessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0)  &lt;> Exempel: `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* **RewriteCond** BackreferencesDessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0)  &lt;>

Variabler: Detta är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE är en sträng för namnet på en definierad variabel. Mer information om hur du anger miljövariabler finns i `*[E]*`-flaggan.

Funktioner: Detta är funktioner i formatet ${NAME_OF_FUNCTION:key} där NAME_OF_FUNCTION är följande:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.
* escape URL-kodar alla tecken i *nyckel*.
* Tecknen &#39;a&#39;..&#39;z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; och &#39;_&#39; ändras inte; Blanksteg översätts till + och alla andra tecken omvandlas till sin %xx URL-kodade motsvarighet.
* unescape omformar &#39;+&#39; tillbaka till blanksteg och alla %xx URL-kodade tecken tillbaka till enskilda tecken.

>[!NOTE]
>
>Det finns en särskild ersättningssträng: `'-'` betyder&quot;INGEN ersättning&quot;. Strängen `'-'` används ofta med C-flaggan (chain), vilket gör att du kan matcha en URL till flera mönster innan en ersättning görs.

**Flaggor**

(valfritt) Omslut flaggor inom hakparenteser `[]`. Flera flaggor är kommaavgränsade.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Sista regeln. </p> <p>Stoppar skrivprocessen och tillämpar inga ytterligare skrivregler. Använd den här flaggan för att förhindra vidare bearbetning till den aktuella URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Nästa runda. </p> <p> Återkör omskrivningsprocessen (med början igen med den första omskrivningsregeln) med URL:en från den senaste omskrivningsregeln (inte den ursprungliga URL:en). Var försiktig så att du inte skapar en dödslinga! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> kedja|C </p> </td> 
   <td colname="col2"> <p>Målad med nästa regel. </p> <p>Gör om den aktuella regeln till nästa regel (som också kan kopplas till nästa regel, och så vidare). Om en regel matchar fortsätter ersättningsprocessen som vanligt. Om regeln inte matchar hoppas alla efterföljande kopplade regler över. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Inget fall. </p> <p> Gör mönstret inte skiftlägeskänsligt (det vill säga det finns ingen skillnad mellan"A-Z" och"a-z") när mönstret matchas mot den aktuella URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> skip|S=num' </p> </td> 
   <td colname="col2"> <p>Hoppa över nästa regel eller regler. </p> <p> Om den aktuella regeln matchar, tvingar den här flaggan omskrivningsmotorn att hoppa över nästa antal regler i regeluppsättningen. Använd den här flaggan för att skapa pseudo if-then-else-konstruktioner. Den sista regeln i då-satsen blir en skip=N där N är antalet regler i else-satsen. </p> <p> <p>Obs!  Den här flaggan är inte densamma som flaggan 'chain|C'!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Anger miljövariabeln. </p> <p>Skapar en miljövariabel, "VAR", som är inställd på värdet VAL, där VAL kan innehålla reguljära uttryck för bakåtreferenser, $N och %N, som färdigställs. Du kan använda den här flaggan mer än en gång för att ange flera variabler. Variablerna kan senare avrefereras i följande RewriteCond-mönster via %{VAR}. </p> <p>Använd den här flaggan för att ta bort och komma ihåg information från URL-adresser. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Variabelvärdena för Lagra omskrivningsregler och Hämta omskrivningsregler delas. På grund av detta kan du ange en variabel som ett tidskänsligt sessionid-värde när en inbäddad URL påträffas och lagras. När nästa URL hämtas från listan över tillfälliga lager kan det senaste värdet för sessionid läggas till innan sidan hämtas.

**Exempel på en RewriteRule med en funktion**

Anta att du har en skiftlägeskänslig server som hanterar strängarna `"www.mydomain.com"` och `"www.MyDomain.com"` på olika sätt. För att servern ska fungera på rätt sätt måste domänen alltid vara `"www.mydomain.com"` även om vissa dokument innehåller länkar som refererar till `"www.MyDomain.com."` För att göra detta kan du använda följande regel:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

Denna omskrivningsregel använder funktionen `tolower` för att skriva om domändelen av en URL för att säkerställa att den alltid är i gemener, som i följande:

1. Mönstret `(^https://([^/]*)(.*)$)` innehåller en bakåtreferens `([^/]*)` som matchar alla tecken mellan `https://` och den första `/` i URL:en. Mönstret innehåller också en andra bakåtreferens `(.*)` som matchar alla återstående tecken i URL:en.

1. Ersättningen `(https://${tolower:$1}$2)` anger för sökmotorn att skriva om URL:en med funktionen `tolower` på den första bakåtreferensen `(https:// ${tolower:$1}$2)` och lämna resten av URL:en orörd `(https://${tolower:$1} $2)`.

Därför skrivs en URL-adress i formatet `https://www.MyDomain.com/INTRO/index.Html` om som `https://www.mydomain.com/INTRO/index.Html`.

## Om RewriteCond-direktiv {#section_CD5A19B2D3204F73B645411931FC34A1}

Direktivet RewriteCond definierar ett regelvillkor. När en RewriteCond föregår en RewriteRule används regeln bara om dess mönster matchar den aktuella titeln och de ytterligare villkoren gäller. Omskrivningsvillkoren har följande format:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` är en sträng som kan innehålla följande konstruktioner:

Oformaterad text: Text som skickas oförändrad.

Med bakåtreferenser får du tillgång till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Följande två typer av bakåtreferenser:

* **RewriteRule** BackreferencesDessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0)  &lt;> Exempel, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`.

* **RewriteCond** BackreferencesDessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0)&lt;>

Variabler: Detta är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE kan vara en sträng för namnet på en definierad variabel. Mer information om hur du anger variabler finns i RewriteRule-flaggan *`[E]`*.

Funktioner: Detta är funktioner i formatet ${NAME_OF_FUNCTION:key} där NAME_OF_FUNCTION är följande:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.
* escape URL-kodar alla tecken i nyckeln. Tecknen &#39;a&#39;..&#39;z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; och &#39;_&#39; ändras inte, blanksteg översätts till &#39;+&#39; och alla andra tecken omvandlas till sin `%xx` URL-kodade motsvarighet.
* unescape omformar &#39;+&#39; tillbaka till blanksteg och alla `%xx` URL-kodningstecken tillbaka till enskilda tecken.

**** CondPattern är ett utökat reguljärt standarduttryck med några tillägg. Mönstersträngen kan prefixeras med ett `!`-tecken (utropstecken) för att ange ett icke-matchande mönster. I stället för riktiga strängar för reguljära uttryck kan du använda någon av följande specialvarianter:

>[!NOTE]
>
>Du kan även prefix för alla dessa tester med ett utropstecken (!) för att förneka deras betydelse.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-sträng </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexiskt mindre. </p> <p> Hanterar CondPattern som en oformaterad sträng och jämför den lexibelt med TestString. True if TestString is lexically less than CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexiskt större. </p> <p> Hanterar CondPattern som en oformaterad sträng och jämför den lexibelt med TestString. True if TestString is lexically greater than CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lika med. </p> <p> Hanterar CondPattern som en oformaterad sträng och jämför den lexibelt med TestString. True if TestString is lexically equal to CondPattern, d.v.s., the two strings are exact (character by character). Om CondPattern bara är "" (två citattecken) jämförs TestString med den tomma strängen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flaggor**
 (valfritt) Omslut flaggor inom hakparenteser  `[]`. Flera flaggor är kommaavgränsade.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Inget fall. </p> <p>Den här flaggan gör testet inte skiftlägeskänsligt, vilket innebär att det inte finns någon skillnad mellan"A-Z" och"a-z" både i den expanderade TestString och i CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>Eller nästa villkor. </p> <p>Använd den här flaggan för att kombinera regelvillkor med ett lokalt OR i stället för det implicita AND-uttrycket. Utan den här flaggan måste du skriva cond/rule flera gånger. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempel**

Vissa webbsidor tilldelar en CGI-variabel för sessionid första gången en besökare kommer till en webbplats. Variabeln används för att identifiera besökaren och variabeln skickas när besökaren bläddrar genom webbplatsen. Eftersom sökroboten ser ut som en besökare på webbplatsen tilldelas den ett sessionid-nummer. Sökroboten behåller det här enda värdet för sessionid, även om en andra webbplatssida försöker tilldela ett nytt värde. För att säkerställa detta behöver du två regler för omskrivning.

Den första regeln används för att identifiera och lagra sessionid-variabeln:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule använder en E-flagga `([E=sessionid:$1])` för att tilldela det aktuella värdet för sessionid-parametern CGI till variabeln `sessionid`. `$1` refererar till den första bakåtreferensen, som finns mellan den första uppsättningen parenteser i RewriteRule-mönstret `([^&#]+)`.

Det reguljära uttrycket `^&#]+` matchar delen av en URL mellan ordet `sessionid` och nästa `**&**or**#**`-tecken. Eftersom RewriteRule endast används för att skapa det ursprungliga värdet för sessionid-variabeln skrivs det inte om. Observera att regelns ersättningsfält är inställt på `-` för att ange att ingen omskrivning krävs.

RewriteCond undersöker variabeln `sessionid` ( `%{sessionid}`). Om den inte har ett enda tecken (!.).+) matchar RewriteRule.

Med den här regeln läses URL:en som `https://www.domain.com/home/?sessionid=1234&function=start` och tilldelar värdet `1234` till variabeln `sessionid`.

Den andra regeln används för att skriva om alla URL:er som matchar följande RewriteRule-mönster:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

RewriteRule-mönstret innehåller två bakåtreferenser: `(.+)` och `(.*)`. Den första bakåtreferensen matchar alla tecken före `sessionid`. Den andra bakåtreferensen matchar alla tecken efter avslutandet `&` eller `#`.

Ersättningsmönstret skriver om URL:en med den första bakåtreferensen, följt av strängen &quot;sessionid=&quot;, följt av värdet på den sessions-ID-variabel som definieras av den första regeln `%{sessionid}`, följt av den andra bakåtreferensen. `($1sessionid=%{sessionid} $2)`

Observera att RewriteRule inte innehåller en RewriteCond. Därför skapas en omskrivning för alla URL:er som matchar RewriteRule *Pattern*. Om värdet för sessionid-variabeln ( `%{sessionid}`) är `1234` skrivs en URL i formatet `https://www.domain.com/products/?sessionid=5678&function=buy` om som `https://www.domain.com/products/?sessionid=1234&function=buy`

## Bekräftelse {#section_B17088EF38244496BC1DDD4ECF75EB5B}

Programvaran för omskrivningsmotorn utvecklades ursprungligen av Apache Group för användning i Apache HTTP-serverprojektet (https://www.apache.org/).

## Lägger till en URL-regel för crawllistans arkiv {#task_22DD40DF95584B12BE8E6ECFBF579BCD}

Du kan lägga till URL-regler för crawllistearkiv för att ange hur URL:er som påträffas i webbinnehållet ska skrivas om. Du kan ange ett obegränsat antal regler och villkor, och du kan ändra vilken del som helst av de URL-adresser som påträffas.

<!-- 

t_adding_a_crawl_list_store_url_rule.xml

 -->

**Lägga till URL-regler för crawllistans arkiv**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Store URL Rules]** på produktmenyn.
1. I fältet [!DNL Crawl List Store URL Rules] anger du de regler du vill använda.

   Tomma rader och kommentarsrader som börjar med tecknet &#39;#&#39; (hash) tillåts.
1. (Valfritt) På sidan [!DNL Crawl List Store URL Rules] anger du en test-URL vars crawlningsregler du vill testa i fältet [!DNL Test Crawl List Store URL Rules] och klickar sedan på **Testa**.
1. Klicka på **Spara ändringar**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Crawl List Store URL Rules]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om Hämta URL-regler för crawlningslista {#concept_EC8E2E48B99A458D8567B526C9827CBA}

URL-regler för crawlning anger hur URL:er som påträffas i webbinnehåll skrivs om. Du kan ange ett obegränsat antal regler och villkor, och du kan ändra vilken del som helst av de URL-adresser som påträffas.

<!-- 

c_about_crawl_list_retrieve_url_rules.xml

 -->

Innan effekterna av reglerna är synliga för kunderna måste du återskapa webbplatsindexet.

Crawlningsregler är mest användbara när du vill skriva om dynamiska delar av en URL, till exempel en sessionsidentifierare som är unik för varje kund som besöker webbplatsen. Du kan också använda omskrivningsregler för att dölja delar av en URL, t.ex. frågeparametrar, från sökroboten. Som standard har inga regler angetts och ingen URL-omskrivning utförs.

När en webbplats crawlas lagras inbäddade innehålls-URL:er i en tillfällig lista över ytterligare webbsidor som ska crawlas. När sökroboten hämtar en URL-adress från listan används Hämta regler för att ändra delar av den URL-adressen. Hämtningsreglerna används vanligtvis för att infoga tidskänsliga data i en URL. Det är den slutliga URL-adressen som används för att hämta sidan från din webbplats.

Hämta skrivregler är bara nödvändigt om URL:er innehåller dynamiska data, som ett sessions-ID, och om dessa dynamiska data ändras över tid för att förbli giltiga. I det här fallet använder du Skriv om regler för att hämta det senaste tillståndet för data från de URL:er som påträffas. Sedan använder du Retrieve Rewrite Rules för att lägga till dessa data till varje URL när sökroboterna hämtar sidan.

Varje regel anges med ett omskrivningsregeldirektiv (RewriteRule) och ett eller flera valfria omskrivningsvillkor (RewriteCond). Ordningen på reglerna är viktig. Regeluppsättningen upprepas regel för regel. När en regel matchar, körs en slinga genom alla motsvarande omskrivningsvillkor. En crawlnings-URL-regel anges på följande sätt:

```
RewriteCond TestString CondPattern [Flags] 
RewriteRule Pattern Substitution [Flags]
```

När en inbäddad URL påträffas försöker sökroboten matcha URL:en med mönstret för varje crawlningsregel. Om mönstret matchar söker omskrivningsmotorn efter motsvarande RewriteCond-direktiv. Om det inte finns några villkor ersätts URL-adressen med ett nytt värde som skapas från ersättningssträngen och fortsätter med nästa regel i regeluppsättningen. Om det finns villkor bearbetas de i den ordning som de listas. Omskrivningsmotorn försöker matcha ett villkorsmönster (CondPattern) mot en teststräng (TestString). Om de två matchar varandra behandlas nästa villkor tills inga fler villkor är tillgängliga. Om alla villkor matchar ersätts URL:en med det ersättningsalternativ som anges i regeln. Om villkoret inte uppfylls misslyckas hela uppsättningen villkor och motsvarande regel.

## Om RewriteRule-direktiv {#section_32B24B29627946398AFBC5F869A610CB}

Ett RewriteRule-direktiv har följande format:

```
           
<i>RewriteRule Pattern Substitution [Flags]</i> 
        
```

`Pattern` kan vara ett reguljärt POSIX-uttryck som används på den aktuella URL:en. Aktuell URL kan skilja sig från den ursprungliga begärda URL-adressen eftersom tidigare regler redan har matchat och ändrat URL-adressen.

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Du kan inte använda tecknet &quot;not&quot; (&#39;!&#39;) för att prefix till mönstret. Med tecknet&quot;inte&quot; kan du negera ett mönster, d.v.s. bara vara sant om den aktuella URL:en INTE matchar det här mönstret. Tecknet&quot;inte&quot; kan användas när det är bättre att matcha ett negativt mönster eller som en slutlig standardregel.

>[!NOTE]
>
>Du kan inte använda både&quot;inte&quot;-tecknet och grupperade jokertecken i ett mönster. Du kan inte heller använda ett negerat mönster när ersättningssträngen innehåller $N.

Du kan använda parenteser för att skapa en bakåtreferens i mönstret, som du kan referera till av Substitution och CondPattern.

**** SubstitutionURL:en ersätts av ersättningssträngen som innehåller följande:

Oformaterad text: Text som skickas oförändrad.

Med bakåtreferenser får du tillgång till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Följande två typer av bakåtreferenser:

* **RewriteRule** BackreferencesDessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0)  &lt;> Exempel: `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2.`

* ** RewriteCond Backreferences** Dessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0 &lt;= N &lt;= 9).

Variabler: Detta är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE är en sträng för namnet på en definierad variabel. Mer information om hur du anger miljövariabler finns i *[E]*-flaggan.

Funktioner: Detta är funktioner i formatet ${NAME_OF_FUNCTION:key} där NAME_OF_FUNCTION är följande:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.
* escape URL-kodar alla tecken i *nyckel*.
* Tecknen &#39;a&#39;..&#39;z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; och &#39;_&#39; ändras inte; Blanksteg översätts till + och alla andra tecken omvandlas till sin %xx URL-kodade motsvarighet.
* unescape omformar &#39;+&#39; tillbaka till blanksteg och alla %xx URL-kodade tecken tillbaka till enskilda tecken.

>[!NOTE]
>
>Det finns en särskild ersättningssträng: &#39;-&#39; betyder &quot;INGEN substitution&quot;. Strängen &#39;-&#39; används ofta med C-flaggan (chain), vilket gör att du kan matcha en URL till flera mönster innan en ersättning görs.

**Flaggor**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Sista regeln. </p> <p>Stoppar skrivprocessen och tillämpar inga ytterligare skrivregler. Använd den här flaggan för att förhindra vidare bearbetning till den aktuella URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Nästa runda. </p> <p> Återkör omskrivningsprocessen (med början igen med den första omskrivningsregeln) med URL:en från den senaste omskrivningsregeln (inte den ursprungliga URL:en). Var försiktig så att du inte skapar en dödslinga. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> kedja|C </p> </td> 
   <td colname="col2"> <p>Målad med nästa regel. </p> <p>Gör om den aktuella regeln till nästa regel (som också kan kopplas till nästa regel, och så vidare). Om en regel matchar fortsätter ersättningsprocessen som vanligt. Om regeln inte matchar hoppas alla efterföljande kopplade regler över. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Inget fall. </p> <p> Gör mönstret inte skiftlägeskänsligt (det vill säga det finns ingen skillnad mellan"A-Z" och"a-z") när mönstret matchas mot den aktuella URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> skip|S=num' </p> </td> 
   <td colname="col2"> <p>Hoppa över nästa regel eller regler. </p> <p> Om den aktuella regeln matchar, tvingar den här flaggan omskrivningsmotorn att hoppa över nästa antal regler i regeluppsättningen. Använd den här flaggan för att skapa pseudo if-then-else-konstruktioner. Den sista regeln i då-satsen blir en skip=N där N är antalet regler i else-satsen. </p> <p> <p>Obs!  Den här flaggan är inte densamma som flaggan 'chain|C'!) </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Anger miljövariabeln. </p> <p>Skapar en miljövariabel, "VAR", som är inställd på värdet VAL, där VAL kan innehålla reguljära uttryck för bakåtreferenser, $N och %N, som färdigställs. Du kan använda den här flaggan mer än en gång för att ange flera variabler. Variablerna kan senare avrefereras i följande RewriteCond-mönster via %{VAR}. </p> <p>Använd den här flaggan för att ta bort och komma ihåg information från URL-adresser. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Variabelvärdena för Lagra omskrivningsregler och Hämta omskrivningsregler delas. På grund av detta kan du ange en variabel som ett tidskänsligt sessionid-värde när en inbäddad URL påträffas och lagras. När nästa URL hämtas från listan över tillfälliga lager kan det senaste värdet för sessionid läggas till innan sidan hämtas.

**Exempel på en RewriteRule med en funktion**

Anta att du har en skiftlägeskänslig server som hanterar strängarna &quot;www.mydomain.com&quot; och &quot;www.MyDomain.com&quot; på ett annat sätt. För att servern ska fungera på rätt sätt måste domänen alltid vara&quot;www.mydomain.com&quot; även om vissa dokument innehåller länkar som refererar till&quot;www.MyDomain.com&quot;. Du kan göra detta med följande regel:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2
```

Denna omskrivningsregel använder funktionen `tolower` för att skriva om domändelen av en URL för att säkerställa att den alltid är i gemener, som i följande:

1. Mönstret `(^https://([^/]*)(.*)$)` innehåller en bakåtreferens ** `([^/]*)`** som matchar alla tecken mellan `https://` och den första `/` i URL:en. Mönstret innehåller också en andra bakåtreferens `(.*)` som matchar alla återstående tecken i URL:en.
1. Ersättningen `(https://${tolower:$1}$2)` anger för sökmotorn att skriva om URL:en med funktionen `tolower` på den första bakåtreferensen `(https:// ${tolower:$1}$2)` och lämna resten av URL:en orörd `(https://${tolower:$1} $2)`.

Därför skrivs en URL-adress i formatet `https://www.MyDomain.com/INTRO/index.Html` om som `https://www.mydomain.com/INTRO/index.Html`.

## Om RewriteCond-direktiv {#section_ADD642A24B68452CB98294A0BD687EC3}

Direktivet RewriteCond definierar ett regelvillkor. När en RewriteCond föregår en RewriteRule används regeln bara om dess mönster matchar den aktuella titeln och de ytterligare villkoren gäller. Omskrivningsvillkoren har följande format:

```
           
<i>RewriteCond TestString CondPattern [Flags]</i> 
        
```

`TestString` är en sträng som kan innehålla följande konstruktioner:

Oformaterad text: Text som skickas oförändrad.

Med bakåtreferenser får du tillgång till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Följande två typer av bakåtreferenser:

* **RewriteRule** BackreferencesDessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0)  &lt;> Exempel, `RewriteRule ^https:// ([^/]*) (.*)$ https://${tolower: $1} $2`.

* **RewriteCond** BackreferencesDessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0)&lt;>

Variabler: Detta är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE kan vara en sträng för namnet på en definierad variabel. Mer information om hur du anger variabler finns i RewriteRule-flaggan *`[E]`*.

Funktioner: Detta är funktioner i formatet ${NAME_OF_FUNCTION:key} där NAME_OF_FUNCTION är följande:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.
* escape URL-kodar alla tecken i nyckeln. Tecknen &#39;a&#39;..&#39;z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; och &#39;_&#39; ändras inte, blanksteg översätts till &#39;+&#39; och alla andra tecken omvandlas till sin %xx URL-kodade motsvarighet.
* unescape omformar &#39;+&#39; tillbaka till blanksteg och alla %xx URL-kodningstecken tillbaka till enskilda tecken.

**** CondPattern är ett utökat reguljärt standarduttryck med några tillägg. Mönstersträngen kan prefixeras med &#39;!&#39; (utropstecken) om du vill ange ett mönster som inte matchar. I stället för riktiga strängar för reguljära uttryck kan du använda någon av följande specialvarianter:

>[!NOTE]
>
>Du kan även prefix för alla dessa tester med ett utropstecken (!) för att förneka deras betydelse.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-sträng </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexiskt mindre. </p> <p> Hanterar CondPattern som en oformaterad sträng och jämför den lexibelt med TestString. True if TestString is lexically less than CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Lexiskt större. </p> <p> Hanterar CondPattern som en oformaterad sträng och jämför den lexibelt med TestString. True if TestString is lexically greater than CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Lika med. </p> <p> Hanterar CondPattern som en oformaterad sträng och jämför den lexibelt med TestString. True if TestString is lexically equal to CondPattern, d.v.s., the two strings are exact (character by character). Om CondPattern bara är "" (två citattecken) jämförs TestString med den tomma strängen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flaggor**
 (valfritt) Omslut flaggor inom hakparenteser  `[]`. Flera flaggor är kommaavgränsade.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Inget fall. </p> <p>Den här flaggan gör testet inte skiftlägeskänsligt, vilket innebär att det inte finns någon skillnad mellan"A-Z" och"a-z" både i den expanderade TestString och i CondPattern. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p>Eller nästa villkor. </p> <p>Använd den här flaggan för att kombinera regelvillkor med ett lokalt OR i stället för det implicita AND-uttrycket. Utan den här flaggan måste du skriva cond/rule flera gånger. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempel**

Vissa webbsidor tilldelar en CGI-variabel för sessionid första gången en besökare kommer till en webbplats. Variabeln används för att identifiera besökaren och variabeln skickas när besökaren bläddrar genom webbplatsen. Eftersom sökroboten ser ut som en besökare på webbplatsen tilldelas den ett sessionid-nummer. Sökroboten behåller det här enda värdet för sessionid, även om en andra webbplatssida försöker tilldela ett nytt värde. För att säkerställa detta behöver du två regler för omskrivning.

Den första regeln används för att identifiera och lagra sessionid-variabeln:

```
RewriteCond  %{sessionid}  !.+ 
RewriteRule  ^.+sessionid= 
<b>([^&#]+)</b>.*$  -   
<i>[E=sessionid:$1]</i>
```

RewriteRule använder en E-flagga `([E=sessionid:$1])` för att tilldela det aktuella värdet för sessionid-parametern CGI till variabeln `sessionid`. `$1` refererar till den första bakåtreferensen, som finns mellan den första uppsättningen parenteser i RewriteRule-mönstret `([^&#]+)`.

Det reguljära uttrycket `^&#]+` matchar delen av en URL mellan ordet `sessionid` och nästa**&amp;**eller**#**tecken. Eftersom RewriteRule endast används för att skapa det ursprungliga värdet för sessionid-variabeln skrivs det inte om. Observera att regelns ersättningsfält är inställt på `-` för att ange att ingen omskrivning krävs.

RewriteCond undersöker variabeln `sessionid` ( `%{sessionid}`). Om den inte har ett enda tecken (!.).+) matchar RewriteRule.

Med den här regeln läses URL:en som `https://www.domain.com/home/?sessionid=1234&function=start` och tilldelar värdet `1234` till variabeln `sessionid`.

Den andra regeln används för att skriva om alla URL:er som matchar följande RewriteRule-mönster:

```
RewriteRule   
<b>^(.+)</b>sessionid=[^&#]+ 
<i>(.*)$</i>  $1sessionid=%{sessionid}$2
```

RewriteRule-mönstret innehåller två bakåtreferenser: `(.+)` och `(.*)`. Den första bakåtreferensen matchar alla tecken före `sessionid`. Den andra bakåtreferensen matchar alla tecken efter avslutandet `&` eller `#`.

Ersättningsmönstret skriver om URL:en med den första bakåtreferensen, följt av strängen &quot;sessionid=&quot;, följt av värdet på den sessions-ID-variabel som definieras av den första regeln `%{sessionid}`, följt av den andra bakåtreferensen. `($1sessionid=%{sessionid} $2)`

Observera att RewriteRule inte innehåller en RewriteCond. Därför skapas en omskrivning för alla URL:er som matchar RewriteRule *Pattern*. Om värdet för sessionid-variabeln ( `%{sessionid}`) är `1234` skrivs en URL i formatet `https://www.domain.com/products/?sessionid=5678&function=buy` om som `https://www.domain.com/products/?sessionid=1234&function=buy`

## Bekräftelse {#section_EC3A1DAEB5A54C93A265CB119DF91E9F}

Programvaran för omskrivningsmotorn utvecklades ursprungligen av Apache Group för användning i Apache HTTP-serverprojektet (https://www.apache.org/).

## Lägger till crawlningslista hämtar URL-regler {#task_94A28ED7DC404BFF9767DBB5ADEE6B7A}

Du kan lägga till regler för hämtning av crawlningslistor för att ange hur påträffade URL:er i webbinnehållet ska skrivas om. Hämta regler för att skriva över är bara nödvändigt om URL-adresserna innehåller dynamiska data, till exempel ett sessions-ID, och om dessa dynamiska data ändras över tid för att förbli giltiga.

<!-- 

t_adding_crawl_list_retrieve_url_rules.xml

 -->

**Hämta URL-regler för att lägga till crawlningslista**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]** på produktmenyn.
1. I fältet [!DNL Crawl List Retrieve URL Rules] anger du de regler du vill använda.

   Tomma rader och kommentarsrader som börjar med tecknet &#39;#&#39; (hash) tillåts.
1. (Valfritt) På sidan [!DNL Crawl List Retrieve URL Rules] anger du en test-URL vars crawlningsregler du vill testa i fältet [!DNL Test Crawl List Retrieve URL Rules] och klickar sedan på **Testa**.
1. Klicka på **Spara ändringar**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Crawl List Retrieve URL Rules]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om regler för crawlningsrubrik {#concept_BD3A576987DA4D93A998B0B9CDDC3C79}

Regler för kryptext anger hur påträffade titlar i webbinnehåll skrivs om innan de lagras i sökindexet.

<!-- 

c_about_crawl_title_rules.xml

 -->

Du kan till exempel använda en omskrivningsregel för att ta bort en del av en titel, till exempel ett organisationsnamn. När en webbplats crawlas lagras påträffade titlar i en tillfällig buffert. Innan en titel läggs till i bufferten tillämpas dock reglerna för titeln på den. Som standard har webbplatssökning/-marknadsföring inga regler för kryptext och inga titeländringar görs.

Innan effekterna av reglerna är synliga för kunderna bör du återskapa webbplatsindexet.

Du kan snabbt återställa ändringar som du gör i reglerna för kryptext med hjälp av funktionen Historik.

Regler kan bestå av två huvudelement: RewriteRule och den valfria RewriteCond. Du kan ange ett obegränsat antal regler och villkor. Ordningen på dessa regler är viktig eftersom regeluppsättningen slingras genom regel. När en regel matchar upprepas alla (valfria) motsvarande omskrivningsvillkor. Regler för crawlnings-URL anges på följande sätt:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

När en titel påträffas försöker sökroboten matcha titeln mot mönstret för varje crawlningsregel. Om mönstret matchar söker omskrivningsmotorn efter motsvarande RewriteCond-direktiv. Om det inte finns några villkor ersätts URL-adressen med ett nytt värde som skapas från ersättningssträngen och fortsätter med nästa regel i regeluppsättningen. Om det finns villkor bearbetas de i den ordning som de listas. Omskrivningsmotorn försöker matcha ett villkorsmönster (CondPattern) mot en teststräng (TestString). Om de två matchar varandra behandlas nästa villkor tills inga fler villkor är tillgängliga. Om alla villkor matchar ersätts URL:en med det ersättningsalternativ som anges i regeln. Om villkoret inte uppfylls misslyckas hela uppsättningen villkor och motsvarande regel.

Ange reglerna för crawlnings-URL i textrutan och klicka sedan på Spara ändringar. Tomma rader och kommentarsrader som börjar med tecknet &#39;#&#39; (hash) tillåts. Om du vill testa sökreglerna anger du en test-URL i textrutan Test Rewrite Rules (Testa omskrivningsregler) och klickar sedan på Test (Testa).

## Direktivet RewriteRule {#section_669445C505754E838E14029D6583D9B6}

Varje RewriteRule-direktiv definierar en återskrivningsregel. Reglerna tillämpas i den ordning som de anges. En omskrivningsregel har följande format:

```
RewriteRule Pattern Substitution [Flags]
```

**Mönstret** kan vara ett reguljärt POSIX-uttryck som används i den aktuella titeln. &quot;Aktuell titel&quot; skiljer sig från den ursprungliga titeln eftersom tidigare regler redan har matchat och ändrat den.

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Du kan använda&quot;inte&quot;-tecknet (&#39;!&#39;) för att prefix till mönstret. Tecknet&quot;inte&quot; gör att du kan negera ett mönster, d.v.s. bara vara sant om den aktuella titeln INTE matchar mönstret. Tecknet&quot;inte&quot; kan användas när det är bättre att matcha ett negativt mönster eller som en slutlig standardregel. Obs! Du kan inte använda både&quot;inte&quot;-tecknet och grupperade jokertecken i ett mönster. Du kan inte heller använda ett negerat mönster när ersättningssträngen innehåller $N.

Du kan använda parenteser för att skapa en bakåtreferens som kan refereras av Substitution och CondPattern.

**** ErsättningTiteln ersätts av ersättningssträngen. Strängen kan innehålla följande:

Oformaterad text - Text som skickas oförändrad.

Med bakåtreferenser får du tillgång till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Följande är två typer av bakåtreferenser:

* Backreferences för RewriteRule

   Dessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0 &lt;= N &lt;= 9). Exempel: `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond Backreferences

   Dessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0 &lt;= N &lt;= 9).

Variabler Det här är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE kan vara en sträng för namnet på en definierad variabel. Mer information om hur du anger miljövariabler finns i `[E]`-flaggan.

Funktioner som är funktioner i formatet ${NAME_OF_FUNCTION: nyckel} där NAME_OF_FUNCTION är:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.

>[!NOTE]
>
>Det finns en särskild ersättningssträng: &#39;-&#39; betyder &quot;INGEN substitution&quot;. Strängen &#39;-&#39; är ofta användbar med C-flaggan (chain) så att du kan matcha en titel mot flera mönster innan en ersättning görs.

**Flaggor**  (valfritt)

Flaggor omsluts av hakparenteser `[]`och flera flaggor är kommaavgränsade:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Sista regeln. </p> <p> Stoppar omskrivningsprocessen och tillämpar inga ytterligare omskrivningsregler. Använd den här flaggan för att förhindra vidare bearbetning till den aktuella titeln. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Nästa runda. </p> <p> Återkör omskrivningsprocessen (med början igen med den första omskrivningsregeln) med titeln från den senaste omskrivningsregeln, inte den ursprungliga titeln. Var försiktig så att du inte skapar en död slinga. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> kedja|C </p> </td> 
   <td colname="col2"> <p>Målad med nästa regel. </p> <p>Gör om den aktuella regeln till nästa regel (som också kan kopplas till nästa regel, och så vidare). Om en regel matchar fortsätter ersättningsprocessen som vanligt. Om regeln inte matchar hoppas alla efterföljande kopplade regler över. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Inget fall. </p> <p>Gör mönstret inte skiftlägeskänsligt (det vill säga det finns ingen skillnad mellan"A-Z" och"a-z") när mönstret matchas mot den aktuella titeln. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> skip|S=num' </p> </td> 
   <td colname="col2"> <p>Hoppa över nästa regel eller regler. </p> <p> Om den aktuella regeln matchar, tvingar den här flaggan omskrivningsmotorn att hoppa över nästa antal regler i regeluppsättningen. Använd det här om du vill skapa pseudo if-then-else-konstruktioner. Den sista regeln i då-satsen blir en skip=N där N är antalet regler i else-satsen. (Obs! Detta är inte detsamma som flaggan 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Ange miljövariabel. </p> <p> Skapar en miljövariabel, "VAR", som är inställd på värdet VAL, där VAL kan innehålla reguljära uttryck för bakåtreferenser, $N och %N, som färdigställs. Du kan använda den här flaggan mer än en gång för att ange flera variabler. Variablerna kan senare refereras i följande RewriteCond-mönster via %{VAR}. Använd den här flaggan för att ta bort och komma ihåg information från titlar. </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond-direktivet (valfritt) {#section_D664B71DE3884E0790531804C49A3222}

Direktivet RewriteCond definierar ett regelvillkor. När en RewriteCond föregår en RewriteRule används regeln bara om dess mönster matchar den aktuella titeln och de ytterligare villkoren gäller.

Omskrivningsvillkorsdirektiv har följande format:

```
RewriteCond TestString CondPattern [Flags] 
```

**** TestStringis a string that can contain the following constructs:

Oformaterad text - Text som skickas oförändrad.

Med bakåtreferenser får du tillgång till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Det finns två typer av bakåtreferenser:

* RewriteRule Backreferences Dessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0 &lt;= N &lt;= 9). Exempel: `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`
* RewriteCond Backreferences Dessa matchar bakåtreferenser i det senast matchade RewriteCond CondPattern och har formatet %N (0 &lt;= N &lt;= 9).

Variabler Det här är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE kan vara en sträng för namnet på en definierad variabel. Mer information om hur du anger miljövariabler finns i `[E]`-flaggan.

Funktioner som är funktioner i formatet ${NAME_OF_FUNCTION:key} där NAME_OF_FUNCTION är:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.
* escape URL-kodar alla tecken i nyckeln.
* Tecknen &#39;a&#39;..&#39;z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; och &#39;_&#39; ändras inte, blanksteg översätts till &#39;+&#39; och alla andra tecken omvandlas till sin %xx URL-kodade motsvarighet.
* unescape omformar &#39;+&#39; tillbaka till blanksteg och alla %xx URL-kodade tecken tillbaka till enskilda tecken.

**** CondPattern är ett utökat reguljärt standarduttryck med några tillägg. Mönstersträngen kan prefixeras med &#39;!&#39; (utropstecken) om du vill ange ett mönster som inte matchar. I stället för riktiga strängar för reguljära uttryck kan du använda någon av följande specialvarianter.

>[!NOTE]
>
>Du kan använda ett utropstecken (!) som prefix för alla dessa tester. för att förneka deras betydelse.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-sträng </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Är inte lexikaliskt. </p> <p>Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically less than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Är mycket större än någonsin. </p> <p>Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically greater greater than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p> Är lika i alla lektioner. </p> <p>Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically equal equal to <i>CondPattern</i>, d.v.s., the two strings are exact (character by character). Om <i>CondPattern</i> bara är "" (två citattecken) jämför detta <i>TestString</i> med den tomma strängen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flaggor**  (valfritt)

Flaggor omsluts av hakparenteser `[]`och flera flaggor är kommaavgränsade:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Inget fall. </p> <p> Gör testet okänsligt. Det betyder att det inte finns någon skillnad mellan"A-Z" och"a-z" både i den expanderade <i>TestString</i> och i <i>CondPattern.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'ornext|OR' </p> </td> 
   <td colname="col2"> <p> Eller nästa villkor. </p> <p>Använd den här flaggan för att kombinera regelvillkor med ett lokalt OR i stället för det implicita AND-uttrycket. Utan den här flaggan måste du skriva cond/rule flera gånger. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempel**

Anta att du har en företagswebbplats med ett standardformat: &quot;Mitt företag&quot; följt av ett bindestreck och sedan en sidspecifik beskrivning (&quot;Mitt företag - Välkommen&quot; eller&quot;Mitt företag - nyheter&quot;, till exempel). Du vill ta bort&quot;Mitt företag -&quot; från titeln och konvertera hela titeln till versaler när webbplatsen indexeras.

I följande omskrivningsregel används funktionspekaren för att endast skriva om den beskrivande delen av en titel till versaler:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>}
```

Regelns mönster `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` innehåller en bakåtreferens `(.*)` som matchar titelinnehållet som följer &quot;Mitt företag-&quot;. Tänk på att om du omger en del av ett mönster med parentes ( ) skapas en bakåtreferens som kan refereras av Ersättning. I det här exemplet skriver Ersättning (${toupper:**$1**}) om den bakåtreferensen (**$1**) med hjälp av pekarfunktionen.

Därför skrivs texten&quot;My Company - Welcome&quot; om till&quot;WELCOME&quot;.

**Bekräftelse**

Programvaran för omskrivningsmotorn utvecklades ursprungligen av Apache Group för användning i Apache HTTP-serverprojektet (https://www.apache.org/).

## Lägger till regler för crawlningsrubrik {#task_272BB4C603BA4C9ABDBEEB398798B101}

Du kan lägga till regler för kryptext för att ange hur påträffade titlar i webbinnehållet ska skrivas om innan de lagras i sökindexet.

<!-- 

t_adding_crawl_title_rules.xml

 -->

**Lägga till regler för crawlningsrubrik**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl Title Rules]** på produktmenyn.
1. I fältet [!DNL Crawl Title Rules] anger du de regler du vill använda.

   Tomma rader och kommentarsrader som börjar med tecknet &#39;#&#39; (hash) tillåts.
1. (Valfritt) På sidan [!DNL Crawl Title Rules] anger du en test-URL vars sökregler du vill testa i fältet [!DNL Test Crawl Title Rules] och klickar sedan på **Testa**.
1. Klicka på **Spara ändringar**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Crawl Title Rules]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om URL-regler för sökning {#concept_017EC95E68844B6C8CC9F874F0EC8D3C}

URL-regler för sökning anger hur URL:erna i sökresultaten för din webbplats ska visas. Reglerna fungerar på fullständiga URL:er. Alla delar av URL:en kan ändras, inklusive frågeargument där sessions-ID-information ofta behålls.

<!-- 

c_about_search_url_rules.xml

 -->

Vanligtvis används URL-regler för sökning för att infoga ett sessions-ID i en URL. Du kan dock även använda sök-URL-regler för att ändra det domännamn som visas med dina resultat. Som standard har inga regler angetts och inga URL-ändringar utförs.

URL-regler för sökning kan bestå av två huvudelement: RewriteRule och den valfria RewriteCond. När en URL inkluderas som en del av ett sökresultat, används reglerna för att ändra den. Du kan ange ett obegränsat antal regler och villkor för sökURL. Ordningen på dessa regler är viktig eftersom regeluppsättningen upprepas regel för regel. När en regel matchar körs en slinga genom alla (valfria) motsvarande omskrivningsvillkor. Regler för crawlnings-URL anges på följande sätt:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

När en URL bearbetas försöker webbplatssökningen/försäljningen matcha den med mönstret för varje sökregel. Om matchningen misslyckas avbryter omskrivningsmotorn omedelbart bearbetningen av regeln och fortsätter med nästa regel i uppsättningen. Om mönstret matchar söker omskrivningsmotorn efter motsvarande RewriteCond-instruktioner. Om det inte finns några villkor ersätts URL-adressen med ett nytt värde. Det här värdet skapas från ersättningssträngen och fortsätter med nästa regel i regeluppsättningen. Om det finns villkor är ordningen som de listas i den ordning som de bearbetas. Omskrivningsmotorn försöker matcha ett villkorsmönster (CondPattern) mot en teststräng (TestString). Om de två matchar varandra behandlas nästa villkor tills inga fler villkor är tillgängliga. Om alla villkor matchar ersätts URL:en med den ersättning som anges i regeln. Om villkoret inte uppfylls misslyckas hela uppsättningen villkor och motsvarande regel.

## Om direktivet RewriteRule {#section_A3473B5B90B74DA1970213113A90591E}

En omskrivningsregel har följande format:

```
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

**Mönstret** kan vara ett reguljärt POSIX-uttryck som används i den aktuella URL:en. &quot;Aktuell URL&quot; kan skilja sig från den ursprungliga URL-adressen eftersom tidigare regler redan har matchat och ändrat den.

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Du kan använda&quot;inte&quot;-tecknet (&#39;!&#39;) för att prefix till mönstret. Med tecknet&quot;inte&quot; kan du negera ett mönster. Med andra ord är det bara true om den aktuella URL:en INTE matchar mönstret. Du kan använda&quot;inte&quot;-tecknet när det är bättre att matcha ett negativt mönster eller som en slutlig standardregel. Observera att du inte kan använda både&quot;ej&quot;-tecknet och grupperade jokertecken i ett mönster. Du kan inte heller använda ett negerat mönster när ersättningssträngen innehåller $N.

Du kan använda parenteser för att skapa en bakåtreferens som kan refereras av Substitution och CondPattern.

**** SubstitutionURL:en ersätts helt av ersättningssträngen som kan innehålla följande:

Oformaterad text - Text som skickas oförändrad.

Backreferences Ger åtkomst till de grupperade delarna (inom parentes) av Pattern eller CondPattern. Det finns två typer av bakåtreferenser:

RewriteRule Backreferences Dessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0 &lt;= N &lt;= 9). Exempel: `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

RewriteCond Backreferences- Dessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0 &lt;= N &lt;= 9).

Funktioner: Detta är funktioner i formatet ${NAME_OF_FUNCTION:key} där NAME_OF_FUNCTION är:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.
* escape URL-kodar alla tecken i *nyckel*.
* Tecknen &#39;a&#39;..&#39;z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; och &#39;_&#39; ändras inte; Blanksteg översätts till +. alla andra tecken omvandlas till sin %xx URL-kodade motsvarighet.
* unescape omformar &#39;+&#39; tillbaka till blanksteg och alla %xx URL-kodade tecken tillbaka till enskilda tecken.

>[!NOTE]
>
>Det finns en särskild ersättningssträng: &#39;-&#39; betyder &quot;INGEN substitution&quot;. Strängen &#39;-&#39; är ofta användbar tillsammans med flaggan C (chain). Du kan matcha en URL-adress mot flera mönster innan en ersättning görs.

**Flaggor**  (valfritt)

Flaggor omsluts av hakparenteser `[]`och flera flaggor är kommaavgränsade:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p>Sista regeln. </p> <p> Avbryt omskrivningsprocessen och använd inga ytterligare omskrivningsregler. Använd den här flaggan för att förhindra vidare bearbetning till den aktuella URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p> Nästa runda. </p> <p>Kör om omskrivningsprocessen (med början igen med den första omskrivningsregeln) med URL:en från den senaste omskrivningsregeln (inte den ursprungliga URL:en). Var försiktig så att du inte skapar en död slinga! </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> kedja|C </p> </td> 
   <td colname="col2"> <p> Målad med nästa regel. </p> <p>Den här flaggan kedjar den aktuella regeln till nästa regel, som också kan kopplas till den efterföljande regeln osv. Om en regel matchar fortsätter ersättningsprocessen som vanligt. Om regeln inte matchar hoppas alla efterföljande kopplade regler över. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p>Inget fall. </p> <p>Den här flaggan gör mönstret skiftlägeskänsligt. Det finns alltså ingen skillnad mellan"A-Z" och"a-z" när mönstret matchas mot den aktuella URL:en. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> skip|S=num' </p> </td> 
   <td colname="col2"> <p>Hoppa över nästa regel eller regler. </p> <p> Om den aktuella regeln matchar, tvingar den här flaggan omskrivningsmotorn att hoppa över nästa antal regler i regeluppsättningen. Använd det här om du vill skapa pseudo if-then-else-konstruktioner. Den sista regeln i då-satsen blir en skip=N där N är antalet regler i else-satsen. (Obs! Detta är inte detsamma som flaggan 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Ange miljövariabel. </p> <p> Den här flaggan skapar en miljövariabel,"VAR", som är inställd på värdet VAL. VAL kan innehålla reguljära uttryck för bakåtreferenser, $N och %N, som färdigställs. Du kan använda den här flaggan mer än en gång för att ange flera variabler. Variablerna kan senare avrefereras i följande RewriteCond-mönster via %{VAR}. Använd den här flaggan för att ta bort och komma ihåg information från URL-adresser. </p> </td> 
  </tr> 
 </tbody> 
</table>

Observera att variabelvärdena delas av reglerna för Store Rewrite och Retrieve Rewrite. Därför kan du ange en variabel som ett tidskänsligt sessionid-värde när en inbäddad URL påträffas och lagras. När nästa URL hämtas från listan över tillfälliga lager kan det senaste värdet för sessionid läggas till innan sidan hämtas.

**Exempel**

Anta att du har en skiftlägeskänslig server. Den hanterar strängarna&quot;www.mydomain.com&quot; och&quot;www.MyDomain.com&quot; på olika sätt. För att servern ska fungera på rätt sätt måste du se till att domänen alltid är&quot;www.mydomain.com&quot; även om vissa dokument innehåller länkar som hänvisar till&quot;www.MyDomain.com&quot;. Du kan göra detta med följande regel:

```
RewriteRule  ^https:// 
<b>([^/]*)</b> 
<i>(.*)</i>$  https://${tolower:$1}$2 
```

Denna omskrivningsregel använder funktionen &quot;tolower&quot; för att skriva om domändelen av en URL för att säkerställa att den alltid är i gemener:

1. Mönstret `(^https://([^/]*)(.*)$)` innehåller en bakåtreferens **`([^/]*)`** som matchar alla tecken mellan &quot;https://&quot; och den första &quot;/&quot; i URL:en. Mönstret innehåller också en andra bakåtreferens **(.*)** som matchar alla återstående tecken i URL:en.

1. Ersättningen `(https://${tolower:$1}$2)` instruerar sökmotorn att skriva om URL:en med funktionen **tolower** på den första bakåtreferensen `(https://**${tolower:$1**}$2)` och lämnar resten av URL:en orörd `(https://${tolower:$1}*$2*)`.

Därför skrivs en URL-adress i formatet `https://www.MyDomain.com/INTRO/index.Html` om som `https://www.mydomain.com/INTRO/index.Html`

**direktivet**  RewriteCond (valfritt)

Direktivet RewriteCond definierar ett regelvillkor. När en RewriteCond föregår en RewriteRule används regeln bara om dess mönster matchar den aktuella titeln och de ytterligare villkoren gäller.

Omskrivningsvillkorsdirektiv har följande format:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i>
```

** TestString är en sträng som kan innehålla följande konstruktioner:

Oformaterad text: Text som skickas oförändrad.

Med bakåtreferenser får du tillgång till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Det finns två typer av bakåtreferenser:

* ** RewriteRule Backreferences** Dessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0 &lt;= N &lt;= 9). Exempel: `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond** BackreferencesDessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0)  &lt;>

Variabler Det här är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE kan vara en sträng för namnet på en definierad variabel. Mer information om hur du anger variabler finns i RewriteRule-flaggan *`[E]`*.

>[!NOTE]
>
>I allmänhet används variabler för att skriva om regler. Alla CGI-parametrar från den aktuella URL:en konverteras automatiskt till variabler. Sökwebbadressen `"https://search.atomz.com/search/?sp_a=sp00000000&sp_q="Product"&session=1234&id=5678"` innehåller till exempel automatiskt fyra variabler som kan refereras i reglerna för omskrivning. I det här exemplet kallas en variabel för&quot;session&quot; och dess värde är&quot;1234&quot;, medan en annan variabel kallas för&quot;id&quot; och dess värde är&quot;5678&quot;. (De andra två variablerna är `sp_a` och `sp_q`.) Du bör skicka alla nödvändiga variabler som dolda fält från sökformuläret på webbsidan. I det här exemplet bör du skicka värdena &quot;session&quot; och &quot;id&quot;, som identifierar den webbplatsanvändare som utför sökningen. Om du vill skicka ett dolt fält till sökformuläret använder du en tagg som `<input type=hidden name="session" value="1234">`.

Funktioner som är funktioner i formatet ${NAME_OF_FUNCTION:key} där NAME_OF_FUNCTION är:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.
* escape URL-kodar alla tecken i *nyckel*. Tecknen &#39;a&#39;..&#39;z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; och &#39;_&#39; ändras inte, blanksteg översätts till &#39;+&#39; och alla andra tecken omvandlas till sin %xx URL-kodade motsvarighet.
* unescape omformar &#39;+&#39; tillbaka till blanksteg och alla %xx URL-kodningstecken tillbaka till enskilda tecken.

**** CondPattern är ett utökat reguljärt standarduttryck med några tillägg. Mönstersträngen kan prefixeras med &#39;!&#39; (utropstecken) om du vill ange ett mönster som inte matchar. I stället för riktiga strängar för reguljära uttryck kan du använda någon av följande specialvarianter.

Du kan prefix för alla dessa tester med ett utropstecken (!) för att förneka deras betydelse.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-sträng </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Är inte lexikaliskt. </p> <p> Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically less than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Är mycket större än någonsin. </p> <p> Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically greater greater than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Är lika i alla lektioner. </p> <p> Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically equal equal to <i>CondPattern</i>. De två strängarna är alltså exakt lika (tecken för tecken). Om <i>CondPattern</i> bara är "" (två citattecken) jämför detta <i>TestString</i> med den tomma strängen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flaggor**  (valfritt)

Flaggor omsluts av hakparenteser `[]`och flera flaggor är kommaavgränsade:

&#39;nocase|NC&#39; (inget skiftläge): Detta gör testet skiftlägeskänsligt. Det finns alltså ingen skillnad mellan&quot;A-Z&quot; och&quot;a-z&quot; både i den expanderade *TestString* och i *CondPattern*.

&#39;or next|OR&#39; (eller nästa villkor): Använd det här om du vill kombinera regelvillkor med ett lokalt OR i stället för det implicita AND-uttrycket. Utan den här flaggan måste du skriva cond/rule flera gånger.

**Exempel**

På vissa webbsidor tilldelas en CGI-variabel för sessionid första gången en kund kommer till en webbplats. Variabeln används för att identifiera kunden och variabeln skickas när kunden bläddrar genom webbplatsen. Eftersom sökroboten ser ut som en kund till din webbplats tilldelas den ett sessionid-nummer. Sökroboten behåller det här enda värdet för sessionid, även om en andra webbplatssida försöker tilldela ett nytt värde. Du behöver följande regel för att kunna skriva om:

```
RewriteCond  %{sessionid}  .+ 
RewriteRule  ^ 
<b>(.+)</b>sessionid=[^&#]+ 
<i>(.*)</i>$   
<b>$1</b>sessionid=%{sessionid} 
<i>$2</i>
```

RewriteRule-mönstret innehåller två bakåtreferenser: (.+) och (.*). Den första bakåtreferensen matchar alla tecken före &quot;sessionid=&quot;. Den andra bakåtreferensen matchar alla tecken efter att sessions-ID har avslutat &#39;&amp;&#39; eller &#39;#&#39;.

I ersättningsmönstret skrivs URL:en om med den första bakåtreferensen, följt av strängen &quot;sessionid=&quot;, följt av värdet på variabeln sessions-ID, som skickades som en CGI-parameter i URL:en, följt av den andra bakåtreferensen. `($1sessionid=%{sessionid}$2)`.

**RewriteCond** undersöker variabeln sessionid `(%{sessionid})`. Om den innehåller minst ett tecken (.+) matchar RewriteRule.

Om sökfrågan är `"https://search.atomz.com/search/?sp_a=sp99999999&sp_q=word&sessionid=5678"` skrivs alla URL:er för sökresultat om så att värdet &quot;sessionid&quot; är &quot;5678&quot; i stället för värdet &quot;sessionid&quot; som sökroboten påträffade när den crawlade webbplatsen och sparade länkarna.

**Bekräftelse**

Programvaran för omskrivningsmotorn utvecklades ursprungligen av Apache Group för användning i Apache HTTP-serverprojektet (https://www.apache.org/).

## Lägga till URL-regler för sökning {#task_50C77D1B53804AEEB20896F74265BD6F}

Du kan lägga till regler för sök-URL för att ange hur URL:er i sökresultaten för din webbplats ska visas. Reglerna fungerar på fullständiga URL:er. Du kan ändra valfri del av URL:en, inklusive frågeargument där sessions-ID-information ofta behålls.

<!-- 

t_adding_search_url_rules.xml

 -->

**Lägga till sök-URL-regler**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search URL Rules]** på produktmenyn.
1. I fältet [!DNL Search URL Rules] anger du de regler du vill använda.

   Tomma rader och kommentarsrader som börjar med tecknet &#39;#&#39; (hash) tillåts.
1. (Valfritt) På sidan [!DNL Search URL Rules] anger du en test-URL vars crawlningsregler du vill testa i fältet [!DNL Test Search URL Rules] och klickar sedan på **Testa**.
1. Klicka på **Spara ändringar**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Search URL Rules]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om regler för söktitel {#concept_C72D20F8DFF64EDE809AF4B72797E858}

Titelregler för sökning anger hur titlar i sökresultatet på din webbplats visas. Alla delar av titeln kan ändras.

<!-- 

c_about_search_title_rules.xml

 -->

En omskrivningsregel kan användas för att ta bort en del av en titel, till exempel ett organisationsnamn. Som standard saknar webbplatssökningar och -marknadsföring titelregler och inga titeländringar görs.

Titelregler kan bestå av två huvudelement: RewriteRule och valfri RewriteCond. Ett obegränsat antal regler och villkor kan anges. Ordningen på dessa regler är viktig eftersom regeluppsättningen slingras genom regel. När en regel matchar körs en slinga genom alla (valfria) motsvarande omskrivningsvillkor. Titelregler för sökning anges på följande sätt:

```
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i> 
 
RewriteCond  
<i>TestString CondPattern [Flags]</i> 
RewriteRule  
<i>Pattern Substitution [Flags]</i>
```

När en titel påträffas försöker webbplatssökningen/försäljningen matcha den med mönstret för varje crawlningsregel. Om mönstret matchar söker omskrivningsmotorn efter motsvarande RewriteCond-direktiv. Om det inte finns några villkor ersätts titeln med ett nytt värde som är konstruerat av ersättningssträngen och fortsätter med nästa regel i regeluppsättningen. Om det finns villkor bearbetas de i den ordning som de listas. Omskrivningsmotorn försöker matcha ett villkorsmönster (CondPattern) mot en teststräng (TestString). Om de två matchar varandra behandlas nästa villkor tills inga fler villkor är tillgängliga. Om alla villkor matchar ersätts URL:en med den ersättning som anges i regeln. Om villkoret inte uppfylls misslyckas hela uppsättningen villkor och motsvarande regel.

## Direktivet RewriteRule {#section_3BF2B0FF89F74A26AE79D68FA3184B9B}

Varje RewriteRule-direktiv definierar en återskrivningsregel. Reglerna tillämpas i den ordning som de anges. En omskrivningsregel har följande format:

```
RewriteRule Pattern Substitution [Flags]
```

**MönsterEtt** reguljärt POSIX-uttryck som används för den aktuella titeln. &quot;Aktuell titel&quot; kan skilja sig från den ursprungliga titeln eftersom tidigare regler kanske redan har matchat och ändrat den.

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Du kan använda tecknet &quot;not&quot; (&#39;!&#39;) för att prefix till mönstret. Med tecknet&quot;inte&quot; kan du negera ett mönster. Det vill säga, ska bara vara true om den aktuella titeln INTE matchar mönstret. Tecknet&quot;inte&quot; kan användas när det är bättre att matcha ett negativt mönster eller som en slutlig standardregel. Obs! Du kan inte använda både&quot;inte&quot;-tecknet och grupperade jokertecken i ett mönster. Du kan inte heller använda ett negerat mönster när ersättningssträngen innehåller $N.

Du kan använda parenteser för att skapa en bakåtreferens som kan refereras av Substitution och CondPattern.

**** SubstitutionTiteln ersätts helt av ersättningssträngen som kan innehålla följande:

Oformaterad text - Text som skickas oförändrad.

**** BakåtreferenserGe åtkomst till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Följande är två typer av bakåtreferenser:

* **RewriteRule** BackreferencesDessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0)  &lt;> Exempel: `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* ** RewriteCond Backreferences** Dessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0 &lt;= N &lt;= 9).

**** VariablerDetta är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE kan vara en sträng för namnet på en definierad variabel. Mer information om hur du anger miljövariabler finns i [E]-flaggan. Variabler kan också definieras i det sökformulär som genererade sökresultaten.

**FunktionerDetta är funktioner i formatet ${NAME_OF_FUNCTION:**  nyckel} där NAME_OF_FUNCTION är:

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.

Det finns en särskild ersättningssträng: &#39;-&#39; betyder &quot;INGEN substitution&quot;. Strängen &#39;-&#39; är ofta användbar tillsammans med flaggan C (chain), vilket gör att du kan matcha en titel mot flera mönster innan en ersättning görs.

**Flaggor**  (valfritt)

Flaggor omsluts av hakparenteser `[]`, och flera flaggor är kommaavgränsade:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> 'last|L' </p> </td> 
   <td colname="col2"> <p> Sista regeln. </p> <p> Avbryt omskrivningsprocessen och använd inga ytterligare omskrivningsregler. Använd den här flaggan för att förhindra vidare bearbetning till den aktuella titeln. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'next|N' </p> </td> 
   <td colname="col2"> <p>Nästa runda. </p> <p> Kör om omskrivningsprocessen (med början igen med den första omskrivningsregeln) med titeln från den senaste omskrivningsregeln (inte den ursprungliga titeln!). Var försiktig så att du inte skapar en död slinga. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> kedja|C </p> </td> 
   <td colname="col2"> <p>Målad med nästa regel. </p> <p> Den här flaggan kedjar den aktuella regeln till nästa regel (som också kan kopplas till den efterföljande regeln o.s.v.). Om en regel matchar fortsätter ersättningsprocessen som vanligt. Om regeln inte matchar hoppas alla efterföljande kopplade regler över. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'nocase|NC' </p> </td> 
   <td colname="col2"> <p> Inget fall. </p> <p> Den här flaggan gör mönstret skiftlägeskänsligt. Det betyder att det inte finns någon skillnad mellan"A-Z" och"a-z" när mönstret matchas mot den aktuella titeln. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> skip|S=num' </p> </td> 
   <td colname="col2"> <p> Hoppa över nästa regel eller regler. </p> <p> Om den aktuella regeln matchar, tvingar den här flaggan omskrivningsmotorn att hoppa över nästa antal regler i regeluppsättningen. Använd det här om du vill skapa pseudo if-then-else-konstruktioner. Den sista regeln i då-satsen blir en skip=N där N är antalet regler i else-satsen. (Detta är inte detsamma som flaggan 'chain|C'!) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'env|E=VAR:VAL' </p> </td> 
   <td colname="col2"> <p>Ange miljövariabel. </p> <p> Den här flaggan skapar en miljövariabel, "VAR", som har värdet VAL, där VAL kan innehålla reguljära uttryck som bakåtreferenser, $N och %N, som kommer att expanderas. Du kan använda den här flaggan mer än en gång för att ange flera variabler. Variablerna kan senare refereras i följande RewriteCond-mönster via %{VAR}. Använd den här flaggan för att ta bort och komma ihåg information från titlar. </p> </td> 
  </tr> 
 </tbody> 
</table>

## RewriteCond-direktivet (valfritt) {#section_9D72B2AB454849A7B681BC39C506AAA3}

Direktivet RewriteCond definierar ett regelvillkor. När en RewriteCond föregår en RewriteRule används regeln bara om dess mönster matchar den aktuella titeln och de ytterligare villkoren gäller.

Omskrivningsvillkorsdirektiv har följande format:

```
RewriteCond TestString CondPattern [Flags]
```

**** TestStringis a string that can contain the following constructs:

Oformaterad text - Text som skickas oförändrad.

Med bakåtreferenser får du tillgång till de grupperade delarna (inom parentes) av mönstret eller CondPattern. Det finns två typer av bakåtreferenser:

* **RewriteRule** BackreferencesDessa matchar bakåtreferenser i motsvarande RewriteRule-mönster och har formatet $N (0)  &lt;> Exempel: `RewriteRule ^My[[:blank:]] (.*)$ ${toupper: $1}`

* **RewriteCond** BackreferencesDessa matchar bakåtreferenser i det senast matchade RewriteCond Cond CondPattern och har formatet %N (0)  &lt;>

**** VariablerDetta är variabler i formatet %{NAME_OF_VARIABLE} där NAME_OF_VARIABLE kan vara en sträng för namnet på en definierad variabel. Mer information om hur du anger miljövariabler finns i `[E]`-flaggan. Variabler kan också definieras i det sökformulär som genererade sökresultaten.

**FunktionerDetta är funktioner i formatet ${NAME_OF_FUNCTION:key} där NAME_OF_FUNCTION är:** 

* tolower gör alla tecken i *key* gemener.
* toupper gör alla tecken i *nyckel* versaler.
* escape URL-kodar alla tecken i *nyckel*.
* Tecknen &#39;a&#39;..&#39;z&#39;, &#39;A&#39;..&#39;Z&#39;, &#39;0&#39;..&#39;9, &#39;*&#39;, &#39;-&#39;, &#39;.&#39;, &#39;/&#39;, &#39;@&#39; och &#39;_&#39; ändras inte, blanksteg översätts till &#39;+&#39; och alla andra tecken omvandlas till sin %xx URL-kodade motsvarighet.
* unescape omformar &#39;+&#39; tillbaka till blanksteg och alla %xx URL-kodade tecken tillbaka till enskilda tecken.

Det finns en särskild ersättningssträng: &#39;-&#39; betyder &quot;INGEN substitution&quot;. Strängen &#39;-&#39; är ofta användbar tillsammans med flaggan C (chain), vilket gör att du kan matcha en URL till flera mönster innan en ersättning görs.

**** CondPatternEtt utökat reguljärt standarduttryck med några tillägg. Mönstersträngen kan prefixeras med &#39;!&#39; (utropstecken) om du vill ange ett mönster som inte matchar. I stället för riktiga strängar för reguljära uttryck kan du använda någon av följande specialvarianter.

Alla dessa tester kan också föregås av ett utropstecken (&#39;!&#39;) för att förneka deras betydelse.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>CondPattern-sträng </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> '&lt;CondPattern' </p> </td> 
   <td colname="col2"> <p>Är inte lexikaliskt. </p> <p> Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically less than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '&gt;CondPattern' </p> </td> 
   <td colname="col2"> <p> Är mycket större än någonsin. </p> <p> Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically greater greater than <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> '=CondPattern' </p> </td> 
   <td colname="col2"> <p>Är lika i alla lektioner. </p> <p> Hanterar <i>CondPattern</i> som en oformaterad sträng och jämför den lexibelt med <i>TestString</i>. True if <i>TestString</i> is lexically equal equal to <i>CondPattern</i>. De två strängarna är alltså exakt lika (tecken för tecken). Om <i>CondPattern</i> bara är "" (två citattecken) jämför detta <i>TestString</i> med den tomma strängen. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Flaggor**  (valfritt)

Flaggor omsluts av hakparenteser`[]`, och flera flaggor är kommaavgränsade:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Flagga </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> nocase|NC (inget fall) </p> </td> 
   <td colname="col2"> <p>Gör testet okänsligt. Det betyder att det inte finns någon skillnad mellan"A-Z" och"a-z" både i den expanderade <i>TestString</i> och i <i>CondPattern</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 'or next|OR' (eller nästa villkor) </p> </td> 
   <td colname="col2"> <p> Använd det här om du vill kombinera regelvillkor med ett lokalt OR i stället för det implicita AND-uttrycket. Utan den här flaggan måste du skriva cond/rule flera gånger. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempel {#section_E7454FFE169E459AABD9D033651939CB}

Anta att du har en företagswebbplats med ett standardformat: &quot;Mitt företag&quot; följt av ett bindestreck och sedan en sidspecifik beskrivning (&quot;Mitt företag - Välkommen&quot; eller&quot;Mitt företag - nyheter&quot;, till exempel). Du vill ta bort&quot;Mitt företag -&quot; från titeln och konvertera hela titeln till versaler när webbplatsen indexeras.

I följande omskrivningsregel används funktionspekaren för att endast skriva om den beskrivande delen av en titel till versaler:

```
RewriteRule  ^My[[:blank:]]Company[[:blank:]]-[[:blank:]] 
<b>(.*)</b>$  ${toupper: 
<b>$1</b>} 
```

Regelns mönster `(^My[[:blank:]]Company[[:blank:]]-[[:blank:]] (.*))` innehåller en bakåtreferens **`(.*)`** som matchar titelinnehållet som följer &quot;Mitt företag-&quot;. Tänk på att om du omger en del av ett mönster med parentes ( ) skapas en bakåtreferens som kan refereras av Ersättning. I det här exemplet skriver Ersättning (${toupper:**$1**}) om den bakåtreferensen (**$1**) med hjälp av pekarfunktionen.

Därför skrivs texten&quot;My Company - Welcome&quot; om till&quot;WELCOME&quot;.

**Bekräftelse**

Programvaran för omskrivningsmotorn utvecklades ursprungligen av Apache Group för användning i Apache HTTP-serverprojektet (https://www.apache.org/).

## Lägga till regler för sökrubrik {#task_155CECB74BE3444384EDBBD04F41515E}

Du kan lägga till regler för sökrubrik för att ange hur titlar i sökresultaten för din webbplats ska visas. Du kan ändra alla delar av titeln.

<!-- 

t_adding_search_title_rules.xml

 -->

**Lägga till regler för sökrubrik**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Search Title Rules]** på produktmenyn.
1. I fältet [!DNL Search Title Rules] anger du de regler du vill använda.

   Tomma rader och kommentarsrader som börjar med tecknet &#39;#&#39; (hash) tillåts.
1. (Valfritt) På sidan [!DNL Search Title Rules] anger du en testtitel i fältet [!DNL Test Search Title Rules] och klickar sedan på **Testa**.
1. Klicka på **Spara ändringar**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Search Title Rules]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

