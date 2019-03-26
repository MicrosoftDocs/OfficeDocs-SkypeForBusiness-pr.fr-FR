---
title: Expérience client Teams et conformité aux modes coexistence
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Équipes de l’expérience client et comformance aux modes de coexistence
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6972a09a169560d255c2bb118f80dbbdfb2c7f4f
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800131"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Expérience client Teams et conformité aux modes coexistence

> [!NOTE]
> Cette page décrit des modifications à venir importantes dans le comportement du client équipes lorsque vous êtes dans une de le Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


L’objectif des modes de coexistence est de fournir une expérience prévisible simple pour les utilisateurs finaux en tant que la transition des organisations de Skype pour les entreprises aux équipes.  Pour une organisation déplacement aux équipes, le mode TeamsOnly est la destination finale pour chaque utilisateur, même si tous les utilisateurs ne doivent être attribués TeamsOnly (ou tout autre mode) en même temps.  Avant d’atteindre le mode TeamsOnly des utilisateurs, organisations peuvent utiliser de la Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour assurer la communication entre les utilisateurs qui sont TeamsOnly et ceux qui ne sont pas encore prévisible. 

Lorsqu’un utilisateur est dans un de la Skype pour les modes d’entreprise, toutes les conversations entrantes et les appels sont routés vers Skype l’utilisateur pour client d’entreprise. Pour éviter toute confusion d’utilisateur final et garantir un routage correct, fonctionnalités d’appel et de conversation dans le client d’équipes sont destinées à être désactivée lorsqu’un utilisateur est dans un de la Skype pour les modes d’entreprise. De même, planifier des réunions dans les équipes est destiné à être désactivé lorsque vous êtes dans les modes SfBOnly ou SfBWithTeamsCollab et explicitement activée lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.  Pour désactiver automatiquement la fonctionnalité de conversation et appel de fonctionnalités, ainsi que d’activer/désactiver basée sur le mode de planification de la réunion démarre au déploiement pour les clients appuyez sur.  

Avant de cette fonctionnalité, les conseils de Microsoft a été pour s’assurer de l’expérience utilisateur en définissant les paramètres correspondants dans la messagerie, l’appel et stratégies de réunion. Toutefois, aucune application formelle du présent s’est produite et dans la mesure où les utilisateurs par défaut a rencontré un accès total à toutes les fonctionnalités dans le client d’équipes, certains utilisateurs peuvent conserver l’accès à tout ou partie de ces expériences dans le client d’équipes, quelle que soit leur mode.  Par conséquent, comme cette fonctionnalité déploie, un utilisateur peut afficher une modification de leur expérience dans le client équipes comme l’expérience utilisateur commence à être conforme à leur mode.  Le tableau ci-dessous présente le nouveau comportement :


|Mode efficace de l’utilisateur|Expérience client d’équipes|
|---|---|
|N’importe quel Skype pour le mode d’entreprise|L’appel et de conversation<sup>1</sup> sont désactivées.|
|SfBWithTeamsCollabAndMeetings|Planification de la réunion est disponible|
|SfBWithTeamsCollab ou SfBOnly<sup>2</sup>|Planification de la réunion n’est pas disponible|
|||

**Remarques :**
<sup>1</sup> session est toujours disponible.

<sup>2</sup> pour l’instant, SfBwithTeamsCollab et SfBOnly ont les mêmes, mais l’objectif est de mode SfBOnly également désactiver la fonctionnalité de canaux et les fichiers dans les équipes ; Toutefois, il n’existe actuellement aucun paramètre qui permet cette fonctionnalité dans les équipes à désactiver.


## <a name="how-organizations-can-prepare-for-automatic-ux-conformance-to-modes"></a>Comment les organisations peuvent préparer pour la conformité UX automatique modes

Avant cette modification présentant, les organisations peuvent bénéficier de l’expérience de votre choix dans le client équipes à l’aide des stratégies supplémentaires, comme décrit dans cette section. Cela garantit que le déploiement est transparent pour les utilisateurs finaux. Notez qu’une fois que la modification déploie, définir ces stratégies ne sera pas nécessaire.  Également, les organisations qui ne voulez pas que les utilisateurs ont des fonctionnalités dans le client équipes réduites peuvent se déplacer leurs utilisateurs au mode (îles) ou TeamsOnly, mais qui aura une incidence sur le routage ainsi que.

Pour configurer manuellement l’expérience utilisateur, les administrateurs utilisent les stratégies et les paramètres suivants :


|**Modalité (application)**|**Policy.Setting**|
|---|---|
|Conversation|TeamsMessagingPolicy.AllowUserChat|
|Appels|TeamsCallingPolicy.AllowPrivateCalling|
|Planification de la réunion|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||


Les administrateurs doivent définir chacun de ces paramètres pour les valeurs suivantes pour un mode donné :

|Mode|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou (îles)|Activé|Activé|Activé|Activé|
|SfBWithTeamsCollabAndMeetings|Désactivé|Désactivé|Activé|Activé|
|SfBWithTeamsCollab ou SfBOnly|Désactivé|Désactivé|Désactivé|Désactivé|
||||||

Avant le déploiement de la mise en conformité automatique de l’expérience utilisateur basée sur les modes, le `Grant-CsTeamsUpgradePolicy` cmdlet vérifie la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces les paramètres sont compatibles avec le mode spécifié. Si les ne sont pas configurés correctement, l’octroi réussira, mais un avertissement sera communiquée dans PowerShell indiquant les paramètres spécifiques ne sont pas configurés correctement. Voici un exemple de ce que l’avertissement PowerShell pourrait ressembler à :

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.`

À l’affichage de cet avertissement, l’administrateur doit ensuite mettre à jour les stratégies indiqués afin d’offrir une expérience utilisateur final compatible dans les équipes. Si l’administrateur décide de vous n’avez rien à la suite de l’avertissement, les utilisateurs peuvent toujours accéder à la conversation, appel et/ou des fonctions de planification dans les équipes en fonction des valeurs de TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy, de la réunion qui peut entraîner une expérience utilisateur final confus.

Une fois la mise en conformité automatique de l’expérience du client équipes basée sur le mode TeamsUpgradePolicy est disponible, il ne sera plus nécessaire de définir ces stratégies. La valeur de mode TeamsUpgradePolicy ont priorité sur les valeurs de ces paramètres spécifiques. Mise en conformité automatique est effectuée lors de la résolution de la stratégie à l’infrastructure de stratégie. En cas de conflit des paramètres différents, le comportement basé sur le mode emporte sur les valeurs de AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling et AllowChannelMeetingScheduling. Une fois la mise en conformité automatique est remis, les avertissements PowerShell seront mis à jour pour informer l’administrateur que l’expérience du client sera automatiquement appliquée, en dépit de toutes les valeurs de TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy.







