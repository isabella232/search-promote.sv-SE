---
description: Bläddringar är en navigeringskontroll som du kan lägga till på webbplatsen. Breadcrumb ger kunderna feedback om var de befinner sig i en sökresultatuppsättning. Det hjälper dem också att snabbt gå tillbaka till ett tidigare steg.
solution: Target
subtopic: Navigation
title: Om Breadcrumbs
topic: Design, webbplatssökning och -försäljning
uuid: 3e630a72-a631-4f4f-8aa5-adf2882cdf1c
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 1%

---


# Om vägbeskrivningar{#about-breadcrumbs}

Bläddringar är en navigeringskontroll som du kan lägga till på webbplatsen. Breadcrumb ger kunderna feedback om var de befinner sig i en sökresultatuppsättning. Det hjälper dem också att snabbt gå tillbaka till ett tidigare steg.

## Använda vägbeskrivningar {#concept_FB8A943C594A4A1593B118141DA61F03}

I kolumnerna spåras termen som sökts efter och de efterföljande faktorerna som markerats för att begränsa resultatmängden.

Du kan använda inställningarna för Breadcrumb för att anpassa kontrollen av vägbeskrivningslagret. Om presentationslagret innehåller fler än en uppsättning sökresultat fungerar kontrollen för vägbeskrivningar på den primära sökningen på sidan.

Du kan redigera en vägbeskrivare om du vill ändra standardbeteendet, maximal värdebredd och värdetillägg och om du vill välja om frågetermen ska inkluderas.

## Lägger till ett nytt vägbeskrivningsmönster {#task_2FFA94F82AE74F10BDDE7367CDCEAE8B}

Du kan lägga till ett vägbeskrivningsfält så att kunden kan spåra var de finns på webbplatsen.

<!-- 

t_adding_a_new_breadcrumb.xml

 -->

>[!NOTE]
>
>Var noga med att referera till den synliga sökvägen i presentationsmallen så att den visas på webbplatsen.

**Lägga till en ny vägbeskrivare**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]** på produktmenyn.
1. Klicka på **[!UICONTROL Add Breadcrumb]** på sidan [!DNL Breadcrumbs].
1. Ange önskade alternativ på sidan [!DNL Add Breadcrumb].

   De här inställningarna påverkar både beteendet och standardpresentationen för en vägbeskrivare. Du kan åsidosätta vissa av de här inställningarna med hjälp av presentationsmallens inställningar.

   <!-- 
   
   r_breadcrumb_options.xml
    
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
      <td colname="col1"> <p>Breadcrumb-namn </p> </td> 
      <td colname="col2"> <p>Breadcrumb-namnet. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Beteende </p> </td> 
      <td colname="col2"> <p>Anger ett av följande tre beteenden för vägbeskrivningar: </p> <p> 
      <ul id="ul_7E66ACC1DA494B20BEC3B0B2CCAB103A"> 
        <li id="li_D81876660A8B48AFB70D3317063FBF6F"> <span class="uicontrol"> Gå  </span> <p>Gå till för att ta bort alla vägbeskrivningar efter den som du klickar på och påbörjar en ny sökning vid den punkten. </p> </li> 
        <li id="li_63AE06B544B64DCAA8C55031B3DFFFF7"> <span class="uicontrol"> Ta bort  </span> <p>Ta bort tar bort den synliga sökvägen som kunden klickade på och påbörjar sedan en ny sökning. Det här beteendet är användbart när du vill att kunden ska kunna ångra steg som steg för att gå igenom sökningen. </p> </li> 
        <li id="li_EEC810D420FF41498ECE49EBAAB33BE5"> <span class="uicontrol"> Släpp  </span> <p>Släpp tar bort alla vägbeskrivningar. </p> </li> 
      </ul> </p> <p> Anta t.ex. att du har en bredd på 1 &gt; 2 &gt; 3 &gt; 4. När en kund klickar på"2" får den följande resultat beroende på vilket beteende du har valt: </p> <p> 
      <ul id="ul_96FCD8E4C3704B45B59BC18A7A1AC52A"> 
        <li id="li_B880037088DF426F880788EAA3072180">Gå till - 1 &gt; 2 </li> 
        <li id="li_D0F07A15DCD043EFA4563632ED33A9E2">Ta bort - 1 &gt; 3 &gt; 4 </li> 
        <li id="li_D848ED44B4E44538AA92010F9F186224"> Drop - Hela vägbeskrivningen tas bort, vilket tar kunden tillbaka till punkten innan de börjar gå ned. </li> 
      </ul> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Maximal värdebredd </p> </td> 
      <td colname="col2"> <p>Anger längden på varje värde i den synliga sökvägen. Du anger inställningen som ett antal tecken. </p> <p>En inställning på 6 innebär att det synliga spåret kan innehålla upp till 6 tecken, inklusive blanksteg. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Värdetillägg </p> </td> 
      <td colname="col2"> <p>Anger de ellipser som ska användas när ett vägbeskrivande objekt trunkeras. </p> <p>Som standard ett ".." (ellipser) används. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Inkludera frågeterm </p> </td> 
      <td colname="col2"> <p>Kontrollerar om det finns en frågeterm i en vägbeskrivare. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktivera användardefinierade Crumbs </p> </td> 
      <td colname="col2"> <p>Markera om du vill att du ska kunna använda användardefinierade objekt i vägbeskrivningar med <span class="codeph"> uX=[name]&amp;[name]=[value] </span>-parametrar i URL:en. Du kan använda bearbetningsregler för att hantera de här parametrarna som du vill. </p> <p>Om den här funktionen till exempel är aktiverad och du har URL:en <code> https://search.host.com/?1=category&amp;q1=Clothes&amp;u2= 
          type&amp;type=Men&amp;x3=kind&amp;q3=Sweater </code> om du har ansikten <span class="codeph"> <span class="varname"> kategori </span> </span> och <span class="codeph"> typ <span class="varname"> </span> </span>, ser det ut som <span class="codeph"> kläder &gt; Män &gt; Sötare </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Användardefinierade Crumb-namn </p> </td> 
      <td colname="col2"> <p>En kommaavgränsad lista med alla möjliga namn på användardefinierade breadcrumb-objekt. </p> <p>Det här alternativet är bara tillgängligt om du markerar <span class="uicontrol"> Aktivera användardefinierade Crumbs </span>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Add]**.
