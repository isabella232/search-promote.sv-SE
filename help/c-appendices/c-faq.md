---
description: Läs vanliga frågor om Search&amp;Promote
solution: Target
title: Frågor och svar
topic: bilagor,Webbplatssökning och -försäljning
uuid: 4ce454a4-e770-4587-91a0-a25491818ac6
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '8648'
ht-degree: 0%

---


# Vanliga frågor och svar{#frequently-asked-questions}

## Adobe Flash {#reference_4A25BBDE32214AF5A1A454F38FD51243}

En sida med vanliga frågor som behandlar stöd för indexering och sökning av SWF-filer på en webbplats.

Nedan följer några vanliga frågor om SWF-filer:

* [När crawlas och indexeras en SWF-fil?](#section_01BB5259140D4D5FB04CCB7A1A63DE99)
* [Vad måste jag göra för att indexera en SWF-fil..](#section_0A6A52CC70D4495BBE14D91906318F95)
* [Hur känns SWF-filer igen?](#section_B36C0536AB544F509601DC6A11A8E656)
* [Hur indexeras SWF-filer?](#section_36856058A4B54FA5ABF921344F50410C)
* [Räknas en SWF-fil som en sida?](#section_0158D6DE70BC40D78E2374787B9F58AB)
* [Hur förhindrar jag indexering av enskilda SWF-filer...](#section_E38AD37989EF410B97AF5125057BFD22)
* [Hur förhindrar jag att SWF-filer indexeras..](#section_DF2606A50E9A44859CFA0D44D7C5F2E4)
* [Hur kommer det sig att jag inte kan söka efter kinesiska, japanska eller koreanska SWF-filer på min webbplats?](#section_EE1A3A705AE74148BD195A0CE513A5C4)

## När crawlas och indexeras en SWF-fil? {#section_01BB5259140D4D5FB04CCB7A1A63DE99}

En SWF-fil crawlas och indexeras om den finns i en embed- eller object-tagg på en HTML-sida, som i följande exempel:

```
<embed src="Flash-file-URL">  
 
<object>  
<param name=movie value="Flash-file-URL">  
</object> 
```

En SWF-fil känns också igen om du listar filens URL som en entrypoint.

Se [Lägga till flera URL-startpunkter som du vill indexera](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Vad måste jag göra för att indexera en SWF-fil? {#section_0A6A52CC70D4495BBE14D91906318F95}

Om du vill crawla och indexera SWF-filer väljer du innehållstypen **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Så länge din Flash-fil refereras från en `<embed>`-tagg eller en `<object>`-tagg i ett HTML-dokument, indexeras texten och alla URL:er som anges i filen crawlas.

Om det inte finns någon referens till filen från någon av taggarna `<embed>` eller `<object>` kan du lista SWF-filen i en `<a href=...>`-tagg i ett HTML-dokument eller som en URL-startpunkt.

Se [Lägga till flera URL-startpunkter som du vill indexera](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Hur känns SWF-filer igen? {#section_B36C0536AB544F509601DC6A11A8E656}

SWF-filer identifieras av följande MIME-typ:

`application/x-shockwave-flash`

SWF-filer känns också igen med MIME-typerna `application/octet-stream` eller `text/plain`, förutsatt att filtillägget är .swf.

En felkonfigurerad server kan använda en annan MIME-typ för SWF-filer. Kontrollera serverkonfigurationen om du har problem med att crawla och indexera SWF-filer.

## Hur indexeras SWF-filer? {#section_36856058A4B54FA5ABF921344F50410C}

Texten i en SWF-fil indexeras som om den var `<body>`-text på den omslutande HTML-sidan. Om ett sökresultat hittar text som finns i en inbäddad SWF-fil länkar resultatet faktiskt till den omslutande HTML-sidan och inte till SWF-filen. På så sätt visas SWF-filen i rätt sammanhang.

Om en SWF-fil innehåller en URL-adress som en&quot;Läs in film&quot;-åtgärd indexeras texten i den refererade SWF-filen som en del av den omslutande HTML-sidan.

Om en SWF-fil innehåller en URL som en Get URL-åtgärd crawlas URL-adressen och indexeras senare, precis som en HTML `<a href=...>`-referens crawlas och indexeras senare.

Om en SWF-fil listas som en URL-startpunkt indexeras SWF-filens text som en enda sida. Ett sökresultat som söker efter text från en startpunkt-SWF-länk direkt till filmen, inte till en omslutande HTML-sida.

Se [Lägga till flera URL-startpunkter som du vill indexera](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Räknas en SWF-fil som en sida? {#section_0158D6DE70BC40D78E2374787B9F58AB}

Nej. En SWF-fil anses vara en del av den omslutande HTML-sidan. Alla&quot;Läs in film&quot;-URL:er som finns i SWF-filer betraktas också som en del av den omslutande HTML-sidan. Därför räknas inte SWF-filer som refereras från en HTML-sida som en&quot;sida&quot; för kontots sidsumma.

Om en SWF-fil listas som en URL-startpunkt räknas den SWF-filen och alla Load Movie-URL:er som listas i den SWF-filen som en&quot;sida&quot; för kontots sidsumma.

## Hur förhindrar jag indexering av enskilda SWF-filer? {#section_E38AD37989EF410B97AF5125057BFD22}

Om du vill förhindra indexering av en SWF-fil kan du lägga till en meta-tagg ( `<meta name="ROBOTS" content="NOINDEX">`) eller en `<noindex>`-tagg i det omslutande HTML-dokumentet. Det vill säga det dokument som innehåller taggen `<embed>` eller `<object>`.

Du kan också använda meta-taggen för robotar ( `<meta name="ROBOTS" content="NOFOLLOW">`) för att förhindra följande URL:er som finns i SWF-filen. Om det omslutande HTML-dokumentet har inaktiverats följs inte de URL:er som anges som Hämta URL-åtgärder i SWF-filen.

## Hur förhindrar jag att SWF-filer indexeras på min webbplats? {#section_DF2606A50E9A44859CFA0D44D7C5F2E4}

Om du vill inaktivera SWF-indexering avmarkerar du innehållstypen **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Du kan också välja att använda [!DNL URL Masks] för att inaktivera indexering av SWF-filer.

Se [Lägga till URL-masker till index eller inte indexdelar av..](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Om du vill inaktivera SWF-indexering anger du en av följande URL-masker:

* `exclude *.swf` (om du inte använder reguljära uttryck)
* `exclude regexp ^.*\.swf$` (om du använder reguljära uttryck)

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Hur kommer det sig att jag inte kan söka efter kinesiska, japanska eller koreanska SWF-filer på min webbplats? {#section_EE1A3A705AE74148BD195A0CE513A5C4}

Webbplatssökning/varuexponering hämtar UTF-8 från SWF-filer som skapats med Adobe Flash. UTF-8 innehåller ingen språkindikation. Om du valde innehållstypen **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange vilket språk som ska användas i SWF-filen.

Se [Lägga till fältinjektionsdefinitioner](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

Äldre SWF-filer anger inte heller någon teckenuppsättning. Om du valde SWF-innehållstypen **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange teckenuppsättningen som används i SWF-filen.

## Allmän sökning {#reference_E2C675162789452A9B99C6633B12CBEF}

En sida med vanliga frågor som handlar om hur webbplatssökning/försäljning hjälper kunder som besöker din webbplats att hitta det de letar efter.

Nedan följer några vanliga frågor om allmän sökning:

* [Måste jag installera någon programvara för att kunna använda webbplatsen..](#section_02AB2AFF71984F9DAA3AF2B7C0847A22)
* [Vad händer när min webbplats överskrider sidgränsen?](#section_ECA5FA01032D4322BABA4E2C7FE498C1)
* [Hur ändrar jag e-postadressen där varje vecka..](#section_AE27F63DD13F425B940C8E7D9ED5C614)
* [Hur säker är min kundinformation om webbplatssökning/försäljning?](#section_5484CB954167412BB7F0480CB0C504B8)
* [Hur är sekretessen för mina kunduppgifter?](#section_8FB493F15E51454BA92A0C83E14C0CC7)
* [Får jag visa mina egna banners på sökningen..](#section_611EB8B32C16418386CB7DC7FB6954B8)

Nedan följer några vanliga frågor om sökfunktioner:

* [Kan jag anpassa sökresultaten för min webbplats?](#section_A64B3A621B794DF78D35ED06D9C43D0B)
* [Kan jag se vad kunderna letar efter på min...](#section_73709E1B0E82478DA7B4D15B6C845F33)
* [Hur styr jag vilka innehållstyper (PDF, text, Flash, MP3 och Microsoft Office) som indexeras och söks igenom?](#section_0AB8CB4B6BFA4286AA082055FEBFBE1C)
* [Stöds dynamiskt genererade webbsidor med ASP-, JSP-, PHP-, CFM- eller Perl-baserat innehåll?](#section_E279F004F1C542A2B9773B832E7B013F)
* [Hur kan jag använda synonymer för att förbättra sökresultaten..](#section_E6E36E12514F4D7BAB01F8D1AB61D57B)
* [Har jag kontroll över ordningen på sökresultaten..](#section_C6361048502745779D9749A842C4C370)
* [Kan jag ändra språk på sökresultatsidan..](#section_6EE41DA8241247D48BBEB061A50599C5)
* [Kan jag ha mer än en sajt på Adobe?](#section_AFA8825182094660A71EEC84B8329D6D)
* [Kan jag söka i fler än en domän?](#section_BFBB0E9861D942F095B56CF0A8F16596)
* [Kan jag dela upp min webbplats i separata avsnitt så att...](#section_52153A9DE9F9493B967A70583848B2A4)
* [Hur utesluter jag delar av min webbplats från att vara ...](#section_D452EDE153654EF398F4A87780C6D43B)
* [Vilka teckenuppsättningar stöds?](#section_A62A6F8F15804F968C77F2DEBDE8F8FD)
* [Vad händer om jag ändrar eller uppdaterar min webbplats?](#section_489050E0EBC14D0594DBBAA0CCF4F6BA)
* [Kan min webbplats indexeras automatiskt?](#section_9C7D41636238488691ECDFEE4D4E5103)
* [Jag använder lösenord på min webbplats. Kan jag fortfarande använda webbplatssökning/försäljning?](#section_4618EB5B66704640B5502D1B5CB4B32E)
* [Stöder du crawlning och indexering av https eller...](#section_D5BB8B8FBEA4405583E86B4AEC37151B)
* [Uppfyller webbplatssökning/försäljning filen robots.txt på min webbplats?](#section_73BBF6FE93C64C109F45CBC2FA394DB2)
* [Vissa delar av min webbplats måste uppdateras ofta, så..](#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3)
* [Kan jag använda skript eller program för att initiera en stegvis..](#section_0B6BB039557A42AA876D35D748E17DD0)

## Måste jag installera någon programvara för att kunna använda webbplatssökning/försäljning? {#section_02AB2AFF71984F9DAA3AF2B7C0847A22}

Nej. Detta är den främsta fördelen med webbplatssökning/försäljning. Motorn är en professionell applikation som helt och hållet är värd för våra högpresterande servrar. Detta gör programmet enklare att använda än andra söklösningar. Det enda du behöver göra är att lägga till en liten mängd HTML-kod på sidorna så att kunderna på webbplatsen kan göra sökningar. Webbplatssökning/-marknadsföring tar hand om resten.

## Vad händer när min webbplats överskrider sidgränsen? {#section_ECA5FA01032D4322BABA4E2C7FE498C1}

Vi fortsätter att söka så att besökarna kan söka på webbplatsen utan avbrott. Om du vill se om webbplatsen överskrider sidgränsen granskar du statusen Fullständigt index eller Live-logg.

Se [Om fullständigt index](../c-about-index-menu/c-about-full-index.md#concept_C69BD21863FD4856B49326F35DB570D3).

Se [Visa den fullständiga indexloggen för en live eller staged..](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

## Hur ändrar jag e-postadressen dit veckorapporterna skickas? {#section_AE27F63DD13F425B940C8E7D9ED5C614}

Veckorapporter skickas till ägaren av varje aktivt konto. Du kan ändra e-postadressen genom att klicka på **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**. Om du har fler än ett aktivt sökkonto skickas alla nyhetsbrev till den nya adressen.

Se [Konfigurera din personliga användarinformation](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

## Hur säker är min kundinformation om webbplatssökning/försäljning? {#section_5484CB954167412BB7F0480CB0C504B8}

Sökning/försäljning av webbplatser är säkert, snabbt, stabilt och enkelt att använda. Du behöver inte använda cookies (även om du kan om du vill) för att använda våra produkter, och känslig information, som lösenord, läggs aldrig på någon URL-länk som senare kan hämtas från din webbläsare.

## Hur är sekretessen för mina kunduppgifter? {#section_8FB493F15E51454BA92A0C83E14C0CC7}

Adobe värnar om sina kunders och besökares integritet. Se Adobe [Sekretesscenter](https://www.adobe.com/privacy.html).

## Kan jag visa mina egna banners på sökresultatsidorna? {#section_611EB8B32C16418386CB7DC7FB6954B8}

Ja. Du styr utseendet och innehållet i sökresultaten. I webbplatsens sökresultatmall kan du skapa länkar till ditt eget nätverk för bannerutbyte, som LinkExchange eller SmartClicks. Alla träffar som besökarna gör krediteras ert bannerbörskonto.

## Kan jag anpassa sökresultaten för min webbplats? {#section_A64B3A621B794DF78D35ED06D9C43D0B}

Ja. Detta är en unik egenskap av webbplatssökning/försäljning. Med vår avancerade mallteknik och lite kunskap om HTML kan du styra exakt hur sökresultaten visas.

Se [Sök efter malltaggar](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Övergången mellan era egna servrar och söknings-/försäljningsservrar för webbplatser är helt sömlös och osynlig för era kunder. Om du inte känner till HTML eller inte har tid att skapa en anpassad mall kan du välja bland en mängd tilltalande färdiga mallar som Adobe interna webbutvecklarteam skapar.

## Kan jag se vad kunderna letar efter på min webbplats? {#section_73709E1B0E82478DA7B4D15B6C845F33}

Ja. Vi har sökstatistik över sökningar som besökare gjort på din webbplats under de senaste två månaderna. Du kan när som helst granska statistiken under Rapporter på produktmenyn. Sökrapporter ger dig viktig information om exakt vad besökarna letar efter på din webbplats. Du kan använda den här informationen för att förbättra designen eller för att trimma söknings-/försäljningsmotorn för webbplatser så att de bättre kan hjälpa besökarna.

## Hur styr jag vilka innehållstyper (PDF, text, Flash, MP3 och Microsoft Office) som indexeras och söks igenom? {#section_0AB8CB4B6BFA4286AA082055FEBFBE1C}

Du kan enkelt konfigurera konton för att aktivera eller inaktivera indexering och sökning av text som finns i PDF-dokument, oformaterade textdokument, Flash-filmer, MP3-filer eller Microsoft Office-dokument.

De här inställningarna styrs på sidan [!DNL Staged Content Types].

Se [Om innehållstyper](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Stöds dynamiskt genererade webbsidor med ASP-, JSP-, PHP-, CFM- eller Perl-baserat innehåll? {#section_E279F004F1C542A2B9773B832E7B013F}

Statiska eller dynamiskt genererade HTML-webbsidor indexeras, inklusive sidor som skapats från databaser eller någon annan back-end-process. Eftersom HTML-koden som webbläsaren ser är indexerad kan du använda webbplatssökning/försäljning på webbplatser så länge som dessa serverarkitekturer leder till HTML-sidor.

Sökroboten crawlar webbplatsen genom att börja med den första sidan på den webbplatsadress som anges i [!DNL Account Settings] och följer länkar från sida till sida.

Se [Konfigurera dina kontoinställningar](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

När sökroboten crawlar och indexerar alla sidor på webbplatsen kan du använda sökmotorn för att söka efter webbplatsen. Med andra ord: om dynamiskt genererade dokument vävs in på webbplatsen med länkar från andra sidor kan sökroboten fortfarande crawla och indexera det dynamiska innehållet.

När webbplatsinnehållet har crawlats och indexerats kan kunder till webbplatsen söka efter information i det indexerade innehållet.

## Hur kan jag använda synonymer för att förbättra sökresultaten för min webbplats? {#section_E6E36E12514F4D7BAB01F8D1AB61D57B}

Du kan använda synonymer när du vill att besökarna ska hitta sidor som är relaterade till sökfrågan.

Anta till exempel att du har en sida som innehåller en prislista över produkter som ska säljas på webbplatsen. När du har undersökt de sökrapporter som tillhandahålls av webbplatssökningar/-marknadsföring ser du att kunderna letar efter ordet&quot;kostnad&quot;,&quot;kostnad&quot;,&quot;avgift&quot; eller&quot;avgift&quot; i sina sökningar. De här orden visar inte din prislistsida i sökresultaten. Med funktionen [!DNL Add Synonyms] i [!DNL Dictionaries] kan du ange att alla dessa ord är synonymer, och kunden kan hitta din prislista oavsett vilket sökord de använder.

Se [Om ordlistor](../c-about-linguistics-menu/c-about-dictionaries.md#concept_B8028B71EC8144669614C64578EDB034).

## Har jag kontroll över ordningen på sökresultaten? {#section_C6361048502745779D9749A842C4C370}

Ja. Med det avancerade relevansgränssnittet kan du styra vilka sidor som returneras för en viss sökfråga. Den här funktionen är användbar om du vill vara säker på att kunderna ser en viss sida när de frågar efter vissa ord.

Se [Lägga till ett nytt metataggsfält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Kan jag ändra språk på sökresultatsidan? {#section_6EE41DA8241247D48BBEB061A50599C5}

Ja. Mallen för webbplatssökning/försäljning är flexibel när det gäller att du ska kunna skapa en resultatsida som har det språk du väljer och som matchar utseendet på webbplatsen.

Mallen består av en kombination av text, vanliga HTML-taggar och specialtaggar som är definierade för att visa sökresultaten. När en kund utför en sökning läser sökroboten mallen, matar ut texten med vanliga HTML-taggar och infogar resultatlänkarna baserat på de särskilda malltaggarna.

Se [Sök efter malltaggar](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

Om du vill ändra resultatspråket kan du redigera den engelska texten som visas i mallen.

Se [Redigera en presentation eller en transportmall](../c-about-design-menu/c-about-templates.md#task_800E0E2265C34C028C92FEB5A1243EC3).

## Kan jag ha fler än en plats på Adobe kundinloggningen? {#section_AFA8825182094660A71EEC84B8329D6D}

Ja. Med en och samma Adobe kundinloggning kan ni hantera en annan sökmotor för många olika webbplatser. Välj och hantera konton under Konton.

Se [Välja ett annat konto att använda](../c-about-accounts-menu.md#task_03C0FE918E2D44529CDC3B8DB75D1B26).

## Kan jag söka i fler än en domän? {#section_BFBB0E9861D942F095B56CF0A8F16596}

Ja. Du kan konfigurera åtkomst till mer än en domän genom att använda [!DNL URL Entrypoints]. Ange URL-startpunkter för ytterligare domäner som du äger. Kom ihåg att du måste ha behörighet att indexera domäner som du inte äger.

Se [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Kan jag dela upp min webbplats i separata avsnitt så att kunderna kan söka i dessa områden individuellt eller på hela webbplatsen? {#section_52153A9DE9F9493B967A70583848B2A4}

Ja. Funktionen&quot;Samlingar&quot; ingår, som gör att kunderna kan söka efter specifika delar av webbplatsen för att snabbt hitta det de letar efter.

Se [Om samlingar](../c-about-settings-menu/c-about-searching-menu.md#concept_62E42ACE53D54EEE9273433B86259127).

Kunder kan till exempel söka efter en samling URL:er som är relaterade till produktförsäljningsinformation eller en samling URL:er som är kopplade till supporttjänster. Du kan konfigurera samlingar så att dina kunder ser en nedrullningsbar lista med samlingar eller en grupp kryssrutor.

## Hur förhindrar jag att delar av min webbplats genomsöks? {#section_D452EDE153654EF398F4A87780C6D43B}

Ja. Ange URL-masker för att avgöra vilka webbsidor som du vill inkludera eller exkludera från indexering. URL-masker avgör om webbsidor visas i sökresultatet.

Se [Om URL-masker](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Se [Om URL-maskskript](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

Om du vill förhindra att delar av enskilda webbsidor genomsöks kan du utesluta delar av en sida från indexeringen. Omge texten med `<noindex>`- och `</noindex>`-taggar. Den här metoden är användbar om du vill utesluta navigeringstext från sökningar.

## Vilka teckenuppsättningar stöds? {#section_A62A6F8F15804F968C77F2DEBDE8F8FD}

På webbsidor anges vanligtvis teckenuppsättningen med en meta-tagg som liknar följande:

`<META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=iso-8859-1">`

Webbplatssöknings-/försäljningsmotorn indexerar webbsidor korrekt med alla vanliga teckenuppsättningar som används på Internet idag. Följande teckenuppsättningar stöds:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Arabiska (ISO-8859-6) </p> </td> 
   <td colname="col2"> <p>Kinesiska (traditionell) Big5) </p> </td> 
   <td colname="col3"> <p>Japanska (Shift_JIS) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Arabiska (Windows-1256) </p> </td> 
   <td colname="col2"> <p>Kinesiska (traditionell) EUC-TW) </p> </td> 
   <td colname="col3"> <p>Ryska (KOI8-R) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baltisk (ISO-8859-4) </p> </td> 
   <td colname="col2"> <p>Kyrilliska (ISO-8859-5) </p> </td> 
   <td colname="col3"> <p>Southern European (ISO-8859-3) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Baltisk (Windows-1257) </p> </td> 
   <td colname="col2"> <p>Kyrilliska (Windows-1251) </p> </td> 
   <td colname="col3"> <p>Turkiska (ISO-8859-9) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centraleuropeisk (ISO-8859-2) </p> </td> 
   <td colname="col2"> <p>Grekiska (ISO-8859-7) </p> </td> 
   <td colname="col3"> <p>Turkiska (Windows-1254) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Centraleuropeisk (Windows-1250) </p> </td> 
   <td colname="col2"> <p>Grekiska (Windows-1253) </p> </td> 
   <td colname="col3"> <p>Unicode (UTF-8) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (ISO-2022-CN) </p> </td> 
   <td colname="col2"> <p>Hebreiska (ISO-8859-8) </p> </td> 
   <td colname="col3"> <p>US-ASCII (us-ascii) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (ISO-2022-CN-EXT) </p> </td> 
   <td colname="col2"> <p>Hebreiska (Windows-1255) </p> </td> 
   <td colname="col3"> <p>Västeuropeisk (ISO-8859-1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (förenklad) EUC-CN) </p> </td> 
   <td colname="col2"> <p>Japanska (EUC-JP) </p> </td> 
   <td colname="col3"> <p>Västeuropeisk (ISO-8859-15) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (förenklad) GB2312) </p> </td> 
   <td colname="col2"> <p>Japanska (ISO-2022-JP) </p> </td> 
   <td colname="col3"> <p>Västeuropeisk (Windows-1252) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (förenklad) GBK) </p> </td> 
   <td colname="col2"> <p>Japanska (ISO-2022-JP-1) </p> </td> 
   <td colname="col3"> <p>Västeuropeisk (x-mac-roman) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kinesiska (förenklad) HZ-GB-2312) </p> </td> 
   <td colname="col2"> <p>Japanska (ISO-2022-JP-2) </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Kontakta teknisk support om du vill fråga om teckenuppsättningar som inte finns med i listan ovan.

## Vad händer om jag ändrar eller uppdaterar min webbplats? {#section_489050E0EBC14D0594DBBAA0CCF4F6BA}

När du har ändrat innehållet på webbplatsen kan du antingen utföra ett fullständigt index eller ett inkrementellt index. Webbplatssökning/försäljning hämtar och indexerar ändrat webbplatsinnehåll. När indexeringen är klar kan kunderna söka i det nya innehållet. Du kan också schemalägga en automatisk indexering av webbplatsen vid en viss tidpunkt och på en viss dag.

Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

Se [Ange fullständigt indexschema för en aktiv webbplats](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

Se [Ställa in inkrementellt indexschema för en aktiv webbplats](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Kan min webbplats indexeras automatiskt? {#section_9C7D41636238488691ECDFEE4D4E5103}

Ja. Du kan schemalägga ett automatiskt index för din webbplats varje dag.

Förutom automatisk indexering kan du välja att ändra delar av webbplatsen stegvis. På dagar när du har ett automatiskt index schemalagt kan du styra tidpunkten på dagen då indexet ska äga rum. Du kan också alltid initiera ett platsindex manuellt när du vill.

Se [Ange fullständigt indexschema för en aktiv webbplats](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0).

Se [Ställa in inkrementellt indexschema för en aktiv webbplats](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Jag använder lösenord på min webbplats. Kan jag fortfarande använda webbplatssökning/försäljning? {#section_4618EB5B66704640B5502D1B5CB4B32E}

Om du använder HTTP Basic Authentication för att lösenordsskydda vissa delar av webbplatsen kan du ange de sfärer och lösenord som webbplatsens sökning/försäljning kan använda för att indexera webbplatsen.

Se [Lägga till lösenord för att komma åt områden på webbplatsen som kräver ...](../c-about-settings-menu/c-about-crawling-menu.md#task_DED19D476FF04B48BB6456D5ECB8628A).

## Stöder du crawlning och indexering av https eller säkert serverinnehåll? {#section_D5BB8B8FBEA4405583E86B4AEC37151B}

Ja. Du kan crawla och indexera innehåll på säkra servrar (https).

## Uppfyller webbplatssökning/försäljning filen robots.txt på min webbplats? {#section_73BBF6FE93C64C109F45CBC2FA394DB2}

Ja. Protokollet för uteslutning av rotcertifikat är kompatibelt. Sökroboten undersöker filen robots.txt om den finns på webbplatsen. Om filen robots.txt utesluter alla robotar från att crawla webbplatsen, exkluderas även söknings-/försäljningsroboten för webbplatsen. Om du bara vill tillåta söknings-/försäljningsroboten att crawla webbplatsen anger du följande innehåll i filen robots.txt:

```
User-agent: Atomz/1.0 
Disallow:
```

```
User-agent: * 
Disallow: /
```

Du kan läsa mer om webrobotar och Robots Exclusion Protocol här:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

## Vissa delar av min webbplats måste uppdateras ofta så att mina kunder får de mest korrekta sökresultaten. Hjälper inkrementell indexering till detta problem? {#section_6D2FB1DE1B8A49729F9CCAE2A2770AB3}

Ja. Det här scenariot är vad funktionen för inkrementell indexering har byggts för att underlätta sökning och försäljning av webbplatser. Den främsta fördelen med inkrementell indexering är att den gör det möjligt för företag att ofta indexera dynamiskt ändrade delar av sin webbplats. Den här funktionen gör att du kan visa sökresultat med exakt rätt resultat.

Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

Se [Ställa in inkrementellt indexschema för en aktiv webbplats](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

## Stöds dynamiskt genererade webbsidor från en backend-databas, till exempel produktkataloger eller lagerhanteringssystem? {#section_26896C556483457E879785E751583B16}

Statiska eller dynamiskt genererade HTML-webbsidor, inklusive sidor som byggts från databaser eller andra back end-processer, indexeras. Eftersom HTML-koden, som den visas av en webbläsare, är indexerad, kan du använda webbplatssökning/försäljning på webbplatser så länge som backend-databasinformationen resulterar i HTML-sidor.

Sökroboten crawlar webbplatsen genom att börja med den första sidan på den webbplatsadress som anges i [!DNL Account Settings] och följer länkar från sida till sida.

Se [Konfigurera dina kontoinställningar](../c-about-settings-menu/c-about-account-options-menu.md#task_80A38D0C8E4F453395BD67B81E4B45D9).

När sökroboten crawlar och indexerar alla sidor på webbplatsen kan du använda sökmotorn för att söka efter webbplatsen. Om dynamiskt genererade dokument med länkar från andra sidor till din webbplats med andra ord kan sökroboten fortfarande crawla och indexera det dynamiska databasinnehållet.

När webbplatsinnehållet har crawlats och indexerats kan kunder till webbplatsen söka efter information i det indexerade innehållet.

Du kan enkelt aktivera sökning efter fullständigt innehåll eller en mer smal ämnesbaserad sökning som är begränsad till information i titeln, metabeskrivningen, dokumenttaggar för meta-nyckelord eller alla tre. Med metadatadefinitioner kan du även skapa anpassade visningsfält, t.ex. en produktbild, i de faktiska sökresultaten.

Se [Lägga till ett nytt metataggsfält](../c-about-settings-menu/c-about-metadata-menu.md#task_6DF188C0FC7F4831A4444CA9AFA615E5).

## Kan jag använda skript eller program för att initiera ett inkrementellt index för min webbplats? {#section_0B6BB039557A42AA876D35D748E17DD0}

Ja. Du kan använda skript eller program för att initiera ett inkrementellt index för din webbplats, samt för att pinga servrarna att indexera platsen när innehållet ändras eller uppdateras.

Se [Om skriptat index](../c-about-index-menu/c-about-scripted-index.md#concept_34F58D551BC04BFB8ADC294B9DA9199D).

## Funktionsimplementeringar {#reference_2D0C4A80B8D64051BA9694D562DCE663}

En sida med vanliga frågor som behandlar olika funktionsimplementeringar i [!DNL Search&Promote].

Följande är vanliga frågor om funktionsimplementeringar i [!DNL Search&Promote] på en webbplats:

* [Varför fungerar inte mina affärsregler?](#section_7FEB60383D8A4B11A60DFF9067274699)
* [Varför har jag problem med att schemalägga indexering, fel vid start av indexering och problem med att starta mellanlagrad indexering?](#section_E05758193DF5436784B0145839989F75)
* [Min indexstorleksgräns överskrider min tillåtna gräns. Varför händer detta och hur åtgärdar jag det?](#section_12E7DA979C4C4B1D8A3A6415FC3DDA70)

## Varför fungerar inte mina affärsregler? {#section_7FEB60383D8A4B11A60DFF9067274699}

Konfigurera affärsregler när banners visas, eller för att hjälpa till att avgöra vilka resultat som visas och i vilken ordning. Du kan också konfigurera positionen för ett objekt i din profil och vilken mall som används för en viss sökning.
Ändra ordning på affärsreglerna om du vill ändra i vilken ordning de körs på presentationsmallar. Affärsreglerna körs i den ordning de har definierats. dvs. ju högre ordningsnummer en regel har, desto senare körs den i processen, och tidigare regler trumpetas. Du ändrar ordning på reglerna genom att ange ett nytt nummer i kolumnen Ordning i tabellen på sidan Affärsregler.

Se [Om affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Varför har jag problem med att schemalägga indexering, fel vid start av indexering och problem med att starta mellanlagrad indexering? {#section_E05758193DF5436784B0145839989F75}

När du genererar ett index, oavsett om det är fullständigt eller inkrementellt, visas statusinformation för indexcrawlning i realtid. Du kan t.ex. visa starttiden, förfluten tid och eventuella fel som uppstått under indexeringsprocessen. Information om status för det senaste indexet visas också. Använd den här informationen för att felsöka eventuella indexeringsfel som du stöter på.

Information om schemaläggning av ett index finns i [Ställa in det fullständiga indexschemat för en aktiv webbplats](../c-about-index-menu/c-about-full-index.md#task_6760F3256D004A228B38968DF15421F0) och [Ställa in det inkrementella indexschemat för en aktiv webbplats](../c-about-index-menu/c-about-incremental-index.md#task_2A46BA189ECC4317A9D5C6E99A336F33).

Information om hur du startar ett mellanlagrat index finns i [Köra ett fullständigt index för en live eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D) eller [Kör ett inkrementellt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Min indexstorleksgräns överskrider min tillåtna gräns. Varför händer detta och hur lagar jag det? {#section_12E7DA979C4C4B1D8A3A6415FC3DDA70}

En webbplats kan få en tendens att växa och med tiden kommer Search &amp; Promote att upptäcka fler dokument och webbsidor som lagts till. I så fall kan ditt konto överskrida din indexeringsstorleksgräns. I sådana fall kan du använda **[!UICONTROL URL Mask]**. Den här funktionen döljer dokument och webbsidor från crawlning av index som du inte vill ha eller inte behöver indexera, vilket minskar indexstorleken. Ett annat alternativ kan vara att kontakta teknisk support så att gränsen för indexeringsstorleken blir större på ditt konto.

Se [Om URL-masker](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Om du är osäker på vad du ska göra bör du kontakta teknisk support. Det kan finnas många andra variabler som påverkar indexstorleken och som, om de justeras, även kan påverka faktureringen av ditt konto.

## Internationell {#reference_F017C2968BFB446499EF1D3CE2CAC0FE}

En sida med vanliga frågor som behandlar stöd för indexering och sökning på mer än 19 språk, inklusive asiatiska flerbyte-språk som kinesiska (förenklad och traditionell), japanska och koreanska.

Nedan följer några vanliga frågor om språk och teckenuppsättningar:

* [Detta styr teckenuppsättningens kodning för sökfrågan...](#section_DF2E8570AFC2480FA199FD26C941A22F)
* [Söks bara sidor vars kodning matchar kodningen för...](#section_9E544F3DB7DE41618DC1BC8224B32C5A)
* [Vilken kodning används för sökresultatsidan?](#section_DA68670F35D54EAABF7DBB010F4409BF)
* [Kan jag använda webbplatssökning/försäljning på Unicode-, UTF-8- och kodade sidor?](#section_130997CB08934A13A5261D85CF88040C)
* [Hur kommer det sig att jag inte kan söka i de kinesiska, japanska eller koreanska PDF-filerna på min webbplats?](#section_539AFF482F814D28B5929F683D2F2175)
* [Hur kommer det sig att jag inte kan söka efter kinesiska, japanska eller koreanska SWF-filer på min webbplats?](#section_9C0849528AFF4C10AA97A2C912992638)
* [Hur kommer det sig att jag inte kan söka efter kinesiska, japanska eller koreanska Microsoft Office-filer på min webbplats?](#section_6764BA6863AF492EBA9BE5CCC12CDD1F)
* [Hur kommer det sig att jag inte kan söka efter kinesiska, japanska eller koreanska MP3-filer på min webbplats?](#section_DB6D60CF46F94125BF4E54AF3036DBFC)
* [Behöver jag göra något speciellt för att få..](#section_A8BA6DDD3A6048319D3530BCFD6DA1A5)
* [Hur kommer kinesiska, japanska eller koreanska teckensnitt att visas i sökresultat under Netscape 4.7 och tidigare?](#section_DF42567063304F918D406AC76529DFB7)

## Vilken styr teckenuppsättningens kodning för sökfrågan? {#section_DF2E8570AFC2480FA199FD26C941A22F}

Avsnittet &quot;Webbformulär&quot; i ditt sökkonto innehåller exempelsökformulär som du använder för att lägga till sökfunktioner på webbplatsen. Om du tittar på den här koden för sökformulär kan du hitta en rad som ser ut ungefär så här:

`<input type=hidden name="sp_f" value="iso-8859-1">`

Den här kodraden talar om för sökmotorn att den inkommande frågan är kodad i iso-8859-1, en vanlig kodning för västeuropeiska språk. Du kan ändra den här inställningen genom att gå till produktmenyn och klicka på **[!UICONTROL Settings]** > **[!UICONTROL My Profile]** > **[!UICONTROL Personal Information]**. Välj en ny kodning i listrutan **[!UICONTROL Character Encoding]** på sidan [!DNL Personal Information].

Se [Konfigurera din personliga användarinformation](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Du kan också ändra kodningsvärdet på dina webbsidor manuellt genom att redigera `sp_f`-raden i sökformuläret. Kom ihåg att sökformulärets `sp_f`-värde måste matcha teckenuppsättningens kodning för sidan där det visas.

## Söks bara sidor vars kodning matchar kodningen i sökfrågan? {#section_9E544F3DB7DE41618DC1BC8224B32C5A}

Nej som standard. Så länge webbplatsens sidor korrekt identifierar sin teckenuppsättningskodning, görs nödvändiga konverteringar mellan kodningen av sökfrågan och kodningen av sidorna, även när sidorna använder flera kodningar.

## Vilken kodning används för sökresultatsidan? {#section_DA68670F35D54EAABF7DBB010F4409BF}

Teckenuppsättningskoden för ditt konto avgör standardkodningen för din resultatmall.

Se [Konfigurera din personliga användarinformation](../c-about-settings-menu/c-about-my-profile-menu.md#task_A11A3BE2527B4204B896E04303B04AA6).

Du kan lära dig mer om hur du anger en teckenuppsättning i en HTML-mall.

Se [Sök efter malltaggar](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## Kan jag använda webbplatssökning/försäljning på Unicode-, UTF-8- och kodade sidor? {#section_130997CB08934A13A5261D85CF88040C}

Ja. Unicode-teckenuppsättningar, t.ex. UTF-8, ger dock inte tillräcklig information för att avgöra vilket språk sidorna skrivs i. Om du vill söka rätt på dessa sidor måste du ange språket. Information om dokumentspråket behandlas i följande ordning:

* HTTP-huvud för Content-Language som servern skickar för dokumentet.
* META-element (till exempel `META HTTP-EQUIV="Content-Language" Content="ja_JP"`) i avsnittet `<HEAD>` i dokumentet.

* LANG-attribut för taggen `<HTML>` (till exempel `<HTML LANG="ja_JP">`).

Om servern inte är konfigurerad att leverera HTTP-huvudet för Content-Language och dina dokument varken innehåller META-elementet för språk eller språkattributet för taggen `<HTML>` kan du använda metadatainjektioner för att ange rätt språk.

Se [Lägga till fältinjektionsdefinitioner](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Hur kommer det sig att jag inte kan söka i de kinesiska, japanska eller koreanska PDF-filerna på min webbplats? {#section_539AFF482F814D28B5929F683D2F2175}

Webbplatssökning/-varuexponering hämtar UTF-8 från Adobe PDF-filer utan språkindikation. Om du valde **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange vilket språk som ska användas i PDF-filen.

Se [Lägga till fältinjektionsdefinitioner](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Hur kommer det sig att jag inte kan söka efter kinesiska, japanska eller koreanska SWF-filer på min webbplats? {#section_9C0849528AFF4C10AA97A2C912992638}

Webbplatssökning/varuexponering hämtar UTF-8 från filmfiler från Adobe Flash som skapats med Adobe Flash utan språkindikering. Om du valde innehållstypen **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange vilket språk som ska användas i SWF-filen.

För Flash version 4 eller tidigare av SWF-filer anges inte teckenuppsättningen för tecknen i filen. Om du valde innehållstypen **[!UICONTROL Adobe Flash Movies]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange teckenuppsättningen som används i SWF-filen.

Se [Lägga till fältinjektionsdefinitioner](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Hur kommer det sig att jag inte kan söka efter kinesiska, japanska eller koreanska Microsoft Office-filer på min webbplats? {#section_6764BA6863AF492EBA9BE5CCC12CDD1F}

Webbplatssökning/-varuexponering hämtar UTF-8 från Microsoft Office-filer (Microsoft Word, Microsoft Excel och Microsoft PowerPoint) utan språkindikering. Om du valde innehållstypen **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange vilket språk som ska användas i Microsoft Office-filerna.

Se [Lägga till fältinjektionsdefinitioner](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Hur kommer det sig att jag inte kan söka efter kinesiska, japanska eller koreanska MP3-filer på min webbplats? {#section_DB6D60CF46F94125BF4E54AF3036DBFC}

Om du väljer innehållstypen **[!UICONTROL Text in MP3 Music Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange den teckenuppsättning som ska användas för att koda MP3-filerna.

Se [Lägga till fältinjektionsdefinitioner](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Behöver jag göra något särskilt för att .txt-filerna på min webbplats ska indexeras korrekt? {#section_A8BA6DDD3A6048319D3530BCFD6DA1A5}

Om du valde innehållstypen **[!UICONTROL Text Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange teckenuppsättningen som används för att koda TXT-filerna.

Se [Lägga till fältinjektionsdefinitioner](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## Hur kommer kinesiska, japanska eller koreanska teckensnitt att visas i sökresultat under Netscape 4.7 och tidigare? {#section_DF42567063304F918D406AC76529DFB7}

Om ditt konto använder standardmallen, en av de färdiga mallarna eller en mall som är baserad på någon av dessa mallar, kan den innehålla teckensnittstaggar som anger Arial eller Helvetica som teckensnittsytor. Exempel, `<font face="arial, helvetica" size="+1">`. Netscape 4.7 och tidigare visar inte kinesiska, japanska eller koreanska tecken när teckensnittet Arial eller Helvetica används. Ta bort attributet `face` eller ersätt teckensnittet med ett som passar bättre för kinesiska, japanska eller koreanska.

## Lågt antal sidor {#reference_4344E3E3CB2948939860F8C078BD7773}

En sida med vanliga frågor som behandlar vanliga problem som är kopplade till ett lågt antal indexsidor.

Nedan följer några vanliga frågor om hur få indexsidor är:

* [Har du undersökt din indexlogg?](#section_D6626536DC3D40DDA4A1224F1CB276BF)
* [Har du skrivfel i URL:en?](#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676)
* [Har startpunktens webbsida länkar till andra sidor..](#section_1C2D6ED54E7249268B555D9DC33352B3)
* [Är länkar till andra sidor på webbplatsen inbäddade i...](#section_EE34A67D60A844EBB0921C03544FF63E)
* [Är HTML-taggarna på din webbsida i en ...](#section_F31A2F5D2C284AC084158A5BD763DC5D)
* [Har du felaktigt formaterade HTML-kommentartaggar i ...](#section_D1C39D79341845CB9C38579AABDF3A24)
* [Innehåller din webbsida länkar till sidor på en annan sida..](#section_F8082759184049AAA8FA6342C1F84389)
* [Använder du en virtuell domäntjänst för din URL..](#section_2861F09EA21A45E6B7E15F032739CDF3)
* [Använder webbsidan en metauppdateringstagg?](#section_5A2F544C237C49B8B1A7FE0C45371C0D)
* [Använder din webbsida en metarobot-tagg?](#section_36275A33DDFE4620BABA948F8A63DBD2)
* [Använder din webbplats en exkluderingsfil för robotar?](#section_BF7B663347814F58AD736066C86B7D25)

## Har du undersökt din indexlogg? {#section_D6626536DC3D40DDA4A1224F1CB276BF}

Indexloggen innehåller detaljerad information som webbplatsens sök- och säljrobot samlar in när den indexerar webbplatsen. Loggen innehåller en lista med crawlade länkar och fel som påträffats. Att undersöka indexloggen är bäst att börja med för att avgöra varför alla sidor på webbplatsen inte är indexerade.

Se [Visa den fullständiga indexloggen för en live eller staged..](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

Se [Visa den inkrementella indexloggen för en live eller staged..](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

## Har du skrivfel i URL:en? {#section_BD2CEABC5D0F4A0DA38F3AD72ABBA676}

När du skriver långa URL:er i HTML-formulär kan det medföra ett eller flera typografiska fel. Kom ihåg att URL-adresser inte får innehålla blanksteg. Tänk också på att vissa webbservrar hanterar URL:er på ett skiftlägeskänsligt sätt.

Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]** på produktmenyn. Kontrollera följande på sidan [!DNL Staged URL Entrypoints]:

* Du har inga typografiska fel i dina URL-adresser.
* Alla tecken i URL:erna har rätt skiftläge.
* Det finns inga blankstegstecken i URL-adresserna.

Om du vill testa dina URL-ingångspunkter kopierar och klistrar du in en URL-adress i en webbläsare för att se om webbplatsen visas. Om den inte visas kontrollerar du att du inte har gjort några misstag i URL-sökvägen.

Se [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Har startpunktens webbsida länkar till andra sidor på webbplatsen? {#section_1C2D6ED54E7249268B555D9DC33352B3}

Webbplatssöknings-/säljroboten crawlar webbplatsen precis som kunden gör. genom att följa länkar från sida till sida. Länkar måste finnas på startpunktens webbsida innan sökroboten kan hitta och indexera andra sidor på webbplatsen.

Se [Lägga till flera URL-startpunkter som du vill indexera](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Är länkar till andra sidor på webbplatsen inbäddade i JavaScript? {#section_EE34A67D60A844EBB0921C03544FF63E}

Du kan använda avancerade navigeringstekniker på webbplatsen, till exempel rollover-åtgärder och menyer, som använder JavaScript för att länka till andra sidor. Webbplatssöknings-/försäljningsroboten kan dock inte följa länkar som är inbäddade i JavaScript.

En lösning som du kan använda för att lösa det här problemet är att placera dolda länkar till andra sidor i HTML-koden som innehåller JavaScript. Även om kunderna på din webbplats inte ser dessa länkar hittar och crawlar sökroboten dem fortfarande. Du kan placera dolda taggar längst ned på sidan precis före taggen `</body>`. De kan se ut så här:

```
<a href="/mydir/mypag1.html"></a> 
<a href="/mydir/mypag2.html"></a>
```

En annan lösning är att lista webbadresserna för de ytterligare sidorna på webbplatsen som startpunkter som ska crawlas och indexeras. Börja URL:erna med `https://` enligt följande:

```
https://www.mydomain.com/mydir/mypag1.html 
https://www.mydomain.com/mydir/mypag2.html
```

Se [Lägga till flera URL-startpunkter som du vill indexera](../c-about-settings-menu/c-about-crawling-menu.md#task_2338A47387D74CFDAC4D4EF4A367ED45).

## Har HTML-taggarna på webbsidan en ogiltig sekvens? {#section_F31A2F5D2C284AC084158A5BD763DC5D}

HTML-specifikationen kräver att taggarna `<html>`, `<head>` och `<body>` följer en viss sekvens i ett HTML-dokument. Taggar på alla dina webbsidor måste ha följande sekvens:

```
<html> 
<head> 
...  
<i>head tags go here</i> ... 
</head> 
<body> 
...  
<i>body tags go here</i> ... 
</body> 
</html>
```

Om HTML-taggarna inte är i rätt ordning kan inte webbplatsens sök- och säljrobot tolka och indexera din webbsida korrekt. Följande är ett exempel på taggar som inte finns i rätt sekvens:

```
<body> 
<head> 
...  
<i>head tags are here</i> ... 
</head> 
...  
<i>body tags are here</i> ... 
</body>
```

I så fall placerar du taggarna `<html>`, `<head>` och `<body>` i rätt sekvens på webbsidan.

## Har du felaktigt formaterade HTML-kommentartaggar på webbsidan? {#section_D1C39D79341845CB9C38579AABDF3A24}

Kontrollera att du noggrant granskar och korrigerar alla ogiltiga HTML-kommentarer på dina webbsidor.

HTML-specifikationen kräver att en HTML-kommentar börjar med tecknen `<!--` och slutar med tecknen `-->`. Det är enkelt att förbise felaktigt formaterade kommentarer som gör att webbplatsens sök- och säljrobot felaktigt tolkar taggarna på din webbsida. En felaktigt utformad kommentar kan göra att webbplatsens sök-/säljrobot saknar andra viktiga taggar som måste tolkas. Var uppmärksam på kommentarer precis före `<body>`-taggen på din webbsida.

Följande är ett exempel på en korrekt formaterad kommentar:

`<!-- This HTML comment is OK. -->`

Följande är ett exempel på en felaktigt formaterad kommentar:

```
<!- This HTML comment is improperly formed. -> 
<! This HTML comment is also improperly formed. >
```

## Innehåller din webbsida länkar till sidor på en annan domän? {#section_F8082759184049AAA8FA6342C1F84389}

En webbplats kan ofta bestå av sidor som faktiskt finns på en webbserver med en annan domänadress. Om din huvudwebbplatsadress till exempel är följande:

`https://www.mydomain.com/`

Din webbplats kan också ha sidor på en annan domän, som följande:

`https://www.otherdomain.com/`

Som standard följer inte webbplatsens sök- och säljrobot länkar på en annan domän än den huvudsakliga. Genom att ange ytterligare startpunkter för sökkontot kan du enkelt indexera flera domäner.

Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]** på produktmenyn. Lägg till URL:en för webbplatsens startpunkt. Lägg sedan till ytterligare URL-startpunkter i andra domäner som innehåller webbplatssidor. Du kan till exempel ange din huvudadress för URL till:

`https://www.mydomain.com/`

och lägg till följande ytterligare plats-URL-startpunkt:

`https://www.otherdomain.com/`

## Använder du en virtuell domäntjänst för din URL? {#section_2861F09EA21A45E6B7E15F032739CDF3}

Du kanske använder en virtuell domäntjänst (kallas ibland för en domänomdirigeringstjänst) för att ge en bättre URL för att kunderna ska kunna komma till din webbplats. Anta till exempel att den faktiska adressen för din webbplats är följande:

`https://www.myispdomain.com/~myname/mywebpages/`

Du använder dock en virtuell domäntjänst så att kunderna kan komma till din webbplats på följande adresser:

`https://myname.adomain.com/`

eller

`https://adomain.com/myname/`

Som standard följer inte webbplatsens sök- och säljrobot länkar på en annan domän än den huvudsakliga. Genom att ange ytterligare startpunkter för sökkontot kan du enkelt indexera flera domäner.

Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Entrypoints]** på produktmenyn. Lägg till startpunkten för huvudwebbplatsens URL till platsens virtuella domännamn. Lägg sedan till fler ingångspunkter i domänen där webbplatsen finns.

Du skulle till exempel ange din huvudadress till följande:

`https://myname.adomain.com/`

Och lägg till följande URL-startpunkt för webbplatsen:

`https://www.myispdomain.com/~myname/mywebpages/`

## Använder webbsidan en metauppdateringstagg? {#section_5A2F544C237C49B8B1A7FE0C45371C0D}

Många webbplatser har en startsida som innehåller en metauppdateringstagg mellan `<head>...</head>`-taggarna som liknar följande:

`<meta http-equiv="Refresh" content="0;URL=https://www.adomain.com/apath/afile.html">`

Under vissa omständigheter kan webbplatsens sök- och säljrobot inte följa metauppdaterings-URL:en för att indexera innehållet på webbplatsen. Det här problemet är enkelt att kringgå genom att ange ytterligare startpunkter.

Klicka på **[!UICONTROL Settings]** > Krypning > **[!UICONTROL URL Entrypoints]** på produktmenyn. Lägg till en ny startpunkt i URL:en för metauppdateringstaggen.

## Använder din webbsida en metarobot-tagg? {#section_36275A33DDFE4620BABA948F8A63DBD2}

Ibland använder webbsidor metarobottaggar för att styra webrobotar som regelbundet försöker crawla en webbplats. Meta robots-taggar visas mellan `<head>...</head>`-taggarna för en webbsida och ser ut ungefär som följande tagg:

`<meta name="robots" content="noindex, nofollow">`

Eftersom sökningen/försäljningen av webbplatsen i sig är en webrobot följer den anvisningarna för metarobottaggen. Genom att utesluta andra robotar på det här sättet exkluderar du även webbplatsens sök- och säljrobot.

Du kan läsa mer om webrobotar och Robots Exclusion Protocol här:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Ta bort eller ändra metarobottaggen på de webbsidor som du vill indexera på webbplatsen.

## Använder din webbplats en exkluderingsfil för robotar? {#section_BF7B663347814F58AD736066C86B7D25}

Ibland har en webbplats en sida som heter robots.txt som utesluter alla eller vissa robotar från att crawla den. Om du vill se om webbplatsen har en robots.txt-fil söker du efter den precis under domänen på den översta nivån enligt följande:

`https://www.yourdomain.com/robots.txt`

Innehållet i filen robots.txt ser ut ungefär som följande text:

```
User-agent: * 
Disallow: /
```

Eftersom den automatiska sökningen/försäljningen av webbplatsen i sig är en webborobot följer den anvisningarna i filen robots.txt - den utesluter roboten för sökning/försäljning av webbplatser. Du kan lösa det här problemet genom att redigera exkluderingsfilen för robotar (robots.txt) och tillåta att webbplatsens söknings-/försäljningsrobot crawlar och indexerar din webbplats enligt följande:

```
User-agent: Atomz/1.0 
Disallow: 
 
User-agent: * 
Disallow: /
```

## Microsoft Office {#reference_A85FCC8A96514A7584F4D2A8AC8111D1}

En sida med vanliga frågor som handlar om stöd för indexering och sökning av Microsoft® Office-filer på en webbplats.

Nedan följer några vanliga frågor om Microsoft Office-filer:

* [Vad indexeras i en Microsoft Office-fil?](#section_8681DADFCFE24B7787B1FC08D431EE28)
* [Vad som inte indexeras i en Microsoft Office-fil..](#section_BD53BDABFDD94D7EB0E1F55EC18017BB)
* [Hur indexeras Microsoft Office-filer annorlunda än HTML-sidor..](#section_C104B44684F340549A6B9EB8F39EDDBB)
* [Hur förhindrar jag att Microsoft Office-filer indexeras..](#section_FEBA71274CD14CB99731ADF982087F4C)

## Vad indexeras i en Microsoft Office-fil? {#section_8681DADFCFE24B7787B1FC08D431EE28}

Det fullständiga innehållet i Microsoft Word-filer, Microsoft Excel-filer och Microsoft PowerPoint-filer indexeras.

Följande delar av en Microsoft Word-fil är indexerade:

* Titel
* Nyckelord
* Ämne (beskrivning)
* Textbaserat innehåll
* Hyperlänkar till andra dokument

Följande delar av en Microsoft Excel-fil är indexerade:

* Titel
* Nyckelord
* Ämne (beskrivning)
* Text i celler
* Värden från numeriska formler i celler

Följande delar av en Microsoft PowerPoint-fil är indexerade:

* Titel
* Nyckelord
* Ämne (beskrivning)
* Text på varje bild

## Vad indexeras inte i en Microsoft Office-fil? {#section_BD53BDABFDD94D7EB0E1F55EC18017BB}

Grafik som finns i Microsoft Office-filer, eller text som är en del av en ingående bild, indexeras inte. Anpassade egenskapsdefinitioner är inte indexerade som metadata. En del text i specialfält, t.ex. sidhuvuden och sidfötter i en PowerPoint-fil, indexeras inte heller.

## Hur skiljer sig Microsoft Office-filer från HTML-sidor? {#section_C104B44684F340549A6B9EB8F39EDDBB}

Skillnaden mellan hur sökroboten indexerar Microsoft Office-filer och HTML-filer är att varje HTML-fil är en enskild sida och en Microsoft Office-fil kan representera hundratals sidor. Därför räknas varje sida i en Microsoft Office-fil som en separat sida under ditt sökkonto.

## Hur förhindrar jag att Microsoft Office-filer indexeras på min webbplats? {#section_FEBA71274CD14CB99731ADF982087F4C}

Om du inte vill att sökroboten ska crawla och indexera Microsoft Office-filer avmarkerar du innehållstypen **[!UICONTROL Microsoft Office Files]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Du kan också använda [!DNL URL Masks] för att inaktivera indexering av Microsoft Office-filer.

Ange följande URL-masker:

<table> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Om du inte använder reguljära uttryck </p> </td> 
   <td colname="col2"> 
    <ul id="ul_DFEC911DA11C484C8E4671A0F00E1F88"> 
     <li id="li_2E50374E3869426B97353A5A8CBE09EC">exclude *.doc </li> 
     <li id="li_9089D11161524D90849CA88F703772B6">exclude *.xls </li> 
     <li id="li_7F6CFC6212E64C04AAF38E21A667C763">exclude *.ppt </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Om du använder reguljära uttryck </p> </td> 
   <td colname="col2"> 
    <ul id="ul_012A45C3EC04460EA09C0ECFB49A8FA9"> 
     <li id="li_0C239F0A536D465F85A98EBF7B6ADF27">exkludera regexp ^.*\.doc$ </li> 
     <li id="li_9F91DA35A2A646ACAFF2BA37F9136E2A">exkludera regexp ^.*\.xls$ </li> 
     <li id="li_9D768D9EA2DB44FBB00A1979E21672E2">exkludera regexp ^.*\.ppt$ </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Se [Lägga till URL-masker till index eller inte indexdelar av..](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## MP3 {#reference_7614250EE81C4EEFA43E57A6A74E83D7}

En sida med vanliga frågor som handlar om stöd för indexering och sökning av MP3-musikfiler på en webbplats.

Nedan följer några vanliga frågor om MP3-filer.

* [När crawlas och indexeras en MP3-fil?](#section_538EA1682C9C47E3A62640BB25D84C36)
* [Vad måste jag göra för att crawla och indexera...](#section_3CD794446E3545379C14E9F222118665)
* [Hur känns en MP3-fil igen?](#section_230E7336965A424F96C5CCF1D3C2D103)
* [Vad indexeras i en MP3-fil?](#section_E99D252B27CA4946AED3FCD3ABD8779D)
* [Räknas en MP3-fil som en sida?](#section_9910BEB6617D4D2090558CDF6C65D16B)
* [Hur förhindrar jag indexering av enskilda MP3-filer...](#section_C989DC1D3D3841B38F683A462195DC05)
* [Hur förhindrar jag att MP3-filer indexeras?](#section_305D2B28D1124776B6DC0C62A17827C6)
* [Varför går det inte att söka i kinesiska, japanska eller koreanska MP3-filer på min webbplats?](#section_06A48DA3F9E742CC93CC8B5CCD7382FA)

## När crawlas och indexeras en MP3-fil? {#section_538EA1682C9C47E3A62640BB25D84C36}

MP3-filer crawlas och indexeras på ett av två sätt. Det vanligaste sättet är från en href-ankartagg i en HTML-fil:

`<a href="MP3-file-URL"></a>`

Ett annat sätt är att ange MP3-filens URL som en URL-startpunkt.

Se [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Vad måste jag göra för att crawla och indexera MP3-filerna på min webbplats? {#section_3CD794446E3545379C14E9F222118665}

Om du vill aktivera MP3-crawlning och indexering för ditt konto klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** på produktmenyn. Välj **[!UICONTROL Text in MP3 Music Files]** på sidan [!DNL Staged Content Types].

Se [Om innehållstyper](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Hur känns en MP3-fil igen? {#section_230E7336965A424F96C5CCF1D3C2D103}

En MP3-fil känns igen av sin MIME-typ som är &quot;audio/mpeg&quot;.

## Vad indexeras i en MP3-fil? {#section_E99D252B27CA4946AED3FCD3ABD8779D}

MP3-filer kan lagra en liten mängd textinformation. Informationen kan omfatta albumnamn, artistnamn, låttitel, låtgenre, utgivningsår och en kommentar. Den här informationen lagras i slutet av filen i det som kallas för TAGG. MP3-filer som innehåller TAGG-information indexeras på följande sätt:

* Låttiteln behandlas som titeln på en HTML-sida.
* Kommentaren behandlas som en beskrivning definierad för en HTML-sida.
* Genren behandlas som ett nyckelord som definierats för en HTML-sida.
* Konstnärens namn, albumnamn och versionsår behandlas som brödtexten i ett HTML-dokument.

## Räknas en MP3-fil som en sida? {#section_9910BEB6617D4D2090558CDF6C65D16B}

Ja, varje MP3-fil som crawlas och indexeras på webbplatsen räknas som en sida.

## Hur förhindrar jag indexering av enskilda MP3-filer? {#section_C989DC1D3D3841B38F683A462195DC05}

Omge ankartaggarna som länkar till MP3-filerna med `<nofollow>`- och `</nofollow>`-taggar. Sökroboten följer inte länkar mellan dessa taggar.

Ett annat sätt är att lägga till URL:er för MP3-filerna som exkluderingsmasker.

Se [Om URL-masker](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Se [Om URL-maskskript](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

## Hur förhindrar jag att MP3-filer indexeras? {#section_305D2B28D1124776B6DC0C62A17827C6}

Det enklaste sättet att styra MP3-indexering för ditt konto är att avmarkera **[!UICONTROL Text in MP3 Music Files]** på sidan [!DNL Staged Content Types].

Se [Markera de innehållstyper som ska crawlas och indexeras](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

Du kan också använda funktionen URL-masker för att inaktivera MP3-indexering per filtillägg. Det gör du genom att klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]** på produktmenyn. Ange någon av följande masker:

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Om ditt konto.. </p> </th> 
   <th colname="col2" class="entry"> <p>Ange följande URL-mask </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Använder inte reguljära uttryck </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exclude *.mp3  </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använder reguljära uttryck </p> </td> 
   <td colname="col2"> <p> <span class="codeph"> exkludera regexp ^.*\.mp3$ </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Varför går det inte att söka i kinesiska, japanska eller koreanska MP3-filer på min webbplats? {#section_06A48DA3F9E742CC93CC8B5CCD7382FA}

Om du vill söka efter kinesiska, japanska eller koreanska MP3-filer klickar du på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]** > **[!UICONTROL Text in MP3 Music Files]** på produktmenyn. Klicka sedan på **[!UICONTROL Settings]** > **[!UICONTROL Metadata]** > **[!UICONTROL Injections]** och ange den teckenuppsättning som används för att koda MP3-filerna.

Se [Markera de innehållstyper som ska crawlas och indexeras](../c-about-settings-menu/c-about-crawling-menu.md#task_CCAC5C67C8BF4AB7B79D34A1495D5EE8).

Se [Om injektioner](../c-about-settings-menu/c-about-metadata-menu.md#concept_DA091920671948A0A893A26B3A2FAAE5).

## PDF {#reference_F127C4915A0D436DA34E5D75ABFBB21B}

En sida med vanliga frågor och svar som diskuterar stöd för indexering och sökning av PDF-filer på en webbplats.

Nedan följer några vanliga frågor om PDF-filer:

* [Vad indexeras i en PDF-fil?](#section_62BFCD7158B44F2BB3B1864224B50174)
* [Vad indexeras inte i en PDF-fil?](#section_A14B353AE503408896BACBBF3F748FA0)
* [Hur räknas indexerade PDF-filer?](#section_C35DE36A65D649BD8FF314E9EFD990A6)
* [Kan sökresultaten visa en PDF-ikon?](#section_829CE82CC3544502A13D27C4DB820189)
* [Kan sökresultaten länka till en viss sida i..](#section_A06E7F7017E6441E98209D288EE57BF6)
* [Hur förhindrar jag att PDF-filer indexeras..](#section_96671419A822486AAC654D8DAD819940)
* [Hur kommer det sig att jag inte kan söka i de kinesiska, japanska eller koreanska PDF-filerna på min webbplats?](#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8)

## Vad indexeras i en PDF-fil? {#section_62BFCD7158B44F2BB3B1864224B50174}

Det fullständiga innehållet i PDF-filer indexeras. Följande delar av en PDF-fil är indexerade:

* Titel
* Nyckelord
* Ämne (beskrivning)
* Textbaserat innehåll

## Vad indexeras inte i en PDF-fil? {#section_A14B353AE503408896BACBBF3F748FA0}

PDF-innehållsförteckningen, bilder i filen eller text som är en del av en bild i innehållet indexeras inte.

## Hur räknas indexerade PDF-filer? {#section_C35DE36A65D649BD8FF314E9EFD990A6}

Varje PDF-fil räknas, inklusive PDF-filer som innehåller flera sidor, som ett enda dokument.

## Kan sökresultaten visa en PDF-ikon? {#section_829CE82CC3544502A13D27C4DB820189}

Ja. Använd taggen `<search-if-link-extension>` i mallen för att inkludera en PDF-ikon, eller annan grafik eller text, i sökresultatet:

```
<search-results> 
  ... 
  <search-if-link-extension value=".pdf"> 
    <img src="/search/i/pdficon.gif"> 
  </search-if-link-extension> 
  ... 
</search-results>
```

PDF-ikoner hjälper dina kunder att veta att ett sökresultat länkar till en PDF-fil som kan vara mycket stor. Filstorleken kan vara viktig för kunder som använder webbplatsen via ett modem eller en mobil enhet.

## Kan sökresultaten länka till en viss sida i en PDF-fil? {#section_A06E7F7017E6441E98209D288EE57BF6}

Ja. Med malltaggen för smarta länkar ( `<search-smart-link>...</search-smart-link>`) kan kunderna klicka för att öppna den första PDF-sidan som innehåller sökresultatet.

Om du vill använda smarta länkar ersätter du `<search-link>...</search-link>`-taggarna i sökresultatavsnittet i mallen med `<search-smart-link>...</search-smart-link>`-taggar. När en kund klickar på en länk som de smarta länktaggarna genererar, går de till den första PDF-sidan som är relevant för deras sökfråga.

>[!NOTE]
>
>För att kunna använda den här funktionen måste kunden använda en nyare version av Adobe Acrobat, eller Adobe Acrobat Reader, som måste innehålla plugin-programmet för högdagrar och plugin-programmet för Extern fönsterhantering (EWH). Dessutom måste webbläsaren använda plugin-programmet Adobe Acrobat för Netscape Navigator (du kan använda vilken webbläsare som helst som accepterar plugin-programmet till Netscape Navigator) eller Acrobat ActiveX-kontrollen för Internet Explorer 4.0 och senare.

Se [Sök efter malltaggar](../c-appendices/c-templates.md#reference_F7AA3FF602314E42842BBC740D2CA1A4).

## Hur förhindrar jag att PDF-filer indexeras på min webbplats? {#section_96671419A822486AAC654D8DAD819940}

Om du inte vill att sökroboten ska crawla och indexera PDF-filer avmarkerar du innehållstypen **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**).

Du kan också välja att använda [!DNL URL Masks] för att inaktivera PDF-indexering.

Se [Lägga till URL-masker till index eller inte indexdelar av..](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

Om du vill inaktivera PDF-indexering anger du en av följande URL-masker:

* `exclude *.pdf` (om du inte använder reguljära uttryck)
* `exclude regexp ^.*\.pdf$` (om du använder reguljära uttryck)

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Hur kommer det sig att jag inte kan söka i de kinesiska, japanska eller koreanska PDF-filerna på min webbplats? {#section_D41CA8EFCA0242EA8CF5F8F1924E4CD8}

Webbplatssökning/-varuexponering hämtar UTF-8 från PDF-filer utan språkindikation. Om du valde innehållstypen **[!UICONTROL PDF Documents]** ( **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**) måste du använda metadatainjektioner för att ange vilket språk som ska användas i PDF-filen.

Se [Lägga till fältinjektionsdefinitioner](../c-about-settings-menu/c-about-metadata-menu.md#task_E86566FA1FF74CF68115C0ADA05172AE).

## För många sidor {#reference_48A748BC1ED14844ACAC2735C8388E8A}

En sida med vanliga frågor som förklarar några av orsakerna till varför indexeraren har räknat fler sidor än du har och vad lösningen är i varje enskilt fall.

Om du är säker på att webbplatsen är under gränsen för antalet sidor, men indexeraren säger att gränsen är nådd, bör du läsa dessa vanliga frågor och svar för att se om det finns några möjliga lösningar.

* [Har du undersökt dina olika indexloggar?](#section_C929BF9FDA6B4C9A9078C45AFE80EFE8)
* [Indexeras CGI-program på din webbplats?](#section_86ED8A641B3841EC80153B4F107548FD)
* [Har servern aktiverat katalogbläddring?](#section_073C88EEE74F4CA0AD2C7145D4810B22)
* [Finns det forum eller diskussionsgrupper på din webbplats?](#section_8DCB94F0850A41B9B2EA885F779E2F84)
* [Finns det PDF- eller Microsoft Office-filer på webbplatsen...](#section_455FC5438DF74E68AB9A31D359EAD4D9)
* [Har du flera URL-ingångspunkter?](#section_8C54AFD7DF56472A9364D516482B534C)
* [Har du överskridit de interna byten eller tidsgränserna för ...](#section_AE1BE61A58864FFE81F0BCEED2EBB15D)

## Har du undersökt dina olika indexloggar? {#section_C929BF9FDA6B4C9A9078C45AFE80EFE8}

Indexloggen innehåller detaljerad information som samlats in av webbplatsens sök- och säljrobot när den indexerar webbplatsen. Loggen innehåller en lista med alla crawlade länkar och påträffade fel. Att undersöka indexloggen är bäst att börja när du försöker avgöra vilka sidor som ska indexeras.

Se [Visa den fullständiga indexloggen för en live eller staged..](../c-about-index-menu/c-about-full-index.md#task_02E5E944C56B4EB19CC1FF321F3221B8).

Se [Visa den inkrementella indexloggen för en live eller staged..](../c-about-index-menu/c-about-incremental-index.md#task_E668E1F1240C476DAA1CA783DC728232).

Se [Visa skriptad inkrementell indexlogg för en live eller...](../c-about-index-menu/c-about-scripted-index.md#task_CBFCE9B9A87B4DF7A2A35A6E83DE93D7).

Se [Visa den återskapade indexloggen för en live eller staged..](../c-about-index-menu/c-about-regenerate-index.md#task_61CE8F9E7BF84BA89A8D482B2106BB15).

Se [Visa den omrangordnade indexloggen för en live- eller staged-webbplats](../c-about-index-menu/c-about-re-rank-index.md#task_3C76107DFAC1495FACD3ABB0A688208D).

## Indexeras CGI-program på din webbplats? {#section_86ED8A641B3841EC80153B4F107548FD}

CGI-program använder URL-parametrar som ibland gör att indexeraren crawlar flera &quot;falska&quot; URL:er. Om sökning/försäljning av webbplatser läser dina CGI-program och följande URL:er med CGI-parametrar finns det antagligen flera multipler av sidor som crawlas och indexeras och som inte är användbara i sökindexet. Typiska CGI-parametrar visas i URL:er med `?` eller `&` tecken.

Du kan maskera att CGI-program inte indexeras med funktionen URL-masker. Du kan maskera ett URL-prefix eller använda reguljära uttryck för att maskera dina CGI-skript.

Se [Om URL-masker](../c-about-settings-menu/c-about-crawling-menu.md#concept_8039DFC53FF3410AA494D602F71BA164).

Se [Om URL-maskskript](../c-about-settings-menu/c-about-filtering-menu.md#concept_384F32EA18F84853A7BA99A04009330B).

Se [Reguljära uttryck](../c-appendices/r-regular-expressions.md#reference_B5BA7D61D82E4109A01D2A2D964E3A6A).

## Har servern aktiverat katalogbläddring? {#section_073C88EEE74F4CA0AD2C7145D4810B22}

När en webbserver har katalogbläddring aktiverad och det inte finns någon index.html-fil i en viss katalog kan du besöka den katalogen och visa listan över filer i den katalogen. Vanligtvis finns det länkar överst på sidan så att du kan sortera listan på olika sätt bara genom att klicka på **[!UICONTROL Name]**, **[!UICONTROL Last modified]**, **[!UICONTROL Size]** och så vidare. Vanligtvis visas dessa i webbplatsens sök-/försäljningsindexlogg som URL:er med tecken som `?M=A` i slutet. Webbplatssöknings-/försäljningsindexeraren följer dessa som länkar, vilket kan leda till indexering av flera &quot;falska&quot; URL:er.

Vanligtvis finns indexfiler i alla kataloger på en väldesignad webbplats, eller så är katalogbläddring inaktiverad för de kataloger som saknar indexfiler. Lyckligtvis finns det ett enkelt sätt att maskera dessa falska URL:er om du inte kan ändra dina sidor eller inaktivera kataloglistor på serversidan.

Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]** för att slutföra uppgiften. Lägg till en mask för att maskera en URL som innehåller tecknet `?`. Du kan göra detta genom att ange följande mask för reguljära uttryck:

`exclude regexp ^.*\?.*$`

När du har skapat masken måste du indexera om webbplatsen.

Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Finns det forum eller diskussionsgrupper på din webbplats? {#section_8DCB94F0850A41B9B2EA885F779E2F84}

Om forum eller diskussionsgrupper crawlas på webbplatsen kan det finnas följande URL:er för olika visningsalternativ eller sorteringsalternativ. Detta innebär att samma sida indexeras flera gånger.

Vanligtvis innehåller forum och diskussionsgrupper sina egna sökmotorer. I så fall kan du använda [!DNL URL Masks] för att maskera forumen från webbplatssökning/marknadsföring.

Klicka på **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL URL Masks]** på produktmenyn. Maskera forumen på sidan [!DNL Staged URL Masks] genom att ange deras URL:er som exkluderade URL-masker.

Se [Lägga till URL-masker till index eller inte indexdelar av..](../c-about-settings-menu/c-about-crawling-menu.md#task_E1AFC17C746048B8843013D979E082C1).

När du har skapat maskerna måste du indexera om webbplatsen.

Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Se [Köra ett inkrementellt index för en aktiv eller mellanlagrad webbplats...](../c-about-index-menu/c-about-incremental-index.md#task_9BFB6157F3884B2FAECB7E0E9CA318CB).

## Finns det PDF- eller Microsoft Office-filer på webbplatsen? {#section_455FC5438DF74E68AB9A31D359EAD4D9}

Om du har PDF-filer eller [!DNL Microsoft Office]-filer på webbplatsen kanske du märker att indexstorleken för bara ett fåtal filer är många sidor. Orsaken till att fler sidor indexeras än de dokument du har är att varje sida i en PDF- eller Microsoft Office-fil räknas som en separat sida.

Klicka på **[!UICONTROL Index]** > **[!UICONTROL Full Index]** > **[!UICONTROL Live Index]** på produktmenyn. På sidan [!DNL Full Index] väljer du **[!UICONTROL Count All Pages]** och klickar sedan på **[!UICONTROL Full Index Now]** för att se det totala antalet sidor. Om du inte vill att PDF-filer eller Microsoft Office-filer ska indexeras kan du inaktivera den här innehållstypen under **[!UICONTROL Settings]** > **[!UICONTROL Crawling]** > **[!UICONTROL Content Types]**.

Se [Köra ett fullständigt index för en aktiv eller mellanlagrad webbplats..](../c-about-index-menu/c-about-full-index.md#task_F7FE04D8A1654A7787FCCA31B45EB42D).

Se [Om innehållstyper](../c-about-settings-menu/c-about-crawling-menu.md#concept_6FEA1355C0374500B4C53090C34A8A07).

## Har du flera URL-ingångspunkter? {#section_8C54AFD7DF56472A9364D516482B534C}

Webbplatssöknings-/försäljningsroboten börjar crawla vid angivna URL-startpunkter och följer alla hittade länkar till allt innehåll i den aktuella domänen. Om du har angett många URL-startpunkter kan ett stort antal sidor crawlas.

Använd taggen `nofollow` i Robots Exclusion Protocol i sidhuvudena i entrypoint-dokumenten på de ytterligare domänerna enligt följande:

```
<html> 
<head> 
<meta name="robots" content="nofollow"> 
</head>
```

Koden ovan anger att webbplatsens sök- och säljrobot ska indexera sidans innehåll, men inte följa länkarna till ytterligare sidor.

Du kan läsa mer om webrobotar och Robots Exclusion Protocol här:

[https://www.robotstxt.org/orig.html](https://www.robotstxt.org/orig.html)

Om du inte har åtkomst till sidornas källa i ytterligare domäner kan du ta bort flera URL-startpunkter. På så sätt kan du begränsa indexeringsaktiviteten till endast de domäner vars innehåll du vill att kunderna ska kunna söka i.

Se [Om URL-adresser](../c-about-settings-menu/c-about-crawling-menu.md#concept_5D857E3B5C124E85BC0B5AE77A509573).

## Har du överskridit de interna byten eller tidsgränserna för webbplatssökning/försäljning? {#section_AE1BE61A58864FFE81F0BCEED2EBB15D}

Kontrollera om ditt konto har nått gränsen på skärmen &quot;Full Index Status&quot;. Om statusen visar att ditt index är större än tillåtet eller att det tog längre tid än tillåtet, är webbplatsen inte helt indexerad. Du kan korrigera det här felet så att du får rätt täckning och antal webbplatssidor.

För att skydda servrar för webbplatssökning och -försäljning finns det interna begränsningar för byte och tid. Det är bara när crawlade filer är mycket stora eller när servern som sökningen/försäljningen på webbplatsen försöker nå är långsam som dessa gränser nås.

Om du når en tidsgräns kontrollerar du att servern är online och försöker indexera igen vid ett senare tillfälle. Om du når en gräns på byte bör du kontrollera de crawlade filerna genom att visa indexloggen. Är de ovanligt stora? Kontakta teknisk support om något av dessa meddelanden visas.
