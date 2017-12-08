---
title: Gebruikersapparaatkoppeling - Intune-datawarehouse | Microsoft Docs
description: Een lijst met wijzigingen in de API van Intune-datawarehouse.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c47455b0139f7451796257a77859cbd9899a7dd
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/02/2017
---
# <a name="user-device-association"></a>Gebruikersapparaatkoppeling

De entiteit **UserDeviceAssociation** bevat gebruikersapparaatkoppelingen in uw organisatie.

| Naam               | Beschrijving                                                                                      | Voorbeeld                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Een unieke id van gebruiker in het datawarehouse. (surrogaatsleutel).                              | 123                    |
| DeviceKey          | Een unieke id van het apparaat in het datawarehouse.                                            | 123                    |
| CreatedDateTimeUTC | De datum en tijd wanneer de gebruikersapparaatkoppeling is gemaakt. Hiervoor wordt de UTC-notatie gebruikt.                                | 11/23/2016 12:00:00 AM |
| IsDeleted          | Geeft aan dat de gebruiker het apparaat heeft uitgeschreven en dat de koppeling niet meer actueel is. | Waar/onwaar             |
| EndedDateTimeUTC   | De datum en tijd in UTC waarop IsDeleted is gewijzigd in **Waar**.                                              | 23-06-2017 12.00.00 |