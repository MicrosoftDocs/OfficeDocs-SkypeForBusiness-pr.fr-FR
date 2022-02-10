---
title: Routage direct
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur Teams Système téléphonique’aide du routage direct.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fe723ee8347ea96c87cb0a9e85f7794c5e50e01
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518706"
---
# <a name="direct-routing"></a>Routage direct

Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous avez peut-être déployé [des réunions & conférences](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes maintenant prêt à ajouter des charges de travail vocales, et vous avez décidé d’utiliser votre propre opérateur de téléphonie pour la connectivité de réseau téléphonique commuté (PSTN) à l’aide d’Système téléphonique avec un routage direct. Le routage direct vous permet d’utiliser le système téléphonique avec presque tous les opérateurs.

Cet article décrit les principales décisions prises en matière de déploiement pour le routage direct, ainsi que des considérations supplémentaires à prendre en considération, en fonction des besoins de votre organisation. Pour plus d’informations [sur les](cloud-voice-landing-page.md) offres vocales de Microsoft, consultez également planifier votre solution vocale.

## <a name="learn-more-about-direct-routing"></a>En savoir plus sur le routage direct

Les articles suivants fournissent des informations supplémentaires sur la configuration et l’utilisation du routage direct. La configuration du routage direct nécessite une compréhension de la conception du routage PSTN. Vous devez lire tous les articles suivants pour comprendre comment planifier et configurer le routage direct :

- [Planifier le routage direct](direct-routing-plan.md) 
- [Configurer le routage direct](direct-routing-configure.md)
- [Liste des contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md)
- [Contrôler et dépanner le routage direct](direct-routing-monitor-and-troubleshoot.md)

En outre, vous souhaitez peut-être lire les articles suivants selon vos besoins :

-  [Configurer un contrôleur de frontière de session pour plusieurs clients](direct-routing-sbc-multiple-tenants.md)
-  [Migrer vers un routage direct](direct-routing-migrating.md)
-  [Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Regardez la session suivante pour en savoir plus sur le routage direct : [routage direct dans Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Il s’agit des principales décisions à prendre en considération pour le routage direct. 

|Posez-vous la question|Action |
| :------------|:-------|
|Pour quels utilisateurs activer le routage direct ? | Pour plus d’informations, voir [Activer le service de routage direct pour les utilisateurs](direct-routing-configure.md). |
Ai-je les licences requises pour le routage direct ? | Pour plus d’informations, voir [Gestion des licences et autres conditions requises](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considérations en considérations du contrôleur de bordure de session (SBC)

Avec le routage direct, vous connectez votre propre contrôleur de session Border Controller (SBC) directement à Système téléphonique. Pour obtenir la liste des SBCs [certifiés, voir Contrôleurs de session en bordure pris en charge](direct-routing-border-controllers.md).

|Posez-vous la question|Action |
|:------------|:-------|
| Où et comment puis-je déployer des SBCS ? | Pour plus d’informations, [voir Configurer le routage direct](direct-routing-configure.md) | 
Ai-je plusieurs locataires ? | Pour plus d’informations, voir [Configurer un contrôleur de session en bordure pour plusieurs locataires](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considérations en cas de routage vocal

Vous devrez configurer les Système téléphonique router les appels vers des SCS spécifiques.

|Posez-vous la question|Action |
|:------------|:-------|
| Quelles stratégies de routage vocal, utilisation PSTN et itinéraires vocux dois-je créer ? | Pour plus d’informations sur le routage vocal, voir [Configurer le routage vocal](direct-routing-configure.md).
| Quels utilisateurs seront affectés à la stratégie de routage voix que je définisse ? | Consultez les [exemples de la commande Configurer le routage vocal](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Assurez-vous que les appels entrants arrivent dans le client Teams à l’aide de TeamsUpgradePolicy

Le routage direct n’est pris en charge qu’avec Microsoft Teams. Pour recevoir des appels PSTN via un routage direct, vous devez configurer TeamsUpgradePolicy pour vous assurer que les appels entrants soient reçus dans Teams. Les utilisateurs doivent être en mode TeamsOnly, ce que vous pouvez faire en leur attribuant l’instance « UpgradeToTeams » de TeamsUpgradePolicy. 

|Posez-vous la question|Action |
|:------------|:-------|
|Que signifie le mode TeamsOnly ? | Pour plus d’informations, consultez les conseils [sur la migration et l’interopérabilité pour les organisations qui Teams en même temps que d Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md).|
|||


