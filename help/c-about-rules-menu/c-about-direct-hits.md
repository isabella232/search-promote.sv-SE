---
description: Med direktträffar kan du omdirigera en kund till en angiven URL när kunden söker efter en matchande term. Med den här typen av funktioner kan du förbättra navigeringen i sökningen på webbplatsen.
solution: Target
title: Om direktträffar
topic: Rules,Site search and merchandising
uuid: 374d63c8-2b82-4165-b543-05b587757baa
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---


# Om direktträffar{#about-direct-hits}

Med direktträffar kan du omdirigera en kund till en angiven URL när kunden söker efter en matchande term. Med den här typen av funktioner kan du förbättra navigeringen i sökningen på webbplatsen.

## Använda direktträffar {#concept_C5EE074A19FD4D5B8DD21DB575E35565}

Direktträffar består av två huvuddelar: webbadressen till webbplatsen och ett eller flera kommaavgränsade söktermer. Direktträffar anges enligt följande:

```
    website_URL: term
    website_URL: term, term, term
```

Anta till exempel att du har en företagswebbplats med en sida som anger alla dina villkor. När en kund söker efter dina villkor, i stället för att visa resultaten, kan du dirigera om kunden till din villkorssida.

```
    https://www.mycompany.com/policies.asp?article=terms: terms and conditions, terms, conditions, security
    https://www.mycompany.com/press/news.asp: press releases, press
```

Om frågetermen inte matchar några direkta träffar returneras sökresultaten på vanligt sätt.

## Konfigurerar direkta träffar {#task_64DFB8C554874C699FCC0C2F26C3669F}

Du kan ange söktermer som omdirigerar en webbläsare till en URI i stället för att returnera sökresultaten.

<!-- 

t_configuring_direct_hits.xml

 -->

Tomma rader och kommentarsrader som börjar med tecknet &#39;#&#39; (hash) tillåts.

**Konfigurera direktträffar**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]** på produktmenyn.
1. I fältet [!DNL Direct Hits] anger du webbplatsens URL och en eller flera kommaavgränsade söktermer.
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Testar direktträffar {#task_1E2EA833BF90423AA0DD8C5BBFE77445}

Innan du publicerar regler för direktträffar kan du testa direktträffar genom att ange en term.

<!-- 

t_testing_direct_hits.xml

 -->

Om du testar en term som inte omfattas av en regel för direktträffning visas ett meddelande. I ett sådant scenario skulle sökresultaten returneras som vanligt om regeln för direktträffen fanns på din webbplats. Om du testar en term som omfattas av en regel för direktträffning visas ett meddelande som talar om att en omdirigering har gjorts till den angivna URL:en.

**Testa direktträffar**

1. Klicka på **[!UICONTROL Rules]** > **[!UICONTROL Direct Hits]** på produktmenyn.
1. Ange en sökterm i fältet [!DNL Test Direct Hits] och klicka sedan på **[!UICONTROL Test]**.
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

