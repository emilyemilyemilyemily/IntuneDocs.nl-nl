---
# required metadata

title: De toegang tot e-mail beperken bij Exchange Online en de nieuwe Exchange Online Dedicated | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# De toegang tot e-mail beperken bij Exchange Online en de nieuwe Exchange Online Dedicated met Microsoft Intune

Als u een Exchange Online Dedicated-omgeving hebt en wilt weten of deze de nieuwe of oudere configuratie heeft, neem dan contact op met uw accountmanager.

Configureer voorwaardelijke toegang voor Exchange Online in Intune als u de toegang tot e-mail op Exchange Online of uw nieuwe Exchange Online Dedicated-omgeving wilt beheren.
Zie het artikel [De toegang tot e-mail en O365-service beperken](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) voor meer informatie over hoe voorwaardelijke toegang werkt.

>[!IMPORTANT]
>Voorwaardelijke toegang voor pc's en Windows 10 Mobile-apparaten met apps die moderne authenticatie gebruiken, is momenteel niet voor alle klanten van Intune beschikbaar. Als u deze functies al gebruikt, hoeft u geen actie te ondernemen. U kunt deze functies gewoon blijven gebruiken.

>Als u nog geen beleid voor voorwaardelijke toegang hebt gemaakt voor pc's of Windows 10 Mobile voor apps die moderne authenticatie gebruiken, en dat wel wilt doen, moet u hiervoor een aanvraag indienen.  Meer informatie over bekende problemen en hoe u toegang tot deze functie krijgt, vindt u op de [Microsoft Connect-website](http://go.microsoft.com/fwlink/?LinkId=761472).

**Voordat** u voorwaardelijke toegang kunt configureren, moet u:

-   Een **Office 365-abonnement hebben waarin Exchange Online (zoals E3) is inbegrepen**. Gebruikers moeten bovendien een licentie hebben voor Exchange Online.

-  U kunt eventueel de optionele **Microsoft Intune-serviceconnector** configureren, waarmee u [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] koppelt aan Microsoft Exchange Online en u apparaatgegevens kunt beheren via de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-console U hoeft de connector niet te gebruiken om nalevingsbeleid of beleidsregels voor voorwaardelijke toegang te kunnen gebruiken, maar de connector is wel vereist voor het uitvoeren van rapporten die helpen bij het evalueren van de impact van voorwaardelijke toegang.

   > [!NOTE]
   > Configureer de service-naar-serviceconnector niet als u voorwaardelijke toegang wilt gebruiken voor Exchange Online en Exchange On-premises

   Zie [Intune-service-naar-serviceconnector](intune-service-to-service-exchange-connector.md) voor instructies over het configureren van de connector

Wanneer beleid voor voorwaardelijke toegang wordt geconfigureerd en een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet het volgende met het **apparaat** zijn gedaan voordat een gebruiker verbinding kan maken met zijn e-mail:

-   Het apparaat moet zijn **ingeschreven** bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] of lid zijn van een domein.

-  Het apparaat moet zijn **geregistreerd bij Azure Active Directory**. Dit gebeurt automatisch wanneer het apparaat wordt ingeschreven bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Bovendien moet de client-id van Exchange ActiveSync zijn geregistreerd bij Azure Active Directory.

  AAD DRS wordt automatisch geactiveerd voor Intune- en Office 365-klanten. Klanten die de ADFS Device Registration Service al hebben geïmplementeerd, zien geen geregistreerde apparaten in hun on-premises Active Directory.

-   **Zich houden aan** het [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-nalevingsbeleid dat is geïmplementeerd op het apparaat, of lid zijn van een domein dat is gekoppeld aan een lokaal domein.

Als niet aan een voorwaarde voor het beleid voor voorwaardelijke toegang wordt voldaan, krijgt de gebruiker een van de volgende berichten te zien wanneer hij zich aanmeldt.

- Als het apparaat niet is ingeschreven bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] of niet is geregistreerd bij Azure Active Directory, wordt er een bericht weergegeven met instructies over hoe de bedrijfsportal-app moet worden geïnstalleerd, het apparaat moet worden ingeschreven en e-mail moet worden geactiveerd. Dit proces zorgt er ook voor dat de Exchange ActiveSync-id van het apparaat wordt gekoppeld aan het record in Azure Active Directory.

-   Als wordt vastgesteld dat het apparaat niet voldoet aan de regels van het nalevingsbeleid, wordt de eindgebruiker omgeleid naar de website of app van de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-bedrijfsportal. Hier vindt de gebruiker informatie over het probleem en aanwijzingen om dit op te lossen.


