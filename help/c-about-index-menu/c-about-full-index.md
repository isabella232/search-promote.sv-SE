---
description: Du kan använda Fullständigt index om du vill indexera alla sidor på den testade eller publicerade webbplatsen. Med indexering blir det enklare för kunderna att hitta det de söker efter eller vad de behöver när de gör en sökning.
solution: Target
subtopic: Full Index
title: Om Fullständigt index
topic: Index,Webbplatssökning och -försäljning
uuid: dce1eafd-5aea-4945-8305-8f9e7dc392df
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%

---


# Om Fullständigt index{#about-full-index}

Du kan använda Fullständigt index om du vill indexera alla sidor på den testade eller publicerade webbplatsen. Med indexering blir det enklare för kunderna att hitta det de söker efter eller vad de behöver när de gör en sökning.

## Använda fullständigt index {#concept_C69BD21863FD4856B49326F35DB570D3}

När du genererar ett fullständigt index visas statusinformation, till exempel starttid, förfluten tid och fel under indexeringsprocessen. Information om status för det senaste indexet visas också.

Om du har ändrat en kontoinställning som kräver en omgenerering av index kan statusen vara &quot;Återskapa&quot;. Under omgenereringen används kontoinställningarna för att skapa ett uppdaterat platsindex.

Du kan när som helst stoppa eller starta om indexeringsprocessen.

När det nya indexet har skapats för en aktiv webbplats kan kunderna fortsätta att söka på webbplatsen med det senaste indexvärdet. Information om status för det senaste indexet visas också.

## Ställa in fullständigt indexschema för en aktiv webbplats {#task_6760F3256D004A228B38968DF15421F0}

Du kan ange när och vilka dagar du vill crawla webbplatsen och uppdatera indexet.

Den tid du väljer är lokal enligt den tidszon som är konfigurerad i Kontoinställningar.

Se [Konfigurera dina kontoinställningar](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

Webbservrar är ofta schemalagda för underhåll mitt i natten. Om servern är nere under en schemalagd indextid kommer indexeringsprocessen att misslyckas. Se till att du väljer en tidpunkt på dagen när webbservern är tillgänglig.

Indexschemat gäller endast ditt liveindex. du kan inte schemalägga mellanlagrade index.

**Ställa in ett fullständigt indexschema för en aktiv webbplats**

1. Klicka på **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Schedule]** på produktmenyn.
1. I listrutan **[!UICONTROL Time]** väljer du den timme då du vill att den fullständiga indexeringen ska börja.
1. Markera en eller flera dagar som du vill att den fullständiga indexeringen ska köras.
1. Klicka på **[!UICONTROL Save Changes]**.

## Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats {#task_F7FE04D8A1654A7787FCCA31B45EB42D}

Du kan använda Fullständigt index om du vill indexera alla sidor på den testade eller publicerade webbplatsen. Med indexering blir det enklare för kunderna att hitta det de söker efter eller vad de behöver när de gör en sökning.

**Så här kör du ett fullständigt index för en aktiv eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Index]**.

1. Ange de indexeringsalternativ som du vill ha.

   <table> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
    <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Rensa indexcache </p> </td> 
    <td colname="col2"> <p>Tar bort alla dokument från indexcachen. </p> <p>När du väljer det här alternativet hämtas alla webbplatssidor från servern. Om den här inställningen är markerad och inaktiverad är ditt konto inställt på att rensa cachen varje gång ett fullständigt index utförs. Eller så krävs ett fullständigt index för vissa kontoinställningar som har ändrats tidigare. </p> <p>När du avmarkerar det här alternativet behålls alla indexerade sidor i indexet tills webbservern säger att sidan inte längre finns. Detta gäller även om länkar till den sidan tas bort. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Återskapa väntande </p> </td> 
    <td colname="col2"> <p>Markera Om du har gjort ändringar i kontoinställningarna som har ändrat innehållet i indexet avsevärt. Exempel på viktiga ändringar är att göra ändringar i något av följande: 
    <ul id="ul_4EB8FF692FEB47BBB9A64D61299380D1"> 
    <li id="li_7CF8D286512F4210BEA3DB9F0EFA097A">Synonymer </li> 
    <li id="li_8178ABC342BB4365B3927E20433756E3">Samlingar </li> 
    <li id="li_57C8BD06BFA64AFAA2C9EF2CC59520EF">Metadata </li> 
    <li id="li_C4B6A7DA023B4A43991D03EC592170C9">Uteslutna ord </li> 
    <li id="li_9E0AD4B6DDC24A5A8FB5C2C1CCD5348A">Kontospråk </li> 
    <li id="li_338F107547DF48AAA0EF90F4AD8664A5">Rankning </li> 
    <li id="li_7F49B86D94974E79AAD381A64A1400F2">Växla mellan skiftlägeskänslig sökning </li> 
    <li id="li_E8FE6EE240A840AC826ADF4294AAC6F6">Växla diakritiskt stöd </li> 
    <li id="li_51763D482DCB4ED0972966F492B8C0F2">Växlar nummerindexering </li> 
    </ul> </p> <p>Innan en ny crawlning tar plats sker en snabb genomgång av alla indexdata så att de överensstämmer med de nya kontoinställningarna. </p> <p>Det här alternativet är bara tillgängligt om du gör ett fullständigt index för en mellanlagrad webbplats. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Räkna alla sidor </p> </td> 
    <td colname="col2"> <p>Tillåter crawlning av webbplatssidor att fortsätta även efter att du har nått gränsen för din kontosida. </p> <p>Ytterligare sidor läggs inte till i indexet, men du kan kontrollera det totala antalet dokument på webbplatsen. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Full Index Now]**.
1. (Valfritt) Om indexeringsfel inträffar klickar du på **[!UICONTROL View Errors]** för att visa den associerade loggen.

## Visa den fullständiga indexloggen för en aktiv eller mellanlagrad webbplats {#task_02E5E944C56B4EB19CC1FF321F3221B8}

När ett fullständigt index eller ett mellanlagrat fullständigt index är klart kan du visa tillhörande logg för att felsöka eventuella fel som inträffat.

Du kan inte exportera loggar eller spara dem. Loggen är fortfarande tillgänglig för visning tills det nya indexet inträffar.

**Så här visar du den fullständiga indexloggen för en aktiv eller mellanlagrad webbplats**

1. Gör något av följande på produktmenyn:

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Log]**.

   * Klicka på **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Staged Log]**.

1. Gör något av följande på loggsidan, längst upp eller längst ned:

   * Använd navigeringsalternativen **[!UICONTROL First]**, **[!UICONTROL Prev]**, **[!UICONTROL Next]**, **[!UICONTROL Last]** eller **[!UICONTROL Go to line]** för att gå igenom loggen.

   * Använd visningsalternativen **[!UICONTROL Errors only]**, **[!UICONTROL Wrap line]** eller **[!UICONTROL Show]** för att förfina det du ser.

