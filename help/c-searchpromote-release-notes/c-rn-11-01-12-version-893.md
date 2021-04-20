---
description: Search&amp;Promote 8.9.3 versionsinformation.
solution: Target
title: Sökning&stämpel;amp;Promote 8.9.3 versionsinformation (11/01/2012)
topic: Release Notes,Site search and merchandising
uuid: 7bc7bcb6-f47f-4e05-94e5-a22a13a187b7
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# Versionsinformation om Search &amp; Promote 8.9.3 (11/01/2012){#search-promote-release-notes}

## Versionsinformation om Search &amp; Promote 8.9.3 (11/01/2012) {#concept_85F5B4B4C40C43FEA3AD63E6EA5593CF}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nya funktioner och förbättringar </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fasett Rail </p> </td> 
   <td colname="col2"> <p> 
     <!--3309390--> Lagt till det nya  <span class="uicontrol"> Facet </span> Järnoption som ger dig större kontroll över ordningen på facet-familjer och facet-namn (efter antal, i alfabetisk ordning). </p> <p>Se <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> Om Fasett Rail</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Kapslade aspekter </p> </td> 
   <td colname="col2"> <p> Stöd för alternativ sortering av kapslade aspekter har lagts till. </p> <p>Se <a href="../c-about-design-menu/c-about-facet-rails.md#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB" format="dita" scope="local"> Om Fasett Rail</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anteckningsfält i rankningsregler </p> </td> 
   <td colname="col2"> <p> 
     <!--3063772--> Ett  <span class="wintitle"> </span> anteckningsfält med flera rader har lagts till i dialogrutan  <span class="wintitle"> Lägg till </span> rankningsmetod och i dialogrutan  <span class="wintitle"> Redigera </span> rankningsmetod för rankningsregler och regelgruppsdefinitioner. </p> <p>Rankningsregelanteckningar visas på sidan <span class="wintitle"> Definiera rankningsregler</span>. Regelgruppsanteckningar visas när du redigerar definitionen. </p> <p>Se <a href="../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397" format="dita" scope="local"> Om rankningsregler</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Affärsregler </p> </td> 
   <td colname="col2"> <p> 
     <!--3331637--> Förbättrat stöd för landningssidor genom att ta bort naturliga resultat i en affärsregel med det nya alternativet  <span class="uicontrol"> Ta bort alla </span> resultat. </p> <p>Använd det här nya alternativet tillsammans med andra affärsregelåtgärder för att skapa"inlästa landningssidor". Det innebär att du vill skapa en sidas innehåll utifrån åtgärder för affärsregler exklusivt och du måste ignorera de"naturliga" resultaten av sökningen. </p> <p>Se <a href="../c-about-rules-menu/c-about-business-rules.md#task_BD3B31ED48BB4B1B8F1DCD3BFA2528E7" format="dita" scope="local"> Lägga till en ny affärsregel</a> eller <a href="../c-about-rules-menu/c-about-business-rules.md#task_375CFA75D1D94D9E92A35DE1228E5087" format="dita" scope="local"> Redigera en affärsregel</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Banderoller och affärsregler </p> </td> 
   <td colname="col2"> <p> Ett supportalternativ har lagts till där du kan välja att inte skicka ut banners live när affärsregeln som refererar till banderollen publiceras. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Korrigeringar**

* Affärsreglerna fungerade inkonsekvent när det fanns ett [!DNL Stage]-index.
* Regler för automatisk rangordning tillämpas nu på inlästa landningssidor.

   Se tabellen med alternativ i [Lägga till en rankningsregel](../c-about-rules-menu/c-about-ranking-rules.md#task_A132789FD4E5423DAD090DCDA7311E8A).

* [!DNL promosearch.cgi] returnerade inte kampanjer.

   Se [Om sökningar](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

* Publiceringsregler som refererade till många banners misslyckades ibland.

   Se [Om banners](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA).

* **[!UICONTROL Did You Mean]** sökfrågecachelagring är nu inaktiverad.

   Se [Om Menade du](../c-about-linguistics-menu/c-about-did-you-mean.md#concept_7D4F3C29EF184B538B8AE2ECAE0CDC5E).

