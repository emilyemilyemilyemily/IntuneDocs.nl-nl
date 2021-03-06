---
title: iOS- of macOS-apparaatprofielen maken met Microsoft Intune - Azure | Microsoft Docs
description: Voeg een iOS- of macOS-apparaatprofiel toe of maak er een, configureer instellingen voor AirPrint en AirPlay, bepaal de indeling van het startscherm en configureer instellingen voor app-meldingen, gedeelde apparaten, eenmalige aanmelding en het filteren van webinhoud in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 65457a65504b633018bb61851f16c8c65fa1c806
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185675"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Instellingen van apparaatfuncties voor iOS of macOS toevoegen in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met apparaatfuncties kunt u vele instellingen en functies op iOS- en macOS-apparaten beheren, zoals:

- Instellingen voor AirPrint en AirPlay
- Indeling van het startscherm
- Meldingen van apps
- Configuratie van gedeelde apparaten
- Eenmalige aanmelding instellen
- Webinhoud filteren

In dit artikel leest u basisinformatie over het configureren van functieprofielen voor iOS-apparaten. Daarna kunt u aanvullende artikelen doorlopen om platformspecifieke instellingen te configureren voor uw apparaten.

## <a name="create-a-device-profile"></a>Een apparaatprofiel maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
4. Voer de volgende eigenschappen in:

   - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
   - **Beschrijving:** voer een beschrijving in voor het profiel. (Een beschrijving is optioneel, maar wordt aanbevolen.)
   - **Platform**: selecteer het type platform:
     - **iOS**
     - **macOS**
   - **Profieltype**: selecteer **Apparaatfuncties**.
   - **Instellingen**: welke instellingen u gebruikt, is afhankelijk van het platform dat u kiest. In de volgende artikelen worden de instellingen voor elk profieltype beschreven:

     - [AirPrint-instellingen voor iOS en MacOS](air-print-settings-ios-macos.md)
     - [AirPlay-instellingen voor iOS](airplay-settings-ios.md)
     - [Indelingsinstellingen voor het iOS-startscherm](home-screen-settings-ios.md)
     - [App-meldingsinstellingen voor iOS opgeven](app-notification-settings-ios.md)
     - [Configuratie-instellingen voor gedeelde apparaten voor iOS](shared-device-settings-ios.md)
     - [Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten](sso-ios.md)
     - [Filterinstellingen voor webinhoud in iOS](web-content-filter-settings-ios.md)

5. Wanneer u klaar bent, selecteert u **OK** en kiest u **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en wordt weergegeven in de lijst.

## <a name="next-step"></a>Volgende stap

Zie [Apparaatprofielen toewijzen](device-profile-assign.md) als u dit profiel wilt toewijzen aan groepen.