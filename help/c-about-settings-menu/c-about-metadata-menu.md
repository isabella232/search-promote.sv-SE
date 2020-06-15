---
description: Använd menyn Metadata för att anpassa sökdefinitioner och indexinjektioner.
seo-description: Använd menyn Metadata för att anpassa sökdefinitioner och indexinjektioner.
seo-title: Om menyn Metadata
solution: Target
subtopic: Metadata
title: Om menyn Metadata
topic: Settings,Site search and merchandising
uuid: f12fc863-a140-45e8-b219-3dbfdef099cd
translation-type: tm+mt
source-git-commit: e080a61e24a3809beff7c212ff3d088b2a8ad3b6
workflow-type: tm+mt
source-wordcount: '8064'
ht-degree: 0%

---


# Om menyn Metadata{#about-the-metadata-menu}

Använd menyn Metadata för att anpassa sökdefinitioner och indexinjektioner.

## Om definitioner {#concept_AE48035C210145169BE067D396975620}

Du kan använda [!DNL Definitions] för att anpassa innehållet och relevansen i HTML- och metadatafälten som beaktas när en kund skickar en sökfråga.

Du kan redigera de fält som redan är fördefinierade. Du kan också skapa nya användardefinierade fält baserat på innehåll i metadatataggar. Varje definition visas på en rad på [!DNL Staged Definitions] sidan.

