---
description: Använd menyn Kontoalternativ för att uppdatera kontoinställningarna, ange försäljningsinställningar eller ta bort en egen Search&amp;Promote-konto.
seo-description: Använd menyn Kontoalternativ för att uppdatera kontoinställningarna, ange försäljningsinställningar eller ta bort en egen Search&amp;Promote-konto.
seo-title: Om menyn Kontoalternativ
solution: Target
subtopic: Account Options
title: Om menyn Kontoalternativ
topic: Settings,Site search and merchandising
uuid: 0f830033-de9e-4197-8d76-906c818662eb
translation-type: tm+mt
source-git-commit: f21a3f7fe0aeaab517a5ca36da43594873b3e69a
workflow-type: tm+mt
source-wordcount: '1684'
ht-degree: 0%

---


# Om menyn Kontoalternativ{#about-the-account-options-menu}

Använd menyn Kontoalternativ för att uppdatera kontoinställningarna, ange försäljningsinställningar eller ta bort ditt eget Search &amp; Promote-konto.

## Konfigurerar dina kontoinställningar {#task_80A38D0C8E4F453395BD67B81E4B45D9}

Hantera kontoinställningar som webbplatsens namn och adress, tidszon med mera. Eller så kan du visa ditt kontonummer.

**Så här konfigurerar du dina kontoinställningar**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Account Settings]** på produktmenyn.
1. Ange önskade alternativ på sidan [!DNL Account Settings].

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Webbplatsnamn </p> </td> 
      <td colname="col2"> <p>Obligatoriskt. </p> <p>Ett kort namn som används för att beskriva din webbplats/ditt konto. Det här alternativet är användbart om du har flera webbplatser. </p> <p> <p>Obs!  Du måste kontakta teknisk support för att välja ett eller flera namn som du vill använda. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Webbplatsadress </p> </td> 
      <td colname="col2"> <p>Obligatoriskt. </p> <p>Webbplatsens URL-adress. Adressen som anges här används som startpunkt för webbplatsen. </p> <p>Se även <a href="../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45" type="task" format="dita" scope="local"> Lägga till flera URL-startpunkter som du vill indexera </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tidszon (för rapporter och planering) </p> </td> 
      <td colname="col2"> <p>Den tidszon som används för rapporter och publiceringsåtgärder. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Validera taggattribut för mall vid Spara </p> </td> 
      <td colname="col2"> <p>Validerar alla attribut i <span class="codeph"> &lt;guided-*&gt; </span> och <span class="codeph"> &lt;search-*&gt; </span> när du sparar en mall i redigeraren för mellanlagrad mall. </p> <p>Se <a href="../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3" type="task" format="dita" scope="local"> Redigera en presentation eller en transportmall </a>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Validera mallreferenser till GS-objekt vid Spara </p> </td> 
      <td colname="col2"> <p> Kontrollerar om det finns guidade sökobjekt, t.ex. menyer, ansikten, vägbeskrivningar, anpassade variabler och mallar, som refereras i <span class="codeph"> &lt;guided-*&gt; </span>-taggar. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Tillämpa strikt syntaxkontroll av mallar </p> </td> 
      <td colname="col2"> <p>Gör mallvalideraren mer strikt och aktiverar kontroll av t.ex. obalanserade citattecken och &lt;&gt;-symboler. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Kontonummer </p> </td> 
      <td colname="col2"> <p>Du kan inte redigera kontonumret. Det är endast till för visning. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.

## Konfigurera integrering med Adobe CQ5 {#task_EA2FC2C24960498DAE01A1AB769D2F14}

Du kan konfigurera integreringen av webbplatssökning/-marknadsföring med Adobe CQ5.

**Konfigurera integrering med Adobe CQ5**

1. Hämta ditt medlems-ID och konto-ID genom att göra följande:

   * Logga in på ditt konto för sökning/försäljning av webbplatser.
   * Kopiera medlems-ID och konto-ID i URL-sökvägen.

      Om URL-sökvägen till ditt konto till exempel är `https://searchandpromote.mycompany.com/px/home/?sp_id=00123a4b-sp1234a5b6` är medlems-ID `00123a4b` och konto-ID är `sp1234a5b6`.

1. I Adobe CQ5 använder du fliken Cloud Services för att skapa en webbplatssöknings-/marknadsföringskonfiguration.

   Använd det kopierade medlems-ID:t och konto-ID:t för respektive inställningar.

## Konfigurerar inställningar för marknadsföring {#task_7AC7B9F5D9F44E10AB5BC0B8CB31C37A}

Hantera företagsinställningar som standardregelbyggaren och standardsöktermen.

