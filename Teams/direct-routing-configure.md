---
title: Configurer le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Apprenez à configurer le routage direct du système Microsoft Phone pour connecter votre infrastructure de téléphonie locale à Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701292"
---
# <a name="configure-direct-routing"></a>Configurer le routage direct

Le routage direct du système Microsoft Phone vous permet de connecter votre infrastructure de téléphonie locale à Microsoft Teams. Cet article répertorie les étapes principales requises pour connecter un contrôleur de bordure de session locale pris en charge (SBC) au routage direct et configurer les utilisateurs de teams pour se connecter au réseau téléphonique public commuté (RTC). Cet article fournit des liens vers les articles associés pour plus d’informations.  

Pour savoir si le routage direct est la solution adaptée à votre organisation, reportez-vous à la section [routage direct du système téléphonique](direct-routing-landing-page.md). Pour plus d’informations sur les conditions préalables et la planification de votre déploiement, voir [planifier le routage direct](direct-routing-plan.md).

> [!Tip]
> Vous pouvez également regarder la session suivante pour en savoir plus sur les avantages du routage direct, la planification et la façon de le déployer : le [routage directe dans Microsoft teams](https://aka.ms/teams-direct-routing).

Pour suivre les étapes décrites dans cet article, les administrateurs doivent vous familiariser avec les applets de cmdlet PowerShell. Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Avant d’effectuer les étapes décrites dans les articles suivants, Microsoft vous recommande de vérifier que votre SBC a déjà été configuré conformément aux recommandations de votre fournisseur de SBC : 

- [Documentation de déploiement AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation relative au déploiement d’Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation sur le déploiement des communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation sur le déploiement de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentation sur le déploiement de switch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Pour obtenir la liste complète des commandes SBCs prises en charge, consultez la [liste des contrôleurs de bordure de session certifiés pour le routage direct](direct-routing-border-controllers.md).

Pour configurer le système Microsoft Phone et permettre aux utilisateurs d’utiliser le routage direct, procédez comme suit : 

- **Étape 1.** [Connecter l’SBC avec un système Microsoft Phone et valider la connexion](direct-routing-connect-the-sbc.md)
- **Étape 2.** [Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale](direct-routing-enable-users.md)
- **Étape 3.** [Configurer le routage de la voix](direct-routing-voice-routing.md)
- **Étape 4.** [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 

Si vous configurez une SBC pour plusieurs clients, vous devez également lire [configurer une SBC pour plusieurs clients](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Voir aussi

[Routage direct via le système téléphonique](direct-routing-landing-page.md)

[Planifier le routage direct](direct-routing-plan.md)

