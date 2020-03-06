---
description: Du kan använda Ord och språk för att bestämma hur söktermer matchas mot innehållet på dina webbsidor.
seo-description: Du kan använda Ord och språk för att bestämma hur söktermer matchas mot innehållet på dina webbsidor.
seo-title: Om ord och språk
solution: Target
title: Om ord och språk
topic: Linguistics,Site search and merchandising
uuid: 793d7a40-4609-44b8-a170-536eb1434537
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Om ord och språk{#about-words-language}

Du kan använda [!DNL Words & Language] för att avgöra hur söktermer matchas mot innehållet på dina webbsidor.

## Använda ord och språk {#concept_CEB4B9576F3C4E2EB87B352EEC738D79}

Innan effekterna av [!DNL Words & Language] inställningarna är tillgängliga för webbplatsbesökare, inklusive ändringar som du gör i dessa inställningar, måste du generera om platsindexet. Återskapande innebär, till skillnad från indexering, inte att webbsidorna crawlas, och tar bara några sekunder.

## Konfigurera hur söktermer matchas med ditt webbinnehåll {#task_351A9144A51F4B41923BDBACDEF3B616}

Du kan använda Ord och språk för att avgöra hur webbplatssökning/försäljning matchar söktermer med innehållet på dina webbsidor.

<!-- 

t_configuring_how_search_terms_matched_to_your_web_content.xml

 -->

**Så här konfigurerar du hur söktermer matchas mot ditt webbinnehåll**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]** på produktmenyn.
1. Ange önskade alternativ på [!DNL Words & Languages] sidan.

   <!-- 
   
   r_words_and_languages_options.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Ärendekänslighet </p> </td> 
      <td colname="col2"> <p>Inte markerat som standard. </p> <p>Avgör om versaler ska särskiljas från gemener. Om du väljer det här alternativet kan du t.ex. skilja"Slutfört" från"Klart", och sökresultaten kan variera mellan de två. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Diakritisk känslighet </p> </td> 
      <td colname="col2"> <p>Markerad som standard. </p> <p> Avgör om ord som innehåller diakritiska tecken ska särskiljas från ord som inte gör det. Om du till exempel väljer det här alternativet särskiljs"pagina" från"página". Avmarkera det här alternativet om du har en webbplats som använder icke-engelska språk. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nummer </p> </td> 
      <td colname="col2"> <p>Markerad som standard. </p> <p>Avgör om ord som innehåller siffror ska indexeras. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignorera apostrofer </p> </td> 
      <td colname="col2"> <p>Inte markerat som standard. </p> <p>Apostrofer tas bort från frågor. Om du till exempel söker efter "Tree's" returneras samma resultat som om du söker efter "Tree". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignorera bindestreck </p> </td> 
      <td colname="col2"> <p>Inte markerat som standard. </p> <p>Bindestreck tas bort från frågor. En sökning efter "blue-bell" returnerar till exempel samma resultat som en sökning efter "bluebell". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Partiell alfanumerisk matchning </p> </td> 
      <td colname="col2"> <p>Inte markerat som standard. </p> <p>När du väljer det här alternativet kan du dela tokens i alfabetiska numeriska övergångar så att fritextmatchningar tillåts för delar eller produkttokens. </p> <p>Anta till exempel att du har en identifierare för <span class="codeph"> 910XT </span> i brödtexten för en eller flera sidor på en webbplats. När det här alternativet <i>inte</i> är markerat hittar <span class="keyword"> Adobe Search&amp;Promote </span> matchningar för den här produktidentifieraren när du söker efter <span class="codeph"> 910XT </span>. Och när <span class="uicontrol"> Search Concat-Div-Enable är aktiverat </span> hittar <span class="keyword"> Adobe Search&amp;Promote </span> även <span class="codeph"> 910 XT </span>. Förekomster av <span class="codeph"> 910 </span> eller <span class="codeph"> XT hittas dock inte </span> enbart. </p> <p>När du väljer <span class="uicontrol"> Delvis alfanumerisk matchning </span>delas dessa blandade alfanumeriska variabler upp i flera variabler. En produktidentifierare som <span class="codeph"> XYZ123 </span> indexeras till exempel till tre tokens: <span class="codeph"> XYZ123 </span>, <span class="codeph"> XYZ </span>och <span class="codeph"> 123 </span>. Den funktionen gör att du kan söka efter fri text på valfri plats i sökningen. </p> <p>Anta att du har produktidentifieraren <span class="codeph"> AB910XT i ett annat exempel </span>. Om du väljer <span class="uicontrol"> Delvis alfanumerisk matchning </span> och <i>har</i> Search Concat-Div-Enable <span class="uicontrol"> aktiverat, indexerar </span> Adobe Search&amp;Promote <span class="keyword"> det som </span> AB910XT <span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span><span class="codeph"> </span>,¥ AB,¥ 910¥ och XT¥. När en användare sedan söker efter <span class="codeph"> till exempel 910XT </span>utökas sökningen så att den även söker efter instanser av <span class="codeph"> 910XT </span>, <span class="codeph"> 910 </span>eller <span class="codeph"> XT </span>. </p> <p> <p>Obs!  <span class="uicontrol"> Search Concat-Div-Enable </span> är inte aktiverat som standard. Kontakta teknisk support för att aktivera funktionen. </p> </p> <p> <p>Obs!  <span class="uicontrol"> Partiell alfanumerisk matchning </span> används globalt för alla indexerade fält. Det påverkar dock endast fritextmatchning. påverkar inte exakt matchning eller intervallmatchning. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ljudliknande matchning </p> </td> 
      <td colname="col2"> <p>Markerad som standard. </p> <p>Ord som låter lika matchas, till exempel"hälsa" och"hälsa". Med den här funktionen kan kunden enkelt söka trots att ett ord är felstavat. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Alternativa ordformer </p> </td> 
      <td colname="col2"> <p>Standardvärdet är <b>alternativa ordformer</b>. </p> <p>Du kan välja mellan följande alternativ i listrutan Alternativa ordformer: 
      <ul id="ul_CAC73FB4D1384312BB5DD327D3D66948"> 
      <li id="li_F4E76CD27EA34AC5BC81E648BC6CBA4C"><b>Ingen</b> <p>Inga ordformer eller alternativa ordformer används vid indexering. </p> </li> 
      <li id="li_3186FD1F3BC94A5CB66FFF8EA6726D81"><b>Standardformulär för alternativa ord</b> <p>Stemmning utförs automatiskt under indexering. </p> </li> 
      <li id="li_5815DE0795E0423C9C84C62B96A3F841"><b>Domänordlista</b> <p>Domänordlistor som du anger som ordlista används som en källa med alternativa ordformer. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" type="concept" format="dita" scope="local"> Om ordlistor </a>. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-dictionaries.md#task_541E8453A12F4A8E89CF6F595469F074" type="task" format="dita" scope="local"> Konfigurera en ordlista som en ordlista </a>. </p> </li> 
      </ul> </p> <p>Om frasordsättning är aktiverat i <span class="keyword"> Adobe Search&amp;Promote </span>ska du vara medveten om att alternativa ordformer också förekommer i fraser. </p> <p>Se <a href="../c-searchpromote-release-notes/c-rn-06-19-14-version-815.md#concept_E8CEBC65A28A4E61BDE69B4B4DA55E73" format="dita" scope="local"> Search&amp;Promote 8.15.0 Release Notes (6/19/2014) </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Språk </p> </td> 
      <td colname="col2"> <p>Standard är <b>engelska (USA)</b>. </p> <p>Det valda språket säkerställer att datum och numeriska värden tolkas enligt konventionerna som används i den valda delen av världen. </p> <p>När <span class="uicontrol"> Alternativa ordformer </span> är inställda på <span class="uicontrol"> Alternativa ordformer </span> eller till <span class="uicontrol"> Domänordlista </span>ändras ordformulär och ordslut enligt språkreglerna för det valda språket. </p> <p>Som standard används språkinställningen inte för att avgöra vilket språk som ska användas för sidor som läses från webbplatsen. Språket för en lässida avgörs av dess HTTP-huvuden eller av metataggar på själva sidan. Din webbplats kan innehålla sidor på många olika språk. Varje sida läses och indexeras korrekt, oavsett vilket språk du väljer här. </p> <p>Om du använder Unicode-teckenuppsättningskodning som UTF-8 för vissa sidor på webbplatsen måste du se till att språket för var och en av dessa sidor är korrekt angivet. Om rätt HTTP-rubriker eller metataggar inte finns för dina Unicode-dokument kan du använda <span class="uicontrol"> Settings </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Injektioner </span> för att ange rätt språk. </p> <p>Vill du markera <span class="uicontrol"> Tillämpa på dokument utan angivet språk? </span> om du vill använda språkinställningen för sidor som läses från din webbplats och som inte har någon explicit inställning. Använd den här inställningen när endast <i>vissa</i> av dina dokument saknar språkinställningar. Använd <span class="uicontrol"> Inställningar </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Injektioner </span> om <i>inget</i> av dokumenten har språkinställningar, eller om uppsättningen av de berörda dokumenten är en välkänd och hanterligt liten lista. </p> <p>Se <a href="../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5" type="concept" format="dita" scope="local"> Om injektioner </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Använda Decompounder? </p> </td> 
      <td colname="col2"> <p> <p>Obs!  Den här funktionen används endast för danska och tyska. Den här funktionen är inte heller aktiverad som standard. Kontakta teknisk support för att aktivera funktionen. När det är aktiverat <b>använder du Decompounder?</b> visas bara i användargränssnittet om du väljer <span class="uicontrol"> danska </span> eller <span class="uicontrol"> tyska </span> i <span class="uicontrol"> listrutan </span> Språk som beskrivs ovan i den här tabellen. </p> </p> <p>När du väljer <span class="uicontrol"> Använd dekomprimering? </span>, bryter tjänsten ned sammansatta ord för danska eller tyska som tillåter indexering av komponentord tillsammans med de ursprungliga sammansatta orden. </p> <p>Om du vill se hur den här funktionen fungerar anger du ord i textfältet och klickar sedan på <span class="uicontrol"> Testa </span>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Settings]**.
1. Om du vill förhandsgranska resultatet av ändringarna klickar du på **[!UICONTROL regenerate your staged site index]** för att återskapa det mellanlagrade webbplatsindexet.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

