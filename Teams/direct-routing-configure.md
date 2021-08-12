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
description: Découvrez comment configurer Téléphone Microsoft routage système direct pour connecter votre infrastructure téléphonique locale à Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f903511dd4adc439705513f6ef10ed9648d1bbb4aab42ac6dec1aa7bef6064e8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284175"
---
# <a name="configure-direct-routing"></a>Configurer le routage direct

Téléphone Microsoft Le routage direct du système vous permet de connecter votre infrastructure téléphonique locale à Microsoft Teams. Cet article répertorie les étapes de haut niveau requises pour connecter un contrôleur de session en ligne local pris en charge au routage direct, et comment configurer les utilisateurs d’Teams de façon à utiliser le routage direct pour se connecter au réseau téléphonique commuté (PSTN). Cet article est associé à des articles pour plus d’informations.  

Pour savoir si le routage direct est la solution adaptée à votre organisation, voir [Système téléphonique routage direct.](direct-routing-landing-page.md) Pour plus d’informations sur les conditions préalables et la planification de votre déploiement, voir [Plan de routage direct.](direct-routing-plan.md)

> [!Tip]
> Vous pouvez également regarder la session suivante pour en savoir plus sur les avantages du routage direct, comment le planifier et comment le déployer : Routage direct [dans Microsoft Teams.](https://aka.ms/teams-direct-routing)

Pour suivre les étapes expliquées dans cet article, les administrateurs doivent être familiarisés avec les cmdlets PowerShell. Pour plus d’informations sur l’utilisation de PowerShell, voir [Configurer votre ordinateur pour Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Avant d’effectuer la procédure de ces articles, Microsoft vous recommande de confirmer que votre SBC a déjà été configuré comme recommandé par votre fournisseur SBC : 

- [Documentation sur le déploiement de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation sur le déploiement d’Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation de déploiement de Communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation sur le déploiement des systèmes TE (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentation sur le déploiement de metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Pour obtenir la liste complète des SBCS pris en charge, consultez la liste des contrôleurs de session [certifiés pour le routage direct.](direct-routing-border-controllers.md)

Pour configurer Téléphone Microsoft routage direct et permettre aux utilisateurs d’utiliser le routage direct, suivez ces étapes : 

- **Étape 1.** [Connecter SBC avec Téléphone Microsoft et valider la connexion](direct-routing-connect-the-sbc.md)
- **Étape 2.** [Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale](direct-routing-enable-users.md)
- **Étape 3.** [Configurer le routage vocal](direct-routing-voice-routing.md)
- **Étape 4.** [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 

Si vous configurez un SBC pour plusieurs locataires, vous pouvez également lire Configurer un SBC pour [plusieurs locataires.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Voir aussi

[Routage direct via le système téléphonique](direct-routing-landing-page.md)

[Planifier le routage direct](direct-routing-plan.md)