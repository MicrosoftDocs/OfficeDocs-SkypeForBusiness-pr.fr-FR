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
description: Découvrez comment configurer le routage direct Microsoft pour connecter votre infrastructure de téléphonie locale au système téléphonique Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf6a180b558edad23450fad3991ee2c646f6cf55
ms.sourcegitcommit: 830357674103c0c5c99bd73d40261afe02a2da49
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/09/2022
ms.locfileid: "67291400"
---
# <a name="configure-direct-routing"></a>Configurer le routage direct

Le routage direct vous permet de connecter votre infrastructure de téléphonie locale à Microsoft Teams. L’article répertorie les étapes générales requises pour connecter un contrôleur de frontière de session local (SBC) pris en charge au routage direct, et comment configurer les utilisateurs teams pour qu’ils utilisent le routage direct pour se connecter au réseau téléphonique commuté (RTC). Cet article fournit des liens vers les articles associés pour plus d’informations.  

Pour plus d’informations sur la possibilité que le routage direct soit la solution appropriée pour votre organisation, consultez les [options de connectivité RTC](pstn-connectivity.md). Pour plus d’informations sur les prérequis et la planification de votre déploiement, consultez [Planifier le routage direct](direct-routing-plan.md).

Pour suivre les étapes décrites dans cet article, les administrateurs doivent connaître les applets de commande PowerShell. Pour plus d’informations sur l’utilisation de PowerShell, consultez [Configurer votre ordinateur pour Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Avant d’effectuer les étapes décrites dans ces articles, Microsoft vous recommande de confirmer que votre SBC a déjà été configuré comme recommandé par votre fournisseur SBC : 

- [Documentation sur le déploiement d’AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentation sur le déploiement Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentation sur le déploiement des communications du ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentation de déploiement TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentation sur le déploiement metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Pour obtenir la liste complète des contrôleurs SBC pris en charge, consultez [Contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md).

Pour configurer le système téléphonique et permettre aux utilisateurs d’utiliser le routage direct, procédez comme suit : 

- **Étape 1.** [Connecter le SBC avec le système téléphonique et valider la connexion](direct-routing-connect-the-sbc.md)
- **Étape 2.** [Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale](direct-routing-enable-users.md)
- **Étape 3.** [Configurer le routage des appels](direct-routing-voice-routing.md)
- **Étape 4.** [Traduire des nombres dans un autre format](direct-routing-translate-numbers.md) 

Si vous configurez un SBC pour plusieurs locataires, vous souhaiterez également lire [Configurer un SBC pour plusieurs locataires](direct-routing-sbc-multiple-tenants.md).

## <a name="support-boundaries"></a>Limites de prise en charge
Microsoft ne prend en charge le système téléphonique avec routage direct que lorsqu'il est utilisé avec des périphériques certifiés. En cas de problème, vous devez d’abord contacter le support client de votre fournisseur SBC. Si nécessaire, le fournisseur SBC transmettra le problème à Microsoft par les canaux internes. Microsoft se réserve le droit de rejeter les cas de support où un appareil non certifié est connecté au système téléphonique par le biais du Direct Routing. Si Microsoft détermine que le problème de routage direct d’un client concerne l’appareil SBC d’un fournisseur, le client devra contacter de nouveau le fournisseur SBC pour obtenir de l’aide.

## <a name="related-topics"></a>Rubriques connexes

[Planifier votre solution vocale](cloud-voice-landing-page.md)

[Options de connectivité RTC](pstn-connectivity.md)

[Planifier le routage direct](direct-routing-plan.md)