Het volgende diagram illustreert de werkstroom die door beleid voor voorwaardelijke toegang wordt gevolgd voor Exchange Online.

![Het diagram illustreert de beslissingspunten die bepalen of een apparaat toegang mag hebben of moet worden geblokkeerd](../media/ConditionalAccess8-1.png)

## Ondersteuning voor mobiele apparaten
U kunt toegang tot e-mail van Exchange Online beperken vanuit **Outlook** en andere **apps die moderne authenticatie gebruiken**:

- Android 4.0 of hoger, Samsung Knox Standard 4.0 of hoger
- iOS 7.1 en hoger
- Windows Phone 8.1 en hoger

 **Moderne authenticatie** houdt aanmelding bij Microsoft Office-clients in op basis van Active Directory Authentication Library (ADAL)

> -   Dankzij verificatie op basis van ADAL is voor Office-clients verificatie via een browser (ook wel passieve verificatie) mogelijk.  De gebruiker wordt hierbij naar een aanmeldingspagina geleid om de verificatie uit te voeren. Deze nieuwe aanmeldingsmethode zorgt voor betere beveiliging, zoals **Multi-Factor Authentication** en **op certificaten gebaseerde verificatie**
> In dit [artikel](https://support.office.com/en-US/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517) vindt u gedetailleerde informatie over de werking van moderne authenticatie.


Op de volgende platforms kunt u toegang tot Exchange-e-mail vanuit de ingebouwde **Exchange ActiveSync-e-mailclient** beperken:

- Android 4.0 of hoger, Samsung Knox Standard 4.0 of hoger

- iOS 7.1 en hoger

- Windows Phone 8.1 en hoger

## Ondersteuning voor pc's

U kunt voorwaardelijke toegang instellen voor pc's waarop Office-bureaubladtoepassingen worden uitgevoerd zodat deze toegang hebben tot **Exchange Online** en **SharePoint Online** als de pc’s aan de volgende vereisten voldoen:

-   Op de pc moet Windows 7.0 of Windows 8.1 worden uitgevoerd.

-   De pc moet lid zijn van een domein of voldoen aan de regels van het nalevingsbeleid.

    De pc moet zijn ingeschreven bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] en voldoen aan het beleid, om te worden beschouwd als een apparaat dat het beleid naleeft.

    Pc’s die lid zijn van een domein, moeten zo zijn ingesteld dat deze [automatisch worden geregistreerd](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) bij Azure Active Directory.

-   [Moderne authenticatie van Office 365-moet zijn ingeschakeld](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) en alle nieuwe Office-updates moeten zijn geïnstalleerd.

    Moderne authenticatie maakt op Active Directory Authentication Library (ADAL) gebaseerde aanmelding beschikbaar op Windows-clients met Office 2013 en zorgt voor betere beveiliging, zoals **Multi-Factor Authentication** en **Verificatie op basis van een certificaat**.

