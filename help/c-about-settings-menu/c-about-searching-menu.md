---
description: Använd menyn Sökning för att ange uteslutna ord, samlingar, begränsningar, förhandsgranskning och ramar.
solution: Target
subtopic: Searching
title: Om menyn Söka
topic: Settings,Site search and merchandising
uuid: 072111fc-a32b-4acb-8337-cb21bcdb5542
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '11170'
ht-degree: 0%

---


# Om menyn Söka{#about-the-searching-menu}

Använd menyn Sökning för att ange uteslutna ord, samlingar, begränsningar, förhandsgranskning och ramar.

## Om sökningar {#concept_207105CF26B1448F8A3D223787C56AB8}

Du kan använda Sökningar för att definiera och anpassa de namngivna sökningar som dina presentationsmallar kan referera till.

<!-- 

c_about_searches.xml

 -->

I presentationsmallen kan du referera till namngivna sökningar som är definierade i modulen Sökningar. På så sätt kan du enkelt anpassa typen av sökning som görs för en viss uppsättning mallar.

Information om hur du utesluter fraser och vanliga ord som används ofta från sökresultaten finns i [Konfigurera uteslutna ord](../c-about-linguistics-menu/c-about-excluded-words.md#task_60BF6BB7A66C48479D2BBB32C0F38CDE).

Mer information om hur du definierar specifika, sökbara områden på webbplatsen finns i [Lägga till samlingar](../c-about-settings-menu/c-about-searching-menu.md#task_07732D0F00104E59AD421297A704B2F6).

Mer information om hur du anger en målram för sökresultatlänkar finns i [Använda ramar med formulär](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Information om hur du begränsar sökningar baserat på HTTP-referens, IP-adress eller begäranschema (HTTP eller HTTPS) finns i [Ange värden i Förhandsgranska](../c-about-settings-menu/c-about-searching-menu.md#task_CE267A0FF621474E80AB43B67B1C28D7).

## Söktips {#section_22F0E2BCF259459FA5F49FBCC0F09A7C}

Om du vill få mer specifika sökresultat kan du använda följande söktips.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Söktips </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Kontrollera stavning </p> </td> 
   <td colname="col2"> <p>Se till att söktermerna är rättstavade. Om <span class="uicontrol"> Sound-Alike Matching </span> är aktiverat i <span class="uicontrol"> Linguistics </span> &gt; <span class="uicontrol"> Words &amp; Languages </span> försöker sökmotorn hitta ord som låter ungefär som söktermerna. Det är dock alltid bäst att försöka stava söktermerna korrekt. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Om ord och språk </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd flera ord </p> </td> 
   <td colname="col2"> <p>Exempel: 
     <code>
       our free product 
     </code> </p> <p>Frågor med flera ord ger mer raffinerade resultat än frågor med enstaka ord. </p> <p>Till exempel: 
     <code>
       our free product 
     </code> returnerar mer relevanta resultat än bara 
     <code>
       product 
     </code>. </p> <p>Kom ihåg att relevanta resultat returneras även om de inte innehåller alla frågetermer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd liknande ord </p> </td> 
   <td colname="col2"> <p>Exempel: 
     <code>
       safe secure privacy security 
     </code> </p> <p>Ju mer liknande ord du kan använda i en sökfråga, desto mer relevant är sökresultaten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd lämplig versal </p> </td> 
   <td colname="col2"> <p>Exempel: 
     <code>
       Search Template Reference 
     </code> </p> <p>Använd versaler för rätt substantiv. Om du använder ett ord med gemener matchar sökmotorn alla bokstäver i ordet. </p> <p>Om du till exempel skriver 
     <code>
       search 
     </code> returnerar sökmotorn alla dokument som innehåller orden "search", "Search" och "SEARCH". Om du skriver 
     <code>
       Search 
     </code> returnerar sökmotorn dokument som bara innehåller det versala ordet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd citattecken </p> </td> 
   <td colname="col2"> <p>Exempel: 
     <code>
       "our pledge to you" 
     </code> </p> <p>Använd citattecken för att hitta ord som måste finnas intill varandra, t.ex."vårt löfte till dig". Utan de omgivande citattecknen innehåller sökresultaten orden"vår","pant","till" och"du", men inte nödvändigtvis i den ordningen. I stället kan orden visas var som helst, och i vilken ordning som helst, i dokumentet. </p> <p> Om du använder det avancerade sökformuläret med alternativknappar för <span class="uicontrol"> </span>, <span class="uicontrol"> alla </span> och <span class="uicontrol"> frasen </span>, kan du bara använda citattecken när <span class="uicontrol"> eller </span> är markerat. Citattecken ignoreras om <span class="uicontrol"> alla </span> eller <span class="uicontrol"> fras </span> är markerade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd + (plus) eller - (minus) </p> </td> 
   <td colname="col2"> <p>Exempel: 
     <code>
       +"template language" 
     </code> </p> <p>Använd + för att ange att ett sökord eller en fras måste visas i sökresultatet. </p> <p>Använd - om du vill ange att ett sökord eller en fras inte får ingå i sökresultaten. </p> <p>Du måste innehålla en fras inom citattecken. Lämna inga mellanslag mellan plus- eller minustecknet och söktermen, som i exemplet ovan. </p> <p> Om du använder det avancerade sökformuläret med alternativknappar för <span class="uicontrol"> </span>, <span class="uicontrol"> alla </span> och <span class="uicontrol"> frasen </span>, kan du bara använda citattecken när <span class="uicontrol"> eller </span> är markerat. plus- och minustecknen ignoreras om <span class="uicontrol"> alla </span> eller <span class="uicontrol"> frasen </span> är markerade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd fältsökningar </p> </td> 
   <td colname="col2"> <p>Exempel: </p> <p> 
     <ul id="ul_F7CFF7652894402E8D19D6BA49792530"> 
      <li id="li_27492EF933C5437CB2C499746EC8CF39"> 
       <code>
         title:about 
       </code> </li> 
      <li id="li_BD21505122104FD0B16A4DAD777811DA"> 
       <code>
         desc:"Our Team" 
       </code> </li> 
      <li id="li_8264630F8B3D46BF872EFEB1D69DB6BE"> 
       <code>
         keys:login 
       </code> </li> 
      <li id="li_EBB81CBFC6DA45E99A524890DCD56E9F"> 
       <code>
         body:security 
       </code> </li> 
      <li id="li_6A852E35D6984A2C94144AB6C6D2DFA0"> 
       <code>
         alt:"join now" 
       </code> </li> 
      <li id="li_F4C5699360484D12ACD62BBFB84A7904"> 
       <code>
         url:help 
       </code> </li> 
      <li id="li_B2DBBA2239E74D98868D92B3EDEF5B51"> 
       <code>
         target:Adobe 
       </code> </li> 
     </ul> </p> <p>Med fältsökningar kan du skapa specifika sökningar efter ord som visas i en viss del av ett dokument. </p> <p>Du kan utföra en fältsökning på brödtext (body:), rubriktext (title:), alt-text (alt:), meta description (desc:), meta-nyckelord (keys:), URL (url:) eller meta-målnyckelord (target:). Använd gemener som fältnamn och omedelbart följt av kolon. Det finns inga mellanslag mellan kolon och söktermen. </p> <p>Fältsökningarna följs endast av ett ord eller en fras. Fraser måste finnas inom citattecken. </p> <p>Om du använder det avancerade sökformuläret med en listruta för fältnamnet, kan du bara ange fältnamn före ett ord eller en fras när <span class="uicontrol"> eller </span> är markerat. Specifika fältnamn ignoreras om något annat avancerat sökformulärfält har valts i listrutan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använd jokertecken </p> </td> 
   <td colname="col2"> <p>Exempel: </p> <p> 
     <ul id="ul_D8E3867EB15641B0A6E55AD546CCB4DD"> 
      <li id="li_CB8B8FC15EB14B13BB33BB69F5206303"> 
       <code>
         wh* 
       </code> </li> 
      <li id="li_5350A934648C4C81BD6C0875061B426B"> 
       <code>
         "wh* are" 
       </code> </li> 
      <li id="li_7965A2F7186F40039D2F0736299D11B1"> 
       <code>
         415-*-* 
       </code> </li> 
     </ul> </p> <p>Sökningar med jokertecken utökar antalet träffar för en viss begäran. Tecknet * används som jokertecken. </p> <p>Sök till exempel efter 
     <code>
       wh* 
     </code> hittar orden "what", "why", "when", "whether" och alla andra ord som börjar med "wh". Om du söker efter *henne* hittas orden"här","om","tillsammans","samla" och alla andra ord som innehåller"henne" var som helst i ordet. </p> <p>Du kan kombinera jokertecken med modifierarna + och -, citattecken för fraser samt fältsökningsspecificerare. </p> <p>Sökningen 
     <code>
       +wh* -se*ch 
     </code> söker efter alla sidor som har ett ord som börjar med "wh" och som inte innehåller ett ord som börjar med "se" och slutar med "ch". </p> <p>Sökningen 
     <code>
       "wh* are" 
     </code> hittar fraserna "var är", "vad är", "varför är" osv. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lägga till en ny sökdefinition {#task_98D3A168AB5D4F30A1ADB6E0D48AB648}

Du kan använda panelen [!DNL GS Add Search] för att konfigurera och lägga till en ny sökdefinition för komponenterna i den guidade sökningen, till exempel facets, vägbeskrivningar, sidnavigering, menyer och senaste sökningar, i presentationslagret.

<!-- 

t_adding_a_new_definition.xml

 -->

När du har lagt till din nya sökdefinition måste du referera till den i presentationsmallen så att den visas.

Se [Mallar](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**Lägga till en ny sökdefinition**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Search]** på sidan [!DNL Searches].
1. Ange önskade alternativ på sidan **[!UICONTROL GS Add Search]**.

   <!-- 
   
   r_gs_search_options.xml
   
   -->

   Observera att de bearbetningsregler som väljer din presentationsmall kan åsidosätta några av dessa alternativ.

   Se [Lägga till en ny sökdefinition](../c-about-settings-menu/c-about-searching-menu.md#task_98D3A168AB5D4F30A1ADB6E0D48AB648) eller [Redigera en sökdefinition](../c-about-settings-menu/c-about-searching-menu.md#task_AF1FFB1AEF874C13AB359C28F74BF461).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Söknamn </p> </td> 
      <td colname="col2"> <p>Identifierar namnet på den definierade sökningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Källa </p> </td> 
      <td colname="col2"> <p>Gör att du kan välja den backend-sökning som du vill använda. Du kan välja mellan <span class="wintitle"> SiteSearch </span> eller <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Konto </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Search &amp; Promote </span> som källa. </p> <p>Gör att du kan välja det konto för sökning/försäljning av webbplatser som du vill söka efter. Vanligtvis söker en sökning i det konto som du använder just nu. Presentationsmallen kan dock använda en backend-sökning för alla dina andra konton. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Servernamn/IP </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Merchandising </span> som källa. </p> <p>Anger det fullständiga namnet för den <span class="wintitle"> Merchandising </span>-server som <span class="wintitle"> Merchandising </span>-sökningen ska ha åtkomst till. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Serverport </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Merchandising </span> som källa. </p> <p>Anger serverportnumret för <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Pyramid </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Merchandising </span> som källa. </p> <p>Anger pyramidan i <span class="wintitle"> Merchandising </span>-servern. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Antal resultat </p> </td> 
      <td colname="col2"> <p>Anger antalet sökresultat som du vill returnera. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Antal resultat för första sidan (om olika) </p> </td> 
      <td colname="col2"> <p>Anger antalet resultat som returneras på första sidan. Använd det här alternativet om du vill att det ska skilja sig från andra sidor. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Antal kolumner </p> </td> 
      <td colname="col2"> <p>Anger antalet kolumner som sökresultaten delas upp i. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Typ av sökning </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Search &amp; Promote </span> som källa. </p> <p>Här kan du välja mellan följande tre typer av sökning. </p> <p> 
        <ul id="ul_2F6FA9EFD8DB49EEAB866C3D070E2644"> 
          <li id="li_ECFEBEDD86FF4DE2BB768423B3B91B5E"> <span class="uicontrol"> alla  </span> <p>Söker efter dokument som innehåller alla ord i frågesträngen. </p> <p>Användning av"+" och"-" innan sökord inaktiveras och dessa tecken ignoreras. </p> </li> 
          <li id="li_62EB215BDDE74DF0BF76B3BD5B96776F"> <span class="uicontrol"> alla  </span> <p>Du kan använda "+"- och "-"-ordprefix. </p> </li> 
          <li id="li_3D71982C0BBA41AFA353069AF3F2F6D8"> <span class="uicontrol"> fras  </span> <p>Frågesträngen behandlas som om den vore en fras inom citattecken, och alla citattecken som skrivs av användaren ignoreras. </p> <p>Användning av"+" och"-" innan sökord inaktiveras och dessa tecken ignoreras. </p> </li> 
        </ul> </p> <p> Om du vill att varje ord i en fråga ska kunna välja ett facet-värde, ska den primära sökningen alltid använda <span class="uicontrol"> alla </span>. </p> <p>Du kan visa söktips om användningen av modifieringarna + och - i en sökfråga. </p> <p>Se <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> Om sökningar </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Samling </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Search &amp; Promote </span> som källa. </p> <p>Identifierar den samling i indexet som du vill söka i. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Befordra sökning </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Search &amp; Promote </span> som källa. </p> <p>Gör att du kan använda ett slumpmässigt urval från sökresultaten enligt det <span class="uicontrol"> antal resultat </span> som du har angett. </p> <p>Säljmarknadsföring är ett äldre koncept. Därför rekommenderar vi att du använder det nya banderollhanteringssystemet inom webbplatssökning/försäljning. </p> <p>Se <a href="../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA" type="concept" format="dita" scope="local"> Om banderoller </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Använd parametrar för faset </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du har valt <span class="uicontrol"> Search &amp; Promote </span> som källa och du har valt <span class="uicontrol"> Beforska </span>. </p> <p>Anger att en kampanjsökning använder de valda ansiktena för att begränsa kampanjerna. De flesta kampanjsökkonton använder inte det här alternativet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ange standarderbjudande om ingen matchande kampanj </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du har valt <span class="uicontrol"> Search &amp; Promote </span> som källa och du har valt <span class="uicontrol"> Beforska </span>. </p> <p>Anger att en annan sökning efter en befordran utförs om den inledande sökningen efter en befordran inte hittar något. Den andra sökningen efter en befordran släpper nyckelordet. I stället söker programmet efter en befordran där metadatafältet"is_default" är inställt på"yes". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Markera sökning </p> </td> 
      <td colname="col2"> <p>Visar ett visst antal resultat från huvudsökningen som du vill markera i en"hjältezon". </p> <p>Vanligtvis har markeringssökningar liknande sökvillkor som huvudsökningen men med en annan rangordningsmekanism för att framhäva vissa resultat. Programvaran tar bort dubbletterna från huvudsökningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Bassökning </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du har valt <span class="uicontrol"> Markera sökning </span>. </p> <p>Gör att du kan välja den sökning som innehåller de resultat som du markerar resultaten från. Dubbletter tas bort från sökningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dedupliceringsprioritet </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du har valt <span class="uicontrol"> Markera sökning </span>. </p> <p>Gör att du kan söka efter flera högdagrar. </p> <p>När du har flera markeringssökningar måste du ange prioriteten för borttagning av dubbletter, där"1" är den högsta prioriteten. </p> <p>Anta att du har två markeringssökningar: bästsäljare och nya produkter. Teoretiskt. det är möjligt att en bästsäljare också är en ny produkt. I så fall vill du att dubbletten ska tas bort från de nya produkterna och att huvudsökningen ska göras. Därför sätter ni prioriteten för bästsäljarna till 1 och prioriteten för nya produkter till 2. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parameter </p> </td> 
      <td colname="col2"> <p>Gör att du kan lägga till CGI-parametrar i sökningen. </p> <p>Se <a scope="local" href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita"> CGI-parametrar för backend-sökning </a>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Add]**.
1. (Valfritt) Gör något av följande på sidan [!DNL Searches]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en sökdefinition {#task_AF1FFB1AEF874C13AB359C28F74BF461}

Du kan använda panelen [!DNL Staged GS Edit Search] för att konfigurera om en befintlig sökdefinition för presentationslagret för guidad sökning.

<!-- 

t_editing_a_search_definition.xml

 -->

När du har redigerat sökdefinitionen bör du kontrollera att du har refererat till den i presentationsmallen så att den visas.

Se [Mallar](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**Redigera en sökdefinition**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]** på produktmenyn.
1. På sidan [!DNL Searches] i tabellen klickar du på **[!UICONTROL Edit]** i raden för den definition som du vill ändra.
1. Ange önskade alternativ på sidan **[!UICONTROL GS Edit Search]**.

   <!-- 
   
   r_gs_search_options.xml
   
   -->

   Observera att de bearbetningsregler som väljer presentationsmall kan åsidosätta några av dessa alternativ.

   Se [Lägga till en ny sökdefinition](../c-about-settings-menu/c-about-searching-menu.md#task_98D3A168AB5D4F30A1ADB6E0D48AB648) eller [Redigera en sökdefinition](../c-about-settings-menu/c-about-searching-menu.md#task_AF1FFB1AEF874C13AB359C28F74BF461).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Söknamn </p> </td> 
      <td colname="col2"> <p>Identifierar namnet på den definierade sökningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Källa </p> </td> 
      <td colname="col2"> <p>Gör att du kan välja den backend-sökning som du vill använda. Du kan välja mellan <span class="wintitle"> SiteSearch </span> eller <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Konto </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Search &amp; Promote </span> som källa. </p> <p>Gör att du kan välja det konto för sökning/försäljning av webbplatser som du vill söka efter. Vanligtvis söker en sökning i det konto som du använder just nu. Presentationsmallen kan dock använda en backend-sökning för alla dina andra konton. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Servernamn/IP </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Merchandising </span> som källa. </p> <p>Anger det fullständiga namnet för den <span class="wintitle"> Merchandising </span>-server som <span class="wintitle"> Merchandising </span>-sökningen ska ha åtkomst till. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Serverport </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Merchandising </span> som källa. </p> <p>Anger serverportnumret för <span class="wintitle"> Merchandising </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Pyramid </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Merchandising </span> som källa. </p> <p>Anger pyramidan i <span class="wintitle"> Merchandising </span>-servern. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Antal resultat </p> </td> 
      <td colname="col2"> <p>Anger antalet sökresultat som du vill returnera. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Antal resultat för första sidan (om olika) </p> </td> 
      <td colname="col2"> <p>Anger antalet resultat som returneras på första sidan. Använd det här alternativet om du vill att det ska skilja sig från andra sidor. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Antal kolumner </p> </td> 
      <td colname="col2"> <p>Anger antalet kolumner som sökresultaten delas upp i. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Typ av sökning </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Search &amp; Promote </span> som källa. </p> <p>Här kan du välja mellan följande tre typer av sökning. </p> <p> 
        <ul id="ul_E1D8B3DE9DB24DE4813D53F6298A03A6"> 
          <li id="li_C3DD7AA7699B477A9EE0731CFC012630"> <span class="uicontrol"> alla  </span> <p>Söker efter dokument som innehåller alla ord i frågesträngen. </p> <p>Användning av"+" och"-" innan sökord inaktiveras och dessa tecken ignoreras. </p> </li> 
          <li id="li_4C66B9EFEFA042908A4D3730F9F54EB0"> <span class="uicontrol"> alla  </span> <p>Du kan använda "+"- och "-"-ordprefix. </p> </li> 
          <li id="li_37E9AD42A61C4E31A0816DFB8E71118D"> <span class="uicontrol"> fras  </span> <p>Frågesträngen behandlas som om den vore en fras inom citattecken, och alla citattecken som skrivs av användaren ignoreras. </p> <p>Användning av"+" och"-" innan sökord inaktiveras och dessa tecken ignoreras. </p> </li> 
        </ul> </p> <p> Om du vill att varje ord i en fråga ska kunna välja ett facet-värde, ska den primära sökningen alltid använda <span class="uicontrol"> alla </span>. </p> <p>Du kan visa söktips om användningen av modifieringarna + och - i en sökfråga. </p> <p>Se <a href="../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8" type="concept" format="dita" scope="local"> Om sökningar </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Samling </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Search &amp; Promote </span> som källa. </p> <p>Identifierar den samling i indexet som du vill söka i. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Befordra sökning </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer <span class="uicontrol"> Search &amp; Promote </span> som källa. </p> <p>Gör att du kan använda ett slumpmässigt urval från sökresultaten enligt det <span class="uicontrol"> antal resultat </span> som du har angett. </p> <p>Säljmarknadsföring är ett äldre koncept. Därför rekommenderar vi att du använder det nya banderollhanteringssystemet inom webbplatssökning/försäljning. </p> <p>Se <a href="../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA" type="concept" format="dita" scope="local"> Om banderoller </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Använd parametrar för faset </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du har valt <span class="uicontrol"> Search &amp; Promote </span> som källa och du har valt <span class="uicontrol"> Beforska </span>. </p> <p>Anger att en kampanjsökning använder de valda ansiktena för att begränsa kampanjerna. De flesta kampanjsökkonton använder inte det här alternativet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ange standarderbjudande om ingen matchande kampanj </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du har valt <span class="uicontrol"> Search &amp; Promote </span> som källa och du har valt <span class="uicontrol"> Beforska </span>. </p> <p>Anger att en annan sökning efter en befordran utförs om den inledande sökningen efter en befordran inte hittar något. Den andra sökningen efter en befordran släpper nyckelordet. I stället söker programmet efter en befordran där metadatafältet"is_default" är inställt på"yes". </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Markera sökning </p> </td> 
      <td colname="col2"> <p>Visar ett visst antal resultat från huvudsökningen som du vill markera i en"hjältezon". </p> <p>Vanligtvis har markeringssökningar liknande sökvillkor som huvudsökningen men med en annan rangordningsmekanism för att framhäva vissa resultat. Programvaran tar bort dubbletterna från huvudsökningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Bassökning </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du har valt <span class="uicontrol"> Markera sökning </span>. </p> <p>Gör att du kan välja den sökning som innehåller de resultat som du markerar resultaten från. Dubbletter tas bort från sökningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Dedupliceringsprioritet </p> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du har valt <span class="uicontrol"> Markera sökning </span>. </p> <p>Gör att du kan söka efter flera högdagrar. </p> <p>När du har flera markeringssökningar måste du ange prioriteten för borttagning av dubbletter, där"1" är den högsta prioriteten. </p> <p>Anta att du har två markeringssökningar: bästsäljare och nya produkter. Teoretiskt. det är möjligt att en bästsäljare också är en ny produkt. I så fall vill du att dubbletten ska tas bort från de nya produkterna och att huvudsökningen ska göras. Därför sätter ni prioriteten för bästsäljarna till 1 och prioriteten för nya produkter till 2. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parameter </p> </td> 
      <td colname="col2"> <p>Gör att du kan lägga till CGI-parametrar i sökningen. </p> <p>Se <a scope="local" href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita"> CGI-parametrar för backend-sökning </a>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande på sidan [!DNL Searches]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en sökdefinition {#task_1D8E991E4C4146B7A7311FAE5DAA3742}

Du kan ta bort en stödlinjesökdefinition som du inte längre behöver eller använder.

<!-- 

t_deleting_a_search_definition.xml

 -->

Se [Mallar](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

**Ta bort en sökdefinition**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Searches]** på produktmenyn.
1. På sidan [!DNL Searches] i tabellen klickar du på **[!UICONTROL Delete]** i raden för den definition som du vill ta bort.
1. Klicka på **[!UICONTROL OK]** i dialogrutan [!DNL Confirmation].
1. (Valfritt) Gör något av följande på sidan [!DNL Searches]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om nyckelordshanteraren för fastnålade resultat {#concept_0C5F152C029C485D8872C6795CBCD7C7}

Du kan fästa sökresultaten manuellt på en viss plats. Dessa fästa resultat är kopplade till en specifik sökfråga eller nyckelord. Du kan använda [!DNL Pinned Result Keyword Manager] för att hantera alla nyckelord med fastnålade resultat.

<!-- 

c_about_pinned_results_keyword_manager.xml

 -->

## Sökregler för nyckelord som ska följa {#section_ED67A24BE884468286F34FA5DFF826D7}

Sökfrågan som du anger på panelen har följande regler:

* Radavstånd och avslutande blanksteg tas bort från frågan.
* Det går inte att använda specialsöktecken som följande:

   * Jokerteckenmatchning med asterisker (*).
   * Inget måste-ha eller måste-inte-ha-måste använda plus eller minus (+ eller -).
   * Ingen fältspecificerare med kolontecknet (:).
   * Inga kommatecken eller dubbla citattecken ( eller &quot;).

* Flera termer eller ord avgränsade med blanksteg i frågan tillåts.
* Versaler konverteras till gemener.

Söktermerna sparas exakt som de är; Du måste använda exakt samma sökord igen för att få exakt samma resultat.

Fastnålade resultat stöder inte skiftlägeskänslighet. Alla nyckelord har versaler konverterade till gemener.

## Ändra ordning på sökresultaten {#section_46FBE5279C7740A09D6DC9F54FE104AA}

När du söker efter ett nyckelord på panelen [!DNL Stage Add New Keyword] eller panelen [!DNL Staged Edit Keyword], återspeglar sökresultaten vad som kan hända efter nästa indexåtgärd. Du kan ändra ordningen på sökresultaten i tabellen på något av tre olika sätt.

Den första metoden är att använda kryssrutan **[!UICONTROL Pinned]**. Kryssrutan används för att fästa ett resultat vid en viss position. När du markerar kryssrutan fästs även alla sökresultat ovanför kryssrutan. Den här funktionen ser till att alla resultat ovanför kryssrutan visas i den angivna ordningen. Om du tar bort fästningen av ett sökresultat hamnar det under alla fästa resultat.

Den andra metoden är att dra och släppa i tabellen. Du kan flytta ett resultat till en ny plats genom att dra och släppa. När du har dragit ett resultat till en ny plats fästs alla resultat ovanför den nya platsen. Denna automatiska fästning ser till att resten av resultatet visas ovanför det nyligen dragna resultatet.

Den tredje metoden är att ange ordningen för fästa resultat genom att ange en specifik position i kolumnen &quot;#&quot;. Till skillnad från när du drar och släpper är ordningen på de simulerade sökresultaten bara självklar nästa gång du öppnar panelen [!DNL Staged Edit Keyword]. Om du anger ordernummer för en rad som inte är fäst ser du till att åtminstone många objekt fästs. Om du ställer in ordningsnumret för en fast rad anges ordningen för objektet i de objekt som är fästa. Det ökar dock inte antalet fästa objekt.

När du sparar sökresultaten kan du visa resultatet igen genom att ange exakt samma fråga i fältet Nyckelord.

## Om de fästa sökresultaten {#section_46780B7812F249F3B45503161C4FBDEE}

Sökresultaten ordnas ofta efter relevant poäng. Ett fäst sökresultat ignorerar dock relevant poäng och försöker åsidosätta den naturliga ordningen med dess förbestämda position. Genom att se till att resultatet förblir relativt där det finns, måste andra kända sökresultat ovan fästas.

Sökresultaten som visas på panelen simulerar vad som visas efter nästa index. Ändringar i det ursprungliga dokumentet eller vissa konfigurationsändringar i medlemscentrumet kan dock ge resultat med avvikelser. Om du till exempel ändrar innehållet i ett dokument är det inte känt förrän efter indexet.

Fastnålade resultat visas i en liknande eller samma ordning efter indexet eftersom de inte är relevanta. Ej fastnålade resultat återgår till sin naturliga position efter ett index. ordningen för ej fastnålade resultat är inte garanterad.

## Lägga till ett nytt nyckelord {#task_8CED128DADD34D0DAD2C64B64D0D6B06}

Du kan lägga till nya nyckelord och deras fastnålade resultat.

<!-- 

t_adding_a_new_keyword.xml

 -->

När du lägger till ett nytt nyckelord kan du ändra ordning på sökresultaten och fästa dem på en viss plats.

**Lägga till ett nytt nyckelord**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Keyword]** på sidan [!DNL Pinned Keyword Results Manager].
1. På sidan [!DNL Add New Keyword] anger du en sökfråga i fältet **[!UICONTROL Keyword]** och klickar sedan på **[!UICONTROL Search Keyword]**.

   <!-- 
   
   r_keyword_options.xml
   
   -->

   Du kan använda knappen Redigera tabell för att justera hur du visar tabellen med sökresultat. Du kan till exempel använda listan med kolumner för att visa eller dölja specifika kolumner. Du kan också ändra ordningen på kolumnerna genom att dra och släppa.

   I följande tabell beskrivs de kolumnegenskaper som finns i tabellredigeraren.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Kolumn </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Order </p> </td> 
      <td colname="col2"> <p>Anger den numeriska ordningen för kolumnernas utseende. Du kan dra och släppa kolumnerna för att automatiskt uppdatera ordningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fältnamn </p> </td> 
      <td colname="col2"> <p>Identifierar namnet på kolumnrubriken som visas i tabellen <span class="wintitle"> Simulerade sökresultat </span> i panelen <span class="wintitle"> Mellanlagrade Lägg till nytt nyckelord </span> och panelen <span class="wintitle"> Mellanlagrade redigeringsnyckelord </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkludera </p> </td> 
      <td colname="col2"> <p>Kolumnen visas i tabellen Fastnålade resultat om rutan är markerad. Om rutan är tom eller avmarkerad försvinner kolumnen från tabellen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visa URL som bild </p> </td> 
      <td colname="col2"> <p>Om metafältet som är tilldelat den här kolumnen har URL:er till bilder eller bilder placeras HTML-bildtaggar runt den om du markerar den här rutan och bilden visas. Bilder som saknas eller felaktiga länkar är tomma. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fältlängd </p> </td> 
      <td colname="col2"> <p>Här kan du ange den maximala textlängden för visning innan den trunkeras med ellipser (..). Om kolumnen är inställd på att visa URL:er som bilder har det här fältet ingen effekt. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Valfritt) Gör något av följande:

   * Ändra ordning på sökresultaten.
   * Klicka på **[!UICONTROL Edit Table]** för att justera vyn för tabellen [!DNL Simulated Search Results]. När du är klar klickar du på **[!UICONTROL Save Changes]** för att återgå till panelen [!DNL Add New Keyword].

1. Klicka på **[!UICONTROL Save Search Results]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Pinned Results Keyword Manager]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera ett nyckelord {#task_30C550A7350B4394B5B43536368A84B1}

Du kan redigera befintliga nyckelord och deras fastnålade resultat.

<!-- 

t_editing_a_keyword.xml

 -->

När du redigerar ett nyckelord kan du ändra ordning på sökresultaten och fästa dem vid en viss position.

**Redigera ett nyckelord**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]** på produktmenyn.
1. På sidan [!DNL Pinned Keyword Results Manager] i tabellen klickar du på **[!UICONTROL Edit]** i raden för det nyckelord som du vill ändra.
1. På sidan [!DNL Edit Keyword] anger du en sökfråga i fältet **[!UICONTROL Keyword]** och klickar sedan på **[!UICONTROL Search Keyword]**.

   Se till att du följer reglerna för nyckelordssökningen.

   <!-- 
   
   r_keyword_options.xml
   
   -->

   Du kan använda knappen Redigera tabell för att justera hur du visar tabellen med sökresultat. Du kan till exempel använda listan med kolumner för att visa eller dölja specifika kolumner. Du kan också ändra ordningen på kolumnerna genom att dra och släppa.

   I följande tabell beskrivs de kolumnegenskaper som finns i tabellredigeraren.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Kolumn </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Order </p> </td> 
      <td colname="col2"> <p>Anger den numeriska ordningen för kolumnernas utseende. Du kan dra och släppa kolumnerna för att automatiskt uppdatera ordningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fältnamn </p> </td> 
      <td colname="col2"> <p>Identifierar namnet på kolumnrubriken som visas i tabellen <span class="wintitle"> Simulerade sökresultat </span> i panelen <span class="wintitle"> Mellanlagrade Lägg till nytt nyckelord </span> och panelen <span class="wintitle"> Mellanlagrade redigeringsnyckelord </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkludera </p> </td> 
      <td colname="col2"> <p>Kolumnen visas i tabellen Fastnålade resultat om rutan är markerad. Om rutan är tom eller avmarkerad försvinner kolumnen från tabellen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visa URL som bild </p> </td> 
      <td colname="col2"> <p>Om metafältet som är tilldelat den här kolumnen har URL:er till bilder eller bilder placeras HTML-bildtaggar runt den om du markerar den här rutan och bilden visas. Bilder som saknas eller felaktiga länkar är tomma. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fältlängd </p> </td> 
      <td colname="col2"> <p>Här kan du ange den maximala textlängden för visning innan den trunkeras med ellipser (..). Om kolumnen är inställd på att visa URL:er som bilder har det här fältet ingen effekt. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Valfritt) Gör något av följande:

   * Ändra ordning på sökresultaten.
   * Klicka på **[!UICONTROL Edit Table]** för att justera vyn för tabellen [!DNL Simulated Search Results].

      Se [Lägga till ett nytt nyckelord](../c-about-settings-menu/c-about-searching-menu.md#task_8CED128DADD34D0DAD2C64B64D0D6B06).

      När du är klar klickar du på **[!UICONTROL Save Changes]** för att återgå till panelen [!DNL Add New Keyword].

1. Klicka på **[!UICONTROL Save Search Results]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Pinned Results Keyword Manager]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort ett nyckelord {#task_F17D6357D6DD416495E6D4117899D81D}

Du kan ta bort nyckelord som du inte längre behöver eller använder.

<!-- 

t_deleting_a_keyword.xml

 -->

När du lägger till ett nytt nyckelord kan du ändra ordning på sökresultaten och fästa dem på en viss plats.

**Ta bort ett nyckelord**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Pinned Results]** på produktmenyn.
1. På sidan [!DNL Pinned Keyword Results Manager] i tabellen klickar du på **[!UICONTROL Delete]** i raden för det nyckelord som du vill ta bort.
1. Klicka på **[!UICONTROL Delete]** på sidan [!DNL Delete Keyword].
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Pinned Results Keyword Manager]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om samlingar {#concept_62E42ACE53D54EEE9273433B86259127}

Du kan använda samlingar för att låta kunderna söka efter specifika delar av en webbplats så att de snabbt kan hitta det de letar efter.

<!-- 

c_about_collections.xml

 -->

Se [Om sökningar](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

Se [Använda samlingar i sökformulär](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Kunder kan till exempel söka efter en samling URL:er som är kopplade till produktförsäljning eller till supporttjänster. Innan kunderna kan använda de samlingar du anger måste du uppdatera sökformuläret på menyn Sökformulär.

Innan effekterna av inställningarna för samlingar är synliga för kunderna ska du återskapa platsindexet.

Du kan testa dina samlingar genom att ange en av webbplatsens URL:er i det valfria fältet **[!UICONTROL Test Collections]** och sedan klicka på **[!UICONTROL Test]**. Samlingen som den angivna sidan tillhör returneras.

Varje samling anges på en enda rad med ett namn och en URL-mask. En URL-mask kan bestå av följande:

* en fullständig sökväg som `https://www.mydomain.com/products.html`
* en partiell sökväg som `https://www.mydomain.com/products`
* ett reguljärt uttryck

   Om du vill göra en mask till ett reguljärt uttryck infogar du nyckelordet `regexp` mellan samlingens namn och URL-masken.

   Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

Varje rad i fältet Samlingar kan bara innehålla en URL-mask. Du kan dock ange flera URL-masker för samma samlingsnamn på olika rader. Följande exempel innehåller fyra olika samlingsnamn och fem URL-masker:

```
Company Info https://www.yoursite.com/company 
Products https://www.yoursite.com/products 
FAQs regexp ^.*/faqs 
Support https://www.yoursite.com/email_support/ 
Support https://www.yoursite.com/phone_support/
```

I det här exemplet kan kunderna välja och söka i varje definierad samling individuellt när du har uppdaterat sökformuläret så att det innehåller dessa samlingar. Samlingen `Support` innehåller filer som matchar båda URL-maskerna, så att filer i både `www.yoursite.com/email_support/` och `www.yoursite.com/phone_support` söks igenom när den här samlingen väljs.

## Lägger till samlingar {#task_07732D0F00104E59AD421297A704B2F6}

Du kan lägga till samlingar så att kunderna kan söka efter specifika delar av webbplatsen så att de snabbt kan hitta det de letar efter.

<!-- 

t_adding_collections.xml

 -->

Se till att du återskapar webbplatsindexet så att resultaten av dina URL-masker blir synliga för dina kunder.

Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).

**Lägga till samlingar**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Collections]** på produktmenyn.
1. I fältet [!DNL Collections] anger du ett samlingsnamn och en URL-maskadress, en per rad.
1. (Valfritt) På sidan [!DNL Collections] anger du en test-URL-mask från webbplatsen i fältet **[!UICONTROL Test Collections]** och klickar sedan på **[!UICONTROL Test]**.

   Ett testsamlingsfönster visas med URL:en och namnet på samlingen.
1. När du är klar med att lägga till samlingar klickar du på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Collections]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om begränsningar {#concept_B5B527E04EBF4E9AB5956EEF881DDBF1}

Innan en sökning utförs undersöks den refererande URL:en och IP-adressen för att avgöra om en sökning är möjlig från den platsen. Det du har angett i [!DNL Restrictions] avgör om sökningen är tillåten. Om en sökning inte tillåts returneras en allmän felsida till den som gjorde begäran.

<!-- 

c_about_restrictions.xml

 -->

Du kan ange begränsningsinställningar som antingen refererande URL-masker eller IP-adressmasker. Båda typerna av begränsningar använder masker för att tillåta sökningar och exkludera masker för att neka dem.

En sökning tillåts om den uppfyller villkoren för både referens-URL och IP-adressbegränsning. Om någon av inställningarna inte tillåter sökningen misslyckas sökningen, oavsett andra begränsningar som tillåter den.

Om t.ex. fältet &quot;HTTP-referent&quot; i en sökbegäran matchar en &quot;exclude&quot;-referens-URL-mask, misslyckas sökningen även om den begärande IP-adressen matchar en &quot;include&quot;-IP-adressmask. Om ingen mask matchar referentens URL eller IP-adress inkluderas platsen som standard.

Ange varje inkluderingsmask eller exkludera mask på en rad.

## Lägger till URL-mask för referenten eller IP-adressmask-begränsningar {#task_E6FF2DD83E8D4B00A0E2809DC13A56C9}

Du kan ange begränsningsinställningar som antingen &quot;Refererar-URL-masker&quot; eller &quot;IP-adressmasker&quot;. Båda typerna av begränsningar använder masker för att tillåta sökningar och exkludera masker för att neka dem. En sökning tillåts om den uppfyller villkoren för både referens-URL och IP-adressbegränsning.

<!-- 

t_adding_url_mask_or_jp_address_restrictions.xml

 -->

**Lägga till begränsningar för referentens URL-mask eller IP-adressmask**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]** på produktmenyn.
1. Ange önskade begränsningsalternativ på sidan [!DNL Restrictions]. Ange referens-URL-maskadresser, IP-adressmask-adresser eller, om så önskas, en URL-adress till en anpassad webbsida som visas för kunder som inte har behörighet att söka på din webbplats.

   <!-- 
   
   r_restriction_options.xml
   
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
      <td colname="col1"> <p>Refererande URL-masker </p> </td> 
      <td colname="col2"> <p>Referent-URL:en från HTTP-referensrubriken läses. Den första masken som matchar referenswebbadressen avgör om sökningen ska tillåtas, om masken är en inkluderingsmask. Det kan också avgöra om sökningen ska nekas, om masken är en exkluderingsmask. Om ingen mask matchar referenswebbadressen inkluderas den webbadressen och sökningen tillåts. </p> <p> Om sökmallen innehåller ett nytt sökformulär eller om sökmallen kan innehålla länkar som "Nästa 10", "Föregående 10" eller "Dölj sammanfattningar", listar du din sökresultatmall som en "inkludera"-mask. Det enklaste sättet att göra det är med det reguljära uttrycket som i följande exempel: </p> <p> <span class="codeph"> inkludera regexp ^https?://[^/]*\.atomz\.com/.*[?&amp;]sp_a=sp1000130e.*$ </span> </p> <p>Följande exempel innehåller fem olika URL-masker för referenter: </p> <p> <code> include&nbsp;https://www.mydomain.com/search/ 
          include&nbsp;https://search.mydomain.com/ 
          include&nbsp;regexp&nbsp;^https://www.mydomain.com/help/.*/search/ 
          include&nbsp;regexp&nbsp;^https?://[^/]*\.atomz\.com/.*[?&amp;]sp_a=sp1000130e.*$ 
          exclude&nbsp;* </code> </p> <p>Om referentens URL-masker är följande: </p> <p> <code> https://www.mydomain.com/search/searchpage.html&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://search.mydomain.com/advanced/&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://www.mydomain.com/help/products/search/advanced/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          https://www.mydomain.com/help/products/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          https://www.anotherdomain.com/&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          blank&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>IP-adressmasker </p> </td> 
      <td colname="col2"> <p>Den första masken som matchar IP-adressen avgör om sökningen ska tillåtas, om masken är en inkluderingsmask. Eller så avgör den om sökningen ska tillåtas eller inte om masken är en exkluderingsmask. Om ingen mask matchar den begärande IP-adressen inkluderas den IP-adressen och sökningen tillåts. </p> <p>I följande exempel visas fyra olika IP-adressmasker. </p> <p> <code> include&nbsp;64.128.192.* 
          include&nbsp;192.168. 
          include&nbsp;regexp&nbsp;^209\.42\.97\.[1-5]+ 
          exclude&nbsp;* </code> </p> <p>Om de refererande IP-adressmaskerna är följande: </p> <p> <code> 64.128.192.10&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          192.168.10.127&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          209.42.97.14&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;allowed] 
          64.128.193.10&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          192.169.10.14&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] 
          209.42.97.68&nbsp;&nbsp;&nbsp;&nbsp;[then&nbsp;search&nbsp;is&nbsp;disallowed] </code> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tillåt endast sökningar som använder HTTPS </p> </td> 
      <td colname="col2"> <p>Begränsa sökningar till HTTPS. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>URL som otillåtna begäranden ska skickas till </p> </td> 
      <td colname="col2"> <p> Begränsade användare omdirigeras till den URL som du anger här. Med det här alternativet kan du skapa en egen felsida som kan visas för kunder som inte har behörighet att söka på webbplatsen. </p> <p>Om du inte anger en URL returneras en allmän felsida när en begränsad användare försöker söka på webbplatsen. </p> </td> 
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

## Om Förhandsgranska {#concept_DF293FD3B02C467F8842C8C21D62F294}

Frågesträngen och parametrarna som du anger i [!DNL Preview] används när ett sökformulär testas eller förhandsgranskas i programmet.

<!-- 

c_about_preview.xml

 -->

Se även [Om sökningar](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

## Ange värden i förhandsvisningen {#task_CE267A0FF621474E80AB43B67B1C28D7}

De förhandsvisningsvärden du anger används när ett sökformulär testas eller förhandsgranskas i programmet.

<!-- 

t_setting_values_in_preview.xml

 -->

**Ange värden i förhandsvisningen**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Preview]** på produktmenyn.
1. Ange önskade alternativ på sidan [!DNL Preview].

   <!-- 
   
   r_preview_options.xml
   
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
      <td colname="col1"> <p>Fråga </p> </td> 
      <td colname="col2"> <p>Som standard är frågesträngen inställd på <span class="codeph"> * </span>, vilket vanligtvis returnerar resultat. Du kan dock ange en fråga som är mer specifik för webbplatsens innehåll. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Parametrar </p> </td> 
      <td colname="col2"> <p>Parametrar anges med ett namn och ett värde. Du kan ange så många ytterligare parametrar du behöver. Du kan till exempel ange ytterligare sökvillkor med parametrarna <span class="codeph"> sp_q_1 </span> och <span class="codeph"> sp_x_1 </span>. Parametervärdet <span class="codeph"> sp_q_1=windows&amp;sp_x_1=platform </span> skapar en förhandsvisningssökning som söker efter värdet "windows" i metataggen "platform" för sökda sidor, förutom huvudfrågan. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-parametrar för backend-sökning </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Värd </p> </td> 
      <td colname="col2"> <p>Om din webbplats använder etiketter för privata domäner anger du rätt värdnamn så att sökresultaten förhandsgranskas korrekt. </p> <p>Kontakta kundsupport om du vill ha information om märkning av privata domäner. </p> </td> 
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

## Om feeds {#concept_FEBFEE51A3AB49F88CBA0D16E2AD6916}

Sökindexet visas som en stor databas på webbplatsen. Med tillräcklig information från rätt metataggar samlas information in och organiseras, eller syndikeras, till dataflöden. Du kan skicka dessa dataflöden till en annan tjänst, t.ex. en tredjepartsmottagare.

<!-- 

c_about_feeds.xml

 -->

När webbplatsen har crawlats och indexerats kan du generera automatiska flöden och skicka dem till organiska sökmotorer och shoppingmotorer från tredje part. Du kan skapa följande strömflöden:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Feed-typ </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Recommendations </p> </td> 
   <td colname="col2"> <p>Recommendations feeds erbjuder datasyndikeringsfunktioner med Adobe Recommendations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Allmän feed </p> </td> 
   <td colname="col2"> <p>Du kan implementera många feeds med typen Allmän feed. En anpassad sökfråga görs mot webbplatsens index. Data returneras via anpassade sökmallar som använder samma mallspråk för att visa sökresultat. Den här typen av flexibilitet innebär att du kan skicka feeds till många fler leverantörer, inte bara till specifika flödestyper. </p> <p>Du kan lägga till transportmallen (sökmallen) genom att använda instruktionerna i följande hjälpavsnitt: </p> <p>Se <a href="../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012" type="task" format="dita" scope="local"> Lägga till en ny presentations- eller transportmallfil </a>. </p> <p> När du har lagt till mallen kan du redigera den med hjälp av sökmallstaggar för att definiera vilka sökmetadatafält som du vill inkludera, tillsammans med deras format. </p> <p>Se <a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local"> Redigera en presentation eller en transportmall </a>. </p> <p>Se <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Sökmallstaggar </a>. </p> <p>Kom ihåg namnet på transportmallfilen. Du använder namnet för att binda den generiska feeden till mallen när du anger feeds villkor. </p> <p>Om du har arbetat med andra feeds tidigare kommer du ihåg att du mappar feedsfälten till metadatafälten för sökning. Generiska feeds har inte det här specifika steget i guiden <span class="uicontrol"> Skapa feed </span>. I stället anger mallen metadata och formatering för metadata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Merchant </p> </td> 
   <td colname="col2"> <p>Med Google Merchant Center kan man sälja produkter via flera Google-tjänster. Den har en datakomponent där du kan skicka in en lista över tillgängliga produkter som kan säljas regelbundet. </p> <p>Liksom alla andra leverantörer av feed-tjänster från tredje part har Google Merchant Center specifika standarder som du uppfyller innan de anser att feed-legitimiteten är lagenlig. Mer information får du om du kontaktar din kundrepresentant och går till Google Merchant-dokumentationen. Här följer en kort sammanfattning av vad Google Merchant Center anser när en feed valideras: </p> 
    <ul id="ul_3D84D4A6A4BF4C08860F86403F8F9CD6"> 
     <li id="li_5B6516CC7BC7493B8B8E8AFB454E573F">Varje produkt har en produktsida; en dedikerad URL. </li> 
     <li id="li_5A6D5AD5E1B54A94B224D19E888B5443"> Varje produktvariant har en separat post i fodret. </li> 
     <li id="li_89748D3241B34A4493576DAC38681988"> Varje produkt har en bild-URL, helst från servern. Produktvarianter har specifika bilder som visar de faktiska variationerna. Olika skofärger bör alltså inte ha samma bild. </li> 
     <li id="li_A594AD19480F41EAA72181355F28447B"> Varje produkt har specifik information som tillgänglighet, villkor, beskrivning, kategori och pris. </li> 
     <li id="li_0955B3A6ED2746D2B7CB42DC8AB27D3A">I allmänhet har varje produkt en unik identifierare som ISBN, UPC, JAN eller EAN osv. </li> 
     <li id="li_2C371653F1C5471FA638F3A3818ABC17">I allmänhet klassificeras varje produkt enligt Googles produkttaxonomi. </li> 
     <li id="li_6EB392A5A0BE490FAED5BC5E83228E32"> Apparatprodukter har extra obligatoriska fält som kön, åldersgrupp, färg och storlek. </li> 
     <li id="li_44B91FA9A95F4172A2F03F8206E9081E"> Skatt och frakt anges som kontoinställning i Google Merchant Center eller på produktbasis, inom denna feed. </li> 
     <li id="li_71A63E9905B840C0A04F6CDAA23C9AB0"> Anpassade produkter och vissa kläder kan undantas från vissa av reglerna, men du måste kontakta Google för att få tillstånd och information om sådana undantag. </li> 
    </ul> <p>Det finns många detaljer som styr feedvalidering. Mer information om flödeshantering finns i dokumentationen för Google Merchant. Google ändrar ofta specifikationerna, så kontrollera dokumentationen ofta. </p> <p>Den feed som är kopplad till Google Merchant Center kallas ofta för Googles produktsökningsfeed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Sitemaps </p> </td> 
   <td colname="col2"> <p>Med Google Sitemaps kan du påverka hur Google crawlar din webbplats. En syndikerad datafeed, en platskarta i det här fallet, skickas regelbundet till Google Sitemaps. Platskartan innehåller URL:er som kan nås via Internet och specifik information, som senaste ändringsdatum eller sidprioritet, kan kopplas till varje URL. Om du förser Google med sådan information kan det göra att en viss sida kraschar och indexeras. I vissa fall används en platskarta för att annonsera en lista över länkar som inte kan nås av crawlern under normala förhållanden. </p> <p>Om du är intresserad av att skapa en Google Sitemap med vår feed-funktion kontaktar du din kundrepresentant. Google har gjort sin Google Sitemap-tjänst tillgänglig för allmänheten och de tillhandahåller dokumentation på sin Google Webmaster Tools-sida. </p> <p> <b>Krav för att skapa en Google Sitemap-feed</b> </p> <p>Om du vill skapa en Google Sitemap-feed måste du kontrollera att du har ett Google Webmaster Tools-konto med Google Sitemap som redan har konfigurerats. Se dokumentationen för Google Webmaster Tools för att konfigurera Google SiteMap. </p> <p>Du måste också bestämma hur platskartefilerna ska levereras. I allmänhet kommer platskartefilerna från din domän och, närmare bestämt, roten på din webbplats. Den enkla modellen är att få filerna levererade via FTP till dina servrar. Den andra lösningen är att dirigera om begäran om webbplatskartor till webbplatsens söknings-/säljnätverk. Kontakta din konsultrepresentant för att samordna och konfigurera leveransen av webbplatskartor. </p> </td> 
  </tr> 
 </tbody> 
</table>

Om du är intresserad av automatiska feeds kan du kontakta professionella tjänster för att få hjälp. Varje feed har strikta krav när det gäller kvaliteten på data och överföringen av filerna.

Den feed-typ du väljer påverkar vilka alternativ som visas när du skapar ett fält med hjälp av guiden **[!UICONTROL Create Feed]**. Varje matningstyp har olika dataformat. Se till att du följer rätt dataformat för att undvika att en feed-mottagare refuserar eller skickar felaktiga data till dina kunder. Förutom dataformatet har leverantörerna vanligtvis ett eller flera sätt att ta emot data. Läs leverantörens dokumentation om deras feeds.

En utmaning med att skapa en feed är att matcha data mellan webbplatssökning/försäljning och flödet. Vanligtvis är data som hämtas från indexcrawlning i fel format eller så saknas de. Nedan följer en lista med frågor som kan hjälpa dig att fokusera på vad du ska leta efter när du skapar en feed.

* Vilken typ av affärsrelation har du med feed-mottagaren?
* Måste du registrera och skapa ett konto hos feed-mottagaren?
* Vem ska övervaka och ta hand om frågor som uppstår i samband med maten med avseende på leverantören? I allmänhet är det ditt ansvar att hantera leverantörens konto. Google Sitemap kräver till exempel ett WebMaster-konto och någon som kan övervaka webbplatskartans hälsa.
* Vilket dataformat har matningen?
* Matchar indexvärdet matningens teckenkodning? Tabbavgränsade och kommaavgränsade dataformat blir problem när data har tabbar eller kommatecken.
* Vad gör du när du har tabbar eller kommatecken i dina data?
* Finns det några sidor i indexet med tomma data?
* Kan matningsmottagaren acceptera tomma data? Du kanske kan lösa tomma data genom att redigera villkoren för hur data hämtas av programmet.
* Sammanfogar dataformatet med det som feed-mottagaren vill ha? En del mottagare är till exempel specifika för hur priser och valutor visas.
* Har leverantören ett maximalt antal artiklar som de kan acceptera? Du kan lösa det här potentiella problemet genom att begränsa resultaten med sökvillkoren.
* Hur vill leverantören ta emot feeden? FTP-överföringar och HTTP-värdtjänster stöds.

## Skapa en feed {#task_63179C1FC359497483CD6CE13FD1C250}

Du kan skapa en eller flera dataflöden.

<!-- 

t_creating_a_feed.xml

 -->

**Skapa en feed**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** på produktmenyn.
1. Välj en flödestyp i listrutan **[!UICONTROL Create Feed]** på sidan [!DNL Feeds].
1. Beroende på vilken flödestyp du valde kan du i dialogrutan [!DNL Create Feed] ange de alternativ som identifieras på varje panel i guiden.

   <!-- 
   
   r_feed_options.xml
   
   -->

   Beroende på vilken flödestyp du skapar eller redigerar kan de tillgängliga alternativen skilja sig något.

   **Adobe Recommendations**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Panel </p> </th> 
      <th colname="col2" class="entry"> <p>Panelnamn för guide </p> </th> 
      <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Feednamn </p> </td> 
      <td colname="col3"> <p>Anger feed-namnet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>Fältkartor </p> </td> 
      <td colname="col3"> <p>Gör att du kan mappa leverantörsspecifika matningsfält till webbplatssöknings-/försäljningsmetadatafält. Det här mappningssteget i guiden är viktigt eftersom det gör att feeds kan korrelera informationen mellan fälten i indexet och fälten i feed-data. I de flesta fall, med undantag för <span class="wintitle"> generiska feeds </span>, sparas korrelationerna i en dynamiskt genererad sökmall. </p> <p>Varje rad i tabellen <span class="wintitle"> Fältkartor </span> representerar en fältmappning. Klicka på <span class="uicontrol"> + </span> i kolumnen Lägg till/ta bort för att lägga till en ny fältmappningsrad. klicka på <span class="uicontrol"> - </span> för att ta bort den markerade fältmappningsraden från tabellen. Om du vill associera ett matningsfält med ett söknings-/försäljningsmetadatafält för en webbplats använder du respektive listruta för att välja önskade fält. </p> <p> <b>Fältmappningar för Adobe Recommendations</b> </p> <p>Rekommendationsdataflödet är en CSV-fil, datakolumner avgränsade med kommatecken. Utseendeordningen för varje mappning i tabellen Fältkartor är viktig när de bestämmer ordningen på kolumnerna i CSV-flödesfilen. Skapa mappningsraderna i följande ordning - varje rad är obligatorisk: </p> <p> 
        <ol id="ol_49C739D04DD340168DC6C1F794544C35"> 
          <li id="li_A95D9C5A353746A3A0D38F200AC2EEA2"> id </li> 
          <li id="li_044763D4C7054CEB948C94590735D74F"> name </li> 
          <li id="li_832F07CA0E3F4E10A4AE30171F3E8541"> categoryId </li> 
          <li id="li_2A33FB42F7E942ED881BA1F478542C4D"> message </li> 
          <li id="li_A76E66B2366845B0B63ED5C200531ADD"> thumbnailURL </li> 
          <li id="li_518CCD5E7E404521AB8199981BA86F76"> value </li> 
          <li id="li_14A0A8FCC2B34B758E1FBB98E3F2DFB2"> pageURL </li> 
          <li id="li_36D22F1603394AF89E0C7ADB18AAAAB7"> lager </li> 
          <li id="li_ABDB9C762BBC4F27B82FEA4425A8DDC4"> marginal </li> 
        </ol> </p> <p> <b>Avancerad användning</b> </p> <p>När du har mappat de första nio obligatoriska flödesfälten enligt ovan kan du skapa egna anpassade fält. I listrutan <span class="wintitle"> Feed Fields </span> klickar du på <span class="uicontrol"> Custom </span>. Ange ett eget taggnamn för fältet i det tillhörande textfältet. Det här anpassade alternativet är användbart om en feed behöver speciella leverantörsspecifika fält. </p> <p> <p>Obs!  Även om det i specifikationerna för rekommendationsfeed anges att varje fältnamn måste föregås av "entitet" är det inte nödvändigt i det här fallet. </p> </p> <p>Du kan också skapa ett anpassat metadatafält. I listrutan <span class="wintitle"> Metadatafält </span> klickar du på <span class="uicontrol"> Anpassad </span>. I det associerade textfältet anger du ett anpassat metadatafältvärde. Värdet infogas i den förgenererade mallen och kan även användas för att mata in egna sökmallstaggar. </p> <p>Se <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Sökmallstaggar </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>1 </p> </td> 
      <td colname="col2"> <p>Sökvillkor </p> </td> 
      <td colname="col3"> <p>När matningsfilerna genereras används en sökfråga för att filtrera data. Du definierar de filter som används för sökfrågan på den här panelen. </p> 
        <ul id="ul_799ECF61C03A44878C7182F8B88CC3AD"> 
        <li id="li_0763F600A4FB4650ACC28BF337EB50AF"> <span class="uicontrol"> Meta Field  </span> <p>Definierar vilket metadatafält som du vill filtrera på. </p> <p> <b>Avancerad användning</b> </p> <p>Eftersom filtreringssystemet är en standardsökfråga kan du välja <span class="uicontrol"> Free Form </span> i listrutan och ange CGI-sökparametrar och deras värden. URL-escape krävs. Sökargumentet <span class="codeph"> sp_q </span> ignoreras. Du kan skapa flera rader med textrutor med kostnadsfria formulär. Mellan varje rad avgränsas argumenten automatiskt med &amp;:er. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Söka efter CGI-parametrar </a>. </p> </li> 
        <li id="li_756B776902AE4A0E95524442D663343E"> <span class="uicontrol"> Kriterier  </span> <p>Definierar filteråtgärden. Filteråtgärden som du väljer i listrutan använder det konstanta värde som anges i den tredje kolumnen. </p> </li> 
        <li id="li_7ADEDB8747B241D78AC50F1AC75AE695"> <span class="uicontrol"> Värde  </span> <p>Konstantvärdet. </p> </li> 
        <li id="li_4039A9BC2F74460B83BFF662B58DAA1B"> <span class="uicontrol"> Åtgärd  </span> <p>Lägger till en ny fältmappningsrad eller tar bort den markerade raden. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>Filöverföring </p> </td> 
      <td colname="col3"> <p>Gör att du kan konfigurera schemat för att skicka feed-filerna och ange den metod som du vill använda för att överföra filerna. </p> 
        <ul id="ul_55E253F83BDA46BAABF2BE38F0918E80"> 
        <li id="li_877A376B5B30422FAC816E31D50EA508"> <span class="uicontrol"> Schema  </span> <p>Anger den maximala frekvens som en feed skickas. Om du väljer <span class="uicontrol"> Aldrig </span> inaktiveras feeden. Andra värden definierar den period som flödet väntar innan det skickas igen. Beslutet om när feeden ska skickas görs vid varje index. Med andra ord, i slutet av indexet kontrolleras en feed för att se om den har gått ut och måste uppdateras och skickas av leverantören. Den används också som ett sätt att förhindra att ett konto överför till en leverantör. Vissa leverantörer har policyer mot datakällor som överförs för ofta. Kontrollera att du kontrollerar dataflödets leverantörspolicy om hur ofta du skickar in data. 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> 
          <!--ick <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_760F5068D3ED46C582AE41392A2CA342"> <span class="uicontrol"> Överföringsmetod  </span> <p>De flesta flöden har två sätt att distribuera filerna: FTP och nätverket för värdbaserat innehåll. </p> 
          <ul id="ul_666759EDDD034537AA7C0ED936A2F315"> 
          <li id="li_B4AD5CEEBB7B41C0B8DC291B95DC5F83"> <span class="uicontrol"> FTP  </span> <p>Webbplatssöknings-/försäljningsservrar använder passiv FTP. </p> <p>FTP är det enda sättet att skicka en fil till en annan server. </p> <p> <span class="uicontrol"> FTP-server  </span> - Anger namnet på FTP-servern. Inkludera inte protokollet eller föregående "ftp://". </p> <p> <span class="uicontrol"> FTP-användarnamn  </span> - Anger namnet på FTP-kontot. </p> <p> <span class="uicontrol"> FTP-lösenord  </span> - Anger lösenordet för FTP-kontot. </p> <p> <span class="uicontrol"> FTP-filnamn  </span> - Anger namnet på filen som ska överföras. Det här namnet är en mall om feeden genererar flera filer, vanligtvis med ett nummer i slutet av namnet men före filnamnstillägget. Till exempel: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> FTP-katalog  </span> - Om en viss katalogsökväg krävs anger du den här. Ta inte med filnamnet i sökvägen. </p> </li> 
          <li id="li_C082D3993C6C469B9067F207703BE619"> <span class="uicontrol"> Nätverk av värdbaserat innehåll  </span> <p>Innehållsnätverket är ett sätt att hantera filer från webbservrar för webbplatssökning/försäljning. Mottagaren av feeden hämtar den från webbservrarna med en HTTP-begäran. Den enda informationen som ska anges är <span class="uicontrol"> Content Network Filename </span>. Filnamnet är basnamnet på filen som skickas. Använd endast filnamn med filnamnstillägg. Beroende på matningen är filnamnet en mall för flera filer där matningen kan generera flera filer i följande format: basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml. </p> <p>När basfilnamnet har angetts och flödet har sparats visas URL:en för Content Network-filen på verifieringspanelen i guiden. URL:en blir aktiv när feeden har bearbetats. Leverantören kan hämta feed-data från den här URL:en. Flera filer använder samma URL-sökväg. Se dock till att du ersätter eller ändrar filnamnet enligt uppräkningsschemat. </p> </li> 
          </ul> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>Verifiering </p> </td> 
      <td colname="col3"> <p>När du kommer till panelen <span class="wintitle"> Verifiering </span> sparas din feed då. De faktiska feedfilerna sparas dock inte förrän senare. </p> <p>På panelen <span class="wintitle"> Verifiering </span> kan du göra följande: </p> 
        <ul id="ul_0C6EFB38E06F401696084863D85CBD0D"> 
        <li id="li_07FC9F04C7F640048546F9DC5D91DA1D"> <span class="uicontrol"> Datavy  </span> <p>Gör att du kan klicka på länken för att kontrollera matningsutdata via en datavy som visas i tabellformulär. Datavyn kan även hjälpa dig att felsöka genom att visa vilka metafält som har valts och hur eventuella angivna sökvillkor från panelen <span class="wintitle"> Sökvillkor </span> i guiden påverkar feed-utdata. Datavyn genereras dynamiskt, så den är alltid tillgänglig. </p> </li> 
        <li id="li_67046A56D08C48298E5A3E1F9C4A8AF3"> <span class="uicontrol"> Feed-filer  </span> <p>När servrar för sökning/försäljning av webbplatser har genererat feed-filerna kan du använda listrutan <span class="uicontrol"> Feed Files </span> för att visa filerna från servrarna. En ny webbläsarflik eller ett nytt webbläsarfönster visas med innehållet i feeden. Den här metoden är användbar när du vill felsöka feeds som har formateringsproblem. Observera att du inte visar filerna från slutmålet eller från leverantörerna själva. </p> <p> Om flödet är nytt är listrutan tom tills du genererar feed-filer. </p> </li> 
        <li id="li_99D66C7AD87A475CB3D831D514DB78A0"> <span class="uicontrol"> Länk till innehållsnätverk  </span> <p>Om du väljer <span class="uicontrol"> Hosted Content Network </span> som överföringsmetod i panelen <span class="wintitle"> File Submission </span> i guiden visas URL:en här. Om du ännu inte har genererat några feed-filer är URL:en inte giltig förrän feeden har genererats. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **Allmän feed**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Panel </p> </th> 
      <th colname="col2" class="entry"> <p>Panelnamn för guide </p> </th> 
      <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Feednamn </p> </td> 
      <td colname="col3"> <p>Anger feed-namnet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>Sökvillkor </p> </td> 
      <td colname="col3"> <p>När matningsfilerna genereras används en sökfråga för att filtrera data. Du definierar de filter som används för sökfrågan på den här panelen. </p> 
        <ul id="ul_C750687E69A647D0A4440FF1B6CC7E05"> 
        <li id="li_B5C3B8523D71472E9508A04E23AC0211"> <span class="uicontrol"> Meta Field  </span> <p>Definierar vilket metadatafält som du vill filtrera på. </p> <p> <b>Avancerad användning</b> </p> <p>Eftersom filtreringssystemet är en standardsökfråga kan du välja <span class="uicontrol"> Free Form </span> i listrutan och ange CGI-sökparametrar och deras värden. URL-escape krävs. Sökargumentet <span class="codeph"> sp_q </span> ignoreras. Du kan skapa flera rader med textrutor med kostnadsfria formulär. Mellan varje rad avgränsas argumenten automatiskt med &amp;:er. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Söka efter CGI-parametrar </a>. </p> </li> 
        <li id="li_D1E49834BBEA42CC8C49AE7D72037C53"> <span class="uicontrol"> Kriterier  </span> <p>Definierar filteråtgärden. Filteråtgärden som du väljer i listrutan använder det konstanta värde som anges i den tredje kolumnen. </p> </li> 
        <li id="li_D5F0651B834F4EACAD15A2D154A0737B"> <span class="uicontrol"> Värde  </span> <p>Konstantvärdet. </p> </li> 
        <li id="li_FC8F382BD20C4518BC2230D4B4954591"> <span class="uicontrol"> Åtgärd  </span> <p>Lägger till en ny fältmappningsrad eller tar bort den markerade raden. </p> </li> 
        </ul> <p>Allmänna feeds måste ha en särskild CGI-parameter angiven. Om du vill binda den särskilda mall som är associerad med denna feed definierar du parametern <span class="codeph"> sp_t </span>. Ange värdet <span class="codeph"> sp_t </span> till namnet på transportmallfilen. Om du till exempel har lagt till en transportmallfil med namnet <span class="codeph"> super_feed.tpl </span> skapar du en anpassad CGI-sökparameter som <span class="codeph"> sp_t=super_feed </span>. Textrutan där du anger <span class="codeph"> sp_t </span> visas inte förrän du väljer <span class="uicontrol"> Free Form </span> i listrutan <span class="wintitle"> Metafält </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>1 </p> </td> 
      <td colname="col2"> <p>Filöverföring </p> </td> 
      <td colname="col3"> <p>Gör att du kan konfigurera schemat för att skicka feed-filerna och ange den metod som du vill använda för att överföra filerna. </p> 
        <ul id="ul_30E830C41F6A4526822AF1FD3083075A"> 
        <li id="li_79EAFDBD2B9F411EA985CAEC1BAF3926"> <span class="uicontrol"> Schema  </span> <p>Anger den maximala frekvens som en feed skickas. Om du väljer <span class="uicontrol"> Aldrig </span> inaktiveras feeden. Andra värden definierar den period som flödet väntar innan det skickas igen. Beslutet om när feeden ska skickas görs vid varje index. Med andra ord, i slutet av indexet kontrolleras en feed för att se om den har gått ut och måste uppdateras och skickas av leverantören. Den används också som ett sätt att förhindra att ett konto överför till en leverantör. Vissa leverantörer har policyer mot datakällor som överförs för ofta. Kontrollera att du kontrollerar feedleverantörens policy för hur ofta svar skickas in. 
          <!--he time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> 
          <!--<uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_20BF70A19E7E45BA91CD972E2FCE0EA4"> <span class="uicontrol"> Överföringsmetod  </span> <p>De flesta flöden har två sätt att distribuera filerna: FTP och nätverket för värdbaserat innehåll. </p> 
          <ul id="ul_5888C2E9097645CE89938EE09F8CB4F1"> 
          <li id="li_EA9ED19F3BEA4BEAB1A9F2C2FAFF85F7"> <span class="uicontrol"> FTP  </span> <p>Webbplatssöknings-/försäljningsservrar använder passiv FTP. </p> <p>FTP är det enda sättet att skicka en fil till en annan server. </p> <p> <span class="uicontrol"> FTP-server  </span> - Anger namnet på FTP-servern. Inkludera inte protokollet eller föregående "ftp://". </p> <p> <span class="uicontrol"> FTP-användarnamn  </span> - Anger namnet på FTP-kontot. </p> <p> <span class="uicontrol"> FTP-lösenord  </span> - Anger lösenordet för FTP-kontot. </p> <p> <span class="uicontrol"> FTP-filnamn  </span> - Anger namnet på filen som ska överföras. Det här namnet är en mall om feeden genererar flera filer, vanligtvis med ett nummer i slutet av namnet men före filnamnstillägget. Till exempel: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> FTP-katalog  </span> - Om en viss katalogsökväg krävs anger du den här. Ta inte med filnamnet i sökvägen. </p> </li> 
          <li id="li_181268A7EE40456CA1DB768E8C66EEB9"> <span class="uicontrol"> Nätverk av värdbaserat innehåll  </span> <p>Det värdbaserade innehållsnätverket är ett sätt att hantera filer från webbservrarna för webbplatssökning/försäljning. Mottagaren av feeden hämtar den från webbservrarna med en HTTP-begäran. Den enda informationen som ska anges är <span class="uicontrol"> Content Network Filename </span>. Filnamnet är basnamnet på filen som skickas. Använd endast filnamn med filnamnstillägg. 
            <!--Depending on the feed, the file name is a template for multiple files where the feed might generate multiple files in the following format: basename.xml, basename1.xml, basename2.xml, ..., basename-Nth.xml. --> </p> <p>När basfilnamnet har angetts och flödet har sparats visas URL:en för Content Network-filen på verifieringspanelen i guiden. URL:en blir aktiv när feeden har bearbetats. Leverantören kan hämta feed-data från den här URL:en. </p> </li> 
          </ul> </li> 
        <li id="li_4DF56FA607A7479296CDA042A63C5A2C"> <p> <b>Bevara flikar?</b> </p> <p>Behåll tabbtecken i feeden. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>Verifiering </p> </td> 
      <td colname="col3"> <p>När du kommer till panelen <span class="wintitle"> Verifiering </span> sparas din feed då. De faktiska feedfilerna sparas dock inte förrän senare. </p> <p>På panelen <span class="wintitle"> Verifiering </span> kan du göra följande: </p> 
        <ul id="ul_7420C415987448A796DD979CF5FA2EB6"> 
        <li id="li_AF02E8609B7B4F20A01AF4E010308E15"> <span class="uicontrol"> Datavy  </span> <p>Gör att du kan klicka på länken för att kontrollera matningsutdata via en datavy som visas i tabellformulär. Datavyn kan även hjälpa dig att felsöka genom att visa vilka metafält som har valts och hur eventuella angivna sökvillkor från panelen <span class="wintitle"> Sökvillkor </span> i guiden påverkar feed-utdata. Datavyn genereras dynamiskt, så den är alltid tillgänglig. </p> </li> 
        <li id="li_32CEB8885C184354BFA1773BA66DB7A7"> <span class="uicontrol"> Feed-filer  </span> <p>När servrar för sökning/försäljning av webbplatser har genererat feed-filerna kan du använda listrutan <span class="uicontrol"> Feed Files </span> för att visa filerna från servrarna. En ny webbläsarflik eller ett nytt webbläsarfönster visas med innehållet i feeden. Den här metoden är användbar när du vill felsöka feeds som har formateringsproblem. Observera att du inte visar filerna från slutmålet eller från leverantörerna själva. </p> <p> Om flödet är nytt är listrutan tom tills du genererar feed-filer. </p> </li> 
        <li id="li_8D1B876B0EC2455C8654EC573EC53FA9"> <span class="uicontrol"> Länk till innehållsnätverk  </span> <p>Om du väljer <span class="uicontrol"> Hosted Content Network </span> som överföringsmetod i panelen <span class="wintitle"> File Submission </span> i guiden visas URL:en här. Om du ännu inte har genererat några feed-filer är URL:en inte giltig förrän feeden har genererats. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **Google Merchant Center**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Panel </p> </th> 
      <th colname="col2" class="entry"> <p>Panelnamn för guide </p> </th> 
      <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Feednamn </p> </td> 
      <td colname="col3"> <p>Anger feed-namnet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>Fältkartor </p> </td> 
      <td colname="col3"> <p>Gör att du kan mappa leverantörsspecifika matningsfält till webbplatssöknings-/försäljningsmetadatafält. Det här mappningssteget i guiden är viktigt eftersom det gör att feeds kan korrelera informationen mellan fälten i indexet och fälten i feed-data. I de flesta fall, med undantag för <span class="wintitle"> generiska feeds </span>, sparas korrelationerna i en dynamiskt genererad sökmall. </p> <p>Varje rad i tabellen Fältkartor representerar en fältkoppling. I kolumnen <span class="wintitle"> Lägg till/ta bort </span> i tabellen klickar du på <span class="uicontrol"> + </span> för att lägga till en ny fältmappningsrad. klicka på <span class="uicontrol"> - </span> för att ta bort den markerade fältmappningsraden från tabellen. Om du vill associera ett matningsfält med ett söknings-/försäljningsmetadatafält för en webbplats använder du respektive listruta för att välja önskade fält. </p> <p> <b>Avancerad användning</b> </p> <p>Du kan skapa egna anpassade fält. I listrutan <span class="wintitle"> Feed Fields </span> klickar du på <span class="uicontrol"> Custom </span>. Ange ett eget taggnamn för fältet i det tillhörande textfältet. Det här anpassade alternativet är användbart om en feed behöver speciella leverantörsspecifika fält. </p> <p>Du kan också skapa ett anpassat metadatafält. I listrutan <span class="wintitle"> Metadatafält </span> klickar du på <span class="uicontrol"> Anpassad </span>. I det associerade textfältet anger du ett anpassat metadatafältvärde. Värdet infogas i den förgenererade mallen och kan även användas för att mata in egna sökmallstaggar. </p> <p>Se <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Sökmallstaggar </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Sökvillkor </p> </td> 
      <td colname="col3"> <p>När matningsfilerna genereras används en sökfråga för att filtrera data. Du definierar de filter som används för sökfrågan på den här panelen. </p> 
        <ul id="ul_8179321A58BB4C72B0CDB2B2BEC58FE4"> 
        <li id="li_9F8008A2398A4667B106BC49C94E5E3E"> <span class="uicontrol"> Meta Field  </span> <p>Definierar vilket metadatafält som du vill filtrera på. </p> <p> <b>Avancerad användning</b> </p> <p>Eftersom filtreringssystemet är en standardsökfråga kan du välja <span class="uicontrol"> Free Form </span> i listrutan och ange CGI-sökparametrar och deras värden. URL-escape krävs. Sökargumentet <span class="codeph"> sp_q </span> ignoreras. Du kan skapa flera rader med textrutor med kostnadsfria formulär. Mellan varje rad avgränsas argumenten automatiskt med &amp;:er. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Söka efter CGI-parametrar </a>. </p> </li> 
        <li id="li_50C9CE59E9E5418895F8C1A070560063"> <span class="uicontrol"> Kriterier  </span> <p>Definierar filteråtgärden. Filteråtgärden som du väljer i listrutan använder det konstanta värde som anges i den tredje kolumnen. </p> </li> 
        <li id="li_9F86D0F5010046A4A9F93DBA5FB158B3"> <span class="uicontrol"> Värde  </span> <p>Konstantvärdet. </p> </li> 
        <li id="li_1051AFD5AEA447D0AF5FAB305E1D1E64"> <span class="uicontrol"> Åtgärd  </span> <p>Lägger till en ny fältmappningsrad eller tar bort den markerade raden. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>Filöverföring </p> </td> 
      <td colname="col3"> <p>Gör att du kan konfigurera schemat för att skicka feed-filerna och ange den metod som du vill använda för att överföra filerna. </p> 
        <ul id="ul_A6A3C333AADD4438B835BF3E16E2AEFF"> 
        <li id="li_FCC4DAF198E149278B5CFB870CB6218C"> <span class="uicontrol"> Schema  </span> <p>Anger den maximala frekvens som en feed skickas. Om du väljer <span class="uicontrol"> Aldrig </span> inaktiveras feeden. Andra värden definierar den period som flödet väntar innan det skickas igen. Beslutet om när feeden ska skickas görs vid varje index. Med andra ord, i slutet av indexet kontrolleras en feed för att se om den har gått ut och måste uppdateras och skickas av leverantören. Den används också som ett sätt att förhindra att ett konto överför till en leverantör. Vissa leverantörer har policyer mot datakällor som överförs för ofta. Kontrollera att du kontrollerar feedleverantörens policy för hur ofta svar skickas in. </p> <p> 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> </p> <p> 
          <!--Click <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_2D9ECAFB8E8544D39B486F7BC3DCE589"> <span class="uicontrol"> Överföringsmetod  </span> <p>De flesta flöden har två sätt att distribuera filerna: FTP och nätverket för värdbaserat innehåll. </p> <p>Den rekommenderade överföringsmetoden för att skicka datafeeden är <span class="uicontrol"> FTP </span>. Google Merchant Center är värd för en FTP-server för detta. Se hjälpen för Google Merchant Center om hur du skapar ett separat Google FTP-konto för detta Google Product Search-flöde. </p> 
          <ul id="ul_BC0D8B541068407883CAC948496DBD0A"> 
          <li id="li_DB28CA23C94A4AF09E1A0EB06DF8F40C"> <span class="uicontrol"> FTP  </span> <p>Webbplatssöknings-/försäljningsservrar använder passiv FTP. </p> <p>FTP är det enda sättet att skicka en fil till en annan server. </p> <p> <span class="uicontrol"> FTP-server  </span> - Anger namnet på FTP-servern. I det här fallet är det 
            <code>
              uploads.google.com 
            </code>. Inkludera inte protokollet eller föregående "ftp://". </p> <p> <span class="uicontrol"> FTP-användarnamn  </span> - Anger namnet på FTP-kontot. </p> <p> <span class="uicontrol"> FTP-lösenord  </span> - Anger lösenordet för FTP-kontot. </p> <p> <span class="uicontrol"> FTP-filnamn  </span> - Anger namnet på filen som ska överföras. Det här namnet är en mall om feeden genererar flera filer, vanligtvis med ett nummer i slutet av namnet men före filnamnstillägget. Till exempel: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> FTP-katalog  </span> - Om en viss katalogsökväg krävs anger du den här. Ta inte med filnamnet i sökvägen. </p> </li> 
          <li id="li_5990927146434DAF89273F4636D21437"> <span class="uicontrol"> Nätverk av värdbaserat innehåll  </span> <p>Innehållsnätverket är ett sätt att hantera filer från webbservrar för webbplatssökning/försäljning. Mottagaren av feeden hämtar den från webbservrarna med en HTTP-begäran. </p> <p> 
            <!--After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. --> </p> </li> 
          </ul> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>Verifiering </p> </td> 
      <td colname="col3"> <p>När du kommer till panelen <span class="wintitle"> Verifiering </span> sparas din feed då. De faktiska feedfilerna sparas dock inte förrän senare. </p> <p>På panelen <span class="wintitle"> Verifiering </span> kan du göra följande: </p> 
        <ul id="ul_4A94355A8DF840A3BAF6BD5E9F11C27F"> 
        <li id="li_825697CB36B34C4AB5959B15EDDB55F1"> <span class="uicontrol"> Datavy  </span> <p>Gör att du kan klicka på länken för att kontrollera matningsutdata via en datavy som visas i tabellformulär. Datavyn kan även hjälpa dig att felsöka genom att visa vilka metafält som har valts och hur eventuella angivna sökvillkor från panelen <span class="wintitle"> Sökvillkor </span> i guiden påverkar feed-utdata. Datavyn genereras dynamiskt, så den är alltid tillgänglig. </p> </li> 
        <li id="li_91B8B5F5F9DE4A13863CD62F74AA6206"> <span class="uicontrol"> Feed-filer  </span> <p>När servrar för sökning/försäljning av webbplatser har genererat feed-filerna kan du använda listrutan <span class="uicontrol"> Feed Files </span> för att visa filerna från servrarna. En ny webbläsarflik eller ett nytt webbläsarfönster visas med innehållet i feeden. Den här metoden är användbar när du vill felsöka feeds som har formateringsproblem. Observera att du inte visar filerna från slutmålet eller från leverantörerna själva. </p> <p> Om flödet är nytt är listrutan tom tills du genererar feed-filer. </p> </li> 
        <li id="li_4A5EC089628E43029A38F8919888FF0A"> <span class="uicontrol"> Länk till innehållsnätverk  </span> <p>Om du väljer <span class="uicontrol"> Hosted Content Network </span> som överföringsmetod i panelen <span class="wintitle"> File Submission </span> i guiden visas URL:en här. Om du ännu inte har genererat några feed-filer är URL:en inte giltig förrän feeden har genererats. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

   **Google Sitemaps**

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Panel </p> </th> 
      <th colname="col2" class="entry"> <p>Panelnamn för guide </p> </th> 
      <th colname="col3" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>1 </p> </td> 
      <td colname="col2"> <p>Feednamn </p> </td> 
      <td colname="col3"> <p>Anger feed-namnet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>2 </p> </td> 
      <td colname="col2"> <p>Fältkartor </p> </td> 
      <td colname="col3"> <p>Gör att du kan mappa leverantörsspecifika matningsfält till webbplatssöknings-/försäljningsmetadatafält. Det här mappningssteget i guiden är viktigt eftersom det gör att feeds kan korrelera informationen mellan fälten i indexet och fälten i feed-data. I de flesta fall, med undantag för <span class="wintitle"> generiska feeds </span>, sparas korrelationerna i en dynamiskt genererad sökmall. </p> <p>Varje rad i tabellen Fältkartor representerar en fältkoppling. Klicka på <span class="uicontrol"> + </span> i kolumnen Lägg till/ta bort för att lägga till en ny fältmappningsrad. klicka på <span class="uicontrol"> - </span> för att ta bort den markerade fältmappningsraden från tabellen. Om du vill associera ett matningsfält med ett metadatafält använder du respektive listruta för att välja önskade fält. </p> <p> <b>Avancerad användning</b> </p> <p>Du kan skapa egna anpassade fält. I listrutan <span class="wintitle"> Feed Fields </span> klickar du på <span class="uicontrol"> Custom </span>. Ange ett eget taggnamn för fältet i det tillhörande textfältet. Det här anpassade alternativet är användbart om en feed behöver speciella leverantörsspecifika fält. </p> <p>Du kan också skapa ett anpassat metadatafält. I listrutan <span class="wintitle"> Metadatafält </span> klickar du på <span class="uicontrol"> Anpassad </span>. I det associerade textfältet anger du ett anpassat metadatafältvärde. Värdet infogas i den förgenererade mallen och kan även användas för att mata in egna sökmallstaggar. </p> <p>Se <a href="../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4" type="reference" format="dita" scope="local"> Sökmallstaggar </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>3 </p> </td> 
      <td colname="col2"> <p>Sökvillkor </p> </td> 
      <td colname="col3"> <p>När matningsfilerna genereras används en sökfråga för att filtrera data. Du definierar de filter som används för sökfrågan på den här panelen. </p> 
        <ul id="ul_994585E89A044BD3A89A99D30F277432"> 
        <li id="li_61FA9246B9824E3C8124958C8EBFF0DA"> <span class="uicontrol"> Meta Field  </span> <p>Definierar vilket metadatafält som du vill filtrera på. </p> <p> <b>Avancerad användning</b> </p> <p>Eftersom filtreringssystemet är en standardsökfråga kan du välja <span class="uicontrol"> Free Form </span> i listrutan och ange CGI-sökparametrar och deras värden. URL-escape krävs. Sökargumentet <span class="codeph"> sp_q </span> ignoreras. Du kan skapa flera rader med textrutor med kostnadsfria formulär. Mellan varje rad avgränsas argumenten automatiskt med &amp;:er. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890" type="reference" format="dita" scope="local"> Söka efter CGI-parametrar </a>. </p> </li> 
        <li id="li_A5D00883738845C8B8F612A7521F160F"> <span class="uicontrol"> Kriterier  </span> <p>Definierar filteråtgärden. Filteråtgärden som du väljer i listrutan använder det konstanta värde som anges i den tredje kolumnen. </p> </li> 
        <li id="li_5A312C2984454C2CB518CA453AD9F6D2"> <span class="uicontrol"> Värde  </span> <p>Konstantvärdet. </p> </li> 
        <li id="li_666AAE1BC7A2432E91953B08EC7394DC"> <span class="uicontrol"> Åtgärd  </span> <p>Lägger till en ny fältmappningsrad eller tar bort den markerade raden. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>4 </p> </td> 
      <td colname="col2"> <p>Filöverföring </p> </td> 
      <td colname="col3"> <p>Gör att du kan konfigurera schemat för att skicka feed-filerna och ange den metod som du vill använda för att överföra filerna. </p> 
        <ul id="ul_49B3255BE669424B925BBAEE4C9B385F"> 
        <li id="li_939828C774D440EBB0769F6D5B0BBA23"> <span class="uicontrol"> Schema  </span> <p>Anger den maximala frekvens som en feed skickas. Om du väljer <span class="uicontrol"> Aldrig </span> inaktiveras feeden. Andra värden definierar den period som flödet väntar innan det skickas igen. Beslutet om när feeden ska skickas görs vid varje index. Med andra ord, i slutet av indexet kontrolleras en feed för att se om den har gått ut och måste uppdateras och skickas av leverantören. Den används också som ett sätt att förhindra att ett konto överför till en leverantör. Vissa leverantörer har policyer mot datakällor som överförs för ofta. Kontrollera att du kontrollerar feedleverantörens policy för hur ofta svar skickas in. </p> <p> 
          <!--The time of the last upload and the status of the upload feed is displayed here. If any other feeds are currently running, their status appears here instead. Each account processes one feed at a time. --> </p> <p> 
          <!--Click <uicontrol>Manual Upload</uicontrol> to generate the feed and push the files to the final destination. Any schedule restrictions that you have already set are ignored. --> </p> <p> 
          <!--If <uicontrol>Manual Upload</uicontrol> is dimmed (inactive), the account is currently processing this feed or another feed. An account only works with one feed at a time. --> </p> </li> 
        <li id="li_07B5BCF7936241A7915C4898B231184B"> <span class="uicontrol"> Överföringsmetod  </span> <p>De flesta flöden har två sätt att distribuera filerna: FTP och nätverket för värdbaserat innehåll. </p> 
          <ul id="ul_74FA98A82754469BA5FADCC63FC364F7"> 
          <li id="li_02940B712D6444A8B65C0A51834187E6"> <span class="uicontrol"> FTP  </span> <p>Webbplatssöknings-/försäljningsservrar använder passiv FTP. </p> <p>FTP är det enda sättet att skicka en fil till en annan server. </p> <p> <span class="uicontrol"> FTP-server  </span> - Anger namnet på FTP-servern. Inkludera inte protokollet eller föregående "ftp://". </p> <p> <span class="uicontrol"> FTP-användarnamn  </span> - Anger namnet på FTP-kontot. </p> <p> <span class="uicontrol"> FTP-lösenord  </span> - Anger lösenordet för FTP-kontot. </p> <p> <span class="uicontrol"> FTP-filnamn  </span> - Anger namnet på filen som ska överföras. Det här namnet är en mall om feeden genererar flera filer, vanligtvis med ett nummer i slutet av namnet men före filnamnstillägget. Till exempel: basename.xml, basename1.xml, basename2.xml, ... , basename-Nth.xml </p> <p> <span class="uicontrol"> FTP-katalog  </span> - Om en viss katalogsökväg krävs anger du den här. Ta inte med filnamnet i sökvägen. </p> </li> 
          <li id="li_EAE504436CD84452BA04BE51855A2BEF"> <span class="uicontrol"> Nätverk av värdbaserat innehåll  </span> <p>Innehållsnätverket är ett sätt att hantera filer från webbservrar för webbplatssökning/försäljning. Mottagaren av feeden hämtar den från webbservrarna med en HTTP-begäran. </p> <p> 
            <!--After the base filename is entered and the feed is successfully saved, the URL of the Content Network file is displayed on the Verification panel of the wizard. The URL becomes active after the feed is successfully processed. The vendor can get the feed data from this URL. Multiple files use the same URL path. However, be sure that you replace or change the filename according to the enumeration scheme. --> </p> </li> 
          </ul> </li> 
        </ul> <p>Observera att båda överföringsmetoderna kräver att du anger den URL som Google använder för att hämta platskartan i fältet <span class="wintitle"> URL för huvudplatskarta </span>. Namnet på platskartfilen avgörs också här. Om platskartan är stor kan det finnas flera filer och namnkonventionen är att bifoga ett indexnummer i slutet av filen med början på nummer 1. Den första filen eller indexfilen har inget index, som i <span class="codeph"> sitemap.xml </span>, <span class="codeph"> sitemap1.xml </span>, <span class="codeph"> sitemap2.xml </span> ... <span class="codeph"> sitemap12.xml </span>. </p> <p>Om du väljer <span class="uicontrol"> Hosted Content Network </span> som överföringsmetod har filernas URL samma filnamn, men webbadressen har värdtjänstens sökväg och värdnamn. Därför omdirigerar du begäranden om webbplatskartan till nätverket för värdbaserat innehåll. Du bör också kunna hämta filerna från samma plats. </p> <p>När feed-filerna har skapats och skickats till det mellanliggande målet, pingas Google och talar om för dem att platskartans feed är klar. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>5 </p> </td> 
      <td colname="col2"> <p>Verifiering </p> </td> 
      <td colname="col3"> <p>När du kommer till panelen <span class="wintitle"> Verifiering </span> sparas din feed då. De faktiska feedfilerna sparas dock inte förrän senare. </p> <p>På panelen <span class="wintitle"> Verifiering </span> kan du göra följande: </p> 
        <ul id="ul_A1D889A84972419599FC83F39EA2676A"> 
        <li id="li_C8ED077B6DD1461E85A4914C1CFDBE88"> <span class="uicontrol"> Datavy  </span> <p>Gör att du kan klicka på länken för att kontrollera matningsutdata via en datavy som visas i tabellformulär. Datavyn kan även hjälpa dig att felsöka genom att visa vilka metafält som har valts och hur eventuella angivna sökvillkor från panelen <span class="wintitle"> Sökvillkor </span> i guiden påverkar feed-utdata. Datavyn genereras dynamiskt, så den är alltid tillgänglig. </p> </li> 
        <li id="li_DACEE40703AF40EFBCD90D43825CE9C1"> <span class="uicontrol"> Feed-filer  </span> <p>När feed-filerna har genererats kan du använda listrutan <span class="uicontrol"> Feed Files </span> för att visa filerna från servrarna. En ny webbläsarflik eller ett nytt webbläsarfönster visas med innehållet i feeden. Den här metoden är användbar när du vill felsöka feeds som har formateringsproblem. Observera att du inte kan visa filerna från slutmålet eller från leverantörerna själva. </p> <p> Om flödet är nytt är listrutan tom tills du genererar feed-filer. </p> </li> 
        <li id="li_1C530354B4F34EC79D92CEFEB5B39ED7"> <span class="uicontrol"> Länk till innehållsnätverk  </span> <p>Om du väljer <span class="uicontrol"> Hosted Content Network </span> som överföringsmetod i panelen <span class="wintitle"> File Submission </span> i guiden visas URL:en här. Om du ännu inte har genererat några feed-filer är URL:en inte giltig förrän feeden har genererats. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. När du har slutfört stegen i guiden klickar du på **[!UICONTROL Close]**.

## Redigera en feed {#task_B855D28CD99B4FA58E2D4D4FD6DC9CEB}

Du kan redigera konfigurationen för en befintlig feed.

<!-- 

t_editing_a_feed.xml

 -->

>[!NOTE]
>
>När du redigerar en feed kan du inte ändra flödestypen. Om du behöver ändra flödestypen tar du bort den befintliga feeden och lägger sedan till en ny feed med önskad typ.

Se [Ta bort en feed](../c-about-settings-menu/c-about-searching-menu.md#task_7E39A140E69D43C6B61FB42E81051269).

**Redigera en feed**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** på produktmenyn.
1. Gör något av följande:

* På sidan [!DNL Feeds], under kolumnen [!DNL Name] i tabellen, klickar du på listrutan bredvid ett feed-namn och sedan på **[!UICONTROL Edit feed]**.

* På sidan [!DNL Feeds], under kolumnen [!DNL Name], klickar du på namnet på en feed som du vill ändra.

1. Ange de alternativ som du vill ha för varje panel i guiden för flödet.

   Se alternativtabellerna under **Lägga till en feed**.
1. Klicka på **[!UICONTROL Close]** i panelen [!DNL Verification] i slutet av guiden.

## Ta bort en feed {#task_7E39A140E69D43C6B61FB42E81051269}

Du kan ta bort en feed som du inte längre behöver eller använder.

<!-- 

t_deleting_a_feed.xml

 -->

**Ta bort en feed**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** på produktmenyn.
1. Klicka på **[!UICONTROL Delete]** på skärmen [!DNL Feeds Menu] under kolumnen [!DNL Actions] för det feed-namn som du vill ta bort.
1. Klicka på **[!UICONTROL Yes]** i dialogrutan [!DNL Delete feed] för att bekräfta borttagningen.

## Visa feed-filer {#task_1E413C7650DE466EA68925F72E086884}

Du kan gå till den sista panelen i guiden Feed och få snabb åtkomst för att visa datavyn för flödet eller för att hämta aktuella feed-filer från servern. Den här funktionen är användbar om du vill verifiera och undersöka matningsutdata.

<!-- 

t_viewing_feed_files.xml

 -->

**Så här visar du feed-filer**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** på produktmenyn.
1. På sidan [!DNL Feeds], under kolumnen [!DNL Name] i tabellen, klickar du på listrutan bredvid ett feed-namn och sedan på **[!UICONTROL View Feed Files]**.
1. Klicka på **[!UICONTROL Show Data View]** på panelen [!DNL Verification] i feeds guide.
1. Klicka på **[!UICONTROL Close]**.

## Testa en feed utan filöverföring {#task_F1F390F72E0A4886B6CD4CD86EDB4C8C}

Du kan testa en feed utan att överföra filer till det slutliga målet.

<!-- 

t_testing_a_feed_with_no_file_upload.xml

 -->

**Testa en feed utan filöverföring**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** på produktmenyn.
1. På sidan [!DNL Feeds], under kolumnen [!DNL Name] i tabellen, klickar du på listrutan bredvid ett feed-namn och sedan på **[!UICONTROL Test Feed (No file upload)]**.
1. På sidan [!DNL Feeds] uppdateras kolumnen [!DNL Feed Status] under och efter testet.

## Generera och överföra en feed {#task_C9A57827C7674035B62A22D310DDAA0C}

Du kan generera och skicka feed-filer till det slutliga målet manuellt, oavsett vilket schema du anger på panelen [!DNL File Submission] i Feed-guiden.

<!-- 

t_generating_and_uploading_a_feed.xml

 -->

Se även [Skapa en feed](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250).

**Generera och överföra en feed**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** på produktmenyn.
1. På sidan [!DNL Feeds], under kolumnen [!DNL Name] i tabellen, klickar du på listrutan bredvid ett feed-namn och sedan på **[!UICONTROL Generate and Upload Feed]**.
1. På sidan [!DNL Feeds] uppdateras kolumnen [!DNL Feed Status] under och efter generering och överföring av datafeed.
