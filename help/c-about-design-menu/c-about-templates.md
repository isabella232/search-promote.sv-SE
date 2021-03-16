---
description: Du kan använda Mallar för att hantera presentationsmallar och transportmallar.
solution: Target
title: Om mallar
topic: Design, webbplatssökning och -försäljning
uuid: f5805d3e-43bf-4e13-95df-b6bd6b762d11
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '2652'
ht-degree: 0%

---


# Om mallar{#about-templates}

Du kan använda **[!UICONTROL Templates]** för att hantera presentationsmallar och transportmallar.

## Om mallar {#concept_06EB481B14864E18A8AE2BCD1D6EF0B5}

<!-- 

c_about_templates.xml

 -->

Du kan lägga till, redigera, kopiera, byta namn på eller ta bort presentationsmallar och transportmallar. När du klickar på ett befintligt mallnamn i tabellen Mallar öppnas det i ett redigeringsfönster (eller visningsprogram) där du kan göra ändringarna.

Du kan återställa alla ändringar du gör i mallar med hjälp av funktionen Historik i mallnamnets listruta i tabellen Mallar.

Du kan minska sidbredden för en presentationsmall genom att markera kryssrutan **[!UICONTROL Minimize]** för mallen i malltabellen. Genom att minska mallens sidbredd minimerar du dynamiskt infogat JavaScript och CSS. Du kan också ta bort överflödigt tomt utrymme i HTML-koden. Genom att minimera sidbredden i presentationsmallen kan du leverera sökresultaten snabbare.

Du kan förhandsgranska den minimerade mallens utseende genom att klicka på listrutan bredvid filnamnet och sedan klicka på **[!UICONTROL Preview minimized]**. Om du minimerar huvudpresentationsmallen måste du komma ihåg att aktivera minimering för inkluderade (med taggen `guided-include`) mallar eftersom det här alternativet inte kan ärvas.

Även om du minimerar en presentationsmall kan du fortfarande redigera den&quot;ominimerade&quot; versionen av samma mall.

Du kan använda reglerna för försökning, eftersökning och affärsregler för att avgöra när du ska använda någon av dina andra presentationsmallar. Det är vanligt att ha en regel som &quot;Ställ in målmallen på xxxx för varje sökning&quot;. När du ändrar standardmallen i tabellen Mallar när du har en sådan regel på plats, verkar den inte ha någon effekt.

