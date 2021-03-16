---
description: Du kan använda Uteslutna ord för att ange fraser som du använder ofta och vanliga ord, t.ex. "a" och "the", som du vill utesluta från sökresultatet.
solution: Target
title: Om uteslutna ord
topic: Linguistics, Site search and merchandising
uuid: 1c879462-1b19-44f6-a3b2-20aa786b3221
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---


# Om uteslutna ord{#about-excluded-words}

Du kan använda Uteslutna ord för att ange fraser som du använder ofta och vanliga ord, t.ex. &quot;a&quot; och &quot;the&quot;, som du vill utesluta från sökresultatet.

## Använder uteslutna ord {#concept_9DB67BD2F0DC43AC88741003D9F39812}

Se även [Om sökningar](../c-about-settings-menu/c-about-searching-menu.md#concept_207105CF26B1448F8A3D223787C56AB8).

Om du inte använder uteslutna ord kan sökningar som innehåller dessa ord identifiera ett flertal irrelevanta resultat. När du exkluderar ord och fraser utelämnas sökresultat som endast matchar de uteslutna termer som du har angett. Om en sökfråga innehåller ett utelämnat ord används endast de icke-uteslutna orden för att hitta dokument.

Exkluderade sökord markeras inte i sökresultatet. Relevanspoängen för varje resultat påverkas dock av de uteslutna orden. Med andra ord ignoreras uteslutna ord när du söker efter dokument, men de används fortfarande när du rankar dokumenten på sökresultatsidan. Innan effekterna av inställningarna för Uteslutna ord (eller ändringarna av dessa inställningar) är tillgängliga för kunderna måste du generera om webbplatsindexet.

När du anger ord som ska uteslutas från sökresultatet avgränsar du ord eller fraser från varandra med kommatecken. Du kan ange ett eller flera uteslutningsord per rad. Följande är ett exempel på uteslutna ord på separata rader och dividerade med kommatecken.

![](assets/excluded_words_1.jpg)

Om din kund söker efter&quot;USA:s USA&quot; i exempellistan med uteslutna ord ovan utesluts ordet&quot;USA&quot; och ordet&quot;av&quot; från sökningen. Sökningen hittar i stället alla sidor som innehåller orden&quot;Förenade&quot;,&quot;lägen&quot; och&quot;amerika&quot;. Sidor som bara innehåller ordet &quot;av&quot; eller &quot;på&quot; visas inte.

Vissa webbplatser innehåller specifika fraser på de flesta, eller alla, sidor. En webbplats om turism i New York City kan till exempel innehålla orden New York i titeln på varje sida. Överväg att lägga till den här frasen, och andra gilla den, i exkluderingslistan:

![](assets/excluded_words_2.jpg)

När en fras utesluts används de enskilda orden som utgör den fortfarande som söktermer. Det är bara när en besökare söker efter de exakta orden, i den exakta ordningen för en utesluten fras, som frasen utesluts från sökresultatet. I exemplet ovan anges att om en kund sökte efter den&quot;nya arbetsbaletten&quot; så utesluts ordet&quot;den&quot; och frasen&quot;ny arbetsplats&quot;. endast sidor som innehåller ordet &quot;ballett&quot; returneras som sökresultat. Om du däremot söker efter&quot;nya byggnader&quot; eller&quot;anka&quot; hittar du fortfarande sidor som innehåller ordet&quot;ny&quot; respektive&quot;ork&quot;.

## Konfigurerar uteslutna ord {#task_60BF6BB7A66C48479D2BBB32C0F38CDE}

Du kan utesluta fraser som du använder ofta och vanliga ord från sökresultatet.

Du kan ange ett eller flera ord per rad. Avgränsa varje ord med kommatecken som i följande exempel:

![](assets/excluded_words_1.jpg)

Du kan välja att visa sökresultat när alla ord i kundens sökning är uteslutna. Om du t.ex. har uteslutit ordet&quot;och en kund väljer att bara söka efter&quot;den&quot;, visas alla sidor som innehåller ordet&quot;den&quot; i sökresultatet. Detta resultat är sant även om ordet&quot;the&quot; är exkluderat. Om du inte markerar det här alternativet får kunden inga sökresultat. Den här inställningen har ingen effekt om sökningen innehåller minst ett icke-exkluderat ord.

**Konfigurera uteslutna ord**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Excluded Words]** på produktmenyn.
1. På sidan [!DNL Excluded Words] anger du de ord du vill utesluta från sökresultatet i textfältet **[!UICONTROL Words and Phrases]**.
1. (Valfritt) Klicka på **[!UICONTROL Show results when all words in the query are excluded words]**.

   När alla ord i kundens sökning är uteslutna, används alla ord tillsammans för att utföra sökningen.
1. Klicka på **[!UICONTROL Save Changes]**.
1. Om du vill förhandsgranska resultatet av ändringarna klickar du på **[!UICONTROL regenerate your staged site index]** för att återskapa indexet för den mellanlagrade webbplatsen.

   Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

   Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).
1. (Valfritt) Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Excluded Words]** på produktmenyn och gör sedan något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

