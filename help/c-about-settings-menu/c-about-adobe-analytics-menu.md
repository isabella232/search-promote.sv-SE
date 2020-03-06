---
description: Använd menyn Adobe Analytics för att konfigurera autentisering av Adobe Analytics-mått, hantera Adobe Analytics-mått i en Report Suite eller använd SAINT för att förbättra Adobe Analytics-rapporter genom att acceptera tabelldata från externa källor.
seo-description: Använd menyn Adobe Analytics för att konfigurera autentisering av Adobe Analytics-mått, hantera Adobe Analytics-mått i en Report Suite eller använd SAINT för att förbättra Adobe Analytics-rapporter genom att acceptera tabelldata från externa källor.
seo-title: Om Adobe Analytics-menyn
solution: Target
subtopic: Adobe Analytics
title: Om Adobe Analytics-menyn
topic: Settings,Site search and merchandising
uuid: 5536edf1-d3a4-47af-a307-6e46f385f738
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a

---


# Om Adobe Analytics-menyn{#about-the-adobe-analytics-menu}

Använd menyn Adobe Analytics för att konfigurera autentisering av Adobe Analytics-mått, hantera Adobe Analytics-mått i en Report Suite eller använd SAINT för att förbättra Adobe Analytics-rapporter genom att acceptera tabelldata från externa källor.

## Ställa in autentisering av Adobe Analytics-mått {#task_8AA93F6273B747F9B4DE9E8DFBCBDC42}

Om du vill lägga in Adobe Analytics-statistik i webbplatsens sök- och säljrangordning måste du först skaffa en inloggning för Adobe Analytics Web Services. När du har fått inloggningsinformationen kan du använda den för att konfigurera Adobe Analytics-autentisering i webbplatssökningar/-marknadsföring.

