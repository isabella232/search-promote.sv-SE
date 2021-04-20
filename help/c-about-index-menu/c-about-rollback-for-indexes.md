---
description: Du kan använda Återställning för att säkerhetskopiera och arkivera webbplatsindex som du har skapat. Du kan också när som helst återställa säkerhetskopian av ett index.
solution: Target
subtopic: Rollback
title: Om återställning för index
topic: Index,Site search and merchandising
uuid: abed878a-71b3-4122-9822-7410f4427a9a
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 0%

---


# Om återställning för index{#about-rollback-for-indexes}

Du kan använda [!DNL Rollback] för att säkerhetskopiera och arkivera webbplatsindex som du har skapat. Du kan också när som helst återställa säkerhetskopian av ett index.

## Använda återställning för index {#concept_0BC4BC975DB045A986C3607CF32705D8}

Arkivet innehåller fyra index: det aktuella webbplatsindexet och tre tidigare webbplatsindex som sökroboten automatiskt arkiverar baserat på inställningarna för återställningskonfigurationen. Varje gång webbplatsen indexeras uppdateras arkivet. Nya index ersätter befintliga arkiverade index så att arkivet alltid är aktuellt.

Varje arkiverat index visas i arkivet med följande information:

* Datum och tid när indexet slutfördes.
* Indexera ålder.
* Antal indexerade dokument.
* Typ av indexeringsåtgärd (full, inkrementell och så vidare).
* Indexstatus, t.ex. om indexet är aktivt och om det ska behållas eller tas bort efter nästa index.

Varje gång webbplatsen indexeras läggs det nya indexet till i arkivet och ett befintligt arkiverat index tas bort. Observera dock att det äldsta indexet inte nödvändigtvis är det som tas bort. När ett nytt index läggs till i arkivet görs en åldersjämförelse av varje arkiverat index till de sidor som anges i inställningarna för återställningskonfigurationen. Det index som ligger längst bort från det önskade schemat tas bort. Anta till exempel att konfigurationsinställningen är 24,48,72 och att de sparade indexens ålder är 5, 23, 47 och 71. Det senaste indexet (som är fem timmar gammalt) tas bort när ett nytt index läggs till i arkivet eftersom dess ålder är längst från inställningarna. För enkelhetens skull bör du anteckna vilket index som ska tas bort när webbplatsen indexeras igen.

Du kan navigera till andra områden i användargränssnittet när ett index aktiveras. En statusindikator håller reda på aktiveringsförloppet och är tillgänglig när du visar sidan [!DNL Rollback]. Om ett arkiverat index återställs meddelas användarna högst upp på sidorna Fullständigt index, Inkrementellt index, Skriptade index och Återskapa. Ingen indexeringsåtgärd kan utföras medan ett index återställs. Om en återställningsåtgärd hamnar i konflikt med ett schemalagt platsindex, skjuts den schemalagda indexeringen upp tills återställningen är klar. Om ett index redan pågår avbryts det, förutsatt att användaren bekräftar att återställningen får prioritet.

För att bevara arkivets integritet uppdaterar sökroboten inte återställningsarkivet om fel påträffas under en crawl. Det finns heller ingen uppdatering om en användare avbryter en indexeringsåtgärd. Om en indexeringsåtgärd överskrider maxtiden, antalet byte, sidor eller dokument, slutförs indexet av crawlningsprogrammet och läggs till i arkivet. Om det minsta antalet sidor inte uppfylls under en indexeringsåtgärd avbryts indexet och det föregående indexet förblir aktivt.

## Konfigurera arkiveringsschemat för återställning av index {#task_CD403B9AE2244B13A6B3861B5F9B055C}

Du kan använda [!DNL Configure] för att avgöra vilka indexfiler du vill lagra i återställningsarkivet. Arkivet kan lagra aktuellt index och tre säkerhetskopieringsindex.

Fältet **[!UICONTROL Schedule]** innehåller tre kommaseparerade värden som representerar timmar från det aktuella. Schemavärdena 24,48,72 anger till exempel 24 timmar från dagens eller gårdagens datum, 48 timmar från nuvarande eller två dagar sedan och 72 timmar från nuvarande eller tre dagar sedan.

Vid sökning arkiveras webbplatsindexen som är närmast en dag, två dagar och tre dagar gamla. De faktiska tiderna och datumen i de arkiverade indexen kan variera beroende på webbplatsens indexeringsschema.

**Så här konfigurerar du arkiveringsschemat för återställning av index**

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Configure]** på produktmenyn.
1. På sidan [!DNL Rollback Configuration] anger du i fältet **[!UICONTROL Schedule]** en kommandoavgränsad lista med tre indexsidor i timmar. De index som ligger närmast dessa sidor sparas.
1. Klicka på **[!UICONTROL Save Changes]**.

## Aktivera ett arkiverat index {#task_5DCE3D660F6F4197993E92AA59227332}

Du kan använda Återställning för att aktivera ett arkiverat index.

När du klickar på **[!UICONTROL Activate]** för att återställa ett index, flyttas det aktiva indexet till arkivet.

När det arkiverade indexet har aktiverats återgår du till sidan [!DNL Activate Index]. Information om återställning av index visas. Dessutom identifierar kolumnen [!DNL Activate] i tabellen [!DNL Available Indexes] det återställda indexet med statusen &quot;Aktivt index&quot;.

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Rollback]** > **[!UICONTROL Rollback]** på produktmenyn.
1. På sidan [!DNL Activate Index] i tabellen [!DNL Available Indexes] klickar du på **[!UICONTROL Activate]** för den associerade arkiverade indextypen som du vill göra aktiv.

   Använd kolumnerna Datum, Ålder, Sidor och Åtgärd för att avgöra vilket index som ska aktiveras.
1. Granska indexinformationen på sidan [!DNL Verify Rollback] för att bekräfta att du har valt rätt index och klicka sedan på **[!UICONTROL Activate Now]**.

## Visa loggen för alla indexåterställningar {#task_D2D9AA7203F0465FB5AE0D49212AC41C}

Visa datum och tid för alla återställningsrelaterade åtgärder.

**Visa loggen för alla indexåterställningar**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Live Log]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Re-Rank Index]** > **[!UICONTROL Staged Log]**.

1. Gör något av följande på loggsidan, längst upp eller längst ned:

   * Använd navigeringsalternativen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** eller **[!UICONTROL Go to line]** för att gå igenom loggen.

   * Använd visningsalternativen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** eller **[!UICONTROL Show]** för att förfina det du ser.

