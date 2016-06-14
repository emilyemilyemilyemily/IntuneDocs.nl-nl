---
# required metadata

title: Beleidsinstellingen voor voorwaarden in Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Beleidsinstellingen voor voorwaarden in Microsoft Intune
U kunt de voorwaarden van Intune implementeren voor gebruikersgroepen om uit te leggen hoe zaken als inschrijving, toegang tot werkresources en het gebruik van de bedrijfsportal-app invloed hebben op apparaten en gebruikers. Gebruikers moeten de voorwaarden accepteren voordat ze de bedrijfsportal kunnen gebruiken om hun apparaat te registreren en toegang te krijgen tot hun werk.

U kunt meerdere beleidsregels met verschillende voorwaarden maken en implementeren. U kunt ook meerdere versies van dezelfde voorwaarden in verschillende talen maken en deze voor de betreffende groepen implementeren.

## Een beleid voor voorwaarden maken

1.  Klik in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) op **Beleid** &gt; **Voorwaarden**.

    ![Schermafbeelding van beleidsinstellingen voor voorwaarden](./media/pol-sa-terms-conditions.png)

2.  Klik op **Toevoegen** om een nieuw beleid voor voorwaarden te maken.

    U kunt ook een bestaand beleid **bewerken** of **verwijderen**.

3.  Geef op de pagina **Voorwaarden maken** de volgende gegevens op:

    -   **Naam**: een unieke beleidsnaam die wordt weergegeven in de Intune-console

    -   **Beschrijving**: informatie waarmee u het beleid in de Intune-console kunt herkennen

    -   **Titel**: de titel die voor gebruikers in de bedrijfsportal wordt weergegeven

    -   **Tekst waarmee wordt uitgelegd wat het inhoudt als de gebruiker de voorwaarden accepteert**: de verklaring die gebruikers zien in verband met aanvaarding. **Voorbeeld**: 'Ik ga akkoord met de voorwaarden'.

4.  Klik op **Opslaan** als u klaar bent. Het nieuwe beleid wordt weergegeven in het knooppunt **Voorwaarden** van de werkruimte **Beleid**.

## Een beleid voor voorwaarden implementeren

1.  Klik in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) op **Beleid** &gt; **Voorwaarden**.

2.  Selecteer in de lijst **Beleidsregels voor voorwaarden** het beleid dat u wilt implementeren en klik vervolgens op **Implementatie beheren**..

3.  Selecteer in het dialoogvenster **Implementatie beheren** de gebruikersgroepen waarvoor u het beleid wilt implementeren en klik vervolgens op **OK**..

    Wanneer de betreffende gebruikers de bedrijfsportal openen, worden in Intune de voorwaarden weergegeven die u hebt geïmplementeerd. Gebruikers moeten deze voorwaarden accepteren voordat ze toegang krijgen tot bedrijfsresources.

## Een beleid voor voorwaarden bewaken

1.  Klik in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) op **Beleid** &gt; **Voorwaarden**.

2.  Klik in het venster **Nieuw rapport maken** op **Rapport weergeven**. Het rapport wordt geopend met gedetailleerde informatie over welke gebruikers de door u geïmplementeerde voorwaarden hebben geaccepteerd.

### Updates en versiebeheer voor voorwaarden
Wanneer u bestaande voorwaarden bewerkt, kunt u het gewenste gedrag kiezen wanneer u het beleid implementeert. Volg de volgende procedure om bestaande voorwaarden bij te werken.

## Met meerdere versies van voorwaarden werken

1.  Klik in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) op **Beleid** &gt; **Voorwaarden**.

2.  Selecteer de voorwaarden die u wilt bewerken en klik op **Bewerken**..

3.  Breng op de pagina **Voorwaarden bewerken** de gewenste wijzigingen aan en geef aan of alle gebruikers de nieuwe voorwaarden moeten accepteren of alleen nieuwe gebruikers de nieuwe versie te zien krijgen.

    Het wordt aangeraden het versienummer te verhogen en elke keer dat u belangrijke wijzigingen doorvoert te vereisen dat gebruikers de nieuwe voorwaarden accepteren. Behoud het huidige versienummer als u bijvoorbeeld typefouten wilt herstellen of de opmaak wilt wijzigen.

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


<!--HONumber=May16_HO1-->

