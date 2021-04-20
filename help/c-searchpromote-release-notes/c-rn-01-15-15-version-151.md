---
description: Sök&amp;Befordra versionsinformation för 15.1.1.
solution: Target
title: Sök&stämpel;amp;Promote 15.1.1 Versionsinformation (01/15/2015)
topic: Release Notes,Site search and merchandising
uuid: 070f9c46-426f-4ca1-80c7-8ca53d40a402
translation-type: tm+mt
source-git-commit: d015154efdccbb4c6a39a56907c0c337ec065c9f
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---


# Versionsinformation om Search &amp; Promote 15.1.1 (01/15/2015){#search-promote-release-notes}

## Ny funktion {#section_2A10EF6B40FC4F2CB2381FFA9FFA64BD}

* Tidigare tillämpades språk som ordstam, synonymer o.s.v. alltid på nyckelord i reglerna för guidad sökning. Nu kan du inaktivera den här expanderingen så att nyckelordet används som det är.

   När du vill använda utlösande villkor för en affärsregel väljer du **[!UICONTROL keyword]** i den första listrutan efter [!DNL Advanced Rule Builder] och väljer sedan den nya operatorn **[!UICONTROL equal exact]** i den andra listrutan.**[!UICONTROL If any/all of the following conditions are met]**

   Se [Om affärsregler](../c-about-rules-menu/c-about-business-rules.md#concept_2A93D76216754D3D8412CDEA00BD26BD).

## Korrigeringar och förbättringar {#section_22D1AFC99F394D569898828A0D3C419D}

* [!DNL Visual Rule Builder] och trunkerar  [!DNL Advanced Rule Builder] inte längre MDI-fältvärdet (Merchandising Document ID).
* RBTA-relaterade indexeringsfel har nu åtgärdats.
* Om du redigerar en befintlig affärsregel som har statusen&quot;godkänd&quot; återkallas nu statusen&quot;godkänd&quot;. Du måste använda [!DNL Advanced Rule Builder] för att kontrollera alternativet **[!UICONTROL Approved]** och sedan spara regeln som vanligt. Om du inte godkänner om en redigerad regel anges regelns status automatiskt till Pågående arbete på sidan [!DNL Business Rules].
* Det finns nu ett nytt **[!UICONTROL Advanced Search]**-alternativ på [!DNL Business Rules]-sidan för förbättrad filtrering av regler.
* **[!UICONTROL contains word]**-villkoret har lagts till i regelutlösare i [!DNL Query Cleaning], [!DNL Pre-Search Rules], [!DNL Post Search Rules] och [!DNL Business Rules] så att du enkelt kan ange ordbrytningar.
* Förbättringar av affärsregelanteckningar som när du visar en regel kan du nu hämta anteckningshistoriken för den regeln. Anteckningar loggas nu även i **[!UICONTROL Reports]** > **[!UICONTROL Change Log]**.
* Frågor som inte har `sp_i`-värden som inte är noll körs inte längre via [!DNL Adobe Analytics]-omdirigeraren.

   Se rad 15 i tabellen i [CGI-parametrar för backend-sökning](../c-appendices/c-cgiparameters.md#reference_582E85C3886740C98FE88CA9DF7918E8).

