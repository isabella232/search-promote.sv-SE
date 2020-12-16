---
description: Du kan använda menyer för att anpassa presentationslagret.
seo-description: Du kan använda menyer för att anpassa presentationslagret.
seo-title: Om menyer
solution: Target
subtopic: Navigation
title: Om menyer
topic: Design,Site search and merchandising
uuid: 011050cd-21b6-4150-9503-18fa3f771626
translation-type: tm+mt
source-git-commit: 552f93f1f630c64bbe3d5c8a87c4f5895ae6868c
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 1%

---


# Om menyer{#about-menus}

Du kan använda menyer för att anpassa presentationslagret.

## Använda menyer {#concept_68123CE5CF4447B59217B5D721424E32}

Lägg till menyer som mappar till inställningar i sökningen. Varje alternativ på en meny anger värdet för menyinställningen. Du kan också anpassa menyetiketterna.

I presentationsmallen kan du referera till de menyer som är definierade. Du kan sedan placera dem i en HTML-komponent som du vill ha, t.ex. en markeringskontroll. Med den här kombinationen kan användare anpassa sina sökresultat. Tre menytyper stöds: sortera, räkna och navigera.

## Lägga till en ny meny {#task_EE171532D3AE477FAFE8C2F4077A6D73}

Du kan lägga till menyer som mappar till inställningar i sökresultaten.

<!-- 

t_adding_a_new_menu.xml

 -->

>[!NOTE]
>
>Se till att du refererar till menyn i presentationsmallen så att den visas på webbplatsen.

**Lägga till en ny meny**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]** på produktmenyn.
1. Klicka på **[!UICONTROL Add New Menu]** på sidan [!DNL Menus].
1. Ange önskade alternativ på sidan [!DNL Add Menu].

   De här inställningarna påverkar både beteendet och standardpresentationen för en vägbeskrivare. Du kan åsidosätta vissa av de här inställningarna med hjälp av presentationsmallens inställningar.

   Se [Om menyer](../c-about-design-menu/c-about-menus.md#concept_68123CE5CF4447B59217B5D721424E32).

   <!-- 
   r_add_menu_options.xml
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
      <td colname="col1"> <p>Menynamn </p> </td> 
      <td colname="col2"> <p>Menyns namn. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Menytyp </p> </td> 
      <td colname="col2"> <p>Anger någon av följande tre menytyper: </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
      <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Sortera  </span> <p>Sorterar sökningen efter någon av dina definierade metadatatyper. </p> <p>Du kan till exempel definiera en sorteringsmeny med följande metadatatyper: tre faktorer av betydelse, ett anpassat metadatafält, t.ex. en tillgänglighetskod, och priset. De tre objekten kan ha etiketterna Sortera efter relevans, Sortera efter tillgänglighet respektive Sortera efter pris. När du inkluderar detta i presentationsmallen kan kunden använda den här kontrollen för att sortera sina sökresultat. </p> </li> 
      <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Antal  </span> <p>Definierar antalet sökresultat som ska visas. Den här menytypen mappar till cgi-parametern <span class="varname"> sp_c </span>. </p> <p>Se <a href="../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8" format="dita" scope="local"> CGI-parametrar för backend-sökning </a>. </p> </li> 
      <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Navigering  </span> <p>Anger en uppsättning statiska URL:er som är associerade med menyalternativ. Vanligtvis används en navigeringsmeny för att skapa ett navigeringsfält på den översta nivån på sökresultatsidan. </p> <p>Du kan till exempel skapa en meny som innehåller kvinnor, män, pojkar och flickor där menyalternativen skulle vara något som följer: 
      <code>
        /?q1=womens;x1=gender 
      </code>, 
      <code>
        /?q1=mens;x1=gender 
      </code> </p> </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Merchandising </p> 
        <!--DONT' KNOW WHAT THIS DOES--> </td> 
      <td colname="col2"> <p>Det här alternativet är bara tillgängligt om du väljer menytypen <span class="uicontrol"> Sortera. </span> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Antal alternativ på menyn </p> </td> 
      <td colname="col2"> <p>Anger antalet alternativ på en meny. Om du ändrar den här inställningen läggs fält till eller tas bort från formuläret. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardartikel </p> </td> 
      <td colname="col2"> <p>Här kan du välja vilket menyalternativ som ska visas som standard. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Artikelvärde </p> </td> 
      <td colname="col2"> <p>Alternativets värde beror på vilken menytyp du har angett. </p> 
        <ul id="ul_2F14E6AA673640578A2D5161FD9D13EF"> 
        <li id="li_5017EC6E4ACB4B8E99E0AA61CBAAFFAE"> Typ av sorteringsmeny <p>Identifierar vad det markerade objektet på menyn ska sorteras efter. De markerade objekten fylls i med sorterbara metadatafält. </p> <p>För ett enskilt objekt kan du sortera efter tre metadatafält. Sorteringen görs i den ordning som anges. </p> </li> 
        <li id="li_CC6BAFBF969C4367A71B55F08E0758D1"> Typ av räkningsmeny <p>Här kan du ange hur många resultat du vill returnera när kunden väljer det här menyalternativet. </p> </li> 
        </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Artikeletikett </p> </td> 
      <td colname="col2"> <p>Alternativets etikett beror på vilken menytyp du har angett. </p> 
        <ul id="ul_957BF01235F84748B5EB7062D6AEAC41"> 
        <li id="li_03FB2E2C96134A2B8E08154F87F0CD55"> Typ av sorteringsmeny <p>Identifierar den anpassade etikett som du vill att kunden ska se när de visar det här alternativet på menyn. </p> </li> 
        <li id="li_C9FE2BC46D9443FB85FEB837C7CA45E1"> Typ av räkningsmeny <p>Identifierar den anpassade etikett som du vill visa för det här menyalternativet. </p> </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Add]**.
1. (Valfritt) Gör något av följande på sidan [!DNL Menus]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera en meny {#task_0770DBFD0C7046169097FB6F771B9114}

Du kan redigera inställningarna för alla menyer som du har lagt till.

<!-- 

t_editing_a_menu.xml

 -->

>[!NOTE]
>
>Se till att du refererar till menyn i presentationsmallen så att den visas på webbplatsen.

**Redigera en meny**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]** på produktmenyn.
1. På sidan [!DNL Menus] klickar du på **[!UICONTROL Edit]** längst till höger om ett menynamn.
1. Ange önskade alternativ på sidan [!DNL Edit Menu].

   Se tabellen med alternativ under [Lägga till en ny meny](../c-about-design-menu/c-about-menus.md#task_EE171532D3AE477FAFE8C2F4077A6D73).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande på sidan [!DNL Menus]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort en meny {#task_645E212311A045CD8D9D906878165F47}

Du kan ta bort alla menyer som du har lagt till.

<!-- 

t_deleting_a_menu.xml

 -->

**Ta bort en meny**

1. På produktmenyn klickar du på **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Menus]**
1. På sidan [!DNL Menus] klickar du på **[!UICONTROL Delete]** längst till höger om ett menynamn.
1. Klicka på **[!UICONTROL OK]** i dialogrutan [!DNL Confirmation].
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

