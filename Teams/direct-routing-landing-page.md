---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Page d’accueil pour le routage direct
appliesto:
- Microsoft Teams
ms.openlocfilehash: d643c137145649c0843296300a909c520ba653a6
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157902"
---
# <a name="phone-system-direct-routing"></a>Routage direct via le système téléphonique

Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous avez peut-être déployé des [réunions & des conférences](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes désormais prêt à ajouter des charges de travail audio Cloud et vous avez décidé d’utiliser votre propre opérateur de téléphonie pour une connectivité de réseau téléphonique commuté (PSTN) à l’aide du routage direct du système téléphonique. Avec le routage direct, vous pouvez utiliser le système téléphonique avec quasiment n’importe quel opérateur de téléphonie.

Cet article décrit les décisions de déploiement principales pour le routage direct ainsi que les considérations supplémentaires dont vous pouvez penser en fonction des besoins de votre organisation. Pour plus d’informations sur les services vocaux Cloud de Microsoft, consultez également la [voix Cloud de Microsoft teams](cloud-voice-landing-page.md) .

## <a name="learn-more-about-direct-routing"></a>En savoir plus sur le routage direct

Les articles suivants fournissent des informations supplémentaires sur la configuration et l’utilisation du routage direct du système téléphonique. La configuration du routage direct nécessite une bonne compréhension de la conception du routage PSTN. Nous vous conseillons de lire tous les articles suivants pour comprendre comment planifier et configurer le routage direct :

- [Planifier le routage direct](direct-routing-plan.md) 
- [Configurer le routage direct](direct-routing-configure.md)
- [Liste des contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md)
- [Contrôler et dépanner le routage direct](direct-routing-monitor-and-troubleshoot.md)

Par ailleurs, vous souhaiterez peut-être lire les articles suivants selon vos besoins :

-  [Configurer un contrôleur de frontière de session pour plusieurs clients](direct-routing-sbc-multiple-tenants.md)
-  [Migrer vers un routage direct](direct-routing-migrating.md)
-  [Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Regardez la session suivante pour en savoir plus sur le routage direct : [routage direct dans Microsoft teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Voici les principales décisions à prendre en considération pour le routage direct. 

|Posez-vous la question|Action |
| :------------|:-------|
|Pour quels utilisateurs le routage direct est-il activé ? | Pour plus d’informations, voir [activer les utilisateurs pour le service de routage direct](direct-routing-configure.md). |
Est-ce que je dispose des licences requises pour le routage direct ? | Pour plus d’informations, reportez-vous à la rubrique [licences et autres exigences](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considérations en matière de contrôleur de bordure de session (SBC)

Avec le routage direct, vous connectez votre propre contrôleur de bordure de session (SBC) directement au système téléphonique.  Pour obtenir la liste des [contrôleurs de frontière de session, voir prises en charge](direct-routing-border-controllers.md).

|Posez-vous la question|Action |
|:------------|:-------|
| Où et comment dois-je déployer SBCs ? | Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md) | 
Ai-je besoin de plusieurs clients ? | Pour plus d’informations, consultez [configurer un contrôleur de bordure de session pour plusieurs clients](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considérations relatives au routage vocal

Vous devez configurer le système téléphonique pour acheminer les appels vers l’objet SBCs spécifique.

|Posez-vous la question|Action |
|:------------|:-------|
| Quelles sont les stratégies de routage vocal, l’utilisation RTC et les itinéraires vocaux nécessaires ? | Pour plus d’informations sur le routage vocal, voir [configurer le routage](direct-routing-configure.md)de la voix.
| Quels utilisateurs seront attribués à la stratégie de routage vocale que j’ai définie ? | Pour plus d’exemples, voir [configurer le routage](direct-routing-configure.md)de la voix. |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Faire en sorte que les appels entrants soient dans le client teams à l’aide de TeamsUpgradePolicy

Le routage direct est uniquement pris en charge par Microsoft Teams. Pour recevoir des appels RTC via le routage direct, vous devez configurer TeamsUpgradePolicy pour vous assurer que les appels entrants sont reçus dans Teams. Les utilisateurs doivent être en mode d’équipe uniquement, ce que vous pouvez faire en leur attribuant l’instance « UpgradeToTeams » de TeamsUpgradePolicy. 

|Posez-vous la question|Action |
|:------------|:-------|
|Que signifie le mode équipes uniquement ? | Pour plus d’informations, reportez-vous à la rubrique [Guide de migration et d’interopérabilité pour les organisations qui utilisent des équipes dans Skype entreprise](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).|
|||

## <a name="additional-deployment-considerations"></a>Considérations relatives au déploiement supplémentaire

Vous voudrez peut-être prendre en compte les éléments suivants, en fonction des besoins et de la configuration de votre organisation :

| Posez-vous la question| Action |
| :------------|:-------|
| Avez-vous déjà un déploiement Skype entreprise Server avec connectivité hybride configuré ? |  Pour mieux comprendre comment le déploiement et la gestion des comptes d’utilisateurs dans un environnement hybride, voir [comptes d’utilisateurs dans un environnement hybride avec connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Migrez-vous vers le routage direct à partir d’un plan d’appels ou d’un environnement Skype entreprise local ? | Pour en savoir plus sur la migration vers le routage direct à partir d’un environnement existant, reportez-vous à la rubrique [migration vers le routage direct](direct-routing-migrating.md). |
|||
