---
title: Ondertekening en versleuteling van e-mailberichten met S/MIME - Azure | Micrososft Docs
description: S/MIME gebruiken of inschakelen om e-mailberichten te ondertekenen en versleutelen in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: eaa85870b289bb3b65ce997d8610324f43d69452
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185641"
---
# <a name="smime-email-signing-and-encryption-in-intune"></a>Ondertekening en versleuteling van e-mailberichten met S/MIME in Intune

> [!IMPORTANT]
> Er worden enkele verbeteringen aangebracht aan de S/MIME-functie die in dit artikel wordt beschreven. Als gevolg hiervan is de S/MIME-functie tijdelijk uit Intune verwijderd. Wanneer deze functie wordt uitgebracht, wordt deze opmerking verwijderd.

S/MIME biedt via versleuteling en ontsleuteling een extra beveiligingsniveau voor uw e-mailberichten. Microsoft Intune kan S/MIME gebruiken om e-mailberichten te ondertekenen en versleutelen op mobiele apparaten met iOS, Windows, Windows Phone, Android en macOS.

Op iOS-apparaten kunt u een door Intune beheerd e-mailprofiel maken dat gebruikmaakt van S/MIME en certificaten voor ondertekening en versleuteling van binnenkomende en uitgaande e-mailberichten. Op andere platforms wordt S/MIME mogelijk niet ondersteund. Als S/MIME wordt ondersteund, kunt u certificaten installeren die gebruikmaken van S/MIME-ondertekening en -versleuteling. Vervolgens kunnen eindgebruikers S/MIME inschakelen in hun e-mailtoepassing.

Zie [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) (S/MIME voor e-mailondertekening en -versleuteling) voor meer informatie over S/MIME-ondertekening en -versleuteling van e-mailberichten.

## <a name="signing-certificates"></a>Handtekeningcertificaten

Met certificaten die worden gebruikt voor ondertekening kunnen client-e-mail-apps veilig communiceren met de e-mailserver.

Als u handtekeningcertificaten wilt gebruiken, maakt u een sjabloon op de certificeringsinstantie die is gericht op ondertekening. [Het sjabloon Webservercertificaat configureren](https://docs.microsoft.com/windows-server/networking/core-network-guide/cncg/server-certs/configure-the-server-certificate-template) op Microsoft Active Directory Certificeringsinstantie bevat de stappen voor het maken van certificaatsjablonen.

Voor het ondertekenen van certificaten in Intune wordt gebruik gemaakt van PKCS-certificaten. In [PKCS-certificaten configureren en gebruiken](certficates-pfx-configure.md) wordt beschreven hoe u PKCS-certificaten in uw Intune-omgeving implementeert en gebruikt. Deze stappen omvatten:

- De Microsoft Intune-certificaatconnector downloaden en installeren ter ondersteuning van PKCS-certificaataanvragen.
- Een profiel voor een vertrouwd basiscertificaat maken voor uw apparaten. Deze stap omvat het gebruik van vertrouwde basis- en tussencertificaten voor uw certificeringsinstantie en de implementatie van het profiel op apparaten.
- Een PKCS-certificaatprofiel maken met behulp van de certificaatsjabloon die u hebt gemaakt. Met dit profiel zorgt u voor ondertekening van certificaten op apparaten en implementeert u het PKCS-certificaatprofiel op apparaten.

U kunt ook een handtekeningcertificaat voor een specifieke gebruiker importeren. Het handtekeningcertificaat wordt geïmplementeerd op elk apparaat dat door een gebruiker wordt geregistreerd. Voor het importeren van certificaten in Intune gebruikt u de [PowerShell-cmdlets in GitHub](https://github.com/Microsoft/Intune-Resource-Access). Voor de implementatie van een PKCS-certificaat dat in Intune is geïmporteerd en wordt gebruikt voor e-mailondertekening volgt u de stappen in [PKCS-certificaten configureren en gebruiken in Intune](certficates-pfx-configure.md). Deze stappen omvatten:

- De PFX-certificaatconnector voor Microsoft Intune downloaden en installeren. Deze connector levert geïmporteerde PKCS-certificaten aan apparaten.
- S/MIME-e-mailondertekeningscertificaten importeren naar Intune.
- Maak een geïmporteerd PKCS-certificaatprofiel. Dit profiel levert geïmporteerde PKCS-certificaten aan de desbetreffende apparaten van de gebruiker.

## <a name="encryption-certificates"></a>Versleutelingscertificaten

Certificaten die worden gebruikt voor versleuteling zorgen ervoor dat een versleuteld e-mailbericht alleen kan worden ontsleuteld door de beoogde ontvanger. S/MIME-versleuteling is een extra beveiligingslaag die kan worden gebruikt voor e-mailberichten.

Wanneer u een versleuteld e-mailbericht naar een andere gebruiker verstuurt, wordt de openbare sleutel van het versleutelingscertificaat van die gebruiker verkregen en wordt het e-mailbericht dat u verstuurt, versleuteld. De ontvanger ontsleutelt het e-mailbericht met behulp van de persoonlijke sleutel op het apparaat. Gebruikers kunnen een geschiedenis hebben van certificaten die worden gebruikt voor versleuteling van e-mailberichten. Elk van deze certificaten moet worden geïmplementeerd op alle apparaten van een specifieke gebruiker, zodat hun e-mailberichten worden ontsleuteld.

Het maken van e-mailversleutelingscertificaten in Intune wordt afgeraden. Hoewel Intune het uitgeven van PKCS-certificaten voor versleuteling ondersteunt, wordt in Intune een uniek certificaat per apparaat gemaakt. Een uniek certificaat per apparaat is niet ideaal voor een S/MIME-versleutelingsscenario waarin het versleutelingscertificaat moet worden gedeeld met alle apparaten van de gebruiker.

Als u S/MIME-certificaten met Intune wilt implementeren, moet u alle versleutelingscertificaten van de gebruiker naar Intune importeren. Intune implementeert vervolgens alle certificaten op elk apparaat dat door een gebruiker wordt geregistreerd. Voor het importeren van certificaten in Intune gebruikt u de [PowerShell-cmdlets in GitHub](https://github.com/Microsoft/Intune-Resource-Access).

Voor de implementatie van een PKCS-certificaat dat in Intune is geïmporteerd en wordt gebruikt voor e-mailondertekening volgt u de stappen in [PKCS-certificaten configureren en gebruiken in Intune](certficates-pfx-configure.md). Deze stappen omvatten:

- De PFX-certificaatconnector voor Microsoft Intune downloaden en installeren. Deze connector levert geïmporteerde PKCS-certificaten aan apparaten.
- S/MIME-e-mailversleutelingscertificaten importeren in Intune.
- Maak een geïmporteerd PKCS-certificaatprofiel. Dit profiel levert geïmporteerde PKCS-certificaten aan de desbetreffende apparaten van de gebruiker.

 > [!NOTE]
 > Geïmporteerde S/MIME-versleutelingscertificaten worden door Intune verwijderd wanneer de bedrijfsgegevens worden verwijderd of wanneer gebruikers worden uitgeschreven voor beheer. De certificaten worden echter niet ingetrokken door de certificeringsinstantie.

## <a name="smime-email-profiles"></a>S/MIME-e-mailprofielen

Nadat u S/MIME-certificaatprofielen voor ondertekening en versleuteling hebt gemaakt, kunt u [S/MIME inschakelen voor e-mailberichten die in iOS zijn opgesteld](email-settings-ios.md).