**Så här konfigurerar du inställningar för marknadsföring**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Merchandising Preferences]** på produktmenyn.
1. Ange önskade alternativ på sidan [!DNL Merchandising Preferences].

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Dominerande tröskelvärde för utlösargrupp </p> </td> 
      <td colname="col2"> <p> Tröskelprocenten som ska användas för resultatbaserade utlösare som är"gruppdominanta" och som anger"använd standardkonto". </p> <p>Om du ändrar den här inställningen kan direktsökningar omedelbart påverkas, och du bör därför vara försiktig. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Gruppdefinition </p> </td> 
      <td colname="col2"> <p>Antal resultat i en grupp för marknadsföringskonsolen. Maximalt är 50 000. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> MDI-fält (Merchandising Document ID) </p> </td> 
      <td colname="col2"> <p> Fältet som du anger måste"göra sökresultaten enhetliga" som du vill ändra med hjälp av resultatbaserade utlösare och åtgärder som baseras på ett resultat. </p> <p>I vissa fall fungerar det fördefinierade URL-fältet, men det rekommenderas inte. Ett användardefinierat metafält med ett unikt ID för varje sida (till exempel SKU eller product_id) skulle vara mycket effektivare än att använda URL-fältet. Om du anger none inaktiveras resultatbaserade utlösare och åtgärder för ett resultat i regelhanteraren. Om du ändrar det här alternativet gäller det endast regler som sparas framåt. befintliga regler fortsätter att använda den MDI som de ursprungligen sparades med. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardsökterm för VRB (Visual Rule Builder) </p> </td> 
      <td colname="col2"> <p> Här kan du anpassa det inledande sökord som används i Visual Rule Builder. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardsökning för VRB </p> </td> 
      <td colname="col2"> <p>Med den här inställningen kan du ange vilken standardsökning som först väljs i Visual Rule Builder. </p> <p> Den här inställningen är endast relevant för implementering med flera sökningar. Med VRB kan du välja vilken sökning som den definierade gruppen ska söka efter. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Timeout för VRB/simulator </p> </td> 
      <td colname="col2"> <p>VRB och simulator skickar sökningar via en proxyserver som är långsammare än din produktionssökning. Under vissa omständigheter, till exempel långsam inläsning av resurser, kan VRB eller simulatorn timeout. Du kan öka eller minska antalet sekunder som användargränssnittet måste vänta innan det stoppas. Du behöver sällan öka den här inställningen från standardvärdet 60. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.

## Konfigurera åtkomst till ditt Dynamic Media Classic-konto i Adobe {#task_CEFF88C2033D41D0B2FE86C435EDAC6D}

Länka söknings-/säljkontot till Adobe Dynamic Media Classic så att du enkelt kan lägga till bannerannonser på webbplatsen med överförda digitala resurser från Adobe Scene7.