Se [Om regler för försökning](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

Se [Om regler för eftersökning](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

Se [Om affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Om presentationsmallar {#section_ACDDEA5C499E481C828A517C230D4596}

Presentationsmallar är HTML-mallar som en kund ser när de visar sökresultaten på din webbplats.

I presentationslagret kan du ha en enda presentationsmall som visar resultatet av flera sökningar från olika källor. Du kan definiera så många presentationsmallar du vill och till och med definiera presentationsmallar som andra mallar delar med hjälp av `include`-kommandon. Presentationsmallen är den plats där alla designkomponenter, som fasetter, menyer och vägbeskrivningar, samlas. Om du vill visa de olika designkomponenterna måste du använda taggar för presentationsmallar.

Se [Presentationsmalltaggar](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

När du har flera presentationsmallar definierar du under vilka förhållanden de olika presentationsmallarna ska användas. Du kan välja vilken presentationsmall som ska användas baserat på inkommande CGI-parametrar och cookies. Du kan också växla vilken presentationsmall du använder baserat på resultatet från en tidigare sökning.

När du använder flera presentationsmallar måste du ange vilken mall du vill att sökresultaten ska visas från början. Du kan göra detta med kolumnen **[!UICONTROL Default]** i tabellen Mallar.

## Om transportmallar {#section_35FD3E8AAA4E4695A737DB7E00C3258B}

Transportmallar kan vara antingen XML- eller JSON-mallar som skickar data från den bakomliggande sökningen till presentationslagret för guidad sökning.

Som standard är ditt konto konfigurerat att använda XML-transportmallar. Om du däremot föredrar att använda JSON för att skicka data till guidad sökning kontaktar du Adobe Consulting som kan hjälpa dig.

I presentationslagret kan du ha en enda presentationsmall som visar resultatet av flera sökningar. Vid varje sökning kan samma transportmall eller en anpassad transportmall användas för att skicka data till presentationslagret. Eftersom transportmallen bara används för att skicka data till presentationslagret, får den inte ha någon HTML som används för att visa sökresultaten. I mallen används transportmallstaggar för att skicka sökresultatet och resultaten för att fylla i ansiktena. I dessa taggar används standardtaggar för sökmallar för att visa de faktiska värdena.

Se [Sök efter malltaggar](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

**XML-transportmallsspecifika taggar**

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>XML-transportmallstagg </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;guided-xml&gt;&lt;/guided-xml&gt; </span> </p> </td> 
   <td colname="col2"> <p>Detta är de XML-rottaggar som används i presentationslagret för att identifiera vad det måste tolka från transportmallen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;general&gt;&lt;/general&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här uppsättningen taggar omger sökmallstaggar som ger sammanfattningsdata baserat på resultatuppsättningen. Vanligtvis innehåller dessa taggar söktaggar för det totala antalet resultat, det lägsta resultatet och det högsta resultatet. Du kan definiera valfritt antal ytterligare globala fält som du vill använda med taggen <span class="codeph"> general-field </span>. </p> <p> <b>Exempel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;general&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;total&gt;&lt;search-total&nbsp;/&gt;&lt;/total&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;lower&gt;&lt;search-lower&nbsp;/&gt;&lt;/lower&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;upper&gt;&lt;search-upper&nbsp;/&gt;&lt;/upper&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;general-field&nbsp;name="my_custom_field"&gt;Some&nbsp;global&nbsp;content&lt;/general-field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/general&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;results&gt;&lt;/results&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här uppsättningen taggar placeras runt sökresultaten så att den guidade sökningen vet var de finns. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;result&gt;&lt;/result&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här uppsättningen taggar placeras runt varje sökresultat så att den guidade sökningen känner igen var innehållet för ett enskilt sökresultat börjar och slutar. </p> <p> <b>Exempel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-cdata&gt;&lt;search-url&nbsp;length="500"&nbsp;/&gt;&lt;/search-cdata&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;attribute-table name="tablename"&gt; </span> </p> </td> 
   <td colname="col2"> <p>Med den här taggen kan du göra en slinga genom varje objekt i en flervärdeslista för ett enda resultat. Använd taggen bara i ett resultat. Dess främsta syfte är att du ska kunna iterera över attribut som tillhör ett resultatfält. </p> <p> <b>Exempel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;index&gt;&lt;search-index&nbsp;/&gt;&lt;/index&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;loc&gt;&lt;search-url&nbsp;/&gt;&lt;/loc&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;search-title&nbsp;/&gt;&lt;/title&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;attribute-table&nbsp;name="downloads"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_title"&gt;&lt;search-display-field&nbsp;name="download_title"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;field&nbsp;name="download_link"&nbsp;delimiter="|"&gt;&lt;search-display-field&nbsp;name="download_link"&nbsp;/&gt;&lt;/field&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/attribute-table&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/result&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-results&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/results&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facets&gt;&lt;/facets&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här uppsättningen taggar överför resultaten som fyller i ansiktena. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;facet name="name"&gt;&lt;/facet&gt; </span> </p> </td> 
   <td colname="col2"> <p>Varje aspekt måste ha sina egna facet-taggar där name-parametern matchar facet-namnet. Söktaggar används i facet-taggarna för ansiktsvärdena. </p> <p>Se <a href="../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5" type="concept" format="dita" scope="local"> Om ansikten </a>. </p> <p> <b>Exempel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;facets&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="brand"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="brand"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;facet&nbsp;name="category"&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;values&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="values"&nbsp;sortby="values"&nbsp;/&gt;&lt;/values&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;counts&gt;&lt;search-field-value-list&nbsp;name="category"&nbsp;quotes="no"&nbsp;commas="yes"&nbsp;data="counts"&nbsp;sortby="values"&nbsp;/&gt;&lt;/counts&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/facet&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/facets&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestions&gt;&lt;/suggestions&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här uppsättningen taggar omger dina Menade-förslag så att guidad sökning känner igen vilka XML-noder som innehåller förslag. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> &lt;suggestion&gt;&lt;/suggestion&gt; </span> </p> </td> 
   <td colname="col2"> <p>Den här uppsättningen taggar omsluter varje "Menade du förslag". </p> <p> <b>Exempel</b> </p> <p> <code> &nbsp;&nbsp;&nbsp;&nbsp;&lt;search-if-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;value&gt;&lt;search-suggestion-text&nbsp;/&gt;&lt;/value&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;count&gt;&lt;search-suggestion-result-count&nbsp;/&gt;&lt;/count&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestion&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/suggestions&gt; 
      &nbsp;&nbsp;&nbsp;&nbsp;&lt;/search-if-suggestions&gt; </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Mallspecifika taggar för JSON-transport**

Att skicka JSON mot XML från sökmotorn är känt för att vara snabbare eftersom det är mindre nyttolast och en snabbare tolk. Var försiktig när du använder JSON för att se till att utdata är strikt JSON eftersom tolken inte förlåter.

Om du inte har använt JSON tidigare kan du använda följande länkar och exempel för att komma igång:

* En introduktion till JSON. Se [https://www.json.org/](https://www.json.org/).
* Testa din JSON för att kontrollera att den är giltig. Se [https://jsonlint.com/](https://jsonlint.com/).

**Exempel på JSON-mall**

```
{ 
 "general": 
 { 
  "total" : "<search-total />", 
  "lower" : "<search-lower />", 
  "upper" : "<search-upper />", 
  "rbt-trigger-list" : "<search-rbta-trigger-id-list>", 
  "fields" :  
  [ 
   { 
    "name" : "seo_search_title", 
    "value" : "<search-include file="seo/seo_search_title.tpl" />" 
   }, 
   { 
    "name" : "seo_search_keywords", 
    "value" : "<search-include file="seo/seo_search_keywords.tpl" />" 
   } 
  ] 
 }, 
 
 <search-if-suggestions> 
 "suggestions": 
  [ 
  <search-suggestions> 
  { 
   "suggestion":"<search-suggestion-text />", 
   "count": "<search-suggestion-result-count>" 
  }<search-if-not-last-suggestion>,</search-if-not-last-suggestion> 
  </search-suggestions> 
 ], 
 </search-if-suggestions> 
 
 "facets" : 
 [ 
  { 
   "name" : "leveli", 
   "values" : [ <search-field-value-list name="leveli" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="leveli" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" :"levelii", 
   "values" : [<search-field-value-list name="levelii" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="levelii" quotes="no" sortby="values" data="results" />] 
  }, 
  { 
   "name" : "brand", 
   "values" : [<search-field-value-list name="brand" quotes="yes" sortby="values" data="values" encoding="json"/>], 
   "counts" : [<search-field-value-list name="brand" quotes="no" sortby="values" data="results" />] 
  }, 
 ], 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    }, 
    { 
     "name" : "title", 
     "value" : "<search-display-field name="title" encoding="json"/>" 
    }, 
    { 
     "name" : "img_url_thumbnail", 
     "value" : "<search-display-field name="img_url_thumbnail" encoding="json"/>" 
    }, 
    { 
     "name" : "description", 
     "value" : "<search-display-field name="description" encoding="json"/>" 
    }, 
    { 
     "name" : "mdi", 
     "value" : "<SEARCH-RBTA-DISPLAY-MDI-FIELD>" 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**Exempel på JSON-resultatavsnitt med en resultatattributtabell**

```
{ 
 "results" : 
 [ 
  <search-results> 
  { 
   "fields" : 
   [ 
    { 
     "name" : "index", 
     "value" : "<search-index />" 
    }, 
    { 
     "name" : "loc", 
     "value" : "<search-display-field name="url" length="500" encoding="json"/>" 
    } 
   ], 
   "tables" : 
   [ 
    { 
     "name" : "downloads", 
     "fields" : 
     [ 
      { 
       "name" : "download_title", 
       "value" : <search-display-field name="download_title" encoding="json"/> 
      }, 
      { 
       "name" : "download_link", 
       "value" : <search-display-field name="download_link" encoding="json"/> 
      } 
     ] 
    } 
   ] 
  }<search-if-not-last>,</search-if-not-last>  
  </search-results> 
 ] 
}
```

**Exempel på JSON Facet-avsnitt för en aspekt med associerade fält**

```
{ 
 facets" : 
 [ 
  { 
   "name" : "t1", 
   "values" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
   "counts" : [<search-field-value-list name="t1" quotes="yes" commas="yes" data="results" sortby="values" />], 
   "custom-fields" : 
   [ 
    { 
     "name" : "taxonmyId", 
     "value" : [<search-field-value-list name="tax1" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />] 
    } 
   ] 
  } 
 ] 
}
```

**Exempel på JSON Facet-avsnitt för lutade ytor**

```
{ 
  "facets" : 
  [  
   { 
    "name" : "fvalue0", 
                  "dynamic" : 1, 
                  "display-names" : [<search-field-value-list name="fname0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "values" : [<search-field-value-list name="fvalue0" quotes="yes" commas="yes" data="values" sortby="values" encoding="json" />], 
    "counts" : [<search-field-value-list name="fvalue0" quotes="no" commas="yes" data="results" sortby="values" />] 
   } 
  ] 
} 
```

## Lägga till en ny presentations- eller transportmallfil {#task_73199757B6E748CAA604902FF913F012}

Du kan använda **[!UICONTROL Add Template]** för att lägga till presentationsmallar (.tmpl) eller transportmallar (.tpl) på sidan [!DNL Templates].

<!-- 

t_adding_a_new_presentation_or_transport_template_file.xml

 -->

**Lägga till en ny presentations- eller transportmallfil**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Template]** på sidan [!DNL Templates].
1. Ange önskade alternativ i dialogrutan [!DNL Add Template].

   <!-- 
   
   r_add_template_options.xml
   
   -->

   | Alternativ | Beskrivning |
   |--- |--- |
   | Nytt filnamn | Anger namnet på mallen som du vill lägga till. Rätt filtillägg läggs automatiskt till i filnamnet, baserat på den malltyp du väljer.  Presentationsmallar har filtillägget .tmpl. Transportmallar har filtillägget .tpl. |
   | Ny malltyp | Här kan du välja en presentation eller en transportmall som du vill lägga till.  Se [Mallar](../c-about-design-menu/c-about-templates.md). |

   Se även [Redigera en presentation eller en transportmall](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).
1. Klicka på **[!UICONTROL Add]**.
1. (Valfritt) Gör något av följande på sidan [!DNL Templates]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en presentation eller en transportmall {#task_800E0E2265C34C028C92FEB5A1243EC3}

Du kan använda mallredigeraren för att visa och redigera innehållet i presentations- och transportmallsfilerna.

<!-- 

t_editing_a_template.xml

 -->

Du kan redigera och testa dina presentations- och transportmallar medan besökarna på webbplatsen fortsätter att använda liveversionerna av mallarna. Du testar den mellanlagrade mallen med den mellanlagrade versionen av din sökdomän-URL. Du kan till exempel testa den mellanlagrade transportmallen genom att köra en mellanlagrad fråga ( `sp_staged=1`) med `sp_t` som är inställd på transportmallens namn. När du är nöjd med hur layouten visas kan du använda **[!UICONTROL Push Live]** inifrån mallredigeraren för att göra mallen offentlig. När mallen är publicerad börjar besökarna använda den.

Använd taggreferensen för presentationsmallen om du vill lära dig hur du kopplar ihop presentationsmallen med komponenter för guidad sökning, t.ex. ansikten, vägbeskrivningar och menyer.

Se [Presentationsmalltaggar](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64)

Använd transportmallens taggreferens för att lära dig mer om taggarna som ska användas i transportmallar.

Se [Transportmallstaggar](../c-appendices/c-templates.md#reference_227D199F5A7248049BE1D405C0584751)

**[!UICONTROL To edit a presentation or a transport template]**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. Klicka på ett presentations- eller transportmallfilnamn på sidan [!DNL Templates].
1. Gör de ändringar du vill av taggarna och kodningen på sidan [!DNL Template Editor].

   Var försiktig med de ändringar du gör i [!DNL Template Editor]; det finns ingen Ångra-funktion. Om du gör en oönskad ändring och vill gå tillbaka till den tidigare versionen av filen kan du klicka på **[!UICONTROL Cancel]** för att gå tillbaka till malltabellen (förutsatt att du inte sparat några ändringar fram till den tidpunkten). Om du redan har sparat ändringarna kan du använda **[!UICONTROL History]** i redigeraren för att återställa ändringarna.
1. (Valfritt) Klicka på **[!UICONTROL Insert Symbol]** om du vill ange specialtecken och symboler som inte har motsvarande tangenter på tangentbord för amerikansk engelska.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

1. Stäng mallredigeringssidan när du är klar; du kommer tillbaka till mallsidan.

## Kopiera en presentation eller en transportmallfil {#task_B744AB3384C84DD59C33CD25E18C2C90}

Du kan använda **[!UICONTROL Copy Template]** för att spara tid genom att duplicera en befintlig presentationsmall (.tmpl) eller transportmall (.tpl) och lägga till den på mallsidan.

<!-- 

t_copying_a_presentation_or_a_transport_template.xml

 -->

Du måste ändra mallnamnet, malltypen eller både och. Om du inte gör några ändringar kopieras inte mallen.

Du måste ha en mall som redan har lagts till för att kunna kopiera en mall.

Se [Lägga till en ny presentations- eller transportmallfil](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

**Så här kopierar du en presentation eller en transportmallfil**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. På sidan [!DNL Templates] klickar du på **[!UICONTROL Copy]** i listrutan bredvid ett mallnamn som du vill kopiera.
1. I dialogrutan [!DNL Copy Template] anger du ett eller flera av de alternativ du vill använda.
1. Klicka på **[!UICONTROL Copy]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Byta namn på en presentation eller en transportmallfil {#task_CC30050FC2DE4898BF44379D8378EB31}

Du kan använda [!DNL Rename Template] för att ändra namnet på en befintlig presentationsmall (.tmpl) eller en transportmall (.tpl).

<!-- 

t_renaming_a_presentation_or_a_transport_template_file.xml

 -->

Du kan också ändra malltypen om du vill.

Du måste ha en mall som redan har lagts till för att kunna byta namn på en mall.

Se [Lägga till en ny presentations- eller transportmallfil](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

**Byta namn på en presentation eller en transportmallfil**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. På sidan [!DNL Templates] klickar du på **[!UICONTROL Rename]** i listrutan bredvid ett mallnamn som du vill byta namn på.
1. I dialogrutan [!DNL Rename Template] anger du ett eller flera av de alternativ du vill använda.
1. Klicka på **[!UICONTROL Rename]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en presentation eller en transportmallfil {#task_67E532C2B83A449687737E3B06C5AA58}

Du kan använda **[!UICONTROL Delete Template]** för att ta bort en befintlig presentationsmall (.tmpl) eller en transportmall (.tpl).

<!-- 

t_deleting_a_presentation_or_a_transport_template_file.xml

 -->

Du kanske redan har en motsvarande version av den mellanlagrade mallen som publiceras. I så fall måste du se till att du gör den borttagna mallen offentlig med **[!UICONTROL Staging]** så att den också tas bort från den aktiva miljön. Du kan också använda **[!UICONTROL Push Live]** på mallsidan.

Se [Om mellanlagring](../c-about-staging.md#concept_08B8F3CA1F4241108F14BA7FC7806CA7)

Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)

Du måste ha en mall som redan har lagts till för att kunna ta bort en mall.

Se [Lägga till en ny presentations- eller transportmallfil](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

**Ta bort en presentation eller en transportmallfil**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. På sidan [!DNL Templates] klickar du på **[!UICONTROL Delete]** i listrutan bredvid ett mallnamn som du vill ta bort.
1. Klicka på **[!UICONTROL Delete.]** i dialogrutan [!DNL Delete Template]
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Förhandsgranskning av presentationsmallen minimerad {#task_1757B6207CC74221AE4BFFE5674D320B}

Du kan använda **[!UICONTROL Preview minimized]** för att se hur den reducerade sidvikten för en presentationsmall skulle se ut om du väljer att minimera den.

<!-- 

t_previewing_the_presentation_template_minimized.xml

 -->

Om du minimerar huvudpresentationsmallen måste du komma ihåg att aktivera minimering för inkluderade (med tagg för guidad infogning) mallar eftersom det här alternativet inte kan ärvas.

Se [Minska sidbredden för en presentationsmall på din...](../c-about-design-menu/c-about-templates.md#task_B09BB3CE89714DEAAE8D9A899CF3009E)

Du måste ha en mall som redan har lagts till för att förhandsgranska mallen minimerad.

Se [Lägga till en ny presentations- eller transportmallfil](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012)

Du kan förhandsgranska XML-koden för en transportmallfil.

Se [Förhandsgranska XML för en transportmallfil](../c-about-design-menu/c-about-templates.md#task_58C6C52078E14AD88D2B2F0B3C439AE8)

**Förhandsgranska presentationsmallen minimerad**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. På sidan [!DNL Templates] klickar du på **[!UICONTROL Preview minimized]** i listrutan bredvid ett presentationsmallnamn.

   Använd kolumnen **[!UICONTROL Type]** i tabellen Mallar för att sortera mallarna efter presentation och transport.
1. (Valfritt) På sidan [!DNL Preview Minimized Template] markerar du **[!UICONTROL Wrap lines]** för att läsa taggarna i det definierade fönstret.
1. Klicka på **[!UICONTROL Close]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Minska sidbredden för en presentationsmall på webbplatsen {#task_B09BB3CE89714DEAAE8D9A899CF3009E}

Du kan minska sidbredden för en presentationsmall genom att använda alternativet **[!UICONTROL Minimize]** i malltabellen.

<!-- 

t_reducing_the_page_weight_of_a_presentation_template.xml

 -->

Genom att minska mallens sidbredd minimerar du dynamiskt infogat JavaScript och CSS. Du kan också ta bort överflödigt tomt utrymme i HTML-koden. Genom att minimera sidbredden i presentationsmallen kan du leverera sökresultaten snabbare.

Du kan också förhandsgranska utseendet på den minimerade presentationsmallen genom att använda **[!UICONTROL Preview minimized]**.

Se [Förhandsgranska presentationsmallen minimerad](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**[!UICONTROL To reduce the page weight of a presentation template on your website]**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. Markera kryssrutan för en eller flera presentationsmallfiler som du vill skicka som minimerade på webbplatsen under kolumnen [!DNL Minimize] på sidan [!DNL Templates].

   Använd kolumnen **[!UICONTROL Type]** i tabellen [!DNL Templates] för att sortera mallarna efter Presentation och Transport.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Anger standardpresentationsmallfilen som ska användas på webbplatsen {#task_C1E8CE817E4D43E096167A347C54DD53}

När du har flera presentationsmallar kan du ange vilken mall som ska användas först för att visa sökresultaten.

<!-- 

t_setting_the_default_presentation_template_file_to_use.xml

 -->

Du kan använda reglerna för försökning, eftersökning och affärsregler för att avgöra när någon av dina andra presentationsmallar ska användas.

Se [Om regler för försökning](../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F).

Se [Om regler för eftersökning](../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE).

Se [Om affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

Det är vanligt att ha en regel som &quot;Ställ in målpresentationsmallen på xxxx för varje sökning.&quot; När en sådan regel är på plats verkar det som om ändringar av standardmallen på mallsidan inte har någon effekt.

**[!UICONTROL To set the default presentation template file to use on your website]**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. Klicka på alternativknappen under kolumnen [!DNL Default] på sidan [!DNL Templates] till motsvarande presentationsmallfil som du vill ska fungera som standard.

   Använd kolumnen **[!UICONTROL Type]** i tabellen [!DNL Templates] för att sortera mallarna efter Presentation och Transport.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Förhandsgranska XML för en transportmallfil {#task_58C6C52078E14AD88D2B2F0B3C439AE8}

Du kan använda [!DNL Preview] för att granska XML för en transportmall som du har lagt till.

<!-- 

t_previewing_the_xml_of_a_transport_template_file.xml

 -->

Du måste ha en transportmall som redan har lagts till för att kunna förhandsgranska mallens XML.

Se [Lägga till en ny presentations- eller transportmallfil](../c-about-design-menu/c-about-templates.md#task_73199757B6E748CAA604902FF913F012).

Du kan förhandsgranska minimerade presentationsmallfiler om du vill visa den reducerade sidbredden.

Se [Förhandsgranska presentationsmallen minimerad](../c-about-design-menu/c-about-templates.md#task_1757B6207CC74221AE4BFFE5674D320B).

**Förhandsgranska XML-koden för en transportmallfil**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Templates]** på produktmenyn.
1. På sidan [!DNL Templates] klickar du på **[!UICONTROL Preview]** i listrutan bredvid namnet på en transportmall.

   Använd kolumnen **[!UICONTROL Type]** i tabellen [!DNL Templates] för att sortera mallarna efter Presentation och Transport.
1. Stäng visningsfönstret och återgå till [!DNL site search/merchandising].
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

