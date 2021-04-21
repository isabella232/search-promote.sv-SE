---
description: Du kan åsidosätta utökningen av sökfrågeresultat.
solution: Target
title: Om åsidosättningar av frågetillägg
topic-legacy: Linguistics,Site search and merchandising
uuid: dfe18004-b8fd-4889-b01c-72a3b0c82b9c
exl-id: 6157ffcb-e696-419a-acb5-2076c12a6763
translation-type: tm+mt
source-git-commit: 7559f5f7437d46e3510d4659772308666425ec96
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 0%

---

# Om åsidosättningar av frågetillägg{#about-query-expansion-overrides}

Du kan åsidosätta utökningen av sökfrågeresultat.

## Använda frågeexpansion åsidosätter {#concept_6895B469B0E044299E93361BFA06B554}

När du konfigurerar åsidosättning av frågeexpansion skapar du en uppsättning regler. Varje regel säger i princip&quot;Utöka inte `<this>` till `<that>` vid sökningen&quot; där `<this>` är ett enkelt textord eller en enkel fras och `<that>` är ett textord eller en fras eller en klassificering.

>[!NOTE]
>
>Den här funktionen är inte aktiverad i Search &amp; Promote som standard. Kontakta teknisk support för att aktivera funktionen. När funktionen Åsidosätta frågeexpansion är aktiverad måste du aktivera den i användargränssnittet.

**Så här fungerar Åsidosättning av frågeutökning**

När ett text- och termvärde anges på sidan Lägg till åsidosätts av frågetillägget, fungerar koden på den specifika parningen. När en klassificeringstyp anges som en term, t.ex. ordlistor eller alternativa ord-Forms, konverteras inte värdet Expandera till något formulär som skapas av den angivna klassificeringen.

Anta till exempel att du har följande definition:

`Do Not Expand = "dog"`

`Type = Text`

`Term = "dogs"`

En sökfråga efter &quot;hund&quot;, som utökas till att inkludera &quot;hund&quot; och &quot;hund&quot; via Alternate Word Forms, inkluderar inte &quot;hund&quot;.

Om definitionen var följande:

`Do Not Expand = "dog"`

`Type = Alternate Word Forms`

Frågan innehåller inte &quot;hund&quot; eller &quot;hund&quot; (det tillgängliga alternativa Word Forms för &quot;hund&quot;).

Du kan ange flera termer, flera klassificeringar eller båda. Om du väljer Alla som Typ komprimeras alla listor med flera termer till endast en enda Alla-post.

Om text- och klassificeringsposter är blandade i en regel ordnas de om i användargränssnittet så att textvärden visas först. Detta innebär dock inte eller påverkar inte utvärderingsordningen vid tidpunkten för sökningen.

Texttermer valideras för att ta bort meningslösa referenser. Det innebär att termen jämförs med värdet Expandera inte och termen tas bort om det finns en matchning. Dessutom tas dubbletter av termvärden, antingen text eller klassificering, bort.

Om du lägger till en ny regel med värdet Utvidga inte som replikerar en tidigare definition, läggs den nya definitionens villkor till i originalet.

## Konfigurerar åsidosättningar av frågeexpansion {#task_A087354A509D4997BA275186C224160E}

Definiera och lägga till åsidosättning av frågeexpansion i Search &amp; Promote.

<!-- 

t_configuring_query_expansion_overrides.xml

 -->

>[!NOTE]
Den här funktionen är inte aktiverad i Search &amp; Promote som standard. Kontakta teknisk support för att aktivera funktionen. När funktionen Åsidosätta frågeexpansion är aktiverad måste du aktivera den i användargränssnittet. De första stegen nedan visar hur du gör det.

**Så här konfigurerar du åsidosättningar av frågetillägg**

1. Klicka på **Inställningar** > **Användare** > **Visa roller** i Search &amp; Promote.
1. På sidan Visa roller i kolumnen Åtgärder i tabellen klickar du på **Redigera** till höger om rollen som du vill ge åtkomst till Åsidosättningar av frågeexpansion på menyn Språk.
1. Expandera språkträdet på sidan Redigera roll.
1. Markera **Åsidosättningar av frågetillägg** och klicka sedan på **Spara ändringar**.
1. Klicka på **Linguistics** > **Query Expansion Overrides**.
1. Klicka på **Lägg till åsidosättning av frågeexpansion**.
1. Ange önskade alternativ på sidan Lägg till i frågeexpansion.

   <!-- 
   
   r_query_expansion_override_definitions.xml
   
   -->

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Expandera inte </p> </td> 
      <td colname="col2"> <p>Anger det ord eller den fras som du inte vill expandera. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Typ </p> </td> 
      <td colname="col2"> <p>Välj <b>Text</b> om du vill ange ett specifikt ord eller en fraspar. Du kan också välja en klassificering för att ange att ordet eller frasen Expandera inte inte konverteras med den valda klassificeringen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Villkor </p> </td> 
      <td colname="col2"> <p>Endast tillgängligt om du har valt <b>Text</b> som Typ. Anger det ord eller den fras som ska uteslutas vid sökningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Åtgärd </p> </td> 
      <td colname="col2"> <p> Klicka på <b>+</b> eller <b>-</b> för att lägga till respektive ta bort termer i definitionen. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. När du är klar klickar du på **Lägg till**.

   På sidan Frågetillägg åsidosätter definitioner kan du redigera eller ta bort definitioner som du har lagt till.
1. Om du vill förhandsgranska resultatet av dina tillägg klickar du på **återskapa indexet för den mellanlagrade platsen** i den blå rutan för att snabbt återskapa indexet för den mellanlagrade webbplatsen.
1. (Valfritt) Gör något av följande:

   * Klicka på **Live**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F)

   * Klicka på **Push Live**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4)
