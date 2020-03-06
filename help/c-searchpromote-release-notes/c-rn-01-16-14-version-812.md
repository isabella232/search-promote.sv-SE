---
description: 'null'
seo-description: 'null'
seo-title: Sökning&stämpel;amp;Promote 8.12.0 Versionsinformation (01/16/2014)
solution: Target
title: Sökning&stämpel;amp;Promote 8.12.0 Versionsinformation (01/16/2014)
topic: Release Notes,Site search and merchandising
uuid: 4db10eb4-11bf-4483-a7f2-87981d9c7a50
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e

---


# Search&amp;Promote 8.12.0 Release Notes (01/16/2014){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nya funktioner och förbättringar </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ordlistor för ordlistor har lagts till </p> </td> 
   <td colname="col2"> <p> </p> <p> Ordlistor för ordlistor lades till för indonesiska och turkiska språk. </p> <p>Se <a href="../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034" format="dita" scope="local"> Om ordlistor</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exportera rapporter </p> </td> 
   <td colname="col2"> <p> 
     <!--3683368-->Du kan nu exportera data till CSV från följande rapporter: 
     <ul id="ul_93B619DBB3444F64BD6D7F9E969AB1E1"> 
      <li id="li_96DDE1A196834845A0FA319903C5934B"> <p>Termrapport </p> </li> 
      <li id="li_4F1A19DE98C84F8CAD963EEA2B38ED7A"> <p>Rapport om null-sökvillkor </p> </li> 
      <li id="li_A7716C62C4D44CD69D411C3FEE246D96"> <p>Rapport över sökförfrågningar </p> </li> 
     </ul> </p> <p>Se <a href="../c-about-reports-menu/c-about-reports-menu.md#concept_5F901459C7AB461BAB30B305957EB00C" format="dita" scope="local"> Om menyn</a>Rapporter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Associera inte </p> </td> 
   <td colname="col2"> <p>Nu kan du styra vilka två ord som inte ska kopplas ihop i sökresultat, till exempel"Svetta" och"Skeva". </p> <p> <p>Obs!  Den här funktionen är inte aktiverad som standard. Kontakta Adobes kundtjänst om du vill aktivera funktionen i Search&amp;Promote. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Korrigeringar**

* Det gick inte att lägga till resultat i en rekommenderad zon som låg utanför de valda villkoren för facettering.
* Det gick inte att spara resultatbaserade regler för ett konto med endast HTTPS-sökning.
* Det gick inte att konfigurera en affärsregel för &quot;är inte en mobiltelefon&quot;.

   Se [Affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

* Att utföra en lagerfiltersökning returnerade inte några resultat.
* Storleksordningen uppdaterades inte.
* Alternativet för en anpassad regeldefinition har lagts till på sidan Frågerensning.

   Se [Om renderingsregler](../c-about-rules-menu/c-about-query-cleaning-rules.md#concept_17F3CDDC3C8A4128AF092A82B777B86C)för frågor.

* Terms-rapporten upprepade poster om det inte fanns tillräckligt med data.

   Se [Visa termrapporten eller Null Search Terms Report...](../c-about-reports-menu/c-about-reports-menu.md#task_53B7ED1582DD4B0E8376546A7AFC789A).

* Att aktivera en enda affärsregel i realtid fungerade i mellanlagringsläge, men misslyckades i Live-läge.
* Automatiskt slutförda redigeringar i inkluderings- eller uteslutningslistor sparades inte i historiken och kunde därför inte återställas.

   Se [Komplettera](../c-about-auto-complete.md#concept_093A9CD754864BA79B456FE4BEB64578)automatiskt.

