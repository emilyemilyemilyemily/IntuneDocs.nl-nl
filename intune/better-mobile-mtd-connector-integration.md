---
title: Better Mobile-integratie met Intune instellen
titleSuffix: Intune on Azure
description: Integratie van de Better Mobile-connector met Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 7/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.openlocfilehash: aa447721449b2b3733e20d9f65f0253e9123228b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184197"
---
# <a name="integrate-better-mobile-with-intune"></a>Better Mobile integreren met Intune

Voer de volgende stappen uit om de Better Mobile Threat Defense-oplossing te integreren met Intune.

## <a name="before-you-begin"></a>Voordat u begint

> [!NOTE]
> De volgende stappen moeten worden uitgevoerd in de [Better Mobile-beheerconsole](https://aad.bmobi.net).

Zorg ervoor dat u over het volgende beschikt voordat u begint met de integratie van Better Mobile met Intune:

-   Microsoft Intune-abonnement

-   Azure Active Directory-beheerdersreferenties om de volgende machtigingen te verlenen:

    -   Aanmelden en gebruikersprofiel lezen

    -   Toegang tot de map als de aangemelde gebruiker

    -   Mapgegevens lezen

    -   Gegevens van een apparaat verzenden naar Intune

-   Beheerdersreferenties voor toegang tot de beheerconsole van Better Mobile.

### <a name="better-mobile-app-authorization"></a>Autorisatie voor Better Mobile-apps

Het autorisatieproces van de Better Mobile-app is als volgt:

-   De Better Mobile-service toestaan informatie met betrekking tot de status van apparaten naar Intune te communiceren.

-   Better Mobile wordt gesynchroniseerd met het Azure AD Enrollment-groepslidmaatschap om de database van het apparaat te vullen.

-   Toestaan dat Better Mobile-beheerconsole Azure AD-enkelvoudige aanmelding (SSO) gebruikt.

-   De app Better Mobile toestaan zich aan te melden met Azure AD-eenmalige aanmelding.

## <a name="to-set-up-better-mobile-integration"></a>Better Mobile-integratie instellen

1. Ga naar [-beheerconsole](https://aad.bmobi.net) en meld u aan met uw referenties.
2. Kies **integratie** > **EMM/MDM** > **ACCOUNT TOEVOEGEN**.

     ![Better Mobile-beheerconsole](media/better_mobile_console.png)
 
3. Kies **Intune**.
4. Naast **ACCOUNTNAAM** typt u een descriptor. 
5. Voer uw Intune-referenties in het venster voor **aanmelden bij Microsoft** in.
6. Kies in het venster **Aangevraagde machtigingen** de optie **Accepteren**.
7. Zoek naar de Azure AD-beveiligingsgroepen waarmee Better Mobile apparaten moet synchroniseren en selecteer ze in de lijst. Selecteer vervolgens **Doorgaan**.
8. Selecteer **Voltooid**.
9. De pagina **Account toevoegen** wordt opnieuw weergegeven. Sluit de pagina. 

## <a name="next-steps"></a>Volgende stappen

-   [Betere client-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)