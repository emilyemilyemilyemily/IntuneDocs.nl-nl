---
title: Voorwaardelijke toegang voor Exchange in Microsoft Intune controleren
titlesuffix: ''
description: De naleving van voorwaardelijke toegang bewaken voor On-Premises Exchange en Exchange Online via Intune Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 20a99290d2a84c22bc2bee823d7a3bb42e43aced
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180575"
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>De naleving van voorwaardelijke toegang in Intune controleren voor Exchange On-Premises en Exchange Online

Vanaf versie Intune 1704 kunnen beheerders rapportagegegevens weergeven met betrekking tot Exchange ActiveSync-apparaatrecords die zijn gesynchroniseerd met Intune via on-premises Exchange Connector of Intune Service to Service Connector (Exchange Online-connector). De nalevingsrapportage van voorwaardelijke toegang biedt een overzicht van apparaten met verschillende synchronisatiestatussen:

-   **Toestaan**

-   **Blokkeren**

-   **Quarantaine**

## <a name="to-monitor-conditional-access-compliance"></a>Naleving van voorwaardelijke toegang bewaken

1.  Ga naar [Azure Portal](https://portal.azure.com/) en meld u aan met uw Intune-referenties.

2.  Nadat u zich hebt aangemeld, ziet u het **Azure-dashboard**.

3.  Kies  **Alle services**  in het linkermenu en typ dan  **Intune**  in het filtertekstvak.

4.  Kies  **Intune**. Vervolgens ziet u het **Intune-dashboard**.

5.  Kies **Voorwaardelijke toegang** en kies vervolgens **Overzicht**.

6.  Kies een van de drie gebieden (**Toegestaan**, **Geblokkeerd** of **Quarantaine**) op de grafiek om uw rapport van de naleving van het voorwaardelijke toegangsbeleid weer te geven.

    ![Afbeelding van de dashboard voor voorwaardelijke toegang](./media/CA-reporting-intune-1.png)

Als u een van de drie gebieden hebt gekozen, kunt u meer details weergeven over apparaten die worden toegestaan, geblokkeerd of in quarantaine worden geplaatst.

U kunt ook inzoomen op bepaalde apparaten voor meer informatie. Het apparaat in de volgende afbeelding is bijvoorbeeld geblokkeerd. Intune biedt de mogelijkheid om bedrijfsgegevens uit het deelvenster voor het rapport van de naleving van voorwaardelijke toegang te verwijderen.

![Afbeelding van een rapport van apparaatdetails voor voorwaardelijke toegang](./media/CA-reporting-intune-3.png)

In het deelvenster Apparaatdetails ziet u meer informatie:

-   **Overzicht:** hier kunt u apparaateigenschappen bekijken, zoals de OS-versie, het apparaatmodel, het eigendom, het serienummer, de fabrikant, het telefoonnummer en de laatste keer dat het apparaat is ingecheckt.

-   **Eigenschappen:** hier kunt u het apparaateigendom instellen (persoonlijk of bedrijfseigendom).

-   **Hardware:** biedt de informatie die u in het overzicht ziet en ook opslagdetails (totale ruimte en vrije schijfruimte), systeembehuizing, netwerkdetails, netwerkservice en meer blokkeringsdetails van voorwaardelijke toegang.

-   **Gedetecteerde apps:** hier ziet u alle toepassingen die op uw apparaat zijn geïnstalleerd. U kunt de lijst met geïnstalleerde apps ook exporteren naar een CSV-indeling.

-   **Compatibiliteit:** hier worden alle details van het nalevingsbeleid van het apparaat weergegeven.

-   **Apparaatconfiguratie:** hier ziet u alle configuratiedetails van het apparaat.

-   **Toegang tot Exchange:** hier vindt u meer informatie over de apparaatstatus na het toepassen van beleid voor voorwaardelijke toegang.
