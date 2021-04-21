---
description: En uppdaterare som rör syntax och regler för att skapa reguljära uttryck.
solution: Target
title: Reguljära uttryck
topic-legacy: Appendices,Site search and merchandising
uuid: 369b54f6-372a-41de-bb5d-3ae0bd640199
exl-id: 6deb9385-9b17-47c2-b6d9-b63f13df8399
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 0%

---

# Reguljära uttryck{#regular-expressions}

En uppdaterare som rör syntax och regler för att skapa reguljära uttryck.

Se även [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Syntax för reguljära uttryck**

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Text</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Ett enda tecken </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [chars] </p> </td> 
   <td colname="col3"> <p> Klassen Character: Ett tecken </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> [^chars] </p> </td> 
   <td colname="col3"> <p>Klassen Character: Inget tecken </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> text1|text2 </p> </td> 
   <td colname="col3"> <p> Alternativ: text1 eller text2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Kvantifierare</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ? </p> </td> 
   <td colname="col3"> <p> 0 eller 1 av föregående text </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> * </p> </td> 
   <td colname="col3"> <p> 0 eller N av föregående text (N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> + </p> </td> 
   <td colname="col3"> <p>1 eller N av föregående text (N &gt; 1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Gruppering</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> (text) </p> </td> 
   <td colname="col3"> <p> Gruppering av text, antingen för att ange kanterna för ett alternativ eller för att skapa bakåtreferenser där den n:e gruppen används i RHS för en RewriteRule med $N) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Fästpunkter</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> ^ </p> </td> 
   <td colname="col3"> <p> Början av linjefästpunkt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p> $ </p> </td> 
   <td colname="col3"> <p> Linjeslut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Escaping</b> </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>\char </p> </td> 
   <td colname="col3"> <p>Escape the particular char. Om du till exempel vill ange tecknen ".[]()" och så vidare. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Regler om reguljära uttryck**

* Ett vanligt tecken, inte ett av specialtecknen som beskrivs nedan, är ett reguljärt uttryck med ett tecken som matchar sig självt.
* Ett omvänt snedstreck (\) följt av ett specialtecken är ett reguljärt uttryck med ett tecken som matchar specialtecknet. Specialtecken är följande:

   * `.` (punkt),  `*` (asterisk),  `?` (frågetecken),  `+` (plustecken),  `[` (vänster hakparentes),  `|` (vertikalt rör) och  `\` (omvänt snedstreck) är alltid specialtecken, utom när de visas inom hakparenteser.
   * `^` (cirkumflex eller cirkumflex) är speciellt i början av ett reguljärt uttryck eller när det omedelbart följer vänster om ett par hakparenteser.
   * `$` (dollartecken) är specialtecken i slutet av ett reguljärt uttryck.
   * `.` (punkt) är ett reguljärt uttryck med ett tecken som matchar alla tecken, inklusive extra koduppsättningstecken med undantag för radbyten.
   * En sträng med tecken som inte är tom och som omges av `[ ]` (vänster och höger hakparentes) är ett reguljärt uttryck med ett tecken som matchar ett tecken, inklusive extratecken för koduppsättningen, i strängen.

      Om det första tecknet i strängen däremot är ett `^` (cirflex) matchar det reguljära uttrycket med ett tecken alla tecken, inklusive extratecken, med undantag för den nya raden och de återstående tecknen i strängen.

      `^` har bara den här speciella betydelsen om den förekommer först i strängen. Du kan använda `-` (minustecken) för att ange ett intervall med efterföljande tecken, inklusive extratecknen för koduppsättningen. [0-9] motsvarar till exempel [0123456789].

      Tecken som anger intervallet måste komma från samma koduppsättning. När tecknen kommer från olika koduppsättningar matchas ett av tecknen som anger intervallet. `-` förlorar den här speciella betydelsen om den inträffar först (efter en inledande `^`, om det finns någon) eller sist i strängen. `]` (höger hakparentes) avslutar inte en sådan sträng när den är det första tecknet i den, efter en inledande `^`, om det finns någon. `[]a-f]` matchar till exempel antingen `]` (höger hakparentes) eller en av ASCII-bokstäverna a till och med f. De fyra tecknen som anges som specialtecken ovan står för sig själva inom en sådan teckensträng.

**Regler för att skapa reguljära uttryck från reguljära uttryck med ett tecken**

Du kan använda följande regler för att skapa reguljära uttryck från reguljära uttryck med ett tecken:

* Ett reguljärt uttryck med ett tecken är ett reguljärt uttryck som matchar det reguljära uttrycket med ett tecken.
* Ett reguljärt uttryck med ett tecken följt av en `*` (asterisk) är ett reguljärt uttryck som matchar noll eller flera förekomster av det reguljära uttrycket med ett tecken, som kan vara ett tilläggstecken i koduppsättningen. Om det finns något alternativ väljs den längsta vänstra strängen som tillåter en matchning.
* Ett reguljärt uttryck med ett tecken följt av ett `?` (frågetecken) är ett reguljärt uttryck som matchar noll eller en förekomst av det reguljära uttrycket med ett tecken, som kan vara ett tilläggstecken i koduppsättningen. Om det finns något alternativ väljs den längsta vänstra strängen som tillåter en matchning.
* Ett reguljärt uttryck med ett tecken följt av ett `+` (plustecken) är ett reguljärt uttryck som matchar en eller flera förekomster av det reguljära uttrycket med ett tecken, som kan vara ett tilläggstecken i koduppsättningen. Om det finns något alternativ väljs den längsta vänstra strängen som tillåter en matchning.
* Ett reguljärt uttryck med ett tecken följt av `{m}`, `{m,}` eller `{m,n}` är ett reguljärt uttryck som matchar ett intervall med förekomster av det reguljära uttrycket med ett tecken. Värdena för m och n får inte vara negativa heltal under 256. `{m}` matchar exakt m förekomster; `{m,}` matchar minst m förekomster; `{m,n}` matchar alla förekomster mellan m och n. När det finns ett val matchar det reguljära uttrycket så många förekomster som möjligt.
* Sammanfogningen av reguljära uttryck är ett reguljärt uttryck som matchar sammanfogningen av strängarna som matchas av varje komponent i det reguljära uttrycket.
* Ett reguljärt uttryck mellan teckensekvenserna ( och ) är ett reguljärt uttryck som matchar det reguljära uttryck som inte är indraget.
* Ett reguljärt uttryck följt av ett `|` (vertikalt vertikalt rör) följt av ett reguljärt uttryck är ett reguljärt uttryck som matchar antingen det första reguljära uttrycket (före vertikalt vertikalt rör) eller det andra reguljära uttrycket (efter vertikalt rör).

Du kan också begränsa ett reguljärt uttryck så att det bara matchar ett inledande segment eller det sista segmentet i en linje, eller både och.

* Ett `^` (cirflex) i början av ett reguljärt uttryck begränsar det reguljära uttrycket så att det matchar ett inledande segment på en rad.
* Ett `$`-tecken (dollartecken) i slutet av ett helt reguljärt uttryck begränsar det reguljära uttrycket så att det matchar ett linjesegment.
* Konstruktionen ^regular expression$ begränsar det reguljära uttrycket så att det matchar hela raden.

Det finns några fördefinierade teckenklassnamn som du kan använda i stället för reguljära uttryck med komplexa hakparenteser. En siffra kan till exempel representeras av det reguljära uttrycket [0-9] för ett tecken eller av det reguljära uttrycket för en teckenklass [[:digit:]].

De fördefinierade teckenklasserna och deras innebörd är följande:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Klassen Character </p> </th> 
   <th colname="col2" class="entry"> <p>Betydelse </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:alnum:]] </p> </td> 
   <td colname="col2"> <p> Ett alfabetiskt tecken eller en siffra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:alpha:]] </p> </td> 
   <td colname="col2"> <p>Ett alfabetiskt tecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:blank:]] </p> </td> 
   <td colname="col2"> <p>Ett mellanslag eller en tabb. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:cntrl:]] </p> </td> 
   <td colname="col2"> <p> En kontrollkod. ej utskrivbara tecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:digit:]] </p> </td> 
   <td colname="col2"> <p>En siffra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:diagram:]] </p> </td> 
   <td colname="col2"> <p> Alla utskrivbara tecken utom blanksteg. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:nedre:]] </p> </td> 
   <td colname="col2"> <p>Ett alfabetiskt tecken med gemener. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:skriv ut:]] </p> </td> 
   <td colname="col2"> <p> Alla utskrivbara tecken inklusive blanksteg. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:punct:]] </p> </td> 
   <td colname="col2"> <p> Interpunktion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:space:]] </p> </td> 
   <td colname="col2"> <p> Tomt utrymme, t.ex. ett mellanslag, en tabb eller ett radslut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:upper:]] </p> </td> 
   <td colname="col2"> <p> Ett alfabetiskt tecken med versaler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:xdigit:]] </p> </td> 
   <td colname="col2"> <p> En hexadecimal siffra, versal eller gemen. </p> </td> 
  </tr> 
 </tbody> 
</table>

Två specialteckenklassnamn matchar det tomma utrymmet i början och slutet av ett ord. De matchar alltså inte ett faktiskt tecken. Ett ord anses vara en sekvens med alfabetiska tecken, siffror eller understreck (_).

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Klassen Character </p> </th> 
   <th colname="col2" class="entry"> <p>Betydelse </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> [[:&lt;:]] </p> </td> 
   <td colname="col2"> <p> början av ett ord </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> [[:&gt;:]] </p> </td> 
   <td colname="col2"> <p>slutet av ett ord </p> </td> 
  </tr> 
 </tbody> 
</table>
