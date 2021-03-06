---
title: Apparaatbeperkingen voor Android-werkprofielen in Microsoft Intune - Azure | Microsoft Docs
description: Op apparaten met een Android Enterprise-profiel kunt u beperkingen instellen voor bepaalde instellingen op het apparaat, zoals voor kopiëren en plakken, het weergeven van meldingen, app-machtigingen, het delen van gegevens, de wachtwoordlengte, mislukte aanmeldpogingen, het gebruik van vingerafdrukken om te ontgrendelen, het opnieuw gebruiken van wachtwoorden en het delen van zakelijke contactpersonen via Bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f0270818a03c68afd24e32d86a9c1f847e2f2ee2
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181986"
---
# <a name="work-device-restriction-settings-in-intune"></a>Work-apparaatbeperkingsinstellingen in Intune

In dit artikel vindt u meer informatie over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met een Android Enterprise-profiel.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Werkprofielinstellingen

### <a name="general-settings"></a>Algemene instellingen

- **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen**: hiermee beheert u het kopiëren en plakken tussen zakelijke apps en persoonlijke apps. Kies **Blokkeren** om blokkeren in te schakelen. Kies **Niet geconfigureerd** om blokkeren uit te schakelen.
- **Gegevens delen tussen werkprofiel en persoonlijk profiel**: hiermee kunt u bepalen of apps in het werkprofiel gegevens mogen delen met apps in het persoonlijke profiel. Met deze instelling worden de deelacties binnen toepassingen bepaald, zoals de optie **Delen…** in de Chrome-browser-app. Deze instelling geldt niet voor kopiëren en plakken op het klembord. In tegenstelling tot de [beleidsinstellingen voor de beveiliging van apps](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) worden de instellingen voor apparaatbeperkingen beheerd via de Intune-portal en wordt de partitie voor Android-werkprofielen gebruikt om beheerde apps te isoleren. U kunt kiezen uit:
  - **Delen buiten grenzen toestaan**: dit is de standaardinstelling voor het delen van gegevens van het apparaat en deze is afhankelijk van de Android-versie. Delen van het persoonlijke profiel naar het werkprofiel is standaard toegestaan. Delen van het werkprofiel naar het persoonlijke profiel is standaard geblokkeerd. Met deze instelling wordt voorkomen dat er gegevens worden gedeeld van het werkprofiel met het persoonlijke profiel. Google blokkeert niet delen van het persoonlijke profiel naar het werkprofiel op apparaten met versie 6.0 of hoger.
  - **Met de apps in het werkprofiel kunnen aanvragen voor het delen van het persoonlijke profiel worden verwerkt**: hiermee kunt u de ingebouwde Android-functie inschakelen waarmee het delen van gegevens vanuit het persoonlijke profiel naar het werkprofiel is toegestaan. Wanneer dit is ingeschakeld, kan een deelverzoek van een app in het persoonlijke profiel worden gedeeld met apps in het werkprofiel. Dit is de standaardinstelling voor Android-apparaten met een oudere versie dan 6.0.
  - **Standaardbeperkingen voor delen**: biedt de mogelijkheid om in beide richtingen buiten de grenzen van het werkprofiel te delen. Wanneer u deze instelling selecteert, kunnen apps met het werkprofiel gegevens delen met apps in het persoonlijke profiel die geen badge hebben. Met deze instelling kunnen beheerde apps in het werkprofiel gegevens delen met apps aan de onbeheerde zijde van het apparaat. Gebruik deze instelling daarom zorgvuldig.

