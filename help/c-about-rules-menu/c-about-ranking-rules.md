---
description: Du kan använda Rankningsregler för att styra den relativa placeringen eller rangordningen av kundens sökresultat baserat på innehållet i metataggar och relaterade Adobe Analytics-mått.
solution: Target
subtopic: Ranking Rules
title: Om rankningsregler
topic: Regler,Webbplatssökning och -försäljning
uuid: 21962f9a-1d9c-442f-a6c4-5f452436c640
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '4621'
ht-degree: 0%

---


# Om rankningsregler{#about-ranking-rules}

Du kan använda Rankningsregler för att styra den relativa placeringen eller rangordningen av kundens sökresultat baserat på innehållet i metataggar och relaterade Adobe Analytics-mått.

## Använda rankningsregler {#concept_F555C076759B4E81B925441CFE707397}

Du definierar rankningsregler som påverkar den relativa placeringen av dokumenten i sökresultaten, baserat på innehållet i varje dokument. Du kan basera rankningsregler antingen på metataggens innehåll, Adobe Analytics-statistik (om ditt konto är konfigurerat att fungera med Adobe Analytics) eller Adobe Analytics HBX-statistik (om ditt konto är konfigurerat att fungera med Adobe Analytics HBX).

Du kan ställa in webbsidor som innehåller metataggar med önskade egenskaper, t.ex. ett visst varumärke eller pris, eller webbsidor som har önskvärda nyckeltal för Adobe Analytics, t.ex. unika visningsprogram, så att de får en högre rankning än webbsidor som inte har det. De&quot;önskade&quot; egenskaperna uppdateras enkelt genom att rankningsreglerna läggs till eller redigeras och webbplatsen indexeras om.

Om du har definierat fler än en metatagg av typen rankning kan du skapa separata samlingar med regler som du kan använda när du beräknar de olika rankningsfälten. Du kan lägga till en rankningsregelgrupp som du sedan kan tilldela till ett av dina definierade Rankningsfält. Regelgrupper innehåller vanligtvis en eller flera regeldefinitioner, men kan även referera till andra regelgrupper, så att du kan skapa en eller flera grupper med vanliga regler som delas vid beräkningen av flera rankningar.

