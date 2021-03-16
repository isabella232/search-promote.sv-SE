---
description: Med skriptbaserat index kan du skriva, uppdatera och underhålla alternativ för inkrementell indexering utan att behöva logga in. Sökroboten läser instruktioner från en textfil som finns på servern.
solution: Target
subtopic: Scripted Index
title: Om skriptindex
topic: Index,Webbplatssökning och -försäljning
uuid: 51e726ad-414b-4cbd-8a68-fefc3cf9b565
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1730'
ht-degree: 0%

---


# Om skriptat index{#about-scripted-index}

Med skriptbaserat index kan du skriva, uppdatera och underhålla alternativ för inkrementell indexering utan att behöva logga in. Sökroboten läser instruktioner från en textfil som finns på servern.

## Använda skriptindex {#concept_34F58D551BC04BFB8ADC294B9DA9199D}

## Konfigurera skriptad inkrementell indexering {#section_161D254065E143F3A39F3FC09C400090}

Om du vill använda skriptbaserat index använder du sidan Konfiguration av skriptad inkrementellt index för att ange URL:en till en skriptfil (en vanlig textfil) som finns på servern. Exempel, `https://www.mysite.com/indexlist.txt`. När webbplatsen ändras kan du lägga till kommandoblock i textfilen antingen manuellt eller automatiskt (med ett skript som utlöses av att information kommer från en nyhetsfeed, en börskursfil eller annan ändrad fil).

När det skriptade stegvisa indexvärdet börjar läser sökroboten textfilen och kör de nya kommandona som finns i filen. Som standard bearbetar sökroboten bara de nya kommandona, som bestäms av fildatumet. Om du inte markerar **[!UICONTROL Clear Date]** när du konfigurerar skriptbaserat index kommer sökroboten ihåg datumspecificeraren för det senast bearbetade blocket.

## Om skriptfilen {#section_B312E40539F44C6583B4F9637D428E19}

Skriptfilen som du anger i URL:en är en oformaterad textfil som finns på servern. Du kan använda radmatningar, radmatningar eller båda för radslutssekvensen. En tom rad innehåller noll eller flera blankstegstecken följt av en radslutssekvens. Alla kommandon är inte skiftlägeskänsliga.

Textfilen ordnas i block som beskriver informationen som används av sökroboten när ett skriptbaserat stegvis indexvärde utförs.

Blocken ordnas efter datum, med de äldsta blocken överst i textfilen och de senaste blocken längst ned. Varje block börjar med ett enda raddatatecken och ett datumspecificeringskommando, och slutar med en tom avgränsare, som i följande blockexempel (däremellan finns flera kommandon):