- **Werkprofielmeldingen terwijl het apparaat is vergrendeld**: hiermee kunt u bepalen of de apps in het werkprofiel gegevens in meldingen kunnen weergeven wanneer het apparaat is vergrendeld.
- **Standaardapp-machtigingen**: hiermee stelt u het standaardmachtigingsbeleid in voor alle apps in het werkprofiel. Vanaf Android 6 wordt de gebruiker gevraagd bepaalde vereiste machtigingen aan apps toe te kennen wanneer de app wordt gestart. Met deze beleidsinstelling kunt u in het werkprofiel bepalen of gebruikers wordt gevraagd om machtigingen toe te kennen voor alle apps in het werkprofiel. U kunt bijvoorbeeld een app aan het werkprofiel toewijzen waarvoor toegang tot de locatie is vereist. Normaal gesproken wordt de gebruiker gevraagd of hij de app toegang tot de locatie wil geven. Gebruik dit beleid om automatisch machtigingen te verlenen zonder om bevestiging te vragen, automatisch machtigingen te weigeren zonder om bevestiging te vragen, of om de eindgebruiker te laten beslissen. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Vragen**
  - **Automatisch verlenen**
  - **Automatisch weigeren**

    U kunt ook een app-configuratiebeleid gebruiken om machtigingen voor afzonderlijke apps te verlenen (**Client-apps** > **App-configuratiebeleid**).

- **Accounts toevoegen en verwijderen**

   Hiermee voorkomt u dat eindgebruikers handmatig accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen.

   Als u de Gmail-app bijvoorbeeld implementeert in een Android-werkprofiel, kunt u verhinderen dat eindgebruikers accounts toevoegen aan of verwijderen uit dit werkprofiel.

- **Contactpersonen delen via Bluetooth**: hiermee krijgt u toegang tot werkcontactpersonen op een ander apparaat, zoals een auto, dat via Bluetooth is gekoppeld. Standaard is deze instelling niet geconfigureerd en worden contactpersonen met een werkprofiel niet weergegeven. Selecteer **Inschakelen** om het delen hiervan toe te staan en contactpersonen met een werkprofiel weer te geven. Deze instelling is van toepassing op Android-apparaten met een werkprofiel met Android OS v6.0 en hoger. Door deze instelling in te schakelen, kunnen bepaalde Bluetooth-apparaten werkcontactpersonen cachen bij de eerste verbinding. Als u dit beleid uitschakelt na een eerste synchronisatie, zijn de werkcontactpersonen van een Bluetooth-apparaat niet meteen verwijderd.

- **Schermopname**: hiermee blokkeert u de schermopname in het werkprofiel op het apparaat. U voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben.

- **Beller-id zakelijk contactpersoon in persoonlijk profiel weergeven**: indien ingeschakeld (niet-geconfigureerd), worden de details van een beller die een zakelijke contactpersoon is, weergegeven in het persoonlijke profiel. Indien geblokkeerd, wordt het nummer van deze zakelijke contactpersoon niet weergegeven in het persoonlijke profiel. Van toepassing op Android OS v6.0 en nieuwere versies.

- **Camera**: hiermee blokkeert u de camera in het werkprofiel op het apparaat. De camera aan de persoonlijke zijde wordt niet beïnvloed door de instelling.

### <a name="work-profile-password"></a>Werkprofielwachtwoord

- **Werkprofielwachtwoord vereisen**: van toepassing op Android 7.0 en hoger waarvoor het werkprofiel is ingeschakeld. Definieer een beleid voor wachtwoordcodes dat alleen van toepassing is op de apps in het werkprofiel. De eindgebruiker kan standaard de twee afzonderlijk gedefinieerde pincodes gebruiken, maar kan er ook voor kiezen om de twee gedefinieerde pincodes te combineren in de sterkste van de twee.
- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal tekens op waaruit het wachtwoord moet bestaan (**4**-**16**).
- **Maximum aantal minuten van inactiviteit voordat het werkprofiel wordt vergrendeld**: selecteer de hoeveelheid tijd voordat het werkprofiel wordt vergrendeld. De gebruiker moet vervolgens zijn referenties invoeren om weer toegang te krijgen.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer in hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het werkprofiel wordt gewist van het apparaat.
- **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**).
- **Vereist wachtwoordtype**: selecteer het type wachtwoord dat moet worden ingesteld op het apparaat. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Vereist**
  - **Ten minste numeriek**
  - **Numeriek complex**: herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt (van **1**-**24**).
- **Ontgrendelen met vingerafdruk**: blokkeren dat een eindgebruiker de vingerafdrukscanner van het apparaat gebruikt om het apparaat te ontgrendelen
- **Smart Lock en andere trustagenten**: hiermee kunt u de functie Smart Lock beheren op compatibele apparaten. Met deze telefoonfunctie, ook wel trust- of vertrouwensagent genoemd, kunt u het werkprofielwachtwoord uitschakelen of overslaan als het apparaat zich op een vertrouwde locatie bevindt. Hiermee kan bijvoorbeeld het wachtwoord van het werkprofiel worden overgeslagen wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. Gebruik deze instelling om te voorkomen dat gebruikers Smart Lock configureren.

