---
description: Du kan definiera vanliga fraser som används på webbplatsen så att när en kund skriver in en sökfråga behöver han/hon inte skriva citattecken runt någon av de fraser som du har definierat.
seo-description: Du kan definiera vanliga fraser som används på webbplatsen så att när en kund skriver in en sökfråga behöver han/hon inte skriva citattecken runt någon av de fraser som du har definierat.
seo-title: Om vanliga fraser
solution: Target
title: Om vanliga fraser
topic: Linguistics,Site search and merchandising
uuid: 0f980a22-d826-4476-97de-0e9c14549bc8
translation-type: tm+mt
source-git-commit: 8efa90ac2927b263b7d48ccbf25d4b0e917dac79

---


# Om vanliga fraser{#about-common-phrases}

Du kan definiera vanliga fraser som används på webbplatsen så att när en kund skriver in en sökfråga behöver han/hon inte skriva citattecken runt någon av de fraser som du har definierat.

## Använda vanliga fraser {#concept_4946E53586DF492EAEB1B7F757FD440F}

>[!NOTE]
>
>Funktionen för gemensam fras visas inte i användargränssnittet eftersom den inte är aktiverad som standard. Kontakta teknisk support för att aktivera den här funktionen.

Vanliga fraser är en samling fraser med flera ord som känns igen under kundens sökning. Den behandlar fraserna som en kombinerad ordgrupp i stället för som enskilda ord. När en kund skriver in en sökfråga på din webbplats kan han eller hon identifiera fraser genom att omge termerna med dubbla citattecken, t.ex.&quot;Stillahavsområdet&quot;. När du lägger till grupper med vanliga fraser utförs offertstegen automatiskt för kunden när matchande fraser hittas i sökfrågan.

Anta till exempel att en kund på webbplatsen skriver in följande sökfråga:

`hotels near the pacific ocean`

Utan citattecken `pacific ocean`returnerar kundens sökning resultat för hotell i närheten av havet i världen, vilket inte är vad kunden avsåg.

När du lägger till den vanliga frasen&quot;Stillahavsområdet&quot; konverteras sökfrågan automatiskt till följande:

`hotels near the "pacific ocean"`

Användningen av Vanliga fraser förhindrar inte att kunderna uttryckligen använder citattecken runt fraser i ord, utan lägger i stället till citattecken när dessa fraser hittas i sökfrågan.

Den här sökfrågan omfattar CGI-parametrar `sp_q` och `sp_q_#`för backend-sökning.