En inledande nolla krävs för alla ordningstal som är lägre än den 10:e när formatet HTTP 1.1 används. Den 6 november är till exempel 06 nov, inte 6 nov.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Kommando </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>date-command </p> </td> 
   <td colname="col2"> <p>Den första raden i varje block börjar med ett av två datumkommandon: </p> <p> 
     <ul id="ul_9C1B229B7F1846C490B853FC34989E77"> 
      <li id="li_31FEF1A7163842BDBB0ABE779D07045A"> <span class="codeph"> datum  </span> <p>Använd kommandot "date" för att ange att datumspecificeraren ska bestå av en dag, ett datum, en tid och en tidszon. </p> </li> 
      <li id="li_0918D5B090014C1A852CB80BB7C2867C"> <span class="codeph"> sekunder  </span> <p>Använd <span class="codeph"> sekunder </span> för att ange att datumspecificeraren ska bestå av en tid i epoksekunder (till exempel 78411777). När du använder <span class="codeph"> sekunder </span> måste du se till att antalet sekunder ökar mellan blocken. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>datumspecificerare </p> </td> 
   <td colname="col2"> <p>Kommandot <span class="codeph"> date-specify </span> registrerar vanligtvis antingen ordningstalsdatumet och -tiden (date-kommando) eller tiden i epoksekunder (seconds-kommando) som blockinformationen lades till i filen. Exempel: </p> <p> <code> date&nbsp;Sun,&nbsp;06&nbsp;Nov&nbsp;1994&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.1&nbsp;style) 
      date&nbsp;Sunday,&nbsp;06-Nov-94&nbsp;08:49:37&nbsp;GMT&nbsp;(HTTP&nbsp;1.0&nbsp;style) 
      date&nbsp;Sun&nbsp;Nov&nbsp;6&nbsp;08:49:37&nbsp;1994&nbsp;(Unix&nbsp;asctime()&nbsp;date&nbsp;style) 
      seconds&nbsp;784111777&nbsp;(Unix&nbsp;epoch-seconds&nbsp;style) </code> </p> <p>En inledande nolla krävs för alla ordningstal som är lägre än den 10:e när formatet HTTP 1.1 används. Den 6 november är till exempel 06 nov, inte 6 nov. </p> <p>Sökroboten "kommer ihåg" datumspecificeraren för det senast bearbetade blocket och indexerar bara information som den anser vara "nyare". (Det spelar ingen roll för sökroboten i realtid. I stället är tiden i förhållande till andra tidigare bearbetade tider det som är viktigt.) </p> <p>När sökroboten läser ett block med datumspecificeraren 10:00, läser den till exempel inte några block som spelar in före 10:00, oavsett när indexåtgärden körs. I ett värsta fall kanske du av misstag anger året "2040" i stället för "2004" i datumspecifikationen. I så fall indexerar sökroboten blocket 2040 under nästa indexeringsåtgärd och vägrar sedan att läsa andra informationsblock (såvida inte ett efter 2040). Om detta skulle inträffa tar du bort alla tidigare bearbetade block från textfilen, klickar på <span class="uicontrol"> Radera datum </span> och aktiverar det sedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>kommentarsrad </p> </td> 
   <td colname="col2"> <p>Börja kommentera rader med tecknet "#". </p> <p>Varje kommentarsrad måste vara en egen rad. du kan inte skriva radslutskommentarer. </p> <p>En kommentarsrad betraktas inte som en tom rad. Den kan också visas var som helst i ett block, till och med före ett datum- eller sekundkommando som i följande exempel: </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;#Added&nbsp;by&nbsp;Cathy&nbsp;Read&nbsp;after&nbsp;the&nbsp;Y2K&nbsp;seminar 
      &nbsp;&nbsp;&nbsp;&nbsp;date&nbsp;Mon,&nbsp;29&nbsp;Dec&nbsp;1999&nbsp;09:32:20&nbsp;GMT&nbsp; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>action-command </p> </td> 
   <td colname="col2"> <p>Varje textblock kan innehålla så många åtgärdskommandon du vill. Följande åtgärdskommandoalternativ motsvarar dem för stegvis standardindexering: </p> <p> 
     <ul id="ul_8E1435350A0F416BB8F7826CD3886E74"> 
      <li id="li_22181666628C48A28A6A0BA1F7CA8E77"> 
       <code>
         add 
       </code> <p>Använd med URL. Sökroboten indexerar bara de angivna URL:er som har ändrats sedan den senaste indexeringsåtgärden. Sökroboten följer dessutom länkar som finns i angivna dokument och indexerar endast de dokument som har ändrats. </p> <p>Du kan följa URL:en med 
        <code>
          nofollow 
        </code> eller 
        <code>
          noindex 
        </code> nyckelord som i följande exempel: </p> <p> <code> add&amp;nbsp;https://www.mydomain.com/&amp;nbsp;noindex </code> </p> </li> 
      <li id="li_8E47BF07DB24417083883F5BF40D6B9E"> 
       <code>
         update 
       </code> <p>Använd med URL-mask. Sökroboten hittar och uppdaterar alla dokument som matchar den angivna URL-masken. </p> <p>Du kan följa URL:en med 
        <code>
          nofollow 
        </code> eller 
        <code>
          noindex 
        </code> nyckelord som i följande exempel: </p> <p> <code> update&amp;nbsp;https://www.mydomain.com/products/ </code> </p> </li> 
      <li id="li_B3EC8B1670D54F66A1D8411A694EF7E4"> 
       <code>
         include 
       </code> eller  
       <code>
         exclude 
       </code> <p>Använd med URL-mask. Sökroboten hittar och indexerar ("include") eller ignorerar ("exclude") dokument baserat på den angivna masktypen. </p> <p>Exempel: </p> <p> <code> include&amp;nbsp;https://www.mydomain.com/products/household/lightbulbs*.html </code> </p> <p>eller </p> <p> <code> exclude&amp;nbsp;https://www.mydomain.com/archive/ </code> </p> </li> 
      <li id="li_050B54B735F0475E93806455FA6DC6A5"> 
       <code>
         include-date 
       </code> eller  
       <code>
         exclude-date 
       </code> <p>Använd med URL-mask. Sökroboten hittar och indexerar ("include") eller ignorerar ("exclude") dokument baserat på både URL-adressen och dokumentdatumet. Följande typer av masker är tillgängliga: </p> <p> 
        <ul id="ul_23A15CB492214B86BE84D8E6EA1820AE"> 
         <li id="li_0C7051AC3B5A4C57A3E477F7B6246611"> 
          <code>
            include-days NNN 
          </code> <p>Sökroboten indexerar alla dokument som matchar den angivna URL-masken och är NNN days eller mer gamla. </p> <p>Du kan följa URL-masken med nyckelorden 
           <code>
             nofollow 
           </code>, 
           <code>
             noindex 
           </code>, och/eller 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_983A10E2ED5D434EA9031F32143F4EF4"> 
          <code>
            include-date YYYY-MM-DD 
          </code> <p> Sökroboten indexerar alla dokument som matchar den angivna URL-masken och som är lika gamla eller äldre än datumet YYY-MM-DD, där "YYY" är det fyrsiffriga året, "MM" är den en- eller tvåsiffriga månaden (1-12) och "DD" är den en- eller tvåsiffriga dagen (1-31). </p> <p>Du kan följa URL-masken med nyckelorden 
           <code>
             nofollow 
           </code>, 
           <code>
             noindex 
           </code>, och/eller 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_733CE1B748024CECA7FBE00D7BC7B88A"> 
          <code>
            exclude-days NNN 
          </code> <p> Inaktiverar indexering av alla dokument som matchar den angivna URL-masken och som är NNN days eller mer gamla. </p> <p>Du kan följa URL-masken med nyckelordet 
           <code>
             server-date 
           </code>. </p> </li> 
         <li id="li_90056A0B96CC4DA3854711860A15CE89"> 
          <code>
            exclude-date YYYY-MM-DD 
          </code> <p>Inaktiverar indexering av alla dokument som matchar den angivna URL-masken och som är lika gamla eller äldre än datumet YYY-MM-DD. </p> <p>Du kan följa URL-masken med nyckelordet 
           <code>
             server-date 
           </code>. </p> </li> 
        </ul> </p> </li> 
      <li id="li_AA78F22B60FE4535BE73BA87A8992C08"> 
       <code>
         delete 
       </code> <p>Ange URL:er. Sökroboten tar bort dokument från indexet som identifieras av URL:en. </p> </li> 
      <li id="li_9C63061568AA4D57A4FEBCF6DB9194EC"> 
       <code>
         deletemask 
       </code> <p>Sökroboten tar bort dokument från indexet som matchar den angivna URL-masken. </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Se även [Om URL-masker](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

## Exempel på skriptfil {#section_9F580F20E7214751B157A28B392BD64E}

I följande skriptfilexempel bearbetar sökroboten blocken under förutsättning att datumspecificerarna efterdaterar datumspecificeraren för det senast bearbetade blocket. Om så är fallet utförs följande indexeringsåtgärder:

* Tar bort `y2k-problems.html` från indexet.
* Lägger till `no-y2k-problems.html` i sökindexet och följer inte någon av länkarna för `no-y2k-problems.html`.

* Vid crawlning utelämnar du URL:er som matchar `housewares.htm` och `lightfixtures.htm`l från sökindexet.

* Inkludera alla andra kataloger och dokument under `www.mydomain.com`.
* Uppdatera alla dokument i katalogerna `products` och `information`, crawlar och indexerar alla underordnade länkar som har ändrats sedan den senaste indexeringsåtgärden.

* Undanta URL:er i avsnittet `archive` på webbplatsen om de är daterade den 1 januari 1999 eller tidigare när de crawlas.
* Uteslut URL:er som matchar `housewares.html` och `lightfixtures.html` från sökindexet.

* Indexera filer i katalogen `help`, men crawla eller indexera inga länkar från de filerna.
* Crawla och indexera alla andra filer som påträffats för `www.mydomain.com`.

```
# Start of file. 
# Added by John Smith 
date Sat, 01 Jan 2004 16:05:53 PST 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/ 
delete https://www.mydomain.com/y2k-problems.html 
add https://www.mydomain.com/no-y2k-problems.html nofollow 
 
date Sun, 02 Jan 2004 20:19:08 PST 
# Added by the wire service updater 
exclude-date 1999-01-01 https://www.mydomain.com/archive server-date 
exclude https://www.mydomain.com/housewares.html 
exclude https://www.mydomain.com/lightfixtures.html 
include https://www.mydomain.com/help/ nofollow 
include https://www.mydomain.com/ 
# no add files, just update existing files 
# update all files in the "products" directory 
update https://www.mydomain.com/products/ 
# update all files in the "information" directory 
update regexp ^https://www\.mydomain\.com/information/.*$ 
# End of file.
```

## Konfigurera ett skriptat inkrementellt index {#task_05AE040FE75E40FFAA5E10B6B6D4D255}

Du kan ange ett skript som du har skapat och som skriver, uppdaterar och underhåller ett inkrementellt index, utan att du behöver logga in. Sökroboten läser instruktioner från textfilen som finns på servern för att utföra det stegvisa indexet.

**Konfigurera ett skriptbaserat inkrementellt index**

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Configuration]** på produktmenyn.
1. På sidan **[!UICONTROL Scripted Incremental Index Configuration]** anger du URL:en till textfilsskriptet som finns på servern i **[!UICONTROL Script File URL]**.

   Se [Om skriptat index](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D).
