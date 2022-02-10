---
title: Configurer le routage direct
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
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
description: Découvrez comment configurer le routage Microsoft Direct pour connecter votre infrastructure téléphonique locale à Teams Système téléphonique.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b72a51008e2a5d55b57809ab5e8ae989f4ed3ec7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518576"
---
# <a name="configure-direct-routing"></a>Configurer le routage direct

Le routage direct vous permet de connecter votre infrastructure téléphonique locale à Microsoft Teams. Cet article répertorie les étapes de haut niveau requises pour connecter un contrôleur de session en ligne local pris en charge au routage direct, et comment configurer les utilisateurs d’Teams de façon à utiliser le routage direct pour se connecter au réseau téléphonique commuté (PSTN). Cet article est associé à des articles pour plus d’informations.  

Pour plus d’informations sur l’option de routage direct adaptée à votre organisation, voir [les options de connectivité RSTN](pstn-connectivity.md). Pour plus d’informations sur les conditions préalables et la planification de votre déploiement, voir [Plan de routage direct](direct-routing-plan.md).

Pour suivre les étapes expliquées dans cet article, les administrateurs doivent être familiarisés avec les cmdlets PowerShell. Pour plus d’informations sur l’utilisation de PowerShell, voir [Configurer votre ordinateur pour Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Avant d’effectuer la procédure de ces articles, Microsoft vous recommande de confirmer que votre SBC a déjà été configuré comme recommandé par votre fournisseur SBC : 

- [Documentation sur le déploiement de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation sur le déploiement d’Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation de déploiement de Communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation sur le déploiement des systèmes TE (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentation sur le déploiement de metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Pour obtenir la liste complète des SBCs pris en charge, consultez les [contrôleurs de session en bordure certifiés pour le routage direct](direct-routing-border-controllers.md).

Pour configurer des Système téléphonique et permettre aux utilisateurs d’utiliser le routage direct, suivez ces étapes : 

- **Étape 1.** [Connecter le SBC avec Système téléphonique et valider la connexion](direct-routing-connect-the-sbc.md)
- **Étape 2.** [Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale](direct-routing-enable-users.md)
- **Étape 3.** [Configurer le routage des appels](direct-routing-voice-routing.md)
- **Étape 4.** [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 

Si vous configurez un SBC pour plusieurs locataires, vous pouvez également lire Configurer un [SBC pour plusieurs locataires](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Voir aussi

[Planifier votre solution vocale](cloud-voice-landing-page.md)

[Options de connectivité PSTN](pstn-connectivity.md)

[Planifier le routage direct](direct-routing-plan.md)