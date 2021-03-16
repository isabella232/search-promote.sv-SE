---
description: Sök&amp;Promote 8.11.0 versionsinformation.
solution: Target
title: Sökning&stämpel;amp;Promote 8.11.0 Versionsinformation (10/29/2013)
topic: Versionsinformation,Webbplatssökning och -försäljning
uuid: 973f9608-a5c7-4571-ae2b-6f1fa05bc862
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---


# Versionsinformation om Search &amp; Promote 8.11.0 (2013-10-29){#search-promote-release-notes}

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Ny funktion </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Dansk decomununder </p> </td> 
   <td colname="col2"> <p> Det finns nu en mekanism som gör att <span class="keyword"> Adobe Search &amp; Promote</span> kan komma åt de tjänster för språkidentifiering, dekomposition, ordstamning och segmentering som Adobe tillhandahåller. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Förbättringar och korrigeringar**

* Förbättringar har gjorts i de befintliga [!DNL Search&Promote] tabellmatchningsfunktionerna. Förbättringarna ger bättre stöd för kundernas krav i samband med allt mer komplexa relationer mellan SKU och produktdata.

   >[!NOTE]
   >
   >Den här funktionen är inte aktiverad som standard. Kontakta Adobe kundtjänst om du vill aktivera funktionen i Search &amp; Promote.

* Ett alternativ har lagts till som tillåter att guidad sökning sorterar ansikten med kontots språkinställning.

   >[!NOTE]
   Den här funktionen är inte aktiverad som standard. Kontakta Adobe kundtjänst om du vill aktivera funktionen i Search &amp; Promote.

* Ett alternativ har lagts till för att öka antalet fasettvärden som en användare kan ange för flervalsaspekter.

   >[!NOTE]
   Den här funktionen är inte aktiverad som standard. Kontakta Adobe kundtjänst om du vill aktivera funktionen i Search &amp; Promote.

* Kryssrutealternativet **[!UICONTROL Only allow searches that use HTTPS]** har lagts till i **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Restrictions]**.

   Se [Om begränsningar](../c-about-settings-menu/c-about-searching-menu.md#concept_B5B527E04EBF4E9AB5956EEF881DDBF1).

* Ett alternativ har lagts till i **[!UICONTROL Settings]** > **[!UICONTROL Searching]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]** > **[!UICONTROL Generic Feed]** för att bevara tabbtecken i panelen [!DNL File Submission] i guiden.

   Se [Skapa en feed](../c-about-settings-menu/c-about-searching-menu.md#task_63179C1FC359497483CD6CE13FD1C250).

* Ökade storleken på data som accepteras i vart och ett av de övre och nedre fälten för det nya ansiktsdefinitionsformuläret från 80 tecken till 1 000.

   Se [Om ansikten](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

* Felsökningsparametrar för guidad sökning rapporterar nu korrekt företagsregelnummer.
* Affärsreglerna tillämpas nu i Live-miljön.
* Proximity-sökning fungerar nu vid sökning efter longitud/latitud, för konton som konfigurerats med Språk = &quot;Danska (Danmark)&quot;.
* Resultatbaserade utlösare utan tilldelat schema aktiveras nu.
* Konsekventa resultat rapporteras nu när du använder alternativet **[!UICONTROL Ignore Apostrophes]** i **[!UICONTROL Linguistics]** > **[!UICONTROL Words & Language]**.

   Se [Om ord och språk](../c-about-linguistics-menu/c-about-words-and-language.md#concept_CEB4B9576F3C4E2EB87B352EEC738D79).

* Funktionen Komplettera ordlista automatiskt fungerar nu på ett stort antal sidor.

