---
description: Du kan definiera de datumformat som ska användas när fält med datatypen"date" tolkas och indexeras.
solution: Target
title: Datumformat
topic: Appendices,Site search and merchandising
uuid: 148914b5-33ef-41db-8404-67c03f6f0832
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---


# Datumformat{#date-formats}

Du kan definiera de datumformat som ska användas när fält med datatypen&quot;date&quot; tolkas och indexeras.

Formatet för datum och tid anges med en formatsträng. Formatsträngen består av noll eller flera konverteringsspecifikationer (en konverteringsspecifikation består av ett procenttecken och ett annat tecken) och vanliga tecken. En standardlista med datumformatsträngar finns för varje datumfält.

Du har fullständig kontroll över den här listan och kan lägga till eller ändra den efter webbplatsens behov. Den översta formatsträngen har företräde och efterföljande formatsträngar används bara om tolkningen av innehållet i en viss metadatatagg genererar ett fel.

Anta att du har angett följande datumformat:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d, %Y %T %Z </p> <p>%b %d, %Y %T %Z </p> <p>%A %B %d, %Y %T %Z </p> <p>%A %b %d, %Y %T %Z </p> <p>%a %B %d, %Y %T %Z </p> <p>%a %b %d, %Y %T %Z </p> <p>%d %b %Y %T %Z </p> </td> 
  </tr> 
 </tbody> 
</table>

Det första formatet, %B %d, %Y %T %Z, matchar datum som följande 20 september 2014 13:12:00 PDT. Om metadatataggens innehåll inte kan parsas med den här formatsträngen, kommer nästa tillgängliga format, %b %d, %Y %T %Z att försökas. Formatet matchar datum enligt följande: &quot;20 september 2014 3:12:00 PDT&quot;. Om metadatataggens innehåll inte kan analyseras med den här formatsträngen, flyttas webbplatssökningen/försäljningen nedåt i listan med formatsträngar tills en formatsträng som fungerar hittas.

I följande tabell beskrivs tillgängliga datumformatsträngar:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Dataformat </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%A </p> </td> 
   <td colname="col2"> <p>Matchar den nationella representationen av det fullständiga veckodagens namn, till exempel "Måndag". Den nationella representationen bestäms av inställningen "Språk" i alternativet "Ord och språk" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a </p> </td> 
   <td colname="col2"> <p> matchar den nationella representationen av det förkortade veckodagens namn, där förkortningen är de tre första tecknen, t.ex. "mån." Den nationella representationen bestäms av inställningen "Språk" i alternativet "Ord och språk" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%B </p> </td> 
   <td colname="col2"> <p> matchar den nationella representationen av det fullständiga månadsnamnet, t.ex. "Juni." Den nationella representationen bestäms av inställningen "Språk" i alternativet "Ord och språk" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b </p> </td> 
   <td colname="col2"> <p> matchar den nationella representationen av det förkortade månadsnamnet, där förkortningen är de tre första tecknen, t.ex. "Jun." Den nationella representationen bestäms av inställningen "Språk" i alternativet "Ord och språk" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%D </p> </td> 
   <td colname="col2"> <p> motsvarar "%m/%d/%y", t.ex. "06/06/01" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d </p> </td> 
   <td colname="col2"> <p> matchar dagen i månaden som ett decimaltal (01-31) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%e </p> </td> 
   <td colname="col2"> <p> matchar dagen i månaden som ett decimaltal (1-31), enstaka siffror föregås av en tom </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%H </p> </td> 
   <td colname="col2"> <p> matchar timmen (24-timmars klocka) som ett decimaltal (00-23) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%h </p> </td> 
   <td colname="col2"> <p> matchar den nationella representationen av det förkortade månadsnamnet, där förkortningen är de tre första tecknen, t.ex. "Jun" (samma som %b) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%I </p> </td> 
   <td colname="col2"> <p> matchar timmen (12-timmars klocka) som ett decimaltal (01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%j </p> </td> 
   <td colname="col2"> <p> matchar årets dag som ett decimaltal (001-366) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%k </p> </td> 
   <td colname="col2"> <p> matchar timmen (24-timmars klocka) som ett decimaltal (0-23), enstaka siffror föregås av en tom </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%l </p> </td> 
   <td colname="col2"> <p> matchar timmen (12-timmars klocka) som ett decimaltal (1-12), enstaka siffror föregås av en tom </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%M </p> </td> 
   <td colname="col2"> <p> matchar minuten som ett decimaltal (00-59) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%m </p> </td> 
   <td colname="col2"> <p> matchar månaden som ett decimaltal (01-12) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%p </p> </td> 
   <td colname="col2"> <p> matchar den nationella representationen av antingen "ante meridiem" eller "post meridiem", beroende på vad som är tillämpligt, t.ex. "PM." Den nationella representationen bestäms av inställningen "Språk" i alternativet "Ord och språk" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%R </p> </td> 
   <td colname="col2"> <p> motsvarar "%H:%M", t.ex. "13:23" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%r </p> </td> 
   <td colname="col2"> <p> motsvarar "%I:%M:%S %p", t.ex. "01:23:45 PM" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%s </p> </td> 
   <td colname="col2"> <p> matchar det andra som ett decimaltal (00-60) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%T </p> </td> 
   <td colname="col2"> <p> motsvarar "%H:%M:%S", t.ex. "13:26:47" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%U </p> </td> 
   <td colname="col2"> <p> matchar årets veckonummer (söndag som veckodag) som ett decimaltal (00-53) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%v </p> </td> 
   <td colname="col2"> <p> motsvarar "%e-%b-%Y", t.ex. "6-Jun-2001" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Y </p> </td> 
   <td colname="col2"> <p> matchar året med århundradet som ett decimaltal, t.ex. "2001" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%y </p> </td> 
   <td colname="col2"> <p> matchar året utan årtionde som ett decimaltal (00-99) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%Z </p> </td> 
   <td colname="col2"> <p> matchar tidszonsnamnet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%% </p> </td> 
   <td colname="col2"> <p> matchar "%" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Standardformatsträngar**

Följande standardformatsträngar används av mallar. Du kan lägga till eller redigera listan efter behov.

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Standardformatsträng </p> </th> 
   <th colname="col2" class="entry"> <p>Resultatexempel </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>%B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5 september 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5 september 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Söndag 5 september 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%A %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Söndag 5 september 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %B %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sun 5 september 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%a %b %d, %Y %T %Z </p> </td> 
   <td colname="col2"> <p> Sun Sep 5, 1999 13:12:00 PDT </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>%d %b %Y %T %Z </p> </td> 
   <td colname="col2"> <p> 5 september 1999 13:12:00 PDT </p> </td> 
  </tr> 
 </tbody> 
</table>

