---
description: Använd Crawling-menyn för att ange datum och URL-masker, lösenord, innehållstyper, anslutningar, formulärdefinitioner och URL-startpunkter.
solution: Target
subtopic: Crawling
title: Om Crawling-menyn
topic-legacy: Settings,Site search and merchandising
uuid: a58c03bf-90f7-4b5b-91ff-988b95c246b0
exl-id: 22dbbc30-bf1c-4d51-8fb0-708115ba844b
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '11011'
ht-degree: 0%

---

# Om Crawling-menyn{#about-the-crawling-menu}

Använd Crawling-menyn för att ange datum och URL-masker, lösenord, innehållstyper, anslutningar, formulärdefinitioner och URL-startpunkter.

## Om URL-adresser {#concept_5D857E3B5C124E85BC0B5AE77A509573}

De flesta webbplatser har en primär startpunkt eller hemsida som en kund först besöker. Den här huvudstartpunkten är den URL-adress från vilken sökroboten börjar crawla index. Om webbplatsen har flera domäner eller underdomäner, eller om delar av webbplatsen inte är länkade från den primära startpunkten, kan du använda URL-adresser för att lägga till fler startpunkter.

Alla webbplatssidor under varje angiven URL-startpunkt indexeras. Du kan kombinera URL-startpunkter med masker för att styra exakt vilka delar av en webbplats som du vill indexera. Du måste återskapa webbplatsindexet innan effekterna av URL-adressinställningarna blir synliga för kunderna.

Huvudstartpunkten är vanligtvis URL-adressen till webbplatsen som du vill indexera och söka efter. Du konfigurerar den här huvudstartpunkten i Kontoinställningar.

Se [Konfigurera dina kontoinställningar](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

När du har angett huvud-URL-startpunkten kan du välja att ange ytterligare startpunkter som du vill crawla i ordning. Oftast anger du ytterligare startpunkter för webbsidor som inte är länkade från sidor under startpunkten. Ange ytterligare startpunkter när webbplatsen sträcker sig över flera domäner, som i följande exempel:

`https://www.domain.com/`

`https://www.domain.com/not_linked/but_search_me_too/`

`https://more.domain.com/`

Du kvalificerar varje startpunkt med ett eller flera av följande blankstegsavgränsade nyckelord i tabellen nedan. Dessa nyckelord påverkar hur sidan indexeras.

**Viktigt**: Se till att du avgränsar ett visst nyckelord från startpunkten och från varandra med ett blanksteg. ett komma är inte en giltig avgränsare.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nyckelord </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Om du inte vill indexera texten på startpunktssidan, men vill följa sidans länkar, lägger du till 
     <code>
       noindex 
     </code> efter startpunkten. </p> <p>Avgränsa nyckelordet från startpunkten med ett blanksteg som i följande exempel: </p> <p> <code> https://www.my-additional-domain.com/more_pages/main.html&amp;nbsp;noindex </code> </p> <p>Det här nyckelordet motsvarar en meta-tagg för robotar med 
     <code>
       content="noindex" 
     </code>) mellan 
     <code>
       &lt;head&gt; 
     </code>.. 
     <code>
       &lt;/head&gt; 
     </code>-taggar för startpunktssidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Om du vill indexera texten på startpunktssidan men inte vill följa någon av sidans länkar, lägger du till 
     <code>
       nofollow 
     </code> efter startpunkten. </p> <p>Avgränsa nyckelordet från startpunkten med ett blanksteg som i följande exempel: </p> <p> <code> https://www.domain.com/not_linked/directory_listing&amp;nbsp;nofollow </code> </p> <p>Det här nyckelordet motsvarar en meta-tagg för robotar med 
     <code>
       content="nofollow" 
     </code> mellan 
     <code>
       &lt;head&gt; 
     </code>.. 
     <code>
       &lt;/head&gt; 
     </code>-tagg för en startpunktssida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>formulär </p> </td> 
   <td colname="col2"> <p> När startpunkten är en inloggningssida 
     <code>
       form 
     </code> används vanligtvis så att sökroboten kan skicka inloggningsformuläret och ta emot lämpliga cookies innan webbplatsen crawlas. När nyckelordet "form" används indexeras inte startpunktssidan och sökroboten markerar inte startpunktssidan som crawlad. Använd 
     <code>
       nofollow 
     </code> om du inte vill att sökroboten ska följa sidans länkar. </p> </td> 
  </tr> 
 </tbody> 
</table>

