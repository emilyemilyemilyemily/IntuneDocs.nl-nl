---
# required metadata

title: Er ontbreekt een vereist certificaat voor uw apparaat | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Er ontbreekt een vereist certificaat voor uw apparaat
Als uw Android-apparaat niet bij Intune is ingeschreven en er ontbreekt een certificaat dat normaal gesproken op uw telefoon is geïnstalleerd, kunt u zich niet bij de bedrijfsportal-app voor Android aanmelden. Wanneer u zich probeert aan te melden, wordt het volgende bericht weergegeven:

![Ontbrekend certificaat voor Android-installatie](./media/andr-cert_install-1-cert_missing.png)

U kunt dit probleem als volgt oplossen en het vereiste certificaat ophalen:

1.  Navigeer in een browser naar deze [pagina voor Digicert-certificaten](https://www.digicert.com/digicert-root-certificates.htm)..

2.  Zoek en download het Baltimore CyberTrust-basiscertificaat (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

3.  Veeg vanaf de bovenkant van het scherm naar beneden om uw meldingenlijst te openen en tik in die lijst op **BaltimoreCyberTrustRoot.crt**.

4.  Accepteer in het scherm **Benoem het certificaat** de standaardcertificaatnaam.

5. Zorg ervoor dat **Gebruik van referenties** is ingesteld op **Worden gebruikt voor VPN en apps** en tik op **OK**.

    ![Naam van certificaat voor Android-installatie](./media/andr-cert_install-2-add_cert_name.png)

6. Sluit de webbrowser en de bedrijfsportal-app.

7. Open de bedrijfsportal-app opnieuw. Nu moet u zich bij de bedrijfsportal-app kunnen aanmelden. Neem contact op met de IT-beheerder als u hulp nodig hebt.

<!--HONumber=May16_HO1-->

