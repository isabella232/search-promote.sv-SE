---
description: Du kan använda Återskapa index för att uppdatera webbplatsens index utan att behöva crawla webbplatsen på nytt.
seo-description: Du kan använda Återskapa index för att uppdatera webbplatsens index utan att behöva crawla webbplatsen på nytt.
seo-title: Om Återskapa index
solution: Target
subtopic: Regenerate Index
title: Om Återskapa index
topic: Index,Site search and merchandising
uuid: 9d1f1d88-0453-4422-a625-a348febbf224
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 0%

---


# Om Återskapa index{#about-regenerate-index}

Du kan använda [!DNL Regenerate Index] för att uppdatera webbplatsens index utan att du behöver crawla om webbplatsen.

## Använda Återskapa index {#concept_6CBE6B8D18EF47D293091CBA542245FA}

Du kan använda det här alternativet när du ändrar följande kontoalternativ:

* Ord och språk
* Exkluderade ord
* Synonymer
* Metadatainställningar som när du tar bort ett metadatafält, ändrar ett fältnamn, datatyp, datumformat, sorteringsordning, lägsta eller högsta rankningsvärde, standardrankningsvärde, listtyp eller listavgränsare.

Den uppdaterade kontoalternativinformationen används för att generera ett nytt platsindex. Med Återskapa kan du snabbt och effektivt ändra webbplatsindexet.

Som standard tas inte allt nytt eller ändrat webbplatsinnehåll med i indexet. Om du vill ta med sådant innehåll kör du ett fullständigt eller inkrementellt index.

Se även [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Se även [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Återskapa indexet för en aktiv eller mellanlagrad webbplats {#task_B28DE40C0E9A475ABCBCBC4FF993AACD}

Du kan använda [!DNL Regenerate Index] för att uppdatera webbplatsens index utan att behöva rita om webbplatsen.

**Så här genererar du om indexet för en publicerad eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Regenerate Index]** > **[!UICONTROL Live Regenerate]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Regenerate Index]** > **[!UICONTROL Staged Regenerate]**.

1. Klicka på **[!UICONTROL Regenerate Index Now]** på sidan [!DNL Regenerate].
1. (Valfritt) Gör något av följande:

   * Om du väljer att köra **[!UICONTROL Live Regenerate]** klickar du på **[!UICONTROL View Last Crawl]** för att granska prestandastatistik för den senaste omgenereringen av index som utfördes.

   * När indexet genereras om klickar du på **[!UICONTROL Stop Regenerate Now]** för att stoppa omgenereringsprocessen.
   * När indexet återskapas klickar du på **[!UICONTROL Restart Regenerate Now]** för att starta om indexåterskapningsprocessen från början.
   * Om indexeringsfel uppstår efter en mellanlagrad omgenerering klickar du på **[!UICONTROL View Errors]** för att visa den associerade loggen.

## Visa den återskapade indexloggen för en aktiv eller mellanlagrad webbplats {#task_61CE8F9E7BF84BA89A8D482B2106BB15}

När en omgenerering av ett index i realtid eller en omgenerering av ett mellanlagrat index är slutförd kan du visa tillhörande logg för att felsöka eventuella fel som inträffat.

Du kan inte exportera loggar eller spara dem. Loggen är dock fortfarande tillgänglig för visning tills det nya indexet inträffar.

**Så här visar du den återskapade indexloggen för en aktiv eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Regenerate Index]** > **[!UICONTROL Live Log]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Regenerate Index]** > **[!UICONTROL Staged Log]**.

1. Gör något av följande på loggsidan, längst upp eller längst ned:

   * Använd navigeringsalternativen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** eller **[!UICONTROL Go to line]** för att gå igenom loggen.

   * Använd visningsalternativen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** eller **[!UICONTROL Show]** för att förfina det du ser.

