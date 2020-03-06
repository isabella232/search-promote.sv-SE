---
description: Använd Facet Rail för att ordna om grupper av ansikten på en webbsida.
seo-description: Använd Facet Rail för att ordna om grupper av ansikten på en webbsida.
seo-title: Om Fasett Rail
solution: Target
subtopic: Navigation
title: Om Fasett Rail
topic: Design,Site search and merchandising
uuid: 6da2bd67-8c20-4955-9836-bc8ba88546c5
translation-type: tm+mt
source-git-commit: 6b3aa733b0dfaace956f0ffc25f433fefd21e15f

---


# Om Fasett Rail{#about-facet-rail}

Använd Facet Rail för att ordna om grupper av ansikten på en webbsida.

## Använda Fasett Rail {#concept_1FDC8BCDFFC84A0889DA670F63D5F6DB}

En aspekt är en egenskap eller en egenskap. Det är ett sätt att generellt kategorisera sökresultaten. Till exempel kan tillverkare, pris och färg betraktas som en grupp av faktorer. Varje aspekt kan ha flera begränsningar eller värden. Om du t.ex. har en färg som en fasett kan &quot;fasettvärdena&quot; vara rött, orange, gult, grönt, blått, indigo och violett.

Se [Om ansikten](../c-about-design-menu/c-about-facets.md#concept_FA912B3B41EE493DB2F492D188457FF5).

Du använder Facet Rail för att ändra ordning på de här grupperna på en webbsida. Anta till exempel att du har ett avsnitt med sökresultat på vänster sida av en webbsida. Avsnittet ovan, uppifrån och ned, en kategorifaktor, en varumärkestroch, en prisfaktor och en Most Popular-aspekt. Om du använder en fasetterad räl kan du t.ex. ha den mest populära aspekten ovanför eller under kategoriaspekten.

Den grupp av ansikten som du vill ändra ordning på tillsammans tillhör en facet rail-tagg. En fasett kan bara tillhöra en facet rail. Fasettspåret är en presentationsmall-tagg och omger en enda representation av en fasett. Alla aspekter som hör till den här rälen delar samma ansiktsrepresentation.

Se [Mallar](../c-about-design-menu/c-about-templates.md#concept_06EB481B14864E18A8AE2BCD1D6EF0B5) och Fasett i [Presentationsmallstaggar](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

## Konfigurera en begränsningsram {#task_561A8FF1CAD1402B9DD33E276BBC6A0E}

Du kan lägga till en begränsningsram för att anpassa presentationslagret. Fasettspår ger dina kunder en guidad sökning där de kan fördjupa sig i sökresultaten baserat på den ordning som ansiktena på webbsidan har.

<!-- 

t_configuring_facet_rail.xml

-->

Alla ändringar du gör i ansiktsskenor kan ångras med hjälp av funktionen Historik.

**Konfigurera en begränsningsram**

1. Innan du kan konfigurera en begränsningsram måste du kontrollera att du redan har lagt till en fasett och, som en del av den uppgiften, ange ett namn på begränsningsramen.

   Se [Lägga till en ny aspekt](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B).
1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Facet Rail.]**
1. På [!DNL Facet Rail] sidan markerar du de aspekter som du vill ta med i ansiktslisten och anger sedan **[!UICONTROL Sort Facets Method]** alternativet i listrutan.

   <!-- 
   r_facet_rail_options.xml
   -->

   | Funktion/Alternativ | Beskrivning |
   |--- |--- |
   | Ansiktets spårnamn | Identifierar namnet på faktafältet.  Du skapar namnet på ansiktsrälen när du lägger till ansiktet.  Se [Lägga till en ny aspekt](../c-about-design-menu/c-about-facets.md#task_FC07BFFA62CA4B718D6CBF4F2855C89B) |
   | Inkluderade ansikten | En lista över möjliga aspekter som du kan välja att lägga till i ansiktsskenan.  Om du väljer att sortera ansikten med `Custom`bestämmer den ordning som du väljer ansiktena här ordningen i vilken de visas i `Custom Facet Order` textrutan. |
   | Sorteringsmetod | Välj något av följande tre alternativ i listrutan:<ul><li>`Alpha` Fetterna sorteras i alfabetisk ordning efter namn, inklusive skiljetecken.</li><li>`Alpha (not case sensitive)` Fetterna sorteras i alfabetisk ordning efter namn, utan hänsyn till skiftläget för alfabetiska tecken och med skiljetecken. </li><li>`Alpha (alphanumeric only)` Fetterna sorteras i alfabetisk ordning efter namn, och skiljetecken ignoreras. </li><li>`Alpha (not case sensitive, alphanumeric only)` Fetterna sorteras i alfabetisk ordning efter namn, skiftläge för alfabetiska tecken ignoreras och skiljetecken ignoreras. </li><li>`Count` Fetterna sorteras baserat på antal. </li><li>`Custom` Öppnar textrutan där du kan definiera ansiktsordningens ordning genom att ange det exakta namnet på varje aspekt. `Custom Facet Order` Alla fasettetiketter som utelämnas tas bort från `Custom Facet Order` listan.</li></ul> |
   | Egen begränsningsordning | Det här alternativet är bara tillgängligt om du har valt `Custom` i `Sort Facets Method` listrutan.  Gör att du kan lista ansiktsnamn, antingen en per rad eller alla på en rad och kommaavgränsade. Om fasettetiketter definieras visas de i `Facets Included` listan inom parentes.  Inkludera inte fasettetiketter i `Custom Facet Order` textrutan.  När du markerar eller avmarkerar ansikten i `Facets Included` listan uppdateras `Custom Facet Order` textrutan automatiskt. |

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande på [!DNL Facet Rail] sidan:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

1. Redigera presentationsmallen genom att göra följande:

   * Skapa en facet-mall i presentationsmallen.
   * Omge&quot;faktamallen&quot; med `<guided-facet-rail>` -taggarna.

      Se Ansikten i [Presentationsmallstaggar](../c-appendices/c-templates.md#reference_F1BBF616BCEC4AD7B2548ECD3CA74C64).

      Exempel:

      ```
      <guided-facet-rail>
        <guided-facet>
          <guided-facet-display-name/>
          ...
          </guided-facet>
        </guided-facet-rail>
      ```

      Dessa taggar genererar ett avsnitt i presentationsmallen som blir ett repeterbart mönster för varje aspekt i ansiktsskenan. Varje aspekt som tillhör ansiktsrälen använder det här ursparade avsnittet för att utvärdera utdata. Endast en `<guided-facet-rail>` tagg kan visas i den slutliga presentationsmallen.

      Följande taggar behöver inte attributet `gsname` inuti `<guided-facet-rail>` eftersom värdet bestäms dynamiskt vid sökningen och ersätts korrekt:

      `<guided-facet>`
      `<guided-facet-display-name>`
      `<guided-facet-total-count>`
      `<guided-facet-undo-link>`
      `<guided-facet-undo-path>`
      `<guided-facet-behavior>`

   * Spara presentationsmallen och gör den offentlig.

      Se [Redigera en presentation eller en transportmall](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).
