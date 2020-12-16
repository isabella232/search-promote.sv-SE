---
description: Du kan använda regler för eftersökning för att undersöka resultatet av en sökning och avgöra hur sökningen påverkar det visade innehållet.
seo-description: Du kan använda regler för eftersökning för att undersöka resultatet av en sökning och avgöra hur sökningen påverkar det visade innehållet.
seo-title: Om regler för eftersökning
solution: Target
title: Om regler för eftersökning
topic: Rules,Site search and merchandising
uuid: 312d1e4a-f5b6-4629-8645-17e6f6c09fc4
translation-type: tm+mt
source-git-commit: d07cdc2c88f93eed4cecb0ee8818f7fdea06ee9d
workflow-type: tm+mt
source-wordcount: '2121'
ht-degree: 0%

---


# Om regler för eftersökning{#about-post-search-rules}

Du kan använda regler för eftersökning för att undersöka resultatet av en sökning och avgöra hur sökningen påverkar det visade innehållet.

## Använda eftersökningsregler {#concept_AF6ADFCC0ADF4A788003964939917FDE}

Om en sökning inte har några resultat kan en regel efter sökning göra en sökning efter ett liknande objekt. Eller så kan den visa en webbsida som rekommenderar andra objekt till kunder som söker efter det objekt som inte hittades.

Varje regel består av två huvudelement: regelns åtgärder och dess valfria villkor. Du kan ange ett obegränsat antal regler och villkor. Ordningen på dessa regler är viktig eftersom regeluppsättningen upprepas regel för regel. När en regel har samma villkor utförs alla associerade åtgärder.

Du kan förfina uppsättningen sökresultat för högst tre sökomgångar. Därefter används det som för närvarande är tillgängligt. Denna gräns förhindrar oändliga slingor och säkerställer att kunden får ett effektivt svar. Ju fler gånger du gör om en sökning desto längre tid tar det att returnera sökresultaten. Om ingen av de matchande reglerna ändrar en av sökningarna för den presentationsmall som används för tillfället eller byter mall, betraktas uppsättningen sökresultat som slutförda och eftersökningen avslutas.

Bearbetning efter sökning bygger på de tidigare bearbetningsmodulerna Frågerengöring och Försökning. Därför är alla anpassade variabler som anges i dessa moduler tillgängliga för användning i bearbetningsreglerna för eftersökning. Försöksbearbetningen har på samma sätt instansierat alla mallar där varje namngiven sökning som är kopplad till presentationsmallen har en egen lokal kopia av CGI-parametrarna. Du kan i sin tur anpassa varje sökning för sig.

Se [Om regler för frågerensning](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C).

