---
description: Du kan konfigurera olika områden i Komplettera automatiskt för att styra genereringen av det automatiskt ifyllda sökformuläret och filen autocomplete_data.js, som ingår som en del i det automatiskt ifyllda sökformuläret.
solution: Target
subtopic: Auto-Complete
title: Om Komplettera automatiskt
topic-legacy: Design,Site search and merchandising
uuid: 3dfdd14d-2044-4f01-a5bc-fcb2eb0d5068
exl-id: a1d08c0a-6c68-4da2-88d2-fe953d333536
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 1%

---

# Om Komplettera automatiskt{#about-auto-complete}

Du kan konfigurera olika områden i Komplettera automatiskt för att styra genereringen av det automatiskt ifyllda sökformuläret och filen autocomplete_data.js, som ingår som en del i det automatiskt ifyllda sökformuläret.

## Om Komplettera automatiskt {#concept_093A9CD754864BA79B456FE4BEB64578}

Filen [!DNL autocomplete_data.js] genereras om och publiceras i sökinnehållsnätverket varje gång det finns ändringar som har sparats på sidan Komplettera automatiskt.

## Konfigurerar Komplettera automatiskt {#task_F491F2BFC4D24A61BBDC48B9059C11BB}

Du kan konfigurera och konfigurera alternativ som styr genereringen av det automatiskt ifyllda sökformuläret och filen.

<!-- 

t_configuring_auto-complete.xml

 -->

När du har konfigurerat Komplettera automatiskt kan du visa den slutliga HTML-källan för granskning. HTML-källan är den du kopierar och klistrar in på webbplatsens sidor.

