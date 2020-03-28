---
description: 'null'
seo-description: 'null'
seo-title: Sökning&stämpel;amp;Promote 8.9.4 Versionsinformation (01/17/2013)
solution: Target
title: Sökning&stämpel;amp;Promote 8.9.4 Versionsinformation (01/17/2013)
topic: Release Notes,Site search and merchandising
uuid: a9d550f6-0a23-4c71-b123-c31b997e7384
translation-type: tm+mt
source-git-commit: ffdec2cfcb30e733c664a7d1ca23868b7a9a9aa5

---


# Search&amp;Promote 8.9.4, versionsinformation (01/17/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nya funktioner och förbättringar </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Regler </p> </td> 
   <td colname="col2"> <p> Lagt till möjlighet att skapa textbundna anteckningar när du skapar regler för Frågerengöring, regler för försökning och regler för eftersökning. I anteckningsfältet kan du dokumentera och förklara reglerna. </p> <p>Se <a href="../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C" format="dita" scope="local"> Om renderingsregler</a>för frågor. </p> <p>Se <a href="../c-about-rules-menu/c-about-pre-search-rules.md#concept_5BF84BB6FACB4645BA9CB7496A01CD1F" format="dita" scope="local"> Om regler</a>för försökning. </p> <p>Se <a href="../c-about-rules-menu/c-about-post-search-rules.md#concept_AF6ADFCC0ADF4A788003964939917FDE" format="dita" scope="local"> Om regler</a>för eftersökning. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Guidad sökning </p> </td> 
   <td colname="col2"> <p> Guidade söktaggar har lagts till för att ange den totala tiden som en sökning tog. </p> <p> <span class="codeph"> &lt;guided-search-time&gt;</span> - Anger hur lång tid sökningen tog. Det returnerade söktidsvärdet anges i ms. </p> <p> <span class="codeph"> &lt;guided-fall-through-searches&gt;</span> - Returnerar antalet kärnsökningar som används för att skapa sidan med sökresultat. </p> <p> <span class="codeph"> &lt;guided-if-fall-through-search&gt;</span> - Testar om antalet grundsökningar är större än 1. </p> <p>Se även Övrigt språk i <a href="../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64" format="dita" scope="local"> Presentationsmallstaggar</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Korrigeringar**

* Termrapporten ignorerar nu asterisken.

   Se [Visa termrapporten eller Null Search Terms Report...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* Öppna **[!UICONTROL Reports > Null Search Terms Report]**, välj en tidsrymd och visa sedan rapporten. Klicka på ett ord i rapporten för att öppna sökningen och klicka sedan på Visa rapport igen. Antalet sökningar för nyckelordet du klickade på ökade två gånger. Den här är nu lagad.

   Se [Visa termrapporten eller Null Search Terms Report...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* En prestandaoptimering gjordes när ni publicerade affärsreglerna.

   Se [Affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Möjligheten att ta bort i [!DNL Breadcrumbs] fungerade inte hela tiden.

   Se [Om vägbeskrivningar](../c-about-design-menu/c-about-breadcrumbs.md#concept_FB8A943C594A4A1593B118141DA61F03).

* Om du inte använde återskapa kunde inte ändrade rankningsregler användas i sökresultaten.

   Se [Om rankningsregler](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

   Se [Om rangordningsindex](../c-about-index-menu/c-about-re-rank-index.md#concept_147B0A9FCD51451787DA898E06F7C692).