1. (Valfritt) Gör något av följande på sidan [!DNL Breadcrumbs]:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Redigera ett vägbeskrivande objekt {#task_583481D9A23E4E0F97AEB18E72CBE13F}

Du kan redigera inställningarna för de vägbeskrivningar som du har lagt till.

<!-- 

t_editing_a_breadcrumb.xml

 -->

>[!NOTE]
>
>Var noga med att referera till den synliga sökvägen i presentationsmallen så att den visas på webbplatsen.

**Så här redigerar du ett vägbeskrivningsmönster**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]** på produktmenyn.
1. På sidan [!DNL Breadcrumbs] klickar du på **[!UICONTROL Edit]** längst till höger om ett felsökningsnamn.
1. Ange önskade alternativ på sidan [!DNL Edit Breadcrumb].

   Se tabellen med alternativ under [Lägga till en ny vägbeskrivare](../c-about-design-menu/c-about-breadcrumbs.md#task_2FFA94F82AE74F10BDDE7367CDCEAE8B).
1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Gör något av följande på sidan **[!UICONTROL Breadcrumb]**:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Tar bort ett vägbeskrivningsfel {#task_401C6E481A744284906E15A29E04F757}

Du kan ta bort alla synliga tecken som du har lagt till.

<!-- 

t_deleting_a_breadcrumb.xml

 -->

**Så här tar du bort ett vägbeskrivningsmönster**

1. Klicka på **[!UICONTROL Design]** > **[!UICONTROL Navigation]** > **[!UICONTROL Breadcrumbs]** på produktmenyn.
1. På sidan [!DNL Breadcrumbs] klickar du på **[!UICONTROL Delete]** längst till höger om ett felsökningsnamn.
1. Klicka på **[!UICONTROL OK]** i dialogrutan [!DNL Confirmation].
1. (Valfritt) Gör något av följande:

   * Klicka på **[!UICONTROL History]** om du vill återställa ändringar som du har gjort.

      Se [Använda alternativet Historik](../t-using-the-history-option.md#task_70DD3F87A67242BBBD2CB27156F43002).

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

