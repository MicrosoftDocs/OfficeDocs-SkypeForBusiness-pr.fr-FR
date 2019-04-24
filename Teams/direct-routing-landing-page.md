---
title: Routage direct via le système téléphonique
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: Page d’accueil routage Direct
appliesto: Microsoft Teams
ms.openlocfilehash: 8f2e213b1e77217640f66e050f470b66f9750ef0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198091"
---
# <a name="phone-system-direct-routing"></a>Routage direct via le système téléphonique

Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Peut-être que vous avez déployé la [conférence & de réunions](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes maintenant prêt à ajouter des charges de travail de voix dans le cloud, et vous avez décidé d’utiliser votre propre opérateur de téléphonie pour la connectivité Public réseau de téléphonique commuté (RTC) à l’aide de routage d’un système téléphonique directe. Avec le routage Direct, vous pouvez utiliser le système téléphonique avec n’importe quel opérateur de téléphonie.

Cet article décrit les décisions de déploiement principaux pour le routage Direct ainsi que les considérations supplémentaires que vous souhaiterez peut-être considération, en fonction des besoins de votre organisation. Vous devez également lire [Cloud vocale dans les équipes Microsoft](cloud-voice-landing-page.md) pour plus d’informations sur les offres de voix de cloud de Microsoft.

## <a name="learn-more-about-direct-routing"></a>Pour plus d’informations sur le routage Direct

Les articles suivants fournissent plus d’informations sur la configuration et l’utilisation du routage Direct de système téléphonique. Configuration du routage Direct nécessite la compréhension de la conception du routage PSTN. Vous devez lire tous ces articles pour comprendre comment planifier et configurer le routage Direct :

- [Planifier le routage direct](direct-routing-plan.md) 
- [Configurer le routage direct](direct-routing-configure.md)
- [Liste des contrôleurs de frontière de session certifiés pour le routage direct](direct-routing-border-controllers.md)
- [Contrôler et dépanner le routage direct](direct-routing-monitor-and-troubleshoot.md)

En outre, vous pouvez souhaiter lire les articles suivants, selon vos besoins :

-  [Configurer un contrôleur de frontière de session pour plusieurs clients](direct-routing-sbc-multiple-tenants.md)
-  [Migrer vers un routage direct](direct-routing-migrating.md)
-  [Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Regarder la session suivante pour en savoir plus sur le routage Direct : [Routage Direct dans les équipes Microsoft](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Il s’agit des décisions clés à prendre en compte pour le routage Direct. 

|Posez-vous la question|Action |
| :------------|:-------|
|Pour les utilisateurs qui seront Activer routage Direct ? | Pour plus d’informations, voir [Activer les utilisateurs pour le Service de routage Direct](direct-routing-configure.md#enable-users-for-direct-routing-service). |
J’ai les licences requises pour le routage Direct ? | Pour plus d’informations, voir [licences et autres composants requis](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considérations relatives à la session contrôleur de périphérie (SBC)

Avec le routage Direct, vous vous connectez à votre propre contrôleur de Session en périphérie (SBC) directement au système téléphonique.  Pour une liste de SBC certifié, voir [Contrôleurs de frontière de Session pris en charge](direct-routing-border-controllers.md).

|Posez-vous la question|Action |
|:------------|:-------|
| Où et comment allez déployer SBCs ? | Pour plus d’informations, voir [Configurer le routage Direct](direct-routing-configure.md) | 
Je dispose de plusieurs clients ? | Pour plus d’informations, voir [configurer une Session Border Controller pour plusieurs clients](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considérations relatives au routage de voix

Vous devez configurer le système téléphonique pour acheminer les appels vers la SBC spécifique.

|Posez-vous la question|Action |
|:------------|:-------|
| Les stratégies de routage voix PSTN et d’utilisation des itinéraires ai-je besoin créer ? | Pour les informations de routage des communications vocales, voir [Configurer le routage de la voix](direct-routing-configure.md#configure-voice-routing).
| Les utilisateurs qui seront attribués à la stratégie de routage voix pour définir ? | Consultez les exemples de [Configurer Routage des communications vocales](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="calling-and-interop-policies"></a>Stratégies d’appel et interopérabilités

Routage direct est uniquement pris en charge avec Microsoft Teams. Pour passer ou recevoir des appels PSTN par le biais de routage Direct, vous devez configurer les stratégies nécessaires pour garantir les appels entrants sont reçus dans les équipes. Vous pouvez configurer les utilisateurs pour définir les équipes comme leur client par défaut pour les appels par configuration de l’utilisateur pour le mode équipes uniquement ou configurer des équipes en tant que client appelant par défaut en affectant la TeamsCallingPolicy et le TeamsInteropPolicy.

|Posez-vous la question|Action |
|:------------|:-------|
|Comment activer les équipes comme client par défaut pour les appels ? | Pour plus d’informations, voir [définir les équipes Microsoft en tant que préférable appel client pour les utilisateurs](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).|
|||

## <a name="additional-deployment-considerations"></a>Autres aspects du déploiement

Vous souhaiterez peut-être prendre en compte les éléments suivants, selon les besoins de votre organisation et la configuration :

| Posez-vous la question| Action |
| :------------|:-------|
| Vous avez un Skype existant pour le déploiement de serveur d’entreprise avec connectivité hybride configurée ? |  Pour comprendre comment les comptes d’utilisateurs dans un environnement hybride sont mis en service et gérées, voir [comptes d’utilisateurs dans un environnement hybride avec une connectivité PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Vous migrez vers routage Direct à partir de l’appel de planifier ou d’un Skype pour un environnement sur site ? | Pour en savoir plus sur la migration vers routage Direct à partir d’un environnement existant, consultez [migration vers routage Direct](direct-routing-migrating.md). |
|||
