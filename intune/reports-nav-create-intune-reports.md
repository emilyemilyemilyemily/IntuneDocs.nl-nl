---
title: Het Intune-datawarehouse gebruiken | Microsoft Docs
description: Gebruik het Intune-datawarehouse om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: db6661dd92b890d711f655a60eb883b417a30d8a
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2017
---
# <a name="use-the-intune-data-warehouse"></a>Het Intune-datawarehouse gebruiken

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik het Intune-datawarehouse om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden. Rapporten kunnen bijvoorbeeld het volgende bevatten:
-   Trend van gebruikers die zich registreren bij Intune, zodat u uw licentieaankopen kunt optimaliseren
-   Uitsplitsing van app- en besturingssysteemversies zodat u de status van mobiele apparaten kunt controleren
-   Registratie- en apparaatnalevingstrends zodat u de implementatie van beleidsupdates soepel kunt laten verlopen

Het datawarehouse biedt u toegang tot meer informatie over uw mobiele omgeving dan Azure Portal. U hebt met het Intune-datawarehouse toegang tot:

  -  Historische Intune-gegevens
  -  Gegevens die dagelijks worden vernieuwd
  -  Een gegevensmodel waarbij de OData-standaard wordt gebruikt

> [!Important]  
> U kunt de meest recente functionaliteit van het datawarehouse met behulp van de bètaversie uitproberen. Voor het gebruik van de bètaversie moet uw URL de queryparameter `api-version=beta` bevatten. De bètaversie biedt functies voordat ze algemeen beschikbaar zijn als een ondersteunde service. Als er nieuwe functies aan Intune worden toegevoegd, kunnen de werking en gegevenscontracten worden gewijzigd. Alle aangepaste code of rapportagemiddelen die afhankelijk zijn van de bètaversie, worden mogelijk onbruikbaar bij nieuwe updates. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**Volgende stappen**

- Haal een koppeling op en gebruik Power BI om inzicht te krijgen. Zie [Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md) (Verbinding maken met het Intune-datawarehouse met Power BI) voor instructies.
- Verkrijg meer informatie over de Intune-datawarehouse-API, het gegevensmodel en relaties tussen entiteiten<!-- , and an example of creating a custom client to retrieve data,--> (zie [Intune-datawarehouse-API](reports-nav-intune-date-warehouse.md)).