## <a name="device-password"></a>Wachtwoord van apparaat

- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal tekens op waaruit het wachtwoord moet bestaan (**4**-**14**).
- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: selecteer de hoeveelheid tijd voordat een inactief apparaat automatisch wordt vergrendeld.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer in hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat alle gegevens worden gewist van het apparaat.
- **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**).
- **Vereist wachtwoordtype**: selecteer het type wachtwoord dat moet worden ingesteld op het apparaat. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Vereist**
  - **Ten minste numeriek**
  - **Numeriek complex**: herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt (van **1**-**24**).
- **Ontgrendelen met vingerafdruk**: blokkeren dat een eindgebruiker de vingerafdrukscanner van het apparaat gebruikt om het apparaat te ontgrendelen.
- **Smart Lock en andere trustagenten**: hiermee kunt u de functie Smart Lock beheren op compatibele apparaten. Met deze telefoonfunctie, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt. Hiermee kan bijvoorbeeld het wachtwoord van het werkprofiel worden overgeslagen wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. Gebruik deze instelling om te voorkomen dat gebruikers Smart Lock configureren.

## <a name="system-security"></a>Systeembeveiliging

- **Bedreigingenscan voor apps**: hiermee kunt u afdwingen dat de instelling **Apps controleren** is ingeschakeld voor werk- en privéprofielen.

   > [!Note]
   > Deze instelling werkt alleen voor apparaten met Android O en later.

## <a name="connectivity"></a>Connectiviteit

- **AlwaysOn VPN**: kies **Inschakelen** om in te stellen dat een VPN-client automatisch verbinding maakt en opnieuw verbinding maakt met het VPN. AlwaysOn VPN-verbindingen blijven verbonden of maken direct verbinding wanneer gebruikers hun apparaat vergrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. 

  Kies **Niet geconfigureerd** om AlwaysOn VPN voor alle VPN-clients uit te schakelen. 

  > [!IMPORTANT]
  > Implementeer slechts één AlwaysOn VPN-beleid per apparaat. Het implementeren van meerdere AlwaysOn VPN-beleidsregels op één apparaat wordt niet ondersteund.

- **VPN-client**: kies een VPN-client die ondersteuning biedt voor AlwaysOn. Uw opties zijn:
  - Cisco AnyConnect
  - F5-toegang
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Aangepast
    - **Pakket-id**: voer de pakket-id in van de app in Google Play. Als de URL voor de app in Google Play bijvoorbeeld `https://play.google.com/store/details?id=com.contosovpn.android.prod` is, is de pakket-id `com.contosovpn.android.prod`.

    > [!IMPORTANT]
    >  - De VPN-client die u kiest moet op het apparaat worden geïnstalleerd en moet VPN per app in werkprofielen ondersteunen. Anders treedt er een fout op. 
    >  - U dient de VPN-client-app goed te keuren in de **Beheerde Google Play Store**, de app te synchroniseren naar Intune en de app te implementeren op het apparaat. Nadat u dit hebt gedaan, is de app geïnstalleerd in het werkprofiel van de gebruiker.
    >  - Er zijn bekende problemen bij het gebruik van VPN per app met F5 Access voor Android 3.0.3. Zie [Releaseopmerkingen voor F5 Access voor Android 3.0.3](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-3.html#relnotes_known_issues_f5_access_android) voor meer informatie.

- **Vergrendelingsmodus**: kies **Inschakelen** om af te dwingen dat al het verkeer de VPN-tunnel gebruikt. Als er geen VPN-verbinding is ingesteld, heeft het apparaat geen toegang tot het netwerk.

  Kies **Niet geconfigureerd** om toe te staan dat verkeer via de VPN-tunnel of via het mobiele netwerk gaat.

## <a name="next-step"></a>Volgende stap

[Profielen toewijzen](device-profile-assign.md) aan gebruikers en apparaten.
