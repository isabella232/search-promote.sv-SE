---
description: Analysera och ändra den inkommande frågan med hjälp av Regler för frågerensning.
solution: Target
title: Om renderingsregler för frågor
topic: Regler,Webbplatssökning och -försäljning
uuid: 683af81f-f7c0-45f8-9212-e5e7cb82ccca
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 0%

---


# Om regler för frågerensning{#about-query-cleaning-rules}

Analysera och ändra den inkommande frågan med hjälp av Regler för frågerensning.

## Använda frågerensningsregler {#concept_17F3CDDC3C8A4128AF092A82B777B86C}

Den här funktionen används ofta när du vill ändra webbplatssöknings-/försäljningsbeteendet. Du kan t.ex. ändra en tom sökning till ett populärt nyckelord i stället för till en &quot;*&quot;-sökning och på så sätt marknadsföra en populär produkt. Du kan också använda frågerengöringsregler för att utföra en direkt träff, där du omdirigerar till en URL. Detta kan vara särskilt användbart när du upptäcker att någon söker efter en produkt-SKU och du vill hoppa över sökningen och dirigera om till den produktens sida. Frågerengöring kan även användas för att ta bort frågan och ange anpassade variabler som kan användas i senare bearbetningsflödessteg. Regler för frågerensning körs i sekvens för varje fråga. Om du vill ändra ordningen på reglerna kan du dra och släppa. Den faktiska ordningen ändras inte förrän du sparar den.

Regler för frågerensning i en frågerensningsmodul granskas för att avgöra om någon av frågeparametrarna måste ändras eller om några anpassade variabler måste anges. Varje frågerensregel består av två huvudelement: regelns åtgärder och valfria villkor. Ett obegränsat antal regler och villkor kan anges. Ordningen på dessa regler är viktig eftersom sökningar/marknadsföring på webbplatsen sker genom regeluppsättningsregeln per regel. När en regel har samma villkor utförs alla associerade åtgärder.

När frågerensningen är klar används de resulterande CGI-parametrarna framåt. Alla anpassade variabler som har angetts är tillgängliga för senare steg i bearbetningsflödet. Som standard tar systemet automatiskt bort inledande och avslutande blanksteg från frågetermen.

## Om villkor för frågerensning {#section_BF6F25F94FED4DDEA8600D921EA43A66}

Villkoren är valfria. Om du bestämmer dig för att åtgärder ska anges för varje fråga utförs alltid åtgärderna. Villkoren kan baseras på CGI-frågeparametrar, befintliga cookies eller anpassade variabler som en tidigare regel har angett. Det anses vara&quot;bästa metoden&quot; att den första frågerengöringsregeln körs för varje fråga, där den definierar och initierar alla anpassade variabler som du tänker använda.

## Om åtgärder för att rensa frågor {#section_78F74A9B48DE484191CDA95F5B4E7154}

Alla åtgärder i en frågerensningsregel som har matchande villkor utförs. Åtgärderna består vanligtvis av en åtgärd, de data som åtgärden ska utföras på och det värde som ska användas.

Se tabellen med alternativ i [Lägga till en frågerengöringsregel](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54).

## Om omdirigeringar {#section_597481E6194440C0A7B9E6FC901A81C0}

Med gränssnittet Direktträffar kan du definiera en uppsättning omdirigeringar baserat på den inkommande frågetermen. Omdirigeringar i Frågerengöring utökar den här idén. Omdirigeringar ger dig emellertid en bättre detaljrikedom när en omdirigering sker via att du anger villkor och låter dig omdirigera till en dynamisk URL i stället för en statisk URL. När du väljer omdirigeringsåtgärden uppdateras raden med en textruta där du anger den URL som du vill omdirigera till. I URL-adressen kan du ange variabler eller parametrar som du vill ersätta genom att omsluta dem med dubbla klammerparenteser. Egna variabler har högre prioritet än CGI-parametrar i ersättningen.

## Exempel {#section_DB5047CC38FB4A57B15CAAF9848073E3}

Anta att du har en klädbutik med en webbplats. Om användaren klickar på Sök utan sökord, vill du returnera en sökning mot jeans eftersom det är det du är internationellt känd för. Du vill också analysera frågetermen för ett kön så att du kan skapa en regel för förhandssökning senare, baserat på den anpassade variabeln som använder olika presentationsmallar för varje kön.

