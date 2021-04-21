---
description: Använd regler före sökning för att analysera den inkommande frågan och avgöra vilken presentationsmall som ska användas. Regler före sökning körs i sekvens för varje fråga. Om du vill ändra ordningen på reglerna kan du dra och släppa. Den faktiska ordningen ändras inte förrän du sparar den.
solution: Target
title: Om regler för försökning
topic-legacy: Rules,Site search and merchandising
uuid: e75f9d9e-e8ca-4184-bf79-b1fdadb5c0fe
exl-id: 23e7feda-956a-48ce-8c61-fe0498c1bbda
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1661'
ht-degree: 0%

---

# Om regler för försökning{#about-pre-search-rules}

Använd regler före sökning för att analysera den inkommande frågan och avgöra vilken presentationsmall som ska användas. Regler före sökning körs i sekvens för varje fråga. Om du vill ändra ordningen på reglerna kan du dra och släppa. Den faktiska ordningen ändras inte förrän du sparar den.

## Använda regler för försökning {#concept_5BF84BB6FACB4645BA9CB7496A01CD1F}

Regler före sökning används vanligtvis för att välja vilken presentationsmall som ska visa resultatet baserat på den inkommande frågan. Mer avancerade funktioner kan användas för att ändra frågan som används för en sökning som görs för en presentationsmall. Du kan lägga till, ta bort eller ändra värdet på frågeparametrar efter behov. För varje inkommande fråga undersöker en bearbetningsmodul för försökning reglerna för försökning för att avgöra om frågan ändras och vilken presentationsmall som används. Varje regel för försökning består av två huvudelement: regelns åtgärder och valfria villkor. Du kan ange ett obegränsat antal regler och villkor. Ordningen på dessa regler är viktig eftersom regeluppsättningen slingras genom regel. När en regels villkor matchas utförs alla associerade åtgärder.

I modulen Försöksbearbetning instansieras alla definierade mallar och tillhörande namngivna sökningar där varje sökning får en lokal kopia av cgi-parametrarna. Det innebär att du kan anpassa en sökning genom att lägga till, ta bort eller ändra någon av de cgi-parametrar som används i sökningen utan att ändra några andra namngivna sökningar som mallen använder eller påverkar någon av de andra mallarna. Om du har en presentationsmall som visar mer än en resultatuppsättning kan du därför anpassa varje sökning individuellt. Om du vill göra ändringar i de globala CGI-parametrarna innan de kopieras till varje sökning för varje mall använder du frågerensningsmodulen.

## Villkor för regel för försökning {#section_B5568ADEB28546A280720309498B045D}

Villkoren är valfria. Om du väljer att ange åtgärder för varje fråga utförs alltid åtgärderna. Det är en god vana att köra den första regeln för varje fråga, där den väljer din standardpresentationsmall. På det här sättet kan du vara säker på att du, oavsett vilken fråga som kommer in, har valt en mall för presentation av det värsta scenariot som ska användas. Villkoren kan baseras på CGI-frågeparametrar, cookies eller anpassade variabler som en tidigare regel har angett eller en systemvariabel.

## Regelåtgärder före sökning {#section_3B8E19D287554C1C969F5B8D81226981}

Alla åtgärder i en regel före sökning som har matchande villkor utförs. Åtgärderna består vanligtvis av en åtgärd, de data som ska utföra åtgärden på och det värde som ska användas. Den enklaste åtgärden är att ange vilken presentationsmall som ska användas när frågan matchar villkoren för regeln för förhandssökning. Ange sedan målmallen som namnet på presentationsmallen. Mer komplicerade åtgärder kan användas för att ändra sökningen som används för en viss mall genom att utföra en åtgärd på en malls sökparameter. När du utför en åtgärd på en malls sökparameter anger du en presentationsmall och en sökning.

## Allmänna regler {#section_885ECB9DBF0C4D539C14F82BCAA35B4E}

