---
title: Wachtwoordcode opnieuw instellen op Windows-apparaten met Microsoft Intune - Azure | Microsoft Docs
description: Om de wachtwoordcode op Windows-apparaten opnieuw in te stellen, installeert u de Microsoft Pin Reset Service en Microsoft Pin Reset Client, maakt u een apparaatbeleid met uw Azure Active Directory-id en stelt u vervolgens de wachtwoordcode opnieuw in de Azure Portal in met Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 36ed7a4dda91cfcc3cc4b97cc9ab8872b0a2c80e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189143"
---
# <a name="reset-the-passcode-on-windows-devices-using-intune"></a>De wachtwoordcode opnieuw instellen op Windows-apparaten met Intune

U kunt de wachtwoordcode voor Windows-apparaten opnieuw instellen. De functie voor het opnieuw instellen van de wachtwoordcode gebruikt de Microsoft Pin Reset Service om een nieuwe wachtwoordcode te genereren voor apparaten met Windows 10 Mobile. 

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows 10 Mobile met Creators Update en hoger (lid van Azure AD-domein).

De volgende platformen worden **niet** ondersteund:
- Windows
- iOS
- macOS
- Android

## <a name="authorize-the-pin-reset-services"></a>De PIN Reset-services autoriseren

Als u de wachtwoordcode op Windows-apparaten opnieuw wilt instellen, moet u de PIN Reset-service vrijgeven voor uw Intune-tenant.

1. Ga naar [Microsoft PIN Reset Service-productie](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) en meld u aan met het tenantbeheerdersaccount.
2. **Accepteer** de toestemming zodat de PIN Reset-service toegang krijgt tot uw account: ![Het verzoek van de PIN Reset Server om toestemming accepteren](./media/pin-reset-service-home-screen.png)
3. Ga naar [Microsoft PIN Reset Client-productie](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) en meld u aan met het tenantbeheerdersaccount. **Accepteer** de toestemming zodat de PIN Reset Client toegang krijgt tot uw account.
4. In de [Azure Portal](https://portal.azure.com) controleert u of de PIN Reset-services worden vermeld in de bedrijfstoepassingen (alle toepassingen): ![machtigingenpagina PIN Reset-service](./media/pin-reset-service-application.png)

> [!NOTE]
> Nadat u de verzoeken om de pincode opnieuw in te stellen hebt geaccepteerd, krijgt u mogelijk een `Page not found`-bericht of lijkt het alsof er niets gebeurt. Dit gedrag is normaal. Controleer of de twee PIN Reset-toepassingen voor uw tenant worden vermeld.

## <a name="configure-windows-devices-to-use-pin-reset"></a>Windows-apparaten configureren voor de service PIN Reset

Als u de service PIN Reset wilt configureren op Windows-apparaten die u beheert, gebruikt u een [aangepast apparaatbeleid van Intune Windows 10](custom-settings-windows-10.md). Configureer het beleid met behulp van de volgende Configuration Service Provider (CSP) van Windows:

**Het apparaatbeleid gebruiken** - `./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery`

Vervang *tenant-id* door uw Azure AD Directory-id, die wordt vermeld in de **Eigenschappen** van Azure Active Directory in de [Azure Portal](https://portal.azure.com).

Stel de waarde voor deze CSP in op **Waar**.

> [!TIP]
> Nadat u het beleid hebt gemaakt, wijst u het toe aan een groep (of implementeert u het). Het beleid kan worden toegewezen aan gebruikersgroepen of aan apparaatgroepen. Als u het toewijst aan een gebruikersgroep , kan de groep gebruikers omvatten met andere apparaten, zoals IOS. Technisch gezien is het beleid niet van toepassing, maar deze apparaten worden wel genoemd in de statusdetails.

## <a name="reset-the-passcode"></a>De wachtwoordcode opnieuw instellen

1. Meld u aan bij [Azure Portal](https://portal.azure.com). 
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Selecteer het apparaat waarvan u de wachtwoordcode opnieuw wilt instellen. Selecteer **Nieuwe wachtwoordcode** in de apparaateigenschappen.
5. Selecteer **Ja** om te bevestigen. De wachtwoordcode wordt gegenereerd en wordt gedurende zeven dagen weergegeven in de portal.

## <a name="next-step"></a>Volgende stap

Als het opnieuw instellen van de wachtwoordcode mislukt, kunt u in de portal een koppeling volgen voor meer informatie.
