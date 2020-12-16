---
description: 'null'
seo-description: 'null'
seo-title: Mallar
solution: Target
title: Mallar
topic: Appendices,Site search and merchandising
uuid: 78299032-dc23-4dfe-b68f-cd57b2b6d7d8
translation-type: tm+mt
source-git-commit: ca4156f80d7dbb85d2d56b6caf7c0f560299d86e
workflow-type: tm+mt
source-wordcount: '15139'
ht-degree: 1%

---


# Mallar{#templates}

## Mallar {#concept_A5CFB6BD805D49459A96219AF1B17842}

## Presentationsmalltaggar {#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64}

En lista med webbplatsens sök-/säljtaggar och attribut för presentationsmallar.


En presentationsmall är en HTML-fil som innehåller presentationsmalltaggar som definieras av webbplatssökningen/försäljningen. Dessa taggar anger hur de sökresultat som kunderna ser formateras.

Se [Mallar](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5).

Du kan välja bland följande grupper av presentationstaggar:

* [Deklarationer](../c-appendices/c-templates.md#section_82C5CA734D2941EB858FEFE3B695D2EC)
* [Resultat](../c-appendices/c-templates.md#section_06F249C9F6AE4B0F8C32117E19DCC905)
* [Fasetter](../c-appendices/c-templates.md#section_EA4C5678D5864B89BAB4D0DFE62A4624)
* [Breadcrumb](../c-appendices/c-templates.md#section_9B39B71FA6EC49FA8D88AD8A3BA987F7)
* [Menyer](../c-appendices/c-templates.md#section_1D489ADF041F4351A66E5D5742125CA8)
* [Pagenav](../c-appendices/c-templates.md#section_2EE397635C514BBC8D668278EA314F35)
* [Senaste sökningar](../c-appendices/c-templates.md#section_8CD907521F584257B475595B01A5964B)
* [Menade du](../c-appendices/c-templates.md#section_C1EB3B9D8E1242798A6E04609D1E3543)
* [Komplettera automatiskt](../c-appendices/c-templates.md#section_897316BEE1454E839A56B565CA4AF018)
* [Butik](../c-appendices/c-templates.md#section_A33E25DB5E67404A823BD9618665B773)
* [Zoner](../c-appendices/c-templates.md#section_B9B3179E000C42D492E1541F2FE44CB5)
* [Loopindikatorer](../c-appendices/c-templates.md#section_387322CA0AA843A2ACF2795C328673E9)
* [Övrigt språk](../c-appendices/c-templates.md#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C)

## Deklarationer {#section_82C5CA734D2941EB858FEFE3B695D2EC}

Deklarationer är speciella guidade deklarationstaggar som du kan ange högst upp i en presentationsmall på den översta nivån. Eventuella efterföljande deklarationer ignoreras, inklusive deklarationer i inkluderade mallar.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-content-type-header content="content-type"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Som standard skickas presentationsmallen tillbaka med mime-typen text/html. Du kan ändra vilken innehållstyp som används med den här taggen. </p> <p>Deklarera taggen så hög som möjligt i presentationsmallen. Lägg inte till annan text på samma rad med den här taggen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml-declare&gt; </span> </p> </td> 
   <td colname="col2"> <p> Om du returnerar XML kan du använda den här taggen för att skapa XML-deklarationen. Gör den här taggen till den första raden i presentationsmallen. När du använder den här taggen anges innehållstypen automatiskt till text/xml, såvida du inte åsidosätter den med <span class="codeph"> &lt;guided-content-type-header&gt; </span> på den första raden. Om du inte anger någon teckenuppsättning används UTF-8 som standard. Den här taggen ger följande utdata i XML-dokumentet: </p> <p> <span class="codeph"> &lt;?xml version="1.0" encoding="charset-name" standalone="yes" ?&gt; </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resultat {#section_06F249C9F6AE4B0F8C32117E19DCC905}

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-results&gt;&lt;/guided-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Taggen för guidade resultat definierar gränserna för en resultatslinga. Du kan komma åt alla resultatuppsättningar genom att ange ett <span class="codeph">-gsname </span>-attribut. Om inget <span class="codeph">-namn </span> anges visas standardsökresultaten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-link&gt;&lt;/guided-result-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Om du vill skapa en länk till ett givet resultat använder du taggen <span class="codeph"> guided-result-link </span>. Genom att definiera ett <span class="codeph">-gsname </span>-attribut kan du använda ett fält från indexvärdet i stället för standardtaggen "loc" som refererar till "search-url". Alla andra attribut, till exempel class och target, kan också skickas, som returneras i den resulterande ankartaggen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng 1/31/13--> <span class="codeph"> &lt;guided-result-img gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-result-img&gt; </span>-taggen hjälper dig att skapa bildtaggar i stället för att bädda in variabler inuti en rå <span class="codeph"> img </span>-tagg. </p> <p>Ange det fält som ska användas för bildsökvägen i attributet <span class="codeph"> gsname </span>. Resultatet är en <span class="codeph"> img </span>-tagg med alla HTML-standardattribut som du har definierat och som skickats igenom. I följande exempel: </p> <p> <code class="syntax html"> &lt;guided-result-img&nbsp;gsname="thumbnail" 
      &nbsp;class="thumb"&nbsp;border="0"/&gt; </code> </p> <p>blir: </p> <p> <code class="syntax html"> &lt;img&nbsp;src="prod8172.jpg"&nbsp;class="thumb" 
      &nbsp;border="0"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 1/31/13; search-eng version does not have [escape...] Added ijson on 8/28/2015--> <span class="codeph"> &lt;guided-result-field gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p> All information som ska visas i resultatet visas som en <span class="codeph"> &lt;guided-result-field&gt; </span>-tagg (förutom när du använder autogenererande taggar som <span class="codeph"> &lt;guided-result-img&gt; </span>-taggen). </p> <p>Ange namnet på sökindexsfältet i <span class="codeph">-spelet </span>. Den exakta sträng som skickas är utdata i mallen. </p> <p>Du kan ange ett escape-alternativ om du vill att det här fältet ska rymmas på ett annat sätt än vad som angetts i transportmallen. </p> <p>Den här kodningen används ovanpå den kodning som har angetts i transportmallen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if-result-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här uppsättningen villkorstaggar är true om det finns innehåll i det specifika fältet som ska visas. Om inget innehåll finns är villkoret false. Du kan använda taggarna för att bestämma om omgivande HTML ska visas eller inte om ett värde inte finns, om en annan bild visas och så vidare. </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"&nbsp;/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"&nbsp;/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <code> &lt;guided-if[-not]-result-wrap&gt; 
      &lt;guided-else-result-wrap&gt; 
      &lt;/guided-if[-not]-result-wrap&gt; </code> </p> </td> 
   <td colname="col2"> <p>När du visar resultat i kolumner används den här taggen för att identifiera om det aktuella resultatet är slutet på en kolumn. </p> <p>När det booleska villkoret är true läggs HTML till i slutet av resultatet för att avsluta raden och starta en ny. När det är den sista raden startas ingen ny rad. </p> <p>Mer information om den taggen finns i <span class="codeph"> &lt;guided-if-not-last&gt; </span>. </p> <p> <code class="syntax html"> &lt;guided-if-result-wrap&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&lt;/guided-if-result-wrap&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-results-found&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar 1 om backend-sökbegäran returnerade resultat och 0 om det inte gjorde det. Om inget <span class="codeph">-namn </span> anges används den primära sökningen för taggen. Den här taggen är användbar för att skicka logik till JavaScript-rutiner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar det totala antalet resultat i den angivna resultatmängden. Antar standardsökningen när inget <span class="codeph">-namn </span> har angetts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-lower&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar resultatnumret för det nedre resultatet på sidan för den angivna resultatmängden. Antar standardsökningen när inget <span class="codeph">-namn </span> har angetts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-results-upper&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar resultatnumret för det övre resultatet på sidan för den angivna resultatmängden. Antar standardsökningen när inget <span class="codeph">-namn </span> har angetts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-results-found&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Visar innehåll när resultat hittas. Eller visar ingen resultat-HTML när resultat inte hittas. </p> <p> <code class="syntax html"> &lt;guided-if-results-found&nbsp;gsname="products"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-results&nbsp;gsname="products"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-results&gt; 
      &lt;guided-else-results-found&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;No&nbsp;results&nbsp;were&nbsp;found. 
      &lt;/guided-if-results-found&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-title /&gt; </span> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> &lt;guided-result-title&gt; </span>-taggen ger värdet för titeltransportmallfältet som anges med <span class="codeph"> &lt;title&gt; </span>-transporttaggen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-description /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Taggen <span class="codeph"> &lt;guided-result-description&gt; </span> ger ett värde för det beskrivande transportmallfält som anges med <span class="codeph"> &lt;description&gt; </span>-transporttaggen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-loc /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Taggen &lt; <span class="codeph"> guided-result-loc&gt; </span> ger ett värde för det lokala transportmallsfältet som anges med <span class="codeph"> &lt;loc&gt; </span>-transporttaggen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-result-field;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>True if there is content in the specific field to display. Om inget innehåll finns är villkoret false. Använd taggarna för att bestämma om omgivande HTML ska visas eller inte om ett värde inte finns, om en annan bild visas och så vidare. </p> <p> <code class="syntax html"> &lt;guided-if-result-field&nbsp;gsname="thumbnail"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-result-img&nbsp;gsname="thumbnail"&nbsp;class="thumb"/&gt; 
      &lt;guided-else-result-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;img&nbsp;src="nothumb.jpg"&nbsp;class="nothumb"/&gt; 
      &lt;/guided-if-result-field&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table gsname="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen tillhandahåller en slinga genom den attributtabell som definieras i transportmallen med transporttaggen <span class="codeph"> &lt;attribute_table&gt; </span>. Det finns <span class="codeph"> &lt;guided-result-attribute-table-field&gt; </span>-tagg för att visa värden för attributtabellfält. Det går också att använda den enkla taggen <span class="codeph"> guided-result-field </span> i slingan för att visa andra resultatfält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-result-attribute-table-field gsname="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar attributtabellfält enligt transportmallen. </p> <p> 

    ...
    
    &amp;lt;ul;
    
    &amp;lt;guided-result-attribute-table&amp;nbsp;gsname=&quot;downloads&quot;&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;lt;li&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;a&amp;nbsp;href=&quot;&amp;lt;guided-result-attribute-table-field&amp;nbsp;gsname=&quot;download_link&quot;&amp;nbsp;/&amp;gt;&quot;&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp; bsp;&amp;lt;guided-result-attribute-table-field&amp;nbsp;gsname=&quot;download_title&quot;&amp;nbsp;/&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;/a&amp;nbsp;(&amp;lt;guided-result-field &amp;nbsp;gsname=&quot;title&quot;/&amp;gt;)
    &amp;nbsp;&amp;nbsp;&amp;lt;/li&amp;gt;
    &amp;lt;/guided-result-attribute-table&amp;gt;
    
    &amp;lt;/ul&amp;gt;
    
    ..
    
    &amp;lt;/guided-results&amp;gt;   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release in October 2014--> <span class="codeph"> &lt;guided-trace&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar den spårningsinformation som finns i spårningsdata i det allmänna avsnittet i JSON-utdata av transportmallen för den angivna sökningen. </p> <p>Om inget söknamn anges antas <span class="codeph"> </span> som standard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30, 2014)--> <span class="codeph"> &lt;guided-result-trace /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar JSON-innehållet som hittats i resultaten &gt; spårningsinformation för JSON-datautdata av transportmallen för det aktuella sökresultatet. </p> <p>Den här taggen är bara giltig i <span class="codeph"> &lt;guided-results&gt;&lt;/guided-results&gt; </span>-slingan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ansikten {#section_EA4C5678D5864B89BAB4D0DFE62A4624}

Ansikten är navigeringskomponenter som gör att du kan gå in i sökresultaten. Du kan använda ansiktstaggarna för att visa olika aspekter i presentationsmallen. Du refererar till ansikten efter namn.

Se [Om ansikten](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

Se [Om Fasett Rail](../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB).

Se [Om dynamiska ansikten](../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 02/27/2014--> <span class="codeph"> &lt;guided-dynamic-facets&gt;&lt;/guided-dynamic-facets&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--NEW 2/2/2014--> <p>En loop-kontext för alla dynamiska aspekter för en given sökning. </p> <p><span class="codeph"> &lt;guided-facet&gt; </span>-presentationsmalltaggen redigeras så att gsname-attributet automatiskt tillhandahålls av <span class="codeph"> &lt;guided-dynamic-facets&gt; </span>-upprepningskontexten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-display-name gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar ansiktets visningsetikett. </p> <p>Om funktionen använder taggen <span class="codeph"> &lt;display-name&gt; </span> i transportmallen blir innehållet i taggen etikett. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-rail&gt;&lt;/guided-facet-rail&gt; </span> </p> </td> 
   <td colname="col2"> <p> Definierar ett avsnitt i presentationsmallen som används som ett upprepande mönster för varje aspekt i ansiktsskenan. </p> <p> Varje aspekt som tillhör ansiktsrälen använder det här avsnittet för att utvärdera utdata. </p> <p>Följande är ett exempel på en fasetterad räl: </p> <p> <code class="syntax html"> &lt;guided-facet-rail&gt; 
      &nbsp;&nbsp;&lt;guided-facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-display-name/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;... 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet&gt; 
      &nbsp;&nbsp;&lt;/guided-facet-rail&gt; </code> </p> <p>Observera att följande taggar inte behöver attributet <span class="codeph"> gsname </span> när det finns i <span class="codeph"> &lt;guided-facet-rail&gt; </span>-taggen eftersom värdet bestäms dynamiskt vid sökningen och ersätts korrekt: </p> 
    <ul id="ul_5B5ACAFD2B8848DDB27471AB9DA7BE6E"> 
     <li id="li_5A07E78D51FE4708879DD742C877FFFF">styrd-facet </li> 
     <li id="li_B875DCACD7AB4FC890A456A6939AB657">guided-facet-display-name </li> 
     <li id="li_B70450749E864DE7BA401E3CD6EF5EB3">guided-facet-total-count </li> 
     <li id="li_DECDF5EF6FF7454F86C236D322F2BFEA">guided-facet-undo-link </li> 
     <li id="li_176949227AC14E8CA643A419E10F7B5A">guided-facet-undo-path </li> 
     <li id="li_B32D981281744462BC680F6EFEAC0069">guided-facet-behavior </li> 
    </ul> <p>Sorteringsvillkoren på sidan <span class="wintitle"> Fasett Rail </span> avgör fasetternas position. Du kan välja sorteringsordning i listrutan Sorteringsmetoder. </p> <p> 
     <!--NEW 02/27/2014-->Den här taggen kan som tillval acceptera attributvärdet Gsname för  <span class="codeph"> _dynamic_facets  </span>, vilket ger en loop-kontext för alla dynamiska aspekter av sökningen. Den här fördefinierade aspektspåret visas även i användargränssnittet för affärsregler för åtgärden <span class="codeph"> push facet X i facet rail '_dynamic_facets' till position Y </span>. </p> <p>Se <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> Om Fasett Rail </a>. </p> <p>Se även <a href="../c-about-design-menu/c-about-dynamic-facets.md#concept_E65A70C9C2E04804BF24FBE1B3CAD899" format="dita" scope="local"> Om dynamiska ansikten </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match current search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet gsname=" <span class="varname"> facetname </span>" height=" <span class="varname"> 60px </span>" width=" <span class="varname"> 120px </span>"&gt;&lt;/guided-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>Använd <span class="codeph">-taggen för guidade funktioner </span> för att definiera ett område där alla fasettaggar relaterar till en viss aspekt. Den här taggen är också en boolesk tagg som döljer allt innehåll om det inte finns några värden i ansiktet. I så fall finns det ingen punkt som skriver ut fasettsvärdena). </p> <p>Attributen height och width är valfria och dimensionerna anges i pixlar (px). Dessa två attribut används i Visual Rule Builder (VRB) och en prickad ruta visas som en interaktiv platshållare när ansiktet är dolt. </p> <p> När visningsnamnet finns i ansiktet och ansiktet är dolt, döljs även namnet. Om namnet ligger utanför ansiktet kan du bara dölja namnet om en <span class="codeph">-zon </span>-tagg eller en <span class="codeph"> guidad-if-facet-visible </span>-tagg placeras runt den. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här villkorstaggen är sann när antalet fasettvärden överstiger det längdtröskelvärde som definieras i konfigurationen. Använd den för att visa en fasett som ett annat gränssnittselement (till exempel en trunkerad lista eller en rullningsruta) när listan är för lång. </p> <p> <code class="syntax xml"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;select&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-option&nbsp;/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/select&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-long&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Du kan också använda det här villkoret utanför kontexten för ett <span class="codeph">-block med stödfunktioner för </span> genom att referera till en viss aspekt direkt med attributet <span class="codeph"> gsname </span>. </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här villkorstaggen är sann när användaren klickar på den minst en gång och ett fasettvärde är markerat. Den används för att visa eller dölja HTML- eller gs-taggar beroende på om någon har klickat på en aspekt. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Du kan också använda det här villkoret utanför kontexten för ett <span class="codeph">-block med stödfunktioner för </span> genom att referera till en viss aspekt direkt med attributet <span class="codeph"> gsname </span>. </p> <p> <code> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här villkorstaggen är true när det bara finns ett facet-värde. Använd taggen för att ändra visningen av ansiktet när det inte går att förfina resultatet. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Du kan också använda det här villkoret utanför kontexten för ett <span class="codeph">-block med stödfunktioner för </span> genom att referera till en viss aspekt direkt med attributet <span class="codeph"> gsname </span>. </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Added 7/15/2014--> <span class="codeph"> &lt;guided-if&gt;&lt;/guided-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här villkorstaggen är true när ansiktet är flermarkerat. Använd taggen för att ändra visningen av aspekten i <span class="codeph"> &lt;guided-facet-rail&gt; </span> eller <span class="codeph"> &lt;guided-dynamic-facets&gt; </span>-taggar. </p> <p> 

    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;guided-if-facet-multiselect&amp;gt;
    &amp;nbsp;..
    &amp;nbsp;&amp;lt;guided-else-facet-multiselect&amp;gt;
    &amp;nbsp;..
    &amp;nbsp;&amp;lt;/guided-if-facet-multiselect&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;..
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;lt;/guided-facet&amp;gt;
    &amp;nbsp;&amp;nbsp;&amp;lt;/guided-facet-rail&amp;gt;   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-values&gt; facetname  </span>"]&gt;&lt;/guided-facet-values&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>Detta är iteratortaggen för facet-värdeslingan. Du kan definiera det i kontexten för ett <span class="codeph">-block med stödfunktioner för </span>, och då kan du utelämna <span class="codeph"> <span class="varname">-gennamnet </span> </span>. Eller så kan du definiera det utanför ett <span class="codeph">-block med stödfunktioner för </span>, men det skulle kräva <span class="codeph"> <span class="varname">-attributet </span> </span> för att identifiera vilken uppsättning med ansiktsvärden som visas. </p> <p>Du kan också använda den här taggen för att visa fasettsvärden utanför kontexten för ett <span class="codeph">-block med stödlinjer </span>. Du refererar till en specifik aspekt direkt genom att använda attributet <span class="codeph"> <span class="varname"> gsname </span> </span>. </p> <p> <code class="syntax html"> &lt;script&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;registerFacetValues('category',&nbsp;'&lt;guided-facet-values&nbsp;gsname="category"&gt;&lt;guided-facet-value/&gt;,&lt;/guided-facet-values&gt;'); 
      &lt;/script&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>Matar ut strängen för det aktuella facet-värdet. </p> <p>Som standard är värdet HTML escape. Du kan använda alternativet escape för att ändra hur värdet escape-konverteras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--In search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-count /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar antalet resultat som matchar det aktuella ansiktsvärdet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW, brought in from search-eng version, 1/31/13--> <span class="codeph"> &lt;guided-facet-value-link&gt;&lt;/guided-facet-value-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapar en länk runt begränsningsvärdesträngen som besökaren kan klicka på. Sökvägen genereras automatiskt för att begränsa resultatet med det aktuella facet-värdet. Det har stöd för att skicka attribut direkt till ankartaggen. </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-value-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-value-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <code> &lt;guided-if-facet-value-selected&gt; 
      &lt;guided-else-facet- 
      value-selected&gt; 
      &lt;/guided-if-facet-value-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>Ändrar visningen av ansiktsvärdet när det är markerat. Om den redan har valts är den i de flesta fall inte längre länkbar. </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;&lt;guided-facet-value/&gt;&lt;/b&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt;&nbsp;&nbsp;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> 

    &amp;lt;/guided-if[-not]-facet-value-spökgt&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Ändrar visningen av ansiktsvärdet när det är ett spökvärde. När ett fasettvärde är ett spökvärde visas det vanligtvis i kursiv text för att ange att värdet saknas eller är"ghosted". </p> <p>Följande kodutdrag är ett exempel på ett facet-block: </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;b&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/b&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;i&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(0)&lt;/i&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="link"&gt;&lt;guided-facet-value&nbsp;/&gt;&lt;/guided-facet-link&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;) 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-ghost&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-value-selected&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version 1/31/13--> <span class="codeph"> &lt;guided-facet-undo-link gsname=" <span class="varname"> facetname </span>"&gt;&lt;/guided-facet-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar en ångra-länk för en viss aspekt. Om det finns flervalsaspekter avmarkerar den här länken alla värden för den angivna aspekten. Ge ansiktet ett namn. Om begränsningen inte är markerad är länken den aktuella sökvägen. </p> <p>Följande är ett exempel på hur den här taggen används: </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-undo-link&nbsp;gsname="category"&gt;Undo&nbsp;Category&lt;/guided-facet-undo-link&gt; 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-long [gsname="facetname"]&gt; 
      &lt;guided-else-facet-long&gt;&lt;/guided-if-facet-long&gt; </code> </p> </td> 
   <td colname="col2"> <p>Den här villkorstaggen är sann när antalet fasettvärden överstiger det längdtröskelvärde som definieras i konfigurationen. Använd den för att visa en fasett som ett annat element i användargränssnittet (till exempel en trunkerad lista eller en rullningsruta) när listan är för lång. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;class="long_facet"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;div&nbsp;class="facet"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/div&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-long&gt; 
      &nbsp;&lt;/guided-facet&gt; </code> </p> <p>Du kan också använda det här villkoret utanför kontexten för ett <span class="codeph">-block med stödfunktioner för </span> genom att referera till en viss aspekt direkt med attributet <span class="codeph"> <span class="varname"> för gsname </span> </span>. </p> <p> <code class="syntax html"> &lt;guided-if-facet-long&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;very&nbsp;long! 
      &lt;/guided-if-facet-long&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-selected [gsname="facetname"]&gt; 
      &lt;guided-else-facet-selected&gt;&lt;/guided-if-facet-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>Den här villkorstaggen är sann när användaren klickar på den minst en gång och ett fasettvärde är markerat. Den kan användas för att visa eller dölja HTML- eller gs-taggar beroende på om någon klickar på en aspekt. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This&nbsp;facet&nbsp;has&nbsp;been&nbsp;selected.&nbsp;&nbsp;You&nbsp;can&nbsp;no&nbsp;longer&nbsp;refine&nbsp;it. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-selected&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-selected&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Du kan också använda det här villkoret utanför kontexten för ett <span class="codeph">-block med stödfunktioner för </span> genom att referera till en viss aspekt direkt med attributet <span class="codeph"> gsname </span>. </p> <p> <code class="syntax html"> &lt;guided-if-facet-selected&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The&nbsp;category&nbsp;facet&nbsp;is&nbsp;selected! 
      &lt;/guided-if-facet-selected&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-single [gsname="facetname"]&gt; 
      &lt;guided-else-facet-single&gt;&lt;/guided-if-facet-single&gt; </code> </p> </td> 
   <td colname="col2"> <p>Den här villkorstaggen är true när det bara finns ett facet-värde. Den kan användas för att ändra visningen av ansiktet när det inte går att förfina resultatet. </p> <p> <code class="syntax html"> &lt;guided-facet&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Facet&nbsp;is&nbsp;not&nbsp;refinable. 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-else-facet-single&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-facet-single&gt; 
      &lt;/guided-facet&gt; </code> </p> <p>Du kan också använda det här villkoret utanför kontexten för ett <span class="codeph">-block med stödfunktioner för </span> genom att referera till en viss aspekt direkt med attributet <span class="codeph"> <span class="varname"> för gsname </span> </span>. </p> <p> <code class="syntax html"> &lt;guided-if-facet-single&nbsp;gsname="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There&nbsp;is&nbsp;only&nbsp;one&nbsp;value&nbsp;in&nbsp;the&nbsp;category&nbsp;facet! 
      &lt;/guided-if-facet-single&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-has-values [gsname="facetname"]&gt; 
      &lt;guided-else-facet-has-values&gt;&lt;/guided-if-facet-has-values&gt; </code> </p> </td> 
   <td colname="col2"> <p>Med det här villkoret kan du kontrollera om den angivna aspekten har några värden alls. Du kan använda den för att visa en annan aspekt i stället för en tom. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-total-count gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar det totala antalet resultat som ligger inom den angivna aspekten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value gsname=" <span class="varname"> associated custom facet value </span>"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Matar ut strängen för ett värde som är associerat med ansiktet. Du kan ha minst 0 fält kopplade till en fasett. Om du har associerade fält är det sällsynt och som stöd för det konfigurerar du transportmallen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-facet-value gsname=" <span class="varname"> associated custom facet value </span>" /&gt;&lt;guided-else-facet-value&gt;&lt;/guided-if-facet-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>Testar om faktavärdet har ett associerat fältvärde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-link&gt; value  </span>"]+&gt;&lt;/guided-facet-link&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>Skapar en länk runt begränsningsvärdesträngen som kunden kan klicka på. Sökvägen genereras automatiskt för att begränsa resultatet med det aktuella facet-värdet. Det har stöd för att skicka attribut direkt till ankartaggen. </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;class="facetlink"&gt;&lt;guided-facet-value/&gt;&lt;/guided-facet-link&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapar en egen länk till ett facet-värde. </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-lt/&gt;a&nbsp;href="&lt;guided-facet-value-path/&gt;"&lt;guided-gt/&gt;&lt;guided-facet-value/&gt;&lt;/a&gt; 
      &lt;/guided-facet-values&gt; </code> </p> <p>Som standard är värdet URL escape. Du kan dock lägga till ytterligare ett kodningslager genom att ange vilket läge du vill använda som escape-parameter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-children&gt;&lt;/guided-facet-value-children&gt; </span> </p> </td> 
   <td colname="col2"> <p>När <span class="codeph"> &lt;guided-facet-values&gt; </span> itererar genom varje facet-värde itererar den här taggen igenom alla underordnade värden för en kapslad aspekt. I den här taggen använder du de typiska facet-taggarna för att skapa länkar, skapa ångra-länkar och visa ansiktsvärden. Den här taggen måste finnas i <span class="codeph"> &lt;guided-facet-values&gt; </span> eftersom den inte har kapslade slingor. </p> <p>Ett exempel på hur du använder den här taggen är följande: </p> <p> <code class="syntax html"> &lt;guided-facet-values&gt; 
      &nbsp;&nbsp;&lt;guided-facet-link&nbsp;title='&lt;guided-facet-value&nbsp;/&gt;'&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&lt;guided-if-facet-value-has-children&gt; 
      &nbsp;&nbsp;&nbsp;&lt;guided-facet-value-children&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-facet-link&nbsp;title='&lt;guided-facet-value&nbsp;/&gt;'&gt;&lt;guided-facet-value&nbsp;/&gt;&nbsp;(&lt;guided-facet-count&nbsp;/&gt;)&lt;/guided-facet-link&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/guided-facet-value-children&gt; 
      &nbsp;&nbsp;&lt;/guided-if-facet-value-has-children&gt; 
      &lt;/guided-facet-values&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-value-has-children&gt; 
      &lt;guided-else-facet- 
      value-has-children&gt; 
      &lt;/guided-if-facet-value-has-children&gt; </code> </p> </td> 
   <td colname="col2"> <p>Testar om det aktuella ansiktsvärdet har underordnade värden. Rekommenderas att användas innan <span class="codeph"> &lt;guided-facet-value-children&gt; </span>-taggar används. Satsen else är valfri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-above-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-above-length-threshold&amp;gt&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Avgör om det aktuella facet-värdet i facet-values-slingan ligger över längdtröskeln. Det används vanligtvis för att endast visa värden under tröskelvärdet i en lång aspekt (såvida inte användaren tidigare har valt länken "Se mer" som visas under ansiktet). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;guided-else[-not]-facet-value-equals-length-threshold&amp;gt;
    
    &amp;lt;/guided-if[-not]-facet-value-equals-length-threshold&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Avgör om det aktuella facet-värdet i facet-values-slingan är lika med längdtröskeln. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-link&gt;&lt;/guided-facet-value-undo-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar en ångra-länk för ett visst angivet facet-värde. Använd den för att visa en ångra-länk bredvid ett valt facet-värde. Eftersom den här ångra-länken endast ångrar det markerade värdet skiljer den sig från <span class="codeph"> &lt;guided-facet-undo-link&gt; </span> som avmarkerar alla markerade värden. </p> <p> <p>Obs!  Om begränsningen inte har ett flervalsbeteende har de två ångra-länkarna samma beteende. Det innebär att ansiktet bara kan ha ett valt värde. </p> </p> <p>Om begränsningen inte är markerad är länken den aktuella sökvägen. Använd den här taggen endast i en <span class="codeph">-slinga med guidade ansiktsvärden </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>30 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-value-undo-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapa en egen länk för Ångra av facet-värde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>31 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-undo-path gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapa en egen Ångra-länk för facet. </p> <p> Liknar <span class="codeph"> &lt;guided-facet-undo-link&gt; </span>-taggen förutom att den ger dig den råa sökvägen för att skapa en egen ångra-länk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>32 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-facet-value-matches facetname="facetname" value="value"&gt;&lt;guided-else-facet-value-matches&gt; 
      &lt;/guided-if-facet-value-matches&gt; </code> </p> </td> 
   <td colname="col2"> <p>Visa HTML när den angivna aspekten har det valda värdet eller det enskilda värdet "value". Den här uppsättningen taggar används ofta för att visa en aspekt baserat på det värde som valts i en annan aspekt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>33 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-facet-behavior gsname=" <span class="varname"> facetname </span>" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Bestäm en fasets beteende, till exempel normal, klisterlappande eller flerval. Det är användbart för kunder som tar emot XML-resultat och vill dynamiskt ändra hur aspekten visas baserat på dess beteende. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>34 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-facet[-not]-visible&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Innehållet som den här taggen figursätter döljs eller visas baserat på ansiktets synlighetstillstånd. Om en affärsregel döljer eller visar aspekten direkt, döljs eller visas allt innehåll i aspekten. Dessa taggar behöver inte figursättas runt ansiktet. </p> <p> Ett vanligt användningsområde för den här taggen är att dölja visningsnamnet när namnet är utanför ansiktet. Om du placerar den här taggen runt visningsnamnet försvinner namnet när ansiktet är dolt. </p> <p>Den här taggen ersätter zonen och har många av samma prestandafördelar som att använda zoner. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Breadcrumb {#section_9B39B71FA6EC49FA8D88AD8A3BA987F7}

Se [Om vägbeskrivningar](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb&gt; breadcrumbname  </span>"]&gt;&lt;/guided-breadcrumb&gt; </span><span class="varname"> </span></p> </td> 
   <td colname="col2"> <p>Looptaggen för vägbeskrivningen. Allt innehåll mellan den inledande och avslutande taggen itereras för varje frågenummer i det aktuella läget. </p> <p>Om <span class="codeph"> <span class="varname"> gsname </span> </span> utelämnas används det synliga kolumnnamnet "default". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-link&gt;&lt;/guided-breadcrumb-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapar en länk i vägbeskrivningsfilen. Standardbeteendet är goto-beteendet. Om länken fungerar annorlunda använder du det valfria attributet <span class="codeph"> <span class="varname"> </span> </span> för att ange "remove" eller "drop". Alla attribut som ingår i taggen skickas vidare till den resulterande ankartaggen. </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&nbsp;gsname="remove"&nbsp;class="bc_link"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Taggen value skriver ut det omformade värdet för den aktuella urklippsalternationen. Den används endast i kontexten för ett <span class="codeph">-block av typen guided-bar.</span> </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-breadcrumb-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Etikettaggen genererar en etikett för ett vägbeskrivningsvärde som anger vilken aspekt som valdes för att generera det vägbeskrivande objektet. Det används bara i kontexten för ett <span class="codeph">-block med stödlinjer </span>. </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;:&nbsp;&lt;guided-breadcrumb-value/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to search-eng version, 2/1/2013--> <code> &lt;guided-if-breadcrumb-label&gt; 
      &lt;guided-else- 
      breadcrumb-label&gt; 
      &lt;guided-if-breadcrumb-label /&gt; </code> </p> </td> 
   <td colname="col2"> <p>Den här villkorstaggen används för att villkorligt visa innehåll om det aktuella kolumnvärdet har en etikett. Den används endast för att visa etiketter och relaterat innehåll när det finns en etikett. Det används bara i kontexten för ett <span class="codeph">-block med stödlinjer </span>. </p> <p> <code class="syntax html"> &lt;guided-breadcrumb&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-label/&gt;: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-if-breadcrumb-label&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-breadcrumb-value/&gt;&lt;/guided-breadcrumb-link&gt; 
      &lt;/guided-breadcrumb&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-breadcrumb-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>Används för att skapa en egen felsökningslänk. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Menyer {#section_1D489ADF041F4351A66E5D5742125CA8}

Se [Om menyer](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu gsname="menuname"&gt;&lt;/guided-menu&gt; </span> </p> </td> 
   <td colname="col2"> <p>Det här är menyvärdeslingans iteratortagg. Använd attributet <span class="codeph"> gsname </span> för att identifiera vilken uppsättning menyalternativ som visas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-link&gt;&lt;/guided-menu-item-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ger dig URL-adressen för att förfina den aktuella sökningen efter menyalternativet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-option&gt; </span> </p> </td> 
   <td colname="col2"> <p>Vanligtvis visas en meny i en markeringskontroll i en mall. Den här taggen gör det enklare att skapa markeringskontrollen eftersom HTML-koden genereras som alternativ för markeringskontrollen. </p> <p>Följande kodblock: </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
      &lt;guided-menu&nbsp;gsname="sort"&gt; 
      &lt;guided-menu-item-option/&gt; 
      &lt;/guided-menu&gt; 
      &lt;/select&gt; </code> </p> <p>Kan generera HTML enligt följande: </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sort"&nbsp;onchange="gcGo(this);"&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=relevance;sp_sfvl_field=product-type|category|size;"&nbsp;selected="selected"&gt;Sort&nbsp;by&nbsp;Relevance&lt;/option&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=avail-code;sp_sfvl_field=product-type|category|size;"&gt;Sort&nbsp;by&nbsp;Availability&lt;/option&gt; 
      &nbsp;&nbsp;&lt;option&nbsp;value="?sort=price;sp_sfvl_field=product-type|category|size;"&gt;Sort&nbsp;by&nbsp;Price&lt;/option&gt; 
      &lt;/select&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-value /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar strängen för värdet som är associerat med menyn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-label /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar strängen för etiketten som är associerad med menyn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-menu-item-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar sökvägssträngen. Använd taggen om du vill lägga till en parameter i sökvägen och skapa en anpassad länk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-menu-item-selected&gt; 
      &lt;guided-else-menu- 
      item-selected&gt; 
      &lt;/guided-if-menu-item-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>Returnerar ett tal på 1 eller 0 som anger om det aktuella menyalternativet är markerat. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Pagenav {#section_2EE397635C514BBC8D668278EA314F35}

Sidnavigeringstaggarna kan användas för att skapa en uppsättning länkar som gör det möjligt för en användare att bläddra igenom sökresultaten.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-pages&gt;&lt;/guided-pages&gt; </span> </p> </td> 
   <td colname="col2"> <p>Loopkoden för sidnavigeringen. Allt innehåll mellan de inledande och avslutande taggarna itereras för varje sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapar en länk i sidnavigeringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-link gsname="first|prev|next|last|viewall|viewpages"&gt;&lt;/guided-page-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapar en länk till den första, föregående, nästa eller sista sidan. Den kan också skapa en länk för att visa alla sidor på en sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-number /&gt; </span> </p> </td> 
   <td colname="col2"> <p> Returnerar en sträng med det aktuella sidnumret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if-page-selected&gt; 
      &lt;guided-else-page- 
      selected&gt; 
      &lt;/guided-if-page-selected&gt; </code> </p> </td> 
   <td colname="col2"> <p>Den här uppsättningen villkorstaggar är true om sidan som itereras över är markerad. Det används vanligtvis för att visa sidnumret på ett annat sätt i sidnavigeringskontrollen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-prev&gt; 
      &lt;guided-else-page- 
      prev&gt; 
      &lt;/guided-if[-not]-page-prev&gt; </code> </p> </td> 
   <td colname="col2"> <p> Den här uppsättningen villkorstaggar är true om den aktuella sidan har en tidigare sida. Det används vanligtvis för att visa en tidigare länk i sidnavigeringen när det passar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-next&gt; 
      &lt;guided-else-page- 
      next&gt; 
      &lt;/guided-if[-not]-page-next&gt; </code> </p> </td> 
   <td colname="col2"> <p> Den här uppsättningen villkorstaggar är true om den aktuella sidan har en nästa sida. Det används vanligtvis för att visa en tidigare länk i sidnavigeringen när det passar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewall&gt; 
      &lt;guided-else-page- 
      viewall&gt; 
      &lt;/guided-if[-not]-page-viewall&gt; </code> </p> </td> 
   <td colname="col2"> <p> När en sökning returnerar en stor resultatmängd kanske du inte vill kunna visa alla resultat. Du kan därför använda den här uppsättningen villkorstaggar för att avgöra när länken Visa alla ska visas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-page-viewpages&gt; 
      &lt;guided-else-page- 
      viewpages&gt; 
      &lt;/guided-if[-not]-page-viewpages&gt; </code> </p> </td> 
   <td colname="col2"> <p>Du kan använda den här uppsättningen villkorstaggar för att avgöra när länken Visa sidor ska visas. Det används vanligtvis för att låta en kund visa vissa sidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> 

    &amp;lt;guided-else-page-link&amp;gt;
    &amp;lt;/guided-if[-not]-page-link&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Testar om sidnavigeringen har en första sida, föregående sida, nästa sida och så vidare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matched search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-page-total /&gt; </span> </p> </td> 
   <td colname="col2"> <p> Returnerar en sträng med det totala antalet sidor med sökresultat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-pagination gsname= 
      "pagination_name"&gt;&lt;/guided-pagination&gt; </code> </p> </td> 
   <td colname="col2"> <p>Använd taggen <span class="codeph"> guided-pagination </span> för att definiera ett område där alla sidnumreringstaggar relaterar till en viss sidnumreringsinställning om du har angett några sidnavigeringsinställningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> 

    next|last|viewAll|viewpages]/&amp;gt;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Skapar en egen länk i sidnavigeringen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-page-high-eq-last&gt; 
      &lt;guided-else-page- 
      high-eq-last&gt; 
      &lt;/guided-if-page-high-eq-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>Testar om den översta sidan i sidnavigeringen är lika med det totala antalet sidor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-page-low-eq-first&gt; 
      &lt;guided-else-page-low-eq-first&gt; &lt;/guided-if-page-low-eq-first&gt; </code> </p> </td> 
   <td colname="col2"> <p>Testar om den lägsta sidan i sidnavigeringen är lika med den. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-page-is-multipage&gt; &lt;guided-else-page-is-multipage&gt; &lt;/guided-if-page-is-multipage&gt; </span> </p> </td> 
   <td colname="col2"> <p>Testar om det finns en enda resultatsida eller flera resultatsidor. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Senaste sökningar {#section_8CD907521F584257B475595B01A5964B}

Du kan använda taggar för senaste sökningar för att skapa en uppsättning länkar som gör att en användare snabbt kan köra en tidigare sökning, som i följande exempel:

```
<guided-if-recent-searches> 
    <span>Recent Searches</span><br/> 
    <guided-recent-searches> 
        <guided-recent-searches-link><guided-recent-searches-value></guided-recent-searches-link><br/> 
    </guided-recent-searches> 
    <guided-recent-searches-clear-link>Clear Recent Searches</guided-recent-searches-clear-link> 
</guided-if-recent-searches>
```

Se [Konfigurera senaste sökningar](../c-about-design-menu/t-configuring-recent-searches.md#task_E9E8ACA04C90484F8AFD5262167B2562).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches&gt;&lt;/guided-recent-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p>Slingtaggen för de senaste sökningarna. Allt innehåll mellan de inledande och avslutande taggarna itereras för varje sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-recent-searches-link [attr="value"]+&gt; 
      &lt;/guided-recent-searches-link&gt; </code> </p> </td> 
   <td colname="col2"> <p>Gör att du kan skapa en länk till en nyligen utförd sökning. Det har stöd för att skicka HTML-attribut direkt till ankartaggen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gör att du kan hämta den relativa URL-sökvägen för en nyligen utförd sökning, inom en <span class="codeph">-slinga med guidade sökningar </span>. Vanligtvis använder du <span class="codeph"> guided-recent-search-link </span>. Men om du vill skapa en egen länk kan du använda den här taggen. Följande är ett exempel: </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;a&amp;nbsp;href="&lt;guided_recent_searches_path&gt;"&gt;&lt;guided-recent-searches-value&gt;&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-value&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gör att du kan hämta den frågeterm som är associerad med en senaste sökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-link&gt;&lt;/guided-recent-searches-clear-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gör att du kan ge dina kunder möjlighet att rensa nyligen sparade sökningar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-recent-searches-clear-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar sökvägen som <span class="codeph"> &lt;guided-recent-searches-clear-link&gt; </span> använder så att du kan skapa en egen länk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 

    &amp;lt;/guided-if-recent-searches;   &lt;/p>  &lt;/td>
<td colname="col2"> <p>Här kan du visa de senaste sökningarna när en kund har gjort en nyligen utförd sökning. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Menade du {#section_C1EB3B9D8E1242798A6E04609D1E3543}

Du kan använda Menade-taggar för att skapa en uppsättning länkar till förslag när en sökning inte ger några resultat och söktermen inte finns i kontots ordlista. Följande är ett exempel på hur du använder Menade-taggar:

```
<guided-if-suggestions> 
    <span>Did You Mean?</span><br/> 
    <guided-suggestions> 
        <guided-suggestion-link><guided-suggestion/></guided-suggestion-link><br/> 
    </guided-suggestions> 
</guided-if-suggestions>
```

Se [Om Menade du](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestions&gt;&lt;/guided-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Det här är loopkoden för att repetera förslagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Matches search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestion-link&gt;&lt;/guided-suggestion-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapar en länk till det angivna förslaget. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Newly added from search-eng version, 2/1/2013--> <span class="codeph"> &lt;guided-suggestion-value /&gt; </span> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-suggestions&gt;&lt;guided-else[-not]- 
      suggestions&gt;&lt;/guided-if[-not]-suggestions&gt; </code> </p> </td> 
   <td colname="col2"> <p>Gör att du kan testa om det finns några förslag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-path /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar sökvägssträngen till förslaget. Du kan använda den för att skapa en egen ankartagg. Vanligtvis används <span class="codeph"> guided-draft-link </span> i stället. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ett förslag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-result-count /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Resultatantal för förslaget. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-autosearch&gt; 
      &lt;guided-else[-not]-suggestion-autosearch&gt; 
      &lt;/guided-if[-not]-suggestion-autosearch&gt; </code> </p> </td> 
   <td colname="col2"> <p>Gör att du kan testa om automatisk sökning med förslag på nollresultat har utförts, om den här funktionen är aktiverad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-suggestion-original-query /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar den ursprungliga frågan om automatisk sökning utfördes. </p> <p>Exempel: </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-autosearch&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;Search&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;&nbsp;instead&nbsp;of&nbsp;&lt;guided-suggestion-original-query&nbsp;/&gt; 
      &lt;/guided-if-suggestion-autosearch&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-suggestion-low-results&gt; 
      &lt;guided-else[-not]-suggestion-low-results&gt; 
      &lt;/guided-if[-not]-suggestion-low-results&gt; </code> </p> </td> 
   <td colname="col2"> <p>Det här villkoret är sant om det finns förslag på grund av ett lågt resultatantal, om den här funktionen är aktiverad. </p> <p>Här följer ett exempel på hur du använder den här taggen: </p> <p> <code class="syntax html"> &lt;guided-if-suggestion-low-results&gt; 
      &nbsp;&nbsp;&nbsp;You&nbsp;have&nbsp;a&nbsp;low&nbsp;result&nbsp;count&nbsp;for&nbsp;&lt;guided-query-param&nbsp;gsname="q"&nbsp;/&gt;. 
      &nbsp;&nbsp;&nbsp;Did&nbsp;you&nbsp;mean:&nbsp;&lt;guided-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion-link&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;guided-suggestion&nbsp;/&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/guided-suggestion-link&gt;&lt;guided-if-not-last&gt;,&nbsp;&lt;/guided-if-not-last&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/guided-suggestions&gt; 
      &lt;/guided-if-suggestion-low-results&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Komplettera automatiskt {#section_897316BEE1454E839A56B565CA4AF018}

Följande taggar kan användas för att lägga till automatisk ifyllnad i sökformuläret. Taggar för head-content och form-content krävs för att automatisk komplettering ska fungera korrekt. Vi rekommenderar att du använder taggarna i stället för att hårdkoda Javascript och CSS som fylls i automatiskt i din presentationsmall. Orsaken är att taggar gör att dina mallar kan hämta nya cacheminne-ID när du ändrar inställningarna för automatisk komplettering utan att behöva uppdatera mallen manuellt.

Se [Om Komplettera automatiskt](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-autocomplete&gt; &lt;guided-else-autocomplete&gt; &lt;/guided-if-autocomplete&gt; </span> </p> </td> 
   <td colname="col2"> <p>Identifierar om funktionen Komplettera automatiskt är aktiverad. Du kan använda taggarna för att alternativt hämta huvud- och formulärinnehåll som krävs för automatisk ifyllning. Detta gör att du kan aktivera och inaktivera funktionen och inte behöver ändra presentationsmallarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-css /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Används i huvudet på presentationsmallen och ersätts av lämpligt CSS-skript för automatisk komplettering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-form-content /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Används i sökformuläret (mellan taggarna <span class="codeph"> &lt;form&gt; </span> och <span class="codeph"> &lt;/form&gt; </span>) i presentationsmallen i stället för att de automatiska kompletta taggarna i formuläret kodas automatiskt. Taggarna ersätts med lämplig HTML som krävs för att automatisk komplettering ska fungera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-ac-javascript /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapar länkarna till JavaScript-koden som slutförs automatiskt. För bästa prestanda rekommenderar vi att du placerar den här taggen längst ned på sidan före den avslutande body-taggen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lagra {#section_A33E25DB5E67404A823BD9618665B773}

Använd följande taggar för att testa och visa butiken där en användare befinner sig.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-store /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar den aktuella butiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store-defined&gt; &lt;guided-else-store-defined&gt; &lt;/guided-if-store-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>Identifierar om användaren finns i en butik. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-store gsname="store"&gt; &lt;guided-else-store&gt; &lt;/guided-if-store&gt; </span> </p> </td> 
   <td colname="col2"> <p>Identifierar om användaren finns i arkivet som anges av parametern <span class="codeph"> gsname </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zoner {#section_B9B3179E000C42D492E1541F2FE44CB5}

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-zone gsname="zone area"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Du kan kapsla in allt innehåll i zontaggar för att skapa en zon utanför det området. På så sätt kan du använda affärsregler för att visa zonen efter behov. Som standard visas alltid zoner. Du kan använda de valfria sök- och facet-parametrarna för att ange vilken sökning eller aspekt som är associerad med zonen. Med den här funktionen kan programmet hoppa över sökningar eller ansikten när en zon är dold, vilket förbättrar sökningens prestanda. Attributen height och width är valfria och används för att konfigurera hur platshållaren visas i Visual Rule Builder när en zon tas bort. </p> <p> Använd taggen <span class="codeph"> guided-if-facet[-not]-visible </span> i stället för zonen där det är möjligt. Det förenklar presentationsmallen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-zone gsname="zone area"&gt; &lt;guided-else-zone&gt; &lt;/guided-if-zone&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med den här uppsättningen taggar kan du testa om en zon visas just nu. Det är användbart när du har innehåll någon annanstans på sidan som du bara vill visa när zonen visas. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Loopindikatorer {#section_387322CA0AA843A2ACF2795C328673E9}

Du kan använda var och en av följande slingindikatorer i något av dessa slingblock:

* guidade resultat
* guided-facet-values
* guided-breadcrumb
* guidade menyalternativ
* guidade sidor

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-first&gt;&lt;guided-else[-not]-first&gt; 
      &lt;/guided-if[-not]-first&gt; </code> </p> </td> 
   <td colname="col2"> <p>Detta villkor är sant när den aktuella iterationen är den första iterationen i slingan. Det behöver inte innebära det första resultatet eller den första sidan, utan den första som visas. Om besökaren befinner sig på sidan 2 i en resultatuppsättning som är 10 per sida blir den första upprepningen resultatet 11. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-last&gt;&lt;guided-else[-not]-last&gt; 
      &lt;/guided-if[-not]-last&gt; </code> </p> </td> 
   <td colname="col2"> <p>Detta villkor är sant när den aktuella iterationen är den sista upprepningen i slingan. Det behöver inte innebära det sista resultatet eller den sista sidan, utan den sista som visas i det aktuella sammanhanget (sidan). Om besökaren finns på sidan 1 i en resultatuppsättning som innehåller 200 resultat men bara har 10 resultat per sida blir den senaste upprepningen 10 i stället för resultatet 200. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng version, 2/1/2013--> <code> &lt;guided-if[-not]-odd&gt;&lt;guided-else[-not]-odd&gt; 
      &lt;/guided-if[-not]-odd&gt; </code> </p> </td> 
   <td colname="col2"> <p>Detta villkor är sant när den aktuella iterationen är en udda iteration av slingan (jämfört med en jämn iteration). Detta är praktiskt när du vill visa olika radfärger. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>Detta villkor är sant när den aktuella iterationen är en jämn iteration av slingan (jämfört med en udda iteration). Detta är praktiskt när du vill visa olika radfärger. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>Detta villkor är sant när den aktuella iterationen är en jämn iteration av slingan. Detta är praktiskt när du vill visa olika radfärger. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>Innehåller texten mellan dem om den aktuella iterationen varken är den första eller den sista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>Innehåller texten mellan dem om den aktuella iterationen är den första eller sista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ett heltal (med början från 0) vars värde ökar för varje iteration i slingan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-loop-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ett heltal (med början från 1) vars värde ökar för varje iteration i slingan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Övrigt språk {#section_BFE8DC98E26F4D7BB60FEC54D9A5DC6C}

Följande taggar är tillgängliga så att du kan göra mer avancerade saker med mallen, som att skapa egna minifacet.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-current-path&gt; </span> </p> </td> 
   <td colname="col2"> <p>Ger dig den aktuella sökvägen som används. Vanligtvis används den för att skapa en länk som lägger till en ny parameter i den befintliga sökningen. Som standard är sökvägen URL escape. Du kan ange vilket läge du vill använda för escape-parametern. </p> <p>Exempel: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path&nbsp;/&gt;&amp;lang=fr"&gt; 
      French&nbsp;Version </code> </p> <p>I det här exemplet använder en regel för sökbearbetning språk för att välja den franska versionen. </p> <p>Den aktuella sökvägen har alltid minst en frågeparameter. Om det inte finns några andra frågeparametrar anges det till <span class="codeph"> q=* </span>, vilket gör det enklare att lägga till fler parametrar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> Grundsökväg  </span> </p> </td> 
   <td colname="col2"> <p> Om du vill skapa en länk med bassökvägen använder du <span class="codeph"> / </span> i början av <span class="codeph"> href </span> och lägger till i parametrar. </p> <p> <code class="syntax html"> &lt;a&nbsp;href="/"&gt;All&nbsp;Products&lt;/a&gt; 
      Would&nbsp;create&nbsp;a&nbsp;link&nbsp;"All&nbsp;Products"&nbsp;to&nbsp;your 
      basepath,&nbsp;for&nbsp;example&nbsp;https://search.mycompany.com/ 
       </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> 
     <!--Updated to match search-eng, 2/1/2013--> <span class="codeph"> &lt;guided-query-param gsname="query_parameter"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Här kan du hämta det befintliga värdet för en frågeparameter som finns på URL:en. Om parametern inte finns returnerar den här taggen en tom sträng. Om du inte anger ett escape-alternativ som den returnerade strängen automatiskt HTML-escape-konverterare kan du ange antingen HTML eller URL-escape. </p> <p>Exempel: </p> <p> 

    &amp;lt;guided-query-param&amp;nbsp;gsname=&quot;q&quot;&amp;nbsp;/&amp;gt;
    ger&amp;nbsp;du&amp;nbsp;the&amp;nbsp;value&amp;nbsp;byxor
    
    &amp;lt;guided-query-param&amp;nbsp;gsname=&quot;lang&quot;&amp;nbsp;/ gt;
    ger&amp;nbsp;du&amp;nbsp;the&amp;nbsp;value&amp;nbsp;en
    
    &amp;lt;guided-query-param&amp;nbsp;gsname=&quot;test&quot;&amp;nbsp;/&amp;gt;
    ger&amp;nbsp;du&amp;nbsp;an&amp;nbsp;empty&amp;nbsp;string 
    &amp;nbsp;
    &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;   &lt;/p>  &lt;/td>
</tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-query-param-name gsname="param#" offset="offset_number" /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med guidad sökning avses ett frågenummer som används i kontrollen för vägbeskrivningar. <span class="codeph"> Med hjälp av guided-query-param-name  </span> kan du definiera parametrar som en del av en länk i presentationsmallen där guidad sökning anger rätt frågenummer för dig. <span class="codeph">-spelet </span> har ett "x" i sig, som den guidade sökningen ersätter med rätt nummer. Förskjutningsvärdet kan vara 0 - 15, där 0 anger att nästa tillgängliga frågenummer används. En siffra anger att du vill lägga till 1 i den och så vidare. </p> <p>I kombination med <span class="codeph"> guidad-aktuell-sökväg </span> kan du skapa en egen minifacet-länk eller tillåta en extra detaljnivå. </p> <p>Exempel: </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;&amp;&lt;guided-query-param-name&nbsp;gsname="q#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=mens&amp;&lt;guided-query-param-name&nbsp;gsname="x#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=category"&nbsp;&gt;Category:Men&lt;/a&gt;&nbsp; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </code> </p> <p> <code class="syntax html"> &lt;a&nbsp;href="&lt;guided-current-path 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;&amp;&lt;guided-query-param-name&nbsp;gsname="sp_q_exact_#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=mens&amp;&lt;guided-query-param-name&nbsp;gsname="sp_x_#"&nbsp;offset="0" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=category&amp;&lt;guided-query-param-name&nbsp;gsname="sp_q_exact_#"&nbsp;offset="1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=Jeans&amp;&lt;guided-query-param-name&nbsp;gsname="sp_x_#"&nbsp;offset="1" 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/&gt;=product-type"&nbsp;&gt;Cat:Men&nbsp;-&nbsp;Product:Jeans&lt;/a&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-include gsfile="filename" /&gt; </span> </p> </td> 
   <td colname="col2"> <p> Gör att du kan ta med andra mallfiler. Den här funktionen innebär att du kan skapa flera mallar med hjälp av undermallar som moduler. </p> <p>I följande exempel inkluderas <span class="filepath">-stavfel </span> och <span class="filepath">-ansikten </span>-filer: </p> <p> <code class="syntax html"> &lt;guided-include&nbsp;gsfile='breadcrumbs.tmpl'&nbsp;/&gt; 
      &lt;guided-include&nbsp;gsfile='facets.tmpl'&nbsp;/&gt; </code> </p> <p>Dynamiska inkluderingar stöds inte. Det innebär att <span class="codeph"> gsfile </span> inte kan vara en variabel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p> Identifierar hur lång tid sökningen tog. Det returnerade söktidsvärdet anges i ms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-fall-through-searches&gt; </span> </p> </td> 
   <td colname="col2"> <p> Returnerar antalet kärnsökningar som används för att skapa sidan med sökresultat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW 1/17/2013--> <span class="codeph"> &lt;guided-if-fall-through-search&gt;&lt;/guided-if-fall-through-search&gt; </span> </p> </td> 
   <td colname="col2"> <p>Testar om antalet kärnsökningar är större än ett. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-even&gt;&lt;guided-else[-not]-even&gt; 
      &lt;/guided-if[-not]-even&gt; </code> </p> </td> 
   <td colname="col2"> <p>Detta villkor är sant när den aktuella iterationen är en jämn iteration av slingan (jämfört med en udda iteration). Detta är praktiskt när du vill visa olika radfärger. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-alt&gt;&lt;guided-else[-not]-alt&gt; 
      &lt;/guided-if[-not]-alt&gt; </code> </p> </td> 
   <td colname="col2"> <p>Detta villkor är sant när den aktuella iterationen är en jämn iteration av slingan. Detta är praktiskt när du vill visa olika radfärger. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-inner&gt;&lt;guided-else[-not]-inner&gt; 
      &lt;/guided-if[-not]-inner&gt; </code> </p> </td> 
   <td colname="col2"> <p>Innehåller texten mellan dem om den aktuella iterationen varken är den första eller den sista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if[-not]-outer&gt;&lt;guided-else[-not]-outer&gt; 
      &lt;/guided-if[-not]-outer&gt; </code> </p> </td> 
   <td colname="col2"> <p>Innehåller texten mellan dem om den aktuella iterationen är den första eller sista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <code> &lt;guided-if-first-search&gt;&lt;guided-else-first-search&gt; 
      &lt;/guided-if-first-search&gt; </code> </p> </td> 
   <td colname="col2"> <p>Här kan du kontrollera om du är med i den inledande sökningen eller inte (frågan var resultatet av en sökning från sökrutan). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-search-url /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Du kan använda den här taggen i mallen för att spara dig från att hårdkoda sökformulärets åtgärd. Den upptäcker när du befinner dig i scenvyn eller Live-miljön och ändras därefter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-query-param-defined gsname="query_parameter"&gt; &lt;guided-else-query-param-defined&gt; &lt;/guided-if-query-param-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med den här uppsättningen taggar kan du testa vilka CGI-parametrar som definieras i söksökvägen. Du kan bara testa parametrarnas värden om de är definierade. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-next-query-number&gt; </span> </p> </td> 
   <td colname="col2"> <p>Motorn för guidad sökning som driver mallen har begreppet flytande frågenummer där varje ny länk som motorn skapar använder nästa tillgängliga frågenummer. Med den här taggen kan du hämta nästa frågenummer eller förskjutningar så att du kan skapa anpassade länkar som detaljerar i resultatuppsättningen. Med förskjutning kan du förskjuta till nästa frågenummer. Om du t.ex. har valt en aspekt är nästa frågenummer 2, med förskjutningen 1 är det returnerade frågenumret 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-custom-var gsname="custom_variable"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Här kan du hämta det befintliga värdet för en anpassad variabel som bearbetningsreglerna definierar. Om du inte anger ett escape-alternativ som den returnerade strängen automatiskt HTML escape-konverteras kan du ange antingen <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span> eller <span class="codeph"> 0 </span>. Om du använder en bearbetningsregel för att kopiera en inkommande CGI-parameter till en anpassad variabel och sedan visa eller använda variabeln i mallen med escape-inställningen none eller js, kan du skapa en XSS-säkerhetslucka i sökningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-custom-var-defined gsname="custom_variable"&gt; &lt;guided-else-custom-var-defined&gt; &lt;/guided-if-custom-var-defined&gt; </span> </p> </td> 
   <td colname="col2"> <p>Aktiverar testning om en anpassad variabel har definierats i bearbetningsreglerna (frågerensning, försöksbearbetning och eftersökningsbearbetning). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-general-field gsname="searchname" field="fieldname"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Här kan du visa innehållet i ett allmänt fält som är definierat i transportmallen. Om du inte anger ett escape-alternativ kodas den returnerade strängen i det format som du har angett i fältets transportmall. Om du anger ett escape-alternativ tillämpas det ovanpå det format som du kodar fältet som i transportmallen. Du kan ange antingen <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span>, <span class="codeph"> json </span> eller <span class="codeph"> 0 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-general-field gsname="searchname" field="fieldname"&gt; &lt;guided-else-general-field&gt; &lt;/guided-if-general-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Aktiverar testning om innehållet i ett allmänt fält, enligt definitionen i transportmallen, finns. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-cookie-value gsname="cookie_name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gör att du kan hämta värdet för en cookie, förutsatt att cookien är tillgänglig. Om du inte anger ett escape-alternativ som den returnerade strängen automatiskt HTML escape-konverteras kan du ange antingen <span class="codeph"> html </span>, <span class="codeph"> url </span>, <span class="codeph"> js </span>, <span class="codeph"> json </span> eller <span class="codeph"> 0 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-cookie gsname="cookie_name"&gt; &lt;guided-else-cookie&gt; &lt;/guided-if-cookie&gt; </span> </p> </td> 
   <td colname="col2"> <p>Aktiverar testning om det finns en cookie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>23 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-banner gsname="banner area"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skapar banderollen för ett visst område. De valfria attributen width och height används i Visual Rule Builder för att aktivera visning av en meningsfull platshållare så att användarna kan välja en banderoll. Som standard escape-konverteras inte banners. I stället vill du mata in HTML i presentationsmallen. Om du skapar en JSON-mall bör du använda alternativet för att ta bort js. </p> <p>Exempel: </p> <p> <code class="syntax html"> &lt;guided-banner&nbsp;gsname="top"&nbsp;width="400px" 
      &nbsp;height="50px"/&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>24 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-banner-set gsname="banner area"&gt; &lt;guided-else-banner-set&gt; &lt;/guided-if-banner-set&gt; </span> </p> </td> 
   <td colname="col2"> <p>Aktiverar testning om ett banderollområde är inställt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>25 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-simulator-mode&gt; &lt;guided-else-simulator-mode&gt; &lt;/guided-if-simulator-mode&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gör att du kan identifiera när du visar sökningen i simulatorn eller i Visual Rule Builder. Det används vanligtvis för att visa extra felsökningsinformation för dig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>26 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-tnt-business-rules&gt; &lt;guided-else-tnt-business-rules&gt; &lt;/guided-if-tnt-business-rules&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gör att du kan identifiera om du har några affärsregler som refererar till en <span class="keyword"> Adobe Target </span>-kampanj. Det används vanligtvis som en del av integreringen med <span class="keyword"> Adobe Target </span> för att förhindra att <span class="keyword"> Target </span>-servrarna påverkas när det inte är nödvändigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>27 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-redirect /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Som standard utförs omdirigeringar automatiskt. Om du har konfigurerat webbplatssökning/försäljning för att returnera ett XML- eller JSON-svar till ditt webbprogram kan du välja att antingen analysera 302/301-svaret i ditt webbprogram eller låta omdirigeringen skickas till dig som en del av resultatet. Om du skickar omdirigeringen som en del av resultatuppsättningen kan den här taggen användas i mallen för att skicka omdirigeringsplatsen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>28 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-if-redirect&gt; &lt;guided-else-redirect&gt; &lt;/guided-if-redirect&gt; </span> </p> </td> 
   <td colname="col2"> <p>När du har konfigurerat webbplatssökning/försäljning för att returnera omdirigeringar i resultatuppsättningen, kan den här uppsättningen taggar användas för att avgöra om det finns en omdirigering till utdata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>29 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-lt /&gt; &lt;guided-gt /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med den här uppsättningen taggar kan du bädda in guidade malltaggar i HTML-attribut. </p> <p>Exempel: </p> <p> <code class="syntax html"> &lt;guided-lt/&gt;div&nbsp;&lt;guided-if-facet-long&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;style="height:&nbsp;125px;&nbsp;overflow: 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;auto;"&lt;/guided-if-facet-long&gt;&lt;guided-gt/&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Transportmallstaggar {#reference_227D199F5A7248049BE1D405C0584751}

Transportmallar är XML-mallar som skickar data från backend-sökningen till presentationslagret för guidad sökning.

<!-- 

r_transport_template_tags.xml

 -->

I presentationslagret kan du ha en enda presentationsmall som visar resultatet av flera sökningar. Alla sökningar kan använda samma transportmall eller en anpassad transportmall för att skicka data till presentationslagret.

Eftersom transportmallen bara används för att skicka data till presentationslagret har den ingen HTML-kod som är relevant för att visa sökresultaten. Transportmallen använder XML-taggar för transportmallar för att skicka sökresultaten för att fylla i komponenterna för guidad sökning, till exempel facets, vägbeskrivningar och menyer. Standardtaggarna för sökmallar används för att visa de faktiska värdena.

Se [Redigera en presentation eller en transportmall](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).

Se [Sök efter malltaggar](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Transportmallstagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>XML-rottaggar som används i presentationslagret för att identifiera vad som tolkas från transportmallen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>Taggar omgivande sökmallstaggar som ger sammanfattningsdata baserat på resultatuppsättningen. Vanligtvis innehåller dessa taggar söktaggar för totalt antal resultat, lägre resultat och högsta resultat. Du kan definiera valfritt antal ytterligare globala fält som du vill använda med taggen <span class="codeph"> general-field </span>, som i följande exempel: </p> <p> <code class="syntax html"> &lt;general&gt; 
      &nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Taggar placeras runt sökresultatet så att den guidade sökningen vet var de ska sökas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>Taggar placeras runt varje sökresultat så att den guidade sökningen känner igen var innehållet i ett enskilt sökresultat börjar och slutar, som i följande exempel: </p> <code class="syntax html"> &lt;results&gt; 
     &nbsp;&nbsp;&lt;search-results&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
     &nbsp;&nbsp;&lt;/search-results&gt; 
     &lt;/results&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Gör att du kan slingra dig genom varje objekt i en flervärdeslista för ett enda resultat. Använd bara den här taggen i ett resultat. Syftet med den är att du ska kunna iterera över attribut som tillhör ett resultatfält, som i följande exempel: </p> <code class="syntax html"> &lt;results&gt; 
     &nbsp;&nbsp;&lt;search-results&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
     &nbsp;&nbsp;&lt;/search-results&gt; 
     &lt;/results&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>Skickar på resultaten som fyller i ansiktena. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <!--NEW 2/27/2014--> <span class="codeph"> &lt;dynamic-facet&gt;&lt;/dynamic-facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> Du kan ange en fasett som både en dynamisk aspekt och som medlem av en fasetterad räl. Deras behandling är dock oberoende när det gäller de relaterade presentationsmalltaggarna. </p> <p>Det är alltså inte tillåtet att kapsla in en loop-kontext för en fasett i en dynamisk facet-slingkontext, eller vice versa. </p> <p>För både dynamiska och uppkopplade ansikten är endast de dynamiska aspekter som returnerades för en viss sökning synliga i uppslutningssammanhanget för ansiktsskenan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p> Varje aspekt har sina egna facet-taggar där name-parametern matchar facet-namnet. Söktaggar används i facet-taggarna för ansiktsvärdena, som i följande exempel: </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; 
     &lt;/facets&gt; </code> <p> Konton som använder skårade ansikten kan använda den dynamiska taggen och taggen för visningsnamn. Båda dessa taggar underlättar mappningen mellan skårade och verkliga aspekter samtidigt som de skapar affärsregler. </p> <code class="syntax html"> &lt;facets&gt; 
     &nbsp;&nbsp;&lt;facet&nbsp;name="facet_values01"&gt; 
     &nbsp;&lt;dynamic&gt;1&lt;/dynamic&gt; 
     &nbsp;&lt;display-names&gt;&lt;search-field-value-list&nbsp;name="facet_names01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/display-names&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="facet_values01"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
     &nbsp;&nbsp;&lt;/facet&gt; </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field separator=","&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med <span class="codeph">-avgränsarattributet </span> kan du ändra avgränsaren som används när du skapar data för sökvisningsfält för listor. Standardvärdet är ett komma. </p> <p>I allmänhet bör avgränsaren som du använder vara något som inte visas på ett enkelt sätt i fältinnehållet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions&gt;&lt;/suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p> Omsluta dina Menade du-förslag med taggar så att guidad sökning kan identifiera vilka XML-noder som innehåller förslag. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local"> Om Menade du</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion&gt;&lt;/suggestion&gt; </span> </p> </td> 
   <td colname="col2"> <p>Radbryt varje "Menade"-förslag med taggar, som i följande exempel: </p> <code class="syntax html"> &lt;search-if-suggestions&gt; 
     &nbsp;&nbsp;&lt;suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/suggestion&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
     &nbsp;&nbsp;&lt;/suggestions&gt; 
     &lt;/search-if-suggestions&gt; </code> <p>Se <a href="../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E" type="concept" format="dita" scope="local"> Om Menade du</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sök efter malltaggar {#reference_F7AA3FF602314E42842BBC740D2CA1A4}

En sökmall är en HTML-fil som innehåller malltaggar som definieras av webbplatssökningen/försäljningen. Dessa taggar anger hur sökresultaten formateras. Följande referens innehåller en kort beskrivning av varje sökmallstagg och dess attribut.

<!-- 

r_search_template_tags.xml

 -->

>[!NOTE]
>
>Använd bara sökmallstaggar i transportmallsfiler (.tpl).

Du kan välja bland följande sökmallstagggrupper och referensmaterial.

Taggar som bara är giltiga i resultatslingan innehåller följande:

* [Om resultatlooptaggar](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629)
* [Resultatloop, strängtaggar](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [Villkorstaggar för resultatslinga](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [Länkmärkord för resultatloopar](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [Slinga villkorstaggar för position](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

Följande taggar är giltiga i hela mallen:

* [Listtaggar för fältvärde](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1)
* [Looptaggar för fältvärdeslista](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E)
* [Föreslå taggar](../c-appendices/c-templates.md#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC)
* [Mallsträngstaggar](../c-appendices/c-templates.md#section_67E3D529661F4F03A1FF469D9D658CAF)
* [Länktaggar för mallankarlänk](../c-appendices/c-templates.md#section_3A51D27616C541E2B818CC52B2B856BA)
* [Villkorstaggar för mall](../c-appendices/c-templates.md#section_18D9BC66DE484881932FD2F7EA9D170D)
* [Kontrolltaggar för mallformulär](../c-appendices/c-templates.md#section_45AFC414ACA74825B72FEAA8456F8DD2)

Referensämnen för sökmallar

* [Datumformatsträngar](../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4)
* [Språkidentifierare](../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911)
* [Ange HTTP-huvudet av innehållstyp](../c-appendices/c-templates.md#section_AEED823E9938448A9EDB2F286D9CFD90)
* [Ange en teckenuppsättning i en HTML-mall](../c-appendices/c-templates.md#section_E0D1816ABB5846BEBE9C26D5980CCBE6)
* [Ange en teckenuppsättning i en XML-mall](../c-appendices/c-templates.md#section_17DC31CDCC104F5F8081466B41A96E9D)
* [Inkludera en sökmall i en annan](../c-appendices/c-templates.md#section_7D1FCD3D9E2340C291E354C9720E8BC0)

## Om resultatlooptaggar {#section_D4DC7B4560144663972E8DBC3369C629}

Resultatloop-taggen är mallsystemets arbetshäst. När taggen påträffas under en sökning upprepas HTML-koden och andra taggar mellan den inledande och avslutande resultatloop-taggen, vilket ersätter andra taggar med sökresultatet.

`<search-results> ... </search-results>`

Resultatlooptaggarna omger HTML-koden som visar sökresultaten. HTML mellan taggarna upprepas för varje resultat och visas på sidan.

Följande taggar är bara giltiga i resultatslingan:

* [Resultatloop, strängtaggar](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320)
* [Villkorstaggar för resultatslinga](../c-appendices/c-templates.md#section_35C367969E384A06A9865E388F1F9360)
* [Länkmärkord för resultatloopar](../c-appendices/c-templates.md#section_C5FAEF520E9E42ADAD1F90651922AA02)
* [Slinga villkorstaggar för position](../c-appendices/c-templates.md#section_E0C29DDA09E043C9A396F36334F05EBB)

## Resultatloop, strängtaggar {#section_80D68334E8D04A33937A6E58ABAAA320}

Följande taggar returnerar en sträng.

Se [Om resultatlooptaggar](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar det numeriska indexvärdet för det aktuella resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-title length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar sidrubriken för det aktuella resultatet. Attributet för valfri längd används för att begränsa längden på de strängar som visas, med standardvärdet 80 tecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-bodytext length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar brödtexten från sidans överkant. Relevanta termer visas i fet stil. Attributet för valfri längd används för att begränsa längden på de strängar som visas, med standardvärdet 80 tecken. Kodningsattributet är valfritt och kan koda utdatatecken med HTML-kodning (standard), JavaScript-kodning, Perl-kodning eller ingen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-description length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p> Returnerar beskrivningen av det aktuella resultatet. Om meta description-taggen finns och innehållsattributet inte är tomt, visas den texten. I annat fall visas början på sidans brödtext. Attributet för valfri längd används för att begränsa längden på de strängar som visas, med standardvärdet 80 tecken. </p> <p>Det valfria attributet <span class="codeph"> encoding </span> styr om utdata är HTML-kodade, JavaScript-kodade, Perl-kodade, URL-kodade eller inte kodade, för utdata på resultatsidan. Standardvärdet för <span class="codeph">-kodning </span> är <span class="codeph"> html </span>. Normalt behöver du inte ange kodningsattributet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-score rank="dynamic/static/dynamic-raw/static-raw/final-raw" precision="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar poängen för det aktuella resultatet, vilket är ett tal mellan 0 och 100. Om du har definierat ett rangfält under <span class="uicontrol"> Alternativ </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span> kan du visa den dynamiska sidrankningen genom att ange rankningsattributet till dynamiskt ( <span class="codeph"> &lt;search-score rank="dynamic"&gt; </span>). Du kan visa den statiska sidrankningen genom att ange rankningsattributet till statiskt ( <span class="codeph"> &lt;search-score rank="static"&gt; </span>). Du kan använda det valfria precisionsattributet för att ange antalet decimaler som ska visas. Standardvärdet är 0, vilket visar heltalsmusiken). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-date length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar datumet för det aktuella resultatet. Det valfria textvärdet "none" visas om det inte finns något datum kopplat till det aktuella resultatet. Om det valfria värdet "none" inte anges visas texten "No Date" om det inte finns något datum som är associerat med det aktuella resultatet. </p> <p>Attributet "date-format" har en datumformatsträng i UNIX-format, t.ex. "%A, %B %d, %Y" (för "Måndag, 25 juli 2016"). "gmt" är som standard "yes" och kontrollerar om tidsdelen i datumsträngen ska skrivas ut i GMT ("yes") eller kontots tidszon ("no"). </p> <p>Attributet"language" styr språk- och språkkonventionerna för utdatadatumsträngen. "0" (standard) betyder "Använd kontospråk". "2" betyder "Använd dokumentspråk". Värdet 1 för språk är reserverat för framtida bruk. Alla andra"language"-värden tolkas som en specifik språkidentifierare, till exempel betyder"en_US" "English (USA)". </p> <p>Attributet för valfri längd används för att begränsa längden på de strängar som visas, med standardvärdet 80 tecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-size&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar storleken på det aktuella resultatet i byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar URL:en för det aktuella resultatet. </p> <p>Använd det valfria attributet <span class="codeph"> length </span> för att begränsa längden på de strängar som visas, med ett standardvärde på obegränsat antal tecken. </p> <p><span class="codeph">-attributet </span> är valfritt och kan koda utdatatecken med HTML-kodning, Javascript-kodning, Perl-kodning eller ingen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-url-path-query length="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar sökvägen och frågedelarna inklusive frågetecknet för det aktuella resultatets URL. </p> <p>Använd det valfria attributet <span class="codeph"> length </span> för att begränsa längden på de strängar som visas, med ett standardvärde på obegränsat antal tecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-context length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar nästa rad med kontext för söktermen. Relevanta termer visas i fet stil. Anropa den här taggen upprepade gånger för att visa mer än en kontextrad för det aktuella resultatet. </p> <p>Använd det valfria attributet <span class="codeph"> length </span> för att begränsa längden på de strängar som visas, med standardvärdet 80 tecken. Attributet <span class="codeph"> length </span> ignoreras om den här taggen omges av <span class="codeph"> &lt;search-if-context&gt; </span> eller <span class="codeph"> &lt;search-if-any-context&gt; </span> taggar som innehåller ett length-attribut. </p> <p><span class="codeph">-attributet </span> är valfritt och kan koda utdatatecken med HTML-kodning (standard), Javascript-kodning, Perl-kodning eller ingen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field name="field-name" length="XX" none="text" date-format="date-format-string" gmt="yes/no" language="0/2/language-id" encoding="html/javascript/json/perl/url/none" quotes="yes/no" commas="yes/no" units="miles/kilometers" separator="|"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här avancerade taggen visar innehållet i metadatafältet (url, title, desc, keys, target, body, alt, date, charset, and language eller fält som definieras under <span class="uicontrol"> Options </span> &gt; <span class="uicontrol"> Metadata </span> &gt; Definitions) som anges i attributet <span class="codeph"> name </span> för det aktuella resultatet. Exempel: </p> <p> <span class="codeph"> &lt;search-display-field name="title" length="70" none="no title"&gt; </span> </p> <p>Visar sidans rubrik för ett sökresultat. Om det valfria <span class="codeph">-attributet ingen </span> har angetts visas dess värde endast på resultatsidan om det inte finns något innehåll kopplat till fältet. </p> <p>Attributen <span class="codeph"> date-format </span>, <span class="codeph"> gmt </span> och <span class="codeph"> språk </span> är bara relevanta om innehållstypen för det angivna fältet är <span class="codeph"> datum </span>. </p> <p>Attributet <span class="codeph"> date-format </span> har en datumformatsträng i UNIX-format som <span class="codeph"> %A, %B %d, %Y </span> (för måndag den 25 juli 2016). <span class="codeph"> gmt  </span> har standardvärdet  <span class="codeph"> yes  </span> och styr om tidsdelen i datumsträngen ska skrivas ut i GMT (  <span class="codeph"> yes  </span>) eller kontots tidszon (  <span class="codeph"> no  </span>). </p> <p>Se <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Datumformatsträngar</a>. </p> <p>Attributet <span class="codeph"> språk </span> styr språk- och språkkonventionerna för strängen för utdatadatum. <span class="codeph"> 0  </span> (standard) betyder "Använd kontospråk". <span class="codeph"> 2  </span> betyder"Använd dokumentspråk". Värdet <span class="codeph"> för språket </span> <span class="codeph"> 1 </span> är reserverat för framtida bruk). Alla andra <span class="codeph">-språkvärden </span> tolkas som en specifik språkidentifierare, till exempel betyder <span class="codeph"> en_US </span> "English (USA)". </p> <p>Se <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Språkidentifierare</a>. </p> <p>Det valfria attributet <span class="codeph"> length </span> används för att begränsa längden på de strängar som visas, med standardvärdet 80 tecken. </p> <p>Det valfria attributet <span class="codeph"> encoding </span> styr om utdata är HTML-kodade, JavaScript-kodade, Perl-kodade, URL-kodade eller inte kodade, för utdata på resultatsidan. Standardvärdet för <span class="codeph">-kodning </span> är <span class="codeph"> html </span>. Normalt behöver du inte ange kodningsattributet. </p> <p>Det valfria attributet <span class="codeph"> citattecken </span> styr om enskilda objekts utdata omges av dubbla citattecken (eller enkla citattecken om <span class="codeph"> encoding=perl </span>). Standardvärdet för <span class="codeph"> citattecken </span> är <span class="codeph"> inte </span>. </p> <p>Det valfria attributet <span class="codeph"> komma </span> styr om enskilda objekts utdata avgränsas med kommatecken. Standardvärdet för <span class="codeph"> kommatecken </span> är <span class="codeph"> yes </span>. Attributet <span class="codeph"> för kommatecken </span> ignoreras för fält som inte är av listtyp. </p> <p>Det valfria attributet <span class="codeph"> enheter </span> styr de avståndsenheter som används i ett utdatafält för närhetssökning. Standardvärdet för <span class="codeph"> enheter </span> bestäms av inställningen "Standardenheter" i fältet för platstyp som är associerat med det angivna proximity-sökutdatafältet. </p> <p>Se <a href="../c-appendices/r-about-proximity-search.md#reference_45AC6BB50609431ABD31DA46EE65360D" type="reference" format="dita" scope="local"> Om närhetssökning</a>. </p> <p>Det valfria <span class="codeph">-avgränsarattributet </span> definierar det enskilda tecknet, eller avgränsaren, som infogas mellan värdena för utdata för listtypsfält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-values name="field-name"&gt; ...&lt;search-display-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen skapar en slinga för att räkna upp metadatafältvärden (url, title, desc, keys, target, body, alt, date, charset och language eller fält som definieras under <span class="uicontrol"> Alternativ </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>) för det aktuella resultatet. Kapsla inte den här taggen inuti en annan <span class="codeph"> &lt;search-display-field-values&gt; </span>-tagg. <span class="codeph">-attributet </span> anger namnet på fältet som innehåller de värden som ska räknas upp. Den här taggen är mest användbar för fält där attributet <span class="uicontrol"> Tillåtelselista </span> är markerat (under <span class="uicontrol"> Alternativ </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen returnerar metadatafältvärdet (url, title, desc, keys, target, body, alt, date, charset och language eller fält som definieras under <span class="uicontrol"> Alternativ </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>) för den aktuella <span class="codeph"> &lt;search-display-field-values&gt; </span> eration. Den här taggen är bara giltig inuti en <span class="codeph"> &lt;search-display-field-values&gt; </span>-slinga. Attributen <span class="codeph"> date-format </span>, <span class="codeph"> gmt </span> och <span class="codeph"> språk </span> är bara relevanta om innehållstypen för fältnamnet som anges i den avgränsande <span class="codeph"> &lt;search-display-field-values&gt; </span>-taggen är <span class="codeph"> datum </span>. Attributet <span class="codeph"> date-format </span> har en datumformatsträng i UNIX-format som <span class="codeph"> "%A </span>, <span class="codeph"> %B </span> <span class="codeph"> %d </span>, <span class="codeph"> %Y </span>" (för "Måndag, 25 juli 2016"). Attributet <span class="codeph"> gmt </span> är som standard <span class="codeph"> yes </span> och kontrollerar om tidsdelen i datumsträngen är utdata i GMT ( <span class="codeph"> yes </span>) eller kontots tidszon ( <span class="codeph"> no </span>). </p> <p>Attributet <span class="codeph"> språk </span> styr språk- och språkkonventionerna för strängen för utdatadatum. <span class="codeph"> 0  </span> (standard) betyder "Använd kontospråk". Alla andra <span class="codeph">-språkvärden </span> tolkas som en specifik språkidentifierare, till exempel betyder <span class="codeph"> en_US </span> "English (USA)". </p> <p>Det valfria attributet <span class="codeph"> encoding </span> styr om utdata är HTML-kodade, JavaScript-kodade, Perl-kodade, URL-kodade eller inte kodade, för utdata på resultatsidan. Standardvärdet för <span class="codeph">-kodning </span> är <span class="codeph"> html </span>. Normalt behöver du inte ange kodningsattributet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-count name="field-name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar det totala antalet värden i det aktuella resultatet för metadatafältet (url, title, desc, keys, target, body, alt, date, charset och language eller fält som definieras under <span class="uicontrol"> Alternativ </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>) som anges med namnattributet. Den här taggen kan visas var som helst i resultatslingan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-display-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar den ordinala räknaren (1, 2, 3 och så vidare) för den aktuella <span class="codeph"> &lt;search-display-field-values&gt; </span>-loopitationen. Den här taggen är bara giltig inuti en <span class="codeph"> &lt;search-display-field-values&gt; </span>-slinga. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-fields&gt; </span> </p> </td> 
   <td colname="col2"> <p>Startar en loop-kontext för alla dynamiska facet-fält som returneras för den här sökningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-dynamic-facet-field-name&gt; </span> </p> </td> 
   <td colname="col2"> <p>Anger namnet på det aktuella dynamiska facet-fältet för den här upprepningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-result-trace encoding="html/javascript/ json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar information om placeringen av det aktuella resultatet, t.ex. eventuella resultatbaserade åtgärder som påverkade resultatets position. </p> <p>Utdataformatet för den här taggen är JSON som i följande exempel: </p> <p> <code> { 
      &nbsp;&nbsp;"sliceID":&nbsp;5, 
      &nbsp;&nbsp;"indexID":&nbsp;5894, 
      &nbsp;&nbsp;"finalScore":&nbsp;98.5, 
      &nbsp;&nbsp;"dynamicScore":&nbsp;15.3, 
      &nbsp;&nbsp;"staticScore":&nbsp;55.456, 
      &nbsp;&nbsp;"position":&nbsp;1, 
      &nbsp;&nbsp;"rbtaActionListID":&nbsp;117, 
      &nbsp;&nbsp;"rbtaActionID":&nbsp;57 
      } </code> </p> 
    <!--<p> Results added to the results set by way of <codeph>rbta</codeph> have a "naturalPosition" value of -1. </p>--> <p><span class="codeph">-attributet för kodning </span> är valfritt; standardvärdet är <span class="codeph"> html </span>. </p> <p> <p>Obs!  Den här taggen har bara utdata om <span class="codeph"> sp_trace=1 </span> har angetts med huvudsökfrågeparametrarna. </p> </p> <p>Se rad 48 i tabellen som finns i <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> CGI-parametrar för backend-sökning</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Villkorstaggar för resultatslinga {#section_35C367969E384A06A9865E388F1F9360}

Följande taggar inkluderar villkorligt HTML mellan dem.

Se [Om resultatlooptaggar](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-title&gt; ...  &lt;/search-if-title&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-title&gt; ...  &lt;/search-if-not-title&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML mellan dem om nästa anrop till <span class="codeph"> &lt;search-title&gt; </span> returnerar (eller inte returnerar) text från dokumenttiteln. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-description length="XX"&gt; ... /search-if-description&gt;  </span> </p> <p> <span class="codeph"> &lt;search-if-not-description&gt; ...  &lt;/search-if-not-description&gt; </span> </p> </td> 
   <td colname="col2"> <p> Dessa taggar innehåller HTML mellan dem om nästa anrop till <span class="codeph"> &lt;search-description&gt; </span> returnerar (eller inte returnerar) text från dokumentbeskrivningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bodytext&gt; ...  &lt;/search-if-bodytext&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bodytext&gt; ...  &lt;/search-if-not-bodytext&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML mellan dem om nästa anrop till <span class="codeph"> &lt;search-bodytext&gt; </span> returnerar (eller inte returnerar) text från dokumentets brödtext. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-context length="XX"&gt; ...  &lt;/search-if-context&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-context&gt; ...  &lt;/search-if-not-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML mellan dem om nästa anrop till <span class="codeph"> &lt;search-context&gt; </span> returnerar (eller inte returnerar) en icke-tom kontextsträng. Attributet length åsidosätter attributet length för en omsluten <span class="codeph"> &lt;search-context&gt; </span>-tagg. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-any-context length="XX"&gt; ... /search-if-any-context&gt;  </span> </p> <p> <span class="codeph"> &lt;search-if-not-any-context&gt; ...  &lt;/search-if-not-any-context&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar innehåller HTML mellan dem om det finns (eller inte är) en kontextsträng som är associerad med resultatet. Attributet length åsidosätter attributet length för en omsluten <span class="codeph"> &lt;search-context&gt; </span>-tagg. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-score lower="XX" upper="yy" rank="dynamic/static/dynamic-raw/static-raw/final-raw"&gt; ...  &lt;/search-if-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-score lower="XX" upper="yy" rank="dynamic/static"&gt; ...  &lt;/search-if-not-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML mellan dem om poängen för det aktuella resultatet är (eller inte är) mellan XX och YY. Användbart om du vill lägga till punkter eller bilder för att visa hur relevant resultatet är. Om du har definierat ett rangordningsfält under <span class="uicontrol"> Alternativ </span> &gt; <span class="uicontrol"> Metadata </span> &gt; <span class="uicontrol"> Definitioner </span>, kan du kontrollera den dynamiska sidrankningen genom att ange rankningsattributet till dynamiskt ( <span class="codeph"> &lt;search-if-score rank="dynamic" lower=XX upper=YY&gt; </span>). Du kan kontrollera den statiska sidrankningen genom att ange rankningsattributet till statiskt ( <span class="codeph"> &lt;search-if-score rank="static" lower=XX upper=YY&gt; </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field name="field-name" value="value"&gt; ...  &lt;/search-if-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field name="field-name" value="value"&gt; ...  &lt;/search-if-not-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa avancerade taggar inkluderar HTML mellan dem baserat på om fältet som anges i attributet "name" har innehåll eller inte. Om det valfria "value"-attributet anges, inkluderar taggarna HTML mellan dem baserat på om det givna värdet matchar (eller inte matchar) värdet för fältet i det aktuella resultatet. Dessa taggar fungerar bara i resultatslingan (mellan <span class="codeph"> &lt;search-results&gt; </span> och <span class="codeph"> &lt;/search-results&gt; </span>-taggar). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Resultatloop, ankarlänkstaggar {#section_C5FAEF520E9E42ADAD1F90651922AA02}

Se [Om resultatlooptaggar](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ...  &lt;/search-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Det här taggparet skapar en ankarlänk runt HTML-koden mellan dem. När någon klickar på länken visas resultatsidan. Ett valfritt målattribut anger det namngivna fönster i vilket webbläsare som stöder bildrutor ska visa resultatsidan. </p> <p>Ställ in attributet hbx-enable på"yes" för att dra nytta av de analyser som är tillgängliga via HBX. Ange hbx-line-child-name till namnet på ett metadatafält som du vill spåra. Om du till exempel vill spåra sökresultat efter SKU-nummer anger du hbx-line-child-name till namnet på fältet Meta-data som innehåller SKU-information. </p> <p>Datumtypsfält stöds för närvarande inte. Värdet för hbx-line-child-name läggs till i länk-ID:t i det genererade ankaret. Värdet för attributet hbx-line-none läggs till i länk-ID:t när det namngivna metadatafältet är tomt. Värdet för hbx-line-length begränsar antalet tecken som hämtas och visas från meta-taggen. Standardantalet tecken är 12. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-smart-link target="frame-name" hbx-enable="yes/no" hbx-linkid-name="field-name" hbx-linkid-none="text" hbx-linkid-length="XX"&gt; ...  &lt;/search-smart-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Det här taggparet liknar <span class="codeph"> &lt;search-link&gt; ... &lt;/search-link&gt; </span>-taggar. När du klickar på de skapade ankarlänkarna visas resultatsidan, men sidan rullas till närmaste ankartagg före resultatet. För PDF-länkar visar Acrobat-visningsprogrammet den sida som innehåller resultatet. Ett valfritt målattribut anger det namngivna fönster i vilket webbläsare som stöder bildrutor ska visa resultatsidan. </p> <p>Ställ in attributet hbx-enable på"yes" för att dra nytta av de analyser som är tillgängliga via HBX. Ange hbx-line-child-name till namnet på ett metadatafält som du vill spåra. Om du till exempel vill spåra sökresultat efter SKU-nummer anger du hbx-line-child-name till namnet på fältet Meta-data som innehåller SKU-information. </p> <p>Datumtypsfält stöds för närvarande inte. Värdet för hbx-line-child-name läggs till i länk-ID:t i det genererade ankaret. Värdet för attributet hbx-line-none läggs till i länk-ID:t när det namngivna metadatafältet är tomt. Värdet för hbx-line-length begränsar antalet tecken som hämtas och visas från meta-taggen. Standardantalet tecken är 12. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-link-extension&gt; ...  &lt;/search-if-link-extension&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-link-extension&gt; ...  &lt;/search-if-not-link-extension&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar innehåller HTML mellan dem om ett värdeattribut anger ett tillägg som matchar slutet av URL:en för resultatet. Det här märkordet är användbart om du vill inkludera en bild i sökresultaten baserat på länktillägget. Attributet value är en lista med ett eller flera tillägg (blankstegsavgränsade) enligt följande: VALUE=".pdf" eller VALUE=".html.htm". </p> </td> 
  </tr> 
 </tbody> 
</table>

## Slinga villkorstaggar för position {#section_E0C29DDA09E043C9A396F36334F05EBB}

Följande taggar inkluderar texten mellan dem. De får bara finnas inuti slingorna: &lt; `search-results>` och `<search-field-values>`. De används för att testa det aktuella resultatets position i resultatmängden.

Se [Om resultatlooptaggar](../c-appendices/c-templates.md#section_D4DC7B4560144663972E8DBC3369C629).

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-first&gt; ...  &lt;/search-if-first&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-first&gt; ...  &lt;/search-if-not-first&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar innehåller texten mellan dem om det aktuella resultatet är (eller inte är) det första resultatet på sidan (när det används i <span class="codeph"> &lt;search-results&gt; </span>) eller det första fältvärdet (när det används i <span class="codeph"> &lt;search-field-values&gt; </span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-last&gt; ...  &lt;/search-if-last&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-last&gt; ...  &lt;/search-if-not-last&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar innehåller texten mellan dem om det aktuella resultatet är (eller inte är) det sista resultatet på sidan (när det används i <span class="codeph"> &lt;search-results&gt; </span>) eller det sista fältvärdet (när det används i <span class="codeph"> &lt;search-field-values&gt; </span>). Den här taggen kan användas för att infoga en avgränsare mellan resultaten. Detta infogar till exempel en <span class="codeph"> &lt;hr&gt; </span>-tagg mellan resultaten: </p> <p> <code class="syntax html"> &lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-inner&gt; ...  &lt;/search-if-inner&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-inner&gt; ...  &lt;/search-if-not-inner&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar innehåller texten mellan dem om det aktuella resultatet inte är det första eller sista resultatet på sidan (när det används i <span class="codeph"> &lt;search-results&gt; </span>) eller inte är det första eller sista fältvärdet (när det används i <span class="codeph"> &lt;search-field-values&gt; </span>). Om taggen inte är en version av testas om resultatet är antingen det första eller det sista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-alt&gt; ...  &lt;/search-if-alt&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-alt&gt; ...  &lt;/search-if-not-alt&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar innehåller texten mellan dem om det aktuella resultatet är (eller inte är) ett alternativt resultat på sidan (när det används i <span class="codeph"> &lt;search-results&gt; </span>) eller ett alternativt fältvärde (när det används i <span class="codeph"> &lt;search-field-values&gt; </span>). "Alternativa" resultat är den andra, fjärde, sjätte och så vidare, på sidan. I det här exemplet används en annan klass för alternativa tabellrader. Observera att <span class="codeph"> &lt;search-lt&gt; </span> och <span class="codeph"> &lt;search-gt&gt; </span> <span class="codeph"> &lt;search-if-alt&gt; </span>-taggen kan placeras "inuti" <span class="codeph"> &lt;tr&gt; </span>-taggen. </p> <p> <code class="syntax html"> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-lt&gt;tr&lt;search-if-alt&gt;&nbsp;class="alt"&lt;/search-if-alt&gt;&lt;search-gt&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td&gt;&lt;search-url&gt;&lt;/td&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-even&gt; ...  &lt;/search-if-even&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-even&gt; ...  &lt;/search-if-not-even&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar innehåller texten mellan dem om det aktuella resultatet är (eller inte är) ett jämnt numrerat resultat (när det används i <span class="codeph"> &lt;search-results&gt; </span>) eller ett jämnt numrerat fältvärde (när det används i <span class="codeph"> &lt;search-field-values&gt; </span>). Ett sökresultat är jämnt numrerat om dess <span class="codeph"> &lt;search-index&gt; </span>-värde är jämnt. Med andra ord, om dess position i hela resultatmängden är jämn. Detta kan skilja sig från <span class="codeph"> &lt;search-if-alt&gt; </span> som testar positionen för ett resultat på sidan, inte inom hela resultatuppsättningen. I följande två tabeller illustreras skillnaden: </p> </td> 
  </tr> 
 </tbody> 
</table>

### Första sidan, sp_n=1

<table>  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Index </p> </th> 
   <th colname="col2" class="entry"> <p>Resultat </p> </th> 
   <th colname="col3" class="entry"> <p>Eller hur? </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Första resultatet </p> </td> 
   <td colname="col3"> <p>Nej </p> </td> 
   <td colname="col4"> <p>Nej </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Andra resultatet </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Ja </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>3 </p> </td> 
   <td colname="col2"> <p>Tredje resultatet </p> </td> 
   <td colname="col3"> <p>Nej </p> </td> 
   <td colname="col4"> <p>Nej </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4 </p> </td> 
   <td colname="col2"> <p>Fjärde resultatet </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Ja </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>5 </p> </td> 
   <td colname="col2"> <p>Femte resultatet </p> </td> 
   <td colname="col3"> <p>Nej </p> </td> 
   <td colname="col4"> <p>Nej </p> </td> 
  </tr> 
 </tbody> 
</table>

### Senare sida, sp_n=10

<table>  
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Index </p> </th> 
   <th colname="col2" class="entry"> <p>Resultat </p> </th> 
   <th colname="col3" class="entry"> <p>Eller hur? </p> </th> 
   <th colname="col4" class="entry"> <p>Alt? </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>10 </p> </td> 
   <td colname="col2"> <p>Tionde resultatet </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Nej </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>11 </p> </td> 
   <td colname="col2"> <p>Ettonde resultatet </p> </td> 
   <td colname="col3"> <p>Nej </p> </td> 
   <td colname="col4"> <p>Ja </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>12 </p> </td> 
   <td colname="col2"> <p>Tolfte resultatet </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Nej </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>13 </p> </td> 
   <td colname="col2"> <p>Trettonde resultatet </p> </td> 
   <td colname="col3"> <p>Nej </p> </td> 
   <td colname="col4"> <p>Ja </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>14 </p> </td> 
   <td colname="col2"> <p>Fjortonde resultatet </p> </td> 
   <td colname="col3"> <p>Ja </p> </td> 
   <td colname="col4"> <p>Nej </p> </td> 
  </tr> 
 </tbody> 
</table>

Observera slutligen att `<search-if-even>` alltid är samma som `<search-if-alt>` för sökfältsvärden eftersom fältvärden inte växlas.

## Fältvärdeslisttaggar {#section_D3298B5F976447DBA0032B883DCC91B1}

Följande avancerade taggar genererar fältvärden och relaterade data från hela uppsättningen sökresultat. Dessa taggar ger bara utdata för fält som anges av CGI-parametrarna `sp-sfvl-field` i sökfrågan.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list name="field-name" quotes="yes/no" commas="yes/no" data="values/counts/results" separator="X" sortby="none/values/counts/results" max-items="XX" date-format="date-format-string" gmt="yes/no" language="0/language-id" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen visar en lista med unika fältvärden, värdeantal eller resultatantal inom hela resultatuppsättningen. </p> <p>Den här taggen ger bara utdata för fält som anges av CGI-parametrarna <span class="codeph"> sp_sfvl_field </span> i sökfrågan. Attributet"quotes" (valfria"quotes") styr om enskilda utdataobjekt omges av dubbla citattecken (eller enkla citattecken, om encoding=perl). Standardvärdet för"citattecken" är"ja". Det valfria attributet "komma" styr om enskilda objekts utdata separeras med kommatecken. Standardvärdet för komma är ja. Det valfria attributet "data" kontrollerar om varje unikt fältvärde är utdata (data="values"), det totala antalet för varje unikt fältvärde är utdata (data="counts") eller antalet resultat som innehåller varje unikt värde (data="results"). Standardvärdet för data är "values". För fält som inte är av listtyp är data="counts" och data="results" likvärdiga. Separatorattributet definierar det enda tecken, eller avgränsare, som ska infogas mellan värdena för utdata. Det valfria attributet "sortby" styr ordningen på utdata. sortBy="none" betyder ingen speciell ordning, sortBy="values" betyder sortering efter fältvärden (i stigande eller fallande ordning enligt fältets Sorting-egenskap), sortBy="counts" betyder sortering i fallande ordning efter fältvärdesantal och sortBy="results" betyder sortering i fallande ordning efter antalet resultat som innehåller varje värde. </p> <p>Observera att sortby="counts" och sortby="results" motsvarar icke-listtypsfält. Det valfria attributet "max-items" begränsar antalet objekt som ska skrivas ut. Standardvärdet för "max-items" är -1, vilket betyder "output all items". </p> <p>Det finns en absolut gräns på 100 för max-items. Attributen "date-format", "gmt" och "language" är bara relevanta om innehållstypen för det angivna fältet är "date". Attributet "date-format" har en datumformatsträng i UNIX-format, t.ex. "%A, %B %d, %Y" (för "Måndag, 25 juli 2016"). "gmt" är som standard "yes" och kontrollerar om tidsdelen i datumsträngen ska skrivas ut i GMT ("yes") eller kontots tidszon ("no"). </p> <p>Se <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Datumformatsträngar</a>. </p> <p>Attributet"language" styr språk- och språkkonventionerna för utdatadatumsträngen. "0" (standard) betyder "Använd kontospråk". Alla andra"language"-värden tolkas som en specifik språkidentifierare, till exempel betyder"en_US" "English (USA)". Det valfria attributet "encoding" kontrollerar om utdatasträngstecknen är HTML-kodade, JavaScript-kodade, Perl-kodade, URL-kodade eller inte kodade, för utdata på resultatsidan. Standardvärdet för "encoding" är "html". </p> <p>Se <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Språkidentifierare</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value" results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen visar räkningsinformation för en viss sökfält-värde-lista. Det finns tre olika användningsområden för den här taggen. Om endast attributet "name" anges returnerar taggen antalet unika värden för det namngivna fältet i hela resultatuppsättningen. Om attributen "name" och "value" båda anges returnerar taggen antingen det totala antalet för det givna värdet i hela resultatmängden (for results="no") eller det totala antalet resultat som innehåller det givna värdet i hela resultatmängden (for results="yes"). Standardvärdet för "results" är "no". Obs! För fält som inte är av listtyp är results="yes" och results="no" likvärdiga. Värdet för "results" ignoreras om attributet "value" inte anges. Den här taggen ger bara utdata för fält som anges av CGI-parametrarna <span class="codeph"> sp-sfvl-field </span> i sökfrågan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-field-value-list-count name="field-name" value="field-value"&gt; ...  &lt;/search-if-field-value-list-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-field-value-list-count name="field-name" value="field-value"&gt; ...  &lt;/search-if-not-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar visar HTML mellan dem om det motsvarande anropet till <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value"&gt; </span> med de angivna attributen skulle (eller inte skulle) returnera ett värde som är större än noll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-single-field-value-list-count name="field-name"&gt; ...  &lt;/search-if-single-field-value-list-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar visar innehållet mellan dem om det motsvarande anropet till <span class="codeph"> &lt;search-field-value-list-count name="field-name" value="field-value"&gt; </span> med de angivna attributen skulle (eller inte skulle) returnera ett enda värde. Detta används vanligtvis när ett konto använder facets-platser. Med facet vill du vanligtvis bara visa värdet-slot när den associerade namnplatsen har ett enda objekt. Den här kontrollen i transportmallen är effektivare än om du gör det i presentationslagret. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Looptaggar för fältvärdeslista {#section_0717FA09F0FC449CB916883B0500A60E}

Följande avancerade taggar räknar upp och returnerar fältvärden och relaterade data från hela uppsättningen sökresultat med hjälp av en slingkonstruktion. Dessa taggar ger bara utdata för fält som anges av CGI-parametrarna `sp-sfvl-field` i sökfrågan.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-values name="field-name" sortby="none/values/counts/results" max-items="XX"&gt; ...  &lt;/search-field-values&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen skapar en slinga för att räkna upp fältvärden och relaterade data för ett visst fält i hela resultatuppsättningen. Kapsla inte den här taggen inuti en annan <span class="codeph"> &lt;search-field-values&gt; </span>-tagg. Attributet name anger namnet på fältet som innehåller de värden som ska räknas upp. Det valfria attributet "sortby" styr uppräkningsordningen: "none" betyder ingen speciell ordning, "values" betyder sortering efter fältvärden (i stigande eller fallande ordning enligt fältets Sorting-egenskap), sortby="counts" betyder sortering i fallande ordning efter fältvärdesantal och sortby="results" betyder sortering i fallande ordning efter antalet resultat som innehåller varje värde. </p> <p>Observera att sortby="counts" och sortby="results" motsvarar icke-listtypsfält. . Det valfria attributet "max-items" begränsar antalet iterationer till det angivna värdet. Standardvärdet för "max-items" är -1, vilket betyder "enumerate all values". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value date-format="date-format-string" encoding="html/javascript/json/perl/url/none" gmt="yes/no" language="0/language-id"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen matar ut fältvärdet för den aktuella upprepningen av &lt;search-field-values&gt;-loop. Den här taggen är bara giltig inuti en <span class="codeph"> &lt;search-field-values&gt; </span>-slinga. Attributen "date-format", "gmt" och "language" är bara relevanta om innehållstypen för fältnamnet som anges i den omslutande &lt;search-field-values&gt;-taggen är "date". Attributet "date-format" har en datumformatsträng i UNIX-format, t.ex. "%A, %B %d, %Y" (för "Måndag, 25 juli 2020"). </p> <p>Se <a href="../c-appendices/c-templates.md#section_4BBDBBEF2B96414497617CD4B52D96E4" type="section" format="dita" scope="local"> Datumformatsträngar</a>. </p> <p>Det valfria attributet "encoding" kontrollerar om utdatasträngstecknen är HTML-kodade, JavaScript-kodade, Perl-kodade, URL-kodade eller inte kodade, för utdata på resultatsidan. Standardvärdet för "encoding" är "none". Normalt behöver du inte ange kodningsattributet. "gmt" är som standard "yes" och kontrollerar om tidsdelen i datumsträngen ska skrivas ut i GMT ("yes") eller kontots tidszon ("no"). Attributet"language" styr språk- och språkkonventionerna för utdatadatumsträngen. "0" (standard) betyder "Använd kontospråk". Alla andra"language"-värden tolkas som en specifik språkidentifierare, till exempel betyder"en_US" "English (USA)". </p> <p>Se <a href="../c-appendices/c-templates.md#section_0490DECC00E34691ADE5A9ED90A6D911" type="section" format="dita" scope="local"> Språkidentifierare</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-count results="yes/no"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen returnerar det antal som är associerat med den aktuella <span class="codeph"> &lt;search-field-values&gt; </span>-loopitationen. Antal utdata är antingen antalet resultat i hela resultatuppsättningen som innehåller fältvärdet (results="yes") eller det totala antalet för fältvärdet i hela resultatuppsättningen. Standardvärdet för "results" är "no". </p> <p>För fält som inte är av listtyp är results="yes" och results="no" likvärdiga. Den här taggen är bara giltig inuti en <span class="codeph"> &lt;search-field-values&gt; </span>-slinga. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-field-value-counter&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen matar ut den ordinala räknaren för den aktuella <span class="codeph"> &lt;search-field-values&gt; </span>-loopitationen. Den här taggen är bara giltig inuti en <span class="codeph"> &lt;search-field-values&gt; </span>-slinga. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Föreslå taggar {#section_C28EB8B4F7DC4E278A0F143BCFEEB1AC}

Föreslå innehåller ett användarvänligt&quot;Menade du?&quot; för att föreslå alternativa söktermer. Om en användare har felstavat en sökterm, till exempel, kan Föreslå hjälpa användaren att hitta resultat genom att föreslå en korrekt stavning. Systemet kan även föreslå relaterade nyckelord som kan hjälpa en användare att identifiera resultaten. När du skapar förslag använder tjänsten Föreslå två ordlistor: en baserad på kontospråket (anges under **[!UICONTROL Indexing]** > **[!UICONTROL Words and Languages]** > **[!UICONTROL Language]**) och den andra som är unikt genererad från nyckelorden i kontoindexet.

>[!NOTE]
>
>Föreslagstjänsten fungerar inte för kinesiska, japanska eller koreanska.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-suggestions&gt; ...  &lt;/search-if-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Omge dessa taggar med malltaggar som "Föreslå", t.ex. <span class="codeph"> &lt;sök-förslag&gt; </span>, <span class="codeph"> &lt;sök-förslag-länk&gt; </span> osv. Om sökningen genererar förslag genereras och bearbetas allt mellan den öppna och den avslutande taggen. Om sökningen inte genererar några förslag kommer inget av det kapslade innehållet att skapas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestions&gt; ...  &lt;/search-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med den här taggen genereras slingan "Föreslå", som innehåller en lista med föreslagna söktermer (till exempel "Föreslå", "Tänkt" och "Avsikt" för en fråga som ursprungligen angavs som "Avsikt"). När sökmotorn genererar en lista med termer upprepas alla kapslade HTML- och/eller malltaggar upp till fem gånger, vilket är det maximala antalet förslag. Använd attributet count för att ange antalet genererade förslag (mellan 0 och 5). </p> <p>Taggen <span class="codeph"> &lt;search-ideas&gt; </span> kan visas flera gånger på sidan för att upprepa listan med förslag. Flera förslag sorteras efter antalet resultat som varje resultat ger. </p> <p>Kapsla <span class="codeph"> &lt;search-ideas&gt; </span>-taggen mellan öppna och stäng <span class="codeph"> &lt;search-if-ideas&gt; </span>-taggar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-link&gt; ...  &lt;/search-suggestion-link&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med det här märkordet skapas en länk till den ursprungliga sökfrågan med det valda föreslagna söktermen i stället för det ursprungliga. Taggen godkänner och skriver helt enkelt ut alla HTML-attribut som class, target och style. Taggen kan även acceptera ett URL-attribut, vars värde används som bas-URL för den genererade länken. Taggarna kan bara finnas inuti <span class="codeph"> &lt;search-recommendations&gt; </span>-slingan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-text /&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med den här taggen skrivs den aktuella föreslagna frågetermen ut (t.ex. "avser" för en fråga som ursprungligen angavs som "avser"). Taggen har inga attribut och kan bara finnas inuti <span class="codeph"> &lt;search-ideas&gt; </span>-slingan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-not-suggestions&gt; ...  &lt;/search-if-not-suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Om sökningen inte genererar några förslag genereras och bearbetas allt mellan den öppna och den avslutande taggen. Om sökningen genererar förslag kommer inget av det kapslade innehållet att skapas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if&gt; ...  &lt;/search-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa villkorstaggar innehåller HTML mellan dem baserat på om den föreslagna termen är den första termen i slingan Föreslå. Taggarna måste visas mellan öppna och avslutande <span class="codeph"> &lt;search-draft&gt; </span>-taggar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if&gt; ...  &lt;/search-if&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa villkorstaggar innehåller HTML mellan dem baserat på om den föreslagna termen är den sista termen i slingan Föreslå. Taggarna måste visas mellan öppna och avslutande <span class="codeph"> &lt;search-draft&gt; </span>-taggar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-index&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen returnerar det numeriska indexvärdet för den aktuella föreslagna söktermen. Taggen måste visas mellan öppna och avslutande <span class="codeph"> &lt;search-draft&gt; </span>-taggar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen returnerar det totala antalet genererade föreslagna söktermer. Taggen måste visas mellan öppna och avslutande <span class="codeph"> &lt;search-draft&gt; </span>-taggar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-suggestion-result-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här taggen returnerar det totala antalet resultat för den föreslagna söktermen. Taggen måste visas mellan öppna och avslutande <span class="codeph"> &lt;search-draft&gt; </span>-taggar. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mallsträngstaggar {#section_67E3D529661F4F03A1FF469D9D658CAF}

Med följande taggar skapas en sträng i HTML-koden vid den tidpunkten i mallen.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-body&gt; </span> </p> </td> 
   <td colname="col2"> <p>HTML-body-taggen med eventuella inställningar för söklänksfärg som anges av Basic Look Section under Template-länken. Lägg till ett bakgrundsattribut till den här taggen om du vill visa bakgrundsbilder på resultatsidan. Alla färgattribut som läggs till i den här taggen åsidosätter de inställningar för länkfärg som anges i avsnittet Grundläggande utseende. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-header&gt; </span> </p> </td> 
   <td colname="col2"> <p>HTML-koden för sökresultatrubriken som angetts i avsnittet Grundläggande sökning under länken Mall. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-cdata&gt; ...  &lt;/search-cdata&gt; </span> </p> </td> 
   <td colname="col2"> <p>Sökning-cdata-taggarna ersätts med sina XML-motsvarigheter: <span class="codeph"> &lt;search-data&gt; </span> ersätts med <span class="codeph"> &lt;![CDATA[" och taggen &lt;/search-data&gt; </span> ersätts med " <span class="codeph"> ]]&gt; </span>". En XML-tolk tolkar inte någon information mellan taggen open och close. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-query query-number="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Frågan som besökaren angav. Det avancerade valfria attributet "query-number" kontrollerar vilken numrerad frågesträng som skapas av den här taggen. <span class="codeph"> &lt;search-query-number=1&gt; </span> matar ut innehållet i parametern <span class="codeph"> sp_q_1 </span> cgi. Om "query-number" inte har angetts, eller om query-number är "0", kommer huvudfrågan ( <span class="codeph"> sp_q </span>) att returneras. Det valfria attributet "encoding" kontrollerar om utdata är HTML-kodade, JavaScript-kodade, Perl-kodade, URL-kodade eller inte kodade, för utdata på resultatsidan. Standardvärdet för "encoding" är "html". Normalt behöver du inte ange kodningsattributet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-total&gt; </span> </p> </td> 
   <td colname="col2"> <p>Det totala antalet resultat för den här sökningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Antal rapporterade resultat för den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lower&gt; </span> </p> </td> 
   <td colname="col2"> <p>Antalet första resultat som rapporteras för den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-upper&gt; </span> </p> </td> 
   <td colname="col2"> <p>Antalet senaste resultat som har rapporterats för den här sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-prev-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Antalet resultat som rapporterats för föregående sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>10 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Antalet resultat som rapporteras för nästa sida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>11 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-time&gt; </span> </p> </td> 
   <td colname="col2"> <p>Tiden i sekunder för den här sökningen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>12 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-logo&gt; </span> </p> </td> 
   <td colname="col2"> <p>HTML för söklogotypen som är konfigurerad för ditt konto, om sådan finns. Den här logotypen är bilden som ger meriter till webbplatssökning/försäljning </p> <p>De flesta konton har för närvarande ingen associerad söklogotyp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>13 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-collection all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Samlingen av resultaten för den här sökningen. Det valfria attributet "all" används för att ge namnet på samlingen som representerar hela webbplatsen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>14 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-form&gt; ...&lt;/search-form&gt; </span> </p> </td> 
   <td colname="col2"> <p>Infogar inledande och avslutande formulärtaggar. Infogar attributen method och action i den inledande formulärtaggen. Tar emot ytterligare attribut, inklusive attributen dir="RTL" för språk samt JavaScript-relaterade attributen "name" och "onSubmit". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>15 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-account&gt; </span> </p> </td> 
   <td colname="col2"> <p>Infogar en formulärindatatagg som anger ditt kontonummer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>16 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-gallery&gt; </span> </p> </td> 
   <td colname="col2"> <p>Infogar en formulärindatatagg som anger gallerinumret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>17 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-query query-number="XX"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Infogar en formulärindatatagg som anger frågesträngen. Det avancerade valfria attributet "query-number" kontrollerar vilken numrerad fråga som används för formulärindatataggen. <span class="codeph"> &lt;search-input-query-number=1&gt; </span> skickar till exempel en formulärindatatagg för <span class="codeph"> sp_q_1 </span>-frågan. Om "query-number" inte har angetts, eller om "query-number" är "0", infogas en indatatagg för huvudfrågan <span class="codeph"> sp_q </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>18 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input-collections all="name"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Infogar en tagg för att markera formulär och associerad HTML som visar markeringsmenyn för samlingar. Det valfria attributet "all" används för att ge namnet på samlingen som representerar hela webbplatsen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>19 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-lt&gt; </span> </p> </td> 
   <td colname="col2"> <p>Infogar utdata från en av sökmallstaggarna i andra HTML- eller malltaggar på resultatsidan. <span class="codeph"> &lt;search-lt&gt; </span> infogar ett mindre än-tecken. Om du använder <span class="codeph"> &lt;search-lt&gt; </span> och <span class="codeph"> &lt;search-gt&gt; </span> kan du undvika definitionen av en tagg så att du kan använda sökmallstaggar som attributvärden. När mallen återges som svar på en sökning ersätter ett mindre än-tecken (&lt;) <span class="codeph"> &lt;search-lt&gt; </span>-taggen. <span class="codeph"> &lt;search-link&gt; </span> motsvarar till exempel <span class="codeph"> &lt;search-lt&gt;a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>20 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-gt&gt; </span> </p> </td> 
   <td colname="col2"> <p>Infogar utdata från en av sökmallstaggarna i andra HTML- eller malltaggar på resultatsidan. <span class="codeph"> &lt;search-gt&gt; </span> infogar ett större än-tecken. Om du använder <span class="codeph"> &lt;search-lt&gt; </span> och <span class="codeph"> &lt;search-gt&gt; </span> kan du undvika definitionen av en tagg så att du kan använda andra malltaggar som attributvärden. När mallen återges som svar på en sökning ersätter ett större än-tecken (&gt;) <span class="codeph"> &lt;search-gt&gt; </span>-taggen. <span class="codeph"> &lt;search-link&gt; </span> motsvarar till exempel <span class="codeph"> &lt;search-lt&gt;a href="&lt;search-url&gt;"&lt;search-gt&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>21 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-param name="param-name" length="XX" encoding="html/javascript/json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Returnerar värdet för cgi-parametern med namnet "param-name" från den aktuella sökbegäran. Det valfria attributet "encoding" kontrollerar om utdata är HTML-kodade, JavaScript-kodade, Perl-kodade, URL-kodade eller inte kodade, för utdata på resultatsidan. Standardvärdet för "encoding" är "html". Normalt behöver du inte ange kodningsattributet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>22 </p> </td> 
   <td colname="col1"> <p> 
     <!--NEW for S&P 8.17.0 release on October 30 2014--> <span class="codeph"> &lt;search-trace encoding="html/javascript/ json/perl/url/none"&gt; </span> </p> </td> 
   <td colname="col2"> 
    <!--<p>This global core search template tag outputs a representation of the submitted core search query, including any "fuzzy-search" query term expansions that happen by way of synonyms, sound-alikes, and so forth. </p>--> <p><span class="codeph">-attributet för kodning </span> är valfritt; standardvärdet är <span class="codeph"> json </span>. </p> <p> <p>Obs!  Den här taggen har bara utdata om <span class="codeph"> sp_trace=1 </span> har angetts med huvudsökfrågeparametrarna. </p> </p> <p>Se rad 48 i tabellen som finns i <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> CGI-parametrar för backend-sökning</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Länktaggar för mallankarlänk {#section_3A51D27616C541E2B818CC52B2B856BA}

Följande taggar gör att en ankarlänk omger HTML-koden mellan dem. När du klickar på ankarlänken begär ankarlänken en annan resultatsida att visa. Det valfria attributet &quot;count&quot; begär så många resultat på sidan som ska visas. Om inget anges används det begärda antalet på den aktuella sidan. Det avancerade valfria URL-attributet styr domänen som den associerade länken är riktad till. Som standard är domänen `https://search.atomz.com/search/`, men du kan ändra detta med URL-attributet.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-next URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-next&gt; </span> </p> <p> <span class="codeph"> &lt;search-prev URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-prev&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar nästa eller föregående sida med resultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-date URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-sort-by-score URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-sort-by-score&gt; </span> </p> </td> 
   <td colname="col2"> <p>Sorterar resultaten efter datum eller relevans. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-show-summaries URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-hide-summaries URL="https://search.yourdomain.com/search/"&gt; ...  &lt;/search-hide-summaries&gt; </span> </p> </td> 
   <td colname="col2"> <p>Visar eller döljer sammanfattningarna. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Villkorstaggar för mall {#section_18D9BC66DE484881932FD2F7EA9D170D}

Taggar som gör att du kan inkludera HTML mellan dem om du vill.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-results&gt; ...  &lt;/search-if-results&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-results&gt; ...&lt;/search-if-not-results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML om den aktuella sidan innehåller några (eller inga) sökresultat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-prev-count&gt; ...  &lt;/search-if-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-prev-count&gt; ...  &lt;/search-if-not-prev-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-next-count&gt; ...  &lt;/search-if-next-count&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-next-count&gt; ...  &lt;/search-if-not-next-count&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML om föregående sida eller nästa sida har några (eller inga) resultat kopplade till sig. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-score&gt; ...  &lt;/search-if-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-score&gt; ...  &lt;/search-if-not-sort-by-score&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-sort-by-date&gt; ...  &lt;/search-if-sort-by-date&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-date&gt; ...  &lt;/search-if-not-sort-by-date&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML om den aktuella sidan är, eller inte är, sorterad efter relevans eller efter datum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>4 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-show-summaries&gt; ...  &lt;/search-if-show-summaries&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-hide-summaries&gt; ...  &lt;/search-if-hide-summaries&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML om den aktuella sidan visar eller döljer sammanfattningar. Du kan använda dessa taggar för att ta med eller utesluta delar av sökresultatet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>5 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-input-collections&gt; ...  &lt;/search-if-input-collections&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-input-collections&gt; ...  &lt;/search-if-not-input-collections&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML om en samling har angetts i genereringen av sökresultat för den aktuella sidan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>6 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-advanced&gt; ...  &lt;/search-if-advanced&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-advanced&gt; ...  &lt;/search-if-not-advanced&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar HTML om CGI-parametern <span class="codeph"> sp_advanced=1 </span> har angetts för sökfrågan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>7 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-bad-param name="parameter-name"&gt; ...  &lt;/search-if-bad-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-bad-param name="parameter-name"&gt; ...  &lt;/search-if-not-bad-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa taggar inkluderar eller exkluderar HTML mellan dem om den angivna parametern är eller inte är giltig. </p> <p>För närvarande stöds bara parametern <span class="codeph"> sp_q_location[_#] </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>8 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-param name="param-name" value="param-value"&gt; ...  &lt;/search-if-param&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-param name="param-name" value="param-value"&gt; ...  &lt;/search-if-not-param&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa avancerade taggar inkluderar HTML mellan dem baserat på om CGI-parametern som anges i attributet "name" har värdet som anges i attributet "value". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>9 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-if-sort-by-field name="field-name"&gt; ...  &lt;/search-if-sort-by-field&gt; </span> </p> <p> <span class="codeph"> &lt;search-if-not-sort-by-field name="field-name"&gt; ...  &lt;/search-if-not-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa avancerade taggar inkluderar HTML mellan dem om den aktuella sidan sorteras efter det angivna fältnamnet eller inte. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Kontrolltaggar för mallformulär {#section_45AFC414ACA74825B72FEAA8456F8DD2}

Taggar som gör att du kan styra standardmarkeringstillståndet för kryssrutor, alternativknappar och listrutor i en `<form>` i sökmallen.

<table> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> <p>Tagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-input&gt; </span> </p> </td> 
   <td colname="col2"> <p>Används i en mall i stället för en <span class="codeph"> &lt;input&gt; </span>-tagg. När taggen skrivs till webbläsaren ersätter ordet <span class="codeph"> input </span> <span class="codeph"> search-input </span> och all annan information i taggen returneras som vanligt. Om <span class="codeph">-namnet </span> som anges i taggen listas som en CGI-parameter och om <span class="codeph">-värdet </span> som anges i taggen är värdet för den CGI-parametern, läggs ordet <span class="codeph"> som är markerat </span> till i slutet av taggen. På så sätt kan du automatiskt göra standardläget för alternativknappen eller kryssrutan i sökresultatet till samma som för den aktuella frågan. </p> <p>HTML-koden för en kryssruta kan till exempel se ut så här: </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact"&gt;Ingen ljudmatchning  </span> </p> <p>Motsvarande mallkod för kryssrutan är följande: </p> <p> <span class="codeph"> &lt;search-input type="checkbox" name="sp_w" value="exact"&gt;Ingen ljudmatchning  </span> </p> <p>Om CGI-parametersträngen för frågan innehåller <span class="codeph"> sp_w=exact </span> ser taggen som skrivs till webbläsaren med sökresultaten ut så här (ordet <span class="codeph"> markerat </span> infogas i slutet av taggen): </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact" checked=""&gt;Ingen ljudmatchning  </span> </p> <p>Om CGI-parametersträngen för frågan inte innehåller <span class="codeph"> sp_w=exact </span> ser taggen som skrivs till webbläsaren med sökresultaten ut så här (ordet <span class="codeph"> markerat </span> finns inte med i taggen): </p> <p> <span class="codeph"> &lt;input type="checkbox" name="sp_w" value="exact"&gt;Ingen ljudmatchning  </span> </p> <p>Taggen <span class="codeph"> &lt;search-input&gt; </span> är användbar när du vill placera kryssrutor och alternativknappar i sökmallen. Om du har kryssrutor eller alternativknappar som du vill lägga till i <span class="codeph"> &lt;form&gt; </span> i sökmallen använder du <span class="codeph"> &lt;search-input...&gt; </span> istället för <span class="codeph"> &lt;input...&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>2 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-select&gt; ...  &lt;/search-select&gt; </span> </p> <p> <span class="codeph"> &lt;search-option&gt; ...  &lt;/search-option&gt; </span> </p> </td> 
   <td colname="col2"> <p>Listrutor i en <span class="codeph"> &lt;form&gt; </span>-tagg har startats med en <span class="codeph"> &lt;select&gt; </span>-tagg och avslutats med en <span class="codeph"> &lt;/select&gt; </span>-tagg. <span class="codeph">-namnet </span> för den associerade CGI-parametern visas i <span class="codeph"> &lt;select&gt; </span>-taggen. Efter <span class="codeph"> &lt;select&gt; </span>-taggen är en lista med <span class="codeph"> &lt;option&gt; </span>-taggar som anger vilka värden som ska visas i listrutan. </p> <p><span class="codeph"> &lt;search-select&gt; </span>, <span class="codeph"> &lt;/search-select&gt; </span>, <span class="codeph"> &lt;search-option&gt; </span> och <span class="codeph"> &lt;/search-option&gt; </span>-taggarna har liknande funktioner som <span class="codeph"> &lt;search-input&gt; </span>-taggen. Det innebär att ordet <span class="codeph"> markerat </span> automatiskt läggs till i slutet av <span class="codeph"> &lt;option&gt; </span>-taggen som skickas till webbläsaren om <span class="codeph">-namnet </span> i <span class="codeph"> &lt;search-select&gt; </span>-taggen listas som en CGI-parameter och om <span class="codeph">-värdet </span> för CGI-parametern är anges som <span class="codeph">-värdet </span> i en viss <span class="codeph"> &lt;search-option&gt; </span>-tagg. På så sätt kan du automatiskt göra standardvalet för listrutor i sökresultatet till samma som för den aktuella frågan. </p> <p>En vanlig listruta ser till exempel ut så här: </p> <p> <code class="syntax html"> &lt;select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;option&nbsp;value="any"&nbsp;selected&gt;Anywhere&lt;/option&gt; 
      &lt;option&nbsp;value="title"&gt;Title&lt;/option&gt; 
      &lt;option&nbsp;value="desc"&gt;Description&lt;/option&gt; 
      &lt;option&nbsp;value="keys"&gt;Keywords&lt;/option&gt; 
      &lt;option&nbsp;value="body"&gt;Body&lt;/option&gt; 
      &lt;option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/option&gt; 
      &lt;option&nbsp;value="url"&gt;URL&lt;/option&gt; 
      &lt;option&nbsp;value="target"&gt;Target&lt;/option&gt; 
      &lt;/select&gt; </code> </p> <p>Motsvarande mallkod för den listrutan är följande: </p> <p> <code class="syntax html"> &lt;search-select&nbsp;name="sp_x"&nbsp;size=1&gt; 
      &lt;search-option&nbsp;value="any"&gt;Anywhere&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="title"&gt;Title&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="desc"&gt;Description&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="keys"&gt;Keywords&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="body"&gt;Body&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="alt"&gt;Alternate&nbsp;text&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="url"&gt;URL&lt;/search-option&gt; 
      &lt;search-option&nbsp;value="target"&gt;Target&lt;/search-option&gt; 
      &lt;/search-select&gt; </code> </p> <p>Om du har listrutor som du vill lägga till i <span class="codeph"> &lt;form&gt; </span> i sökmallen använder du <span class="codeph"> &lt;search-select..&gt; </span> i stället för <span class="codeph"> &lt;select...&gt; </span>, <span class="codeph"> &lt;/search-select&gt; </span> i stället för <span class="codeph"> &lt;/select&gt; </span>, <span class="codeph"> &lt;search-option..&gt; </span> i stället för <span class="codeph"> &lt;option..&gt; </span> och <span class="codeph"> &lt;/search-option&gt; </span> i stället för <span class="codeph"> &lt;/option&gt; </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>3 </p> </td> 
   <td colname="col1"> <p> <span class="codeph"> &lt;search-sort-by-field name="field-name" count="XX"&gt; ...  &lt;/search-sort-by-field&gt; </span> </p> </td> 
   <td colname="col2"> <p>Dessa avancerade taggar skapar en ankarlänk runt HTML-koden mellan dem. När du klickar på den här ankarpunkten visas en resultatsida som är sorterad i det angivna fältet. Det valfria attributet <span class="codeph"> count </span> anger antalet resultat som ska visas på resultatsidan. Om <span class="codeph"> antal </span> utelämnas används antalet som används på den aktuella sidan. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datumformatsträngar {#section_4BBDBBEF2B96414497617CD4B52D96E4}

Du kan använda följande konverteringsspecifikationer i datumformatsträngar:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Datumformatsträng </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p> Matchar den nationella representationen av det fullständiga veckodagens namn, till exempel "Måndag". Inställningen i <span class="uicontrol"> Linguistics </span> &gt; <span class="uicontrol"> Words &amp; Languages </span> &gt; <span class="uicontrol"> Language </span> avgör den nationella representationen. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Ord och språk</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> Matchar den nationella representationen av det förkortade veckodagsnamnet, där förkortningen är de första tre tecknen, till exempel"Mån". Inställningen i <span class="uicontrol"> Linguistics </span> &gt; <span class="uicontrol"> Words &amp; Languages </span> &gt; <span class="uicontrol"> Language </span> avgör den nationella representationen. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Ord och språk</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> Matchar den nationella representationen av det fullständiga månadsnamnet, till exempel"Juni". Inställningen i <span class="uicontrol"> Linguistics </span> &gt; <span class="uicontrol"> Words &amp; Languages </span> &gt; <span class="uicontrol"> Language </span> avgör den nationella representationen. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Ord och språk</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> Matchar den nationella representationen av det förkortade månadsnamnet, där förkortningen är de första tre tecknen, till exempel "Jun". Inställningen i <span class="uicontrol"> Linguistics </span> &gt; <span class="uicontrol"> Words &amp; Languages </span> &gt; <span class="uicontrol"> Language </span> avgör den nationella representationen. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Ord och språk</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p>Motsvarar "%m/%d/%y", t.ex. "07/25/13". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> Matchar dagen i månaden som ett decimaltal (01-31). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> Matchar dagen i månaden som ett decimaltal (1-31). Ett tomt värde föregår enstaka siffror. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> Matchar 24-timmarsklockan som ett decimaltal (00-23). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> Matchar den nationella representationen av det förkortade månadsnamnet, där förkortningen är de första tre tecknen, till exempel "Jun" (samma som %b). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> Matchar 12-timmars-klockan som ett decimaltal (01-12). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> Matchar dagen på året som ett decimaltal (001-366). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> Matchar (24-timmars klocka som ett decimaltal (0-23). Ett tomt värde föregår enstaka siffror. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> Matchar klockan 12 timmar som ett decimaltal (1-12). Ett tomt värde föregår enstaka siffror. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> Matchar minuten som ett decimaltal (00-59). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> Matchar månaden som ett decimaltal (01-12). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> Matchar den nationella representationen av "ante meridiem" eller "post meridiem", beroende på vad som är tillämpligt, t.ex. "PM". Inställningen i <span class="uicontrol"> Linguistics </span> &gt; <span class="uicontrol"> Words &amp; Languages </span> &gt; <span class="uicontrol"> Language </span> avgör den nationella representationen. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79" type="concept" format="dita" scope="local"> Ord och språk</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p>Motsvarar "%H:%M", t.ex. "13:23". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p>Motsvarar "%I:%M:%S %p", till exempel "01:23:45 PM". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%s </p> </td> 
   <td colname="col2"> <p> Matchar den andra som ett decimaltal (00-60). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p>Motsvarar "%H:%M:%S", t.ex. "13:26:47". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> Matchar årets veckonummer (söndag som veckodag) som ett decimaltal (00-53). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p>Motsvarar "%e-%b-%Y", t.ex. "25-Jul-2013". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> Matchar året med århundradet som ett decimaltal, t.ex. "2013". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> Matchar året utan århundrade som ett decimaltal (00-99). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> Matchar tidszonens namn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> Matchar %. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Språkidentifierare {#section_0490DECC00E34691ADE5A9ED90A6D911}

Följande tabell innehåller språkidentifierare för varje språk som stöds. Du kan använda dessa identifierare som värden för det valfria&quot;language&quot;-attributet i följande malltaggar:

* `search-date` och  `search-display-field`.

   Se [Resultatloop, strängtaggar](../c-appendices/c-templates.md#section_80D68334E8D04A33937A6E58ABAAA320).

* `search-field-value-list` Se  [Listtaggar](../c-appendices/c-templates.md#section_D3298B5F976447DBA0032B883DCC91B1) för fältvärden.

* `search-field-value` Se Looptaggar för  [fältvärdeslista](../c-appendices/c-templates.md#section_0717FA09F0FC449CB916883B0500A60E).

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Språk </p> </th> 
   <th colname="col2" class="entry"> <p>Språkidentifierare </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Bulgariska (Bulgarien) </p> </td> 
   <td colname="col2"> <p> bg_BG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (Kina) </p> </td> 
   <td colname="col2"> <p> zh_CN </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (Hongkong) </p> </td> 
   <td colname="col2"> <p> zh_HK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (Singapore) </p> </td> 
   <td colname="col2"> <p>zh_SG </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (Taiwan) </p> </td> 
   <td colname="col2"> <p> zh_TW </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tjeckiska (Tjeckien) </p> </td> 
   <td colname="col2"> <p> cs_CZ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Danska (Danmark) </p> </td> 
   <td colname="col2"> <p> da_DK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nederländska (Belgien) </p> </td> 
   <td colname="col2"> <p> nl_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nederländska (Nederländerna) </p> </td> 
   <td colname="col2"> <p> nl_NL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Engelska (Australien) </p> </td> 
   <td colname="col2"> <p> en_AU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Engelska (Kanada) </p> </td> 
   <td colname="col2"> <p> en_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Engelska (Storbritannien) </p> </td> 
   <td colname="col2"> <p> en_GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Engelska (USA) </p> </td> 
   <td colname="col2"> <p> en_US </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Franska (Belgien) </p> </td> 
   <td colname="col2"> <p> fr_BE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Franska (Kanada) </p> </td> 
   <td colname="col2"> <p>fr_CA </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Finska (Finland) </p> </td> 
   <td colname="col2"> <p> fi_FI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Franska (Frankrike) </p> </td> 
   <td colname="col2"> <p> fr_FR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Franska (Schweiz) </p> </td> 
   <td colname="col2"> <p> fr_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tyska (Österrike) </p> </td> 
   <td colname="col2"> <p> de_AT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tyska (Tyskland) </p> </td> 
   <td colname="col2"> <p> de_DE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tyska (Schweiz) </p> </td> 
   <td colname="col2"> <p> de_CH </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grekiska (Grekland) </p> </td> 
   <td colname="col2"> <p> el_GR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Iriska galiska (Irland) </p> </td> 
   <td colname="col2"> <p> ga_IE </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Italienska (Italien) </p> </td> 
   <td colname="col2"> <p> it_IT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Japanska (Japan) </p> </td> 
   <td colname="col2"> <p> ja_JP </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Koreanska (Korea) </p> </td> 
   <td colname="col2"> <p> ko_KR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Norska (Norge) </p> </td> 
   <td colname="col2"> <p> no_NO </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Polska (Polen) </p> </td> 
   <td colname="col2"> <p> pl_PL </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portugisiska (Brasilien) </p> </td> 
   <td colname="col2"> <p> pt_BR </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Portugisiska (Portugal) </p> </td> 
   <td colname="col2"> <p> pt_PT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ryska (f.d. Sovjetunionen) </p> </td> 
   <td colname="col2"> <p> ru_SU </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slovakiska (Slovakien) </p> </td> 
   <td colname="col2"> <p> sk_SK </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Slovakiska (Slovenien) </p> </td> 
   <td colname="col2"> <p>sl_SI </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spanska (Mexiko) </p> </td> 
   <td colname="col2"> <p> es_MX </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spanska (Spanien) </p> </td> 
   <td colname="col2"> <p> es_ES </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Svenska (Sverige) </p> </td> 
   <td colname="col2"> <p> sv_SE </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ange HTTP-huvudet {#section_AEED823E9938448A9EDB2F286D9CFD90} av innehållstypen

Du kan ange HTTP-svarshuvudet Content-Type med följande tagg:

`<search-content-type-header [content="MIME-type"] [charset="charset-name"]>`

Attributen `content` och `charset` är valfria. Taggen ska visas så tidigt som möjligt i mallen. Vi rekommenderar även att den visas före antingen `<search-html-meta-charset>` eller `<search-xml-decl>`, eftersom det påverkar beteendet för dessa taggar.

Om du inte anger attributet `content` blir värdet `MIME-type` som standard det värde som anges i **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**. Om du anger ett `content`-attribut används det som standard `content`-attribut för taggen `<search-html-meta-charset>`.

Om du inte anger attributet `charset` skrivs inget `charset`-värde till rubriken `content-type`.

Om du anger `charset="1"` är det faktiska värdet för `charset-name` värdet för CGI-parametern `sp_f`. Om ingen `sp_f` CGI-parameter skickas med sökningen läses det faktiska värdet för `charset-name` från dina kontoinställningar. Du kan visa eller ändra teckenuppsättningen som är kopplad till ditt konto under **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**.

Se [Konfigurera din personliga användarinformation](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Du kan välja ett specifikt teckenuppsättningsnamn genom att ange det som `charset`-värde, till exempel `charset="iso-8859-1"` eller `charset="Shift-JIS"`.

Om du anger ett `charset`-attribut används det som standard `charset`-attribut för `<search-html-meta-charset>`- och `<search-xml-decl>`-taggarna, samt som utdata till `content-type`-huvudet.

## Ange en teckenuppsättning i en HTML-mall {#section_E0D1816ABB5846BEBE9C26D5980CCBE6}

Standardmallarna för sökresultat i HTML anger teckenuppsättningen som är kopplad till det aktuella kontot via följande tagg:

`<search-html-meta-charset [content="MIME-type"] [charset="charset-name"]>`

Attributen content och charset är valfria. Den här taggen måste finnas i HTML `<head>`-avsnittet i mallen. Den här taggen ger följande tagg på HTML-sidan som genereras från mallen:

`<meta http-equiv="content-type" content="MIME-type; charset=charset-name">`

Om du inte anger innehållsattributet blir det faktiska värdet `MIME-type` som standard ett av två värden. Om taggen `<search-content-type-header>` har angett ett `content`-attribut används det värdet. I annat fall används det värde som anges på fliken **[!UICONTROL Templates]** > **[!UICONTROL Settings]** > **[!UICONTROL Content Type]**.

Om du inte anger attributet `charset` blir det faktiska värdet `charset-name` som standard ett av två värden. Om taggen `<search-content-type-header>` har angett ett `charset`-attribut används det värdet. Annars läses det faktiska värdet för `charset-name` från dina kontoinställningar. Du kan visa eller ändra teckenuppsättningen som är kopplad till ditt konto under **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**.

Se [Konfigurera din personliga användarinformation](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Om du anger `charset="1"` är det faktiska värdet för `charset-name` värdet för CGI-parametern `sp_f`. Om ingen `sp_f` CGI-parameter skickas tillsammans med sökningen är det faktiska värdet för `charset-name` antingen det värde som angetts i `<search-content-type-header>`-taggen om den angetts, eller det värde som angetts i kontoinställningarna.

Du kan ange ett specifikt teckenuppsättningsnamn, som i `charset="charset-name"`. Till exempel `charset="iso-8859-1"` eller `charset="Shift-JIS"`.

Taggen `<search-html-meta-charset>` är valfri. Om du tar bort den får webbläsaren standardvärdena för `content-type`, vilket är följande: `content="text/html; charset=ISO-8859-1"`. Du kan också välja att ersätta `<search-html-meta-charset>`-taggen med din egen `http-equiv`-tagg.

## Ange en teckenuppsättning i en XML-mall {#section_17DC31CDCC104F5F8081466B41A96E9D}

Standardmallen för XML-sökresultat anger teckenuppsättningen som är associerad med det aktuella kontot med följande tagg:

`<search-xml-decl [charset="charset-name"]>`

Attributet `charset` är valfritt. Den här taggen måste visas högst upp i mallen, men efter en `<search-content-type-header>`-tagg. Det här märkordet ger följande märkord i XML-dokumentet som genereras från mallen:

`<?xml version="1.0" encoding="charset-name" standalone="yes" ?>`

Om du inte anger `charset` blir det faktiska värdet `charset-name` som standard ett av två värden. Om `<search-content-type-header>` har angett ett `charset`-attribut används det värdet. Annars läses det faktiska värdet för `charset-name` från dina kontoinställningar. Du kan visa eller ändra teckenuppsättningen som är kopplad till ditt konto under **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]** > **[!UICONTROL Character Encoding]**.

Se [Konfigurera din personliga användarinformation](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Om du anger `charset="1"` är det faktiska värdet för `charset-name` värdet för CGI-parametern `sp_f`. Om ingen `sp_f` CGI-parameter skickas tillsammans med sökningen är det faktiska värdet för `charset-name` antingen det värde som anges i `<search-content-type-header>`-taggen om den angavs, eller det värde som anges i dina kontoinställningar.

Du kan ange ett specifikt teckenuppsättningsnamn, som i `charset="charset-name"`, om du vill. Exempel, `charset="iso-8859-1" or charset="Shift-JIS"`.

Du kan välja att ersätta `<search-xml-decl>`-taggen med din egen `?xml`-tagg.

## Inkludera en sökmall i en annan {#section_7D1FCD3D9E2340C291E354C9720E8BC0}

Om du vill ta med en sökmall i en annan använder du taggen `<search-include>` och anger filattributet till namnet på den mallfil som du vill ta med som i följande exempel:

`<search-include file="seo/seo_search_title.tpl" />`

SEO-sökmallssegment finns i undermappen `seo/` och normala sökmallar finns i undermappen `templates/`. Det är bara tpl-filer som är relevanta att inkludera i det här sammanhanget.

## Hantera flera transportmallar för webbplatsen {#reference_12AAB3B9F4C74C11956F1DBA95714C2F}

Du kan styra utseendet på sökresultaten på hela webbplatsen genom att använda olika söktransportmallar för varje område.

<!-- 

r_managing_multiple_templates.xml

 -->

Om du vill använda den här typen av sökfunktioner kan du hantera transportmallar i webbplatssökningar och -försäljningar. Du kan också hantera dina transportmallar i Publish. Precis som för webbplatssökning och -försäljning kan du med Publish redigera, förhandsgranska och publicera flera söktransportmallar.

Om du vill ställa in sökformulären så att de använder en viss transportmall (annan än standardtransportmallen) använder du frågeparametern `sp_t`. Anta till exempel att du har en sökmall som heter&quot;radering&quot; för den markerade säljardelen på din webbplats. Du använder det vanliga HTML-sökformuläret med följande extra formulärkod:

`<input type=hidden name="sp_t" value="clearance">`

När en kund klickar på ett standardformulär som innehåller den här kodraden visas transportmallen för rensning tillsammans med sökresultaten.

Se [Använda samlingar i sökformulär](../c-appendices/c-searchforms.md#reference_5A079AEEEFB84457892EF0870D0605C3).

Se [Använda ramar med formulär](../c-appendices/c-searchforms.md#reference_82CDDDA1E37042E4849EBF7EA05407C5).

Se [Exempel på avancerat sökformulär](../c-appendices/c-searchforms.md#reference_82E1051918744EBA88A01E9E6AE42C4A).
