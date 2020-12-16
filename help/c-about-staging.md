---
description: Med mellanlagring kan du testa och förhandsgranska ändringar av dina inställningar och konfigurationer utan att påverka ditt Live-index.
seo-description: Med mellanlagring kan du testa och förhandsgranska ändringar av dina inställningar och konfigurationer utan att påverka ditt Live-index.
seo-title: Om Förproduktion
solution: Target
title: Om Förproduktion
topic: Staging,Site search and merchandising
uuid: 2e5889a6-2e9c-4ac7-9d6e-d35e7cafda5b
translation-type: tm+mt
source-git-commit: ef818327e1cdaad79ac47575a8dfba1de3dc5c2e
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 0%

---


# Om Förproduktion{#about-staging}

Med mellanlagring kan du testa och förhandsgranska ändringar av dina inställningar och konfigurationer utan att påverka ditt Live-index.

## Om mellanlagring {#concept_08B8F3CA1F4241108F14BA7FC7806CA7}

Med mellanlagring kan du testa och förhandsgranska ändringar av dina inställningar och konfigurationer utan att påverka ditt Live-index.

Se även [Element-ID:context_A5783D07C72042EC886F300FFF62C50](c-about-simulator.md#context_A5783D07C72042EC8886F300FFF62C50).

Alla sidor som har mellanlagringsalternativen **[!UICONTROL Push All Live]** eller **[!UICONTROL View Live Settings]** betyder att alla inställningar på den sidan kan mellanlagras. Undantag är webbsidorna i Index. Sidorna i det här området är antingen explicit för det mellanlagrade indexet eller live-indexet så att du direkt kan kontrollera de två indexen oberoende av varandra.

Du kan scenera nästan vad som helst, inklusive ditt index. Vissa undantag inkluderar kontospecifika inställningar som påverkar både testmiljön och den aktiva miljön samtidigt och schemaläggningen av indexeringsåtgärder. När du sparar ändringar i en inställning som kan mellanlagras mellanlagras den automatiskt.

När alternativen **[!UICONTROL Push All Live]** eller **[!UICONTROL View Lives Settings]** inte är aktiverade (nedtonade) betyder det att inställningarna för den mellanlagrade sidan är desamma som inställningarna för direktuppspelning.

Observera att den aktiva versionen av inställningarna är skrivskyddad för ett objekt som är mellanlagrat. kan bara ändras genom att de mellanlagrade inställningarna aktiveras.

## Om historik på mellanlagrade sidor {#section_5BE780AFF26A450A9EFF4000DE53531B}

De flesta mellanlagrade inställningar har ett [!DNL History]-alternativ i sidans övre högra del. När du klickar på **[!UICONTROL History]** kan du återställa alla ändringar som du nyligen har gjort på den aktuella mellanlagrade sidan som du har öppnat.

Du kan även visa ändringsloggen för en alternativ vy av Historik. Varje gång en ändring görs skapas en säkerhetskopia av den underliggande datafilen. Ändringsloggen visar varje sådan revision, med versionsnummer, e-postadress till den användare som utförde ändringarna och det datum då säkerhetskopieringen gjordes. Posten med ett fet versionsvärde representerar den aktuella versionen.

Se [Visa ändringsloggen](c-about-reports-menu/c-about-reports-menu.md#task_166F1156719F4B3D834BEA8E249C8057).

## Sidan Hantera Stage-Live-inställningar {#section_E72B8CAF516345A5B6B6783CF6E512EE}

Förutom att erbjuda alternativen **[!UICONTROL Push All Live]** och **[!UICONTROL View Live Settings]** direkt från en viss sida, kan du även använda sidan **[!UICONTROL Manage Stage-Live Settings]** för att göra samma sak. Sidan **[!UICONTROL Manage Stage-Live Settings]**, som finns på huvudproduktmenyn, är en central plats som visar alla inställningar i ditt konto som för närvarande är mellanlagrade. Du kan överföra alla inställningar live, bara överföra valda inställningar live eller ta bort inställningar. Som en bra rutin bör du dock alltid skicka alla mellanlagrade objekt live för att undvika problem med inbördes beroenden.

Inställningarna på sidan är grupperade i kategorier. Du kan expandera varje kategori för att visa vilka sidinställningar som är mellanlagrade. Beroenden spåras för närvarande inte i scenhanteraren. Därför rekommenderar vi att du flyttar allt live samtidigt förutom indexet.

Du kan överföra ett mellanlagrat index live. Kontrollera först att det mellanlagrade indexet inte är inaktuellt eller skadat. Om du gör ett misstag och flyttar det mellanlagrade indexet live kan du återställa ett gammalt direktindex. Det tar vanligtvis mindre än 30 sekunder att överföra ett mellanlagrat index live.

## Testar en mellanlagrad inställning eller ett indexvärde {#section_6800E52D20854A779946EAB600801F12}

På sidor som har stöd för en testkontroll kan du testa mot inställningarna för testläge eller live. När du visar de mellanlagrade inställningarna används den mellanlagrade inställningen för testet. På samma sätt används live-inställningarna för testet när du visar live-inställningen. I mallavsnittet utförs alla tester mot den mellanlagrade versionen av indexet. Om du vill söka efter ett mellanlagrat index anger du CGI-parametern `sp_staged` som lika med 1. Det innebär i sin tur att du vill använda det mellanlagrade indexet. Om det inte finns något mellanlagrat index genomsöks ditt Live-index och eventuella mellanlagrade inställningar för söktid tillämpas.

Se även [CGI-parametrar för backend-sökning](c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

## Visa Live-inställningar {#task_401A0EBDB5DB4D4CA933CBA7BECDC10F}

Du kan granska den aktiva versionen av inställningarna från vilken mellanlagrad sida som helst.

<!-- 

t_viewing_live_settings.xml

 -->

Om alternativet **[!UICONTROL View Live Settings]** inte är aktiverat (nedtonat) betyder det att sceninställningarna för den sidan och live-inställningarna redan är synkroniserade.

**Visa Live-inställningar**

1. Klicka på **[!UICONTROL View Live Settings]** på en sida som har mellanlagsinställningar för att se den aktiva versionen av inställningarna.
1. Du kan även göra något av följande:

   * Klicka på **[!UICONTROL View]** för att se de aktuella alternativen som är valda för den mellanlagrade inställningen.
   * Klicka på **[!UICONTROL View Stage Settings]** för att återgå till den mellanlagrade inställningen där du kan redigera eller ta bort inställningen.

## Inställningar för push-scen live {#task_44306783B4C0408AAA58B471DAF2D9A4}

Du kan överföra inställningar direkt från alla mellanlagrade sidvyer eller från den centrala **[!UICONTROL Manage Stage-Live Settings]**-sidan.

<!-- 

t_pushing_live_settings_live.xml

 -->

När alternativet **[!UICONTROL Push Live]** är aktiverat (onedtonat) på en sida betyder det att det finns en inställning som är mellanlagrad. Eller så betyder det att en inställning har redigeringar och när du sparar blir inställningen mellanlagrad. När du klickar på det här alternativet sparas alla osparade redigeringar i mellanlagringsområdet. Om det inte finns några väntande redigeringar publiceras sidans inställningar omedelbart.

**Så här skickar du mellanlagrade inställningar live**

1. Gör något av följande:

   * Klicka på **[!UICONTROL Push Live]** på en sida där &quot;Staged&quot; har valts som vy.
   * Klicka på **[!UICONTROL Staging]** på produktmenyn. Gör något av följande på sidan **[!UICONTROL Manage Stage-Live Settings]**:

   * Använd inställningsträdet för att endast kontrollera de inställningar som du vill göra dynamiska och klicka sedan på **[!UICONTROL Push Selected Live]**.
   * Klicka på **[!UICONTROL Push All Live]**.

## Tar bort inställningar för direktuppspelning från en central plats {#task_B72BEA9269704B1399600A9CA273369B}

Om du har många inställningar att ta bort kan du använda sidan **[!UICONTROL Manage Stage-Live Settings]** för att ta bort inställningar från en central plats.

<!-- 

t_deleting_staged_settings_from_a_central_location.xml

 -->

**Varning**: När du klickar  **[!UICONTROL Delete Selected]** tas alla markerade inställningar bort omedelbart; det inte finns någon bekräftelsedialogruta som bekräftar att du verkligen vill ta bort de valda inställningarna. Det finns heller ingen historikfunktion kopplad till sidan. Du kan därför inte ångra borttagningen.

**Ta bort inställningar för direktuppspelning på en central plats**

1. Klicka på **[!UICONTROL Staging]** på produktmenyn.
1. Använd inställningsträdet på sidan **[!UICONTROL Manage Stage-Live Settings]** för att endast kontrollera de inställningar som du vill ta bort.
1. Klicka på **[!UICONTROL Delete Selected]**.