När du utför åtgärder på en malls sökparameter finns det två speciella värden: *target och *primär för presentationsmallen respektive den namngivna sökningen. Med dessa värden kan du skapa regler som baseras på den aktuella målmallens primära sökning. Med hjälp av dessa konstruktioner kan du skapa allmänna regler där du inte behöver oroa dig för vad den aktuella målmallen eller den primära sökningen kallas. Det är tydligt att en tidigare regel för försökning definierar vad den aktuella målmallen är. I annat fall väljs en inledande presentationsmall åt dig, vilket ger oönskade resultat.

## Exempel {#section_EA153A151987454EA44A4A6862466DF6}

Ställ in standardmallen på guided.tmpl, och när användaren skickar in en cgi-parameter med namnet lang, som är inställd på ett känt språk, använd det språkets mall.

```
    On condition: 
      Every Query 
    Perform the following actions: 
      Set targeted template to guided 
 
    On condition: 
      Query lang matches regular expression fr 
    Perform the following actions: 
      Set targeted template to guided_french 
 
    On condition: 
      Query lang matches regular expression de 
    Perform the following actions: 
      Set targeted template to guided_german
```

## Bästa praxis {#section_31EBAE5E54174DEE8986CBB636746A98}

* Den första regeln väljer en standardmall för varje fråga.
* Frågans datautvinning görs inom frågerensningsregler. Du kan referera till dem i försöksbearbetningen.
* Lägg till nya anpassade variabler som du har skapat i reglerna för försökning till en regel för försökning som körs för varje fråga innan andra regler för försökning refererar till dem.

## Lägga till en ny regel för försökning {#task_182B95918462490D8BDA7F16A81CAC11}

Du kan använda [!DNL Pre-Search Rules] för att välja vilken presentationsmall som ska användas för att visa sökresultaten baserat på den inkommande frågan.

**Lägga till en ny regel för försökning**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Rule]** på sidan [!DNL Pre-Search Rules].
1. I fältet [!DNL Name] skriver du namnet på den nya frågerengöringsregeln.
1. Använd listrutorna och textfälten på sidan [!DNL Add Pre-Search Rule] för att bygga ut frågan.

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
      <td colname="col2"> <p>En HTTP-cookie. Cookies-namn och -värden måste vara Uniform Resource Identifier-kodade. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Anpassad variabel </p> </td> 
      <td colname="col2"> <p>En användardefinierad variabel. Lägg till, ta bort eller ange ett obegränsat antal användardefinierade variabler. </p> <p>Du kan referera till alla variabler som du har definierat i modulen Frågerengöring i reglerna för försökning. </p> </td> 
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
        </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fasett </p> </td> 
      <td colname="col2"> <p>Särskilda CGI-parametrar i den globala samlingen som är kopplade till en viss aspekt. Alla CGI-parametrar kopieras till alla namngivna sökningar i en mall efter Frågerensning. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Frågeparameter </p> </td> 
      <td colname="col2"> <p>CGI-parametern i den globala samlingen. Parametrarna kopieras till varje namngiven sökning i en mall efter Frågerensning. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mallens sökparameter </p> </td> 
      <td colname="col2"> <p>En CGI-parameter som är lokal till en namngiven sökning som är kopplad till en presentationsmall. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mallens serverdelsparameter </p> </td> 
      <td colname="col2"> <p>Inkommande frågeparametrar översätts till slut till serverdelsparametrar som används för att utföra sökningen. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-parametrar för backend-sökning </a>. </p> <p>Backend-parametrar visas inte i navigeringselement. Det innebär att du kan dölja eventuella ytterligare parametrar som du vill tillämpa på en sökning från dina kunder. Parametern är lokal för en viss sökning i en presentationsmall. Åtgärder på backend-parametrar är sena. alltså används de precis innan sökningen skickas. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Målmall </p> </td> 
      <td colname="col2"> <p>En särskild instans av en systemdefinierad anpassad variabel som inte kan tas bort. Den här variabeln innehåller den aktuella målpresentationsmallen. Du kan läsa eller ställa in den här variabeln genom att ange den anpassade variabeln"target_template". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rankning </p> </td> 
      <td colname="col2"> <p>Här kan du ange vilken rankningsregel som ska användas i sökningen. Det här alternativet visas bara när du har definierat rankningsfält och rankningsregler. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Butik </p> </td> 
      <td colname="col2"> <p>Sökmotorn identifierar automatiskt vilket arkiv kunden befinner sig i baserat på värdnamnet eller frågeparametern <span class="codeph"> gs_store </span>, där den senare har prioritet. Du kan skapa villkor från butiken. Om du bara rensar en fråga kan du även använda en åtgärd för att åsidosätta den aktuella butiken. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sista regeln </p> </td> 
      <td colname="col2"> <p>När det här alternativet är markerat utför bearbetningsmodulen för försökning inga ytterligare regler efter matchningsregelns åtgärd. Den här åtgärden är användbar när du har angett åtgärder som gör att en senare regel matchar, men du inte vill att den senare regeln ska köras. </p> </td> 
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