Se även [Om innehållstyper](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

Se även [Om indexkoppling](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84).

## Lägga till flera URL-startpunkter som du vill indexera {#task_2338A47387D74CFDAC4D4EF4A367ED45}

Om webbplatsen har flera domäner eller underdomäner och du vill att de ska crawlas kan du använda URL-adresser för att lägga till fler URL:er.

Om du vill ange webbplatsens huvud-URL-startpunkt använder du Kontoinställningar.

Se [Konfigurera dina kontoinställningar](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

**Lägga till flera URL-startpunkter som du vill indexera**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]** på produktmenyn.
1. På sidan [!DNL URL Entrypoints] anger du en URL-adress per rad i fältet [!DNL Entrypoints].
1. (Valfritt) I listrutan **[!UICONTROL Add Index Connector Configurations]** väljer du en indexkoppling som du vill lägga till som en startpunkt för indexering.

   Listrutan är bara tillgänglig om du tidigare har lagt till en eller flera definitioner för indexkoppling.

   ![](assets/url_entrypoints_index_connector.png)

   Se [Lägga till en indexanslutningsdefinition](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om URL-masker {#concept_8039DFC53FF3410AA494D602F71BA164}

URL-masker är mönster som avgör vilket av webbplatsens dokument som sökroboten indexerar eller inte indexerar.

Se till att du återskapar webbplatsindexet så att resultaten av dina URL-masker blir synliga för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Följande är två typer av URL-masker som du kan använda:

* Inkludera URL-masker
* Uteslut URL-masker

Inkludera URL-masker och instruera sökroboten att indexera dokument som matchar maskens mönster.

Exkludera URL-masker instruerar sökroboten att indexera matchande dokument.

När sökroboten förflyttar sig från länken till länken via webbplatsen upptäcker den URL:er och söker efter masker som matchar dessa URL:er. Den första matchningen avgör om URL:en ska inkluderas eller exkluderas från indexet. Om ingen mask matchar en påträffad URL tas URL:en bort från indexet.

Inkludera URL-masker för ingångspunktens URL:er genereras automatiskt. Detta beteende gör att alla påträffade dokument på webbplatsen indexeras. Dessutom finns det länkar som&quot;lämnar&quot; webbplatsen. Om en indexerad sida till exempel länkar till https://www.yahoo.com indexeras inte den URL:en eftersom den inte matchar den inkluderingsmask som skapas automatiskt av URL:en för startpunkten.

Varje URL-mask som du anger måste finnas på en separat rad.

Masken kan ange något av följande:

* En fullständig sökväg som i `https://www.mydomain.com/products.html`.
* En partiell sökväg som i `https://www.mydomain.com/products`.
* En URL som använder jokertecken som i `https://www.mydomain.com/*.html`.
* Ett reguljärt uttryck (för avancerade användare).

   Om du vill göra en mask till ett reguljärt uttryck infogar du nyckelordet `regexp` mellan masktypen ( `exclude` eller `include`) och URL-masken.

Följande är ett enkelt exempel på en exkluderad URL-mask:

```
exclude https://www.mydomain.com/photos
```

Eftersom det här exemplet är en exkluderande URL-mask, indexeras inte dokument som matchar mönstret. Mönstret matchar alla påträffade objekt, både filer och mappar, så att `https://www.mydomain.com/photos.html` och `https://www.mydomain.com/photos/index.html`, som båda matchar den utelämnade URL:en, inte indexeras. Om du bara vill matcha filer i mappen `/photos/` måste URL-masken innehålla ett avslutande snedstreck, som i följande exempel:

```
exclude https://www.mydomain.com/photos/
```

I följande exempel på exkluderingsmask används ett jokertecken. Den instruerar sökroboten att ignorera filer med tillägget&quot;.pdf&quot;. Sökroboten lägger inte till dessa filer i indexet.

```
exclude *.pdf
```

En enkel URL-mask för inkludering är följande:

```
include https://www.mydomain.com/news/
```

Endast dokument som är länkade via en serie länkar från en URL-startpunkt, eller som används som en URL-startpunkt, indexeras. Det är bara när du anger ett dokuments URL som en inkluderingsURL-mask som indexerar inte ett olänkat dokument. Om du vill lägga till olänkade dokument i indexet kan du använda funktionen URL-adresser.

Se [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Inkludera masker och exkludera masker kan fungera tillsammans. Du kan utesluta en stor del av webbplatsen från indexeringen genom att skapa en exkluderande URL-mask och ändå ta med en eller flera av de uteslutna sidorna med en inkluderingsURL-mask. Anta till exempel att URL-adressen för ingångspunkten är följande:

```
https://www.mydomain.com/photos/
```

Sökroboten crawlar och indexerar alla sidor under `/photos/summer/`, `/photos/spring/` och `/photos/fall/` (förutsatt att det finns länkar till minst en sida i varje katalog från mappen `photos`). Detta beteende beror på att länksökvägarna gör det möjligt för sökroboten att hitta dokumenten i mapparna `/summer/`, `/spring/` och `/fall/`, och mappens URL:er matchar den inkluderingsmask som skapas automatiskt av startpunktens URL.

Du kan välja att exkludera alla sidor i mappen `/fall/` med en exklusiv URL-mask som i följande exempel:

```
exclude https://www.mydomain.com/photos/fall/
```

Eller ta med endast `/photos/fall/redleaves4.html` som en del av indexet med följande URL-mask:

```
include https://www.mydomain.com/photos/fall/redleaves4.html
```

För att de två ovanstående maskexemplen ska fungera som avsett visas den inkluderade masken först, som i följande exempel:

```
include https://www.mydomain.com/photos/fall/redleaves4.html 
exclude https://www.mydomain.com/photos/fall/
```

Eftersom sökroboten följer instruktionerna i den ordning de listas, innehåller sökroboten först `/photos/fall/redleaves4.html` och utesluter sedan resten av filerna i mappen `/fall`.

Om instruktionerna anges på motsatt sätt som i följande:

```
exclude https://www.mydomain.com/photos/fall/ 
include https://www.mydomain.com/photos/fall/redleaves4.html
```

Sedan tas inte `/photos/fall/redleaves4.html` med, även om masken anger att den ingår.

En URL-mask som visas först har alltid företräde framför en URL-mask som visas senare i maskinställningarna. Om sökroboten hittar en sida som matchar en inkluderingswebbmask och en exkluderande URL-mask, har den mask som visas först alltid företräde.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Använda nyckelord med URL-masker {#section_7609A7A6D79B482ABCA8900886541AAB}

Du kan kvalificera varje inkluderingsmask med ett eller flera blankstegsavgränsade nyckelord, som påverkar hur de matchande sidorna indexeras.

Ett komma är inte giltigt som avgränsare mellan masken och nyckelordet. Du kan bara använda blanksteg.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nyckelord </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Om du inte vill indexera texten på sidorna som matchar URL-masken, men vill följa de matchade sidlänkarna, lägger du till 
     <code>
       noindex 
     </code> efter inkluderingswebbmasken. Se till att du skiljer nyckelordet från masken med ett blanksteg som i följande exempel: </p> <p> <code> include&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>Exemplet ovan anger att sökroboten följer alla länkar från filer med 
     <code>
       .swf 
     </code>-tillägg, men inaktiverar indexering av all text i dessa filer. </p> <p>The 
     <code>
       noindex 
     </code>-nyckelordet motsvarar en robotmeta-tagg med 
     <code>
       content="noindex" 
     </code> mellan 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>-taggar för matchade sidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Om du vill indexera texten på sidorna som matchar URL-masken, men inte vill följa länkarna för den matchade sidan, lägger du till 
     <code>
       nofollow 
     </code> efter inkluderingswebbmasken. Se till att du skiljer nyckelordet från masken med ett blanksteg som i följande exempel: </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>The 
     <code>
       nofollow 
     </code>-nyckelordet motsvarar en robotmeta-tagg med 
     <code>
       content="nofollow" 
     </code> mellan 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>-taggar för matchade sidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p>Används för både att inkludera och exkludera masker. </p> <p>En URL-mask föregås av 
     <code>
       regexp 
     </code> behandlas som ett reguljärt uttryck. Om sökroboten stöter på dokument som matchar en URL-mask för ett exkluderat uttryck, indexeras inte dessa dokument. Om sökroboten påträffar dokument som matchar en URL-mask för ett reguljärt uttryck, indexeras dessa dokument. Anta att du har följande URL-mask: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*/products/.*\.html$ </code> </p> <p>Sökroboten exkluderar matchande filer som 
     <code>
       https://www.mydomain.com/products/page1.html 
     </code> </p> <p>Om du hade följande URL-mask för reguljära uttryck: </p> <p> <code> exclude&amp;nbsp;regexp&amp;nbsp;^.*\?..*$ </code> </p> <p>Sökroboten innehåller ingen URL som innehåller en CGI-parameter som 
     <code>
       https://www.mydomain.com/cgi/prog/?arg1=val1&amp;arg2=val2 
     </code>. </p> <p>Om du hade följande URL-mask för reguljära uttryck: </p> <p> <code> include&amp;nbsp;regexp&amp;nbsp;^.*\.swf$&amp;nbsp;noindex </code> </p> <p>Sökroboten följer alla länkar från filer med tillägget".swf". The 
     <code>
       noindex 
     </code>-nyckelordet anger också att texten i matchade filer inte indexeras. </p> <p>Se <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguljära uttryck </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lägga till URL-masker till index eller inte indexera delar av webbplatsen {#task_E1AFC17C746048B8843013D979E082C1}

Du kan använda [!DNL URL Masks] för att definiera vilka delar av webbplatsen som du vill eller inte vill ska crawlas och indexeras.

Använd fältet Testa URL-masker för att testa om ett dokument finns med eller inte efter indexeringen.

Se till att du återskapar webbplatsindexet så att resultaten av dina URL-masker blir synliga för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Lägga till URL-masker i index eller inte indexera delar av webbplatsen**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]** på produktmenyn.
1. (Valfritt) På sidan [!DNL URL Masks] anger du en test-URL-mask från webbplatsen i fältet **[!UICONTROL Test URL Masks]** och klickar sedan på **[!UICONTROL Test]**.
1. I fältet [!DNL URL Masks] skriver du `include` (för att lägga till en webbplats som du vill crawla och indexera) eller `exclude` (för att blockera en webbplats från att crawlas och indexeras), följt av URL-maskadressen.

   Ange en URL-maskadress per rad. Exempel:

   ```
   include https://www.mycompany.com/summer 
   include https://www.mycompany.com/spring 
   exclude regexp .*\.xml 
   exclude https://www.mycompany.com/fall
   ```

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om datummasker {#concept_F4F1F58A646F4A86B8650EC46FDCEF66}

Du kan använda Datummasker för att inkludera eller exkludera filer från sökresultaten baserat på filens ålder.

Se till att du återskapar webbplatsindexet så att resultaten av dina URL-masker blir synliga för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Det här är två typer av datummasker som du kan använda:

* Inkludera datummasker (&quot;include-days&quot; och&quot;include-date&quot;)

   Inkludera datummaskindexfiler som är daterade på eller före det angivna datumet.
* Uteslut datummasker (&quot;exkluderingsdagar&quot; och&quot;exkluderingsdatum&quot;)

   Uteslut indexfiler för datummasker som är daterade på eller före det angivna datumet.

Som standard bestäms fildatumet av metatagginformationen. Om ingen metatagg hittas bestäms datumet för en fil av HTTP-huvudet som tas emot från servern när sökroboten hämtar en fil.

Varje datummask som du anger måste finnas på en separat rad.

Masken kan ange något av följande:

* En fullständig sökväg som i `https://www.mydomain.com/products.html`
* En partiell sökväg som i `https://www.mydomain.com/products`
* En URL som använder jokertecken `https://www.mydomain.com/*.html`
* Ett reguljärt uttryck. Om du vill göra en mask till ett reguljärt uttryck infogar du nyckelordet `regexp` före URL:en.

I både Inkludera och Exkludera datummasker kan du ange ett datum på något av följande två sätt. Maskerna tillämpas bara om de matchande filerna skapades på eller före det angivna datumet:

1. Ett antal dagar. Anta till exempel att din datummask är följande:

   ```
   exclude-days 30 https://www.mydomain.com/docs/archive/)
   ```

   Antalet angivna dagar räknas tillbaka. Om filen är daterad på eller före det datum då den togs emot, tillämpas masken.

1. Ett faktiskt datum med formatet ÅÅÅ-MM-DD. Anta till exempel att din datummask är följande:

   ```
   include-date 2011-02-15 https://www.mydomain.com/docs/archive/)
   ```

   Om det matchande dokumentet är daterat på eller före det angivna datumet används datummasken.

Följande är ett enkelt exempel på en uteslutningsdatummask:

```
exclude-days 90 https://www.mydomain.com/docs/archive
```

Eftersom det här är en mask för uteslutningsdatum indexeras inte filer som matchar mönstret och är 90 dagar eller äldre. När du utelämnar ett dokument indexeras ingen text och inga länkar följer från filen. Filen ignoreras. I det här exemplet kan både filer och mappar matcha det angivna URL-mönstret. Observera att både `https://www.mydomain.com/docs/archive.html` och `https://www.mydomain.com/docs/archive/index.html` matchar mönstret och inte indexeras om de är 90 dagar eller äldre. Om du bara vill matcha filer i mappen `/docs/archive/` måste datummasken innehålla ett avslutande snedstreck enligt följande:

```
exclude-days 90 https://www.mydomain.com/docs/archive/
```

Datummasker kan också användas med jokertecken. Följande exkluderingsmask anger att sökroboten ska ignorera filer med tillägget&quot;.pdf&quot; som är daterad 2011-02-15 eller tidigare. Sökroboten lägger inte till några matchande filer i indexet.

```
exclude-date 2011-02-15 *.pdf
```

Inkludera en datummask ser likadan ut, bara matchade filer läggs till i indexet. Följande exempel på en datummask anger för sökroboten att indexera texten från filer som är noll dagar gamla eller äldre i `/docs/archive/manual/`-området på webbplatsen.

```
include-days 0 https://www.mydomain.com/docs/archive/manual/
```

Inkludera masker och exkludera masker kan fungera tillsammans. Du kan t.ex. utesluta en stor del av webbplatsen från indexeringen genom att skapa en mask för uteslutningsdatum men ändå inkludera en eller flera av de uteslutna sidorna med en inkluderingswebbadress. Om din entrypoint-URL är följande:

```
https://www.mydomain.com/archive/
```

Sökroboten crawlar och indexerar alla sidor under `/archive/summer/`, `/archive/spring/` och `/archive/fall/` (förutsatt att det finns länkar till minst en sida i varje mapp från mappen `archive`). Detta beteende beror på att länksökvägarna gör att sökroboten kan &quot;söka efter&quot; filer i mapparna `/summer/`, `/spring/` och `/fall/` och mappens URL:er matchar den inkluderingsmask som skapas automatiskt av startpunktens URL.

Se [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

Se [Konfigurera dina kontoinställningar](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Du kan välja att exkludera alla sidor som är äldre än 90 dagar i mappen `/fall/` med en exkluderingsdatummask enligt följande:

```
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Du kan välja att endast inkludera `/archive/fall/index.html` (oavsett hur gammal den är - alla filer från 0 dagar eller äldre matchas) som en del av indexet med följande datummask:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html
```

För att de två ovanstående maskexemplen ska fungera som avsett måste du först visa inkluderingsmasken så här:

```
include-days 0 https://www.mydomain.com/archive/fall/index.html 
exclude-days 90 https://www.mydomain.com/archive/fall/
```

Eftersom sökroboten följer instruktionerna i den ordning som de anges, innehåller sökroboten först `/archive/fall/index.html` och utesluter sedan resten av filerna i mappen `/fall`.

Om instruktionerna anges på motsatt sätt som i följande:

```
exclude-days 90 https://www.mydomain.com/archive/fall/ 
include-days 0 https://www.mydomain.com/archive/fall/index.html 
```

Sedan tas inte `/archive/fall/index.html` med, även om masken anger att den ska vara det. En datummask som visas först har alltid företräde framför en datummask som kan visas senare i maskinställningarna. Om sökroboten hittar en sida som matchar både en inkluderingsdatummask och en exkluderingsdatummask, har den mask som visas först alltid företräde.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Använda nyckelord med datummasker {#section_CCBB3E3FDBDE4725B2B571FD6594470C}

Du kan kvalificera varje inkluderingsmask med ett eller flera blankstegsavgränsade nyckelord, som påverkar hur de matchande sidorna indexeras.

Ett komma är inte giltigt som avgränsare mellan masken och nyckelordet. Du kan bara använda blanksteg.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nyckelord </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>noindex </p> </td> 
   <td colname="col2"> <p> Om du inte vill indexera texten på sidorna som är daterade på eller före det datum som anges av inkluderingsmasken lägger du till 
     <code>
       noindex 
     </code> efter inkluderingsdatummasken enligt följande: </p> <p> <code> include-days&amp;nbsp;10&amp;nbsp;*.swf&amp;nbsp;noindex </code> </p> <p>Se till att du skiljer nyckelordet från masken med ett mellanslag. </p> <p>Exemplet ovan anger att sökroboten följer alla länkar från filer med tillägget".swf" som är 10 dagar eller äldre. Den inaktiverar emellertid indexering av all text i dessa filer. </p> <p>Du kan kontrollera att texten för äldre filer inte är indexerad, men ändå följa alla länkar från dessa filer. I sådana fall ska du använda en inkluderingsdatummask med nyckelordet "noindex" i stället för en exkluderingsdatummask. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nofollow </p> </td> 
   <td colname="col2"> <p> Om du vill indexera texten på sidorna som är daterade på eller före det datum som anges av inkluderingsmasken, men inte vill följa den matchade sidans länkar, lägger du till 
     <code>
       nofollow 
     </code> efter inkluderingsdatummasken enligt följande: </p> <p> <code> include-days&amp;nbsp;8&amp;nbsp;https://www.mydomain.com/photos&amp;nbsp;nofollow </code> </p> <p>Se till att du skiljer nyckelordet från masken med ett mellanslag. </p> <p>The 
     <code>
       nofollow 
     </code>-nyckelordet motsvarar en robotmeta-tagg med 
     <code>
       content="nofollow" 
     </code> mellan 
     <code>
       &lt;head&gt;...&lt;/head&gt; 
     </code>-tagg för matchade sidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>serverdatum </p> </td> 
   <td colname="col2"> <p>Används för både att inkludera och exkludera masker. </p> <p>Sökroboten hämtar och tolkar vanligtvis alla filer innan datummaskerna kontrolleras. Detta beteende beror på att vissa filtyper kan ange ett datum inuti själva filen. Ett HTML-dokument kan till exempel innehålla metataggar som anger datumet för filen. </p> <p>Om du ska utesluta många filer baserat på deras datum och du inte vill göra en onödig belastning på dina servrar, kan du använda 
     <code>
       server-date 
     </code> efter URL:en i datummasken. </p> <p>Det här nyckelordet instruerar sökroboten att lita på datumet för filen som returneras av servern i stället för att analysera varje fil. I följande mask för exkluderingsdatum ignoreras sidor som matchar URL:en om dokumenten är 90 dagar eller äldre, enligt det datum som servern returnerar i HTTP-rubrikerna: </p> <p> <code> exclude-days&amp;nbsp;90&amp;nbsp;https://www.mydomain.com/docs/archive&amp;nbsp;server-date </code> </p> <p> Om datumet som returneras av servern är 90 dagar eller längre, 
     <code>
       server-date 
     </code> anger att de undantagna dokumenten inte ska hämtas från servern. Resultatet innebär snabbare indexeringstid för dina dokument och minskad belastning på servrarna. If 
     <code>
       server-date 
     </code> har inte angetts. Sökroboten ignorerar det datum som servern returnerade i HTTP-rubrikerna. I stället hämtas och kontrolleras varje fil för att se om datumet har angetts. Om inget datum anges i filen använder sökroboten det datum som returneras av servern. </p> <p>Du ska inte använda 
     <code>
       server-date 
     </code> om filerna innehåller kommandon som åsidosätter serverdatumet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>regexp </p> </td> 
   <td colname="col2"> <p> Använd för både inkludera och exkludera masker. </p> <p>Alla datummasker som föregås av 
     <code>
       regexp 
     </code> behandlas som ett reguljärt uttryck. </p> <p>Om sökroboten hittar filer som matchar en exkluderad datummask för reguljära uttryck indexeras inte dessa filer. </p> <p>Om sökroboten hittar filer som matchar en datummask för ett reguljärt uttryck indexeras dessa dokument. </p> <p>Anta att du har följande datummask: </p> <p> <code> exclude-days&amp;nbsp;180&amp;nbsp;regexp&amp;nbsp;.*archive.* </code> </p> <p>Masken instruerar sökroboten att utesluta matchande filer som är 180 dagar eller äldre. Det vill säga filer som innehåller ordet"arkiv" i sin URL. </p> <p>Se <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguljära uttryck </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lägga till datummasker i index eller inte indexera delar av webbplatsen {#task_0010543C55F648D2B5DEFEFAD60FAF04}

Du kan använda Datummasker för att inkludera eller exkludera filer från kundsökresultat baserat på filernas ålder.

Använd fälten **[!UICONTROL Test Date]** och **[!UICONTROL Test URL]** för att testa om en fil ingår eller inte efter indexeringen.

Se till att du återskapar webbplatsindexet så att resultaten av dina URL-masker blir synliga för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Lägga till datummasker i index eller inte indexera delar av webbplatsen**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Date Masks]** på produktmenyn.
1. (Valfritt) På sidan [!DNL Date Masks] anger du i fältet **[!UICONTROL Test Date]** ett datum formaterat som YYY-MM-DD (t.ex. `2011-07-25`); i fältet **[!UICONTROL Test URL]** anger du en URL-mask från webbplatsen och klickar sedan på **[!UICONTROL Test]**.
1. I fältet [!DNL Date Masks] anger du en datummaskadress per rad.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om lösenord {#concept_3EDBD731725D46B891F834D4472774DC}

Om du vill komma åt delar av webbplatsen som skyddas med grundläggande HTTP-autentisering kan du lägga till ett eller flera lösenord.

Innan effekterna av lösenordsinställningarna är synliga för kunderna måste du återskapa platsindexet.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

På sidan [!DNL Passwords] skriver du respektive lösenord på en rad. Lösenordet består av en URL eller sfär, ett användarnamn och ett lösenord, som i följande exempel:

```
https://www.mydomain.com/ myname mypassword
```

I stället för att använda en URL-sökväg, som ovan, kan du även ange en sfär.

Du kan avgöra vilken sfär som ska användas genom att öppna en lösenordsskyddad webbsida med en webbläsare och titta i dialogrutan Ange nätverkslösenord.

![](assets/realms.gif)

Sfärnamnet är i det här fallet&quot;Min webbplats-sfär&quot;.

Med hjälp av sfärnamnet ovan kan ditt lösenord se ut så här:

```
My Site Realm myusername mypassword
```

Om din webbplats har flera sfärer kan du skapa flera lösenord genom att ange ett användarnamn och lösenord för varje sfärg på en separat rad, som i följande exempel:

```
Realm1 name1 password1 
Realm2 name2 password2 
Realm3 name3 password3
```

Du kan blanda lösenord som innehåller URL:er eller sfärer så att lösenordslistan ser ut så här:

```
Realm1 name1 password1 
https://www.mysite.com/path1/path2 name2 password2 
Realm3 name3 password3 
Realm4 name4 password4 
https://www.mysite.com/path1/path5 name5 password5 
https://www.mysite.com/path6 name6 password6
```

I listan ovan används det första lösenordet som innehåller en sfär eller URL som matchar serverns autentiseringsbegäran. Även om filen på `https://www.mysite.com/path1/path2/index.html` är i `Realm3`, används till exempel `name2` och `password2` eftersom lösenordet som definieras med URL:en finns ovanför det som definierats med sfären.

## Lägga till lösenord för att komma åt områden på webbplatsen som kräver autentisering {#task_DED19D476FF04B48BB6456D5ECB8628A}

Du kan använda Lösenord för att komma åt lösenordsskyddade delar av webbplatsen för crawlnings- och indexeringsändamål.

Innan effekterna av ditt lösenord är synliga för kunderna måste du se till att du återskapar platsindexet

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Lägga till lösenord för att komma åt områden på webbplatsen som kräver autentisering**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Passwords]** på produktmenyn.
1. På sidan [!DNL Passwords] anger du en sfär eller URL och tillhörande användarnamn och lösenord i fältet **[!UICONTROL Passwords]**, avgränsat med blanksteg.

   Exempel på ett sfäriskt lösenord och ett URL-lösenord på separata rader:

   ```
   Realm1 name1 password1 
   https://www.mysite.com/path1/path2 name2 password2
   ```

   Lägg bara till ett lösenord per rad.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om innehållstyper {#concept_6FEA1355C0374500B4C53090C34A8A07}

Du kan använda [!DNL Content Types] för att välja vilka typer av filer som du vill crawla och indexera för det här kontot.

Innehållstyper som du kan använda för att crawla och indexera är PDF-dokument, textdokument, Adobe Flash-filmer, filer från Microsoft Office-program som Word, Excel och PowerPoint samt text i MP3-filer. Texten som finns i de valda innehållstyperna söks igenom tillsammans med all annan text på webbplatsen.

Innan effekterna av inställningarna för innehållstyper visas för kunderna måste du återskapa platsindexet.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

## Indexera MP3-musikfiler {#section_AD2E28BEEE3E46629E2B05C34A963673}

Om du väljer alternativet **[!UICONTROL Text in MP3 Music Files]** på sidan [!DNL Content Types] crawlas och indexeras en MP3-fil på ett av två sätt. Det första och vanligaste sättet är från en href-ankartagg i en HTML-fil som i följande:

```
<a href="MP3-file-URL"></a>
```

Det andra sättet är att ange MP3-filens URL som en URL-startpunkt.

Se [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

En MP3-fil känns igen av MIME-typen &quot;audio/mpeg&quot;.

Tänk på att storleken på MP3-musikfiler kan vara ganska stor, även om de vanligtvis bara innehåller en liten mängd text. MP3-filer kan till exempel lagra albumnamn, artistnamn, låttitel, låtgenre, versionsår och en kommentar. Den här informationen lagras i slutet av filen i det som kallas för TAGG. MP3-filer som innehåller TAG-information indexeras på följande sätt:

* Låttiteln behandlas som titeln på en HTML-sida.
* Kommentaren behandlas som en beskrivning som är definierad för en HTML-sida.
* Genren behandlas som ett nyckelord som är definierat för en HTML-sida.
* Konstnärens namn, albumnamn och versionsår behandlas som en HTML-sidas brödtext.

Observera att varje MP3-fil som crawlas och indexeras på webbplatsen räknas som en sida.

Om webbplatsen innehåller många stora MP3-filer kan du överskrida indexeringsbytegränsen för ditt konto. Om detta inträffar kan du avmarkera **[!UICONTROL Text in MP3 Music Files]** på [!DNL Content Types]-sidan för att förhindra indexering av alla MP3-filer på webbplatsen.

Om du bara vill förhindra indexering av vissa MP3-filer på webbplatsen kan du göra något av följande:

* Omge ankartaggarna som länkar till MP3-filerna med `<nofollow>`- och `</nofollow>`-taggar. Sökroboten följer inte länkar mellan dessa taggar.

* Lägg till MP3-filernas URL:er som exkluderingsmasker.

   Se [Om URL-masker](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Välja innehållstyper som ska crawlas och indexeras {#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8}

Du kan använda [!DNL Content Types] för att välja vilka typer av filer som du vill crawla och indexera för det här kontot.

Innehållstyper som du kan använda för att crawla och indexera är PDF-dokument, textdokument, Adobe Flash-filmer, filer från Microsoft Office-program som Word, Excel och PowerPoint samt text i MP3-filer. Texten som finns i de valda innehållstyperna söks igenom tillsammans med all annan text på webbplatsen.

Innan effekterna av inställningarna för innehållstyper visas för kunderna måste du återskapa platsindexet.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

Följ stegen nedan för att crawla och indexera kinesiska, japanska eller koreanska MP3-filer. I **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]** anger du sedan den teckenuppsättning som används för att koda MP3-filerna.

Se [Om injektioner](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

**Så här väljer du innehållstyper som ska crawlas och indexeras**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** på produktmenyn.
1. På sidan [!DNL Content Types] kontrollerar du de filtyper som du vill crawla och indexera på webbplatsen.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om anslutningar {#concept_E2F3B7E7521147479E5948A94BB3A40B}

Du kan använda Anslutningar för att lägga till upp till tio HTTP-anslutningar som sökroboten använder för att indexera webbplatsen.

Om du ökar antalet anslutningar kan det ta betydligt kortare tid att slutföra en crawl och ett index. Tänk dock på att varje ytterligare anslutning ökar belastningen på servern.

## Lägga till anslutningar för att öka indexeringshastigheten {#task_3E9B83E43C1842A19066355A15C4A6FB}

Du kan minska den tid det tar att indexera webbplatsen genom att använda Anslutningar för att öka antalet samtidiga HTTP-anslutningar som crawlern använder. Du kan lägga till upp till tio anslutningar.

Tänk på att varje ytterligare anslutning ökar belastningen som läggs på servern.

**Lägga till anslutningar för att öka indexeringshastigheten**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Connections]** på produktmenyn.
1. På sidan [!DNL Parallel Indexing Connections] anger du antalet anslutningar (1-10) som du vill lägga till i fältet **[!UICONTROL Number of Connections]**.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om inskickning av formulär {#concept_CADD5D7CF373497DAA6F8564D7BC8502}

Du kan använda Skicka formulär för att identifiera och bearbeta formulär på din webbplats.

Under crawlningen och indexeringen av webbplatsen jämförs varje formulär som påträffas med de formulärdefinitioner som du har lagt till. Om ett formulär matchar en formulärdefinition skickas formuläret för indexering. Om ett formulär matchar mer än en definition skickas formuläret en gång för varje matchad definition.

## Lägga till formulärdefinitioner för att indexera formulär på webbplatsen {#task_62FBCE9E6DBE4BDA8D1249233ADFC00F}

Du kan använda [!DNL Form Submission] för att bearbeta formulär som känns igen på webbplatsen i indexeringssyfte.

Se till att du återskapar webbplatsindexet så att resultatet av ändringarna blir synligt för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Lägga till formulärdefinitioner för att indexera formulär på webbplatsen**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Form]** på sidan [!DNL Form Submission].
1. På sidan [!DNL Add Form Definition] anger du alternativen [!DNL Form Recognition] och [!DNL Form Submission].

   De fem alternativen i avsnittet [!DNL Form Recognition] på [!DNL Form Definition]-sidan används för att identifiera formulär på dina webbsidor som kan bearbetas.

   De tre alternativen i avsnittet [!DNL Form Submission] används för att ange parametrar och värden som skickas med ett formulär till webbservern.

   Ange en igenkännings- eller inskicksparameter per rad. Varje parameter måste innehålla ett namn och ett värde.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p> <b>Igenkänning av formulär</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL-mask för sida </p> </td> 
      <td colname="col2"> <p>Identifiera den eller de webbsidor som innehåller formuläret. Om du vill identifiera ett formulär som visas på en sida anger du sidans URL-adress som i följande exempel: </p> <p> <code> https://www.mydomain.com/login.html </code> </p> <p>Om du vill identifiera formulär som visas på flera sidor anger du en URL-mask som använder jokertecken för att beskriva sidorna. Om du vill identifiera formulär som har påträffats på en ASP-sida under <code> https://www.mydomain.com/register/ </code> anger du till exempel följande: </p> <p> <code> https://www.mydomain.com/register/*.asp&amp;nbsp; </code> </p> <p>Du kan också använda ett reguljärt uttryck för att identifiera flera sidor. Ange bara 
      <code>
        regexp 
      </code>-nyckelord före URL-masken som i följande exempel: </p> <p> <code> regexp&amp;nbsp;^https://www\.mydomain\.com/.*/login\.html$ </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Åtgärds-URL-mask </p> </td> 
      <td colname="col2"> <p>Identifierar åtgärdsattributet för 
      <code>
        &lt;form&gt; 
      </code>-tagg. </p> <p>Precis som sidans URL-mask kan URL-masken för åtgärden ha formen av en enda URL, en URL med jokertecken eller ett reguljärt uttryck. </p> <p>URL-masken kan vara något av följande: 
      <ul id="ul_EDFE7688D3DD4C0BBACCE5D4648D8E44"> 
      <li id="li_77550A448D954EF29FF33EE5E8B5E0F5"> En fullständig sökväg som i följande: <code> https://www.mydomain.com/products.html </code> </li> 
      <li id="li_F84E25553BBA41419BE153DC0709E011"> En del sökväg som i följande: <code> https://www.mydomain.com/products </code> </li> 
      <li id="li_8DADA1C8604740FCACBA30B4AAADB2A1"> En URL som använder jokertecken som i följande exempel: <code> https://www.mydomain.com/*.html </code> </li> 
      <li id="li_1EF637B450654B509AA4B618F7FD3C2B"> Ett reguljärt uttryck som i följande: <code> regexp&amp;nbsp^https://www\.mydomain\.com/.*/login\.html$ </code> </li> 
      </ul> </p> <p>Om du inte vill indexera texten på sidor som identifieras av en URL-mask eller en URL-mask för en åtgärd, eller om du inte vill att länkarna ska följas på dessa sidor, kan du använda kommandot 
      <code>
        noindex 
      </code> och 
      <code>
        nofollow 
      </code> nyckelord. Du kan lägga till dessa nyckelord i masker med hjälp av URL-masker eller ingångspunkter. </p> <p>Se <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573" type="concept" format="dita" scope="local"> Om URL-adresser </a>. </p> <p>Se <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> Om URL-masker </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formulärnamnsmask </p> </td> 
      <td colname="col2"> <p>Identifierar formulär om 
      <code>
        &lt;form&gt; 
      </code>-taggar på dina webbsidor innehåller ett namnattribut. </p> <p>Du kan använda ett enkelt namn ( 
      <code>
        login_form 
      </code>), ett namn med jokertecken ( 
      <code>
        form* 
      </code>, eller ett reguljärt uttryck ( 
      <code>
        regexp ^.*authorize.*$ 
      </code>). </p> <p>Du kan vanligtvis lämna fältet tomt eftersom formulär vanligtvis inte har något namnattribut. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Form ID Mask </p> </td> 
      <td colname="col2"> <p>Identifierar formulär om 
      <code>
        &lt;form&gt; 
      </code>-taggar på dina webbsidor innehåller ett id-attribut. </p> <p>Du kan använda ett enkelt namn ( 
      <code>
        login_form 
      </code>), ett namn med jokertecken ( 
      <code>
        form* 
      </code>, eller ett reguljärt uttryck ( 
      <code>
        regexp ^.*authorize.*$ 
      </code>). </p> <p>Du kan vanligtvis lämna fältet tomt eftersom formulär vanligtvis inte har något namnattribut. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametrar </p> </td> 
      <td colname="col2"> <p>Identifiera formulär som innehåller, eller inte innehåller, en namngiven parameter eller en namngiven parameter med ett specifikt värde. </p> <p>Om du till exempel vill identifiera ett formulär som innehåller en e-postparameter som är förinställd på rick_brough@mydomain.com, en lösenordsparameter, men inte en förnamnsparameter, anger du följande parameterinställningar, en per rad: </p> <p> <code> email=rick_brough@mydomain.com password  not&nbsp;first-name </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Inlämning av formulär</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Åsidosätt åtgärds-URL </p> </td> 
      <td colname="col2"> <p>Ange när målet för formuläröverföringen skiljer sig från det som anges i formulärets åtgärdsattribut. </p> <p>Du kan till exempel använda det här alternativet när formuläret skickas via en JavaScript-funktion som konstruerar ett URL-värde som skiljer sig från det som finns i formuläret. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Åsidosättningsmetod </p> </td> 
      <td colname="col2"> <p>Ange när målet för formuläröverföringen skiljer sig från det som används i formulärets åtgärdsattribut och när den inskickande JavaScript-koden har ändrat metoden. </p> <p>Standardvärdena för alla formulärparametrar ( 
      <code>
        &lt;input&gt; 
      </code>-taggar, inklusive dolda fält), standardvärdet 
      <code>
        &lt;option&gt; 
      </code> från en 
      <code>
        &lt;select&gt; 
      </code>-taggen och standardtexten mellan 
      <code>
        &lt;textarea&gt;...&lt;/textarea&gt; 
      </code>-taggar) läses från webbsidan. Alla parametrar som visas i avsnittet <span class="wintitle"> Formulärinskickning </span> i fältet <span class="uicontrol"> Parametrar </span> ersätts dock med standardvärdena för formuläret. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametrar </p> </td> 
      <td colname="col2"> <p>Du kan lägga till prefix i parametrar för formulärinskickning med 
      <code>
        not 
      </code>-nyckelord. </p> <p>När du prefix en parameter med 
      <code>
        not 
      </code> skickas inte som en del av formuläröverföringen. Det här beteendet är användbart för kryssrutor som ska skickas avmarkerade. </p> <p>Anta att du vill skicka följande parametrar: </p> <p> 
      <ul id="ul_962D12BACF464FF189DB12BFAFCC93A6"> 
      <li id="li_830C6C3EC8D2448388A453BB8EDE5940"> E-postparametern med värdet 
      <code>
        nobody@mydomain.com 
      </code> </li> 
      <li id="li_905497E3FACE472DBDD49392D5B45E01"> Parametern password med värdet 
      <code>
        tryme 
      </code> </li> 
      <li id="li_AAA411708ADC464793EADF0D821E282E"> Parametern mycheckbox har avmarkerats. </li> 
      <li id="li_0D3DDE641E2B4BEF9F570C03FDB40ED2"> <p>Alla andra 
      <code>
        &lt;form&gt; 
      </code>-parametrar som standardvärden </p> </li> 
      </ul> </p> <p>Din formulärinlämningsparameter ser ut så här: </p> <p> <code> email=nobody@mydomain.com 
        password=tryme 
        not&nbsp;mycheckbox </code> </p> <p>Metodattributet för 
      <code>
        &lt;form&gt; 
      </code>-taggen på webbsidan används för att avgöra om data skickas till servern med hjälp av metoden GET eller POST. </p> <p>Om 
      <code>
        &lt;form&gt; 
      </code>-taggen innehåller inget metodattribut. Formuläret skickas med metoden GET. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Add]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en formulärdefinition {#task_9FB34E9C8A814DFE9BF7F8F8F69BF314}

Du kan redigera en befintlig formulärdefinition om ett formulär på webbplatsen har ändrats eller om du bara behöver ändra definitionen.

Observera att det inte finns någon [!DNL History]-funktion på [!DNL Form Submission]-sidan som kan återställa ändringar som du gör i en formulärdefinition.

Se till att du återskapar webbplatsindexet så att resultatet av ändringarna blir synligt för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Redigera en formulärdefinition**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]** på produktmenyn.
1. På sidan [!DNL Form Submission] klickar du på **[!UICONTROL Edit]** till höger om den formulärdefinition som du vill uppdatera.
1. På sidan [!DNL Edit Form Definition] anger du alternativen [!DNL Form Recognition] och [!DNL Form Submission].

   Se tabellen med alternativ under [Lägga till formulärdefinitioner för att indexera formulär på din webbplats](../c-about-settings-menu/c-about-crawling-menu.md#task_62FBCE9E6DBE4BDA8D1249233ADFC00F).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en formulärdefinition {#task_C350FC0CDE344F2786215D544C048B5E}

Du kan ta bort en befintlig formulärdefinition om formuläret inte längre finns på webbplatsen eller om du inte längre vill bearbeta och indexera ett visst formulär.

Observera att det inte finns någon [!DNL History]-funktion på [!DNL Form Submission]-sidan som kan återställa ändringar som du gör i en formulärdefinition.

Se till att du återskapar webbplatsindexet så att resultatet av ändringarna blir synligt för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Ta bort en formulärdefinition**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Form Submission]** på produktmenyn.
1. På sidan [!DNL Form Submission] klickar du på **[!UICONTROL Delete]** till höger om en formulärdefinition som du vill ta bort.

   Se till att du väljer rätt formulärdefinition att ta bort. Det finns ingen bekräftelsedialogruta för borttagning när du klickar på **[!UICONTROL Delete]** i nästa steg.
1. Klicka på **[!UICONTROL Delete]** på sidan [!DNL Delete Form Definition].
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om Indexanslutning {#concept_CA6921E2FBF641F9B4F60C92B32AFA84}

Använd [!DNL Index Connector] för att definiera ytterligare indatakällor för indexering av XML-sidor eller andra typer av flöden.

Du kan använda en indatakälla för dataflöden för att komma åt innehåll som lagras i ett formulär som skiljer sig från det som normalt identifieras på en webbplats med någon av de tillgängliga crawlningsmetoderna. Varje dokument som crawlas och indexeras direkt motsvarar en innehållssida på webbplatsen. En dataström kommer dock antingen från ett XML-dokument eller från en kommaavgränsad eller tabbavgränsad textfil och innehåller den innehållsinformation som ska indexeras.

En XML-datakälla består av XML-stanter, eller poster, som innehåller information som motsvarar enskilda dokument. Dessa enskilda dokument läggs till i indexet. En textmatning innehåller enskilda radavgränsade poster som motsvarar enskilda dokument. Dessa enskilda dokument läggs också till i indexet. I båda fallen beskrivs hur matningen ska tolkas i en indexanslutningskonfiguration. Varje konfiguration beskriver var filen finns och hur servrarna kommer åt den. I konfigurationen beskrivs även mappningsinformation. Det innebär att varje posts objekt används för att fylla i metadatafälten i det resulterande indexet.

När du har lagt till en indexanslutningsdefinition på sidan [!DNL Staged Index Connector Definitions] kan du ändra alla konfigurationsinställningar, *förutom* för värdena Namn och Typ.

På sidan [!DNL Index Connector] visas följande information:

* Namnet på definierade indexanslutningar som du har konfigurerat och lagt till.
* En av följande datakälltyper för varje koppling du har lagt till:

   * **Text**  - Enkla&quot;platta&quot; filer, kommaavgränsade, tabbavgränsade eller andra konsekvent avgränsade format.
   * **Feed**  - XML-flöden.
   * **XML** - Samlingar med XML-dokument.

* Anger om kopplingen är aktiverad eller inte för nästa crawl och indexering.
* Datakällans adress.

Se även [Om Index Connector](../c-about-settings-menu/c-about-crawling-menu.md#concept_CA6921E2FBF641F9B4F60C92B32AFA84)

## Så här fungerar indexeringsprocessen för konfigurationer av text och feed i Index Connector {#section_E059A33D61EE4DB0972A37B8A35E9E16}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Steg </p> </th> 
   <th colname="col2" class="entry"> <p>Process </p> </th> 
   <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Hämta datakällan. </p> </td> 
   <td colname="col3"> <p>För konfigurationer av text och feed är det en enkel filhämtning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Dela upp den hämtade datakällan i enskilda pseudodokument. </p> </td> 
   <td colname="col3"> <p>För <span class="uicontrol"> text </span> motsvarar varje radavgränsad textrad ett enskilt dokument och tolkas med den angivna avgränsaren, till exempel ett komma eller en tabb. </p> <p>För <span class="uicontrol">-feed </span> extraheras data för varje dokument med hjälp av ett mönster för reguljära uttryck i följande format: </p> <p> <code> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Skapa en cachelagrad kopia av data och skapa sedan en lista med länkar för crawlern med hjälp av <span class="uicontrol"> Map </span> på sidan <span class="wintitle"> Index Connector Add </span>. Data lagras i en lokal cache och fylls i med de konfigurerade fälten. </p> <p>De tolkade data skrivs till det lokala cacheminnet. </p> <p>Cachen läses senare för att skapa de enkla HTML-dokument som crawlern behöver. Exempel: </p> <p> <code> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p><span class="codeph"> &lt;title&gt; </span>-elementet genereras bara när det finns en mappning till metadatafältet Rubrik. På samma sätt genereras <span class="codeph"> &lt;body&gt; </span>-elementet endast när det finns en mappning till body-metadatafältet. </p> <p> <b>Viktigt</b>: Det finns inget stöd för tilldelning av värden till den fördefinierade URL-meta-taggen. </p> <p>För alla andra mappningar genereras <span class="codeph"> &lt;meta&gt; </span>-taggar för varje fält som innehåller data i det ursprungliga dokumentet. </p> <p>Fälten för varje dokument läggs till i cachen. För varje dokument som skrivs till cachen skapas även en länk enligt följande exempel: </p> <p> <code> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>Konfigurationens mappning måste ha ett fält som identifieras som primärnyckel. Den här mappningen utgör nyckeln som används när data hämtas från cachen. </p> <p>Crawlningen känner igen URL:en <span class="codeph">-index: </span>-schemaprefix, som sedan kan komma åt lokalt cachelagrade data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Crawla den cachelagrade dokumentuppsättningen. </p> </td> 
   <td colname="col3"> <p>Indexvärdet <span class="codeph">: </span>-länkar läggs till i crawlerns väntande lista och bearbetas i den normala crawlningssekvensen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Bearbeta varje dokument. </p> </td> 
   <td colname="col3"> <p>Nyckelvärdet för varje länk motsvarar en post i cachen, så om du crawlar varje länk hämtas dokumentets data från cachen. Sedan"sammanfogas" den till en HTML-bild som bearbetas och läggs till i indexet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Så här fungerar indexeringsprocessen för XML-konfigurationer i Index Connector {#section_7F1551EA51854C5C99F284CE260526EB}

Indexeringsprocessen för XML-konfigurationen liknar processen för text- och flödeskonfigurationer med följande mindre ändringar och undantag.

Eftersom dokumenten för XML-crawlningar redan är separerade till enskilda filer, gäller inte steg 1 och 2 i tabellen ovan direkt. Om du anger en URL i fälten **[!UICONTROL Host Address]** och **[!UICONTROL File Path]** på sidan [!DNL Index Connector Add] hämtas den och behandlas som ett vanligt HTML-dokument. Förväntningen är att det hämtade dokumentet innehåller en samling `<a href="{url}"...`-länkar, som alla pekar på ett XML-dokument som bearbetas. Sådana länkar konverteras till följande format:

```
<a href="index:<ic_config_name>?url="{url}">
```

Om Adobe-inställningarna till exempel returnerade följande länkar:

```
<a href="https://www.adobe.com/somepath/doc1.xml">doc 1</a> 
<a href="https://www.adobe.com/otherpath/doc2.xml">doc 2</a>
```

I tabellen ovan gäller inte steg 3 och steg 4 slutförs vid crawlning och indexering.

Du kan också blanda XML-dokument med andra dokument som har identifierats naturligt under crawlningsprocessen. I sådana fall kan du använda omskrivningsregler ( **[!UICONTROL Settings]** > **[!UICONTROL Rewrite Rules]** > **[!UICONTROL Crawl List Retrieve URL Rules]**) för att ändra XML-dokumentens URL:er så att de dirigeras till Index Connector.

Se [Om Hämta URL-regler för crawllista](../c-about-settings-menu/c-about-rewrite-rules-menu.md#concept_EC8E2E48B99A458D8567B526C9827CBA).

Anta att du har följande regel för omskrivning:

```
RewriteRule (^http.*[.]xml$) index:Adobe?key=$1
```

Den här regeln översätter alla URL:er som slutar med `.xml` till en indexkopplingslänk. Crawlningen känner igen och skriver om URL-schemat `index:`. Hämtningsprocessen dirigeras om via Index Connector Apache-servern på den primära servern. Varje nedladdat dokument granskas med samma mönster för reguljära uttryck som används med Feeds. I det här fallet sparas dock inte det tillverkade HTML-dokumentet i cachen. I stället skickas den direkt till crawlern för indexbearbetning.

## Konfigurera flera indexanslutningar {#section_C2B14C0F06354A57AEF6238FF3814E5D}

Du kan definiera flera Index Connector-konfigurationer för vilket konto som helst. Konfigurationerna läggs automatiskt till i listrutan i **[!UICONTROL Settings]** > **[!UICONTROL Crawl]** > **[!UICONTROL URL Entrypoints]** enligt följande bild:

![](assets/url_entrypoints_index_connector.png)

Om du väljer en konfiguration i listrutan läggs värdet till i slutet av listan med URL-startpunkter.

>[!NOTE]
>
>Även om inaktiverade Index Connector-konfigurationer läggs till i listrutan kan du inte välja dem. Om du väljer samma indexanslutarkonfiguration en andra gång läggs den till i slutet av listan och den föregående instansen tas bort.

Om du vill ange en indexkopplingspunkt för en stegvis crawlning kan du lägga till poster i följande format:

```
index:<indexconnector_configuration_name>
```

Crawlningen bearbetar varje tillagd post om den finns på sidan Indexanslutningar och är aktiverad.

Obs! Eftersom varje dokuments URL skapas med hjälp av konfigurationsnamnet för indexkoppling och dokumentets primärnyckel, måste du använda samma konfigurationsnamn för indexkoppling när du utför stegvisa uppdateringar. Om du gör det kan [!DNL Adobe Search&Promote] uppdatera tidigare indexerade dokument korrekt.

Se även [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

**Användning av Setup Maps när du lägger till en Index Connector**

När du lägger till en Index Connector kan du välja att använda funktionen **[!UICONTROL Setup Maps]** för att hämta ett exempel på datakällan. Uppgifterna undersöks för indexering av lämplighet.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Om du valde typen Indexanslutning.. </p> </th> 
   <th colname="col2" class="entry"> <p>Funktionen Konfigurera kartor.. </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Text </p> </td> 
   <td colname="col2"> <p>Avgör avgränsarvärdet genom att prova tabbar först och sedan lodräta staplar ( <span class="codeph">) | </span>) och finally-kommatecken ( <span class="codeph">, </span>). Om du redan har angett ett avgränsningsvärde innan du klickade på <span class="uicontrol"> Setup Maps </span>, används det värdet i stället. </p> <p>Det bästa schemat för anpassning gör att kartfälten fylls i med gissningar på rätt tagg- och fältvärden. Dessutom visas en sampling av tolkade data. Se till att du väljer <span class="uicontrol"> Rubriker i första raden </span> om du vet att filen innehåller en rubrikrad. Installationsfunktionen använder den här informationen för att bättre identifiera de resulterande mappningsposterna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Hämtar datakällan och utför enkel XML-tolkning. </p> <p>De resulterande XPath-identifierarna visas i taggraderna i tabellen Map och liknande värden i Fält. Dessa rader identifierar bara tillgängliga data och genererar inte de mer komplicerade XPath-definitionerna. Det är dock fortfarande användbart eftersom det beskriver XML-data och identifierar ItemTag-värden. </p> <p> <p>Obs!  Funktionen Setup Maps hämtar hela XML-källan för att utföra analysen. Om filen är stor kan timeout uppstå för den här åtgärden. </p> </p> <p>När det är klart identifierar den här funktionen alla möjliga XPath-objekt, varav många inte är lämpliga att använda. Se till att du undersöker de resulterande kartdefinitionerna och tar bort dem som du inte behöver eller vill ha. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>XML </p> </td> 
   <td colname="col2"> <p>Hämtar URL:en för ett representativt enskilt dokument, inte den primära länklistan. Det här dokumentet tolkas på samma sätt som i Feeds, och resultatet visas. </p> <p>Innan du klickar på <span class="uicontrol"> Lägg till </span> för att spara konfigurationen måste du ändra URL:en tillbaka till listdokumentet för den primära länken. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Viktigt**: Funktionen Setup Maps fungerar kanske inte för stora XML-datauppsättningar eftersom filparsern försöker läsa hela filen i minnet. Det kan leda till att minnet tar slut. Men när samma dokument bearbetas vid indexeringen läses det inte in i minnet. I stället bearbetas stora dokument &quot;i farten&quot; och läses inte in helt i minnet först.

**Användning av Förhandsgranska när du lägger till en indexkoppling**

När du lägger till en Index Connector kan du använda funktionen **[!UICONTROL Preview]** för att validera data, som om du sparade dem. Den kör ett test mot konfigurationen, men utan att spara konfigurationen till kontot. Testet kommer åt den konfigurerade datakällan. Hämtningscachen skrivs dock till en tillfällig plats. den inte hamnar i konflikt med huvudcachemappen som används av indexeringscrawlern.

I Förhandsgranska bearbetas bara standardvärdena för fem dokument enligt funktionen Act:IndexConnector-Preview-Max-Documents. De förhandsvisade dokumenten visas i källformat när de presenteras för indexeringscrawlaren. Visningen liknar funktionen Visa källa i en webbläsare. Du kan navigera bland dokumenten i förhandsvisningsuppsättningen med hjälp av standardnavigeringslänkar.

Förhandsgranskningen stöder inte XML-konfigurationer eftersom sådana dokument bearbetas direkt och inte hämtas till cachen.

## Lägga till en indexanslutningsdefinition {#task_96779B651A654E1F871F55D6DBBC8886}

Varje konfiguration av Index Connector definierar en datakälla och mappningar som relaterar dataobjekten som definierats för den källan till metadatafälten i indexet.

Innan effekterna av den nya och aktiverade definitionen är synliga för kunderna ska du återskapa platsindexet.

**Lägga till en indexanslutningsdefinition**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Index Connector]** på sidan [!DNL Stage Index Connector Definitions].
1. På sidan [!DNL Index Connector Add] anger du önskade anslutningsalternativ. Vilka alternativ som är tillgängliga beror på **[!UICONTROL Type]** som du har valt.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Namn </p> </td> 
      <td colname="col2"> <p>Det unika namnet på konfigurationen för indexkoppling. Du kan använda alfanumeriska tecken. Tecknen"_" och"-" är också tillåtna. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Typ </p> </td> 
      <td colname="col2"> <p>Källan till dina data. Datakälltypen som du väljer påverkar de alternativ som är tillgängliga på sidan <span class="wintitle"> Lägg till </span> indexkoppling. Du kan välja mellan följande: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Text  </span> <p>Enkla platta textfiler, kommaavgränsade, tabbavgränsade eller andra konsekvent avgränsade format. Varje radavgränsad textrad motsvarar ett enskilt dokument och tolkas med den angivna avgränsaren. </p> <p>Du kan mappa varje värde, eller kolumn, till ett metadatafält, som kolumnnumret refererar till, med början vid 1 (ett). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed  </span> <p>Hämtar ett primärt XML-dokument som innehåller flera "rader" med information. </p> </li> 
      <li id="li_5A61C53522D74D4C9A5F65989604BDEF"> <span class="uicontrol"> XML  </span> <p>Hämtar ett primärt XML-dokument som innehåller länkar ( 
      <code>
        &lt;a&gt; 
      </code>) till enskilda XML-dokument. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datakälltyp: Text</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiverad </p> </td> 
      <td colname="col2"> <p>Aktiverar konfigurationen till crawl och index. Du kan även inaktivera konfigurationen för att förhindra crawlning och indexering. </p> <p> <b>Obs</b>: Inaktiverade Index Connector-konfigurationer ignoreras om de finns i en entrypoint-lista. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Värdadress </p> </td> 
      <td colname="col2"> <p>Anger adressen till servervärden där data finns. </p> <p>Om du vill kan du ange en fullständig URI (Uniform Resource Identifier)-sökväg till datakälldokumentet som i följande exempel: </p> <p> <code> https://www.somewhere.com/some_path/some_file.xml </code> </p> <p>eller </p> <p> <code> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.xml </code> </p> <p>URI:n delas upp i lämpliga poster för fälten Värdadress, Filsökväg, Protokoll och, eventuellt, Användarnamn och Lösenord. </p> <p>Anger IP-adressen eller URL-adressen för värdsystemet där datakällfilen finns. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till den enkla platta textfilen, kommaavgränsad, tabbavgränsad eller annan fil med konsekvent avgränsat format. </p> <p>Sökvägen är relativ till värdadressens rot. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkrementell filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till den enkla platta textfilen, kommaavgränsad, tabbavgränsad eller annan fil med konsekvent avgränsat format. </p> <p>Sökvägen är relativ till värdadressens rot. </p> <p>Den här filen hämtas och bearbetas under inkrementella indexåtgärder, om den anges. Om ingen fil anges används filen under Filsökväg i stället. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lodrät filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till den enkla platta textfilen, kommaavgränsad, tabbavgränsad eller annan konsekvent avgränsad formatfil som ska användas vid en lodrät uppdatering. </p> <p>Sökvägen är relativ till värdadressens rot. </p> <p>Den här filen hämtas och bearbetas under Lodrät uppdatering, om den har angetts. </p> <p> <b>Obs</b>: Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera funktionen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tar bort filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till den enkla platta textfilen, som innehåller ett enda dokumentidentifierarvärde per rad. </p> <p>Sökvägen är relativ till värdadressens rot. </p> <p>Den här filen hämtas och bearbetas under inkrementella indexåtgärder, om den anges. De värden som hittas i den här filen används för att skapa"delete"-begäranden för att ta bort tidigare indexerade dokument. Värdena i den här filen måste motsvara de värden som finns i den fullständiga eller inkrementella filsökvägen, i kolumnen <span class="uicontrol"> primärnyckel </span>. </p> <p> <b>Obs</b>: Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera funktionen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Anger det protokoll som används för att komma åt filen. Du kan välja mellan följande: </p> <p> 
      <ul id="ul_F6BC10FD51CA4A1D855B2B3212838A9C"> 
      <li id="li_79FB7DC65E774ABBB23E57BF98AD9738"> HTTP <p>Om det behövs kan du ange korrekta autentiseringsuppgifter för att få åtkomst till HTTP-servern. </p> </li> 
      <li id="li_BAA9AD5E4B014E09B3A66C94022B7225"> HTTPS <p>Om det behövs kan du ange korrekta autentiseringsuppgifter för att få åtkomst till HTTPS-servern. </p> </li> 
      <li id="li_E716ABB169DD408BA91F1CA27F445A16"> FTP <p>Du måste ange korrekta autentiseringsuppgifter för att komma åt FTP-servern. </p> </li> 
      <li id="li_FD7143019C5244C3B8A5B1B5AA84859A"> SFTP <p>Du måste ange korrekta autentiseringsuppgifter för att komma åt SFTP-servern. </p> </li> 
      <li id="li_38E0036C1365419F9D00083CACA34AFB"> Fil </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Timeout </p> </td> 
      <td colname="col2"> <p>Anger timeout i sekunder för FTP-, SFTP-, HTTP- eller HTTPS-anslutningar. Värdet måste vara mellan 30 och 300. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Försök igen </p> </td> 
      <td colname="col2"> <p>Anger maximalt antal försök för misslyckade FTP-, SFTP-, HTTP- eller HTTPS-anslutningar. Värdet måste vara mellan 0 och 10. </p> <p>Värdet noll (0) förhindrar försök igen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kodning </p> </td> 
      <td colname="col2"> <p>Anger det teckenkodningssystem som används i den angivna datakällfilen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Avgränsare </p> </td> 
      <td colname="col2"> <p>Anger det tecken som du vill använda för att avgränsa varje fält i den angivna datakällfilen. </p> <p>Kommatecknet ( <span class="codeph">, </span>) är ett exempel på en avgränsare. Kommatecknet fungerar som en fältavgränsare som hjälper till att separera datafält i den angivna datakällfilen. </p> <p>Välj fliken <span class="uicontrol">? </span> om du vill använda det vågräta tabbtecknet som avgränsare. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rubriker i första raden </p> </td> 
      <td colname="col2"> <p>Anger att den första raden i datakällfilen endast innehåller rubrikinformation, inte data. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minsta antal dokument för indexering </p> </td> 
      <td colname="col2"> <p>Om det anges med ett positivt värde anger detta det minsta antalet poster som förväntas i den hämtade filen. Om färre poster tas emot avbryts indexåtgärden. </p> <p> <b>Obs</b>: Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera funktionen. </p> <p> <b>Obs</b>: Den här funktionen används endast vid fullständiga indexåtgärder. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Karta </p> </td> 
      <td colname="col2"> <p>Anger mappningar kolumn-till-metadata med kolumnnummer. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Kolumn  </span> <p> Anger ett kolumnnummer med den första kolumnen som 1 (ett). Om du vill lägga till nya mappningsrader för varje kolumn, under <span class="wintitle"> Åtgärd </span>, klickar du på <span class="uicontrol"> + </span>. </p> <p>Du behöver inte referera till varje kolumn i datakällan. I stället kan du välja att hoppa över värden. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Fält  </span> <p>Definierar det name-attributvärde som används för varje genererad &lt;meta&gt;-tagg. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadata?  </span> <p>Gör att <span class="uicontrol">-fältet </span> blir en listruta där du kan välja definierade metadatafält för det aktuella kontot. </p> <p>Värdet för <span class="uicontrol">-fältet </span> kan vid behov vara ett odefinierat metadatafält. Ett odefinierat metadatafält är ibland användbart för att skapa innehåll som används av <span class="wintitle"> Filtreringsskript </span>. </p> <p>Se <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Om att filtrera skript </a>. </p> <p>När Index Connector bearbetar XML-dokument med flera träffar i ett kartfält sammanfogas de olika värdena till ett enda värde i det cachelagrade dokumentet. Som standard kombineras dessa värden med en kommaavgränsare. Anta dock att motsvarande <span class="wintitle">-fältvärde </span> är ett definierat metadatafält. Dessutom har fältet attributuppsättningen <span class="wintitle"> Tillåtelselista </span>. I det här fallet används fältets listavgränsarvärde, som är den första avgränsaren som definieras, i sammanfogningen. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Primärnyckel?  </span> <p>Endast en kartdefinition identifieras som primärnyckel. Det här fältet blir den unika referens som visas när dokumentet läggs till i indexet. Det här värdet används i dokumentets URL i indexet. </p> <p>Värdena <span class="uicontrol"> för primärnyckeln </span> måste vara unika för alla dokument som representeras av konfigurationen för indexkoppling. Eventuella dubbletter som påträffas ignoreras. Om källdokumenten inte innehåller ett enda unikt värde att använda som <span class="uicontrol"> primärnyckel </span>, men två eller flera fält tillsammans <i>kan</i> vara en unik identifierare, kan du definiera primärnyckeln <span class="uicontrol"> </span> genom att kombinera flera <span class="uicontrol"> kolumnvärden </span> med ett lodrätt fält ("|") som avgränsar värdena. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> Ta bort HTML?  </span> <p>När det här alternativet är markerat tas alla HTML-taggar som finns i fältets data bort. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Åtgärd  </span> <p>Gör att du kan lägga till rader på kartan eller ta bort rader från kartan. Radernas ordning är inte viktig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datakälltyp: Feed</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiverad </p> </td> 
      <td colname="col2"> <p>Aktiverar konfigurationen till crawl och index. Du kan även inaktivera konfigurationen för att förhindra crawlning och indexering. </p> <p> <b>Obs</b>: Inaktiverade Index Connector-konfigurationer ignoreras om de finns i en entrypoint-lista. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Värdadress </p> </td> 
      <td colname="col2"> <p>Anger IP-adressen eller URL-adressen för värdsystemet där datakällfilen finns. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till det primära XML-dokumentet som innehåller flera "rader" med information. </p> <p>Sökvägen är relativ till värdadressens rot. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkrementell filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till det inkrementella XML-dokumentet som innehåller flera "rader" med information. </p> <p>Sökvägen är relativ till värdadressens rot. </p> <p>Den här filen hämtas och bearbetas under inkrementella indexåtgärder, om den anges. Om ingen fil anges används filen under Filsökväg i stället. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lodrät filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till XML-dokumentet som innehåller flera "rader" med sparse-information som ska användas under en lodrät uppdatering. </p> <p>Sökvägen är relativ till värdadressens rot. </p> <p>Den här filen hämtas och bearbetas under Lodrät uppdatering, om den har angetts. </p> <p> <b>Obs</b>: Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera funktionen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tar bort filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till den enkla platta textfilen, som innehåller ett enda dokumentidentifierarvärde per rad. </p> <p>Sökvägen är relativ till värdadressens rot. </p> <p>Den här filen hämtas och bearbetas under inkrementella indexåtgärder, om den anges. De värden som hittas i den här filen används för att skapa"delete"-begäranden för att ta bort tidigare indexerade dokument. Värdena i den här filen måste motsvara de värden som finns i den fullständiga eller inkrementella filsökvägen, i kolumnen <span class="uicontrol"> primärnyckel </span>. </p> <p> <b>Obs</b>: Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera funktionen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Anger det protokoll som används för att komma åt filen. Du kan välja mellan följande: </p> <p> 
      <ul id="ul_976A34FD14A841F2B610C1C0CCBB82B9"> 
      <li id="li_05BBA0F670F14431A89AE4178F1A6F94"> HTTP <p>Om det behövs kan du ange korrekta autentiseringsuppgifter för att få åtkomst till HTTP-servern. </p> </li> 
      <li id="li_100446691F304572B8FC3F083F86A2CB"> HTTPS <p>Om det behövs kan du ange korrekta autentiseringsuppgifter för att få åtkomst till HTTPS-servern. </p> </li> 
      <li id="li_027088A8E30444DAA8CCCC5B0BAA74C1"> FTP <p>Du måste ange korrekta autentiseringsuppgifter för att komma åt FTP-servern. </p> </li> 
      <li id="li_DCEF9D5C99354990B03E29083C2ED8DC"> SFTP <p>Du måste ange korrekta autentiseringsuppgifter för att komma åt SFTP-servern. </p> </li> 
      <li id="li_44E34FF2AB0D429EB3408106E6FCF780"> Fil </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>ItemTagg </p> </td> 
      <td colname="col2"> <p>Identifierar XML-elementet som du kan använda för att identifiera enskilda XML-rader i datakällfilen som du har angett. </p> <p>I följande feed-fragment av ett XML-dokument i Adobe är ItemTag-värdet <span class="codeph"> post </span>: </p> <p> <code> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt;&lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt;         &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt;         &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt;         &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
        &lt;/record&gt; 
        ... 
        &lt;record&gt; 
        ... 
        &lt;/record&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/group&gt; 
        &lt;/gsafeed&gt; 
        </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minsta antal dokument för indexering </p> </td> 
      <td colname="col2"> <p>Om det anges med ett positivt värde anger detta det minsta antalet poster som förväntas i den hämtade filen. Om färre poster tas emot avbryts indexåtgärden. </p> <p> <b>Obs</b>: Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera funktionen. </p> <p> <b>Obs</b>: Den här funktionen används endast vid fullständiga indexåtgärder. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Karta </p> </td> 
      <td colname="col2"> <p>Gör att du kan ange mappningar av XML-element-till-metadata med XPath-uttryck. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tagg  </span> <p>Anger en XPath-representation av tolkade XML-data. Med exempeldokumentet Adobe XML ovan, under alternativet Item-tag, kan det mappas med följande syntax: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
      /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
      /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>Syntaxen ovan innebär följande: </p> <p> 
      <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
      <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p><span class="codeph"> displayURL </span>-attributet för <span class="codeph">-posten </span>-element mappar till metadatafältet <span class="codeph"> page-url </span>. </p> </li> 
      <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p><span class="codeph"> content </span>-attributet för alla <span class="codeph">-metaelement </span> som finns inuti ett <span class="codeph"> metadata </span>-element, som finns inuti en <span class="codeph">-post </span>-element, vars namnattribut är <span class="codeph"> title </span>, mappar till metadatafältet <span class="codeph"> title </span>. </p> </li> 
      <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p><span class="codeph"> content </span>-attributet för alla <span class="codeph">-metaelement </span> som finns i ett <span class="codeph"> metadata </span>-element, som finns inuti <span class="codeph">-posten </span>-element, vars name-attribut är <span class="codeph"> description </span>, mappar till metadatafältet <span class="codeph"> desc &lt;a1 1/&gt;.</span> </p> </li> 
      <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p><span class="codeph"> content </span>-attributet för alla <span class="codeph">-metaelement </span> som finns i ett <span class="codeph"> metadata </span>-element, som finns i <span class="codeph">-elementet </span>, vars namnattribut är <span class="codeph"> description </span>, mappas till metadatafältet <span class="codeph"> body </span>. </p> </li> 
      </ul> </p> <p>XPath är en relativt komplicerad notation. Mer information finns på följande plats: </p> <p>Se <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Fält  </span> <p>Definierar det name-attributvärde som används för varje genererad <span class="codeph"> &lt;meta&gt; </span>-tagg. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadata?  </span> <p>Gör att <span class="uicontrol">-fältet </span> blir en listruta där du kan välja definierade metadatafält för det aktuella kontot. </p> <p>Värdet för <span class="uicontrol">-fältet </span> kan vid behov vara ett odefinierat metadatafält. Ett odefinierat metadatafält är ibland användbart för att skapa innehåll som används av <span class="wintitle"> Filtreringsskript </span>. </p> <p>Se <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Om att filtrera skript </a>. </p> <p>När Index Connector bearbetar XML-dokument med flera träffar i ett kartfält sammanfogas de olika värdena till ett enda värde i det cachelagrade dokumentet. Som standard kombineras dessa värden med en kommaavgränsare. Anta dock att motsvarande <span class="wintitle">-fältvärde </span> är ett definierat metadatafält. Dessutom har fältet attributuppsättningen <span class="wintitle"> Tillåtelselista </span>. I det här fallet används fältets listavgränsarvärde, som är den första avgränsaren som definieras, i sammanfogningen. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Primärnyckel?  </span> <p>Endast en kartdefinition identifieras som primärnyckel. Det här fältet blir den unika referens som visas när dokumentet läggs till i indexet. Det här värdet används i dokumentets URL i indexet. </p> <p>Värdena <span class="uicontrol"> för primärnyckeln </span> måste vara unika för alla dokument som representeras av konfigurationen för indexkoppling. Eventuella dubbletter som påträffas ignoreras. Om källdokumenten inte innehåller ett enda unikt värde att använda som <span class="uicontrol"> primärnyckel </span>, men två eller flera fält tillsammans <i>kan</i> vara en unik identifierare, kan du definiera primärnyckeln <span class="uicontrol"> </span> genom att kombinera flera <span class="uicontrol">-taggdefinitioner </span> med ett lodrätt fält ("|") som avgränsar värdena. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC81F"> <span class="uicontrol"> Ta bort HTML?  </span> <p>När det här alternativet är markerat tas alla HTML-taggar som hittas i fältets data bort. </p> </li> 
      <li id="li_5E829D1D0DBD4BB7AAB5DB983053D248"> <span class="uicontrol"> Används för att ta bort?  </span> <p>Används endast vid inkrementella indexåtgärder. Poster som matchar detta XPath-mönster identifierar objekt som ska tas bort. Värdet <span class="uicontrol"> för primärnyckeln </span> för varje sådan post används för att skapa borttagningsbegäranden, som med Ta bort filsökväg. </p> <p> <b>Obs</b>: Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera funktionen. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Åtgärd  </span> <p>Gör att du kan lägga till rader på kartan eller ta bort rader från kartan. Radernas ordning är inte viktig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datakälltyp: XML</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiverad </p> </td> 
      <td colname="col2"> <p>Aktiverar konfigurationen till crawl och index. Du kan även inaktivera konfigurationen för att förhindra crawlning och indexering. </p> <p> <b>Obs</b>: Inaktiverade Index Connector-konfigurationer ignoreras om de finns i en entrypoint-lista. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Värdadress </p> </td> 
      <td colname="col2"> <p>Anger URL-adressen till värdsystemet där datakällfilen finns. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till det primära XML-dokumentet som innehåller länkar ( 
      <code>
        &lt;a&gt; 
      </code>) till enskilda XML-dokument. </p> <p>Sökvägen är relativ till värdadressens rot. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Protokoll </p> </td> 
      <td colname="col2"> <p>Anger det protokoll som används för att komma åt filen. Du kan välja mellan följande: </p> <p> 
      <ul id="ul_EA4EB7953D68483FAD75753B2EE70E74"> 
      <li id="li_537F24C6B2AB435CB7C14117663D7B3F"> HTTP <p>Om det behövs kan du ange korrekta autentiseringsuppgifter för att få åtkomst till HTTP-servern. </p> </li> 
      <li id="li_8C13C93C52364FFA8B9B18830CDB223C"> HTTPS <p>Om det behövs kan du ange korrekta autentiseringsuppgifter för att få åtkomst till HTTPS-servern. </p> </li> 
      <li id="li_2F967B5675254C949B31EAB19910751C"> FTP <p>Du måste ange korrekta autentiseringsuppgifter för att komma åt FTP-servern. </p> </li> 
      <li id="li_C24BE4C1DE79488AA64C7133D78CD3A6"> SFTP <p>Du måste ange korrekta autentiseringsuppgifter för att komma åt SFTP-servern. </p> </li> 
      <li id="li_7581C21CFC104986A361F62BD7A370C1"> Fil </li> 
      </ul> </p> <p> <b>Obs</b>: Protokollinställningen används endast när det finns information angiven i fälten Värdadress och/eller Sökväg. Enskilda XML-dokument hämtas antingen via HTTP eller HTTPS, enligt deras URL-specifikationer. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>ItemTagg </p> </td> 
      <td colname="col2"> <p>Identifierar XML-elementet som definierar en "rad" i datakällfilen som du angav. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Karta </p> </td> 
      <td colname="col2"> <p>Här kan du ange mappningar kolumn-till-metadata med kolumnnummer. </p> <p> 
      <ul id="ul_06F50CBA0AA64C7CB1AFAE076E629A64"> 
      <li id="li_0FA2502869BA40DC93D790B79E15A9D2"> <span class="uicontrol"> Tagg  </span> <p>Anger en XPath-representation av tolkade XML-data. Med exempeldokumentet Adobe XML ovan, under alternativet Item-tag, kan du mappa det med följande syntax: </p> <p> <code> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>Syntaxen ovan innebär följande: </p> <p> 
      <ul id="ul_F8C536E6E54546D9AA5B22B879C0AF39"> 
      <li id="li_78A35DFFF1B4496CAC6EDC7B1E991F29"> <code> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p><span class="codeph"> displayURL </span>-attributet för <span class="codeph">-posten </span>-element mappar till metadatafältet <span class="codeph"> page-url </span>. </p> </li> 
      <li id="li_FA7DF3D1942248B98660F3D0C82F4563"> <code> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p><span class="codeph"> content </span>-attributet för alla <span class="codeph">-metaelement </span> som finns inuti ett <span class="codeph"> metadata </span>-element, som finns inuti en <span class="codeph">-post </span>-element, vars namnattribut är <span class="codeph"> title </span>, mappar till metadatafältet <span class="codeph"> title </span>. </p> </li> 
      <li id="li_D8000A116FF84DE59ED19C656DDD3BC1"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p><span class="codeph"> content </span>-attributet för alla <span class="codeph">-metaelement </span> som finns i ett <span class="codeph"> metadata </span>-element, som finns inuti <span class="codeph">-posten </span>-element, vars name-attribut är <span class="codeph"> description </span>, mappar till metadatafältet <span class="codeph"> desc &lt;a1 1/&gt;.</span> </p> </li> 
      <li id="li_7FA6A53DFD3D42A98B7BA17CC29DDB81"> <code> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p><span class="codeph"> content </span>-attributet för alla <span class="codeph">-metaelement </span> som finns i ett <span class="codeph"> metadata </span>-element, som finns i <span class="codeph">-elementet </span>, vars namnattribut är <span class="codeph"> description </span>, mappas till metadatafältet <span class="codeph"> body </span>. </p> </li> 
      </ul> </p> <p>XPath är en relativt komplicerad notation. Mer information finns på följande plats: </p> <p>Se <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_84999D07E0AE4265BC7928BBB49957B9"> <span class="uicontrol"> Fält  </span> <p>Definierar det name-attributvärde som används för varje genererad &lt;meta&gt;-tagg. </p> </li> 
      <li id="li_E125788D0F5242958BD790E26A675C20"> <span class="uicontrol"> Metadata?  </span> <p>Gör att <span class="uicontrol">-fältet </span> blir en listruta där du kan välja definierade metadatafält för det aktuella kontot. </p> <p>Värdet för <span class="uicontrol">-fältet </span> kan vid behov vara ett odefinierat metadatafält. Ett odefinierat metadatafält är ibland användbart för att skapa innehåll som används av <span class="wintitle"> Filtreringsskript </span>. </p> <p>Se <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Om att filtrera skript </a>. </p> <p>När Index Connector bearbetar XML-dokument med flera träffar i ett kartfält sammanfogas de olika värdena till ett enda värde i det cachelagrade dokumentet. Som standard kombineras dessa värden med en kommaavgränsare. Anta dock att motsvarande <span class="wintitle">-fältvärde </span> är ett definierat metadatafält. Dessutom har fältet attributuppsättningen <span class="wintitle"> Tillåtelselista </span>. I det här fallet används fältets listavgränsarvärde, som är den första avgränsaren som definieras, i sammanfogningen. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824609F"> <span class="uicontrol"> Primärnyckel?  </span> <p>Endast en kartdefinition identifieras som primärnyckel. Det här fältet blir den unika referens som visas när dokumentet läggs till i indexet. Det här värdet används i dokumentets URL i indexet. </p> <p>Värdena <span class="uicontrol"> för primärnyckeln </span> måste vara unika för alla dokument som representeras av konfigurationen för indexkoppling. Eventuella dubbletter som påträffas ignoreras. Om källdokumenten inte innehåller ett enda unikt värde att använda som <span class="uicontrol"> primärnyckel </span>, men två eller flera fält tillsammans <i>kan</i> vara en unik identifierare, kan du definiera primärnyckeln <span class="uicontrol"> </span> genom att kombinera flera <span class="uicontrol">-taggdefinitioner </span> med ett lodrätt fält ("|") som avgränsar värdena. </p> </li> 
      <li id="li_9F435EFB3EC74B409EC82A851824610G"> <span class="uicontrol"> Ta bort HTML?  </span> <p>När det här alternativet är markerat tas alla HTML-taggar som hittas i fältets data bort. </p> </li> 
      <li id="li_6302D18971AD439FBECE27742649C56B"> <span class="uicontrol"> Åtgärd  </span> <p>Gör att du kan lägga till rader på kartan eller ta bort rader från kartan. Radernas ordning är inte viktig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Valfritt) Klicka på **[!UICONTROL Setup Maps]** om du vill hämta ett exempel på datakällan. Uppgifterna undersöks för indexering av lämplighet. Den här funktionen är endast tillgänglig för text- och matningstyper.
1. (Valfritt) Klicka på **[!UICONTROL Preview]** för att testa hur konfigurationen fungerar. Den här funktionen är endast tillgänglig för text- och matningstyper.
1. Klicka på **[!UICONTROL Add]** för att lägga till konfigurationen på sidan [!DNL Index Connector Definitions] och i listrutan [!DNL Index Connector Configurations] på sidan [!DNL URL Entrypoints].

   Se [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).
1. Klicka på **[!UICONTROL rebuild your staged site index]** på sidan [!DNL Index Connector Definitions].
1. (Valfritt) Gör något av följande på sidan [!DNL Index Connector Definitions]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en indexanslutningsdefinition {#task_DCFC9C6A9964421DB5AB6C25DEE98DE9}

Du kan redigera en befintlig Index Connector som du har definierat.

>[!NOTE]
>
>Det finns inte alla alternativ som du kan ändra, till exempel namnet på indexkopplingen eller typen i listrutan [!DNL Type].

**Så här redigerar du en definition för en indexkoppling**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]** på produktmenyn.
1. På sidan [!DNL Index Connector], under kolumnrubriken [!DNL Actions], klickar du på **[!UICONTROL Edit]** för ett definitionsnamn för Index Connector vars inställningar du vill ändra.
1. Ange önskade alternativ på sidan [!DNL Index Connector Edit].

   Se tabellen med alternativ under [Lägga till en indexanslutningsdefinition](../c-about-settings-menu/c-about-crawling-menu.md#task_96779B651A654E1F871F55D6DBBC8886).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) På sidan [!DNL Index Connector Definitions] klickar du på **[!UICONTROL rebuild your staged site index]**.
1. (Valfritt) Gör något av följande på sidan [!DNL Index Connector Definitions]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Visa inställningarna för en indexanslutningsdefinition {#task_D0B71A7426E54247BDB3468EC576D871}

Du kan granska konfigurationsinställningarna för en befintlig indexanslutningsdefinition.

När en definition av Indexanslutning har lagts till på sidan [!DNL Index Connector Definitions] kan du inte ändra dess typinställning. I stället måste du ta bort definitionen och sedan lägga till en ny.

**Så här visar du inställningarna för en indexanslutningsdefinition**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]** på produktmenyn.
1. På sidan [!DNL Index Connector], under kolumnrubriken [!DNL Actions], klickar du på **[!UICONTROL Edit]** för ett definitionsnamn för Index Connector vars inställningar du vill granska eller redigera.

## Kopiera en indexanslutningsdefinition {#task_3AD55DF07FC44A748D0EFDAB7B35699B}

Du kan kopiera en befintlig Index Connector-definition som ska användas som bas för en ny Index Connector som du vill skapa.

När du kopierar en indexanslutningsdefinition är den kopierade definitionen inaktiverad som standard. Om du vill aktivera eller aktivera definitionen måste du redigera den på sidan [!DNL Index Connector Edit] och välja **[!UICONTROL Enable]**.

Se [Redigera en indexanslutningsdefinition](../c-about-settings-menu/c-about-crawling-menu.md#task_DCFC9C6A9964421DB5AB6C25DEE98DE9).

**Så här kopierar du en indexanslutningsdefinition**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]** på produktmenyn.
1. På sidan [!DNL Index Connector], under kolumnrubriken [!DNL Actions], klickar du på **[!UICONTROL Copy]** för ett definitionsnamn för Index Connector vars inställningar du vill duplicera.
1. Ange det nya namnet på definitionen på sidan [!DNL Index Connector Copy].
1. Klicka på **[!UICONTROL Copy]**.
1. (Valfritt) Gör något av följande på sidan [!DNL Index Connector Definitions]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Byta namn på en indexanslutningsdefinition {#task_5132118FC21B47D99881E0ED425225D7}

Du kan ändra namnet på en befintlig Index Connector-definition.

När du har bytt namn på definitionen kontrollerar du **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Du vill se till att det nya definitionsnamnet återspeglas i listrutan på sidan [!DNL URL Entrypoints].

Se [Lägga till flera URL-startpunkter som du vill indexera](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

**Byta namn på en definition för indexkoppling**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]** på produktmenyn.
1. På sidan [!DNL Index Connector], under kolumnrubriken [!DNL Actions], klickar du på **[!UICONTROL Rename]** för det indexanslutningsdefinitionsnamn som du vill ändra.
1. På sidan [!DNL Index Connector Rename] anger du det nya namnet på definitionen i fältet [!DNL Name].
1. Klicka på **[!UICONTROL Rename]**.
1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]**. Om den föregående indexanslutarens namn finns i listan tar du bort det och lägger till den nya posten.

   Se [Lägga till flera URL-startpunkter som du vill indexera](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45). 1. (Valfritt) Gör något av följande på sidan [!DNL Index Connector Definitions]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en indexanslutningsdefinition {#task_6B0BD5D0C09F4597A401B0F3AC7C7EA7}

Du kan ta bort en befintlig Index Connector-definition som du inte längre behöver eller använder.

**Så här tar du bort en definition för indexkoppling**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Index Connector]** på produktmenyn.
1. På sidan [!DNL Index Connector Definitions], under kolumnrubriken [!DNL Actions], klickar du på **[!UICONTROL Delete]** för det indexanslutningsdefinitionsnamn som du vill ta bort.
1. Klicka på **[!UICONTROL Delete]** på sidan [!DNL Index Connector Delete].