Se [Förhandsgranska sökformuläret som det skulle se ut på din dator..](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

Se [Konfigurera automatisk komplettering av ordlista](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4).

Se [Konfigurera Komplettera CSS automatiskt](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**Konfigurera Komplettera automatiskt**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Setup]** på produktmenyn.
1. Ange önskade alternativ på sidan [!DNL Auto-Complete Setup].

   Se även [Förhandsgranska sökformuläret som det skulle se ut på din dator..](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Maximalt antal förslag </p> </td> 
      <td colname="col2"> <p>Anger det maximala antalet objekt som ska visas i listan med automatiska förslag. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minsta antal indatatecken </p> </td> 
      <td colname="col2"> <p>Anger det antal tecken som en kund måste skriva i det automatiska sökformuläret innan förslag visas. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximalt antal cacheposter </p> </td> 
      <td colname="col2"> <p>Anger maximalt antal tidigare begärda automatiska förslag för att cachelagra i kundens webbläsare. I allmänhet bör du låta inställningen vara som standard 1 000. </p> <p>Du kan inaktivera webbläsarcachelagring helt genom att ange det här alternativet till 0, men det rekommenderas inte. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Formulärnamn </p> </td> 
      <td colname="col2"> <p>Anger attributet "name" för det automatiskt ifyllda aktiverade sökformulärets "form"-tagg. Exempel: </p> <p> <span class="filepath"> &lt;form name="SiteSearch" method="get" action="https://sp1004337c.guided.t1.atomz.com" target="_blank"&gt; </span> </p> <p>där <span class="filepath"> SiteSearch </span> är formtaggens namnattribut. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Div-tagg-ID </p> </td> 
      <td colname="col2"> <p>Anger ID-attributet för det automatiskt ifyllda aktiverade sökformulärets div-tagg. Exempel: </p> <p> <span class="filepath"> &lt;div id="autocomplete"&gt; </span> </p> <p>där <span class="filepath"> autocomplete </span> är div-taggens attribut. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>ID för indatatagg </p> </td> 
      <td colname="col2"> <p>Anger ID-attributet för det automatiskt ifyllda sökformulärets indatatagg. Exempel: </p> <p> <span class="filepath"> &lt;input type="text" id="q" name="q" /&gt; </span> </p> <p>där <span class="filepath"> q </span> är id-attributet för input-taggen. </p> </td> 
      </tr> 
      <tr>
      <td colname="col1"> <p>Visa skugga </p> </td>
      <td colname="col2"> <p>Lägger till en kosmetisk skuggning i listan med automatiska förslag. </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>Matcha endast i början av frasen </p> </td>
      <td colname="col2"> <p>Föreslå endast resultat som matchar början av indatatexten. </p> </td>
      </tr>
      <tr>
      <td colname="col1"> <p>Stöd för teckenuppsättningen UTF-8 </p> </td>
      <td colname="col2"> <p>Hantera icke-ASCII-tecken korrekt i termer. </p> </td>
      </tr>
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurerar automatisk komplettering av ordlista {#task_1F8E0F346263443383F8CFD2C7AB35D4}

Konfigurera listan med ord och fraser som Komplettera automatiskt visar för en kund som förslag.

<!-- 

t_configuring_auto-complete_word_list.xml

 -->

Se [Konfigurera Komplettera automatiskt](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Se [Konfigurera Komplettera CSS automatiskt](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

**Så här konfigurerar du Komplettera ordlista automatiskt**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete Word List]** på produktmenyn.
1. Ange önskade alternativ på sidan [!DNL Auto-Complete Word List].

   Se [Förhandsgranska sökformuläret som det skulle se ut på din dator..](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Period för populära sökningar </p> </td> 
      <td colname="col2"> <p> Styr tidsperioden för att inkludera ord och fraser från en kunds senaste sökningar. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> Maximalt antal sökningar </p> </td> 
      <td colname="col2"> <p>Styr det maximala antalet sökningar efter ord och fraser som ska tas med i den automatiska ordlistan. De översta orden och fraserna, som också är de populäraste, finns med. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fältnamn </p> </td> 
      <td colname="col2"> <p>Varje fältnamn definierar namnet på ett fält för vilket indexerade värden ska inkluderas. Använd + och - för att lägga till eller ta bort fältnamn. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximalt värde </p> </td> 
      <td colname="col2"> <p>Definierar det maximala antalet fältvärden som tillåts för det valda fältnamnet. De översta värdena, som också är de mest refererade, inkluderas. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lägg till dessa ord och fraser </p> </td> 
      <td colname="col2"> <p> Ordlistan som fylls i automatiskt fylls i med de ord och fraser som visas i det här området. </p> <p> Klicka på <span class="uicontrol"> Redigera </span> om du vill visa listan eller lägga till ord och fraser i listan. När du är klar klickar du på <span class="uicontrol"> Spara ändringar </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ta bort dessa ord och fraser </p> </td> 
      <td colname="col2"> <p> Poster i det här området visas inte i ordlistan som fylls i automatiskt. </p> <p> Klicka på <span class="uicontrol"> Redigera </span> om du vill visa listan eller lägga till ord och fraser i listan. När du är klar klickar du på <span class="uicontrol"> Spara ändringar </span>. </p> <p> Reguljära uttryck tillåts i den här listan. Om du vill ange ett reguljärt uttryck i den här listan börjar du raden med <code>regexp</code> följt av ett blanksteg följt av det reguljära uttrycket. Alla rader i ordlistan som matchar det reguljära uttrycket tas bort. </p> <p> <b>Viktigt</b>: Du bör bara använda reguljära uttryck om du tidigare har arbetat med dem i andra program. </p> <p>Se <a href="c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A" type="reference" format="dita" scope="local"> Reguljära uttryck </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ignorera skiftläge </p> </td> 
      <td colname="col2"> <p>Dubblettposter i ordlistan som fylls i automatiskt och som endast skiljer sig åt i alfabetisk ordning tas bort. alla ordlisteposter skrivs med gemener. </p> <p>Om du vill att förslagen Komplettera automatiskt ska visas med"inledande versal" eller"versaler" lägger du till 
        <code>
          text-transform : capitalize; 
        </code> eller 
        <code>
          text-transform : uppercase; 
        </code> CSS-textegenskaper till CSS-innehållet Komplettera automatiskt, under "/*-format för resultatobjektet */". </p> <p>Se <a href="c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96" type="task" format="dita" scope="local"> Konfigurera Komplettera CSS automatiskt </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Uppdatera vid omindexering </p> </td> 
      <td colname="col2"> <p>Den automatiska kompletteringen av ordlistan genereras automatiskt om efter att varje lyckat kontoomindexering har gjorts. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.
   * Klicka på **[!UICONTROL Preview Word List]** för att spara ändringar du har gjort och öppna sedan sidan [!DNL Auto-Complete Word List Preview] där du kan granska listan med automatiska förslag. Använd navigeringsalternativen längst upp på sidan för att granska och förfina den visade listan. När du är klar klickar du på **[!UICONTROL Close]** för att återgå till sidan [!DNL Auto-Complete Word List].

      Se [Använda alternativet Historik](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurera Komplettera CSS automatiskt {#task_EECE35DEB6C94F4A8A5B42B4DED76D96}

Använd Komplettera CSS automatiskt för att konfigurera den CSS-formatmall som du vill använda för automatisk komplettering.

<!-- 

t_configuring_auto-complete_css.xml

 -->

Komplettera automatiskt CSS styr innehållet i [!DNL autocomplete_styles.css], som ingår i det automatiskt ifyllda sökformuläret. Den CSS som du anger här styr den visuella presentationen av listan med automatiska förslag. Ett exempel på visuella presentationsidéer som är möjliga finns i följande:

[https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html](https://developer.yahoo.com/yui/examples/autocomplete/ac_skinning.html).

[Konfigurerar automatisk komplettering av ordlista](c-about-auto-complete.md#task_1F8E0F346263443383F8CFD2C7AB35D4).

[Konfigurerar Komplettera](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB) automatiskt.

När du är klar med konfigurationen av Komplettera automatiskt CSS kan du förhandsgranska sökformuläret för att se om den CSS som du har angett kan användas i utseende och layout.

Se [Förhandsgranska sökformuläret som det skulle se ut på din dator..](c-about-auto-complete.md#task_437B35EFA5424603A08AF8E79E6B4714).

**Viktigt**: Om du vill använda din anpassade CSS-kod för automatisk komplettering måste du ta bort kommentartaggarna från den andra raden som visas i HTML-koden. Sedan flyttar du samma rad till i huvudsektionen på sidan där sökformuläret finns.

Se [Kopiera HTML-koden för sökformuläret till ...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

**Konfigurera Komplettera CSS automatiskt**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Auto-Complete CSS]** på produktmenyn.
1. I textfältet [!DNL Auto-Complete CSS] klistrar du in eller skriver den CSS-information som du vill associera med listan med automatiska förslag.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Förhandsgranska sökformuläret så som det skulle visas på webbplatsen {#task_437B35EFA5424603A08AF8E79E6B4714}

Beroende på din konfiguration av CSS för Komplettera automatiskt och Komplettera automatiskt kan du förhandsgranska hur sökformuläret visas om du vill lägga till HTML-koden på webbplatsen.

<!-- 

t_previewing_the_search_form_as_it_would_appear_on_your_website.xml

 -->

Se [Konfigurera Komplettera automatiskt](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Se [Konfigurera Komplettera CSS automatiskt](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Se [Kopiera HTML-koden för sökformuläret till ...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Se [Använda samlingar i sökformulär](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Se [Använda ramar med formulär](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Se [Exempel på avancerat sökformulär](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).

Se [Avancerad HTML-kod för sökformulär](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9).

Se [Kod för avancerad sökformulärsmall](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579).

**Förhandsgranska sökformuläret så som det skulle visas på webbplatsen**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Search Form]** på produktmenyn.
1. (Valfritt) Klicka på **[!UICONTROL HTML code]** om du vill visa HTML-koden som du kopierar och klistrar in på webbplatsens sidor.

## Kopiera HTML-koden för sökformuläret till sidorna på webbplatsen {#task_A3A01EA800F24C0AA33902387E0362C7}

Beroende på din konfiguration av CSS för Komplettera automatiskt och Komplettera automatiskt kan du förhandsgranska hur sökformuläret visas om du vill lägga till HTML-koden på webbplatsen.

<!-- 

t_copying_the_html_code_of_the_search_form_into_the_pages_of_your_website.xml

 -->

Se [Konfigurera Komplettera automatiskt](c-about-auto-complete.md#task_F491F2BFC4D24A61BBDC48B9059C11BB).

Se [Konfigurera Komplettera CSS automatiskt](c-about-auto-complete.md#task_EECE35DEB6C94F4A8A5B42B4DED76D96).

Se [Kopiera HTML-koden för sökformuläret till ...](c-about-auto-complete.md#task_A3A01EA800F24C0AA33902387E0362C7).

Se [Använda samlingar i sökformulär](c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Se [Använda ramar med formulär](c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Se [Exempel på avancerat sökformulär](c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).

Se [Avancerad HTML-kod för sökformulär](c-appendices/c-searchforms.md#reference_9AAD4A46B68D4D48865508982CB86DB9).

Se [Kod för avancerad sökformulärsmall](c-appendices/c-searchforms.md#reference_D762C22E754E462DBEECD88D2C3FA579).

**Kopiera HTML-koden för sökformuläret till sidorna på webbplatsen**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Auto-Complete]** > **[!UICONTROL Form Source]** på produktmenyn.

   >[!NOTE]
   >
   >Ändra inte `form name=`-värdet i formulärkällan.

1. (Valfritt) Gör något av följande:

   * Om du har konfigurerat CSS som fylls i automatiskt och vill använda formaten i sökformuläret tar du bort kommentartaggarna från den andra raden som visas i HTML-koden. Flytta sedan samma rad till i huvudsektionen på sidan där sökformuläret finns.
   * För att få bästa möjliga prestanda flyttar du taggarna som visas längst ned i HTML-koden och placerar dem längst ned i brödavsnittet på varje sida som innehåller sökformuläret.

1. Kopiera koden och klistra in den på webbplatsens webbsidor där du vill att sökformuläret ska visas.