Se [Om banners](../c-about-design-menu/c-about-banners.md#concept_5BBE01FEC6134393B43CC917C8CC64DA).

Se [Lägga till en banderoll med Adobe Dynamic Media Classic](../c-about-design-menu/c-about-banners.md#task_AD1E0C00A9E04B1FA819EB93288786B3).

**Så här konfigurerar du åtkomst till ditt Adobe Dynamic Media Classic-konto**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Scene7 Configuration]** på produktmenyn.
1. Ange önskade alternativ på sidan [!DNL Scene7 Configuration].

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Län </p> </td> 
      <td colname="col2"> <p>Obligatoriskt. Identifierar det område i världen där ditt Dynamic Media Classic-konto har åtkomst till de olika Dynamic Media Classic-servrarna. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Standardföretag </p> </td> 
      <td colname="col2"> <p>Identifierar namnet på det företag som är associerat med ditt Dynamic Media Classic-konto. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> E-post </p> </td> 
      <td colname="col2"> <p>Obligatoriskt. Identifierar den e-postadress som används för inloggning och kommunikation i Dynamic Media Classic. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Lösenord </p> </td> 
      <td colname="col2"> <p>Obligatoriskt. Ditt Dynamic Media Classic-inloggningslösenord. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Aktiverad </p> </td> 
      <td colname="col2"> <p>Aktiverar alla Dynamic Media Classic-kontroller för webbplatssökning/försäljning. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Testa </p> </td> 
      <td colname="col2"> <p>Verifierar att namnet, e-postadressen och lösenordet för din Dynamic Media Classic-region är korrekta. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. (Valfritt) Klicka på **[!UICONTROL Test]** för att verifiera att namnet, e-postadressen och lösenordet för din Dynamic Media Classic-region är korrekta.
1. Klicka på **[!UICONTROL Save Changes]**.

## Konfigurerar Adobe Analytics Redirector {#task_2C9DE333FD7246E4A460FC0F55204160}

Om du använder [!DNL Adobe Analytics] för att spåra webbplatsbesökare kan du använda [!DNL Adobe Analytics Redirector] i webbplatssökning/försäljning för att spåra alla HTTP-omdirigeringar med [!DNL Adobe Analytics].

**Konfigurera Adobe Analytics Redirector**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Adobe Analytics Redirector]** på produktmenyn.
1. Ange önskade alternativ på sidan [!DNL Adobe Analytics Redirector].

   <table> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> <p>Alternativ </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Aktivera funktionen Adobe Analytics Redirector </p> </td> 
      <td colname="col2"> <p>Aktiverar spårning av HTTP-omdirigeringar med Adobe Analytics. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Spårningsserver </p> </td> 
      <td colname="col2"> <p> Identifierar namnet på Adobe Analytics-spårningsservern. </p> <p>Om du vill ta reda på spårningsserverns namn </p> <p> 
      <ol id="ol_D17B77E81F8D40D0948415CD60839BE3"> 
      <li id="li_BE58DBA104D44F0DB6C64AD3F12CEA97"> I Adobe Analytics klickar du på <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Admin Console </span> &gt; <span class="uicontrol"> Code Manager </span>. </li> 
      <li id="li_67A93D17C3A14874928C6DC4FF2D4784"> I grupprutan <span class="wintitle"> Alternativ </span> väljer du en rapportserie i respektive listruta. </li> 
      <li id="li_5AAB004AC58441DBB0F813BDE30EFFD4"> Klicka på <span class="uicontrol"> Generera kod </span>. </li> 
      <li id="li_E80368993F4D4DD69E37509FF4348B36"> På sidan <span class="wintitle"> Code Manager </span> klickar du på fliken <span class="uicontrol"> Core Javascript File </span>. </li> 
      <li id="li_991BDCDDA41A445F85CEEAAE9A46A304"> I <span class="wintitle"> Config Section </span> söker du efter raden som ser ut så här: <p> <code> s.trackingServer="yourcompany.122.2o7.net" </code> </p> <p>Spårningsserverns namn är i det här fallet <span class="codeph"> "dincompany.122.2o7.net" </span> </p> </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Report Suite-ID </p> </td> 
      <td colname="col2"> <p> Identifierar ditt rapportsvit-ID. </p> <p>Om du vill ta reda på ditt rapportpaket-ID, </p> <p> 
      <ol id="ol_4FD7B2459358486DBDB130426131D16A"> 
      <li id="li_9AF624CEB128453C808892EEE385D5D1"> I Adobe Analytics klickar du på <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Admin Console </span> &gt; <span class="uicontrol"> Report Suites </span>. </li> 
      <li id="li_AAC47EAA04144A67BDCB5C7B8D8098E9"> Titta på kolumnen <span class="wintitle"> Report Suite Id </span> i tabellen för att hitta ID:t. </li> 
      </ol> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Egna parametrar </p> </td> 
      <td colname="col2"> <p>Gör att du kan lägga till egna parametrar i Adobe Analytics omdirigerings-URL:en. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Ange skiftläget för alla anpassade värden till </p> </td> 
      <td colname="col2"> <p>Gör att du kan standardisera med det hölje som används för alla anpassade parametervärden som du har angett ovan. Adobe Analytics är skiftlägeskänsligt, vilket innebär att det finns en anledning att slå ihop gemener och versaler. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Adobe Analytics Redirector]:

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Konfigurerar rotfiler {#task_5F175C8743FB49A2A003813CBF7C56BF}

Hantera rotfiler i webbplatsens rotmapp.

**Så här konfigurerar du rotfiler**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Root Files]** på produktmenyn.
1. På sidan [!DNL Root Files] bläddrar du till de rotfiler som du vill överföra.

   <table> 
    <thead> 
    <tr> 
      <th colname="col1" class="entry"> <p>Rotfil </p> </th> 
      <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
      <td colname="col1"> <p>favicon.ico </p> </td> 
      <td colname="col2"> <p> Ikonen för webbplatsen. Vanligtvis visas den i adressfältet i kundens webbläsare. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>robots.txt </p> </td> 
      <td colname="col2"> <p>Tillåter eller nekar robotar åtkomst till vissa delar av webbplatsen. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>sitemap.xml </p> </td> 
      <td colname="col2"> <p>XML-filen med en lista över alla sidor som är tillgängliga på webbplatsen. </p> </td> 
    </tr> 
    <tr> 
      <td colname="col1"> <p>crossdomain.xml </p> </td> 
      <td colname="col2"> <p>Tillåter eller nekar Flash Player åtkomst till filer över domäner. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Klicka på **[!UICONTROL Save Changes]**.
