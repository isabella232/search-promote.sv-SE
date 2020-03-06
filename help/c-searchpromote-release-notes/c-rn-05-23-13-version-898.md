---
description: 'null'
seo-description: 'null'
seo-title: Sökning&stämpel;amp;Promote 8.9.8 Versionsinformation (05/23/2013)
solution: Target
title: Sökning&stämpel;amp;Promote 8.9.8 Versionsinformation (05/23/2013)
topic: Release Notes,Site search and merchandising
uuid: ff4bfc53-1d0e-4b7d-83ad-54c81d3f9769
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.9.8, versionsinformation (05/23/2013){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Ny funktion </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Vanliga fraser - stöd för exakt matchning </p> </td> 
   <td colname="col2"> <p> Vanliga fraser innehåller termer om två eller flera ord som genomsöks som en helhet, t.ex. "bockklippning" eller "tankstank" - och inte som separata delar. En vanlig fras har en betydelse som är unik och som skiljer sig från någon av dess enskilda delar. </p> <p> Du har en ordlista med vanliga fraser som hör till ditt företag. När en kund gör en sökfråga som innehåller flera ord utförs en sökning i ordlistan för exakt samma matchning. </p> <p>Du kan lägga till, redigera och ta bort vanliga fraser. Du kan också gruppera vanliga fraser som liknar domänordlistor. Du kan t.ex. gruppera vanliga fraser efter kläder, tyg, smycken, mått, butik och allmänt. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-common-phrases.md#concept_4946E53586DF492EAEB1B7F757FD440F" format="dita" scope="local"> Om vanliga fraser </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Korrigeringar och förbättringar**

* CGI-parametern för serverdelssökning fungerar `sp_date_range_#` inte för användardefinierade fält.

   Se CGI-parametrar för [serverdelssökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

* Återställande **[!UICONTROL History]** version uppdaterade inte innehållet i fältet för URL-startpunkter.

   Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   Se även [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

* JSON-kodningen hanterade inte felaktigt kodade tecken.
* Stöd har nu lagts till som gör att du kan skicka ett mellanlagrat index live på fjärrbasis.

   Se [Fjärrkontroll för indexering](../c-about-index-menu/c-about-remote-control-for-indexing.md#concept_C79B322190E84106A434E5C6D4A4118F).

