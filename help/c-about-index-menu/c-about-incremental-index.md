---
description: Du kan använda Inkrementellt index om du vill indexera"delar" av en publicerad eller mellanlagrad webbplats, till exempel en samling sidor som ändras ofta.
solution: Target
subtopic: Incremental Index
title: Om inkrementellt index
topic-legacy: Index,Site search and merchandising
uuid: b1ee9b08-dcbe-4ffe-b0b4-d379daaac9b5
exl-id: 41943f84-23f0-434c-8eef-a9075dd5c03d
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 0%

---

# Om inkrementellt index{#about-incremental-index}

Du kan använda Inkrementellt index om du vill indexera&quot;delar&quot; av en publicerad eller mellanlagrad webbplats, till exempel en samling sidor som ändras ofta.

## Använda inkrementellt index {#concept_A7770F0552D14C47B3DDB65DB78FFFEE}

Ett inkrementellt index tar bara några sekunder att utföra och är användbart på webbplatser med stor kapacitet som kan ta många timmar att indexera helt.

När du genererar ett inkrementellt index visas statusinformation, t.ex. starttid, förfluten tid och fel under indexeringsprocessen. Information om status för det senaste indexet visas också.

Du kan när som helst stoppa eller starta om den stegvisa indexeringsprocessen.

När det nya inkrementella indexet byggs för den aktiva webbplatsen kan kunderna fortsätta att söka på webbplatsen med det senaste inkrementella indexvärdet.

## Konfigurera ett inkrementellt index för en mellanlagrad webbplats {#task_46A367B0786C4C90BFFA5D3F95FD86C0}

Du kan konfigurera vilka webbsidor som ska ingå i det inkrementella indexet genom att ange webbplatsens URL:er och URL-masker.