**Ställa in autentisering med Adobe Analytics-mått**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Authentication]**.
1. På [!DNL Setup Adobe Analytics Metrics Authentication] sidan anger du den information som efterfrågas i varje fält.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Textfält </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Företagsnamn för Adobe Analytics </p> </td> 
      <td colname="col2"> <p>Samma företagsnamninställning som används för att logga in på ditt Adobe Analytics-konto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Användarnamn för webbtjänster </p> </td> 
      <td colname="col2"> <p>Användarnamnet för webbtjänster som är kopplat till ditt Adobe Analytics-konto. </p> <p>Du kan få den här informationen i Adobe Analytics. På Adobe Analytics-menyraden klickar du på <span class="uicontrol"> Admin <b></b> &gt; </span><span class="uicontrol"> Admin Console <b></b> &gt; </span><span class="uicontrol"> <b></b> </span> <span class="uicontrol"> <b></b> </span>Company &gt;¥¥Web Services¥. Informationen finns i tabellen API Access Information. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Delad hemlighet för webbtjänster </p> </td> 
      <td colname="col2"> <p>Den delade hemlighet för webbtjänster som är kopplad till ditt Adobe Analytics-konto. </p> <p>Du kan få den här informationen i Adobe Analytics. På Adobe Analytics-menyraden klickar du på <span class="uicontrol"> Admin <b></b> &gt; </span><span class="uicontrol"> Admin Console <b></b> &gt; </span><span class="uicontrol"> <b></b> </span> <span class="uicontrol"> <b></b> </span>Company &gt;¥¥Web Services¥. Informationen finns i tabellen API Access Information. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om Adobe Analytics-rapportsviter {#concept_1A51AEC5D40E459B813E7891D64B1BAE}

Om du vill använda Adobe Analytics Report Suite-data för webbplatssökning/försäljning måste du först skapa kopior av Adobe Analytics-data i webbplatsens sök-/säljkonto.

Du kan skapa nya Adobe Analytics Report Suite-definitioner eller visa eller ändra befintliga Adobe Analytics-rapportsviter och tillhörande mätvärden.

Första gången du öppnar Adobe Analytics via webbplatssökning/försäljning hämtas och cachelagras en lista över företagets tillgängliga rapportsviter. Om nya rapportsviter nyligen har lagts till, eller om befintliga har tagits bort, kan du uppdatera rapportsvitlistan och hämta listan över rapportsviter igen.

## Lägga till en Adobe Analytics Report Suite {#task_6DE17305EA7146DA8C30FF8FDF68A3C0}

Du kan välja en Adobe Analytics Report Suite som du kan basera dina regler för webbplatssökning/försäljning av rankning.

Den lista du kan välja mellan bör motsvara de rapportsviter som är tillgängliga från ditt Adobe Analytics-konto. Rapportsviten som du väljer avgör vilka mätvärden som är tillgängliga för användning i webbplatsens regler för sökning/försäljning av rankning.

Se [Om rankningsregler](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

När du har lagt till en Adobe Analytics Report Suite kan du redigera dess mätvärden.

Se [Redigera Adobe Analytics-statistik i en Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

**Lägga till en Adobe Analytics Report Suite**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. På sidan Adobe Analytics Report Suites klickar du på **[!UICONTROL Add Report Suite]**.
1. I listrutan för den nya tabellraden väljer du önskad rapportsvit.
1. Redigera Adobe Analytics-statistik för en Report Suite.

## Redigera Adobe Analytics-statistik för en Report Suite {#task_360904CCBBB140238ADA036C3CC07664}

Om du vill inkludera Adobe Analytics-statistik i dina rankningsregler i webbplatssökningar/-försäljningar väljer du en eller flera av de mätvärden som är kopplade till den valda Report Suite. Sedan konfigurerar du alternativen som används för att hämta mätdata via Adobe Analytics-webbtjänsten.

Se [Lägga till en Adobe Analytics Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0).

Se [Konfigurera avancerade Adobe Analytics-alternativ](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_C0FF2D69F59D44D8943A7831ED7FEC19).

**Så här redigerar du Adobe Analytics-statistik för en Report Suite**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. På [!DNL Adobe Analytics Report Suites] sidan, under **[!UICONTROL Actions]** kolumnen, klickar du **[!UICONTROL Edit]** på den rapportsvit vars mätvärden du vill konfigurera.
1. Ange de mått som krävs på [!DNL Edit Adobe Analytics Metrics] sidan. Mätvärden som inte har en asterisk (*) bredvid meternamnet är valfria.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Report Suite </p> </td> 
      <td colname="col2"> <p>Visar namnet på den rapportserie som du har lagt till. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rapportsvyns namn </p> </td> 
      <td colname="col2"> <p>Anger ett aliasnamn för namnet på Adobe Analytics Report Suite. Det här alternativa namnet är användbart om samma Report Suite används i mer än en definition. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Välj rapporttyp </p> </td> 
      <td colname="col2"> <p>Anger värdet för rapporttypen som ska användas med den valda rapportsviten. Värdet identifierar nyckeln för varje returnerad resultatrad. </p> <p>Rapporttypen kallas även Adobe Analytics-elementet. </p> <p>Det här måttet krävs. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fältnamn för korsreferens </p> </td> 
      <td colname="col2"> <p>Anger ett metadatafält vars värden används som söknycklar i rapportsvitens data. </p> <p>Om inget värde är markerat ("— Ingen —"), är den här rapportsvitens data inte tillgängliga för användning i rankningsberäkningar ( <span class="uicontrol"><b>Regler</b> </span> &gt; <span class="uicontrol"> Rankningsregler <b></b> &gt; </span> <span class="uicontrol"> <b></b> </span>Redigera regler¥). </p> <p>När du väljer ett värde används värdena i det här fältet för att korsreferera webbplatssöknings-/försäljningsdokument med Adobe Analytics-data för den här rapportsviten, med det värde för rapporttyp som du valde tidigare. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Rapport om sökvillkor </p> </td> 
      <td colname="col2"> <p>Ger dig åtkomst till att skapa affärsregler och simulera söktermer från sidan <b>Adobe Analytics-dataförhandsgranskning</b> på scenen. </p> <p>Se <a href="../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0" type="task" format="dita" scope="local">Förhandsgranska Adobe Analytics-data</a>. </p> <p>En nedrullningsbar meny visas på varje rad med två alternativ: <b>Simulera söktermer</b> och <b>skapa ny affärsregel</b>. </p> <p>Båda alternativen använder data från rapporttypen som söktermer. Därför är den här funktionen bara användbar om rapporttypen representerar söktermer. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mått </p> </td> 
      <td colname="col2"> <p>Identifierar de mätvärden som du vill hämta och använda i webbplatsens regler för sökning/försäljning av rankning. </p> <p>De mätvärden som du konfigurerar här visas som val på <span class="uicontrol"> Regler <b></b> &gt; </span><span class="uicontrol"> Rankningsregler <b></b> &gt; </span> <span class="uicontrol"> <b></b> </span> <span class="uicontrol"> </span>Redigera regler-medlemssidor, när regelns datatyp är inställd på¥ Adobe Analytics Metric (Number). Alternativen visar en kombination av rapportsvitens namn eller rapportsvitens visningsnamn, om det anges, och de enskilda mätvärdenamnen. </p> <p>Det här måttet krävs. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Minsta måttvärde </p> </td> 
      <td colname="col2"> <p>Ange ett värde som inte är noll för att ange ett minimivärde för måttet. </p> <p>Om värdet är tomt, eller noll, hämtas alla värden för mätvärdet. i annat fall avbryts nedladdningen för det här måttet när det lägsta mätvärdet skickas. </p> <p>Adobe Analytics-statistik hämtas i fallande ordning. </p> <p>Klicka <span class="uicontrol"><b>+</b> </span> för att lägga till ytterligare mätdefinitioner; klicka <span class="uicontrol"><b>-</b> för </span> att ta bort mätdefinitioner som du inte längre behöver eller vill ha. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Mätperiod för Adobe Analytics (dagar) </p> </td> 
      <td colname="col2"> <p> Styr hur många dagar Adobe Analytics-mätvärden ska hämtas, från gårdagens datum. Inga försök görs att hämta data från den aktuella dagen. </p> <p>Standardvärdet är 7. </p> <p>Det här måttet krävs. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Adobe Analytics - hämta uppdateringsfrekvens (dagar) </p> </td> 
      <td colname="col2"> <p> Anger det minsta intervallet mellan hämtningar av Adobe Analytics-data som används för rankningsberäkningar. </p> <p>Index-utlösta hämtningar som inträffar inom intervallet för hämtningsuppdateringsintervall ignoreras. Manuella hämtningar ignorerar dock det här värdet. </p> <p>När du anger det här värdet till standardvärdet 1 hämtas Adobe Analytics-data inte mer än en gång inom en 24-timmarsperiod. Alla sökindex som finns inom intervallet för hämtningsuppdateringsintervall använder den senaste datauppsättningen som hämtades. </p> <p>Det här måttet krävs. </p> </td> 
      </tr> 
    </tbody> 
    </table>

   Se även [Om rankningsregler](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).
1. Klicka på **[!UICONTROL Save Changes]**.

   Du återgår till den mellanlagrade [!DNL Adobe Analytics Report Suites] sidan.
1. (Valfritt) Gör något av följande:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ta bort en Adobe Analytics-rapportserie {#task_0ACA172214D14654ABDB139F417B9F7D}

Du kan använda Ta bort om du vill ta bort en rapportserie från [!DNL Adobe Analytics Report Suites] sidan. Om du tar bort en Report Suite tas endast kopian av data bort från webbplatsens sök-/säljservrar. påverkar inte data i Adobe Analytics-system.

**Så här tar du bort en Adobe Analytics Report Suite**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. På [!DNL Adobe Analytics Report Suites] sidan, under **[!UICONTROL Actions]** kolumnen, klickar du **[!UICONTROL Delete]** på den rapportsvit du vill ta bort.
1. På [!DNL Adobe Analytics Delete Report Suite] sidan klickar du på **[!UICONTROL Delete]**.

## Förhandsgranska Adobe Analytics-data {#task_735CDCC1D8174B7B9F5B8E0AFA5F0CA0}

Du kan använda Förhandsgranska för att visa dina senast inlästa Adobe Analytics-mått.

I kolumnen Rad i tabellen visas numret för varje rad med mätdata, vilket anger den ursprungliga ordningen som Adobe Analytics-mätvärdena lästes in i.

I produktkolumnen visas det Adobe Analytics-element som är kopplat till varje rad med mätdata. Värdena i den här kolumnen används för att associera webbplatsens sök- och försäljningssidor med motsvarande mätvärden, enligt inställningarna i din rankningsdefinition.

Se [Om rankningsregler](../c-about-rules-menu/c-about-ranking-rules.md#concept_F555C076759B4E81B925441CFE707397).

Se [Konfigurera rankning](../c-about-rules-menu/c-about-ranking-rules.md#task_4CEBC13925B047FC95BDC217B48089C5).

De återstående kolumnerna visar de mätvärden som är kopplade till varje post.

Om tabellen är tom innebär det att du inte har läst in några Adobe Analytics-data än. Du kan stänga [!DNL Adobe Analytics Data Preview] sidan och sedan läsa in Adobe Analytics-data.

Se [Läsa in Adobe Analytics-data](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).
Om tabellen har angetts som en söktermrapport visas en liten triangel på varje rad. Du kan klicka på listrutan och välja **Simulera sökterm** eller **Skapa ny affärsregel**. Den åtgärd som du väljer tillämpas på den radens sökord, de data som finns i den andra kolumnen

**Förhandsgranska Adobe Analytics-data**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**. På [!DNL Adobe Analytics Report Suites] sidan, under [!DNL Actions] kolumnen, klickar du **[!UICONTROL Preview]** för den rapportsvit vars hämtade data du vill visa.

   * Klicka på **[!UICONTROL Reports]** > **[!UICONTROL Adobe Analytics Terms Reports]**. På [!DNL Adobe Analytics Terms Report] sidan, under [!DNL Actions] kolumnen, klickar du **[!UICONTROL Preview]** för den rapportsvit vars hämtade data du vill visa.

1. Använd navigerings- och visningsalternativen längst upp och längst ned på sidan för att visa data på [!DNL Adobe Analytics Data Preview] sidan.

   Klicka på en kolumnrubrik i tabellen om du vill sortera data i stigande eller fallande ordning.
1. Gör något av följande:

   * Klicka **[!UICONTROL Download to Desktop]** för att hämta och spara tabellen som en `.xlt` fil.

   * Stäng sidan när du är klar med förhandsgranskningen av Adobe Analytics-data och återgå till den tidigare visade sidan.

## Visa loggen från den senaste inläsningen av Adobe Analytics-data {#task_9C7D6E34BB6C4A40B7CA3EE36ACB0837}

Du kan använda Visa logg för att undersöka Adobe Analytics-dataloggfilen för den senaste hämtningsprocessen. Du kan också använda loggvyn för att övervaka en nedladdning som körs.

Se [Läsa in Adobe Analytics-data](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_2F3C55189B0A4049AB2113F2291CC181).

**Så här visar du loggen från den senaste inläsningen av Adobe Analytics-data**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. På [!DNL Adobe Analytics Report Suites] sidan klickar du på **[!UICONTROL View Log]**. Loggsida,
1. Använd navigerings- och visningsalternativen längst upp och längst ned på sidan för att visa logginformationen på [!DNL Adobe Analytics Data Log] sidan.
1. När du är klar stänger du sidan för att gå tillbaka till [!DNL Adobe Analytics Report Suites] sidan.

## Läsa in Adobe Analytics-data {#task_2F3C55189B0A4049AB2113F2291CC181}

Du kan hämta konfigurerade Adobe Analytics Report Suite-data till webbplatssökning/försäljning.

På sidan Datainläsning visas status för den senaste inläsningsåtgärden för Adobe Analytics med följande information:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Statusfält </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Status </p> </td> 
   <td colname="col2"> <p>Anger om det senaste datainläsningsförsöket lyckades eller misslyckades. Eller så visas status för en datainläsningsåtgärd som redan pågår. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Resultat </p> </td> 
   <td colname="col2"> <p>Visar antalet rader med mätdata som hämtades under det senaste datainläsningsförsöket. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Starttid </p> </td> 
   <td colname="col2"> <p>Visar det datum och den tid då den senaste datainläsningen startades. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stopptid </p> </td> 
   <td colname="col2"> <p>Visar datum och tid för slutförande av den senaste datainläsningen. Eller så anger det att den aktuella datainläsningen fortfarande pågår. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Så här läser du in Adobe Analytics-data**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. På [!DNL Stage Adobe Analytics Report Suites] sidan klickar du på **[!UICONTROL Load Adobe Analytics Data]**.
1. Gör något av följande på **[!UICONTROL Adobe Analytics Data Load]** sidan:

   * Klicka **[!UICONTROL Start Load]** för att starta inläsningen.

      Under en datainläsningsåtgärd innehåller raden **Förlopp** information om förloppet.

   * Klicka **[!UICONTROL Stop Load]** för att stoppa inläsningen.

1. Klicka **[!UICONTROL Close]** för att gå tillbaka till [!DNL Stage Adobe Analytics Reports Suite] sidan.

## Uppdaterar Report Suite-listan {#task_EA6215D438CA4185B106657D9712ED34}

Första gången du får tillgång till Adobe Analytics via användargränssnittet för webbplatssökning/försäljning hämtas och cachelagras en lista över företagets tillgängliga Adobe Analytics-rapportsviter. Om nya rapportsviter nyligen har lagts till, eller om befintliga har tagits bort, kan du använda Uppdatera Report Suite-lista för att uppdatera den lista som visas i webbplatssökningar/-marknadsföring.

Se [Lägga till en Adobe Analytics Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_6DE17305EA7146DA8C30FF8FDF68A3C0).

Se [Ta bort en Adobe Analytics-rapportsserie](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_0ACA172214D14654ABDB139F417B9F7D).

**Så här uppdaterar du Report Suite-listan**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Metrics]**.
1. På [!DNL Adobe Analytics Report Suites] sidan klickar du på **[!UICONTROL Refresh Report Suite List]**.

## Konfigurera avancerade Adobe Analytics-alternativ {#task_C0FF2D69F59D44D8943A7831ED7FEC19}

Du kan använda för [!DNL Advanced Adobe Analytics Options] att styra inställningar som ska hjälpa dig att finjustera beteendet i hämtningsprocessen för Adobe Analytics Report Suite.

Se [Redigera Adobe Analytics-statistik i en Report Suite](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_360904CCBBB140238ADA036C3CC07664).

**Konfigurera avancerade Adobe Analytics-alternativ**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Advanced Options]**.
1. Ange följande alternativ på [!DNL Advanced Adobe Analytics Options] sidan:

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Maximalt antal rader, alla mått </p> </td> 
      <td colname="col2"> <p>En optimeringsinställning som förhindrar nedladdning av för mycket Adobe Analytics-data. </p> <p>Om du anger det här alternativet till ett värde som inte är noll stoppas inhämtningen av Adobe Analytics-data när det totala antalet rader som har hämtats för varje mätvärde överskrider det angivna värdet. </p> <p>Standardvärdet är 0; inget maxvärde används. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Måttupprepande hämtningsstorlek (rader) </p> </td> 
      <td colname="col2"> <p> Styr antalet Adobe Analytics-mätvärden som ska hämtas samtidigt. Måttdataraderna hämtas upprepade gånger tills alla data har hämtats eller tills maxgränsen för rader har nåtts. </p> <p>Normalt behöver du inte ändra den här inställningen. Det kan dock vara praktiskt att optimera nedladdningsfasen för en fullständig indexering av webbplatsen. </p> <p>Standardvärdet är 5000. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Om SAINT-klassificeringsfeeds {#concept_C55609DA24914BBC92CD90ED0259199D}

Ni kan använda Adobe Analytics SAINT för att förbättra era analysrapporter genom att acceptera tabelldata från externa källor. Du kan till exempel använda webbplatssökning/försäljning för att hämta data från egna index och exportera dessa data till Adobe Analytics.

Om du vill kunna använda SAINT-funktionen i Adobe Analytics för webbplatssökningar/-marknadsföring måste du vara medveten om följande krav:

* Du måste ha ett Adobe Analytics-företag och en Report Suite.

   Se [Om Adobe Analytics-menyn](../c-about-settings-menu/c-about-adobe-analytics-menu.md#concept_5FD2D13C9D0D40988E6E51480D690411).
* Adobe Analytics-användarkontot måste ha behörighet att ändra Report Suite.

   Se [Ställa in autentisering](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_8AA93F6273B747F9B4DE9E8DFBCBDC42)med Adobe Analytics-mått.
* Adobe Analytics-användaren måste tillhöra Web API-gruppen så att de kan använda Adobe Analytics Web API.
* Sökindexet måste innehålla data som kan användas i Adobe Analytics, till exempel data i rätt format.

Innan du skapar en feed bör du granska följande frågor och information så att du kan slutföra guiden för SAINT-feed:

* Vilken Report Suite ska du arbeta med?
* Vilken klassificeringsuppsättning, till exempel produkt, e-var osv., ska du ange data för?
* Vilka klassificeringar finns i rapporterna? Svaret på den här frågan avgörs av vilken typ av data som är tillgängliga från webbplatssökning/försäljning och vilken typ av rapporter som Adobe Analytics rapporterar som önskvärda.
* SAINT accepterar data från webbplatssökning/försäljning som en texttyp. Formatet på dessa data påverkar presentationen av Adobe Analytics-rapporterna.

## Skapa en SAINT-feed för Adobe Analytics {#task_914B5AB821E84627953D8EF9339A7DD0}

Ni kan använda Adobe Analytics SAINT för att förbättra Adobe Analytics-rapporter genom att acceptera tabelldata från externa källor.

Du kan till exempel använda webbplatssökning/försäljning för att hämta data från egna index och exportera dessa data till Adobe Analytics.

**Skapa en SAINT-feed för Adobe Analytics**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. På [!DNL SAINT Classification Feeds] sidan klickar du på **[!UICONTROL Create SAINT Feed]**.
1. I [!DNL Create Feed] dialogrutan anger du det nya feed-namnet **i textfältet** Feed och klickar sedan på **[!UICONTROL Next]**.

   Nu sparas feed och läggs till på [!DNL SAINT Classification Feed] sidan. Om du vill kan du avsluta och redigera flödet senare för att slutföra guiden.
1. På [!DNL Authentication] sidan anger du företagsnamnet, användarnamnet och webbhemligheten för Adobe Analytics i respektive textfält och klickar sedan på **[!UICONTROL Next]**.

   Kontrollera att den har behörighet att använda webb-API:t med Adobe Analytics.
1. På **[!UICONTROL Report Suite]** sidan väljer du en rapportserie och dess klassificeringsdatauppsättning och klickar sedan på **[!UICONTROL Next]**.
1. Mappa Adobe Analytics-klassificeringar på [!DNL Field Maps] sidan med metadatafält för webbplatssökning/försäljning och klicka sedan på **[!UICONTROL Next]**.

   Om du vill justera Adobe Analytics-klassificeringar klickar du på **[!UICONTROL Edit]** Adobe Analytics-klassificeringar för att logga in på Adobe Analytics. När du är klar med ändringarna klickar du på **[!UICONTROL Refresh Classifications]** för att uppdatera klassificeringarna.
1. På [!DNL Search Criteria] sidan kan data från webbplatssökning/-marknadsföring filtreras innan de skickas till SAINT för Adobe Analytics. Skapa filterregler här med hjälp av regelbyggargränssnittet och klicka sedan på **[!UICONTROL Next]**.
1. Markera FTP-servern på [!DNL Configure FTP] sidan. Ange hur ofta du vill överföra data och klicka sedan på **[!UICONTROL Next]**.

   Det bästa sättet är att varje feed har ett eget FTP-konto för att undvika oavsiktlig förlust av data. Du kan skapa ett nytt FTP-konto för Adobe Analytics här.
1. Klicka på på [!DNL Verification] sidan **[!UICONTROL Show Data View]** för att granska datavyrepresentationen av utdata. Om det finns några faktiska feed-filer visas de här och är tillgängliga för hämtning.
1. Klicka på **[!UICONTROL Close]**.

## Redigera en SAINT-feed i Adobe Analytics {#task_5BF34D02D0D14359B1CF4B3C1B0ACC84}

Du kan redigera alla aspekter av en befintlig SAINT-feed som du har skapat.

**Redigera en SAINT-feed i Adobe Analytics**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. På [!DNL Saint Classification Feeds] sidan, under **[!UICONTROL Name]** kolumnen, i listrutan bredvid en feed, klickar du på **[!UICONTROL Edit feed]**.
1. I dialogrutan SAINT feed anger du det nya namnet på **feeden i textfältet Feed Name** och klickar sedan på **[!UICONTROL Next]**.

   Nu sparas feed och läggs till på [!DNL SAINT Classification Feed] sidan. Om du vill kan du avsluta och redigera flödet senare för att slutföra guiden.
1. På [!DNL Authentication] sidan anger du företagsnamnet, användarnamnet och webbhemligheten för Adobe Analytics i respektive textfält och klickar sedan på **[!UICONTROL Next]**.

   Kontrollera att den har behörighet att använda webb-API:t med Adobe Analytics.
1. På **[!UICONTROL Report Suite]** sidan väljer du en rapportserie och dess klassificeringsdatauppsättning och klickar sedan på **[!UICONTROL Next]**.
1. Mappa Adobe Analytics-klassificeringar på [!DNL Field Maps] sidan med metadatafält för webbplatssökning/försäljning och klicka sedan på **[!UICONTROL Next]**.

   Om du vill justera Adobe Analytics-klassificeringar klickar du på **[!UICONTROL Edit]** Adobe Analytics-klassificeringar för att logga in på Adobe Analytics. När du är klar med ändringarna klickar du på **[!UICONTROL Refresh Classifications]** för att uppdatera klassificeringarna.
1. På [!DNL Search Criteria] sidan kan data från webbplatssökning/-marknadsföring filtreras innan de skickas till SAINT för Adobe Analytics. Skapa filterregler här med hjälp av regelbyggargränssnittet och klicka sedan på **[!UICONTROL Next]**.
1. Markera FTP-servern på [!DNL Configure FTP] sidan. Ange hur ofta du vill överföra data och klicka sedan på **[!UICONTROL Next]**.

   Det bästa sättet är att varje feed har ett eget FTP-konto för att undvika oavsiktlig förlust av data. Du kan skapa ett nytt FTP-konto för Adobe Analytics här.
1. Klicka på på [!DNL Verification] sidan **[!UICONTROL Show Data View]** för att granska datavyrepresentationen av utdata. Om det finns några faktiska feed-filer visas de här och är tillgängliga för hämtning.
1. Klicka på **[!UICONTROL Close]**.

## Ta bort en SAINT-feed för Adobe Analytics {#task_5319B1F4CA1A406393CFD7AE97258CEB}

Du kan ta bort en befintlig Adobe Analytics SAINT-feed som du inte längre behöver eller använder.

**Så här tar du bort en SAINT-feed i Adobe Analytics**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. På [!DNL Saint Classification Feeds] sidan, under **[!UICONTROL Name]** kolumnen, i listrutan bredvid en feed som du vill ta bort klickar du på **[!UICONTROL Delete feed]**.
1. Klicka på **Ja** i dialogrutan Ta bort för att bekräfta borttagningen av feeden.

## Visa en SAINT-flödesfil för Adobe Analytics {#task_F0C8BADD25E14E5DB30BF31D1F879FDB}

Du kan öppna [!DNL Verification] sidan för en befintlig SAINT-feed för att granska datavyrepresentationen av utdata.

Om det finns några faktiska feed-filer visas de här och kan laddas ned som en textfil.

**Så här visar du en SAINT-feedfil för Adobe Analytics**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. På [!DNL Saint Classification Feeds] sidan, under **[!UICONTROL Name]** kolumnen, i listrutan bredvid en feed, klickar du på **[!UICONTROL View Feed Files]**.
1. (Valfritt) Klicka **[!UICONTROL Download File]** för att spara feed-filen som en textfil.
1. Klicka **[!UICONTROL Close]** för att gå tillbaka till [!DNL SAINT Classification Feeds] sidan.

## Testa en SAINT-feed i Adobe Analytics {#task_9864D69BE3824FC29C10B36EE4855D25}

Du kan testa en befintlig Adobe Analytics SAINT-feed utan någon filöverföring.

Se [Generera och överföra en SAINT-feed](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_47AED946AA964334A877FDC8D4F6F00A)för Adobe Analytics.

Se [Visa en SAINT-flödesfil](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB)för Adobe Analytics.

**Så här testar du en SAINT-feedfil för Adobe Analytics**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. På [!DNL Saint Classification Feeds] sidan, under **[!UICONTROL Name]** kolumnen, i listrutan bredvid en feed, klickar du på **[!UICONTROL Test Feed (No file upload)]**.
1. När feeden har bearbetats klickar du på i den nedrullningsbara listan för feed-namnet **[!UICONTROL View Feed Files]**.
1. Klicka på [!DNL Verification] sidan **[!UICONTROL Download File]** för att hämta feed-filen.
1. Klicka **[!UICONTROL Close]** för att gå tillbaka till [!DNL SAINT Classification Feeds] sidan.

## Generera och överföra en SAINT-feed för Adobe Analytics {#task_47AED946AA964334A877FDC8D4F6F00A}

Du kan generera och överföra feed-filer för en befintlig Adobe Analytics-feed som du har skapat.

Se [Testa en SAINT-feed](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_9864D69BE3824FC29C10B36EE4855D25)i Adobe Analytics.

Se [Visa en SAINT-flödesfil](../c-about-settings-menu/c-about-adobe-analytics-menu.md#task_F0C8BADD25E14E5DB30BF31D1F879FDB)för Adobe Analytics.

**Generera och ladda upp en SAINT-feedfil för Adobe Analytics**

1. På produktmenyn klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Adobe Analytics]** > **[!UICONTROL SAINT Classification Feeds]**.
1. På [!DNL Saint Classification Feeds] sidan, under **[!UICONTROL Name]** kolumnen, i listrutan bredvid en feed, klickar du på **[!UICONTROL Generate and Upload Feed]**.
1. När feeden har bearbetats klickar du på i den nedrullningsbara listan för feed-namnet **[!UICONTROL View Feed Files]**.
1. Klicka på [!DNL Verification] sidan **[!UICONTROL Download File]** för att hämta feed-filen.
1. Klicka **[!UICONTROL Close]** för att gå tillbaka till [!DNL SAINT Classification Feeds] sidan.
