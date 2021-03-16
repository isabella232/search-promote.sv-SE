---
description: Du kan konfigurera Menade du så att kunderna får förslag på giltiga söktermer när de har provat sökningar som har misslyckats. Förslag skapas genom att söka efter stavnings- och skrivkorrigeringar av de söktermer som resulterar i en giltig sökning.
solution: Target
title: Om du menade
topic: Linguistics, Site search and merchandising
uuid: c5973541-3d6b-4fc9-bad4-66d4d3559fe8
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---


# Om Menade du{#about-did-you-mean}

Du kan konfigurera Menade du så att kunderna får förslag på giltiga söktermer när de har provat sökningar som har misslyckats. Förslag skapas genom att söka efter stavnings- och skrivkorrigeringar av de söktermer som resulterar i en giltig sökning.

## Konfigureringen betydde {#task_B539D6A0043547EFB1CA19B67E762371}

Du kan anpassa hur [!DNL site search/merchandising] ger sökförslag när en kunds fråga returnerar inga, eller minimala, sökresultat.

<!-- 

t_configuring_did_you_mean.xml

 -->

**Att konfigurera menade du**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Did You Mean]** på produktmenyn.
1. På sidan [!DNL Did You Mean] anger du blanksteg eller radavgränsade ord för att filtrera bort oönskade förslag i textfältet **Ta bort dessa ord från Förslag**.

   Det här är ord i sökindexet som inte visas som rekommenderade alternativa söktermer. Du kan utesluta ord som matchar ett mönster genom att använda reguljära uttryck. Annars tas bara det exakta ordet bort.

1. Ange **Menade du** alternativ som du vill använda.

   <!-- 
   
   r_did_you_mean_options.xml
   
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
      <td colname="col1"> <p>Förslagsalgoritm </p> </td> 
      <td colname="col2"> <p>Justerar hur långt programmet går för att hitta förslag. Om en användare gör ett misstag med en bokstav visas samma förslag för alla algoritmer. Orsaken till detta är att det bara krävs en redigering för att komma fram till ett fungerande förslag, och alla algoritmer hittar ord som ligger nära originalet. Men när de ursprungliga söktermerna inte liknar de befintliga termerna i indexet fortsätter <b>Deep</b> och <b>Bad Spellers</b> förslagsalgoritmer att söka efter möjliga förslag. Det här scenariot är användbart om en kund försöker med ett egennamn som är svårt att skriva och de låter ut namnen. Om du bara vill att liknande förslag ska visas kan du välja algoritmen <b>Quick</b>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardantal förslag som ska visas </p> </td> 
      <td colname="col2"> <p>Anger antalet Menade du termförslag (0-20) som du vill visa när en kunds sökning inte ger några resultat. Standardvärdet är 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minimal ordlängd för förslag </p> </td> 
      <td colname="col2"> <p>Rensade termer Betyder du termer genom att ange det minsta antalet bokstäver för ett föreslaget ord. </p> <p>Om du till exempel anger värdet 4 föreslår programmet inte ett ord som är 1, 2 eller 3 tecken långt. Om du anger värdet 0 tas inga korta ord bort från termförslagen. Om du anger ett högt värde resulterar det oftast inte i några termförslag. Standardvärdet är 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minsta indexfrekvens </p> </td> 
      <td colname="col2"> <p> Anger det minsta antal gånger ett ord måste finnas i indexet innan det tas med i ordlistan Menade du. </p> <p>Du kan inte ange ett negativt tal i fältet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sök efter föreslagen term om inget resultat </p> </td> 
      <td colname="col2"> <p>Söker automatiskt efter den första föreslagna termen när en kunds sökning inte ger några resultat och det finns minst ett"Menade ni"-förslag. </p> <p>Du kan använda följande taggar i presentationsmallen för att ange att webbplatssökning/försäljning automatiskt söker efter en annan term: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> <p>Här kan du även visa andra förslag. </p> <p> <code>&nbsp;&lt;guided-if-suggestion-autosearch&gt;&nbsp;&nbsp;There&nbsp;was&nbsp;0&nbsp;matches&nbsp;for&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt;&nbsp;&nbsp;&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&lt;guided-param&nbsp;gsname="q"&gt;?&nbsp;Here&nbsp;are&nbsp;the&nbsp;results&nbsp;for&nbsp;that&nbsp;search.&nbsp;&nbsp;&nbsp;Or&nbsp;Did&nbsp;You&nbsp;Mean&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestions&gt;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-autosearch&gt;</code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Gör förslag på grund av låga resultat </p> </td> 
      <td colname="col2"> <p>Om en kund söker efter en term som ger mindre än tio resultat, kontrollerar sökmotorn om den har ett förslag som kan ge mer än 100 resultat. Om den gör det kan du använda följande taggar för att visa för användaren att de kanske har velat söka efter något annat medan de har resultat: </p> <p> <code>&nbsp;&lt;guided-if-suggestion-low-results&gt; &nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;Search&nbsp;for&nbsp;guided-param&nbsp;gsname="q"&gt;.&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestion&gt;&lt;guided-suggestion-link&gt;&lt;guided-suggestion&nbsp;/&gt;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt;&lt;/guided-suggestions&gt;&nbsp;&lt;/guided-if-suggestion-low-results&gt;</code> </p> <p> I ovanstående scenario styrs antalet förslag av värdet som anges i <span class="uicontrol"> Standardantal förslag att visa</span>. Det låga och höga tröskelvärdet kan konfigureras med alternativen nedan. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Gör förslag när de inledande resultaten är färre än </p> </td> 
      <td colname="col2"> <p>Styr antalet resultat när systemet börjar erbjuda förslag. </p> <p>Det här alternativet visas bara när du markerar <span class="uicontrol"> Gör förslag på grund av låga resultat</span>. </p> <p>Standardvärdet är 10. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ett förslag måste generera minst så här många resultat </p> </td> 
      <td colname="col2"> <p>Filtrerar förslag som görs på grund av låga resultat i den primära sökningen efter deras resultatantal. </p> <p>Det här alternativet visas bara när du markerar <span class="uicontrol"> Gör förslag på grund av låga resultat</span>. </p> <p>Standardvärdet är 100. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **Spara ändringar**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