Se [Om regler för försökning](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

## Om villkor för regel efter sökning {#section_C43EB77CC0AC43B8B9D38569264BF1B5}

Villkoren är valfria. Om du anger att åtgärder ska anges för varje fråga utförs alltid åtgärderna. Du kan basera villkor på CGI-frågeparametrar, cookies, sökresultat eller anpassade variabler som en tidigare regel har angett. Eller så kan du basera det på ett systemvillkor som t.ex. vad den markerade mallen är eller om det är den sista sökningen. När du skapar ett villkor för resultatet av en sökning eller en CGI-parameter anger du mallen och namnet på sökningen.

## Regelåtgärder efter sökning {#section_0E15FE683A894ECAAA386267EEC7F7C5}

Alla åtgärder i en regel efter sökning som har matchande villkor utförs. Åtgärderna består vanligtvis av en åtgärd, de data som ska utföra åtgärden på och det värde som ska användas. Den enklaste åtgärden är att växla vilken presentationsmall som ska användas baserat på villkoren för regeln efter sökning. Du kan använda mer avancerade åtgärder för att ändra parametrarna för en sökning som leder till att sökningen görs om. När du utför en åtgärd på en malls sökparameter anger du en presentationsmall och söker.

## Allmänna regler {#section_AEE923988CC748FF9DEF2233FBF333B5}

När du utför åtgärder på en malls sökparameter finns det två specialvärden, *target och *primär för presentationsmallen respektive den namngivna sökningen. Använd dessa värden för att skapa regler som baseras på den aktuella målmallens primära sökning. Med dessa konstruktioner kan du skapa allmänna regler där du inte behöver oroa dig för vad den aktuella målmallen eller den primära sökningen kallas. Om den här skicka är den första genom eftersökningsbearbetningen är målmallen den försökningsbearbetning som den ställs in på.

## Omdirigerar {#section_E5669A2F13C240F2968E31C75591CD6A}

Med Direktträffar och omdirigeringar i Frågerengöring kan du omdirigera till en URL utifrån de inkommande söktermerna. Omdirigeringar i regler för eftersökning utökar den här idén, förutom att du kan kontrollera hur många resultat sökningen gav innan du bestämmer om du vill att en omdirigering ska ske. Med regler för eftersökning kan du omdirigera till en URL där du kan ersätta anpassade variabler eller frågeparametrar. Du kan också omdirigera till ett fält i det första resultatet. När du omdirigerar till ett resultatfält definierar du fältet i transportmallen och måste innehålla en giltig, explicit URL, annars hoppas omdirigeringen över.

När du använder omdirigeringsfunktionen i regler för eftersökning kan du identifiera när en sökning returnerar ett enda resultat. I stället för att returnera ett sådant resultat kan du dirigera om till webbsidan som är kopplad till resultatet.

Se exemplet på omdirigering nedan för ett exempel på hur du använder omdirigeringar med regler för eftersökning.

## Sista regeln {#section_FC1E0050C9324278B171038E98F6C335}

När villkoren är uppfyllda för en regel som har alternativet **[!UICONTROL Last Rule]** angivet utför bearbetningsmodulen efter sökningen inga ytterligare regler efter åtgärden för matchningsregeln. Den här situationen är användbar när du har angett åtgärder som gör att en senare regel matchar, men du vill att bearbetningen ska avbrytas. Och för den senare regeln kanske matchar efter nästa sökomgång.

## Exempel {#section_DDB98383690941F9B44AD00FBA55BB56}

I följande exempel antar du att du har två presentationsmallar. En mall används för att visa många sökresultat och den andra mallen används för att visa ett enda resultat och en ytterligare sökning efter tillbehör som är relaterade till huvudsökningen. Du vill identifiera när du har ett enda resultat och växla till den andra presentationsmallen. För att utföra den här uppgiften kan du använda följande regler:

```
On condition: 
  targeted template is default 
  targeted template primary results equal 1 
  not last search 
Perform the following actions: 
  Set targeted template to product_spotlight
```

MegaElectronic är en stor elektronikbutik. Efter att ha analyserat sökdata får MegaElectronic veta att många av deras kunder gör en produktsökning med hjälp av en produkts artikelnummer. I sådana fall vill MegaElectronic dirigera om till webbsidan som är kopplad till produkten, om kunden sökte efter den direkt och bara en produkt hittades.

För att uppnå detta kan du använda en regel med tre villkor. Det första villkoret kontrollerar att den returnerade sökningen bara har ett resultat. Det andra villkoret säkerställer att frågetermen matchar MegaElektronis artikelnummerformat för de resultat som de vill ska orsaka omdirigeringen. Det tredje villkoret säkerställer att kunden inte använde några faktorer för att gå ned till ett resultat, eftersom artikelnumret kan vara ett deltal och returnera mer än ett resultat. Åtgärden dirigeras om till ett fält i resultatet.

```
On condition: 
  targeted template's primary results equal 1 
  query q matches regular expression ^\D\D\D-\d+ 
  no facet selected ^\D\D\D-\d+ 
Perform the following actions: 
  redirect to result field "loc" in template *targeted for search *primary
```

## Bästa praxis {#section_1BF7DE1BD5664B3BAEC26AA829FDB0BA}

* Alla uppsättningar regler som utlöser en ny sökomgång bör alltid ha en villkorssats som kontrollerar att detta inte är den sista genomgången i modulen. Om du redan har utfört maximalt antal sökningar kan du inte göra om dem.
* Om du befinner dig på den sista omgången i modulen och resultatet fortfarande är dåligt kan du växla till mallen&quot;inga resultat&quot;.
* Du bör basera ändringen av en presentationsmall på resultatet av en sökning som kan ha andra parametrar. Om du vill välja en mall som bara är baserad på den inkommande frågan, är en regel för försökning mer effektiv.
* Frågans datautvinning görs i modulen Frågerensning. Du kan referera till anpassade variabler i eftersökningen.
* När du omdirigerar ska du alltid kontrollera att kunden inte har valt några facets. Orsaken till detta är att det är obekvämt när en kund tränar in i en fasett och plötsligt tas bort från sökresultaten. Kunden kanske vill avmarkera ansiktet när han/hon ser att resultatet inte är som han/hon vill ha det.

## Lägga till en ny eftersökningsregel {#task_52F6F9AAD65B45B5ACA1FF245DFFADD9}

Du kan använda [!DNL Post-Search Rules] för att välja vilken presentationsmall som ska användas för att visa sökresultaten baserat på den inkommande frågan.

**Lägga till en ny regel för eftersökning**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Rule]** på sidan [!DNL Post-Search Rules].
1. I fältet [!DNL Name] skriver du namnet på den nya frågerengöringsregeln.
1. Använd listrutorna och textfälten på sidan [!DNL Add Post-Search Rule] för att bygga ut frågan.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Cookie </p> </td> 
      <td colname="col2"> <p>En HTTP-cookie. Cookie-namn och värden måste vara Uniform Resource Identifier-kodade. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Anpassad variabel </p> </td> 
      <td colname="col2"> <p>En användardefinierad variabel. Du kan lägga till, ta bort eller ange ett obegränsat antal anpassade variabler. </p> <p>Du kan referera till anpassade variabler som du har definierat i Frågerensning och i regelmodulerna Pre-Search, i Regler för postsökning. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Systemvariabel </p> </td> 
      <td colname="col2"> <p>Skrivskyddade variabler som angetts av det interna systemet som du kan kontrollera. Följande systemvariabler stöds: </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> värdnamn  </span> <p>Namnet på servervärden. </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri  </span> <p>Begärd Uniform Resource Identifier utan frågesträngen. </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>Hela frågesträngen. </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> miljö  </span> <p>"Stage" eller "live" beroende på om den inkommande frågan skickades till din staged-miljö eller din livemiljö. </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> hänvisare  </span> <p>Uniform Resource Locator som kunden kom ifrån. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Systemvariabel </p> </td> 
      <td colname="col2"> <p>Skrivskyddade variabler som du kan använda i villkor för att fastställa det aktuella läget. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mallens sökfaktor </p> </td> 
      <td colname="col2"> <p>En aspekt som är lokal för en namngiven sökning som är kopplad till en presentationsmall. En faktor är i stort sett särskilda CGI-parametrar som används för att ange vilket värde inom en aspekt som kunden har valt. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mallens sökparameter </p> </td> 
      <td colname="col2"> <p>En CGI-parameter som är lokal till en namngiven sökning som är kopplad till en presentationsmall. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mallens serverdelsparameter </p> </td> 
      <td colname="col2"> <p>Inkommande frågeparametrar översätts till slut till serverdelsparametrar som används för att utföra sökningen. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-parametrar för backend-sökning </a>. </p> <p>Backend-parametrar visas inte i navigeringselement. Det innebär att du kan dölja eventuella ytterligare parametrar som du vill tillämpa på en sökning från dina kunder. </p> <p>Parametern är lokal för en viss sökning i en presentationsmall. Åtgärder på backend-parametrar är sena. alltså används de precis innan sökningen skickas. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Målmall </p> </td> 
      <td colname="col2"> <p>En särskild instans av en systemdefinierad anpassad variabel som inte kan tas bort. Den här variabeln innehåller den aktuella målpresentationsmallen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rankning </p> </td> 
      <td colname="col2"> <p>Här kan du ange vilken rankningsregel som ska användas i sökningen. Det här alternativet visas bara när du har definierat rankningsfält och rankningsregler. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sista regeln </p> </td> 
      <td colname="col2"> <p>När det här alternativet är markerat utför bearbetningsmodulen inte några ytterligare regler efter matchningsregelns åtgärd. Den här åtgärden är användbar när du har angett åtgärder som gör att en senare regel matchar, men du inte vill att den senare regeln ska köras. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Gör uppehåll </p> </td> 
      <td colname="col2"> <p>Stänger av regelns körning men tar inte bort regeln. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Add]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en regel {#task_ECB00334C0A74C87AF857DB3EB372119} för eftersökning

Du kan redigera befintliga regler för eftersökning som du har lagt till på sidan [!DNL Post-Search Rules].

**Redigera en regel för eftersökning**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** på produktmenyn.
1. På sidan [!DNL Post-Search Rules], under kolumnen **[!UICONTROL Actions]** i tabellen, klickar du på **[!UICONTROL Edit]** för den associerade regel som du vill redigera.
1. Använd listrutorna och textfälten på sidan [!DNL Edit Post-Search Rule] för att bygga ut frågan.

   Se tabellen med alternativ under [Lägga till en ny regel för eftersökning](../c-about-rules-menu/c-about-post-search-rules.md#task_52F6F9AAD65B45B5ACA1FF245DFFADD9).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en regel {#task_0F4653AB20D54B769A4FA8D1491AB4CF} för eftersökning

Du kan ta bort regler för eftersökning som du inte längre behöver eller använder.

När du tar bort en regel justeras ordningen som återstående regler körs automatiskt för att ta hänsyn till borttagningen.

**Ta bort en regel för eftersökning**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]** på produktmenyn.
1. På sidan [!DNL Post-Search Rules], under kolumnen **[!UICONTROL Actions]** i tabellen, klickar du på **[!UICONTROL Delete]** för den associerade regel som du vill ta bort.
1. Klicka på **[!UICONTROL OK]** i dialogrutan [!DNL Confirmation].
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ändra ordningen som regler för eftersökning körs {#task_40542FCD32234BBF881A81BF5477F78F}

Du kan ändra ordningen på reglerna för eftersökning om du vill ändra i vilken ordning de körs på presentationsmallar.

Regler för eftersökning körs i den ordning de definierats. Ju högre ordningsnummer en regel har, desto senare körs den i processen, och tidigare regler trumpetas. Du ändrar ordning på reglerna genom att ange ett nytt nummer i kolumnen Ordning i tabellen på sidan [!DNL Post-Search Rules]. Du kan också använda dra-och-släpp-regler för att ändra deras körningsordning.

**Ändra ordningen som regler för eftersökning körs i**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Post-Search Rules]** på produktmenyn.
1. Gör något av följande på sidan [!DNL Post-Search Rules]:

   * Klicka på kolumnrubriken **[!UICONTROL Order]** om du vill sortera reglerna i stigande eller fallande ordning.
   * I kolumnen [!DNL Order] skriver du ordningsnumret som du vill att regeln ska köras i textfältet till vänster om namnet på en regel för försökning.
   * Dra och släpp en tabellrad till den position där du vill att linjen ska köras. Alla ordernummer uppdateras för att återspegla den nya ordningen som reglerna körs i.

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