```
On condition: 
  query q equal 
Perform the following actions: 
  Set query parameter q to value jeans 
 
On condition: 
  Query q matches regular expression wom[e|a]n[s]|girl[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value female 
 
On condition: 
  Query q matches regular expression men[s]|boy[s] 
Perform the following actions: 
  Add custom variable gender 
  Set custom variable gender to value male
```

MegaElectronic är en stor elektronikbutik. Från analys av sökdata har MegaElectronic lagt märke till att många av deras kunniga kunder ofta söker efter en produkt med hjälp av produktens SKU, i stället för att returnera ett sökresultat för den enskilda produkten, skulle MegaElectronic vilja dirigera om till den webbsida som hör till denna SKU.

```
On condition: 
  query q matches regular expression ^\D\D\D-\d\d\d\d$ 
Perform the following actions: 
  redirect to https://www.megaelectronic.com/?sku={{q}}
```

## Lägger till en frågetorensningsregel {#task_47F43988D3D9485F8AE1DFDA7E00BF54}

Du kan definiera regler som rensar eller redigerar den inkommande sökfrågan från en kund.

Du kan bara välja mallar som finns. Om du inte har några mallar måste du först definiera dem.

Se [Mallar](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**Lägga till en frågetorensningsregel**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Rule]** på sidan [!DNL Query Cleaning Rules].
1. I fältet [!DNL Name] skriver du namnet på den nya frågerengöringsregeln.
1. Använd listrutorna och textfälten på sidan [!DNL Add Query Cleaning Rule] för att bygga ut frågan.

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
      <td colname="col2"> <p>En HTTP-cookie. Du kan definiera villkor baserat på cookies som är kopplade till din domän. Du kan också ange en cookie som skrivs med utgående sökresultat. Cookies-namn och -värden måste vara Uniform Resource Identifier-kodade. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Anpassad variabel </p> </td> 
      <td colname="col2"> <p>En användardefinierad variabel. Lägg till, ta bort eller ange ett obegränsat antal användardefinierade variabler. Du kan referera till valfria användardefinierade variabler här i reglerna för för- och eftersökning. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Systemvariabel </p> </td> 
      <td colname="col2"> <p>Skrivskyddade variabler som angetts av det interna systemet som du kan kontrollera. Följande systemvariabler stöds: </p> <p> 
        <ul id="ul_BC17F1637F27424CA4E8F530C28A3245"> 
          <li id="li_C7DF96EFD7AA4A449D00F7EACCAA0EB1"> <span class="uicontrol"> värdnamn  </span> <p>Namnet på servervärden. </p> </li> 
          <li id="li_F85AB1D2B9374A859657D12B8ED6674B"> <span class="uicontrol"> uri  </span> <p>Begärd URI utan frågesträngen. </p> </li> 
          <li id="li_440149C9EC6E4805B77BBC97BE41542A"> <span class="uicontrol"> args  </span> <p>Hela frågesträngen. </p> </li> 
          <li id="li_F583FC4B0E404858BB3522B33A6F7A0A"> <span class="uicontrol"> miljö  </span> <p>"Stage" eller "live" beroende på om den inkommande frågan skickades till din staged- eller livemiljö. </p> </li> 
          <li id="li_15902AA49B144D42A5E95D7E8B0FB1E1"> <span class="uicontrol"> hänvisare  </span> <p>Den URL som kunden kom ifrån. </p> </li> 
          <li id="li_6FEE352DB7A842FCB2EBE1398AD03666"> <span class="uicontrol"> användaragent  </span> <p>Strängen "user-agent" i kundens webbläsare. </p> </li> 
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Frågeparameter </p> </td> 
      <td colname="col2"> <p>CGI-parametrar skickades till frågan. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Backend-parameter </p> </td> 
      <td colname="col2"> <p>Inkommande frågeparametrar översätts till slut till serverdelsparametrar som används för att utföra sökningen. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-parametrar för backend-sökning </a>. </p> <p>Backend-parametrar visas inte i navigeringselement. Det innebär att du kan dölja eventuella ytterligare parametrar som du vill tillämpa på en sökning från dina kunder. Åtgärder på backend-parametrar är sena. alltså används de precis innan sökningen skickas. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fasett </p> </td> 
      <td colname="col2"> <p>Särskilda CGI-parametrar som är associerade med en viss faktor. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rankning </p> </td> 
      <td colname="col2"> <p>Här kan du ange vilken rankningsregel som ska användas i sökningen. Det här alternativet visas bara när du har definierat några rankningsfält och rankningsregler. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Butik </p> </td> 
      <td colname="col2"> <p>Sökmotorn identifierar automatiskt vilket arkiv användaren befinner sig i baserat på värdnamnet eller frågeparametern <span class="codeph"> gs_store </span>, där den senare har prioritet. Du kan skapa villkor från butiken. Om du bara rensar en fråga kan du även använda en åtgärd för att åsidosätta den aktuella butiken. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sista regeln </p> </td> 
      <td colname="col2"> <p>När villkoren uppfylls för en regel som har den senaste regeluppsättningen, utförs inga ytterligare regler i bearbetningsmodulen för frågerensning efter matchningsregelns åtgärd. Detta är användbart när du har angett åtgärder som gör att en senare regel matchar, men du inte vill att den senare regeln ska aktiveras. Observera att om en regel utför en omdirigering sker omdirigeringen omedelbart, så den fungerar i stort sett som om den sista regeln hade angetts. </p> </td> 
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