## Redigera en regel för försökning {#task_25F77050C5DA42B29DFD1C9718FB8C64}

Du kan redigera befintliga regler för försökning som du har lagt till på sidan [!DNL Pre-Search Rules].

**Redigera en regel för försökning**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** på produktmenyn.
1. På sidan [!DNL Pre-Search Rules], under kolumnen **[!UICONTROL Actions]** i tabellen, klickar du på **[!UICONTROL Edit]** för den associerade regel som du vill redigera.
1. Använd listrutorna och textfälten på sidan [!DNL Edit Pre-Search Rule] för att bygga ut frågan.

   Se tabellen med alternativ under [Lägga till en ny regel för försökning](../c-about-rules-menu/c-about-pre-search-rules.md#task_182B95918462490D8BDA7F16A81CAC11).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en regel {#task_128B6A79CA6C451C991AEDAD58F51743} för försökning

Du kan ta bort regler för försökning som du inte längre behöver eller använder.

När du tar bort en regel justeras ordningen som återstående regler körs automatiskt för att ta hänsyn till borttagningen.

**Ta bort en regel för försökning**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** på produktmenyn.
1. På sidan [!DNL Pre-Search Rules], under kolumnen **[!UICONTROL Actions]** i tabellen, klickar du på **[!UICONTROL Delete]** för den associerade regel som du vill ta bort.
1. Klicka på **[!UICONTROL OK]** i dialogrutan [!DNL Confirmation].
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ändra ordningen som reglerna för försökning körs {#task_C18817276A3C459089C97448076365D1}

Du kan ändra ordningen på reglerna för förhandssökning om du vill ändra i vilken ordning de körs på presentationsmallar.

Regler för försökning körs i den ordning de definierats. Ju högre ordningsnummer en regel har, desto senare körs den i processen, och tidigare regler trumpetas. Du ändrar ordning på reglerna genom att ange ett nytt nummer i kolumnen Ordning i tabellen på sidan [!DNL Pre-Search Rules]. Du kan också använda dra-och-släpp-regler för att ändra deras körningsordning.

**Så här ändrar du ordningen som regler för försökning körs**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Pre-Search Rules]** på produktmenyn.
1. Gör något av följande på sidan [!DNL Pre-Search Rules]:

   * Klicka på kolumnrubriken **[!UICONTROL Order]** om du vill sortera reglerna i stigande eller fallande ordning.
   * I kolumnen **[!UICONTROL Order]** skriver du ordningsnumret som du vill att regeln ska köras i textfältet till vänster om namnet på en regel för försökning.
   * Dra och släpp en tabellrad till den position där du vill att linjen ska köras. Alla ordernummer uppdateras för att återspegla den nya ordningen som reglerna körs i.

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).