**Konfigurera ett inkrementellt index för en mellanlagrad webbplats**

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Configuration]** på produktmenyn.
1. På sidan **[!UICONTROL Incremental Index Configuration]** använder du de olika fälten för att ange vilka sidor du vill indexera.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Fält </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Lägg till eller uppdatera URL:er </p> </td> 
      <td colname="col2"> <p>Ange URL:er. </p> <p>Sökroboten indexerar bara de angivna dokument som har ändrats sedan du indexerade senast. </p> <p>Sökroboten följer dessutom länkar som finns i de angivna dokumenten och indexerar endast de dokument som har ändrats. </p> <p>Det här fältet får endast innehålla dokument-URL:er och inte masker som i följande exempel: </p> <p> 
        <code>
          https://www.mydomain.com/products/new.html 
        </code> </p> <p>Du kan använda följande nyckelord med URL:en: </p> <p> 
        <ul id="ul_62D1082ACBD547D092B10D72C56A3A1E"> 
          <li id="li_32C2B21DE75C4459908384CC44822F7D"> 
          <code>
            noindex 
          </code> <p>Om du inte vill indexera texten på sidan som matchar en angiven URL, men vill följa sidans länkar, lägger du till 
            <code>
              noindex 
            </code> efter URL:en som i följande exempel: </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html noindex 
            </code> </p> <p>Se till att separera 
            <code>
              noindex 
            </code> från URL:en med blanksteg; ett komma är inte en giltig avgränsare. </p> </li> 
          <li id="li_33AB62B669084BF7B976F4308715E435"> 
          <code>
            nofollow 
          </code> <p>Om du vill indexera texten på sidan som matchar den angivna URL-adressen, men inte vill följa sidans länkar, lägger du till 
            <code>
              nofollow 
            </code> efter URL:en som i följande exempel: </p> <p> 
            <code>
              https://www.mydomain.com/products/new.html nofollow 
            </code> </p> <p> Se till att separera 
            <code>
              nofollow 
            </code> från URL:en med blanksteg; ett komma är inte en giltig avgränsare. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Söka efter och uppdatera URL-masker </p> </td> 
      <td colname="col2"> <p>Ange enkla URL-masker - fullständig sökväg, partiell sökväg eller sökvägar som använder jokertecken eller reguljära uttryck. </p> <p>Sökroboten hittar alla matchande dokument och indexerar bara de dokument som har ändrats sedan du indexerade senast. </p> <p>Sökroboten följer dessutom länkar som finns i de matchande dokumenten och indexerar bara de sidor som har ändrats. Exempel: </p> <p> 
      <code>
        https://www.mydomain.com/products/household/*.html 
      </code> </p> <p>Du kan också använda reguljära uttryck som i följande exempel: </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/household/.*\.html$ 
      </code> </p> <p>Se <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguljära uttryck</a>. </p> <p>Du kan också använda nyckelorden 
      <code>
        nofollow 
      </code> och 
      <code>
        noindex 
      </code> enligt beskrivningen i <span class="uicontrol"> Lägg till eller uppdatera URL:er </span> ovan. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkludera och exkludera URL-masker </p> </td> 
      <td colname="col2"> <p>Ange enkla inkluderings- eller exkluderingsmasker för webbadresser - fullständig sökväg, partiell sökväg eller sökvägar som använder jokertecken eller reguljära uttryck. </p> <p>Sökroboten hittar och indexerar ("include") eller ignorerar ("exclude") dokument baserat på den typ av mask som har angetts. </p> <p> När du indexerar en plats följs anvisningarna i utseendeordningen. Följande lista över masker: </p> <p> 
      <code>
        include https://www.mydomain.com/products/household/lightbulbs*.html 
      </code> </p> <p> 
      <code>
        exclude https://www.mydomain.com/products/ 
      </code> </p> <p>indexerar sidorna 
      <code>
        lightbulbs1.html 
      </code> och 
      <code>
        lightbulbs2.html 
      </code>. Den indexerar dock inte några andra sidor som finns listade under produktkatalogen. </p> <p>En URL-mask som visas först har alltid företräde framför en som visas senare i listan. Om sökroboten dessutom stöter på ett dokument som matchar både en inkluderingsmask och en exkluderingsmask, har den mask som listas först företräde. </p> <p>Du kan också använda nyckelorden 
      <code>
        nofollow 
      </code> och 
      <code>
        noindex 
      </code> enligt beskrivningen i <span class="uicontrol"> Lägg till eller uppdatera URL:er </span> ovan. </p> <p>Se <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164" type="concept" format="dita" scope="local"> Om URL-masker</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkludera och exkludera datummasker </p> </td> 
      <td colname="col2"> <p>Ange enkla datummasker för inkludera eller exkludera - fullständig sökväg, partiell sökväg eller sökvägar som använder jokertecken eller reguljära uttryck. </p> <p>Sökroboten hittar och indexerar ("include") eller ignorerar ("exclude") dokument baserat på både URL och dokumentdatum. </p> <p>Du kan använda följande typer av datummasker: </p> <p> 
      <ul id="ul_8958ED54C8EF405AA259236595ED3ABA"> 
      <li id="li_0A7841767E004F088CA6FA42E99B9F32"> 
      <code>
        include-days NNN 
      </code> <p>Sökroboten indexerar alla dokument som matchar den angivna URL-masken och är NNN days eller mer gamla. </p> <p>Du kan följa URL-masken med ett eller flera av följande nyckelord: 
        <ul id="ul_22A38D5F38B344ABB02B16EB1865813B"> 
        <li id="li_B89CC37DC2A1428185E86FFCB9DDB193">nofollow </li> 
        <li id="li_C2579B3A338D4AF987C3F518806734B0">noindex </li> 
        <li id="li_0527BF7103F34B83AC3E684069B899F7">serverdatum </li> 
        </ul> </p> <p>Följande mask innehåller till exempel alla dokument i mappen /archive/support som är 0 dagar eller äldre: </p> <p> 
        <code>
          include-days 0 https://www.mydomain.com/archive/support/ 
        </code> </p> </li> 
      <li id="li_7663ABED40DD4E159F746E4F92BB6407"> 
      <code>
        include-date YYYY-MM-DD 
      </code> <p>Sökroboten indexerar alla dokument som matchar den angivna URL-masken och som är lika gamla eller äldre än datumformatet ÅÅÅ-MM-DD. </p> <p>Du kan följa URL-masken med ett eller flera av följande nyckelord: </p> <p> 
        <ul id="ul_57BF37A413BB4A4D962863DACE56F395"> 
        <li id="li_88CAB9AB583B4754A5C53478BD1108FF">nofollow </li> 
        <li id="li_999E1CD34FDE4A1B9C332B4AA8C2887D">noindex </li> 
        <li id="li_05646FACF3524D2A9E201A23770E357F"> serverdatum </li> 
        </ul> </p> <p>Följande maskexempel innehåller alla dokument i mappen /archive/ som är daterad den 25 juli 2011 eller tidigare: </p> <p> 
        <code>
          include-date 2011-07-25 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      <li id="li_172692DEDA8744B3AA492701D24C2D80"> 
      <code>
        exclude-days NNN 
      </code> <p>Inaktivera indexering av alla dokument som matchar den angivna URL-masken och som är NNN days eller mer gamla. </p> <p>Du kan också följa URL-masken med nyckelordet . 
        <code>
          server-date 
        </code>. </p> <p>I följande maskexempel utesluts alla PDF-filer som är 90 dagar gamla eller äldre från indexet: </p> <p> 
        <code>
          exclude-days 90 *.pdf 
        </code> </p> </li> 
      <li id="li_26078517744D4AECBE1351008926CBAE"> 
      <code>
        exclude-date YYYY-MM-DD 
      </code> <p>Inaktivera indexering av alla dokument som matchar den angivna URL-masken och som är lika gamla eller äldre än datumet YYY-MM-DD. </p> <p>Du kan också följa URL-masken med nyckelordet . 
        <code>
          server-date 
        </code>. </p> <p>I följande maskexempel utesluts alla dokument i mappen /archive/ som är daterad den 23 april 2004 eller tidigare: </p> <p> 
        <code>
          exclude-date 2004-04-23 https://www.mydomain.com/archive/ 
        </code> </p> </li> 
      </ul> </p> <p>Se <a href="../c-about-settings-menu/c-about-crawling-menu.md#concept_F4F1F58A646F4A86B8650EC46FDCEF66" type="concept" format="dita" scope="local"> Datummasker</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ta bort URL:er </p> </td> 
      <td colname="col2"> <p>Ange URL:er. </p> <p>Sökroboten hittar och tar bort de angivna dokumenten från sökindexet. Om en angiven sida redan finns i sökindexet tas den bort innan den lägger till eller uppdaterar andra sidor. </p> <p>Det här fältet får endast innehålla dokumentadresser, inte masker. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Söka efter och ta bort URL-masker </p> </td> 
      <td colname="col2"> <p>Ange enkla URL-masker - fullständig sökväg, partiell sökväg eller sådana som använder jokertecken eller reguljära uttryck. </p> <p>Om den angivna URL-masken matchar sidor i sökindexet tar sökroboten bort sidorna innan den lägger till eller uppdaterar andra sidor. Exempel: </p> <p> 
      <code>
        https://www.mydomain.com/products/1998/household/* 
      </code> </p> <p>Du kan också använda reguljära uttryck som i följande exempel: </p> <p> 
      <code>
        regexp ^https://www\.mydomain\.com/products/199[567]/.*$ 
      </code> </p> <p>Se <a href="../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguljära uttryck</a>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ställa in inkrementellt indexschema för en aktiv webbplats {#task_2A46BA189ECC4317A9D5C6E99A336F33}