## Redigera en frågerensningsregel {#task_FA2FF1A7E2634350AD703485CBC27CB3}

Du kan redigera befintliga frågerensningsregler som du har lagt till på sidan Regler för frågerensning.

**Så här redigerar du en frågerensningsregel**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]** på produktmenyn.
1. På sidan [!DNL Query Cleaning Rules], under kolumnen **[!UICONTROL Actions]** i tabellen, klickar du på **[!UICONTROL Edit]** för den associerade regel som du vill redigera.
1. Använd listrutorna och textfälten på sidan [!DNL Edit Query Cleaning Rule] för att bygga ut frågan.

   Se tabellen med alternativ under [Lägga till en frågerengöringsregel](../c-about-rules-menu/c-about-query-cleaning-rules.md#task_47F43988D3D9485F8AE1DFDA7E00BF54).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en frågetorensningsregel {#task_C52D17226B824590B087CAB6970CBB01}

Du kan ta bort frågerensningsregler som du inte längre behöver eller använder.

När du tar bort en regel justeras ordningen som återstående regler körs automatiskt för att ta hänsyn till borttagningen.

**Så här tar du bort en frågerengöringsregel**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]** på produktmenyn.
1. På sidan [!DNL Query Cleaning Rules], under kolumnen **[!UICONTROL Actions]** i tabellen, klickar du på **[!UICONTROL Delete]** för den associerade regel som du vill ta bort.
1. Klicka på **[!UICONTROL OK]** i dialogrutan [!DNL Confirmation].
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ändra ordningen som frågetorensningsreglerna körs {#task_C24012C45A4445468A7FD998017388CA}

Du kan ändra ordningen på frågerengöringsregler om du vill ändra i vilken ordning de körs på presentationsmallar.

Regler för frågerensning körs i den ordning de definierats. Ju högre ordningsnummer en regel har, desto senare körs den i processen, och tidigare regler trumpetas. Du ändrar ordning på reglerna genom att ange ett nytt nummer i kolumnen Ordning i tabellen på sidan [!DNL Query Cleaning Rules]. Du kan också använda dra-och-släpp-regler för att ändra deras körningsordning.

**Så här ändrar du den ordning som frågerensregler körs i**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Query Cleaning]** på produktmenyn.
1. Gör något av följande på sidan [!DNL Query Cleaning Rules]:

   * Klicka på kolumnrubriken [!DNL Order] om du vill sortera reglerna i stigande eller fallande ordning.
   * I kolumnen [!DNL Order] skriver du ordningsnumret som du vill att regeln ska köras i textfältet till vänster om namnet på en frågerensregel.
   * Dra och släpp en tabellrad till den position där du vill att linjen ska köras. Alla ordernummer uppdateras för att återspegla den nya ordningen som reglerna körs i.

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