Se även [Datavyer](../c-about-reports-menu/c-about-data-views.md#concept_DCA897D074464BC1861AA47B40CC86C3).

## Lägga till ett nytt metataggsfält {#task_6DF188C0FC7F4831A4444CA9AFA615E5}

Du kan definiera och lägga till egna metadatataggsfält.

Innan effekterna av den nya metataggsdefinitionen syns för kunderna måste du återskapa platsindexet.

**Lägga till ett nytt metataggsfält**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. På [!DNL Definitions] sidan klickar du på **[!UICONTROL Add New Field]**.
1. Ange önskade alternativ på [!DNL Add Field] sidan.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Fältnamn </p> </td> 
      <td colname="col2"> <p>Anger ett namn som används som referens för fältet. </p> <p>Fältnamnet måste följa följande regler: </p> <p> 
      <ul id="ul_D39D09CD7E7D41A59ECB6C5A6F4F263D"> 
      <li id="li_11CE852BE3C64CEF90FEC7A6E1079E13"> Namnet får bara innehålla alfanumeriska tecken. </li> 
      <li id="li_7FC340E7C58545C88CE9AF4AF09AD7AD"> Bindestreck tillåts i namnet, men inga mellanslag. </li> 
      <li id="li_996FF38457AB4C6DB22B15850A0830CC"> Du kan ange ett namn som är högst 20 tecken långt. </li> 
      <li id="li_C1019E587995444D9587D5EA495D719E"> Namnet är inte skiftlägeskänsligt, men visas och lagras exakt som du skriver det. </li> 
      <li id="li_E55404D6CE354EC89CFFEB1048A11F44"> Du kan inte använda namnen som finns i de fördefinierade fälten så som de visas i tabellen på <span class="wintitle"> sidan </span> Mellanlagrade definitioner. </li> 
      <li id="li_7CE328AE3B5F45A8A09E2DA7ECB62551"> Du kan inte använda ordet "any" som värde för ett användardefinierat fältnamn. </li> 
      <li id="li_9B8287EED1784E79BFCBBBA956705CD2"> Du kan inte redigera namnen på fördefinierade fält. </li> 
      </ul> </p> <p> Exempel på fältnamn: </p> <p> 
      <ul id="ul_5881669913D04E35A6D4A6D31BEE7DF3"> 
        <li id="li_0AFFB8B516FE40F8A615C2F578F2CEA3"> författare </li> 
        <li id="li_7F0ADFBFB21E4B84ACA8A1CEBFE344D1"> PublishDate </li> 
        <li id="li_6D1BEB3D19AC499E9227EC115AEB6296"> något vilt </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Metataggens namn </p> </td> 
      <td colname="col2"> <p>Bestämmer innehållet som är associerat med det definierade fältet. </p> <p>Namnlistan kan innehålla upp till 255 tecken. Namnet kan dessutom innehålla alla tecken som tillåts i namnattributet för en HTML-meta-tagg. </p> <p>Du kan ange flera metataggar i en enda fältdefinition. </p> <p>Flera värden måste vara kommaavgränsade, och metataggens namn längst till vänster som finns på en viss webbsida har företräde. </p> <p>Anta till exempel att du har definierat ett fält med namnet "auth". Fältnamnet har de associerade metataggarna "author, dc.author". I det här fallet indexeras och söks innehållet från meta-taggen "author" över innehållet i "dc.author" om båda meta-taggarna visas på en webbsida. </p> <p>Användardefinierade fält måste ha minst ett metataggnamn i definitionen. Fördefinierade fält behöver inte ha någon associerad metatagg. Om en eller flera metataggar anges åsidosätter emellertid innehållet i metataggen den aktuella datakällan för varje tagg. </p> <p>Om metataggen "dc.title" är associerad med det fördefinierade "title"-fältet, indexeras innehållet från metataggen "dc.title" över det i 
      <userinput>
        &lt;title&gt; 
      </userinput> -tagg för ett visst dokument. </p> <p>Exempel: </p> <p> 
      <ul id="ul_0132E15FC19E4C0CA13CD5A12EA3BBEC"> 
      <li id="li_ECD3B194FECB4C2090CAEC8449320D3F"> dc.date </li> 
      <li id="li_09C76BC7AC7348859D01989697212E31"> description </li> 
      <li id="li_9230C0450F9D424087D1F127048DA311"> proprietarytag </li> 
      </ul> </p> </td> 
    </tr> 
      <tr> 
      <td colname="col1"> <p>Datatyp </p> </td> 
      <td colname="col2"> <p>Alla fält har en associerad datatyp som text, tal, datum, version, rangordning eller plats. Den här datatypen avgör hur fältets innehåll indexeras, söks och sorteras om så önskas. </p> <p>Du kan inte ändra datatypen när du har skapat fältdefinitionen. </p> <p>Använd följande information för att välja den datatyp som är relevant för informationen som fältet innehåller. </p> <p> 
      <ul id="ul_A3AD5A0CF354410F836311F39151B8A6"> 
      <li id="li_9F412DA7D9EF497BA6E65F9CE10F3046"> <span class="uicontrol"> Textdatatypsfält </span> behandlas som teckensträngar. </li> 
      <li id="li_AD78B75644AE40208F0239311015611F"> <span class="uicontrol"> Nummerdatatypfält </span> behandlas som numeriska heltal eller flyttal. </li> 
      <li id="li_0B46975C589148E9A7C32A8D250487B7"> <span class="uicontrol"> Datumdatatypsfält </span> behandlas som datum-/tidsspecificerare. Du kan anpassa de tillåtna formaten för datum och tid när du lägger till eller redigerar det nya fältet. </li> 
      <li id="li_BB68CB1DBE0543AC9000B3DEDFB28E7E"> <span class="uicontrol"> Datatypsfält för versioner </span> behandlas som numeriska data i fri form. 1.2.3 sorterar till exempel före 1.2.2. </li> 
      <li id="li_0BA895B4DADA46528A7A4161EEB1521E"> <span class="uicontrol"> Rankade </span> datatypfält behandlas på samma sätt som"Number"-typfält, förutom att de dessutom påverkar ranknings-/relevansberäkningarna i sökresultaten. <p>Se <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" type="concept" format="dita" scope="local"> Om rankningsregler </a>. </p> </li> 
      <li id="li_459405DA437049AD88AA1FAC28F04720"> <span class="uicontrol"> Platsdatatypfält </span> behandlas som fysiska platser var som helst i världen. Tillåtna platsformat är: <p> 
      <ul id="ul_D2CEBFA1A5504AA996BA2F7641AFB7F3"> 
      <li id="li_5283A2F2D5D84840B3D920C08D43654C"> 5- eller 9-siffriga ZIP-koder i form av DDDDD eller DDDD-DDDD, där varje "D" är en siffra mellan 0 och 9. </li> 
      <li id="li_A5CD4DFC90164BC68183DB7D10603B7C"> Tresiffriga områdeskoder i form av DDD. </li> 
      <li id="li_9DAEAE64BC7F4902B25043D998C8F56D"> Latitud-/longitudpar i formatet ±DD.DDDD±DDD.DDDD, där det första talet anger latitud och det andra talet anger longitud. </li> 
      </ul> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tillåt listor </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Text </span>eller <span class="uicontrol"> Number </span> har valts. </p> <p>Indexera avgränsade värden separat i metadatainnehållet i det här fältet. </p> <p>Innehållet"Röd, Gul, Grön, Blå" behandlas som fyra separata värden i stället för ett när"Tillåt listor" är markerat. Den här behandlingen är mest användbar vid sökning efter intervall (med 
      <userinput>
        sp_q_min 
      </userinput>, 
      <userinput>
        sp_q_max 
      </userinput>, eller 
      <userinput>
        sp_q_exact 
      </userinput>) och med 
      <userinput>
        &lt;search-field-value-list&gt; 
      </userinput>, 
      <userinput>
        &lt;search-field-values&gt; 
      </userinput>och 
      <userinput>
        &lt;search-display-field-values&gt; 
      </userinput>. </p> <p>Inte tillgängligt om Version-datatypen har valts. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Dynamisk Fasett </p> </td> 
      <td colname="col2"> <p> 
        <!--NEW 2/2/2014--> <p>Obs!  Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera den för användning. När den har aktiverats visas den i användargränssnittet. </p> </p> <p>Anger att den identifierade aspekten ska vara dynamisk. </p> <p>Ansikten byggs ovanpå metataggsfält. Ett metataggsfält är ett lågnivålager för grundsökning i Adobe Search&amp;Promote. Ansikten är å andra sidan en del av GS-presentationsskiktet (Guided Search) - Adobe Search&amp;Promote högnivåskikt. Ansikten över egna metataggsfält är att metataggsfält inte kan någonting om ansikten. </p> <p>Se <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Om dynamiska ansikten </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tillåt borttagning </p> </td> 
      <td colname="col2"> <p>Markera det här alternativet om du vill aktivera borttagning av dubbletter för det här fältet. Det innebär att det här fältet kan anges vid sökningen via 
        <userinput>
          sp_dedupe_field 
        </userinput> Sök efter CGI-parameter. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Sök efter CGI-parametrar </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tabellnamn </p> </td> 
      <td colname="col2"> <p>Associerar det angivna fältet permanent med det angivna tabellnamnet. </p> <p>Varje gång ett sådant fält nämns i en CGI-parameter eller en malltagg anges tabellnamnet automatiskt. Med den här funktionen kan du välja dynamiska aspekter genom tabellmatchningar, men du kan också använda den för icke-dynamiska facettsfält om du vill. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Listavgränsare </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Tillåt listor </span> har valts. </p> <p>Anger vilka tecken som skiljer enskilda listvärden åt. Du kan ange flera tecken, där vart och ett behandlas som en värdeavgränsare. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sök som standard </p> </td> 
      <td colname="col2"> <p>När du väljer det här alternativet genomsöks fältinnehållet även när fältet inte uttryckligen anges i en given sökfråga. Om du avmarkerar det här alternativet söks fältet bara igenom när det efterfrågas. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lodrätt uppdateringsfält </p> </td> 
      <td colname="col2"> <p> <p>Obs!  Den här funktionen är inte aktiverad som standard. Kontakta teknisk support för att aktivera den för användning. När den har aktiverats visas den i användargränssnittet. </p> </p> <p>Anger att det identifierade fältet ska vara ett lodrätt uppdateringsfält. </p> <p>Lodräta uppdateringsfält kan uppdateras genom den lodräta uppdateringsprocessen ( <span class="uicontrol"> Index </span> &gt; <span class="uicontrol"> Lodrät uppdatering </span>). På grund av det sätt som lodräta uppdateringar görs kan innehåll från dessa fält inte sökas i fritextsökningar. Om du markerar det här alternativet läggs inte fältets innehåll till i "Word"-indexet under någon typ av indexåtgärd. Det aktiverar även uppdatering av det här fältet under en vertikal uppdatering. </p> <p>Mer information om lodräta uppdateringar finns i <a href="../c-about-index-menu/c-about-vertical-updates.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Om lodrät uppdatering </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Relevans </p> </td> 
      <td colname="col2"> <p>Du kan redigera relevansen för fördefinierade och användardefinierade fält. </p> <p>Relevans anges på en skala 1-10. En inställning på 1 innebär att den är minst relevant och 10 är den mest relevanta. Dessa värden tas med i beräkningen när programmet bedömer att frågan matchar i varje fält. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sortering </p> </td> 
      <td colname="col2"> <p>Anger när resultaten sorteras efter det namngivna fältet med hjälp av 
        <userinput>
          sp_s 
        </userinput> Sök efter CGI-parameter. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Sök efter CGI-parametrar </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Språk </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Rankning </span>, <span class="uicontrol"> Nummer </span>eller <span class="uicontrol"> Datum </span> har valts. </p> <p>Styr de språk- och språkkonventioner som används vid indexering av datum-, nummer- och rangvärden för det här fältet. </p> <p>Du kan välja att använda kontospråket (Språk &gt; Ord och språk). Du kan också använda det språk som är associerat med dokumentet som innehåller varje tal- eller datumvärde, eller ett visst språk. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Datumformat </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Date </span> är markerad. </p> <p>Styr de datumformat som identifieras när datumvärden indexeras för det här fältet. </p> <p>En standardlista med strängar för datumformat finns för varje datumfält. Du kan lägga till i listan eller redigera den så att den passar din egen webbplats behov. </p> <p>Se <a href="../c-appendices/r-date-formats.md#reference_4D1FC1F6B9F44857967188496D8D335B" type="reference" format="dita" scope="local"> Datumformat </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Testdatumformat </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Datum </span> har valts som datatyp. </p> <p>Här kan du förhandsgranska de datumformat du har angett för att se till att de är korrekt formaterade. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tidszon </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Datum </span> har valts som datatyp. </p> <p>Styr den förmodade tidszon som används vid indexering av datumvärden för det här fältet som inte anger någon tidszon. </p> <p>Om tidszonen för ditt konto till exempel är inställd på"Amerika/Los Angeles" och du väljer <span class="uicontrol"> Använd tidszon för konto, </span>behandlas följande metadatumvärde, som inte har någon angiven tidszon, som om det vore Pacific Time, vilket ger besparingar i dagsljus: </p> <p>&lt;meta name="dc.date" content="Mon, 05 Sep 2012:12:00"&gt; </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minst viktigt rangordningsvärde </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Rank </span> har valts som datatyp. </p> <p>Styr rangvärdet som representerar den minsta rangordningen för ett dokument. </p> <p>Om dokumentets rangordning ligger mellan 0 och 10 för den högsta rangordningen anger du värdet 0. </p> <p>Om dokumentets rangordning ligger mellan 1 och 10 för den lägsta rangordningen anger du värdet 10. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardvärde för rangordning </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Rank </span> har valts som datatyp. </p> <p>Styr rangvärdet som används om ett dokument inte innehåller några metataggar som är definierade för det här rangordningsfältet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Viktigaste rangordningsvärde </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Rank </span> har valts som datatyp. </p> <p>Styr rangvärdet som representerar den högsta rangordningen för ett dokument. </p> <p>Om dokumentets rangordning ligger mellan 0 och 10 för den högsta rangordningen anger du värdet 10. </p> <p>Om dokumentets rangordning ligger mellan 1 och 1 för den högsta rangordningen och 10 för den lägsta rangordningen anger du värdet 1. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardenheter </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om datatypen <span class="uicontrol"> Location </span> har valts som datatyp. </p> <p>Kontrollerar behandlingen av avståndsvärden för närhetssökningar. </p> <p>Om du anger standardenheterna till <span class="uicontrol"> Miles </span>används eventuella kriterier för närhetssökning för minsta/största avstånd som används i det här fältet (via 
      <userinput>
        sp_q_min[_#] 
      </userinput> eller 
      <userinput>
        sp_q_max[_#] 
      </userinput> CGI-parametrar för sökning behandlas som engelska mil, annars som kilometer. </p> <p>Det här alternativet styr även de standardavståndsenheter som används på utdata för 
      <userinput>
        &lt;search-display-Field&gt; 
      </userinput> sökresultatmallstagg när den används i ett närliggande sökutdatafält. </p> <p>Se <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Om närhetssökning </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vill du skapa intervallbeskrivning? </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Nummer </span> har valts som datatyp. </p> <p>Styr det automatiska skapandet av fältintervallbeskrivningar, som används med <span class="uicontrol"> Design </span> &gt; <span class="uicontrol"> Navigering </span> &gt; <span class="uicontrol"> Ansikten </span>. </p> <p>Se <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" format="dita" scope="local"> Om ansikten </a>. </p> <p> <p>Obs!  Om det här fältet har <span class="uicontrol"> fältet för lodrät uppdatering </span> markerat uppdateras det genererade fältintervallbeskrivningsfältet under en lodrät uppdatering. Vi rekommenderar dock att fältet som identifieras i <span class="uicontrol"> Intervallfält </span> också har <span class="uicontrol"> Lodrätt uppdateringsfält </span> markerat. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Intervallfält </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat. </p> <p>Det <span class="uicontrol"> textfält </span> som ska uppdateras med intervallbeskrivningar för det aktuella fältet. Den här listan innehåller alla <span class="uicontrol"> textfält </span> som inte redan används med andra fält för generering av fältintervall. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Intervallvärden </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>En tom avgränsad lista med datapunkter som ska användas när du skapar fältintervallbeskrivningar. Exempel: </p> <code> 10&amp;nbsp;20&amp;nbsp;50&amp;nbsp;100&amp;nbsp;1000 </code> <p>Du kan ange dessa värden i valfri ordning. Värdena sorteras och dubbletter tas bort innan de sparas. Du kan också ange negativa värden och värden som inte är heltal. </p> <p>För varje värde i det här fältet: 
      <ul id="ul_C4B41AF5AADF4B84B9C489CE82FF7075"> 
      <li id="li_90736394A5AE4F5CA6B47687BCB627AA">om värdet är mindre än (&lt;) det minsta värdet i <span class="uicontrol"> Intervallvärden </span>används formatet <span class="uicontrol"> "Mindre än" </span> </li> 
      <li id="li_A5C272B2D26A468CA07EB2046B2EA8A7">Om värdet är större än eller lika med (&gt;=) det största värdet i <span class="uicontrol"> Intervallvärden </span>används formatet <span class="uicontrol"> "Större än" </span> . </li> 
      <li id="li_9DDFB70E1E824CF4819C57450C1A6DD2">I annat fall hittas ett "intervall" där fältvärdet ligger mellan två på varandra följande <span class="uicontrol"> intervallvärden </span> (större än (&gt;), det mindre värdet och mindre än eller lika med (&lt;=) det större värdet), och <span class="uicontrol"> Mellanliggande format </span> används. </li> 
    </ul> </p> <p>Ovanstående exempeluppsättning värden definierar till exempel en uppsättning beskrivningar för värden: 
    <ul id="ul_03ED30D5A19346AB8E6809BDD186A9A9"> 
      <li id="li_F97A6B3763954EFE9B6751F472AF7D20">mindre än 10 </li> 
      <li id="li_12B6F636A6444B8292E0BFE4F55032DF">större än eller lika med 10 och mindre än 20 </li> 
      <li id="li_545A2EAF5BD046B5AD59B77DB43DCD14">större än eller lika med 20 och mindre än 50 </li> 
      <li id="li_26A8CD2422524D2CBD36794C6908572A">större än eller lika med 50 och mindre än 100 </li> 
      <li id="li_05EBEEE68DC348E0821F1CC16D04D69C">större än eller lika med 100 och mindre än 10000 </li> 
      <li id="li_9513A6B519394780A6A41B80762A0370">större än eller lika med 10000 </li> 
      </ul> </p> <p>Vill du se <span class="uicontrol"> Testa med större än? </span> för att ändra hur dessa tester utförs. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>"Mindre än"-format </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>Det här är den mall som används för att ange intervallbeskrivningen för värden som är mindre än det minsta värdet i <span class="uicontrol"> Intervallvärden </span>. Det minsta värdet representeras med den numeriska platshållartoken <span class="uicontrol"> ~N~ </span>. Exempel: </p> <code> Less&amp;nbsp;than&amp;nbsp;~N~ </code> <p>eller: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;below </code> <p>Normalt formateras värdet "as-is", dvs. för en <span class="uicontrol"> intervallvärdesdefinition </span> på "5 10 20" och ett angivet värde på 1, blir den genererade intervallbeskrivningen helt enkelt något som "Mindre än 5". Om du istället vill ha det som"4.99 och lägre" ställer du in <span class="uicontrol"> Precision </span> till <span class="uicontrol"> 2 </span> och använder det här formatet: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;below </code> <p>I <span class="uicontrol"> "Mindre än"-format </span>kommer det gemena <span class="uicontrol"> ~n~ </span> att göra att värdet avrundas <i>nedåt</i> enligt <span class="uicontrol"> precisionsinställningen </span> . </p> <p>Obs! om du vill ta med en numerisk platshållare i intervallbeskrivningen, som den är, anger du med ett omvänt snedstreck (\)-prefix, t.ex. <span class="uicontrol"> \~N~ </span> eller <span class="uicontrol"> \~n~ </span>. Om du vill ta med ett omvänt snedstreck anger du det med ett annat omvänt snedstreck, t.ex. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mellanliggande format </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>Det här är mallen som används för att ange intervallbeskrivningen för värden som ligger någonstans mellan de minsta och största värdena i <span class="uicontrol"> Intervallvärden </span>. För det angivna intervallet representeras det undre intervallvärdet med den numeriska platshållartoken <span class="uicontrol"> ~L~ </span>, och det högre intervallvärdet representeras med token <span class="uicontrol"> ~H~ </span>. Exempel: </p> <code> ~L~&amp;nbsp;to&amp;nbsp;~H~ </code> <p>eller: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>eller: </p> <code> Less&amp;nbsp;than&amp;nbsp;~H~&amp;nbsp;and&amp;nbsp;greater&amp;nbsp;than&amp;nbsp;~L~ </code> <p>Normalt formateras värdena "as-is", dvs. för en <span class="uicontrol"> intervallvärdesdefinition </span> på "5 10 20" och ett angivet värde på 8, blir den genererade intervallbeskrivningen helt enkelt något som "Mellan 5 och 10". Om du i stället vill ha värdet "Mellan 5 och 9,99", med det högre värdet justerat <i>nedåt</i>, ställer du in <span class="uicontrol"> Precision </span> till <span class="uicontrol"> 2 </span> och använder det här formatet: </p> <code> Between&amp;nbsp;~L~&amp;nbsp;and&amp;nbsp;~h~ </code> <p>På samma sätt kan <span class="uicontrol"> ~L~ </span> ersättas med <span class="uicontrol"> ~l~ </span> så att det lägre värdet justeras <i>uppåt</i>, även enligt <span class="uicontrol"> precisionsinställningen </span> . Detta innebär att en definition som: </p> <code> Between&amp;nbsp;~l~&amp;nbsp;and&amp;nbsp;~H~ </code> <p>med ett <span class="uicontrol"> precisionsvärde </span> på <span class="uicontrol"> 2 </span> skapas"Mellan 5,01 och 10". </p> <p>Det gemena värdet <span class="uicontrol"> ~l~ </span> gör att det lägre värdet avrundas <i>uppåt</i> enligt <span class="uicontrol"> precisionsinställningen, och det gemena värdet </span> ~h~ <span class="uicontrol"> gör att det högre värdet avrundas </span> nedåt <i></i>. </p> <p>Obs! om du vill ta med en numerisk platshållare i intervallbeskrivningen, som den är, anger du med ett omvänt snedstreck (\)-prefix, t.ex. <span class="uicontrol"> \~L~ </span> eller <span class="uicontrol"> \~h~ </span>. Om du vill ta med ett omvänt snedstreck anger du det med ett annat omvänt snedstreck, t.ex. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>"Större än"-format </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>Det här är den mall som används för att ange intervallbeskrivningen för värden som är större än det största värdet i <span class="uicontrol"> Intervallvärden </span>. Det största värdet representeras med den numeriska platshållartoken <span class="uicontrol"> ~N~ </span>. Exempel: </p> <code> Greater&amp;nbsp;than&amp;nbsp;~N~ </code> <p>eller: </p> <code> ~N~&amp;nbsp;and&amp;nbsp;above </code> <p>Normalt formateras värdet "as-is", dvs. för en <span class="uicontrol"> intervallvärdesdefinition </span> på "5 10 20" och ett angivet värde på 30, skulle den genererade intervallbeskrivningen helt enkelt vara något som "Större än 20". Om du istället vill ha det som"20.01 och högre" ställer du in <span class="uicontrol"> Precision </span> till <span class="uicontrol"> 2 </span> och använder det här formatet: </p> <code> ~n~&amp;nbsp;and&amp;nbsp;above </code> <p>I <span class="uicontrol"> "Större än"-format </span>kommer det gemena värdet <span class="uicontrol"> ~n~ </span> att avrundas <i>uppåt</i> enligt <span class="uicontrol"> precisionsinställningen </span> . </p> <p>Obs! om du vill ta med en numerisk platshållare i intervallbeskrivningen, som den är, anger du med ett omvänt snedstreck (\)-prefix, t.ex. <span class="uicontrol"> \~N~ </span> eller <span class="uicontrol"> \~n~ </span>. Om du vill ta med ett omvänt snedstreck anger du det med ett annat omvänt snedstreck, t.ex. <span class="uicontrol"> \\ </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Precision </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>Ett heltalsvärde som anger antalet siffror till höger om ett decimaltecken. Detta styr även avrundningsåtgärder. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ta bort inledande nollor? </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat, ett <span class="uicontrol"> Intervallfält- </span> objekt har markerats och ett <span class="uicontrol"> precisionsvärde som inte är noll har </span> angetts. </p> <p>Ska vi visa "0.50" som ".50"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vill du ta bort efterföljande nollor? </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat, ett <span class="uicontrol"> Intervallfält- </span> objekt har markerats och ett <span class="uicontrol"> precisionsvärde som inte är noll har </span> angetts. </p> <p>Ska vi visa"10.00" som"10"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visa tusentals avgränsare? </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>Ska vi visa "10000" som "10 000"? Språkspecifika värden används. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Vill du justera nollvärden? </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>När rundade nollvärden visas, ska de avrundas uppåt eller nedåt enligt <span class="uicontrol"> precisionsinställningen </span> ? d.v.s. display "0.01"? </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Testa med större än? </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>Eftersom varje värde jämförs med värdena i <span class="uicontrol"> Intervallvärden </span>, som bearbetas i <i><b>fallande</b></i> ordning, jämförs det som standard med operatorn större än eller lika med (&gt;=), som stoppas när testet har slutförts. Det innebär att om du har en uppsättning <span class="uicontrol"> intervallvärden </span> som "10 20 50 100 1000" hamnar värdet 100 i intervallet 100 till 1000, eftersom 100 faktiskt är &gt;= 100. Om du hellre vill att den ska ligga i intervallet 50 till 100 markerar du det här alternativet, vilket gör att jämförelsen använder operatorn större än (&gt;) i stället. </p> <p>Om det här alternativet är markerat för till exempel alla värden i det här fältet: 
      <ul id="ul_969621B1BD914FA5BD73ED21F8841010"> 
      <li id="li_157BEFDA7D0E44C481F4E4BC9046EF24">om värdet är mindre än eller lika med (&lt;=) det minsta värdet i <span class="uicontrol"> Intervallvärden </span>används formatet <span class="uicontrol"> "Mindre än" </span> </li> 
      <li id="li_737EE666CA6243A8864E17A311CF3ACC">om värdet är större än (&gt;) det största värdet i <span class="uicontrol"> Intervallvärden </span>används formatet <span class="uicontrol"> "Större än" </span> </li> 
      <li id="li_353A9820F7F74CCCBB3281EC4CB48734">i annat fall hittas ett intervall där fältvärdet ligger mellan två på varandra följande <span class="uicontrol"> intervallvärden </span> (större än eller lika med (&gt;=) det mindre värdet och mindre än (&lt;) det större värdet), och <span class="uicontrol"> Mellanliggande format </span> används </li> 
    </ul> </p> <p>och, när det inte är markerat: 
    <ul id="ul_945844C33C2E4D95A598C4876E15F211"> 
      <li id="li_653B6E2934574DA3B4BCEF07D0A84527">om värdet är mindre än (&lt;) det minsta värdet i <span class="uicontrol"> Intervallvärden </span>används formatet <span class="uicontrol"> "Mindre än" </span> </li> 
      <li id="li_AECA6880002F40FAB1820B37237550A7">om värdet är större än eller lika med (&gt;=) det största värdet i <span class="uicontrol"> Intervallvärden </span>används formatet <span class="uicontrol"> "Större än" </span> </li> 
      <li id="li_ECB2DF7CA592497298E9ADC708220366">i annat fall hittas ett intervall där fältvärdet ligger mellan två på varandra följande <span class="uicontrol"> intervallvärden </span> (större än (&gt;) det mindre värdet och mindre än eller lika med (&lt;=) det större värdet) och <span class="uicontrol"> Mellanliggande format </span> används </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Testa </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om <span class="uicontrol"> Skapa intervallbeskrivning </span> är markerat och ett <span class="uicontrol"> Intervallfält </span> är markerat. </p> <p>Ange ett numeriskt exempelvärde och tryck på <span class="uicontrol"> knappen Testa </span> för att se hur intervallfältet skapas. Den genererade intervallbeskrivningen visas i fönstret. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Se även [Lägga till ett nytt fält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)för metataggar.
1. Klicka på **[!UICONTROL Add]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på [!DNL Definitions] sidan:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera fördefinierade eller användardefinierade metataggsfält {#task_0A7657B63596421BB6DB3ED44F827AB3}

Du kan bara redigera vissa fält i fördefinierade metataggar eller redigera alla fält i metataggar som är användardefinierade.

Innan effekterna av dina metataggsändringar är synliga för kunderna måste du återskapa platsindexet.

**Redigera fördefinierade eller användardefinierade metataggsfält**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. På [!DNL Definitions] sidan, i tabellens [!DNL Actions] kolumn, klickar du **[!UICONTROL Edit]** på raden med metataggens fältnamn som du vill ändra.
1. På [!DNL Pinned Keyword Results Manager] sidan klickar du i tabellen **[!UICONTROL Edit]** på raden för det nyckelord som du vill ändra.
1. Ange önskade alternativ på [!DNL Edit Field] sidan.

   Om du väljer att göra ändringar i ett fördefinierat metataggsfält måste du vara medveten om att alla fält inte kan redigeras.

   Se tabellen med alternativ under [Lägga till ett nytt fält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5)för metataggar.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på [!DNL Definitions] sidan:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ta bort ett användardefinierat metataggsfält {#task_9361EF38B5E743038B6672FA6CF70FD3}

Du kan ta bort ett användardefinierat fält för metataggar som du inte längre behöver eller använder.

Du kan inte ta bort fördefinierade metataggsfält. Du kan dock redigera vissa fält.

Se [Redigera fördefinierade eller användardefinierade metataggfält](../c-about-settings-menu/c-about-metadata-menu.md#task_0A7657B63596421BB6DB3ED44F827AB3).

Innan effekterna av meta-taggen för borttagning är synliga för kunderna måste du återskapa platsindexet.

**Ta bort ett användardefinierat metataggsfält**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]**.
1. På [!DNL Definitions] sidan, i tabellavsnittet, klickar du på raden [!DNL User-defined fields] **[!UICONTROL Delete]** i metataggens fältnamn som du vill ta bort.
1. Klicka på i dialogrutan Bekräfta **[!UICONTROL OK]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på [!DNL Definitions] sidan:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om injektioner {#concept_DA091920671948A0A893A26B3A2FAAE5}

Du kan använda [!DNL Injections] för att infoga innehåll på dina webbsidor utan att behöva redigera själva sidorna.

Du kan lägga till innehåll i specifika indexerade fält som&quot;target&quot; eller&quot;body&quot;, eller ersätta indexerat innehåll med nya värden. Om du till exempel infogar nytt innehåll i metataggfältet&quot;target&quot; behandlas den här informationen på samma sätt som hårdkodat sidinnehåll. Du kan redigera innehållet i alla fördefinierade metataggfält oavsett om webbplatssidorna har motsvarande innehåll eller inte. Du kan till exempel redigera innehållet i följande fördefinierade meta-taggsfältnamn:

* alt
* brödtext
* charset
* datum
* desc
* tangenter
* språk
* target
* title
* url

## Arbeta med testfältsinjektioner {#section_74939EA9E6EA4D2A92E8066B3B11CF92}

Du kan också använda **[!UICONTROL Test]** på [!DNL Staged Injections] sidan. Du anger ett testfältsnamn (till exempel &quot;titel&quot; eller &quot;brödtext&quot;), det ursprungliga fältvärdet (till exempel &quot;Hemsida&quot;) och en test-URL från webbplatsen. Resultatet visas som referens. De aktuella värdena ändras inte under testet.

## Arbeta med fältinjektionsdefinitioner {#section_C1BBF19DE8EF4A6F8CC3ED691F3953A9}

Injektionsdefinitionerna har följande form:

```
append|replace field [regexp] URL value
```

The `append|replace`, `field`, `URL`.. och `value` poster är obligatoriska. Du anger en injektionsdefinition per rad. Följande exempel innehåller sex olika injektionsdefinitioner.

```
replace title  https://www.yoursite.com/company/contactus.html Adobe: Contact Us 
append body https://www.yoursite.com/products/* On Sale Now! 
append target https://www.yoursite.com/news/bob_white/ Regular Weekly Feature 
append target regexp https://www.yoursite.com/travel/mr_travel/.*\column.html$ Regular Weekly Feature 
replace charset https://www.yoursite.com/japanese/intro.txt shift-jis 
replace language https://www.yoursite.com/japanese/intro.txt ja_JP
```

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Inmatningsdefinition </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> append|replace </span> </p> </td> 
   <td colname="col2"> <p>Välj "append" om du vill lägga till värdet för injektionsdefinitionen ("Adobe: Kontakta oss eller"On Sale Now!" i exemplen ovan) till innehållet i befintliga fält. Välj Ersätt om du vill skriva över befintligt fältinnehåll med det definierade värdet. Om ett fält inte har något innehåll läggs det definierade värdet till automatiskt, oavsett vilket alternativ (lägg till eller ersätt) som används. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> fält </span> </p> </td> 
   <td colname="col2"> <p>Ett fältnamn krävs. Följande är tio fördefinierade fältnamn som du kan använda: </p> <p> 
     <ul id="ul_B9336FA53023474EAEE399116E7FC972"> 
      <li id="li_C621203DCD2B4875A54A1DD19F0B5B90"> <span class="codeph"> alt </span> </li> 
      <li id="li_9217E6A037254BEDBB8D006B70D7670D"> <span class="codeph"> brödtext </span> </li> 
      <li id="li_DCDC50F93F224F02897419B745E09399"> <span class="codeph"> charset </span> </li> 
      <li id="li_D95668236B6547B99966668C82B302AB"> <span class="codeph"> datum </span> </li> 
      <li id="li_D2071681274345C3B97E9ADA6D223271"> <span class="codeph"> desc </span> </li> 
      <li id="li_26683A9209454A438D811187FB929482"> <span class="codeph"> tangenter </span> </li> 
      <li id="li_A5E19F81B872402CA62B5AB9497E030D"> <span class="codeph"> språk </span> </li> 
      <li id="li_FD0B1CD9E6304B18B9D7F57E61015107"> <span class="codeph"> target </span> </li> 
      <li id="li_400D7E3F3E9B47EFB2FF5C0D278DB573"> <span class="codeph"> title </span> </li> 
      <li id="li_449BCBEE4F64424BB69F780C10F5956C"> <span class="codeph"> url </span> </li> 
     </ul> </p> <p>Varje fältnamn motsvarar element på webbplatsens sidor. Om du till <span class="codeph"> exempel anger fältnamnet </span> desc kan du lägga till värdet för injektionsdefinitionen i det fält som motsvarar metataggen för beskrivningen på webbplatsens sidor. </p> <p>Om det inte finns någon meta-tagg för beskrivning på sidorna skapas taggen för det definierade innehållet. Innehållet som anges i en <span class="codeph"> desc- </span> injektion visas på resultatsidan på samma sätt som innehåll i en metabeskrivning med hårdkod. </p> <p>Du kan också skapa flera definitioner med samma fältnamn. Anta till exempel att du har följande injektioner: </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/&nbsp;Welcome&nbsp;to&nbsp;My&nbsp;Site </code> </p> <p> <code> replace&nbsp; <b>title</b>&nbsp;https://www.mysite.com/company/*.html&nbsp;My&nbsp;Site:&nbsp;Contact </code> </p> <p>Alla webbplatssidor i exemplet ovan får den inmatade titeln"Välkommen till Min webbplats". Sidorna i mappen "/company/" injiceras med den nya titeln "Min webbplats: Kontakta oss" som ersätter den tidigare versionen. </p> <p>Observera att injektionerna används i den ordning som de visas i <span class="wintitle"> textrutan </span> Fältinjektionsdefinitioner. Om samma fält ("titel" i det här exemplet) definieras mer än en gång för sidor på samma plats, har den senare definitionen företräde. </p> <p> <span class="codeph"> [regexp] </span> - valfritt. Om du väljer att använda <span class="codeph"> alternativet </span> regexp behandlas den definierade URL:en som ett reguljärt uttryck. </p> <p>Se <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguljära uttryck </a>. </p> <p>I följande definition: </p> <p> <code> replace&nbsp;target&nbsp; <b>regexp&amp;nbsp;^.*/products/.*\.html$</b>&nbsp;Important&nbsp;information </code> </p> <p> "Viktig information" infogas i "målfältet" på alla sidor som matchar det reguljära uttrycket <span class="codeph"> ^.*/products/.*\.html$ </span>. </p> <p>Därför har du följande: </p> <p> <code> https://www.mydomain.com/products/page1.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p> <code> https://www.mydomain.com/product/oldstuff.html 
      &nbsp;&nbsp;&nbsp;&nbsp;(Will&nbsp;not&nbsp;receive&nbsp;"target"&nbsp;content) </code> </p> <p>I följande exempel: </p> <p> <code> append&amp;nbsp;title&amp;nbsp;regexp&amp;nbsp;^.*\.pdf$&amp;nbsp;Millennium&amp;nbsp;Science </code> </p> <p>"Millennium Science" läggs till i "title"-innehållet på alla sidor som slutar med filnamnstillägget ".pdf". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> URL </span> </p> </td> 
   <td colname="col2"> <p>En URL krävs och anger vilka dokument som ska matas in. </p> <p>URL:en är något av följande: </p> <p> 
     <ul id="ul_C5C74F6D5EA943B293742989EB822751"> 
      <li id="li_382392DB778D4E14BFFC96D35A861951"> En fullständig sökväg, som i https://www.mydomain.com/products.html </li> 
      <li id="li_EA2BD0FB66A44CD0844613316F6174D4"> En del av en bana, som i https://www.mydomain.com/products </li> 
      <li id="li_D5E0D6D897C8493ABBFC65517CD4A7DB"> En URL som använder jokertecken, som i https://www.mydomain.com/*.html </li> 
     </ul> </p> <p>URL-värdet får inte innehålla blankstegstecken. Om alternativet <span class="codeph"> regexp </span> används behandlas URL:en som ett reguljärt uttryck. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> value </span> </p> </td> 
   <td colname="col2"> <p>Ett värde krävs och används för att antingen ersätta eller lägga till i befintligt fältinnehåll. Du kan ange flera värden för samma fältnamn. Exempel: </p> <p>lägga till <b>tangenter</b> https://www.mysite.com/travel/ <b>sommar</b>, <b>strand</b>, <b>sand</b> </p> <p>lägg till <b>nycklar</b> https://www.mysite.com/travel/fare/*.html <b>billiga biljetter</b> </p> <p>I ovanstående exempel läggs ordet"sommar, strand, sand" till i fältet"nycklar" på alla sidor i katalogen"/travel/". Orden "billiga biljetter" läggs också till i fältet "nycklar" på alla sidor i katalogen "/travel/fare/". </p> </td> 
  </tr> 
 </tbody> 
</table>

Se även [Välja innehållstyper som ska crawlas och indexeras](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

## Lägga till fältinmatningsdefinitioner {#task_E86566FA1FF74CF68115C0ADA05172AE}

Du kan använda [!DNL Injections] för att infoga innehåll på dina webbsidor utan att behöva redigera själva sidorna.

Du kan också använda **[!UICONTROL Test]** på [!DNL Injections] sidan. Du anger ett testfältsnamn (till exempel &quot;titel&quot; eller &quot;brödtext&quot;), det ursprungliga fältvärdet (till exempel &quot;Hemsida&quot;) och en test-URL från webbplatsen. Resultatet visas som referens. De aktuella värdena ändras inte under testet.

**Lägga till fältinmatningsdefinitioner**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]**.
1. (Valfritt) På [!DNL Injections] sidan, i [!DNL Test Field Injections] området, anger du testfältet, testets ursprungliga värde och test-URL och klickar sedan på **[!UICONTROL Test]**.
1. I [!DNL Field Injection Definitions] fältet anger du en injektionsdefinition per rad.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om attributinläsare {#concept_9EF38E98811B42CDA41996432B9AD209}

Använd [!DNL Attribute Loader] för att definiera ytterligare indatakällor för att utöka data som crawlas från en webbplats.

>[!NOTE]
>
>Om du vill använda Attribute Loader måste det vara aktiverat på ditt konto av din Adobe-kontorepresentant eller av Adobes support.

Du kan använda en indatakälla för dataflöden för att komma åt innehåll som lagras i ett annat format än det som normalt identifieras på en webbplats. Du gör detta med en av de tillgängliga crawlningsmetoderna. Data från dessa källor kan sedan injiceras i data från crawlat innehåll.

När du har lagt till en Loader-definition för attribut på [!DNL Staged Attribute Loader Definitions] sidan kan du ändra alla konfigurationsinställningar förutom värdena Namn och Typ

På [!DNL Attribute Loader] sidan visas följande information:

* Namnet på den definierade attributinläsarkonfiguration som du har konfigurerat och lagt till.
* En av följande datakälltyper för varje koppling du har lagt till:

   * **Text** - Enkla&quot;platta&quot; filer, kommaavgränsade, tabbavgränsade eller andra konsekvent avgränsade format.
   * **Feed** - XML-flöden.

* Anger om konfigurationen är aktiverad eller inte för nästa crawl och indexering.
* Datakällans adress.

Se även [Hur attributinjektionen fungerar för Text och feed...](../c-about-settings-menu/c-about-metadata-menu.md#section_E059A33D61EE4DB0972A37B8A35E9E16)

Se även [Konfigurera flera attributinläsare](../c-about-settings-menu/c-about-metadata-menu.md#section_4CC49C74EF294608A184E233F215ADFF)

Se även [Om hur du använder Förhandsgranska när du lägger till ett attribut...](../c-about-settings-menu/c-about-metadata-menu.md#section_E9CAB000A94C4D9189786C1EDB1CDB46)

## Hur attributinmatningsprocessen fungerar för Text- och Feed-konfigurationer i attributinläsaren {#section_E059A33D61EE4DB0972A37B8A35E9E16}

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
   <td colname="col3"> <p>För <span class="uicontrol"> text </span>motsvarar varje radavgränsad textrad ett enskilt dokument och tolkas med den angivna avgränsaren, till exempel ett komma eller en tabb. </p> <p>För <span class="uicontrol"> Feed </span>extraheras data från varje dokument med hjälp av ett mönster för reguljära uttryck i följande form: </p> <p> <code class="syntax js"> &lt;${Itemtag}&gt;(.*?)&lt;/${Itemtag}&gt; </code> </p> <p>Skapa en cachelagrad kopia av data med hjälp av <span class="uicontrol"> Karta </span> på <span class="wintitle"> sidan </span> Attributinläsare, och skapa sedan en lista med länkar för crawlern. Data lagras i en lokal cache och fylls i med de konfigurerade fälten. </p> <p>De tolkade data skrivs till det lokala cacheminnet. </p> <p>Cachen läses senare för att skapa de enkla HTML-dokument som behövs för crawlningen. Exempel: </p> <p> <code class="syntax html"> &lt;html&gt;&lt;head&gt; 
      &lt;title&gt;{title}&lt;/title&gt; 
      &lt;meta&nbsp;name="{field}"&nbsp;content="{data}"&nbsp;/&gt; 
      ... 
      &lt;/head&gt;&lt;body&gt; 
      {body} 
      &lt;/body&gt;&lt;/html&gt; </code> </p> <p>Elementet <span class="codeph"> &lt;title&gt; </span> genereras bara när det finns en mappning till metadatafältet Rubrik. På samma sätt genereras elementet <span class="codeph"> &lt;body&gt; </span> bara när det finns en mappning till tabellens metadatafält. </p> <p> <b>Viktigt</b>: Tilldelning av värden till den fördefinierade URL-meta-taggen stöds inte. </p> <p>För alla andra mappningar genereras <span class="codeph"> &lt;meta&gt;- </span> taggar för varje fält som innehåller data i det ursprungliga dokumentet. </p> <p>Fälten för varje dokument läggs till i cachen. För varje dokument som skrivs till cachen skapas även en länk enligt följande exempel: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      &lt;a&nbsp;href="index:Adobe?key=&lt;primary&nbsp;key&nbsp;field&gt;\"&nbsp;/&gt; 
      .... </code> </p> <p>Konfigurationens mappning måste ha ett fält som identifieras som primärnyckel. Den här mappningen utgör nyckeln som används när data hämtas från cachen. </p> <p>Crawlningen känner igen URL- <span class="codeph"> indexet: </span> schemaprefix, som sedan kan komma åt lokalt cachelagrade data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Crawla den cachelagrade dokumentuppsättningen. </p> </td> 
   <td colname="col3"> <p>Indexvärdet <span class="codeph"> : </span> länkar läggs till i crawlerns väntande lista och bearbetas i den normala crawlningssekvensen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Bearbeta varje dokument. </p> </td> 
   <td colname="col3"> <p>Nyckelvärdet för varje länk motsvarar en post i cachen, så om du crawlar varje länk hämtas dokumentets data från cachen. Sedan"sammanfogas" den till en HTML-bild som bearbetas och läggs till i indexet. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Konfigurera flera attributinläsare {#section_4CC49C74EF294608A184E233F215ADFF}

Du kan definiera flera attributinläsarkonfigurationer för vilket konto som helst.

När du lägger till en attributinläsare kan du använda funktionen **[!UICONTROL Setup Maps]** för att hämta ett exempel på datakällan. Uppgifterna granskas med avseende på lämplighet.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Loader-typ för attribut </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Text </p> </td> 
   <td colname="col2"> <p>Avgör avgränsningsvärdet genom att först prova tabbar och sedan lodräta staplar ( <span class="codeph"> | </span>), och slutligen kommatecken ( <span class="codeph"> , </span>). Om du redan har angett ett avgränsningsvärde innan du klickade på <span class="uicontrol"> Konfigurera kartor </span>används det värdet i stället. </p> <p>Det bästa schemat för anpassning gör att kartfälten fylls i med gissningar på rätt tagg- och fältvärden. Dessutom visas en sampling av tolkade data. Välj <span class="uicontrol"> Sidhuvuden i första raden </span> om du vet att filen innehåller en rubrikrad. Installationsfunktionen använder den här informationen för att bättre identifiera de resulterande mappningsposterna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed </p> </td> 
   <td colname="col2"> <p>Hämtar datakällan och utför enkel XML-tolkning. </p> <p>De resulterande XPath-identifierarna visas i taggraderna i tabellen Map och liknande värden i Fält. Dessa rader identifierar bara tillgängliga data och genererar inte de mer komplicerade XPath-definitionerna. Det är dock fortfarande användbart eftersom det beskriver XML-data och identifierar ItemTag. </p> <p> <p>Obs!  Funktionen Setup Maps hämtar hela XML-källan för att utföra analysen. Om filen är stor kan timeout uppstå för den här åtgärden. </p> </p> <p>När det är klart identifierar den här funktionen alla möjliga XPath-objekt, varav många inte är lämpliga att använda. Se till att du undersöker de resulterande kartdefinitionerna och tar bort dem som du inte behöver eller vill ha. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Funktionen Setup Maps fungerar kanske inte för stora XML-datauppsättningar eftersom filparsern försöker läsa hela filen i minnet. Det kan leda till att minnet tar slut. Men när samma dokument bearbetas vid indexeringen läses det inte in i minnet. I stället bearbetas stora dokument &quot;i farten&quot; och läses inte helt in i minnet först.

## Om hur du använder Förhandsgranska när du lägger till en attributinläsare {#section_E9CAB000A94C4D9189786C1EDB1CDB46}

Loader-data för attribut läses in före en Index-åtgärd.

När du lägger till en attributinläsare kan du använda funktionen för **[!UICONTROL Preview]** att validera data, som om du sparade dem. Den kör ett test mot konfigurationen, men utan att spara konfigurationen till kontot. Testet kommer åt den konfigurerade datakällan. Hämtningscachen skrivs dock till en tillfällig plats. den inte hamnar i konflikt med huvudcachemappen som används av indexeringscrawlern.

I Förhandsgranska bearbetas bara standardvärdena för fem dokument, vilket styrs av **Account:IndexConnector-Preview-Max-Documents**. De förhandsvisade dokumenten visas i källformat när de presenteras för indexeringscrawlaren. Visningen liknar funktionen Visa källa i en webbläsare. Du kan navigera bland dokumenten i förhandsvisningsuppsättningen med hjälp av standardnavigeringslänkar.

Förhandsgranskningen stöder inte XML-konfigurationer eftersom sådana dokument bearbetas direkt och inte hämtas till cachen.

## Lägga till en Loader-definition för attribut {#task_A735E5EF763343A9B675E1A3B09AFDBC}

Varje konfiguration för Loader-attribut definierar en datakälla och mappningar som relaterar dataobjekten som definierats för den källan till metadatafälten i indexet.

>[!NOTE]
>
>Om du vill använda Attribute Loader måste det vara aktiverat på ditt konto av din Adobe-kontorepresentant eller av Adobes support.

Innan effekterna av den nya och aktiverade definitionen är synliga för kunderna ska du återskapa platsindexet.

**Lägga till en Loader-definition för attribut**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Stage Attribute Loader Definitions] sidan klickar du på **[!UICONTROL Add New Attribute Loader]**.
1. Ange de konfigurationsalternativ som du vill använda på [!DNL Attribute Loader Add] sidan. Vilka alternativ som är tillgängliga beror på vilken **[!UICONTROL Type]** du har valt.

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
      <td colname="col2"> <p>Det unika namnet på attributets Loader-konfiguration. Du kan använda alfanumeriska tecken. Tecknen"_" och"-" är också tillåtna. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Typ </p> </td> 
      <td colname="col2"> <p>Källan till dina data. Den typ av datakälla du väljer påverkar de alternativ som är tillgängliga på <span class="wintitle"> sidan Lägg till attributinläsare </span> . Du kan välja mellan följande: </p> <p> 
      <ul id="ul_1ADC3DFBC929467385F7465BE8E13635"> 
      <li id="li_64FCD749F55442BAB316BD474128D4F9"> <span class="uicontrol"> Text </span> <p>Enkla platta textfiler, kommaavgränsade, tabbavgränsade eller andra konsekvent avgränsade format. Varje radavgränsad textrad motsvarar ett enskilt dokument och tolkas med den angivna avgränsaren. </p> <p>Du kan mappa varje värde, eller kolumn, till ett metadatafält, som kolumnnumret refererar till, med början vid 1 (ett). </p> </li> 
      <li id="li_2A4F16CE6DCE4114B7F8E4FE156252BB"> <span class="uicontrol"> Feed </span> <p>Hämtar ett primärt XML-dokument som innehåller flera "rader" med information. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datakälltyp: Text</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiverad </p> </td> 
      <td colname="col2"> <p>Aktiverar konfigurationen för användning. Du kan även inaktivera konfigurationen för att förhindra att den används. </p> <p> <b>Obs</b>: Inaktiverade Loader-konfigurationer för attribut ignoreras. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Värdadress </p> </td> 
      <td colname="col2"> <p>Anger adressen till servervärden där data finns. </p> <p>Om du vill kan du ange en fullständig URI (Uniform Resource Identifier)-sökväg till datakälldokumentet som i följande exempel: </p> <p> <code otherprops="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>eller </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>URI:n delas upp i lämpliga poster för fälten Värdadress, Filsökväg, Protokoll och, eventuellt, Användarnamn och Lösenord </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till den enkla platta textfilen, kommaavgränsad, tabbavgränsad eller annan fil med konsekvent avgränsat format. </p> <p>Sökvägen är relativ till värdadressens rot. </p> </td> 
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
      <td colname="col2"> <p>Anger det tecken som du vill använda för att avgränsa varje fält i den angivna datakällfilen. </p> <p>Kommatecknet ( <span class="codeph"> , </span>) är ett exempel på en avgränsare. Kommatecknet fungerar som en fältavgränsare som hjälper till att separera datafält i den angivna datakällfilen. </p> <p>Välj <span class="uicontrol"> Tabb? </span> om du vill använda det vågräta tabbtecknet som avgränsare. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rubriker i första raden </p> </td> 
      <td colname="col2"> <p>Anger att den första raden i datakällfilen endast innehåller rubrikinformation, inte data. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inaktuella dagar </p> </td> 
      <td colname="col2"> <p>Anger det minsta intervallet mellan hämtningar av attributets Loader-data. Index-utlösta hämtningar som inträffar inom intervallet för hämtningsuppdateringsintervall ignoreras. När du anger det här värdet som standard 1 hämtas inte attributets inläsardata mer än en gång inom en 24-timmarsperiod. Alla sökindex som finns inom intervallet för hämtningsuppdateringsintervall använder den senaste datauppsättningen som hämtades. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Karta </p> </td> 
      <td colname="col2"> <p>Anger mappningar kolumn-till-metadata med kolumnnummer. </p> <p> 
      <ul id="ul_981AE2C6D30443BDBFC6575D413732A2"> 
      <li id="li_A42CB9DFFF8C45A7BAC2D471FE96CEBE"> <span class="uicontrol"> Kolumn </span> <p> Anger ett kolumnnummer med den första kolumnen som 1 (ett). Om du vill lägga till nya mappningsrader för varje kolumn klickar du på <span class="wintitle"> + </span>under Åtgärd <span class="uicontrol"> </span>. </p> <p>Du behöver inte referera till varje kolumn i datakällan. I stället kan du välja att hoppa över värden. </p> </li> 
      <li id="li_26E8C9554A5D4BC5A5073D6385E3626F"> <span class="uicontrol"> Fält </span> <p>Definierar det name-attributvärde som används för varje genererad &lt;meta&gt;-tagg. </p> </li> 
      <li id="li_5DFA514B7F9549B98D6CBC095A66033C"> <span class="uicontrol"> Metadata? </span> <p>Gör <span class="uicontrol"> fält </span> till en nedrullningsbar lista där du kan välja definierade metadatafält för det aktuella kontot. </p> <p>Fältvärdet <span class="uicontrol"> kan </span> vara ett odefinierat metadatafält, om så önskas. Ett odefinierat metadatafält är ibland användbart för att skapa innehåll som används av ett <span class="wintitle"> filtreringsskript </span>. </p> <p>Se <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Filtrera skript </a>. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892C95"> <span class="uicontrol"> Primärnyckel? </span> <p>Endast ett fält identifieras som primärnyckel. Det här fältet används som "sekundärnyckel" för att matcha attributets inläsardata med motsvarande dokument i indexet. </p> </li> 
      <li id="li_80DB205525094CE1AA6762BFC7892D96"> <span class="uicontrol"> Ta bort HTML? </span> <p>När det här alternativet är markerat tas alla HTML-taggar som finns i fältets data bort. </p> </li> 
      <li id="li_359D2902859B4C5BADB0BA26F0BA4DC0"> <span class="uicontrol"> Åtgärd </span> <p>Gör att du kan lägga till rader på kartan eller ta bort rader från kartan. Radernas ordning är inte viktig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> <b>Datakälltyp: Feed</b> </p> </td> 
      <td colname="col2"> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiverad </p> </td> 
      <td colname="col2"> <p>Aktiverar konfigurationen för användning. Du kan även inaktivera konfigurationen för att förhindra att den används. </p> <p> <b>Obs</b>: Inaktiverade Loader-konfigurationer för attribut ignoreras. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Värdadress </p> </td> 
      <td colname="col2"> <p>Anger adressen till servervärden där data finns. </p> <p>Om du vill kan du ange en fullständig URI (Uniform Resource Identifier)-sökväg till datakälldokumentet som i följande exempel: </p> <p> <code class="syntax html"> https://www.somewhere.com/some_path/some_file.tsv </code> </p> <p>eller </p> <p> <code class="syntax html"> ftp://user:password@ftpserver.somewhere.com/some_path/some_file.csv </code> </p> <p>URI:n delas upp i lämpliga poster för fälten Värdadress, Filsökväg, Protokoll och, eventuellt, Användarnamn och Lösenord. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Filsökväg </p> </td> 
      <td colname="col2"> <p>Anger sökvägen till det primära XML-dokumentet som innehåller flera "rader" med information. </p> <p>Sökvägen är relativ till värdadressens rot. </p> </td> 
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
      <td colname="col2"> <p>Identifierar XML-elementet som du kan använda för att identifiera enskilda XML-rader i datakällfilen som du har angett. </p> <p>I följande Feed-fragment av ett Adobe XML-dokument är ItemTag-värdet <span class="codeph"> post </span>: </p> <p> <code class="syntax xml"> &lt;?xml&nbsp;version="1.0"&nbsp;encoding="utf-8"?&gt; 
        &lt;!DOCTYPE&nbsp;gsafeed&nbsp;PUBLIC&nbsp;"-//Google//DTD&nbsp;GSA&nbsp;Feeds//EN"&nbsp;""&gt; 
        &lt;gsafeed&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;datasource&gt;marketplace&lt;/datasource&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;feedtype&gt;incremental&lt;/feedtype&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/header&gt; 
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;group&nbsp;action="add"&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=1&nbsp;action="add"&nbsp;mimetype="text/html"displayurl="https://www.adobe.com/cfusion/marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=1"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="1"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_air.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;AIR&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Discover&nbsp;new&nbsp;applications&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;AIR&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Discover&nbsp;new&nbsp;applications&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;&lt;/cntent&gt; 
        &lt;/record&gt; 
        &lt;record&nbsp;url=https://www.adobe.com/cfusion/marketplace_gsa/ 
        index.cfm?event=marketplace.home&amp;amp;marketplaceid=2&nbsp;action="add"&nbsp;mimetype="text/html"&nbsp;displayurl="https://www.adobe.com/cfusion/ 
        marketplace/index.cfm?event=marketplace.home&amp;amp;marketplaceid=2"&gt; 
        &lt;metadata&gt; 
        &lt;meta&nbsp;name="mp_mkt"&nbsp;content="2"/&gt; 
        &lt;meta&nbsp;name="mp_logo"&nbsp;content="/images/marketplace/ 
        dbreferenced/marketplaceicons/icn_photoshop.png"/&gt; 
        &lt;meta&nbsp;name="title"&nbsp;content="Adobe&nbsp;Photoshop&nbsp;Marketplace"/&gt; 
        &lt;meta&nbsp;name="description"&nbsp;content="Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;..."/&gt; 
        &lt;/metadata&gt; 
        &lt;content&gt;&lt;![CDATA[&lt;html&gt;&lt;head&gt;&lt;title&gt;Adobe&nbsp;Photoshop&nbsp;Marketplace&lt;/title&gt;&lt;/head&gt;&lt;body&gt;Extend&nbsp;your&nbsp;creative&nbsp;possibilities&nbsp;...&lt;/body&gt;&lt;/html&gt;]]&gt;/content&gt; 
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
      <td colname="col1"> <p>Fältnamn för korsreferens </p> </td> 
      <td colname="col2"> <p>Anger ett metadatafält vars värden används som söknycklar till data i konfigurationen för attributinläsaren. Om inget värde har valts (<b>—Ingen—</b>) är den här konfigurationens data inte tillgängliga för användning i rangordningsberäkningar (<b>Regler</b> &gt; <b>Rankningsregler</b> &gt; <b>Redigera regler</b>). När du väljer ett värde används värdena i det här fältet för att korsreferera webbplatssöknings-/försäljningsdokument med data från den här konfigurationen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inaktuella dagar </p> </td> 
      <td colname="col2"> <p>Anger det minsta intervallet mellan hämtningar av attributets Loader-data. Index-utlösta hämtningar som inträffar inom intervallet för hämtningsuppdateringsintervall ignoreras. När du anger det här värdet som standard 1 hämtas inte attributets inläsardata mer än en gång inom en 24-timmarsperiod. Alla sökindex som finns inom intervallet för hämtningsuppdateringsintervall använder den senaste datauppsättningen som hämtades. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Karta </p> </td> 
      <td colname="col2"> <p>Gör att du kan ange mappningar av XML-element-till-metadata med XPath-uttryck. </p> <p> 
      <ul id="ul_604108C0277C4892AE8A40CA39889ABD"> 
      <li id="li_0AF92270AE9F4BA8B2C7EE41FABC0F34"> <span class="uicontrol"> Tagg </span> <p>Anger en XPath-representation av tolkade XML-data. I exemplet med Adobe XML-dokumentet ovan, under alternativet Item-tag, kan det mappas med följande syntax: </p> <p> <code class="syntax xml"> /record/@displayurl&nbsp;-&gt;&nbsp;page-url 
        /record/metadata/meta[@name='title']/@content&nbsp;-&gt;&nbsp;title 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;desc 
        /record/metadata/meta[@name='description']/@content&nbsp;-&gt;&nbsp;body </code> </p> <p>Syntaxen ovan innebär följande: </p> <p> 
        <ul id="ul_6400EBD08D424EADA1612FE4F7EFB640"> 
        <li id="li_9958F9B40D42434195597DBA9F2AF28F"> <code class="syntax xml"> /record/@displayurl&amp;nbsp;-&gt;&amp;nbsp;page-url </code> <p>Attributet <span class="codeph"> displayURL </span> för <span class="codeph"> record </span> element mappas till <span class="codeph"> page-url för metadatafältet </span>. </p> </li> 
        <li id="li_759013EA02CD48BE971A55B0A6A11424"> <code class="syntax xml"> /record/metadata/meta[@name='title']/@content&amp;nbsp;-&gt;&amp;nbsp;title </code> <p>Innehållsattributet <span class="codeph"> för alla </span> metaelement <span class="codeph"> som finns inuti ett </span> metadataelement, som finns inuti ett <span class="codeph"> postelement, </span> vars namnattribut är <span class="codeph"> title, mappas till metadatafältet¥ </span> <span class="codeph"> </span><span class="codeph"> </span>. </p> </li> 
        <li id="li_E741CA59197D462EB2946EDE874AFDC8"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;desc </code> <p>Innehållsattributet <span class="codeph"> för alla </span> metaelement <span class="codeph"> som finns inuti ett </span> metadataelement, som finns inuti <span class="codeph"> postelementet </span> , vars name-attribut är <span class="codeph"> description, mappas till metadatafältet¥ desc </span> <span class="codeph"> </span><span class="codeph"> </span>. </p> </li> 
        <li id="li_E35EAE3D284D46D485D9064D7BB6AB13"> <code class="syntax xml"> /record/metadata/meta[@name='description']/@content&amp;nbsp;-&gt;&amp;nbsp;body </code> <p>Innehållsattributet <span class="codeph"> för </span> alla <span class="codeph"> metaelement </span> som finns i ett <span class="codeph"> metadataelement, som finns i </span> postelementet <span class="codeph"> , vars name-attribut är </span> <span class="codeph"> </span><span class="codeph"> </span>description, mappas till metadatafältet¥. </p> </li> 
        </ul> </p> <p>XPath är en relativt komplicerad notation. Mer information finns på följande plats: </p> <p>Se <a href="https://www.w3schools.com/xpath/" scope="external" format="html"> https://www.w3schools.com/xpath/ </a> </p> </li> 
      <li id="li_8147075D7ACD4811A7ED335F23FE62A6"> <span class="uicontrol"> Fält </span> <p>Definierar det name-attributvärde som används för varje genererad <span class="codeph"> &lt;meta&gt;- </span> tagg. </p> </li> 
      <li id="li_2380199D63BF425A919606D8232FA6E2"> <span class="uicontrol"> Metadata? </span> <p>Gör <span class="uicontrol"> fält </span> till en nedrullningsbar lista där du kan välja definierade metadatafält för det aktuella kontot. </p> <p>Fältvärdet <span class="uicontrol"> kan </span> vara ett odefinierat metadatafält, om så önskas. Ett odefinierat metadatafält är ibland användbart för att skapa innehåll som används av <span class="wintitle"> Filtrera skript </span>. </p> <p>Se <a href="../c-about-settings-menu/c-about-filtering-menu.md#concept_E56B73D625854AB2A899EF2D56CFCB47" type="concept" format="dita" scope="local"> Filtrera skript </a>. </p> <p>När Loader-attribut bearbetar XML-dokument med flera träffar i ett kartfält sammanfogas de olika värdena till ett enda värde i det cachelagrade dokumentet. Som standard kombineras dessa värden med en kommaavgränsare. Anta dock att motsvarande <span class="wintitle"> fältvärde </span> är ett definierat metadatafält. Dessutom har fältet attributet <span class="wintitle"> Allow Lists </span> angivet. I det här fallet används fältets listavgränsarvärde, som är den första avgränsaren som definieras, i sammanfogningen. </p> </li> 
      <li id="li_DEA24003E97E406DA2510C43CCFDC70E"> <span class="uicontrol"> Primärnyckel? </span> <p>Endast ett fält identifieras som primärnyckel. Det här fältet används som "sekundärnyckel" för att matcha attributets inläsardata med motsvarande dokument i indexet. </p> </li> 
      <li id="li_80D6AF130FCE40AC972FE4B605B86BF6"> <span class="uicontrol"> Ta bort HTML? </span> <p>När det här alternativet är markerat tas alla HTML-taggar som finns i fältets data bort. </p> </li> 
      <li id="li_D40E2F9AD8AD49FC9AC4B8C75BA31E28"> <span class="uicontrol"> Åtgärd </span> <p>Gör att du kan lägga till rader på kartan eller ta bort rader från kartan. Radernas ordning är inte viktig. </p> </li> 
      </ul> </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Valfritt) Klicka **[!UICONTROL Setup Maps]** för att hämta ett exempel på datakällan. Uppgifterna granskas med avseende på lämplighet.
1. Klicka **[!UICONTROL Add]** för att lägga till konfigurationen på [!DNL Attribute Loader Definitions] sidan.
1. På [!DNL Attribute Loader Definitions] sidan klickar du på **[!UICONTROL rebuild your staged site index]**.
1. (Valfritt) Gör något av följande på [!DNL Attribute Loader Definitions] sidan:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en Loader-definition för attribut {#task_AA2D1B2BCAFA44A6A0C59A0318274E80}

Du kan redigera en befintlig attributinläsare som du har definierat.

>[!NOTE]
>
>Om du vill använda Attribute Loader måste det vara aktiverat på ditt konto av din Adobe-kontorepresentant eller av Adobes support.

Du kan inte ändra alla alternativ för attributinläsare, till exempel namnet på attributinläsaren eller typen i [!DNL Type] listrutan.

**Redigera en Loader-definition för attribut**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Attribute Loader] sidan, under [!DNL Actions] kolumnrubriken, klickar du **[!UICONTROL Edit]** på ett namn på den attributinläsardefinition vars inställningar du vill ändra.
1. Ange önskade alternativ på [!DNL Attribute Loader Edit] sidan.

   Se tabellen med alternativ under [Lägga till en attributinläsardefinition](../c-about-settings-menu/c-about-metadata-menu.md#task_A735E5EF763343A9B675E1A3B09AFDBC).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) På [!DNL Attribute Loader Definitions] sidan klickar du på **[!UICONTROL rebuild your staged site index]**.
1. (Valfritt) Gör något av följande på [!DNL Attribute Loader Definitions] sidan:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Kopiera en Loader-definition för attribut {#task_9B40D5ECFC81411E9480F62A0FD5F2E0}

Du kan kopiera en befintlig attributinläsardefinition som du vill använda som bas för en ny attributinläsare.

>[!NOTE]
>
>Om du vill använda Attribute Loader måste det vara aktiverat på ditt konto av din Adobe-kontorepresentant eller av Adobes support.

När du kopierar en attributinläsardefinition är den kopierade definitionen inaktiverad som standard. Om du vill aktivera eller aktivera definitionen måste du redigera den från [!DNL Attribute Loader Edit] sidan och markera **[!UICONTROL Enable]**.

Se [Redigera en attributinläsardefinition](../c-about-settings-menu/c-about-metadata-menu.md#task_AA2D1B2BCAFA44A6A0C59A0318274E80).

**Kopiera en Loader-definition för attribut**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Attribute Loader] sidan, under [!DNL Actions] kolumnrubriken, klickar du **[!UICONTROL Copy]** på ett namn på den attributinläsardefinition vars inställningar du vill duplicera.
1. Ange det nya namnet på definitionen på [!DNL Attribute Loader Copy] sidan.
1. Klicka på **[!UICONTROL Copy]**.
1. (Valfritt) Gör något av följande på [!DNL Attribute Loader Definitions] sidan:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Byta namn på en Loader-definition för attribut {#task_58D5DFD7EBC04111BCB91118E4440DB4}

Du kan ändra namnet på en befintlig Loader-definition för attribut.

>[!NOTE]
>
>Om du vill använda Attribute Loader måste det vara aktiverat på ditt konto av din Adobe-kontorepresentant eller av Adobes support.

**Byta namn på en Loader-definition för attribut**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Attribute Loader] sidan, under [!DNL Actions] kolumnrubriken, klickar du på **[!UICONTROL Rename]** namnet på den attributinläsardefinition som du vill ändra.
1. På [!DNL Attribute Loader Rename] sidan anger du det nya namnet på definitionen i [!DNL Name] fältet.
1. Klicka på **[!UICONTROL Rename]**.
1. (Valfritt) Gör något av följande på [!DNL Attribute Loader Definitions] sidan:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Läser in attributinläsardata {#task_2F3C55189B0A4049AB2113F2291CC181}

Du kan hämta konfigurerade attributinläsardata till webbplatssökning/försäljning.

På [!DNL Data Load] sidan visas följande information om statusen för den senaste inläsningen av attributdata:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Statusfält </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Anger om det senaste datainläsningsförsöket lyckades eller misslyckades. Eller så visas status för en datainläsningsåtgärd som redan pågår. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Starttid </p> </td> 
   <td colname="col2"> <p>Visar det datum och den tid då den senaste datainläsningen startades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stopptid </p> </td> 
   <td colname="col2"> <p>Visar datum och tid för slutförande av den senaste datainläsningen. Eller så anger det att den aktuella datainläsningen fortfarande pågår. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Läs in Loader-data för attribut**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Attribute Loader Definitions] sidan klickar du på **[!UICONTROL Load Attribute Loader Data]**.
1. Gör något av följande på **[!UICONTROL Attribute Loader Data Load]** sidan:

   * Klicka **[!UICONTROL Start Load]** för att starta inläsningen.

      Under en datainläsningsåtgärd ger **raden Förlopp** information om dess förlopp.

   * Klicka **[!UICONTROL Stop Load]** för att stoppa inläsningen.

1. Klicka **[!UICONTROL Close]** för att gå tillbaka till [!DNL Attribute Loader Definitions] sidan.

## Förhandsgranska attributinläsardata {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

Du kan använda Förhandsgranska för att visa dina senast inlästa attributinläsardata.

I kolumnen Rad i tabellen visas numret för varje datarad, vilket anger i vilken ordning attributets Loader-värden lästes in.

De återstående kolumnerna visar de värden som är associerade med varje post.

Om tabellen är tom betyder det att du inte har läst in några Loader-data för Attribute. Du kan stänga [!DNL Attribute Loader Data Preview] sidan och sedan läsa in Loader-data för attribut.

Se [Läsa in inläsningsdata](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)för attribut.

**Förhandsgranska Loader-data för attribut**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Attribute Loader Definitions] sidan, under [!DNL Actions] kolumnen, klickar du **[!UICONTROL Preview]** för den konfiguration vars hämtade data du vill visa.
1. Använd navigerings- och visningsalternativen längst upp och längst ned på sidan för att visa data på [!DNL Attribute Loader Data Preview] sidan.

   Klicka på en kolumnrubrik i tabellen om du vill sortera data i stigande eller fallande ordning.
1. Gör något av följande:

   * Klicka **[!UICONTROL Download to Desktop]** för att hämta och spara tabellen som en .xlt-fil.
   * Stäng sidan när du är klar med förhandsgranskningen av Loader-data för attribut och återgå till den tidigare visade sidan.

## Visa inställningarna för en attributinläsardefinition {#task_EA99A9694FE948ADA82C1DBA0667851B}

Du kan granska konfigurationsinställningarna för en befintlig attributinläsardefinition.

När en attributinläsardefinition har lagts till på [!DNL Attribute Loader Definitions] sidan kan du inte ändra dess typinställning. I stället måste du ta bort definitionen och sedan lägga till en ny.

>[!NOTE]
>
>Om du vill använda Attribute Loader måste det vara aktiverat på ditt konto av din Adobe-kontorepresentant eller av Adobes support.

**Så här visar du inställningarna för en Loader-definition för attribut**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Attribute Loader] sidan, under [!DNL Actions] kolumnrubriken, klickar du **[!UICONTROL Edit]** på ett namn på den attributinläsardefinition vars inställningar du vill granska eller redigera.

## Visa loggen från den senaste inläsningen av attributinläsarens data {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

Du kan använda [!DNL View Log] för att undersöka dataloggfilen för Loader-attributet för den senaste hämtningsprocessen. Du kan också använda loggvyn för att övervaka en nedladdning som körs.

Se [Läsa in inläsningsdata](../c-about-settings-menu/c-about-metadata-menu.md#task_2F3C55189B0A4049AB2113F2291CC181)för attribut.

**Så här visar du loggen från den senaste inläsningen av attributinläsarens data**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Attribute Loader Definitions] sidan klickar du på **[!UICONTROL View Log]**. Loggsida,
1. Använd navigerings- och visningsalternativen längst upp och längst ned på sidan för att visa logginformationen på [!DNL Attribute Loader Data Log] sidan.
1. När du är klar stänger du sidan för att gå tillbaka till [!DNL Attribute Loader Definitions] sidan.

## Ta bort en Loader-definition för attribut {#task_E8980F66888B476E98C228C1D307EDF8}

Du kan ta bort en befintlig attributinläsardefinition som du inte längre behöver eller använder.

>[!NOTE]
>
>Om du vill använda Attribute Loader måste det vara aktiverat på ditt konto av din Adobe-kontorepresentant eller av Adobes support.

**Ta bort en Loader-definition för attribut**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Attribute Loader]**.
1. På [!DNL Attribute Loader Definitions] sidan, under [!DNL Actions] kolumnrubriken, klickar du **[!UICONTROL Delete]** på namnet på den attributinläsardefinition som du vill ta bort.
1. På [!DNL Attribute Loader Delete] sidan klickar du på **[!UICONTROL Delete]**.
