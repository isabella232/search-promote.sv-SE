---
description: Med Proximity Search kan du koppla en unik plats till en sida på webbplatsen och sedan söka och sortera resultaten efter närhet (avstånd) från en viss plats.
solution: Target
title: Om närhetssökning
topic: Appendices,Site search and merchandising
uuid: 24fc9265-3400-46a7-b6e0-4de5b049a39a
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 0%

---


# Om närhetssökning{#about-proximity-search}

Med Proximity Search kan du koppla en unik plats till en sida på webbplatsen och sedan söka och sortera resultaten efter närhet (avstånd) från en viss plats.

Anta till exempel att du har fyllt i sidor på din webbplats med metadata för postnummer i USA, som följande:

```
<meta name="zipcode" content="84057">
```

Sedan konfigurerar du ditt konto så att du indexerar dina ZIP-kodmetadata. I **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Definitions]** > **[!UICONTROL Add New Field]** på sidan [!DNL Add Field] anger du följande alternativ:

* Fältnamn: `zip`
* Metataggens namn: `zipcode`
* Datatyp: **[!UICONTROL Location]**
* Sortering: **[!UICONTROL Ascending]**
* Standardenheter: **[!UICONTROL Miles]**

När du har indexerat webbplatsen gör du följande sökning:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_s=zip_proximity
```

Resultatuppsättningen innehåller alla dokument som ligger inom 100 miles från postnummer 84057, sorterade i stigande ordning efter avståndet från det här postnumret.

Du kan också använda telefonområdeskoder för USA-platser. Du kan också använda latitud-/longitudpar för att ange platser i webbplatsens metadata och i sökvillkoren. Platstypen bestäms automatiskt utifrån formuläret för de data som anges.

Tresiffriga platsvärden (&quot;DDD&quot;, där varje&quot;D&quot; representerar en decimalsiffra mellan 0-9) behandlas som ett amerikanskt telefonnummer.

Fem eller fem streckade fyrsiffriga platsvärden (&quot;DDDDD&quot; eller&quot;DDDDD-DDDD&quot;) behandlas som ett amerikanskt postnummer.

Platsvärden i den exakta formen av &quot;±DD.DDDD±DDD.DDDD&quot; behandlas som ett latitud-/longitudpar. Det första signerade numeriska värdet anger latitud och det andra signerade numeriska värdet representerar longitud.

**Viktigt**: Om du anger ett positivt latitudvärde, ett positivt longitudvärde eller både och måste plustecknet&quot;+&quot; i URL:en kodas som  `%2b`. I annat fall tolkas plustecknet (+) som ett blanksteg och värdet känns inte igen som en giltig plats. Anta till exempel att du har ett latitudvärde på +49.2394 och longitudvärdet -123.1892. Platsdelen av URL:en, med &quot;+&quot; kodad, skulle se ut så här:

```
...&sp_q_location_1=%2b49.2394-123.1892...
```

* Positiva latitudvärden representerar grader norr om ekvatorn.
* Negativa latitudvärden representerar grader söder om ekvatorn.
* Positiva longitudvärden representerar grader öster om Prime Meridian.
* Negativa longitudvärden representerar grader väster om Prime Meridian.

Värdet &quot;+48.8577+002.2950&quot; motsvarar till exempel 48,8577 grader norr om ekvatorn, 2,295 grader öster om Prime Meridian, den exakta platsen för Eiffeltornet i Paris, Frankrike. De numeriska tecknen och varje siffra krävs, även inledande och avslutande nollor. De tre värdena &quot;48.8577+2.2950&quot;, &quot;+48.8577+2.2950&quot; och &quot;+48.8577+02.295&quot; är inte platser. Det första värdet saknar inledande tecken på latituden. Det andra värdet saknar de två inledande nollorna på longitud. Det tredje värdet saknar den efterföljande nollan på longitud. Kontrollera att du noggrant undersöker indexloggen för eventuella platsrelaterade problem.

När du söker efter närhet skapas ett speciellt &quot;närhetsutdatafält&quot; för sökningen. Fältet fylls i med det relativa avståndet mellan platsen som anges i sökvillkoren och platsen som associeras med varje sökresultat. Det här specialfältet namnges för det platstypfält som används i sökvillkoren med &quot;_proximity&quot; tillagt i slutet.

I exemplet ovan sorteras resultaten i stigande ordning efter&quot;zip_proximity&quot;. Det vill säga avståndet mellan det angivna postnumret (84057) och varje resultats&quot;zip&quot;-fältplats. Du kan också använda det här speciella &quot;närhetsutdatafältet&quot; för att visa det relativa avståndet för varje sökresultat, i antingen kilometer eller engelska mil, med hjälp av sökmallstaggen `<Search-Display-Field>`.

Se [Sök efter malltaggar](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Du kan också söka utan alternativet sp_s. I så fall sorteras resultaten efter poäng (sp_s=0, som är standard). Poängen påverkas av det relativa avståndet mellan varje resultat från den närhetssökplats som anges med parametern sp_q_location[_#]. En ny cgi-parameter sp_q_max_relevant_distance[#] har lagts till för att eventuellt styra den relevansberäkning som används för närhetssökningar.

Här följer ett exempel på sökning som är relevant för närhet:

```
...&sp_q_location_1=84057&sp_x_1=zip&sp_q_max_1=100&sp_q_2=shirt&sp_x_2=title&sp_q_max_relevant_distance_2=50
```

Resultatuppsättningen innehåller alla dokument som är placerade inom 100 miles från postnummer 84057 och innehåller ordet&quot;skjorta&quot; i titelfältet, sorterat efter poängsättning som påverkas av ungefärlig poängsättning. Ett perfekt relevansresultat för närhetskomponenten skulle representera avståndet 0. En minsta relevanspoäng för närhetskomponenten skulle representera ett avstånd på drygt 50 engelska mil.

Du kan lära dig mer om närhetssökning genom att granska `sp_location`, `sp_location_#`, `sp_q_min`, `sp_q_min_#`, `sp_q_max`, `sp_q_max_#` och `sp_s` i referensavsnittet för CGI-parametrar för sökning.

Se [Sök efter CGI-parametrar](../c-appendices/c-cgiparameters.md#reference_DA27A8B0728246DA94994885E1353890).

Se [Lägga till ett nytt metataggsfält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).