1. (Valfritt) Markera **[!UICONTROL Clear Date]** om du inte vill att sökroboten ska &quot;komma ihåg&quot; datumspecificeraren för det senast bearbetade blocket.

   Som standard behandlar sökroboten endast nya kommandoblock som finns i textfilen, vilket avgörs av filens datum. Om du inte vill använda standardinställningen markerar du **[!UICONTROL Clear Date]**.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ställa in skriptbaserat inkrementellt indexschema för en aktiv webbplats {#task_B3A87AC4AC784507859C23B9062BA11C}

Du kan schemalägga att skriptad stegvis indexering ska ske med regelbundna intervall under dagen.

Den bastid du väljer är lokal enligt den tidszon som är konfigurerad i Kontoinställningar.

Se [Konfigurera dina kontoinställningar](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Webbservrar är ofta schemalagda för underhåll mitt i natten. Om servern är nere under en schemalagd indextid kommer indexeringsprocessen att misslyckas. Se till att du väljer en tidpunkt på dagen när webbservern är tillgänglig.

Indexschemat gäller endast ditt liveindex. du kan inte schemalägga mellanlagrade inkrementella index.

**Ställa in skriptbaserat inkrementellt indexschema för en aktiv webbplats**

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Schedule]** på produktmenyn.
1. På sidan **[!UICONTROL Scripted Incremental Index Schedule]** väljer du i listrutan **[!UICONTROL Read the Scripted Incrementally Indexing File]** den frekvens som du vill att den skriptade inkrementella indextextfilen ska köras, i timmar eller minuter.
1. I listrutan **[!UICONTROL Base Time]** väljer du starttid när du vill generera om ett nytt skriptat inkrementellt index.
1. Klicka på **[!UICONTROL Save Changes]**.

## Köra ett skriptbaserat inkrementellt index för en aktiv eller mellanlagrad webbplats {#task_6E6FC76EE1E84A5FADB3B67AD7B1DACB}

Du kan använda Stegvis skriptad inkrementell indexposition om du vill indexera&quot;delar&quot; av din aktiva eller mellanlagrade webbplats, till exempel en samling sidor som du ofta ändrar, utan att behöva logga in.

Om du vill använda den här funktionen måste du konfigurera en skriptad inkrementell indextextfil.

Se [Konfigurera ett skriptat inkrementellt index](../c-about-index-menu/c-about-scripted-index.md#task_05AE040FE75E40FFAA5E10B6B6D4D255).

**Så här kör du ett skriptbaserat inkrementellt index för en aktiv eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Index]**.
   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Index]**.

1. Klicka på **[!UICONTROL Scripted Index Now]**.
1. (Valfritt) Om indexeringsfel inträffar klickar du på **[!UICONTROL View Errors]** för att visa den associerade loggen.

## Visa skriptad inkrementell indexlogg för en aktiv eller mellanlagrad webbplats {#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7}

När ett fullständigt skriptindex (live) eller ett skriptbaserat index (staged full) är klart kan du visa tillhörande logg för att felsöka eventuella fel som inträffat.

Du kan inte exportera loggar eller spara dem. Loggen är dock fortfarande tillgänglig för visning tills det nya indexet inträffar.

**Så här visar du den inkrementella indexloggen för en aktiv eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Live Log]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Scripted Index]** > **[!UICONTROL Staged Log]**.

1. Gör något av följande på loggsidan, längst upp eller längst ned:

   * Använd navigeringsalternativen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** eller **[!UICONTROL Go to line]** för att gå igenom loggen.

   * Använd visningsalternativen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** eller **[!UICONTROL Show]** för att förfina det du ser.

