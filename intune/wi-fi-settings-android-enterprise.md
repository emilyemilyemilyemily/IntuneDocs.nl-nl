---
title: Wi-Fi-instellingen configureren voor Android Enterprise- en Kiosk-apparaten - Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Een configuratieprofiel voor een Wi-Fi-apparaat voor Android Enterprise en Android Kiosk maken of toevoegen. Zie de verschillende instellingen, zoals voor het toevoegen van certificaten, voor het kiezen van een EAP-type en het selecteren van een verificatiemethode in Microsoft Intune. Voor Kiosk-apparaten moet u ook de vooraf gedeelde sleutel van uw netwerk opgeven.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: be26522555766c6a3661857ba7722c2425cc984e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180439"
---
# <a name="add-wi-fi-settings-for-devices-running-android-enterprise-and-android-kiosk-in-microsoft-intune"></a>Wi-Fi-instellingen voor apparaten met Android Enterprise en Android Kiosk in Microsoft Intune toevoegen

U kunt een profiel maken met specifieke Wi-Fi-instellingen en dit profiel vervolgens implementeren op uw Android Enterprise- en Android Kiosk-apparaten. Microsoft Intune bevat veel functies, waaronder het verifiëren bij uw netwerk, het gebruik van een vooraf gedeelde sleutel en meer.

In dit artikel worden deze instellingen beschreven.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatprofiel](device-profile-create.md).

## <a name="device-owner-only---kiosk"></a>Alleen eigenaar van het apparaat - kiosk

Selecteer deze optie als u een Android Enterprise-apparaat als een kiosk wilt gebruiken.

- **Netwerknaam**: voer een naam in voor deze Wi-Fi-verbinding. Deze waarde krijgen gebruikers te zien in de lijst met beschikbare verbindingen op hun apparaat.
- **SSID**: afkorting voor **Service Set Identifier**. Deze instelling is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken. Gebruikers zien echter alleen de **netwerknaam** die u hebt geconfigureerd wanneer ze de verbinding kiezen.
- **Automatisch verbinding maken**: kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.
- **Wi-Fi-type**: selecteer het beveiligingsprotocol voor de verificatie bij het Wi-Fi-netwerk. Uw opties zijn:

  - **Open (geen verificatie)**: gebruik deze optie alleen als het netwerk niet beveiligd is.
  - **Vooraf gedeelde WEP-sleutel**: typ het wachtwoord bij **Vooraf gedeelde sleutel**. Wanneer het netwerk van uw organisatie is ingesteld of geconfigureerd, wordt er ook een wachtwoord of netwerksleutel geconfigureerd. Voer dit wachtwoord of deze netwerksleutel in voor de PSK-waarde.
  - **Vooraf gedeelde WPA-sleutel**: typ het wachtwoord bij **Vooraf gedeelde sleutel**. Wanneer het netwerk van uw organisatie is ingesteld of geconfigureerd, wordt er ook een wachtwoord of netwerksleutel geconfigureerd. Voer dit wachtwoord of deze netwerksleutel in voor de PSK-waarde.

Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="work-profile-only"></a>Alleen werkprofiel

### <a name="basic-settings"></a>Basisinstellingen

- **Wi-Fi-type**: kies **Basic**.
- **SSID**: afkorting voor **Service Set Identifier**. Deze instelling is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken.
- **Automatisch verbinding maken**: kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.

## <a name="enterprise-profile"></a>Enterprise-profiel

- **Wi-Fi-type**: kies **Enterprise**.
- **SSID**: afkorting voor **Service Set Identifier**. Deze instelling is de echte naam van het draadloze netwerk waarmee apparaten verbinding maken.
- **Automatisch verbinding maken**: kies **Inschakelen** om automatisch verbinding te maken met dit netwerk wanneer het apparaat binnen het bereik daarvan is. Kies **Uitschakelen** om te voorkomen dat apparaten automatisch verbinding maken.
- **Verborgen netwerk**: kies **Inschakelen** om te voorkomen dat dit netwerk op het apparaat wordt weergegeven in de lijst met beschikbare netwerken. De SSID wordt niet verzonden. Kies **Uitschakelen** om dit netwerk in de lijst met beschikbare netwerken op het apparaat weer te geven.
- **EAP-type**: kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt om beveiligde draadloze verbindingen te verifiëren. Uw opties zijn: 

  - **EAP-TLS**: voer ook het volgende in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: kies een profiel voor een bestaand vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie** - **Clientcertificaat voor clientverificatie (identiteitscertificaat)**: kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat wordt geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

  - **EAP-TTLS**: voer ook het volgende in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: kies een profiel voor een bestaand vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie**: kies een **verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: de gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. Voer ook in:
        - **Niet-EAP-methode (interne identiteit)**: kies hoe u de verbinding verifieert. Zorg ervoor dat u hetzelfde protocol kiest dat op uw Wi-Fi-netwerk is geconfigureerd.

          Uw opties: **niet-versleuteld wachtwoord (PAP)**, **Challenge Handshake Authentication Protocol (CHAP)**, **Microsoft CHAP (MS-CHAP)** of **Microsoft CHAP versie 2 (MS-CHAP v2)**

      - **Certificaten**: kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

        Selecteer **OK** om uw wijzigingen op te slaan.

      - **Identiteitsprivacy (externe identiteit)**: voer de tekst in die wordt verzonden als reactie op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

  - **PEAP**: voer ook het volgende in:

    - **Vertrouwelijke server** - **Basiscertificaat voor servervalidatie**: kies een profiel voor een bestaand vertrouwd basiscertificaat. Dit certificaat wordt aangeboden aan de server wanneer de client verbinding met het netwerk maakt, en wordt gebruikt om de verbinding te verifiëren.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Clientverificatie**: kies een **verificatiemethode**. Uw opties zijn:

      - **Gebruikersnaam en wachtwoord**: de gebruiker wordt gevraagd om een gebruikersnaam en wachtwoord om de verbinding te verifiëren. Voer ook in:
        - **Niet-EAP-methode voor verificatie (interne identiteit)**: kies hoe u de verbinding verifieert. Zorg ervoor dat u hetzelfde protocol kiest dat op uw Wi-Fi-netwerk is geconfigureerd.

          Uw opties zijn: **Geen** of **Microsoft CHAP versie 2 (MS-CHAP v2)**

      - **Certificaten**: kies het profiel van het SCEP- of PKCS-clientcertificaat dat ook op het apparaat is geïmplementeerd. Dit certificaat is de identiteit die door het apparaat wordt gepresenteerd aan de server om de verbinding te verifiëren.

        Selecteer **OK** om uw wijzigingen op te slaan.

      - **Identiteitsprivacy (externe identiteit)**: voer de tekst in die wordt verzonden als reactie op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben, zoals `anonymous`. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens [wijst u dit profiel toe](device-profile-assign.md).

## <a name="more-resources"></a>Meer bronnen

- Zie [Wi-Fi-instellingen voor apparaten met Android](wi-fi-settings-android.md) voor de instellingen die beschikbaar zijn voor Android-apparaten.
- [Overzicht Wi-Fi-instellingen](wi-fi-settings-configure.md), met inbegrip van andere platformen.