Se tabellraderna 25, 26 och 32 i CGI-parametrar för [backend-sökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

## Lägga till en gemensam frasgrupp {#task_35C84FABCD9042C5B48C5C788B752871}

Du kan lägga till vanliga frasgrupper för att se till att sökfrågor korrekt returnerar webbsidor som innehåller alla ord, i exakt ordning och i den närhet som kunden skrev.

När du lägger till vanliga frasgrupper kan du använda funktionen Sök på huvudsidan för gemensam frasgrupp. Med sökfunktionen kan du söka efter en befintlig fras och ta reda på i vilken grupp den finns.

Se [Söka efter grupper som innehåller vissa ord i en fras](../c-about-linguistics-menu/c-about-common-phrases.md#task_20714969274740A7BB4DC71E705EA15E).

**Lägga till en gemensam frasgrupp**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** på produktmenyn.
1. På [!DNL Common Phrases Groups] sidan klickar du på **Lägg till frasgrupp**.
1. Ange önskade alternativ på [!DNL Add Common Phrase Group] sidan och lägg till alla fraser som gruppen består av.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Gruppnamn </p> </td> 
      <td colname="col2"> <p>Obligatoriskt. </p> <p>Det unika namnet för Common Phase Group. </p> <p>Om du redigerar en gemensam frasgrupp senare bör du tänka på att du inte kan ändra gruppnamnet. Om du vill ändra gruppnamnet använder du funktionen <span class="uicontrol"> Byt namn</span> . </p> <p>Se Byta namn på en gemensam <a href="../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB" format="dita" scope="local"></a>frasgrupp. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Anteckningar </p> </td> 
      <td colname="col2"> <p>Valfritt. </p> <p>Lägg till information som gäller för den gemensamma frasgruppen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fraser </p> </td> 
      <td colname="col2"> <p>Obligatoriskt. </p> <p>Här kan du ange en fras upp till högst fem ord. Kontakta teknisk support om du vill ändra den maximala ordinställningen. </p> <p>Varje fras som du anger måste vara unik inom en gemensam frasgrupp. </p> <p>Använd plus- (+) och minusikonerna (-) i åtgärdskolumnen för att lägga till den angivna frasen eller för att ta bort en fras. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **Lägg till**.
1. (Valfritt) Gör något av följande:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testa en vanlig fras {#task_A0C344E051CA45A9A0588242F9DA675D}

Om du har valt metadatafält som ska associeras med en frasgrupp kan du testa en viss fras expansion.

När du testar en fras expansion söker du efter en exakt fras mot metadatafälten som du associerar med frasgruppen. Frasen genomsöks som om den omges av citattecken. Alla andra metadatafält söker bara efter orden inom frasen, utan citattecknen. Anta att du testade frasen `audi TT`. De returnerade resultaten kan se ut så här:

`title|body|field3:"Audi TT" url|desc|keys|target|alt:Audi TT`

**Testa en vanlig fras**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** på produktmenyn.
1. På [!DNL Common Phrases Groups] sidan anger du den fras vars metadataexpansion du vill testa i **testfrasen som innehåller** textfältet.
1. Klicka på **[!UICONTROL Test]**.

   Expanderingsresultaten visas i textrutan.
1. (Valfritt) Utöka visningsområdet genom att dra i textrutans nedre högra hörn.

## Söka efter grupper som innehåller vissa ord i en fras {#task_20714969274740A7BB4DC71E705EA15E}

Du kan använda [!DNL Find] för att söka efter specifika ord i en fras bland alla befintliga grupper som du har lagt till.

När du använder Sök hittar den följande:

* Där samma fras hittas av alla grupper.
* Något av orden i frasen bland alla grupper, oavsett ordordning och närhet i frasen.

Se även [Redigera en vanlig frasgrupp](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61).

**Söka efter grupper som innehåller vissa ord i en fras**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** på produktmenyn.
1. Skriv en fras på [!DNL Common Phrases Groups] sidan i **[!UICONTROL Find groups with phrases that contain]** textfältet.
1. Klicka på **[!UICONTROL Find]**.

   Resultatet visas i textrutan.
1. (Valfritt) Gör något av följande:

   * Utöka visningsområdet genom att dra i textrutans nedre högra hörn.
   * Klicka på en hyperlänkad fras i resultatfönstret för att öppna sidan Redigera gemensam frasgrupp i den associerade gruppen.

## Redigera en gemensam frasgrupp {#task_5CAC3A133C5342EEAFE55A7EABCBCD61}

Du kan redigera befintliga fält, anteckningar och fraser i en frasgrupp som du har lagt till. Om du vill redigera gruppnamnet måste du använda [!DNL Rename] funktionen.

Se även [Byta namn på en Common Phrase Group](../c-about-linguistics-menu/c-about-common-phrases.md#task_168E07C59C0F40989D43E7010EFF22EB).

**Så här redigerar du en grupp med vanliga fraser**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** på produktmenyn.
1. På [!DNL Common Phrases Groups] sidan klickar du **[!UICONTROL Edit]** längst till höger om ett gruppnamn.
1. Ange önskade alternativ på [!DNL Edit Common Phrase Group] sidan.

   Se tabellen med alternativ under [Lägga till en gemensam frasgrupp](../c-about-linguistics-menu/c-about-common-phrases.md#task_35C84FABCD9042C5B48C5C788B752871).
1. Klicka på **Spara ändringar**.
1. (Valfritt) Gör något av följande:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Byta namn på en gemensam frasgrupp {#task_168E07C59C0F40989D43E7010EFF22EB}

Du kan ändra namnet på en befintlig gemensam frasgrupp. Om du vill ändra de befintliga fälten, anteckningarna och fraserna i en gemensam frasgrupp måste du använda [!DNL Edit] funktionen.

Se [Redigera en gemensam frasgrupp](../c-about-linguistics-menu/c-about-common-phrases.md#task_5CAC3A133C5342EEAFE55A7EABCBCD61) .

**Så här byter du namn på en grupp med vanliga fraser**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** på produktmenyn.
1. På [!DNL Common Phrases Groups] sidan klickar du **[!UICONTROL Rename]** längst till höger om ett gruppnamn.
1. På [!DNL Rename Common Phrase Group] sidan anger du gruppnamnet i **[!UICONTROL Group Name]** textfältet.
1. Klicka på **Byt namn**.
1. (Valfritt) Gör något av följande:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ta bort en gemensam frasgrupp {#task_4106D282A2ED4A27B09EE5A8CAAEDA36}

Du kan ta bort alla delade frasgrupper som du har lagt till. Om du tar bort en grupp av misstag kan du använda [!DNL History] för att återställa gruppen.

Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

**Så här tar du bort en grupp med vanliga fraser**

1. Klicka på **[!UICONTROL Linguistics]** > **[!UICONTROL Common Phrases]** på produktmenyn.
1. På [!DNL Common Phrases Groups] sidan klickar du **[!UICONTROL Delete]** längst till höger om ett gruppnamn.
1. På [!DNL Delete Common Phrase Group] sidan klickar du på **[!UICONTROL Delete]**.
1. (Valfritt) Gör något av följande:

   * Klicka **[!UICONTROL History]** för att återställa ändringar som du har gjort.

      Se [Använda alternativet](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002)Historik.

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