Se [Lägga till en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

Ett positivt rankningsvärde främjar sökresultaten högst upp. ett negativt rangordningsvärde nedgraderar sökresultaten mot slutet av sökresultaten. Normalt intervall för rankningsvärden är 1,0 vilket är den maximala höjningen inom sökresultaten, medan -1,0 är den maximala degraderingen. Du kan anpassa det här intervallet genom att redigera fältet Rankning i metadatadefinitioner, men den här typen av anpassning behövs vanligtvis inte.

Se [Om definitioner](../c-about-settings-menu/c-about-metadata-menu.md#concept_AE48035C210145169BE067D396975620).

Om du har definierat mer än ett rangordningsfält under Inställningar > Metadata > Definitioner kan du skapa ytterligare uppsättningar med rangordningsregler, en för varje rangordningsfält. Du kan definiera ytterligare uppsättningar med rankningsregler utan att vara direkt kopplad till ett rankningsfält. Med den här flexibiliteten kan du skapa uppsättningar med gemensamma regler som kan delas vid beräkning av ett eller flera rangvärden.

**Viktigt**: Innan du kan använda rankningsregler måste du slutföra flera steg i kontokonfigurationen.

Se [Konfigurera rankning](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5)

## Konfigurerar rankning {#task_4CEBC13925B047FC95BDC217B48089C5}

Innan du kan använda rankningsregler måste du slutföra flera steg i kontokonfigurationen.

**Så här konfigurerar du rankning**

1. Välj bland följande:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Uppgift </p> </th> 
      <th colname="col2" class="entry"> <p>Konfiguration </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Skapa rankningsregler som baseras på metataggar </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_28ABB980143948DFA79AC4360AAB7556"> 
      <li id="li_544075CFA0964C6F8FAF7941AAA9ECCC"> På produktmenyn klickar du på <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>. </li> 
      <li id="li_F237F13B89E8425080C15D3BD697652C"> Klicka på <span class="uicontrol"> Lägg till nytt fält </span> på sidan Definitioner. </li> 
      <li id="li_2A839874D71D45FEA661B3D3B8BE2A86"> Skriv i textfältet <span class="uicontrol"> Fältnamn </span> på sidan Lägg till fält 
      <code>
        rank 
      </code>; i textfältet <span class="uicontrol"> Meta Tag Name </span> skriver du 
      <code>
        rank 
      </code>; i listrutan <span class="uicontrol"> Datatyp </span> väljer du <span class="uicontrol"> Rankning </span>. Lämna alla andra fältalternativ som de är. <p>Se frågeparametern <span class="codeph"> sp_sr </span> i <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-parametrar för backend-sökning </a>. </p> </li> 
      <li id="li_8E91AF4BE51A4A41ABBF9680DDE0B7CE">Klicka på <span class="uicontrol"> Lägg till </span>. </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Skapa rangordningsregler som baseras på Adobe Analytics-statistik </p> </td> 
      <td colname="col2"> <p> 
      <ol id="ol_BE57CBC303D941778B10D855ADC93C68"> 
      <li id="li_8DF5D8F924B24ECBBD2D93C76C69D00C"> Se till att du har konfigurerat Adobe Analytics-autentisering inifrån webbplatssökning/försäljning. <p>Se <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42" type="task" format="dita" scope="local"> Konfigurera autentisering av Adobe Analytics-mått </a>. </p> </li> 
      <li id="li_CF7DD073FC5A432DADBD282AA8BB9920"> Välj och lägg till en tillgänglig rapportserie. <p>Se <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0" type="task" format="dita" scope="local"> Lägga till en Adobe Analytics Report Suite </a>. </p> </li> 
      <li id="li_9A63448577D04E028DF211D8715F943A"> Konfigurera listan med Adobe Analytics-mått som du vill ska vara tillgängliga för att skapa nya rankningsregler. <p>Se <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Redigera Adobe Analytics-statistik för en Report Suite </a>. </p> </li> 
      <li id="li_1ACA3611D9B44AC394604CD89209C966"> Läs in de ursprungliga Adobe Analytics-mätvärdena för webbplatserna. <p>Se <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181" type="task" format="dita" scope="local"> Läsa in Adobe Analytics-data </a>. </p> </li> 
      </ol> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Lägg till en eller flera rankningsregler.

   Se [Lägga till en rankningsregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

1. Klicka på **[!UICONTROL regenerate your staged site index]** för att utföra en fullständig indexering av webbplatsen (från **[!UICONTROL Index]** > **[!UICONTROL Full Index]**).

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. Kontrollera värdena i kolumnen Rankning i **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** för att verifiera att dina Rankningsregler tillämpades korrekt.

## Om att rangordna dokument efter ålder {#topic_770815CF1B2A491F83FF765871B6F1B8}

Du kan rangordna ett HTML-dokument efter dess ålder med en exponentiell minskningsfunktion. Minskningshastigheten anges med en vald halveringskonstant, den tid som måste förflyta innan värdet når hälften av det ursprungliga värdet.

Åldersklassificeringen baseras på följande två ekvationer:

`K = -ln(2) / H`

`RANK = e^(K * T)`

Variablerna `H` och `T` är indata till den här funktionen: `H` är den önskade halveringstiden och `T` är dokumentets ålder, uttryckt i sekunder. `K` är den beräknade halveringstiden och  `RANK` är den exponentiella minskningen av det angivna åldersvärdet. Det resulterande värdet är från 0 till 1. Ett senare dokument har ett rangvärde som ligger närmare 1 jämfört med ett äldre dokument. Teoretiskt sett bör dokument aldrig nå värdet 0, men om du avrundar fel kan resultatet bli 0.

## Krav för att använda åldersrankning {#section_D716507D589442C6B7848892BD28F966}

* Ditt konto bör redan vara korrekt konfigurerat för rankning. Om den inte är konfigurerad kan du läsa [Konfigurera ranking](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).
* HTML-dokumentet måste ha ett HTML-meta-taggfält som representerar dess födelsedatum, eller förekomster som en tidsstämpel eller något annat meningsfullt datumvärde.
* Den speciella inbyggda funktionen `search_get_age_rank()`, som anges på sidorna Lägg till eller Redigera rankningsregel, används för att beräkna ett dokuments ålderrankning. I de följande avsnitten beskrivs i detalj hur funktionen för åldersklassificering används generellt. Ett exempel visas också som demonstrerar funktionen för åldersfördelning.

## Använda search_get_age_rank () på sidan Lägg till rankningsregel eller på sidan Redigera rankningsregel {#section_34BC5276F2AB4419AD92872A397CA0AF}

Ange `search_get_age_rank()` enligt följande:

`search_get_age_rank(Birthdate#Half_Life#Default_Rank)`

* Födelsedatum - Filens födelsedatum eller startdatum måste vara en datumformaterad sträng enligt fältets datumformat. Den här datumformaterade strängen måste vara en fältreferens, som i `{field_name}`.
* Halveringstid - halveringstiden är den tid som måste förflyta innan värdet når hälften av det ursprungliga värdet. Detta värde uttrycks i antal dagar och är ett heltal eller ett flyttal.
* Default_Rank - Standardrangordningen används som säkerhetsnät om födelsedatumet är ogiltigt eller om datumet infaller i framtiden. Du kan inte använda det här standardvärdet om dess associerade metadatafält också har ett giltigt standardvärde. Värdet här är ett flyttal eller ett heltal. Nedan finns förslag om du stöter på problem med vilket standardvärde som används.

Se [Lägga till en rankningsregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

Se [Redigera en rankningsregel](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275).

**Exempel**

I följande exempel

`search_get_age_rank({birthdate}#28#0.20)`

det datum som finns i dokumentets `birthdate`-fält skickas som tidsstämpel. Halveringstiden är 28 dagar. Standardvärdet för rankning är 0,20 om datumet är ogiltigt.

Se alternativtabellen i [Lägga till en rankningsregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

I avsnittet Värden/rankningar på sidan Lägg till rankningsregel eller sidan Redigera rankningsregel kan du bara använda `search_get_age_rank` med anpassade regler. Se därför till att du väljer **Anpassad** i listrutan Värden/Stanke. När regeln använder funktionen för ålderrangordning tillåts inga mellanslag i värdedelen av regeln. Kontrollera att det inte finns några mellanslag i funktionsargumenten eller mellan dem. Och det finns inga mellanslag mellan matematiska eller villkorliga operatorer.

Följande är ett exempel på en värde-/rankningsregel - en regel som är kopplad till ett textfält:

`regexp .* search_get_age_rank({other_field}#365#0.20)`

I det här exemplet antas att `other_field` innehåller ett datumvärde. Om det här fältet inte själv är ett datumtypsfält tolkas det här värdet med de datumformat som är kopplade till det fördefinierade datumfältet. I annat fall används fältets datumformat. Denna värde/rangordning används när dokumentets fält, som identifieras av regelns datakälla, inte är tomma och funktionens returvärde (från 0 till 1) är den tilldelade rangordningen.

För en regel som är associerad med ett numeriskt fält, specifikt ett datumfält:

`9999999999 search_get_age_rank({other_field}#365#0.20)`

När varje dokument bearbetas konverteras värdet i `other_field` till Unix &quot;epoch&quot;-formuläret med fältets datumformatsdefinitioner. Det här värdet används i `search_get_age_rank()`-anropet. Eftersom varje &quot;epok&quot;-värde är mindre än 999999999 (åtminstone för tillfället), anger regeln bara funktionens returvärde (från 0 till 1) som rangordning.

I båda de föregående exemplen är det typiskt att regelns datakälla är samma fält som används i funktionen `search_get_age_rank()` - `other_field` i det här fallet.

## Ett exempel på integrering av åldersklassificering i rankningsregler {#section_A86D909687CC45E19D4EA7A4A9283F28}

Nedan följer ett exempel på hur du kan integrera åldersklassificering i rankningsregler. Exemplet visar även de råa resultaten från ålderrangordningsfunktionen och resultaten från rangordningsreglerna. Exemplet förutsätter följande:

* På webbsidorna som crawlas finns HTML-metataggen &quot;födelsedatum&quot;. Innehållet i den här taggen är en tidsstämpel som hör till dokumentet.
* Metadatadefinitionerna har ett definierat metatagfält för födelsedatumtaggen. Det här fältet är inställt på typen &quot;date&quot;.

**Rankningsregler**

Se [Lägga till ett nytt metataggsfält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

Nu lägger du till en ny rankningsregel. Regeln är definierad för att använda fältet &quot;födelsedatum&quot; i dokumentet. En ny rankningsregel läggs till med följande egenskaper:

* Typ av datakälla: Meta-tagg
* Namn på datakälla: födelsedatum
* Vikter/villkor: 10 - Maximal prioritet
* Värden/rankningar: 9999999999 search_get_age_rank({födelsedatum}#14#0.10)
* Standardrangordning: -1

Regeln gör flera saker. Linjens bredd är inställd på 10. Rankningsvärdet är helt enkelt resultatet av funktionen age-rank, ett värde mellan 0 och 1. Du kan inte använda blanksteg med `search_get_age_rank()`. Lägg även märke till att fältet &quot;födelsedatum&quot; är omgivet av klammerparenteser. När du sparar den här regeln ersätts kommatecknen i definitionen Värden/Rankningar med `#` tecken; detta beteende är normalt.

**Visa resultaten**

Använd datavy-funktionen för att snabbt se resultatet av den rangordnade funktionen. Lägg till lämpliga metadatafält. I exemplet är `age_val` och `myrank` de två metadatafälten som ska läggas till i datavyn. Fältet `myrank` visar hur ålderrankningen påverkar rangordningsvärdena. Fältet `age_val` visar utdata i Raw-format för funktionen exponential-decay för det dokumentet.

## Standardvärden {#section_CB109EF78F914E92955D512ACFC3310E}

Följande är tre standardvärden som används i funktionen `search_get_age_rank()`:

* Standardvärdet som du kan ange i själva funktionen `search_get_age_rank()`.
* Standardrankningsvärdet från rankningsregeln.
* Standardvärdet från metadatadefinitionen.

Beroende på var felet inträffar kan du få olika standardvärden.

Standardvärdet från metadatadefinitionen ska till exempel aldrig inträffa om Rankning och Filtering implementeras korrekt. Det här standardvärdet är det sista ersättningsvärdet när det inte finns något giltigt eller känt innehåll för det metadatafältet. Standardvärdet från rankningsreglerna kan visas när `search_get_age_rank()` refererar till sin egen associerade tagg och taggen saknas i dokumentet. I det här fallet går den här regeln direkt till regelns standardvärde. Om funktionen för ålderrangordning refererar till en annan rankningsregels tagg, är det möjligt att standardvärdet som skickas till den funktionen används om den refererade taggen saknas eller är ogiltig.

## Lägger till en rankningsregel {#task_A132789FD4E5423DAD090DCDA7311E8A}

Du kan lägga till [!DNL Ranking Rules] för att påverka den relativa placeringen av webbsidorna i sökresultaten, baserat på innehållet på varje webbsida.

Se [Konfigurera rankning](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**Lägga till en rankningsregel**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]** på produktmenyn.
1. (Valfritt) Om du har skapat en regelgrupp och lagt till regler i gruppen väljer du en regelgrupp som innehåller de regler du vill redigera på sidan [!DNL Define Ranking Rules] i listrutan **[!UICONTROL Select Rule Group]**.

   Se [Lägga till en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).
1. På sidan [!DNL Define Ranking Rules] klickar du på **[!UICONTROL Add Rule]** för att lägga till en ny rankningsregel eller för att lägga till en referens till en regeluppsättning.
1. Ange önskade alternativ på sidan [!DNL Add Ranking Rule]. Fält som är markerade med en asterisk (*) är obligatoriska.

   Den datakälltyp du väljer påverkar de alternativ som är tillgängliga i listrutan [!DNL Data Source Name]. Om du till exempel har valt **[!UICONTROL Meta Tag]** som datakälltyp, refererar namnet på datakällan till namnet på en meta-tagg på webbplatsens sidor. Om du har valt **[!UICONTROL Adobe Analytics Metric (Number)]** refererar datakällans namn till ett av de Adobe Analytics-mätnamn som du har valt i en rapportsvit som på **[!UICONTROL Edit Adobe Analytics Metrics]**-sidan i webbplatssökning/försäljning.

   Se [Redigera Adobe Analytics-statistik för en Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Typ av datakälla </p> </td> 
      <td colname="col2"> <p>Bestämmer egenskaperna för den datakälla som används som indata för den här rankningsregeln. </p> <p>Datakälltyper som du kan välja bland inkluderar följande: 
      <ul id="ul_B0A97BF0E314495985F44A642C86918D"> 
      <li id="li_4D8BDE32853540809AE78FF5FF5677A1"> <span class="uicontrol"> Meta-tagg  </span> <p> Baserar den här regeln på numeriska data eller textdata som lagras i en namngiven meta-tagg på webbplatsens sidor. </p> </li> 
      <li id="li_4976C31D67254C7F81D554EC49DDBB40"> <span class="uicontrol"> Adobe Analytics-mått (tal)  </span> <p>Baserar den här regeln på ett numeriskt Adobe Analytics-mått som är kopplat till webbplatssidorna. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Namn på datakälla </p> </td> 
      <td colname="col2"> <p>Om du väljer <span class="uicontrol"> metatagg </span> som datakälltyp är det namnet på en metatagg som finns på webbplatsens sidor. Namnen i listrutan kommer från listan med definierade metadatavärden som konfigurerats i Inställningar &gt; Metadata &gt; Definitioner. </p> <p>Se <a scope="local" href="../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5" type="task" format="dita"> Lägga till ett nytt metataggsfält </a>. </p> <p>Om du väljer Adobe Analytics-mått (Number) som datakälltyp är det här namnet på ett Adobe Analytics-mått. Namnen i listrutan kommer från listan med definierade tillgängliga Adobe Analytics-mått som konfigurerades i Inställningar &gt; Adobe Analytics &gt; Metrisk &gt; Redigera. </p> <p>Se <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664" type="task" format="dita" scope="local"> Redigera Adobe Analytics-statistik för en Report Suite </a>. </p> <p>Om det Adobe Analytics-måttnamn du har valt inte redan har definierats i <span class="uicontrol">-inställningarna </span> &gt; <span class="uicontrol">-metadata </span> &gt; <span class="uicontrol">-definitioner </span>, visas ett textfält och en Lägg till-knapp. Ange namnet på metadatafältnamnet (metadatafältnamnet får inte vara längre än 20 tecken) och klicka sedan på <span class="uicontrol"> Lägg till </span>. </p> <p>När sidor påträffas med flera Adobe Analytics-nycklar, som med en produktsida som visar flera produkter, anger Composite Scheme hur de olika Adobe Analytics-mätvärden som är kopplade till den sidan ska hanteras. Välj något av följande: </p> <p> 
      <ul id="ul_D6E51748BB3949048A37C1895F2C0A58"> 
      <li id="li_04F00F382A264C96A519B0D975E25E94"> <span class="uicontrol"> Summa  </span> <p>Returnerar summan av måttvärdena. </p> </li> 
      <li id="li_FA44219B663F4CC197BD3A094EB84396"> <span class="uicontrol"> Genomsnittlig  </span> <p>Returnerar medelvärdet av värdena (summan dividerat med antalet värden). </p> </li> 
      <li id="li_F0EAAE1EA1754FFEB30F611E5550097B"> <span class="uicontrol"> Maximal  </span> <p>Returnerar det största av värdena. </p> </li> 
      <li id="li_38E3E3F3D9AF4C57803B84B60223FB9D"> <span class="uicontrol"> Första  </span> <p>Returnerar värdet som motsvarar den första tangenten. </p> </li> 
      <li id="li_4AEE470CE6BB4D899E975915EC226624"> <span class="uicontrol"> Sista  </span> <p>Returnera värdet som motsvarar den sista tangenten. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vikter/villkor </p> </td> 
      <td colname="col2"> <p>Innehåller antingen ett enkelt viktnummer för en regel eller en kombinerad lista med viktnummer för regler och testvillkor. </p> <p>Ett styckeviktsnummer är ett värde mellan 1 och 10 som anger hur viktig den här rangordningsregeln är i förhållande till de andra rangordningsreglerna när den totala rangordningen för ett dokument ska fastställas. En högre linjetjocklek anger högre prioritet. Värdet noll (0) ignorerar regeln. </p> <p>Välj <span class="uicontrol"> Anpassad </span> i listrutan om du vill anpassa regelbredden för olika sidor genom att definiera en lista med par för regelvikt/testvillkor. Testvillkoren är fragment av Perl som används för att testa datakällvärden, eller globala variabler som definieras i ditt anpassade filterskript (till exempel pris, märke, årstid eller sidvyer som i följande exempel). Om ett testvillkor utvärderas till "true" används det tillhörande regelviktsvärdet. Om ett testvillkor utvärderas till "false" utvärderas nästa villkor i listan. <code> 0&nbsp;({price}&nbsp;&gt;&nbsp;50.00)&nbsp;&amp;&amp;&nbsp;({brand}=~/Kuhl/)5&nbsp;{season}&nbsp;=~&nbsp;/Fall/10&nbsp;{pageviews}&nbsp;&gt;&nbsp;1000005 </code>I exemplet med anpassad vikt/villkor ovan används regelvikten 0 om det första testvillkoret utvärderas till "true". Det vill säga att priset innehåller ett värde som är större än 50 och varumärket innehåller "Kuhl"). Om det första testvillkoret utvärderas till "false" utvärderas nästa villkor. Om inget av de föregående villkoren uppfylls tilldelas regelvikten 5. </p> <p>Du bör alltid ange en linjetjocklek utan villkor i slutet av listan. Om du inte gör det får regeln vikten 0 om inget av villkorstesterna utvärderas som "true". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Värden/omfång </p> </td> 
      <td colname="col2"> <p>Består av någon av de inbyggda rankningsfunktionerna eller av eventuellt innehåll i datakällan tillsammans med önskade rankningar. </p> <p>Om du väljer <span class="uicontrol"> Adobe Analytics Metric (Number) </span> som datakälltyp visas en listruta med följande alternativ: 
      <ul id="ul_104906B6AA8547BAB6979AA37C4FAB90"> 
      <li id="li_7656A2855A054DB8B64E90FE501517AA"> <span class="uicontrol"> Automatisk rangordning efter ordning (standard)  </span> <p>Beräknar en rangordning som baseras på dokumentets relativa position enligt dess Adobe Analytics-mått. Ju närmare dokumentets placering är det översta dokumentet, desto högre rankning. </p> </li> 
      <li id="li_1A7D60EA6965434AA6D39B215C158306"> <span class="uicontrol"> Automatisk rangordning efter värde  </span> <p>Beräknar en rangordning baserat på dokumentets relativa värde, enligt dess Adobe Analytics-mått. Ju närmare dokumentets värde till det högst rankade dokumentets värde, desto högre rankning. </p> </li> 
      <li id="li_457DE44D6ADA40619DC77220BF12318E"> <span class="uicontrol"> Egen  </span> <p>Anger anpassade inställningar. En datakälla med namnet"varumärke" kan till exempel innehålla varumärkesnamnet för en viss produkt. Du kan ange den relativa vikten av varje varumärke genom att ange den tillsammans med dess rankning. </p> </li> 
      </ul> </p> <p>De rangordningsvärden som returneras från beräkningarna av Automatisk rangordning ligger i intervallet 0,0 (lägsta) till 1,0 (högsta). De justeras inte enligt de intervall som är definierade för fältet Rankning under Inställningar &gt; Metadata &gt; Definitioner. </p> <p>Om märkesdatakällan för ett visst sökresultat exakt matchar"DKNY" i följande exempel är rangordningen för det resultatet 0,5. Om varumärket är"Levis" är den tillämpade rankningen 0,1. Innehållet i datakällan måste matcha det angivna värdet. Med andra ord, om datakällans innehåll är "Levis Corp." kommer det inte att matcha värdet "Levis". Skiftläget ignoreras, så"DKNY" matchar"dkny" och"Dkny". <code> DKNY&nbsp;0.5 Levis&nbsp;0.1 Lee&nbsp;0.2 </code> </p> <p>Ett mer avancerat alternativ är att ange värden som reguljära uttryck. Anta till exempel att vissa av webbplatsens sidor innehåller varumärket"Levis" och andra webbplatssidor innehåller varumärket"Levis jeans". Du kan använda ett reguljärt uttryck som anges med nyckelordet 
      <code>
        regexp 
      </code>. </p> <p>Se <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguljära uttryck </a>. </p> <p>I följande exempel tilldelas ett sökresultatdokument som innehåller varumärkesinnehållet"Levis jeans" rangordningen 0.1. Liksom med standardjämförelse ignoreras case för reguljära uttryck. <code> DKNY&nbsp;0.5 regexp&nbsp;Levis.*&nbsp;0.1 Lee&nbsp;0.2 </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardrangordning </p> </td> 
      <td colname="col2"> <p> Anger den rangordning som ska användas för sökresultatdokument som inte matchar något av de angivna värdena. I exemplet ovan tilldelas ett sökresultatdokument med en datakälla för"varumärke" som innehåller"mellanrummet" standardvärdet eftersom"mellanrummet" inte matchar något av de definierade värdena. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Anteckningar </p> </td> 
      <td colname="col2"> <p>Lägg till information som hör till den rankningsregeldefinition eller regelgruppsdefinition som du har skapat. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Giltiga rangvärden är normalt -1,0 till 1,0 enligt följande:

   * `-1.0` är &quot;Minimirankning (visa lägre i sökresultaten).&quot;
   * `0.0` är &quot;Neutral rankning (ändra inte sökresultatordningen)&quot;.
   * `1.0` är &quot;Maximal rankning (visa högre i sökresultaten).&quot;

   Definierade rankningar ska ligga inom samma intervall för alla regler. Rankningsintervallen måste också matcha de intervall som definierats för Rankningsfältet under **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Se [Lägga till ett nytt metataggsfält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

   Se även [Redigera en rankningsregel](../c-about-rules-menu/c-about-ranking-rules.md#task_5EBF55A43D6545FEA46BAE5E586FA275).
1. Klicka på **[!UICONTROL Add]**.
1. Om du vill förhandsgranska resultatet av den nya regeln klickar du på **[!UICONTROL regenerate your staged site index]** för att återskapa det mellanlagrade webbplatsindexet.

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en rankningsregel {#task_5EBF55A43D6545FEA46BAE5E586FA275}

Du kan redigera en befintlig rankningsregel som du redan har lagt till.

Se [Konfigurera rankning](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

**Redigera en rankningsregel**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]** på produktmenyn.
1. (Valfritt) Om du har skapat en regelgrupp och lagt till regler i gruppen väljer du en regelgrupp som innehåller de regler du vill redigera på sidan **[!UICONTROL Define Ranking Rules]** i listrutan **[!UICONTROL Select Rule Group]**.

   Se [Lägga till en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).
1. I tabellen, under kolumnrubriken **[!UICONTROL Actions]**, klickar du på **[!UICONTROL Edit]** för namnet på datakällan som du vill ändra.
1. Ange önskade alternativ på sidan [!DNL Edit Ranking Rule]. Fält som är markerade med en asterisk (*) är obligatoriska.

   Se tabellen med alternativ under [Lägga till en rankningsregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).
1. Klicka på **[!UICONTROL Save Changes]**.
1. Återskapa det mellanlagrade webbplatsindexet för att förhandsgranska resultatet av regelredigeringen.

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en rankningsregel {#task_742A3BCC2A6E4164BE84CC7408807EBB}

Du kan ta bort rankningsregler som du inte längre behöver använda.

Se [Konfigurera rankning](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

Se [Lägga till en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**Ta bort en rankningsregel**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]** på produktmenyn.
1. (Valfritt) Om du har skapat en regelgrupp och lagt till regler i gruppen väljer du en regelgrupp som innehåller regler som du vill ta bort på sidan [!DNL Define Ranking Rules] i listrutan **[!UICONTROL Select Rule Group]**.
1. I tabellen, under kolumnrubriken **[!UICONTROL Actions]**, klickar du på **[!UICONTROL Delete]** för namnet på datakällan som du vill ändra.
1. Klicka på **[!UICONTROL Delete]** på sidan [!DNL Delete Ranking Rule].

   Du återgår till sidan [!DNL Define Ranking Rules].
1. Återskapa indexet för den mellanlagrade webbplatsen för att förhandsgranska resultatet av borttagningen av regeln.

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Lägger till en rankningsregelgrupp {#task_B65081B3CC9E4330A7FEE77B7BCD36C8}

Om du har definierat mer än en metatagg av typen &quot;rankning&quot; kan du skapa separata samlingar med regler som ska användas vid beräkning av de olika rangordningsfälten. Du kan lägga till en rankningsregelgrupp som du sedan kan tilldela till ett av dina definierade Rankningsfält.

Regelgrupper innehåller vanligtvis en eller flera regler som du har lagt till. Regelgrupper kan dock även referera till andra regelgrupper. Du kan till exempel skapa en eller flera regelgrupper och sedan lägga till regler som används ofta för var och en av dem. Dessa regler delas sedan vid beräkningen av de olika rangordningarna.

Se [Redigera en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_D3EC0437E47144BC9E754FEF99C725E5).

Se [Ta bort en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_BE5BE01F377843BEA9846E094A07F2EA).

Se [Granska rankningsregelgrupper](../c-about-rules-menu/c-about-ranking-rules.md#task_5694459D050C4254A25186038CD66B6E).

**Lägga till en rankningsregelgrupp**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]** på produktmenyn.
1. På sidan [!DNL Define Ranking Rules] till höger om listrutan **[!UICONTROL Select Rule Group]** klickar du på **[!UICONTROL Add]**.
1. På sidan [!DNL Add Ranking Rule Group] skriver du ett unikt namn för den nya regelgruppen i fältet **[!UICONTROL Rule Group Name]**.
1. I listrutan **[!UICONTROL Rank Field Name]** väljer du ett namn på ett rangmetadatafält som du vill associera med den nya regelgruppen. Välj **[!UICONTROL None]** om du inte vill tilldela en rankning.

   Listan med namn på rangordnade fält kommer från metadatadefinitioner som lades till i **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Se tabellen med alternativ i [Lägga till ett nytt meta tag-fält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Klicka på **[!UICONTROL Add]**.
1. Bygg om det mellanlagrade webbplatsindexet för att förhandsgranska resultatet av regeltillägget.

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en rankningsregelgrupp {#task_D3EC0437E47144BC9E754FEF99C725E5}

Du kan redigera inställningarna för en befintlig rankningsregelgrupp.

Se [Lägga till en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**Redigera en rankningsregelgrupp**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]** på produktmenyn.
1. På sidan [!DNL Define Ranking Rules] till höger om listrutan **[!UICONTROL Select Rule Group]** klickar du på **[!UICONTROL Edit]**.
1. På sidan [!DNL Edit Ranking Rule Group] skriver du ett unikt namn för regelgruppen i fältet **[!UICONTROL Rule Group Name]**.
1. I listrutan **[!UICONTROL Rank Field Name]** väljer du ett namn på ett rangmetadatafält som du vill associera med regelgruppen. Välj **[!UICONTROL None]** om du inte vill tilldela en rankning.

   Listan med namn på rangordnade fält kommer från metadatadefinitioner som lades till i **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.

   Se tabellen med alternativ i [Lägga till ett nytt meta tag-fält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
1. Klicka på **[!UICONTROL Save Changes]**.
1. Bygg om det mellanlagrade webbplatsindexet för att förhandsgranska resultatet av regeltillägget.

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en rankningsregelgrupp {#task_BE5BE01F377843BEA9846E094A07F2EA}

Du kan ta bort en rankningsregelgrupp som du inte längre behöver eller använder. När du tar bort en grupp tas även regler som har lagts till i gruppen bort. Du kan inte ta bort standardgruppen Rankningsregler.

Innehållet i regelgrupper som ingår i borttagningsgruppen ska inte tas bort. endast referenser till dessa grupper tas bort.

Se till att du indexerar om webbplatsen så att ändringen återspeglas i sökresultaten.

Se [Lägga till en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**Ta bort en rankningsregelgrupp**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]** på produktmenyn.
1. På sidan [!DNL Define Ranking Rules] väljer du en grupp som du vill ta bort i listrutan **[!UICONTROL Select Rule Group]**.
1. Klicka på **[!UICONTROL Delete]** till höger om listrutan **[!UICONTROL Select Rule Group]**.
1. Klicka på **[!UICONTROL Delete]** på sidan [!DNL Delete Ranking Rule Group].
1. Bygg om det mellanlagrade webbplatsindexet för att förhandsgranska resultatet av regeltillägget.

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Granska rankningsregelgrupper {#task_5694459D050C4254A25186038CD66B6E}

Du kan använda rankningsregelgruppsöversikt för att visa varje grupp rankningsfältets namn och tillhörande datakälla och vikt.

Se [Lägga till en rankningsregelgrupp](../c-about-rules-menu/c-about-ranking-rules.md#task_B65081B3CC9E4330A7FEE77B7BCD36C8).

**Granska rankningsregelgrupper**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]** på produktmenyn.
1. På sidan [!DNL Define Ranking Rules] till höger om listrutan **[!UICONTROL Select Rule Group]** klickar du på **[!UICONTROL Overview]**.
1. På sidan [!DNL Ranking Rule Groups Overview] klickar du på **[!UICONTROL Close]** för att återgå till sidan [!DNL Define Ranking Rules].
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testar rankningsregler {#task_56F64EE7ED5B42E481F0990A9DD98ADB}

Du kan ange ett lämpligt URL-test för de definitioner av rankningsregler som du har konfigurerat. De mått som används i beräkningarna visas tillsammans med det beräknade rangordningsvärdet.

Se [Rankningsregler](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

**Testa rankningsregler**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Edit Rules]** på produktmenyn.
1. På sidan [!DNL Define Ranking Rules] skriver du URL:en till en webbsida på webbplatsen i området **[!UICONTROL Test URL]**.
1. Klicka på **[!UICONTROL Test]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Justera vikten som är kopplad till rankningsreglerna {#task_3CB6FC92A66F4D99874A42D55825DB64}

Du kan ändra de relativa bidragen för dina enskilda rankningsregler och bidraget från rankningen till de slutliga sökresultaten.

När rankning inte är definierad är sökresultaten 100 % på **[!UICONTROL Natural Relevance]**-sidan i reglaget Regler och relevans på **[!UICONTROL Adjust Ranking Weights]**-sidan. Denna balans innebär helt enkelt att sökresultaten ordnas enbart utifrån söktermer.

När Rankning är definierat tilldelas det associerade Rank-metadatafältet ett Relevans-värde, mellan 1 och 10. Värdet 1 innebär att den beräknade rangordningen utgör 10 % av sökresultatordningen och Naturlig relevans de återstående 90 %.

Om du har definierat mer än en regel i en regelgrupp, avgör varje regel viktvärde hur mycket den regelns resultat bidrar till den beräknade rangordningen. Anta till exempel att du har en naturlig relevans på 80 %, vilket innebär att det associerade Rank-fältets relevans är 2. Du har också definierat två regler: en med vikten 3 och den andra med vikten 7. I så fall är den första regelns bidrag till slutresultatet 6 % ((3 / (3 + 7)) * 20 %). Den andra regelns bidrag till slutresultatet är 14 % (7 / (3 + 7)) * 20 %).

**Justera vikten som är kopplad till rankningsreglerna**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Ranking Rules]** > **[!UICONTROL Adjust Weights]** på produktmenyn.
1. Välj en grupp vars rankningsvikter du vill justera i listrutan **[!UICONTROL Select Rule Group]** på sidan [!DNL Adjust Ranking Weights].
1. Dra skjutreglagen om du vill ändra motsvarande bidragsvärden.

   I cirkeldiagrammet visas dina ändringar grafiskt.
1. Klicka på **[!UICONTROL Save Changes]**.
1. Bygg om det mellanlagrade webbplatsindexet för att förhandsgranska resultatet av regeltillägget.

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