-   Met het instellen van ADFS worden er regels van kracht die niet-moderne verificatieprotocollen blokkeren. Stapsgewijze instructies vindt u in scenario 3: [alle toegang tot O365 blokkeren behalve op browser gebaseerde toepassingen](https://technet.microsoft.com/library/dn592182.aspx)..

## Voorwaardelijke toegang configureren
### Stap 1: nalevingsbeleid configureren en implementeren
Zorg ervoor dat u nalevingsbeleid [maakt](create-a-device-compliance-policy-in-microsoft-intune.md) en [implementeert](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) voor de gebruikersgroepen die ook het beleid voor voorwaardelijke toegang krijgen.


> [!IMPORTANT]
> Als u geen nalevingsbeleid hebt geïmplementeerd, worden de apparaten beschouwd als apparaten die het beleid naleven en wordt toegang tot Exchange toegestaan.

### Stap 2: het effect van het beleid voor voorwaardelijke toegang beoordelen.
U kunt de **inventarisrapporten voor mobiele apparaten** gebruiken om de apparaten te identificeren waarvoor de toegang tot Exchange mogelijk wordt geblokkeerd nadat u het beleid voor voorwaardelijke toegang hebt geconfigureerd.

Configureer hiervoor een verbinding tussen [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] en Exchange met behulp van de [Microsoft Intune-service-naar-serviceconnector](intune-service-to-service-exchange-connector.md).
1.  Ga naar **Rapporten -> Inventarisrapporten voor mobiele apparaten**.
![Schermafbeelding van de rapportpagina van Inventaris van mobiele apparaten](../media/IntuneSA2bMobileDeviceInventoryReport.png)

2.  Selecteer in de rapportparameters de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-groep die u wilt beoordelen en, indien nodig, de apparaatplatforms waarop het beleid wordt toegepast.
3.  Wanneer u de criteria hebt geselecteerd die voldoen aan de behoeften van uw organisatie, kiest u **Rapport weergeven**.
De Rapportviewer wordt geopend in een nieuw venster.
![Schermafbeelding van een voorbeeld van een inventarisrapport voor mobiele apparaten](../media/IntuneSA2cViewReport.PNG)

Nadat u het rapport hebt uitgevoerd, controleert u deze vier kolommen om te bepalen of een gebruiker wordt geblokkeerd:

-   **Beheerkanaal** – geeft aan of het apparaat wordt beheerd door Intune, Exchange ActiveSync of beide.

-   **Geregistreerd bij AAD** – geeft aan of het apparaat is geregistreerd bij de Azure Active Directory (ook wel 'toegevoegd aan werkplek' genoemd).

-   **Compatibel** – geeft aan of het apparaat voldoet aan alle nalevingsbeleidsregels die u hebt geïmplementeerd.

-   **Exchange ActiveSync-id** – op iOS- en Android-apparaten moet de Exchange ActiveSync-id zijn gekoppeld aan de apparaatregistratierecord in Azure Active Directory. Dit gebeurt wanneer de gebruiker in de e-mail met betrekking tot de quarantaine op de koppeling **E-mail activeren** klikt.

    > [!NOTE]
    > Op Windows Phone-apparaten wordt altijd een waarde weergegeven in deze kolom.

Apparaten die deel uitmaken van een doelgroep, krijgen geen toegang tot Exchange tenzij de kolomwaarden overeenkomen met de waarden die in de volgende tabel worden weergegeven:

--------------------------
|Beheerkanaal|Geregistreerd bij AAD|Compliant|Exchange ActiveSync-id|Resulterende actie|
|----------------------|------------------|-------------|--------------------------|--------------------|
|**Beheerd door Microsoft Intune en Exchange ActiveSync**|Ja|Ja|Een waarde wordt weergegeven|Toegang tot e-mail toegestaan|
|Een andere waarde|Nee|Nee|Er wordt geen waarde weergegeven|Toegang tot e-mail geblokkeerd|
----------------------
U kunt de inhoud van het rapport exporteren en de kolom **E-mailadres** gebruiken om uw gebruikers ervan op de hoogte te stellen dat toegang voor hen wordt geblokkeerd.

### Stap 3: gebruikersgroepen configureren voor het beleid voor voorwaardelijke toegang.
Beleid voor voorwaardelijke toegang is gericht op andere Azure Active Directory-beveiligingsgroepen met gebruikers. U kunt ook bepaalde gebruikersgroepen van dit beleid uitsluiten.  Wanneer een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet elk apparaat dat wordt gebruikt, compatibel zijn om toegang te kunnen krijgen tot e-mail.

U kunt deze groepen configureren in het **Office 365-beheercentrum** of in de **Intune-accountportal**..

U kunt twee soorten groepen opgeven in elk beleid:

-   **Doelgroepen**: gebruikersgroepen waarop het beleid wordt toegepast

-   **Uitgesloten groepen**: gebruikersgroepen waarop het beleid niet van toepassing is (optioneel)

Als een gebruiker zich in beide groepen bevindt, wordt het beleid niet op de gebruiker toegepast.

Alleen de doelgroepen van het voorwaardelijk toegangsbeleid worden beoordeeld.

### Stap 4: het beleid voor voorwaardelijke toegang configureren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Beleid** > **Voorwaardelijke toegang** > **Beleid voor Exchange Online**.
![Schermafbeelding van de pagina met beleid voor voorwaardelijke toegang voor Exchange Online](../media/IntuneSA5dExchangeOnlinePolicy.png)

2.  Selecteer op de pagina **Beleid voor Exchange Online** de optie **Beleid voor voorwaardelijke toegang inschakelen voor Exchange Online**..

    > [!NOTE]
    > Als u geen nalevingsbeleid hebt geïmplementeerd, worden apparaten beschouwd als apparaten die het beleid naleven.
    >
    > Ongeacht de nalevingsstatus moeten alle gebruikers die zich in de doelgroep van het beleid bevinden, hun apparaten inschrijven bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

3.  Onder **Toegang voor toepassingen** zijn er, voor apps die moderne authenticatie gebruiken, twee manieren om te kiezen welke platforms het beleid moet toepassen. Ondersteunde platforms zijn Android, iOS, Windows en Windows Phone.

    -   **Alle platforms**

        Hiervoor is vereist dat alle apparaten die worden gebruikt om toegang te krijgen tot **SharePoint Online**, moeten worden ingeschreven in Intune en aan het nalevingsbeleid moeten voldoen.  Elke clienttoepassing die **moderne authenticatie** gebruikt, moet voldoen aan het beleid voor voorwaardelijke toegang. Als het platform momenteel niet door Intune wordt ondersteund, wordt de toegang tot **SharePoint Online** geblokkeerd.
        >[!TIP]
           Mogelijk ziet u deze optie niet als u al voorwaardelijke toegang voor pc’s gebruikt.  Gebruik in plaats hiervan **Specifieke platforms**. Voorwaardelijke toegang voor pc's is momenteel niet voor alle klanten van Intune beschikbaar.   Meer informatie over bekende problemen en hoe u toegang tot deze functie krijgt, vindt u op de [Microsoft Connect-website](http://go.microsoft.com/fwlink/?LinkId=761472).

    -   **Specifieke platforms**

         Het beleid voor voorwaardelijke toegang wordt toegepast op elke clienttoepassing die **moderne authenticatie** gebruikt op de door u geselecteerde apparaatplatforms.

4.  Onder **Exchange ActiveSync-apps** kunt u de toegang tot Exchange Online blokkeren van apparaten die niet aan het nalevingsbeleid voldoen. U kunt ook aangeven of u toegang tot e-mail wilt toestaan of blokkeren wanneer het apparaat niet op een ondersteund platform wordt uitgevoerd. Ondersteunde platforms zijn Android, iOS, Windows en Windows Phone.


5.  Onder **Doelgroepen** selecteert u de Active Directory-beveiligingsgebruikersgroepen waarop het beleid van toepassing moet zijn. U kunt kiezen of u zich wilt richten op alle gebruikers of op een geselecteerde lijst met gebruikersgroepen.
![Schermafbeelding van de pagina met het beleid voor voorwaardelijke toegang van Exchange Online met opties voor doelgroepen en uitgesloten groepen](../media/IntuneSA5eTargetedExemptedGroups.PNG)
    > [!NOTE]
    > Voor gebruikers in **Doelgroepen** wordt het Intune-beleid vervangen door Exchange-regels en -beleid.
    >
    > In Exchange worden alleen in de volgende gevallen regels voor toestaan, blokkeren en in quarantaine plaatsen, en Exchange-beleid afgedwongen:
    >
    > -   De gebruiker heeft geen licentie voor Intune.
    > -   De gebruiker heeft een licentie voor Intune, maar de gebruiker behoort niet tot een beveiligingsgroep die is gedefinieerd in het beleid voor voorwaardelijke toegang.

6.  Onder **Uitgesloten groepen**selecteert u de Active Directory-beveiligingsgebruikersgroepen waarop dit beleid niet van toepassing is. Als een gebruiker zich in beide groepen bevindt, wordt het beleid niet op de gebruiker toegepast.

7.  Als u klaar bent, kiest u **Opslaan**.

-   U hoeft het beleid voor voorwaardelijke toegang niet te implementeren; het wordt direct van kracht.

-   Wanneer een gebruiker een e-mailaccount maakt, wordt het apparaat onmiddellijk geblokkeerd.

-   Als een geblokkeerde gebruiker het apparaat inschrijft bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] en alle eventuele problemen met het niet-naleven van beleid oplost, wordt de toegangsblokkade voor e-mail binnen twee minuten opgeheven.

-   Als de gebruiker het apparaat uitschrijft, wordt de toegang tot e-mail na circa 6 uur geblokkeerd.

**Voor enkele scenario's met voorbeelden van hoe u beleid voor voorwaardelijke toegang configureert om de toegang door apparaten te beperken, verwijzen wij u naar [Voorbeeldscenario's voor het beperken van toegang tot e-mail](restrict-email-access-example-scenarios.md).**

## De compatibiliteit en het beleid voor voorwaardelijke toegang bewaken

#### Apparaten weergeven die geen toegang hebben tot Exchange

In het [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-dashboard kiest u de tegel **Apparaten zonder toegang tot Exchange** om het aantal geblokkeerde apparaten en koppelingen naar meer informatie weer te geven.
![Schermafdruk van het Intune-dashboard met het aantal apparaten waarvoor de toegang tot Exchange is geblokkeerd](../media/IntuneSA6BlockedDevices.PNG)

## Volgende stappen
[Toegang tot SharePoint Online beperken](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Toegang tot Skype voor Bedrijven Online beperken](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->

