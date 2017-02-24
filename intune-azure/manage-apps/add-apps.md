---
title: Apps toevoegen aan Microsoft Intune | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: met deze procedures kunt u ervoor zorgen dat uw apps in Intune gereed zijn voor toewijzing aan gebruikers en apparaten. '
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 969ce8deae9142944f3481172277dc252baa5779
ms.openlocfilehash: a7838f57b2eb8bd36a875f7b5b001b12eafcbf8d

---

# <a name="how-to-add-an-app"></a>Een app toevoegen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Voordat u apps kunt beheren en toewijzen, moet u deze toevoegen aan Intune. Intune biedt ondersteuning voor een breed scala aan verschillende typen apps en de opties voor elk type kunnen afwijken.

Intune ondersteunt het toevoegen en toewijzen van de volgende typen apps:

![Typen apps die worden ondersteund door Intune](./media/app-types.png)

De volgende platformen worden ondersteund. Klik op een van de onderwerpen voor meer informatie over het toevoegen van elk type app.

- [Line-of-business-apps voor Android](/intune-azure/manage-apps/android-lob-app)
- [Android Store-apps](/intune-azure/manage-apps/android-store-app)
- [Line-of-business-apps voor iOS](/intune-azure/manage-apps/ios-lob-app)
- [iOS Store-apps](/intune-azure/manage-apps/ios-store-app)
- [Web-apps (voor alle platformen)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1 Store-apps](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows Store-apps](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Wanneer u een app vanuit een App Store toevoegt en implementeert, moeten eindgebruikers beschikken over een account bij die Store om de app te kunnen installeren.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Categorieën voor apps maken en bewerken 

App-categorieën kunnen worden gebruikt om apps te sorteren, zodat eindgebruikers deze sneller kunnen vinden in de bedrijfsportal. U kunt een of meer categorieën toewijzen aan een app, bijvoorbeeld **Ontwikkelaars-apps** of **Communicatie-apps**. Als u een app aan Intune toevoegt, kunt u de gewenste categorie selecteren. Aan de hand van de platformenpecifieke onderwerpen kunt u een app toevoegen en categorieën toewijzen. Als u uw eigen categorieën wilt maken en bewerken, gebruikt u de volgende procedure: 

1. Meld u aan bij Azure Portal. 
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**. 
3. Kies **Apps beheren** op de blade **Intune**. 
4. Kies **Instellen** > **App-categorieën** in de workload **Mobiele apps**. 
5. Op de blade **App-categorieën** wordt een lijst met de huidige categorieën weergegeven. Kies een van de volgende acties: 
    - **Een categorie maken**: voer op de blade **Categorie maken** een naam voor de nieuwe categorie in. Namen kunnen slechts in één taal worden ingevoerd en worden niet door Intune vertaald. Wanneer u klaar bent, klikt u op **Maken**.
    - **Een categorie bewerken**: kies voor elke categorie in de lijst '**... **'. Geef op de blade **Eigenschappen** een nieuwe naam voor de categorie op of verwijder de categorie. --->






<!--HONumber=Feb17_HO1-->

