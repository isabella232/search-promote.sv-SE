---
description: Datavyer visar sökresultaten med metafälten. Varje kolumn är ett metafält och varje rad är ett resultat av en sökfråga. Anpassa datavyer genom att välja och ordna om kolumner. Datavyer kan också ha anpassade rubriker och beskrivningar.
solution: Target
title: Om datavyer
topic: Rapporter,Webbplatssökning och -försäljning
uuid: 18930551-960d-40c2-b5b7-0807a2e11134
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 0%

---


# Om datavyer{#about-data-views}

Datavyer visar sökresultaten med metafälten. Varje kolumn är ett metafält och varje rad är ett resultat av en sökfråga. Anpassa datavyer genom att välja och ordna om kolumner. Datavyer kan också ha anpassade rubriker och beskrivningar.

## Använda datavyer {#concept_DCA897D074464BC1861AA47B40CC86C3}

Varje konto kan enkelt skapa flera datavyer. Använd sidan Datavy för att skapa och redigera dessa datavyer.

När du har lagt till en datavy måste du redigera den för att konfigurera och anpassa vyn.

Se [Redigera en datavy](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

Du kan kopiera en befintlig datavy och använda den som bas när du skapar en ny datavy.

Se [Kopiera en datavy](../c-about-reports-menu/c-about-data-views.md#task_78D4C2799BC84677843ED4CA1CD205AF).

## Lägga till en datavy {#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D}

Du kan lägga till en datavy på sidan [!DNL Data Views] för att visa värdena för varje metafält med en sökfråga.

När du har lagt till en datavy måste du redigera den för att konfigurera och anpassa vyn.

Se [Redigera en datavy](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

**Lägga till en datavy**

1. Klicka på **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Data View]** på sidan [!DNL Data Views].
1. I dialogrutan [!DNL Add New Data View] anger du namnet på datavyn som du vill skapa i fältet [!DNL Title].
1. Klicka på **[!UICONTROL Add]**.

## Redigera en datavy {#task_258A367896C24DD498C755925EA8F516}

När du lägger till en datavy på [!DNL Data Views]-sidan använder du Redigera för att ändra datavyns namn och beskrivning eller för att flytta, visa eller dölja visningen av varje metafält.

Du kan också låsa eller låsa upp en markerad datavy.

Se [Lägga till en datavy](../c-about-reports-menu/c-about-data-views.md#task_A20FEB2E1CA1444D816D2F5F4B6E5B2D).

**Redigera en datavy**

1. Klicka på **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** på produktmenyn.
1. På sidan [!DNL Data Views] i kolumnen [!DNL Actions] i tabellen klickar du på **[!UICONTROL Edit]** i raden med datavyn som du vill ändra.
1. Ange önskade alternativ på sidan [!DNL Data Views Editor].

   I Datavy Editor finns alla kontroller för att dölja, visa och flytta fältkolumner på datavy-sidan.

   När du visar en datavy visar den resulterande tabellen även följande ytterligare kolumnfält som inte kan redigeras: Rankning, relevans och poäng (totalt). Dessa tre specialfält representerar relevanspoängen, rangordningspoängen och totalpoängen för varje resultat.

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Titel </p> </td> 
      <td colname="col2"> <p>Datavyns namn. Namnet visas längst upp till höger när du visar datavyn. </p> <p>Se <a href="../c-about-reports-menu/c-about-data-views.md#task_FD0D2CE53DF84CBD9220AD7CA920011F" type="task" format="dita" scope="local"> Visa en datavy</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Beskrivning </p> </td> 
      <td colname="col2"> <p>(Valfritt) Innehåller en beskrivning av datavyn. Beskrivningen visas mellan datavyns titelnamn och textfältet <span class="wintitle"> Ny sökning</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Sökparametrar </p> </td> 
      <td colname="col2"> <p>Här kan du ange standardsökparametrar. När datavyn visas för första gången läggs dessa CGI-parametrar automatiskt till. </p> <p>Ändra eller ta inte bort <span class="codeph"> sp_cs</span> eller <span class="codeph"> sp_f</span>. De här parametrarna är viktiga för datavyn oavsett vilken teckenuppsättning som används för kontot. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" type="reference" format="dita" scope="local"> CGI-parametrar för backend-sökning</a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lås status </p> </td> 
      <td colname="col2"> <p>Gör att du kan låsa eller låsa upp datavyn. </p> <p>Du kan bara visa en låst datavy med ett lösenord och användarnamn. Användaren måste vara en aktuell medlem i kontot. </p> <p>En olåst datavy öppnas utan lösenord eller användarkonto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Order </p> </td> 
      <td colname="col2"> <p> Här kan du ändra kolumnordningen genom att redigera talet i textrutan <span class="wintitle"> Ordna</span>. Du kan också dra och släppa en rad för att ändra kolumnordningen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkludera </p> </td> 
      <td colname="col2"> <p> Gör att du kan aktivera eller inaktivera visningen av kolumnen. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Visa URL som bild </p> </td> 
      <td colname="col2"> <p>Visa miniatyrbilder och bilder i den här kolumnen om sökresultatet för den här kolumnen returnerar en URL. </p> <p>URL:en rensas från schemanamnet eller protokollet innan den blir ett värde för <span class="codeph"> src</span>-attributet för en bildtagg. </p> <p>Om det returnerade sökresultatet inte ser ut som en URL-adress till en bild, visas ett. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Fältlängd </p> </td> 
      <td colname="col2"> <p>Anger antalet tecken som visas som ett resultat i datavyn. </p> <p>Standardvärdet är 100 tecken. </p> <p>Vissa fält, till exempel rankningspoäng och datumfält, har inte justerbara fältlängder. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Kopiera en datavy {#task_78D4C2799BC84677843ED4CA1CD205AF}

Du kan kopiera en befintlig datavy på [!DNL Data Views]-sidan och använda den som bas när du skapar en ny datavy.

När du har kopierat en datavy kan du anpassa den ytterligare genom att redigera vyn.

Se [Redigera en datavy](../c-about-reports-menu/c-about-data-views.md#task_258A367896C24DD498C755925EA8F516).

**Så här kopierar du en datavy**

1. Klicka på **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** på produktmenyn.
1. På sidan [!DNL Data Views] i kolumnen [!DNL Actions] i tabellen klickar du på **[!UICONTROL Copy]** i raden med datavyn som du vill kopiera.
1. På sidan [!DNL Copy Data View] anger du det nya namnet som du vill tilldela datavyn i textfältet [!DNL New Title].
1. Klicka på **[!UICONTROL Copy]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Ta bort en datavy {#task_61C32F8F00A549A5A3E7EDDA6F537098}

Du kan ta bort en datavy på [!DNL Data Views]-sidan som du inte längre behöver eller använder.

**Ta bort en datavy**

1. Klicka på **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** på produktmenyn.
1. På sidan [!DNL Data Views] i kolumnen [!DNL Actions] i tabellen klickar du på **[!UICONTROL Delete]** i raden med datavyn som du vill ta bort.
1. På sidan [!DNL Delete Data View] klickar du på **Ta bort**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Visa en datavy {#task_FD0D2CE53DF84CBD9220AD7CA920011F}

Du kan använda [!DNL View] på sidan [!DNL Data Views] för att visa en vald datavy.

Datavyn som du väljer öppnas i ett separat webbläsarfönster.

**Så här visar du en datavy**

1. Klicka på **[!UICONTROL Reports]** > **[!UICONTROL Data Views]** på produktmenyn.
1. Gör något av följande:

   * På sidan [!DNL Data Views] i kolumnen [!DNL Title] i tabellen klickar du på namnet på den datavy som du vill öppna.

   * På sidan [!DNL Data Views] i kolumnen [!DNL Actions] i tabellen klickar du på **[!UICONTROL View]** i raden med datavyn som du vill öppna.

