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
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Découvrez le système téléphonique Teams avec routage direct.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff97fc683acd693f867126661c9bf90550ebbe5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269919"
---
# <a name="direct-routing"></a>Routage direct

Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous avez peut-être déployé [des réunions & conférence](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes maintenant prêt à ajouter des charges de travail vocales et vous avez décidé d’utiliser votre propre opérateur téléphonique pour la connectivité rtc (RTC) à l’aide du système téléphonique avec routage direct. Le routage direct vous permet d’utiliser le système téléphonique avec presque tous les opérateurs.

Cet article décrit les principales décisions de déploiement pour le routage direct, ainsi que des considérations supplémentaires que vous souhaiterez peut-être prendre en compte, en fonction des besoins de votre organisation. Vous devez également lire [Planifier votre solution vocale](cloud-voice-landing-page.md) pour plus d’informations sur les offres vocales de Microsoft.

## <a name="learn-more-about-direct-routing"></a>En savoir plus sur le routage direct

Les articles suivants fournissent plus d’informations sur la configuration et l’utilisation du routage direct. La configuration du routage direct nécessite une compréhension de la conception du routage RTC. Vous devez lire tous ces articles pour comprendre comment planifier et configurer le routage direct :

- [Planifier le routage direct](direct-routing-plan.md) 
- [Configurer le routage direct](direct-routing-configure.md)
- [Liste des contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md)
- [Contrôler et dépanner le routage direct](direct-routing-monitor-and-troubleshoot.md)

En outre, vous souhaiterez peut-être lire les articles suivants en fonction de vos besoins :

-  [Configurer un contrôleur de frontière de session pour plusieurs clients](direct-routing-sbc-multiple-tenants.md)
-  [Migrer vers un routage direct](direct-routing-migrating.md)
-  [Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Regardez la session suivante pour en savoir plus sur le routage direct : [Routage direct dans Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Il s’agit des principales décisions à prendre en compte pour le routage direct. 

|Posez-vous la question|Action |
| :------------|:-------|
|Pour quels utilisateurs vais-je activer le routage direct ? | Pour plus d’informations, consultez [Activer les utilisateurs pour le service de routage direct](direct-routing-configure.md). |
Ai-je les licences requises pour le routage direct ? | Pour plus d’informations, consultez [Licences et autres exigences](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considérations relatives au contrôleur de frontière de session (SBC)

Avec le routage direct, vous connectez votre propre contrôleur de frontière de session (SBC) directement au système téléphonique. Pour obtenir la liste des contrôleurs de base de données certifiés, consultez [Contrôleurs de frontière de session pris en charge](direct-routing-border-controllers.md).

|Posez-vous la question|Action |
|:------------|:-------|
| Où et comment déployer des SBC ? | Pour plus d’informations, consultez [Configurer le routage direct](direct-routing-configure.md) | 
Ai-je plusieurs locataires ? | Pour plus d’informations, consultez [Configurer un contrôleur de bordure de session pour plusieurs locataires](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considérations relatives au routage vocal

Vous devez configurer le système téléphonique pour acheminer les appels vers les SBC spécifiques.

|Posez-vous la question|Action |
|:------------|:-------|
| Quelles stratégies de routage vocal, utilisation RTC et itinéraires vocaux dois-je créer ? | Pour plus d’informations sur le routage vocal, consultez [Configurer le routage vocal](direct-routing-configure.md).
| Quels utilisateurs seront affectés à la stratégie de routage vocal que je définit ? | Consultez les exemples dans [Configurer le routage vocal](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Vérifier que les appels entrants arrivent dans le client Teams à l’aide de TeamsUpgradePolicy

Le routage direct est pris en charge uniquement avec Microsoft Teams. Pour recevoir des appels RTC via le routage direct, vous devez configurer TeamsUpgradePolicy pour vous assurer que les appels entrants sont reçus dans Teams. Les utilisateurs doivent être en mode TeamsOnly, ce que vous pouvez faire en leur affectant l’instance « UpgradeToTeams » de TeamsUpgradePolicy. 

|Posez-vous la question|Action |
|:------------|:-------|
|Que signifie le mode TeamsOnly ? | Pour plus d’informations, consultez [les conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md).|
|||