Du kan välja frekvensen för inkrementellt index och den bastid som används för att crawla och uppdatera det inkrementella indexet.

Den tid du väljer är lokal enligt den tidszon som är konfigurerad i Kontoinställningar.

Se [Konfigurera dina kontoinställningar](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Webbservrar är ofta schemalagda för underhåll mitt i natten. Om servern är nere under en schemalagd indextid kommer indexeringsprocessen att misslyckas. Se till att du väljer en tidpunkt på dagen när webbservern är tillgänglig.

Indexschemat gäller endast ditt liveindex. du kan inte schemalägga mellanlagrade index.

**Ställa in inkrementellt indexschema för en aktiv webbplats**

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Schedule]** på produktmenyn.
1. Välj indexeringsfrekvens i timmar eller minuter i listrutan **[!UICONTROL Incremental Index Schedule]** på sidan **[!UICONTROL Incrementally Index]**.
1. Välj starttid i listrutan **[!UICONTROL Base Time]** när du vill generera om ett nytt inkrementellt index.
1. Klicka på **[!UICONTROL Save Changes]**.

## Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats {#task_9BFB6157F3884B2FAECB7E0E9CA318CB}

Du kan använda Inkrementellt index om du vill indexera&quot;delar&quot; av en publicerad eller mellanlagrad webbplats, till exempel en samling sidor som ändras ofta.

**Så här kör du ett inkrementellt index för en aktiv eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Index]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Index]**.

1. Klicka på **[!UICONTROL Incremental Index Now]**.
1. (Valfritt) Om indexeringsfel inträffar klickar du på **[!UICONTROL View Errors]** för att visa den associerade loggen.

## Visa den inkrementella indexloggen för en aktiv eller mellanlagrad webbplats {#task_E668E1F1240C476DAA1CA783DC728232}

När ett dynamiskt inkrementellt index eller ett mellanlagrat inkrementellt index är klart kan du visa tillhörande logg för att felsöka eventuella fel som inträffat.


Du kan inte exportera loggar eller spara dem. Loggen är fortfarande tillgänglig för visning tills det nya indexet inträffar.

**Så här visar du den inkrementella indexloggen för en aktiv eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Live Log]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Incremental Index]** > **[!UICONTROL Staged Log]**.

1. Gör något av följande på loggsidan, längst upp eller längst ned:

   * Använd navigeringsalternativen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** eller **[!UICONTROL Go to line]** för att gå igenom loggen.

   * Använd visningsalternativen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** eller **[!UICONTROL Show]** för att förfina det du ser.