1. (Valfritt) Återskapa indexet för den mellanlagrade platsen om du vill förhandsgranska resultatet.

   Se [Konfigurera ett inkrementellt index för en mellanlagrad webbplats](../c-about-index-menu/c-about-incremental-index.md#task_46A367B0786C4C90BFFA5D3F95FD86C0).
1. (Valfritt) Gör något av följande på sidan [!DNL Root Files]:

   * Klicka på **[!UICONTROL Live]**.

      Se [Visa Live-inställningar](../c-about-staging.md#task_401A0EBDB5DB4D4CA933CBA7BECDC10F).

   * Klicka på **[!UICONTROL Push Live]**.

      Se [Publicera sceninställningar live](../c-about-staging.md#task_44306783B4C0408AAA58B471DAF2D9A4).

## Överför kontoägarskap till en annan kontoanvändare {#task_47E3C66CC6374274830DA10171E0CF17}

Om du som kontoägare vill avbryta din inloggning måste du först överföra ägarskapet till en annan aktiv kontoanvändare. Du kan använda [!DNL Transfer Ownership] för att utföra den här uppgiften.

Du kan överföra ägarskap till alla befintliga användare av webbplatsens söknings-/försäljningskonto.

När ägarbytet är slutfört får den nya kontoägaren ett e-postmeddelande och den tidigare ägaren befrias från de begränsningar och ansvarsområden som gäller för den positionen.

Det kan bara finnas en ägare per konto. Om du överför ditt ägarskap till en annan användare har du inte längre äganderätt.

Se [Avbryta inloggningen](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

Se [Ta bort ett konto](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32).

Se [Ta bort dig själv från ett konto](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F).

**Överför kontoägarskap till ett annat konto**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Transfer Ownership]** på produktmenyn.
1. På sidan [!DNL Transfer Ownership] klickar du på den användare som du vill ska bli ägare till ditt konto.
1. Klicka på **[!UICONTROL Transfer]**.

## Tar bort ett konto {#task_975178D5B9444BF8B52D72B897A49C32}

Du kan ta bort ett konto helt och hållet från webbplatssökning/försäljning. När du gör det har du och andra användare av ditt konto inte längre åtkomst till det.

När du tar bort ditt konto kan det inte längre användas för att indexera eller söka på din aktiva webbplats. Dessutom

Om du vill tillåta andra användare att fortsätta använda det här kontot kan du överföra ägarskapet till en annan användare och sedan ta bort dig själv som kontoanvändare.

Se [Överför kontoägarskap till en annan kontoanvändare](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17).

Om du har andra konton kommer du till det första kontot som visas i din inloggning när du har tagit bort det aktuella kontot.

Se [Ta bort dig själv från ett konto](../c-about-settings-menu/c-about-account-options-menu.md#task_C56F5AB87B664BAAAC2FD2F15003E73F).

Se [Avbryta inloggningen](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

**Ta bort ett konto**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Account]** på produktmenyn.
1. (Valfritt) Ange en orsak till att kontot har tagits bort i fältet [!DNL Reason for Removal].
1. Klicka på **[!UICONTROL Remove Account]**.

## Tar bort dig själv från ett konto {#task_C56F5AB87B664BAAAC2FD2F15003E73F}

Du kan ta bort dig själv från ett konto för sökning/försäljning av webbplatser.

När du tar bort dig själv från ett konto kan du inte längre komma åt det och du kan inte redigera kontoinställningar eller indexera din webbplats med det.

Om du vill återfå åtkomst till kontot ber du en aktuell kontoanvändare att återställa dig.

Se [Avbryta inloggningen](../c-about-settings-menu/c-about-my-profile-menu.md#task_D57701BB726243B08CEA14EEC86C3087).

Se [Ta bort ett konto](../c-about-settings-menu/c-about-account-options-menu.md#task_975178D5B9444BF8B52D72B897A49C32).

Se [Överför kontoägarskap till en annan kontoanvändare](../c-about-settings-menu/c-about-account-options-menu.md#task_47E3C66CC6374274830DA10171E0CF17).

**Så här tar du bort dig själv från ett konto**

1. Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Account Options]** > **[!UICONTROL Remove Yourself]** på produktmenyn.
1. Klicka på **[!UICONTROL Remove Yourself]**.
